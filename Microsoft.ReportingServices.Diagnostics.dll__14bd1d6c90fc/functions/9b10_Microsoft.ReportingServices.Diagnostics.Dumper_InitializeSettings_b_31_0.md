# Microsoft.ReportingServices.Diagnostics.Dumper::<InitializeSettings>b__31_0

- ea: `0x9b10`
- end: `0x9bd6`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::<InitializeSettings>b__31_0`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x95e0`
- `0x95f0`
- `0x99e0`
- `0x9a60`
- `0x9b10`
- `0xab80`

## pseudocode

```c

```

## disassembly

```asm
0x9b10  ldarg.0
0x9b11  call     string Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentProcessId()
0x9b16  stfld    string Microsoft.ReportingServices.Diagnostics.Dumper::m_pid
0x9b1b  ldarg.0
0x9b1c  call     instance void Microsoft.ReportingServices.Diagnostics.Dumper::InitializeDumperFlags()
0x9b21  ldnull
0x9b22  stloc.0
0x9b23  call     class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToDump()
0x9b28  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x9b2d  stloc.2
0x9b2e  br.s     loc_9B3F
0x9b30  ldloc.2
0x9b31  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x9b36  stloc.3
0x9b37  ldloc.0
0x9b38  ldloc.3
0x9b39  call     string [mscorlib]System.String::Concat(string, string)
0x9b3e  stloc.0
0x9b3f  ldloc.2
0x9b40  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x9b45  brtrue.s loc_9B30
0x9b47  leave.s  loc_9B5D
0x9b49  ldloc.2
0x9b4a  isinst   [mscorlib]System.IDisposable
0x9b4f  stloc.s  4
0x9b51  ldloc.s  4
0x9b53  brfalse.s loc_9B5C
0x9b55  ldloc.s  4
0x9b57  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9b5c  endfinally
0x9b5d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9b62  ldc.i4.3
0x9b63  ldstr    aDumpOn0// "Dump on: {0}"
0x9b68  ldc.i4.1
0x9b69  newarr   [mscorlib]System.Object
0x9b6e  dup
0x9b6f  ldc.i4.0
0x9b70  ldloc.0
0x9b71  stelem.ref
0x9b72  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x9b77  ldnull
0x9b78  stloc.1
0x9b79  call     class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToNotDump()
0x9b7e  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x9b83  stloc.2
0x9b84  br.s     loc_9B97
0x9b86  ldloc.2
0x9b87  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x9b8c  stloc.s  5
0x9b8e  ldloc.1
0x9b8f  ldloc.s  5
0x9b91  call     string [mscorlib]System.String::Concat(string, string)
0x9b96  stloc.1
0x9b97  ldloc.2
0x9b98  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x9b9d  brtrue.s loc_9B86
0x9b9f  leave.s  loc_9BB5
0x9ba1  ldloc.2
0x9ba2  isinst   [mscorlib]System.IDisposable
0x9ba7  stloc.s  4
0x9ba9  ldloc.s  4
0x9bab  brfalse.s loc_9BB4
0x9bad  ldloc.s  4
0x9baf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9bb4  endfinally
0x9bb5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9bba  ldc.i4.3
0x9bbb  ldstr    aDoNotDumpOn0// "Do not dump on: {0}"
0x9bc0  ldc.i4.1
0x9bc1  newarr   [mscorlib]System.Object
0x9bc6  dup
0x9bc7  ldc.i4.0
0x9bc8  ldloc.1
0x9bc9  stelem.ref
0x9bca  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x9bcf  ldarg.0
0x9bd0  call     instance void Microsoft.ReportingServices.Diagnostics.Dumper::InitializeDumpLocation()
0x9bd5  ret
```
