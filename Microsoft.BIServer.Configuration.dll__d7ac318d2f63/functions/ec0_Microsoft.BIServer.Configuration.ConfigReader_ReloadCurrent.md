# Microsoft.BIServer.Configuration.ConfigReader::ReloadCurrent

- ea: `0xec0`
- end: `0xeeb`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReloadCurrent`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe80`
- `0xec0`
- `0x1100`

## string_xrefs

- `0xed4`: `Exception thrown while reading configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldarg.0
0xec1  ldfld    string Microsoft.BIServer.Configuration.ConfigReader::_configFileFullPath
0xec6  newobj   instance void Microsoft.BIServer.Configuration.ConfigReader::.ctor(string configFileFullPath)
0xecb  call     void Microsoft.BIServer.Configuration.ConfigReader::set_Current(class Microsoft.BIServer.Configuration.ConfigReader value)
0xed0  leave.s  loc_EEA
0xed2  stloc.0
0xed3  ldloc.0
0xed4  ldstr    aExceptionThrow// "Exception thrown while reading configur"...
0xed9  ldc.i4.1
0xeda  newarr   [mscorlib]System.Object
0xedf  dup
0xee0  ldc.i4.0
0xee1  ldloc.0
0xee2  stelem.ref
0xee3  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0xee8  rethrow
0xeea  ret
```
