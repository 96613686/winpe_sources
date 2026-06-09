# Microsoft.BIServer.Configuration.ConfigReader::.ctor

- ea: `0x1100`
- end: `0x1176`
- name: `Microsoft.BIServer.Configuration.ConfigReader::.ctor`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe40`
- `0xec0`

## callees

- `0x1100`
- `0x12f0`
- `0x3d60`
- `0x78a0`

## string_xrefs

- `0x1106`: `Attempting to read Configuration from file {0} -> {1}`
- `0x112b`: `Missing file at path {0}`
- `0x1156`: `rsreportserver.config`
- `0x115b`: `web.config`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldarg.0
0x1101  call     instance void [mscorlib]System.Object::.ctor()
0x1106  ldstr    aAttemptingToRe// "Attempting to read Configuration from f"...
0x110b  ldc.i4.2
0x110c  newarr   [mscorlib]System.Object
0x1111  dup
0x1112  ldc.i4.0
0x1113  ldarg.1
0x1114  stelem.ref
0x1115  dup
0x1116  ldc.i4.1
0x1117  ldarg.1
0x1118  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x111d  stelem.ref
0x111e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x1123  ldarg.1
0x1124  call     bool [mscorlib]System.IO.File::Exists(string)
0x1129  brtrue.s loc_1141
0x112b  ldstr    aMissingFileAtP// "Missing file at path {0}"
0x1130  ldarg.1
0x1131  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x1136  call     string [mscorlib]System.String::Format(string, object)
0x113b  newobj   instance void MissingConfigFile::.ctor(string message)
0x1140  throw
0x1141  ldarg.0
0x1142  ldarg.1
0x1143  stfld    string Microsoft.BIServer.Configuration.ConfigReader::_configFileFullPath
0x1148  ldarg.0
0x1149  ldarg.1
0x114a  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x114f  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1154  ldarg.0
0x1155  ldarg.1
0x1156  ldstr    aRsreportserver// "rsreportserver.config"
0x115b  ldstr    aWebConfig// "web.config"
0x1160  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1165  newobj   instance void Microsoft.BIServer.Configuration.WebConfigFile::.ctor(string webConfigFilePath)
0x116a  stfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x116f  ldarg.0
0x1170  call     instance void Microsoft.BIServer.Configuration.ConfigReader::Init()
0x1175  ret
```
