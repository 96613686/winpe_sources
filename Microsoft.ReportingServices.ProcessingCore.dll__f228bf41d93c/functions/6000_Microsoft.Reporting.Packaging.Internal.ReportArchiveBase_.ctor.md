# Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::.ctor

- ea: `0x6000`
- end: `0x6082`
- name: `Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::.ctor`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xbc380`

## string_xrefs

- `0x6007`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0x6017`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0x6027`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0x6037`: `http://schemas.microsoft.com/sqlserver/reporting/2013/01/reportdefinition`
- `0x6047`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportstate`
- `0x6057`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportstate`
- `0x6067`: `http://schemas.microsoft.com/sqlserver/reporting/2013/01/reportstate`

## pseudocode

```c

```

## disassembly

```asm
0x6000  ldarg.0
0x6001  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6006  dup
0x6007  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0x600c  ldstr    aRdl2010// "rdl2010"
0x6011  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6016  dup
0x6017  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0x601c  ldstr    aRdl2011// "rdl2011"
0x6021  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6026  dup
0x6027  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0x602c  ldstr    aRdl2012// "rdl2012"
0x6031  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6036  dup
0x6037  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x603c  ldstr    aRdl2013// "rdl2013"
0x6041  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6046  dup
0x6047  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/sqlserver/"...
0x604c  ldstr    aRdlrs2011// "rdlrs2011"
0x6051  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6056  dup
0x6057  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/sqlserver/"...
0x605c  ldstr    aRdlrs2012// "rdlrs2012"
0x6061  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6066  dup
0x6067  ldstr    aHttpSchemasMic_6// "http://schemas.microsoft.com/sqlserver/"...
0x606c  ldstr    aRdlrs2013// "rdlrs2013"
0x6071  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6076  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::m_mustUnderstandNamespaces
0x607b  ldarg.0
0x607c  call     instance void [mscorlib]System.Object::.ctor()
0x6081  ret
```
