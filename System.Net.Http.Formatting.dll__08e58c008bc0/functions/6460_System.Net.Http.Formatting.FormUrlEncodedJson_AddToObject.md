# System.Net.Http.Formatting.FormUrlEncodedJson::AddToObject

- ea: `0x6460`
- end: `0x657b`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::AddToObject`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6360`

## callees

- `0x3390`
- `0x3530`
- `0x6460`
- `0x65e0`
- `0x6890`
- `0xb330`

## pseudocode

```c

```

## disassembly

```asm
0x6460  ldarg.1
0x6461  ldlen
0x6462  conv.i4
0x6463  ldc.i4.1
0x6464  sub
0x6465  stloc.0
0x6466  ldarg.1
0x6467  ldloc.0
0x6468  ldelem.ref
0x6469  stloc.1
0x646a  ldarg.0
0x646b  ldloc.1
0x646c  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::ContainsKey(var<u1>)
0x6471  brfalse  loc_655F
0x6476  ldarg.0
0x6477  ldloc.1
0x6478  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x647d  brfalse.s loc_648F
0x647f  ldarg.0
0x6480  ldloc.1
0x6481  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x6486  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x648b  ldc.i4.s 0xA
0x648d  bne.un.s loc_64AC
0x648f  ldarg.3
0x6490  brfalse.s loc_64AA
0x6492  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedMismatchingTypes()
0x6497  ldarg.1
0x6498  ldloc.0
0x6499  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x649e  ldc.i4.0
0x649f  newarr   [mscorlib]System.Object
0x64a4  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x64a9  throw
0x64aa  ldc.i4.0
0x64ab  ret
0x64ac  ldarg.1
0x64ad  ldlen
0x64ae  conv.i4
0x64af  ldc.i4.1
0x64b0  ceq
0x64b2  brfalse  loc_6542
0x64b7  ldarg.0
0x64b8  ldloc.1
0x64b9  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x64be  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x64c3  ldc.i4.8
0x64c4  bne.un.s loc_6505
0x64c6  ldarg.0
0x64c7  ldloc.1
0x64c8  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x64cd  callvirt T0x2B000045
0x64d2  stloc.2
0x64d3  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x64d8  stloc.3
0x64d9  ldloc.3
0x64da  ldstr    a0// "0"
0x64df  ldloc.2
0x64e0  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Implicit(string)
0x64e5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Add(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x64ea  ldloc.3
0x64eb  ldstr    a1// "1"
0x64f0  ldarg.2
0x64f1  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Implicit(string)
0x64f6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Add(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x64fb  ldarg.0
0x64fc  ldloc.1
0x64fd  ldloc.3
0x64fe  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::set_Item(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x6503  br.s     loc_6579
0x6505  ldarg.0
0x6506  ldloc.1
0x6507  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x650c  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x6511  brfalse.s loc_6579
0x6513  ldarg.0
0x6514  ldloc.1
0x6515  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x651a  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x651f  stloc.s  4
0x6521  ldloc.s  4
0x6523  ldarg.3
0x6524  call     string System.Net.Http.Formatting.FormUrlEncodedJson::GetIndex(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject jsonObject, bool throwOnError)
0x6529  stloc.s  5
0x652b  ldloc.s  5
0x652d  brtrue.s loc_6531
0x652f  ldc.i4.0
0x6530  ret
0x6531  ldloc.s  4
0x6533  ldloc.s  5
0x6535  ldarg.2
0x6536  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Implicit(string)
0x653b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Add(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x6540  br.s     loc_6579
0x6542  ldarg.3
0x6543  brfalse.s loc_655D
0x6545  call     string System.Net.Http.Properties.Resources::get_JQuery13CompatModeNotSupportNestedJson()
0x654a  ldarg.1
0x654b  ldloc.0
0x654c  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x6551  ldc.i4.0
0x6552  newarr   [mscorlib]System.Object
0x6557  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x655c  throw
0x655d  ldc.i4.0
0x655e  ret
0x655f  ldarg.2
0x6560  brtrue.s loc_656C
0x6562  ldarg.0
0x6563  ldloc.1
0x6564  ldnull
0x6565  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::set_Item(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x656a  br.s     loc_6579
0x656c  ldarg.0
0x656d  ldloc.1
0x656e  ldarg.2
0x656f  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Implicit(string)
0x6574  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::set_Item(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x6579  ldc.i4.1
0x657a  ret
```
