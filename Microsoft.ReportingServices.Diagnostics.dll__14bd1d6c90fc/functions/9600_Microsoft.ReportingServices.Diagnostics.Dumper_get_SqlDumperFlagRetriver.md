# Microsoft.ReportingServices.Diagnostics.Dumper::get_SqlDumperFlagRetriver

- ea: `0x9600`
- end: `0x9694`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::get_SqlDumperFlagRetriver`
- size: `148`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9590`
- `0x96d0`
- `0x98d0`
- `0x9a60`

## callees

- `0x3420`
- `0x9600`
- `0xa930`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldc.i4.0
0x9601  stloc.0
0x9602  ldtoken  [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags
0x9607  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x960c  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x9611  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_WatsonFlags()
0x9616  stloc.1
0x9617  ldloca.s 1
0x9619  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x961e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9623  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x9628  unbox.any [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags
0x962d  stloc.0
0x962e  leave.s  loc_9692
0x9630  pop
0x9631  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9636  ldc.i4.1
0x9637  ldstr    aInvalidValueFo// "Invalid value for sqldumper flags: "
0x963c  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x9641  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_WatsonFlags()
0x9646  stloc.1
0x9647  ldloca.s 1
0x9649  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x964e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9653  call     string [mscorlib]System.String::Concat(string, string)
0x9658  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x965d  leave.s  loc_9692
0x965f  pop
0x9660  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9665  ldc.i4.1
0x9666  ldstr    aOverflowParsin// "Overflow parsing {0} to DumperFlags"
0x966b  ldc.i4.1
0x966c  newarr   [mscorlib]System.Object
0x9671  dup
0x9672  ldc.i4.0
0x9673  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x9678  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_WatsonFlags()
0x967d  stloc.1
0x967e  ldloca.s 1
0x9680  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9685  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x968a  stelem.ref
0x968b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x9690  leave.s  loc_9692
0x9692  ldloc.0
0x9693  ret
```
