# Microsoft.BIServer.Configuration.ConfigReader::.ctor_0

- ea: `0x1180`
- end: `0x121b`
- name: `Microsoft.BIServer.Configuration.ConfigReader::.ctor_0`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1180`
- `0x12f0`
- `0x3d60`
- `0x78a0`

## string_xrefs

- `0x1186`: `Attempting to read Configuration from file {0} -> {1}`
- `0x11ab`: `Missing file at path {0}`
- `0x11e6`: `Missing file at path {0}`
- `0x11c1`: `Attempting to read Web Configuration from file {0} -> {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldarg.0
0x1181  call     instance void [mscorlib]System.Object::.ctor()
0x1186  ldstr    aAttemptingToRe// "Attempting to read Configuration from f"...
0x118b  ldc.i4.2
0x118c  newarr   [mscorlib]System.Object
0x1191  dup
0x1192  ldc.i4.0
0x1193  ldarg.1
0x1194  stelem.ref
0x1195  dup
0x1196  ldc.i4.1
0x1197  ldarg.1
0x1198  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x119d  stelem.ref
0x119e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x11a3  ldarg.1
0x11a4  call     bool [mscorlib]System.IO.File::Exists(string)
0x11a9  brtrue.s loc_11C1
0x11ab  ldstr    aMissingFileAtP// "Missing file at path {0}"
0x11b0  ldarg.1
0x11b1  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x11b6  call     string [mscorlib]System.String::Format(string, object)
0x11bb  newobj   instance void MissingConfigFile::.ctor(string message)
0x11c0  throw
0x11c1  ldstr    aAttemptingToRe_0// "Attempting to read Web Configuration fr"...
0x11c6  ldc.i4.2
0x11c7  newarr   [mscorlib]System.Object
0x11cc  dup
0x11cd  ldc.i4.0
0x11ce  ldarg.2
0x11cf  stelem.ref
0x11d0  dup
0x11d1  ldc.i4.1
0x11d2  ldarg.2
0x11d3  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x11d8  stelem.ref
0x11d9  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x11de  ldarg.2
0x11df  call     bool [mscorlib]System.IO.File::Exists(string)
0x11e4  brtrue.s loc_11FC
0x11e6  ldstr    aMissingFileAtP// "Missing file at path {0}"
0x11eb  ldarg.2
0x11ec  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x11f1  call     string [mscorlib]System.String::Format(string, object)
0x11f6  newobj   instance void MissingConfigFile::.ctor(string message)
0x11fb  throw
0x11fc  ldarg.0
0x11fd  ldarg.1
0x11fe  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x1203  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1208  ldarg.0
0x1209  ldarg.2
0x120a  newobj   instance void Microsoft.BIServer.Configuration.WebConfigFile::.ctor(string webConfigFilePath)
0x120f  stfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1214  ldarg.0
0x1215  call     instance void Microsoft.BIServer.Configuration.ConfigReader::Init()
0x121a  ret
```
