# Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::IsInternal

- ea: `0xb350`
- end: `0xb38e`
- name: `Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::IsInternal`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb350`
- `0xb3f0`

## string_xrefs

- `0xb35f`: `.microsoft.com`

## pseudocode

```c

```

## disassembly

```asm
0xb350  ldarg.0
0xb351  call     instance string Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::GetUnsafeHostName()
0xb356  stloc.0
0xb357  ldc.i4.2
0xb358  newarr   [mscorlib]System.String
0xb35d  dup
0xb35e  ldc.i4.0
0xb35f  ldstr    aMicrosoftCom// ".microsoft.com"
0xb364  stelem.ref
0xb365  dup
0xb366  ldc.i4.1
0xb367  ldstr    aSysSqlsvrLocal// ".sys-sqlsvr.local"
0xb36c  stelem.ref
0xb36d  stloc.1
0xb36e  ldc.i4.0
0xb36f  stloc.2
0xb370  br.s     loc_B386
0xb372  ldloc.1
0xb373  ldloc.2
0xb374  ldelem.ref
0xb375  stloc.3
0xb376  ldloc.0
0xb377  ldloc.3
0xb378  ldc.i4.5
0xb379  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb37e  brfalse.s loc_B382
0xb380  ldc.i4.1
0xb381  ret
0xb382  ldloc.2
0xb383  ldc.i4.1
0xb384  add
0xb385  stloc.2
0xb386  ldloc.2
0xb387  ldloc.1
0xb388  ldlen
0xb389  conv.i4
0xb38a  blt.s    loc_B372
0xb38c  ldc.i4.0
0xb38d  ret
```
