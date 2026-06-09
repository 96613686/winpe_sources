# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Cancel

- ea: `0xe1c0`
- end: `0xe413`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Cancel`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xd510`

## callees

- `0x7950`
- `0xaff0`
- `0xd420`
- `0xe1c0`
- `0x10310`

## string_xrefs

- `0xe1da`: `ThreadJobContext.Cancel operation ignored because job was disposed`
- `0xe1f9`: `ThreadJobContext.Cancel acquiring lock on command list`
- `0xe21f`: `ThreadJobContext.Cancel lock acquired on command list`
- `0xe25f`: `ThreadJobContext.Cancel Sql: System.Data.IDBCommand was cancelled`
- `0xe287`: `ThreadJobContext.Cancel Sql: Microsoft.ReportingServices.DataProcessing.IDbCommand was cancelled`
- `0xe2f4`: `ThreadJobContext.Cancel: Cancelling via abort helper`
- `0xe324`: `ThreadJobContext.Cancel waiting`
- `0xe344`: `ThreadJobContext.Cancel: Calling Abort() on thread`
- `0xe368`: `ThreadJobContext.Cancel failed - resetting state`
- `0xe3ac`: `ThreadJobContext.Cancel succeeded - abort raised`
- `0xe3be`: `ThreadJobContext.Cancel: Thread is no longer is cancelable state, Thread state = {0}`
- `0xe3e2`: `ThreadJobContext.Cancel lock released on command list`
- `0xe3f6`: `ThreadJobContext.Cancel thread was not in cancelable period`

## pseudocode

```c

```

## disassembly

```asm
0xe1c0  ldarg.0
0xe1c1  ldfld    bool Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_disposed
0xe1c6  brfalse.s loc_E1E6
0xe1c8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe1cd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0xe1d2  brfalse.s loc_E1E4
0xe1d4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe1d9  ldc.i4.4
0xe1da  ldstr    aThreadjobconte_5// "ThreadJobContext.Cancel operation ignor"...
0xe1df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe1e4  ldc.i4.1
0xe1e5  ret
0xe1e6  nop
0xe1e7  ldarg.0
0xe1e8  ldfld    int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe1ed  ldc.i4.1
0xe1ee  bne.un   loc_E3F0
0xe1f3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe1f8  ldc.i4.4
0xe1f9  ldstr    aThreadjobconte_6// "ThreadJobContext.Cancel acquiring lock "...
0xe1fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe203  ldarg.0
0xe204  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_commands
0xe209  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0xe20e  stloc.1
0xe20f  ldc.i4.0
0xe210  stloc.2
0xe211  ldloc.1
0xe212  ldloca.s 2
0xe214  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe219  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe21e  ldc.i4.4
0xe21f  ldstr    aThreadjobconte_7// "ThreadJobContext.Cancel lock acquired o"...
0xe224  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe229  ldarg.0
0xe22a  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_commands
0xe22f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xe234  ldc.i4.0
0xe235  ble.s    loc_E2A3
0xe237  ldc.i4.0
0xe238  stloc.3
0xe239  br.s     loc_E295
0xe23b  ldarg.0
0xe23c  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_commands
0xe241  ldloc.3
0xe242  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xe247  isinst   [System.Data]System.Data.IDbCommand
0xe24c  stloc.s  4
0xe24e  ldloc.s  4
0xe250  brfalse.s loc_E26B
0xe252  ldloc.s  4
0xe254  callvirt instance void [System.Data]System.Data.IDbCommand::Cancel()
0xe259  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe25e  ldc.i4.4
0xe25f  ldstr    aThreadjobconte_8// "ThreadJobContext.Cancel Sql: System.Dat"...
0xe264  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe269  br.s     loc_E291
0xe26b  ldarg.0
0xe26c  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_commands
0xe271  ldloc.3
0xe272  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xe277  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand
0xe27c  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::Cancel()
0xe281  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe286  ldc.i4.4
0xe287  ldstr    aThreadjobconte_9// "ThreadJobContext.Cancel Sql: Microsoft."...
0xe28c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe291  ldloc.3
0xe292  ldc.i4.1
0xe293  add
0xe294  stloc.3
0xe295  ldloc.3
0xe296  ldarg.0
0xe297  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_commands
0xe29c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xe2a1  blt.s    loc_E23B
0xe2a3  leave.s  loc_E2AF
0xe2a5  ldloc.2
0xe2a6  brfalse.s loc_E2AE
0xe2a8  ldloc.1
0xe2a9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xe2ae  endfinally
0xe2af  ldc.i4.0
0xe2b0  stloc.0
0xe2b1  ldarg.0
0xe2b2  ldfld    object Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelperSync
0xe2b7  stloc.1
0xe2b8  ldc.i4.0
0xe2b9  stloc.2
0xe2ba  ldloc.1
0xe2bb  ldloca.s 2
0xe2bd  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe2c2  ldarg.0
0xe2c3  ldfld    class Microsoft.ReportingServices.Diagnostics.IAbortHelper Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelper
0xe2c8  brfalse.s loc_E30C
0xe2ca  ldc.i4.2
0xe2cb  stloc.s  5
0xe2cd  ldarg.1
0xe2ce  switch   loc_E2E1, loc_E2E6, loc_E2EB
0xe2df  br.s     loc_E2EE
0xe2e1  ldc.i4.3
0xe2e2  stloc.s  5
0xe2e4  br.s     loc_E2EE
0xe2e6  ldc.i4.1
0xe2e7  stloc.s  5
0xe2e9  br.s     loc_E2EE
0xe2eb  ldc.i4.1
0xe2ec  stloc.s  5
0xe2ee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe2f3  ldc.i4.4
0xe2f4  ldstr    aThreadjobconte_10// "ThreadJobContext.Cancel: Cancelling via"...
0xe2f9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe2fe  ldarg.0
0xe2ff  ldfld    class Microsoft.ReportingServices.Diagnostics.IAbortHelper Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_abortHelper
0xe304  ldloc.s  5
0xe306  callvirt instance bool Microsoft.ReportingServices.Diagnostics.IAbortHelper::Abort(valuetype Microsoft.ReportingServices.Diagnostics.ProcessingStatus status)
0xe30b  stloc.0
0xe30c  leave.s  loc_E318
0xe30e  ldloc.2
0xe30f  brfalse.s loc_E317
0xe311  ldloc.1
0xe312  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xe317  endfinally
0xe318  ldloc.0
0xe319  brtrue   loc_E3DC
0xe31e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe323  ldc.i4.4
0xe324  ldstr    aThreadjobconte_11// "ThreadJobContext.Cancel waiting"
0xe329  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe32e  ldarg.0
0xe32f  ldflda   int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe334  ldc.i4.2
0xe335  ldc.i4.1
0xe336  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xe33b  ldc.i4.1
0xe33c  bne.un.s loc_E3B8
0xe33e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe343  ldc.i4.4
0xe344  ldstr    aThreadjobconte_12// "ThreadJobContext.Cancel: Calling Abort("...
0xe349  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe34e  ldarg.0
0xe34f  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_thread
0xe354  ldarg.1
0xe355  newobj   instance void Microsoft.ReportingServices.Diagnostics.ReportServerAbortInfo::.ctor(valuetype AbortReason reason)
0xe35a  callvirt instance void [mscorlib]System.Threading.Thread::Abort(object)
0xe35f  leave.s  loc_E3A6
0xe361  pop
0xe362  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe367  ldc.i4.1
0xe368  ldstr    aThreadjobconte_13// "ThreadJobContext.Cancel failed - resett"...
0xe36d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe372  ldarg.0
0xe373  ldflda   int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe378  ldc.i4.1
0xe379  ldc.i4.2
0xe37a  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xe37f  ldc.i4.2
0xe380  beq.s    loc_E3A2
0xe382  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe387  ldstr    aUnexpectedCanc// "Unexpected cancel state: {0} - expected"...
0xe38c  ldarg.0
0xe38d  ldfld    int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe392  box      [mscorlib]System.Int32
0xe397  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xe39c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xe3a1  throw
0xe3a2  ldc.i4.0
0xe3a3  stloc.2
0xe3a4  leave.s  loc_E411
0xe3a6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe3ab  ldc.i4.4
0xe3ac  ldstr    aThreadjobconte_14// "ThreadJobContext.Cancel succeeded - abo"...
0xe3b1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe3b6  br.s     loc_E3DC
0xe3b8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe3bd  ldc.i4.3
0xe3be  ldstr    aThreadjobconte_15// "ThreadJobContext.Cancel: Thread is no l"...
0xe3c3  ldc.i4.1
0xe3c4  newarr   [mscorlib]System.Object
0xe3c9  dup
0xe3ca  ldc.i4.0
0xe3cb  ldarg.0
0xe3cc  ldfld    int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe3d1  box      [mscorlib]System.Int32
0xe3d6  stelem.ref
0xe3d7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xe3dc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe3e1  ldc.i4.4
0xe3e2  ldstr    aThreadjobconte_16// "ThreadJobContext.Cancel lock released o"...
0xe3e7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe3ec  ldc.i4.1
0xe3ed  stloc.2
0xe3ee  leave.s  loc_E411
0xe3f0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe3f5  ldc.i4.4
0xe3f6  ldstr    aThreadjobconte_17// "ThreadJobContext.Cancel thread was not "...
0xe3fb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe400  ldc.i4.0
0xe401  stloc.2
0xe402  leave.s  loc_E411
0xe404  ldarg.0
0xe405  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_parentJobCtx
0xe40a  ldarg.0
0xe40b  callvirt instance void Microsoft.ReportingServices.Diagnostics.RunningJobContext::RemoveWorkThread(class Microsoft.ReportingServices.Diagnostics.ThreadJobContext threadCtx)
0xe410  endfinally
0xe411  ldloc.2
0xe412  ret
```
