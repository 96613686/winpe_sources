# Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetDocument

- ea: `0x560`
- end: `0x599`
- name: `Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetDocument`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6b50`
- `0x6c70`

## pseudocode

```c

```

## disassembly

```asm
0x560  ldloca.s 0
0x562  ldarg.0
0x563  stfld    class Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration <GetDocument>d__3::<>4__this
0x568  ldloca.s 0
0x56a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument>::Create()
0x56f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x574  ldloca.s 0
0x576  ldc.i4.m1
0x577  stfld    int32 <GetDocument>d__3::<>1__state
0x57c  ldloc.0
0x57d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x582  stloc.1
0x583  ldloca.s 1
0x585  ldloca.s 0
0x587  call     T0x2B000002
0x58c  ldloca.s 0
0x58e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x593  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument>::get_Task()
0x598  ret
```
