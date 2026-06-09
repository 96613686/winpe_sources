# Microsoft.ReportingServices.Library.DBPoll::HandleException

- ea: `0xd20`
- end: `0xe10`
- name: `Microsoft.ReportingServices.Library.DBPoll::HandleException`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x8f10`

## callees

- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.2
0xd21  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::IsStoppingException(class [mscorlib]System.Exception)
0xd26  brfalse.s loc_DA3
0xd28  ldarg.2
0xd29  isinst   [mscorlib]System.Threading.ThreadAbortException
0xd2e  brfalse.s loc_D63
0xd30  ldarg.0
0xd31  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xd36  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xd3b  brfalse.s loc_DA1
0xd3d  ldarg.0
0xd3e  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xd43  ldc.i4.3
0xd44  ldstr    a0ExitingForThe// "{0}: Exiting for the following exceptio"...
0xd49  ldc.i4.2
0xd4a  newarr   [mscorlib]System.Object
0xd4f  dup
0xd50  ldc.i4.0
0xd51  ldarg.1
0xd52  stelem.ref
0xd53  dup
0xd54  ldc.i4.1
0xd55  ldarg.2
0xd56  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd5b  stelem.ref
0xd5c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xd61  br.s     loc_DA1
0xd63  ldarg.0
0xd64  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xd69  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xd6e  brfalse.s loc_DA1
0xd70  ldarg.0
0xd71  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xd76  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xd7b  brfalse.s loc_DA1
0xd7d  ldarg.0
0xd7e  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xd83  ldc.i4.1
0xd84  ldstr    a0ExitingForThe// "{0}: Exiting for the following exceptio"...
0xd89  ldc.i4.2
0xd8a  newarr   [mscorlib]System.Object
0xd8f  dup
0xd90  ldc.i4.0
0xd91  ldarg.1
0xd92  stelem.ref
0xd93  dup
0xd94  ldc.i4.1
0xd95  ldarg.2
0xd96  callvirt instance string [mscorlib]System.Object::ToString()
0xd9b  stelem.ref
0xd9c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xda1  ldc.i4.0
0xda2  ret
0xda3  ldarg.3
0xda4  brfalse.s loc_DB9
0xda6  ldarg.2
0xda7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xdac  ldarg.3
0xdad  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xdb2  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xdb7  brfalse.s loc_E03
0xdb9  ldarg.0
0xdba  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xdbf  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xdc4  brfalse.s loc_DEA
0xdc6  ldarg.0
0xdc7  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xdcc  ldc.i4.1
0xdcd  ldstr    a01// "{0}: {1}."
0xdd2  ldc.i4.2
0xdd3  newarr   [mscorlib]System.Object
0xdd8  dup
0xdd9  ldc.i4.0
0xdda  ldarg.1
0xddb  stelem.ref
0xddc  dup
0xddd  ldc.i4.1
0xdde  ldarg.2
0xddf  callvirt instance string [mscorlib]System.Object::ToString()
0xde4  stelem.ref
0xde5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xdea  ldarg.0
0xdeb  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xdf0  ldc.i4.1
0xdf1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::set_BufferOutput(bool)
0xdf6  ldarg.0
0xdf7  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xdfc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::WriteBuffer()
0xe01  br.s     loc_E0E
0xe03  ldarg.0
0xe04  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xe09  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::ClearBuffer()
0xe0e  ldc.i4.1
0xe0f  ret
```
