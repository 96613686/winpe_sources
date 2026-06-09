# Microsoft.BIServer.Configuration.ConfigReader::.ctor_1

- ea: `0x1220`
- end: `0x1248`
- name: `Microsoft.BIServer.Configuration.ConfigReader::.ctor_1`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1220`
- `0x12f0`
- `0x3d60`

## pseudocode

```c

```

## disassembly

```asm
0x1220  ldarg.0
0x1221  call     instance void [mscorlib]System.Object::.ctor()
0x1226  ldarg.0
0x1227  ldarg.1
0x1228  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(class [mscorlib]System.IO.Stream)
0x122d  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1232  ldarg.2
0x1233  brfalse.s loc_1241
0x1235  ldarg.0
0x1236  ldarg.2
0x1237  newobj   instance void Microsoft.BIServer.Configuration.WebConfigFile::.ctor(string webConfigFilePath)
0x123c  stfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1241  ldarg.0
0x1242  call     instance void Microsoft.BIServer.Configuration.ConfigReader::Init()
0x1247  ret
```
