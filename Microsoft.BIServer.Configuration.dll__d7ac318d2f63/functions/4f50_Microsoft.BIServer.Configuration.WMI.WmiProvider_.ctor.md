# Microsoft.BIServer.Configuration.WMI.WmiProvider::.ctor

- ea: `0x4f50`
- end: `0x4f97`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::.ctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4f50`
- `0x5560`

## string_xrefs

- `0x4f74`: `Attempting to create WMI provider, MOF file '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x4f50  ldarg.0
0x4f51  ldsfld   string [mscorlib]System.String::Empty
0x4f56  stfld    string Microsoft.BIServer.Configuration.WMI.WmiProvider::_mofFile
0x4f5b  ldarg.0
0x4f5c  call     instance void [mscorlib]System.Object::.ctor()
0x4f61  ldarg.1
0x4f62  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f67  brfalse.s loc_4F74
0x4f69  ldstr    aMoffile// "mofFile"
0x4f6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f73  throw
0x4f74  ldstr    aAttemptingToCr// "Attempting to create WMI provider, MOF "...
0x4f79  ldc.i4.1
0x4f7a  newarr   [mscorlib]System.Object
0x4f7f  dup
0x4f80  ldc.i4.0
0x4f81  ldarg.1
0x4f82  stelem.ref
0x4f83  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x4f88  ldarg.0
0x4f89  ldarg.1
0x4f8a  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::VerifyFullPath(string filePath)
0x4f8f  ldarg.0
0x4f90  ldarg.1
0x4f91  stfld    string Microsoft.BIServer.Configuration.WMI.WmiProvider::_mofFile
0x4f96  ret
```
