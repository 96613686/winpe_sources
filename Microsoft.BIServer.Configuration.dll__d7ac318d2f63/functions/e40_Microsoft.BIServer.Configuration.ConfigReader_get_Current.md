# Microsoft.BIServer.Configuration.ConfigReader::get_Current

- ea: `0xe40`
- end: `0xe80`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_Current`
- size: `64`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f90`
- `0x3130`
- `0x60e0`
- `0x67f0`

## callees

- `0xe40`
- `0xe80`
- `0x1100`

## string_xrefs

- `0xe4c`: `rsConfigFilePath`
- `0xe64`: `Exception thrown while reading configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldsfld   class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::_global
0xe45  brtrue.s loc_E7A
0xe47  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xe4c  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0xe51  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException(string)
0xe56  newobj   instance void Microsoft.BIServer.Configuration.ConfigReader::.ctor(string configFileFullPath)
0xe5b  call     void Microsoft.BIServer.Configuration.ConfigReader::set_Current(class Microsoft.BIServer.Configuration.ConfigReader value)
0xe60  leave.s  loc_E7A
0xe62  stloc.0
0xe63  ldloc.0
0xe64  ldstr    aExceptionThrow// "Exception thrown while reading configur"...
0xe69  ldc.i4.1
0xe6a  newarr   [mscorlib]System.Object
0xe6f  dup
0xe70  ldc.i4.0
0xe71  ldloc.0
0xe72  stelem.ref
0xe73  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0xe78  rethrow
0xe7a  ldsfld   class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::_global
0xe7f  ret
```
