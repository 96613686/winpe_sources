# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult

- ea: `0x600`
- end: `0x65b`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4a0`

## callees

- `0x600`
- `0x6c0`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldarg.0
0x601  ldsfld   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus> Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::LastLoggedStatus
0x606  stloc.0
0x607  ldloca.s 0
0x609  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::GetValueOrDefault()
0x60e  beq.s    loc_613
0x610  ldc.i4.1
0x611  br.s     loc_61D
0x613  ldloca.s 0
0x615  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::get_HasValue()
0x61a  ldc.i4.0
0x61b  ceq
0x61d  brfalse.s loc_659
0x61f  ldarg.0
0x620  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::.ctor(var<u1>)
0x625  stsfld   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus> Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::LastLoggedStatus
0x62a  ldstr    aDatabaseVersio// "Database Version Detection: {0}\n    Db"...
0x62f  ldc.i4.4
0x630  newarr   [mscorlib]System.Object
0x635  dup
0x636  ldc.i4.0
0x637  ldarg.1
0x638  stelem.ref
0x639  dup
0x63a  ldc.i4.1
0x63b  ldarg.2
0x63c  call     string Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull(object obj)
0x641  stelem.ref
0x642  dup
0x643  ldc.i4.2
0x644  ldarg.3
0x645  call     string Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull(object obj)
0x64a  stelem.ref
0x64b  dup
0x64c  ldc.i4.3
0x64d  ldarg.0
0x64e  box      [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0x653  stelem.ref
0x654  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x659  ldarg.0
0x65a  ret
```
