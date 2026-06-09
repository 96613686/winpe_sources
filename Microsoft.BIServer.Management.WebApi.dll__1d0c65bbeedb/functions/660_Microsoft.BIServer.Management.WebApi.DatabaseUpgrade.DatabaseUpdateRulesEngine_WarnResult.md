# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::WarnResult

- ea: `0x660`
- end: `0x6bb`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::WarnResult`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4a0`

## callees

- `0x660`
- `0x6c0`

## pseudocode

```c

```

## disassembly

```asm
0x660  ldarg.0
0x661  ldsfld   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus> Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::LastLoggedStatus
0x666  stloc.0
0x667  ldloca.s 0
0x669  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::GetValueOrDefault()
0x66e  beq.s    loc_673
0x670  ldc.i4.1
0x671  br.s     loc_67D
0x673  ldloca.s 0
0x675  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::get_HasValue()
0x67a  ldc.i4.0
0x67b  ceq
0x67d  brfalse.s loc_6B9
0x67f  ldarg.0
0x680  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus>::.ctor(var<u1>)
0x685  stsfld   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus> Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::LastLoggedStatus
0x68a  ldstr    aDatabaseVersio// "Database Version Detection: {0}\n    Db"...
0x68f  ldc.i4.4
0x690  newarr   [mscorlib]System.Object
0x695  dup
0x696  ldc.i4.0
0x697  ldarg.1
0x698  stelem.ref
0x699  dup
0x69a  ldc.i4.1
0x69b  ldarg.2
0x69c  call     string Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull(object obj)
0x6a1  stelem.ref
0x6a2  dup
0x6a3  ldc.i4.2
0x6a4  ldarg.3
0x6a5  call     string Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull(object obj)
0x6aa  stelem.ref
0x6ab  dup
0x6ac  ldc.i4.3
0x6ad  ldarg.0
0x6ae  box      [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0x6b3  stelem.ref
0x6b4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x6b9  ldarg.0
0x6ba  ret
```
