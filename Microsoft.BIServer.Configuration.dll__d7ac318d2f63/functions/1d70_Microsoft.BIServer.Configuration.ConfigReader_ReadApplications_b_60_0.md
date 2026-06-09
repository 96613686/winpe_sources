# Microsoft.BIServer.Configuration.ConfigReader::<ReadApplications>b__60_0

- ea: `0x1d70`
- end: `0x1dea`
- name: `Microsoft.BIServer.Configuration.ConfigReader::<ReadApplications>b__60_0`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1610`
- `0x1d70`
- `0x4790`

## string_xrefs

- `0x1dd3`: `VirtualDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.0
0x1d71  ldarg.1
0x1d72  ldstr    aUrls// "URLs"
0x1d77  ldstr    aUrlsUnderAppli// "URLs under Application"
0x1d7c  call     T0x2B000012
0x1d81  pop
0x1d82  ldarg.0
0x1d83  ldarg.1
0x1d84  ldstr    aUrlsUrl// "URLs/URL"
0x1d89  call     T0x2B00000F
0x1d8e  stloc.0
0x1d8f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.URL>::.ctor()
0x1d94  stloc.1
0x1d95  ldloc.0
0x1d96  brfalse.s loc_1DC6
0x1d98  ldloc.0
0x1d99  call     T0x2B000010
0x1d9e  brfalse.s loc_1DC6
0x1da0  ldloc.0
0x1da1  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.BIServer.Configuration.URL> <>c::<>9__60_1
0x1da6  dup
0x1da7  brtrue.s loc_1DC0
0x1da9  pop
0x1daa  ldsfld   class <>c <>c::<>9
0x1daf  ldftn    instance class Microsoft.BIServer.Configuration.URL <>c::<ReadApplications>b__60_1(class [System.Xml.Linq]System.Xml.Linq.XElement urlEntry)
0x1db5  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.BIServer.Configuration.URL>::.ctor(object, native int)
0x1dba  dup
0x1dbb  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.BIServer.Configuration.URL> <>c::<>9__60_1
0x1dc0  call     T0x2B000021
0x1dc5  stloc.1
0x1dc6  ldarg.1
0x1dc7  ldstr    aName// "Name"
0x1dcc  ldc.i4.1
0x1dcd  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x1dd2  ldarg.1
0x1dd3  ldstr    aVirtualdirecto// "VirtualDirectory"
0x1dd8  ldc.i4.1
0x1dd9  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x1dde  ldloc.1
0x1ddf  call     T0x2B000022
0x1de4  newobj   instance void Microsoft.BIServer.Configuration.Application::.ctor(string name, string virtualDirectory, class Microsoft.BIServer.Configuration.URL[] urls)
0x1de9  ret
```
