# <GetProofKeyValues>d__7::MoveNext

- ea: `0x6c70`
- end: `0x6d20`
- name: `<GetProofKeyValues>d__7::MoveNext`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x560`
- `0x690`
- `0x6d0`
- `0x6c70`

## pseudocode

```c

```

## disassembly

```asm
0x6c70  ldarg.0
0x6c71  ldfld    int32 <GetProofKeyValues>d__7::<>1__state
0x6c76  stloc.0
0x6c77  ldarg.0
0x6c78  ldfld    class Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration <GetProofKeyValues>d__7::<>4__this
0x6c7d  stloc.1
0x6c7e  ldloc.0
0x6c7f  brfalse.s loc_6CB8
0x6c81  ldloc.1
0x6c82  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Xml]System.Xml.XmlDocument> Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetDocument()
0x6c87  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Xml]System.Xml.XmlDocument>::GetAwaiter()
0x6c8c  stloc.s  4
0x6c8e  ldloca.s 4
0x6c90  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>::get_IsCompleted()
0x6c95  brtrue.s loc_6CD5
0x6c97  ldarg.0
0x6c98  ldc.i4.0
0x6c99  dup
0x6c9a  stloc.0
0x6c9b  stfld    int32 <GetProofKeyValues>d__7::<>1__state
0x6ca0  ldarg.0
0x6ca1  ldloc.s  4
0x6ca3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetProofKeyValues>d__7::<>u__1
0x6ca8  ldarg.0
0x6ca9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.Configuration.OfficeProofKeyValues> <GetProofKeyValues>d__7::<>t__builder
0x6cae  ldloca.s 4
0x6cb0  ldarg.0
0x6cb1  call     T0x2B00003F
0x6cb6  leave.s  loc_6D1F
0x6cb8  ldarg.0
0x6cb9  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetProofKeyValues>d__7::<>u__1
0x6cbe  stloc.s  4
0x6cc0  ldarg.0
0x6cc1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetProofKeyValues>d__7::<>u__1
0x6cc6  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>
0x6ccc  ldarg.0
0x6ccd  ldc.i4.m1
0x6cce  dup
0x6ccf  stloc.0
0x6cd0  stfld    int32 <GetProofKeyValues>d__7::<>1__state
0x6cd5  ldloca.s 4
0x6cd7  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>::GetResult()
0x6cdc  call     class [System.Xml]System.Xml.XmlNode Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetProofKeyNode(class [System.Xml]System.Xml.XmlDocument xmlDoc)
0x6ce1  stloc.3
0x6ce2  ldloc.3
0x6ce3  brfalse.s loc_6CEE
0x6ce5  ldloc.3
0x6ce6  call     class Microsoft.BIServer.Configuration.OfficeProofKeyValues Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetProofKeyValues(class [System.Xml]System.Xml.XmlNode proofKeyNode)
0x6ceb  stloc.2
0x6cec  leave.s  loc_6D0B
0x6cee  ldnull
0x6cef  stloc.2
0x6cf0  leave.s  loc_6D0B
0x6cf2  stloc.s  5
0x6cf4  ldarg.0
0x6cf5  ldc.i4.s 0xFE
0x6cf7  stfld    int32 <GetProofKeyValues>d__7::<>1__state
0x6cfc  ldarg.0
0x6cfd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.Configuration.OfficeProofKeyValues> <GetProofKeyValues>d__7::<>t__builder
0x6d02  ldloc.s  5
0x6d04  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.Configuration.OfficeProofKeyValues>::SetException(class [mscorlib]System.Exception)
0x6d09  leave.s  loc_6D1F
0x6d0b  ldarg.0
0x6d0c  ldc.i4.s 0xFE
0x6d0e  stfld    int32 <GetProofKeyValues>d__7::<>1__state
0x6d13  ldarg.0
0x6d14  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.Configuration.OfficeProofKeyValues> <GetProofKeyValues>d__7::<>t__builder
0x6d19  ldloc.2
0x6d1a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.Configuration.OfficeProofKeyValues>::SetResult(var<u1>)
0x6d1f  ret
```
