# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ProcessExtensionLoadException

- ea: `0x6dd0`
- end: `0x6e93`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ProcessExtensionLoadException`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6960`
- `0x6ab0`
- `0x7530`

## callees

- `0x4fa0`
- `0x6dd0`
- `0x123b0`
- `0x12470`
- `0x12480`

## string_xrefs

- `0x6e44`: `Skipped instantiating {0} report server extension. Extension was not enabled.`
- `0x6e70`: `Exception caught instantiating {0} report server extension: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x6dd0  ldarg.3
0x6dd1  brtrue.s loc_6DF3
0x6dd3  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x6dd8  ldc.i4   0x89
0x6ddd  ldc.i4.1
0x6dde  newarr   [mscorlib]System.Object
0x6de3  dup
0x6de4  ldc.i4.0
0x6de5  ldarg.2
0x6de6  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6deb  stelem.ref
0x6dec  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype Microsoft.ReportingServices.Diagnostics.Event id, object[] args)
0x6df1  br.s     loc_6E1B
0x6df3  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x6df8  ldc.i4.s 0x6C
0x6dfa  ldc.i4.2
0x6dfb  newarr   [mscorlib]System.Object
0x6e00  dup
0x6e01  ldc.i4.0
0x6e02  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x6e07  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_SourceName()
0x6e0c  stelem.ref
0x6e0d  dup
0x6e0e  ldc.i4.1
0x6e0f  ldarg.2
0x6e10  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6e15  stelem.ref
0x6e16  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype Microsoft.ReportingServices.Diagnostics.Event id, object[] args)
0x6e1b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6e20  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6e25  brfalse.s loc_6E5E
0x6e27  ldarg.1
0x6e28  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x6e2d  ldtoken  [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.NotEnabledException
0x6e32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e37  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x6e3c  brfalse.s loc_6E5E
0x6e3e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6e43  ldc.i4.4
0x6e44  ldstr    aSkippedInstant// "Skipped instantiating {0} report server"...
0x6e49  ldc.i4.1
0x6e4a  newarr   [mscorlib]System.Object
0x6e4f  dup
0x6e50  ldc.i4.0
0x6e51  ldarg.2
0x6e52  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6e57  stelem.ref
0x6e58  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6e5d  ret
0x6e5e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6e63  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x6e68  brfalse.s loc_6E92
0x6e6a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6e6f  ldc.i4.1
0x6e70  ldstr    aExceptionCaugh// "Exception caught instantiating {0} repo"...
0x6e75  ldc.i4.2
0x6e76  newarr   [mscorlib]System.Object
0x6e7b  dup
0x6e7c  ldc.i4.0
0x6e7d  ldarg.2
0x6e7e  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6e83  stelem.ref
0x6e84  dup
0x6e85  ldc.i4.1
0x6e86  ldarg.1
0x6e87  callvirt instance string [mscorlib]System.Object::ToString()
0x6e8c  stelem.ref
0x6e8d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6e92  ret
```
