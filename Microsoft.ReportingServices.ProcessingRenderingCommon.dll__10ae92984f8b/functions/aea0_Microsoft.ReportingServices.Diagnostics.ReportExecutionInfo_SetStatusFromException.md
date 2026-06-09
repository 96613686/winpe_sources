# Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::SetStatusFromException

- ea: `0xaea0`
- end: `0xaf5f`
- name: `Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::SetStatusFromException`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b60`

## callees

- `0xaea0`
- `0xb000`
- `0x10310`

## string_xrefs

- `0xaef5`: `CancelableJobExecution.Execute caught our thread abort exception`
- `0xaf37`: `CancelableJobExecution.Execute caught some other thread abort exception`

## pseudocode

```c

```

## disassembly

```asm
0xaea0  ldarg.1
0xaea1  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0xaea6  stloc.0
0xaea7  ldloc.0
0xaea8  brfalse.s loc_AEBD
0xaeaa  ldarg.0
0xaeab  ldloc.0
0xaeac  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0xaeb1  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_status
0xaeb6  ldloc.0
0xaeb7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::.ctor(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException)
0xaebc  ret
0xaebd  ldarg.1
0xaebe  isinst   [mscorlib]System.Threading.ThreadAbortException
0xaec3  brfalse  loc_AF4B
0xaec8  ldarg.1
0xaec9  isinst   [mscorlib]System.Threading.ThreadAbortException
0xaece  stloc.1
0xaecf  ldloc.1
0xaed0  callvirt instance object [mscorlib]System.Threading.ThreadAbortException::get_ExceptionState()
0xaed5  brfalse.s loc_AF31
0xaed7  ldloc.1
0xaed8  callvirt instance object [mscorlib]System.Threading.ThreadAbortException::get_ExceptionState()
0xaedd  isinst   Microsoft.ReportingServices.Diagnostics.ReportServerAbortInfo
0xaee2  brfalse.s loc_AF31
0xaee4  ldloc.1
0xaee5  callvirt instance object [mscorlib]System.Threading.ThreadAbortException::get_ExceptionState()
0xaeea  isinst   Microsoft.ReportingServices.Diagnostics.ReportServerAbortInfo
0xaeef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xaef4  ldc.i4.3
0xaef5  ldstr    aCancelablejobe// "CancelableJobExecution.Execute caught o"...
0xaefa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xaeff  call     void [mscorlib]System.Threading.Thread::ResetAbort()
0xaf04  callvirt instance valuetype AbortReason Microsoft.ReportingServices.Diagnostics.ReportServerAbortInfo::get_Reason()
0xaf09  stloc.2
0xaf0a  ldloc.2
0xaf0b  brfalse.s loc_AF22
0xaf0d  ldloc.2
0xaf0e  ldc.i4.1
0xaf0f  sub
0xaf10  ldc.i4.1
0xaf11  bgt.un.s loc_AF41
0xaf13  ldarg.0
0xaf14  ldc.i4.s 0x73
0xaf16  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_status
0xaf1b  ldarg.1
0xaf1c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.JobCanceledException::.ctor(class [mscorlib]System.Exception)
0xaf21  ret
0xaf22  ldarg.0
0xaf23  ldc.i4.s 0x72
0xaf25  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_status
0xaf2a  ldarg.1
0xaf2b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportTimeoutExpiredException::.ctor(class [mscorlib]System.Exception)
0xaf30  ret
0xaf31  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xaf36  ldc.i4.3
0xaf37  ldstr    aCancelablejobe_0// "CancelableJobExecution.Execute caught s"...
0xaf3c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xaf41  ldarg.0
0xaf42  ldc.i4.s 0x6D
0xaf44  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_status
0xaf49  ldnull
0xaf4a  ret
0xaf4b  ldarg.0
0xaf4c  ldc.i4.s 0x6D
0xaf4e  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_status
0xaf53  ldarg.1
0xaf54  ldstr    aInternalError// "Internal error"
0xaf59  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0xaf5e  ret
```
