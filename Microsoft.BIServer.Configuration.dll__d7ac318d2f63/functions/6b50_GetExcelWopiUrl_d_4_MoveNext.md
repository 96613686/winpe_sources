# <GetExcelWopiUrl>d__4::MoveNext

- ea: `0x6b50`
- end: `0x6c00`
- name: `<GetExcelWopiUrl>d__4::MoveNext`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x560`
- `0x5e0`
- `0x610`
- `0x6b50`

## pseudocode

```c

```

## disassembly

```asm
0x6b50  ldarg.0
0x6b51  ldfld    int32 <GetExcelWopiUrl>d__4::<>1__state
0x6b56  stloc.0
0x6b57  ldarg.0
0x6b58  ldfld    class Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration <GetExcelWopiUrl>d__4::<>4__this
0x6b5d  stloc.1
0x6b5e  ldloc.0
0x6b5f  brfalse.s loc_6B98
0x6b61  ldloc.1
0x6b62  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Xml]System.Xml.XmlDocument> Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetDocument()
0x6b67  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Xml]System.Xml.XmlDocument>::GetAwaiter()
0x6b6c  stloc.s  4
0x6b6e  ldloca.s 4
0x6b70  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>::get_IsCompleted()
0x6b75  brtrue.s loc_6BB5
0x6b77  ldarg.0
0x6b78  ldc.i4.0
0x6b79  dup
0x6b7a  stloc.0
0x6b7b  stfld    int32 <GetExcelWopiUrl>d__4::<>1__state
0x6b80  ldarg.0
0x6b81  ldloc.s  4
0x6b83  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetExcelWopiUrl>d__4::<>u__1
0x6b88  ldarg.0
0x6b89  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <GetExcelWopiUrl>d__4::<>t__builder
0x6b8e  ldloca.s 4
0x6b90  ldarg.0
0x6b91  call     T0x2B00003E
0x6b96  leave.s  loc_6BFF
0x6b98  ldarg.0
0x6b99  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetExcelWopiUrl>d__4::<>u__1
0x6b9e  stloc.s  4
0x6ba0  ldarg.0
0x6ba1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument> <GetExcelWopiUrl>d__4::<>u__1
0x6ba6  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>
0x6bac  ldarg.0
0x6bad  ldc.i4.m1
0x6bae  dup
0x6baf  stloc.0
0x6bb0  stfld    int32 <GetExcelWopiUrl>d__4::<>1__state
0x6bb5  ldloca.s 4
0x6bb7  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Xml]System.Xml.XmlDocument>::GetResult()
0x6bbc  call     class [System.Xml]System.Xml.XmlNode Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetHighestPriorityNetZoneNode(class [System.Xml]System.Xml.XmlDocument xmlDoc)
0x6bc1  stloc.3
0x6bc2  ldloc.3
0x6bc3  brfalse.s loc_6BCE
0x6bc5  ldloc.3
0x6bc6  call     class [System]System.Uri Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetExcelWopiUrl(class [System.Xml]System.Xml.XmlNode netZoneNode)
0x6bcb  stloc.2
0x6bcc  leave.s  loc_6BEB
0x6bce  ldnull
0x6bcf  stloc.2
0x6bd0  leave.s  loc_6BEB
0x6bd2  stloc.s  5
0x6bd4  ldarg.0
0x6bd5  ldc.i4.s 0xFE
0x6bd7  stfld    int32 <GetExcelWopiUrl>d__4::<>1__state
0x6bdc  ldarg.0
0x6bdd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <GetExcelWopiUrl>d__4::<>t__builder
0x6be2  ldloc.s  5
0x6be4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri>::SetException(class [mscorlib]System.Exception)
0x6be9  leave.s  loc_6BFF
0x6beb  ldarg.0
0x6bec  ldc.i4.s 0xFE
0x6bee  stfld    int32 <GetExcelWopiUrl>d__4::<>1__state
0x6bf3  ldarg.0
0x6bf4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <GetExcelWopiUrl>d__4::<>t__builder
0x6bf9  ldloc.2
0x6bfa  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri>::SetResult(var<u1>)
0x6bff  ret
```
