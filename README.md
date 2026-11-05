import React,{useState} from 'react';
import {View,Text,TextInput,Button} from 'react-native';

export default function App(){
 const [h,H]=useState('');
 const [w,W]=useState('');
 const [b,B]=useState('');

 function calculate(){
  let n=Number(w)/(Number(h)/100)**2;
  B(!h||!w||!isFinite(n)?'Invalid':n.toFixed(2));
 }

 return <View>
  <Text>BMI Calculator</Text>
  <TextInput placeholder="Height (cm)" onChangeText={H}/>
  <TextInput placeholder="Weight (kg)" onChangeText={W}/>
  <Button title="Calculate" onPress={calculate}/>
  <Text>BMI: {b}</Text>
 </View>;
}

import React,{useState} from 'react';
import {View,Text,TextInput,Button} from 'react-native';

export default function App(){
 const [a,A]=useState('');
 const [i,I]=useState(0);
 const [e,E]=useState(0);

 return <View>
  <Text>Expense Manager</Text>
  <TextInput placeholder="Amount" onChangeText={A}/>
  <Button title="Income" onPress={()=>I(i+Number(a))}/>
  <Button title="Expense" onPress={()=>E(e+Number(a))}/>
  <Text>Income: {i}</Text>
  <Text>Expense: {e}</Text>
  <Text>Balance: {i-e}</Text>
 </View>;
}

import React,{useState} from 'react';
import {View,Text,TextInput,Button} from 'react-native';

export default function App(){
 const [v,V]=useState('');
 const [r,R]=useState('');

 return <View>
  <Text>Unit Converter</Text>
  <TextInput placeholder="Enter value" onChangeText={V}/>
  <Button title="KM to Miles" onPress={()=>R(v*0.621371)}/>
  <Button title="Miles to KM" onPress={()=>R(v*1.60934)}/>
  <Button title="KG to Pounds" onPress={()=>R(v*2.20462)}/>
  <Button title="Pounds to KG" onPress={()=>R(v*0.453592)}/>
  <Text>Result: {r}</Text>
 </View>;
}

import React,{useState} from 'react';
import {View,Text,TextInput,Button} from 'react-native';

export default function App(){
 const [h,H]=useState('');
 const [w,W]=useState('');
 const [b,B]=useState('');

 function calculate(){
  let n=Number(w)/(Number(h)/100)**2;
  B(!h||!w||!isFinite(n)?'Invalid':n.toFixed(2));
 }

 return <View>
  <Text>BMI Calculator</Text>
  <TextInput placeholder="Height (cm)" onChangeText={H}/>
  <TextInput placeholder="Weight (kg)" onChangeText={W}/>
  <Button title="Calculate" onPress={calculate}/>
  <Text>BMI: {b}</Text>
 </View>;
}

import React, { useState } from 'react';
import { View, Text, TouchableOpacity, StyleSheet } from 'react-native';
import * as Location from 'expo-location';

export default function App() {
  const [location, setLocation] = useState('Location will appear here');

  const getLocation = async () => {
    let { status } = await Location.requestForegroundPermissionsAsync();
    if (status !== 'granted') {
      setLocation('Permission denied');
      return;
    }
    let loc = await Location.getCurrentPositionAsync({});
    setLocation(`Latitude: ${loc.coords.latitude}\nLongitude: ${loc.coords.longitude}`);
  };

  return (
    <View style={styles.container}>
      <Text style={styles.title}>Location Finder</Text>
      <TouchableOpacity style={styles.btn} onPress={getLocation}>
        <Text style={styles.btnText}>Get Location</Text>
      </TouchableOpacity>
      <Text style={styles.result}>{location}</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: 'center', alignItems: 'center', backgroundColor: '#f4f7fb', padding: 20 },
  title: { fontSize: 24, fontWeight: 'bold', color: '#2563eb', marginBottom: 10 },
  btn: { padding: 12, backgroundColor: '#2563eb', borderRadius: 10, marginTop: 20 },
  btnText: { color: '#fff', fontWeight: 'bold' },
  result: { marginTop: 20, fontSize: 16, textAlign: 'center' }
});
