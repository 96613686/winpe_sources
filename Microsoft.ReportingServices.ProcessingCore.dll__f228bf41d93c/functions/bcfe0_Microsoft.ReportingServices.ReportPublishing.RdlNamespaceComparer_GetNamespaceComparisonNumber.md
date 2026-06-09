# Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::GetNamespaceComparisonNumber

- ea: `0xbcfe0`
- end: `0xbd047`
- name: `Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::GetNamespaceComparisonNumber`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd050`

## callees

- `0xbcfe0`

## string_xrefs

- `0xbcfe1`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0xbcff0`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0xbcfff`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbd00e`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xbcfe0  ldarg.0
0xbcfe1  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0xbcfe6  call     bool [mscorlib]System.String::Equals(string, string)
0xbcfeb  brfalse.s loc_BCFEF
0xbcfed  ldc.i4.0
0xbcfee  ret
0xbcfef  ldarg.0
0xbcff0  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0xbcff5  call     bool [mscorlib]System.String::Equals(string, string)
0xbcffa  brfalse.s loc_BCFFE
0xbcffc  ldc.i4.1
0xbcffd  ret
0xbcffe  ldarg.0
0xbcfff  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbd004  call     bool [mscorlib]System.String::Equals(string, string)
0xbd009  brfalse.s loc_BD00D
0xbd00b  ldc.i4.2
0xbd00c  ret
0xbd00d  ldarg.0
0xbd00e  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbd013  call     bool [mscorlib]System.String::Equals(string, string)
0xbd018  brfalse.s loc_BD01C
0xbd01a  ldc.i4.3
0xbd01b  ret
0xbd01c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xbd021  ldc.i4.0
0xbd022  ldstr    aInvalidRdlName// "Invalid RDL namespace: {0}"
0xbd027  ldc.i4.1
0xbd028  newarr   [mscorlib]System.Object
0xbd02d  dup
0xbd02e  ldc.i4.0
0xbd02f  ldarg.0
0xbd030  stelem.ref
0xbd031  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0xbd036  ldstr    aInvalidRdlName_0// "Invalid RDL namespace: "
0xbd03b  ldarg.0
0xbd03c  call     string [mscorlib]System.String::Concat(string, string)
0xbd041  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xbd046  throw
```
