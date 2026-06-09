# Microsoft.ReportingServices.Diagnostics.Dumper::Init

- ea: `0x94b0`
- end: `0x956b`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::Init`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xa820`

## callees

- `0x94b0`
- `0x99c0`
- `0xa960`

## pseudocode

```c

```

## disassembly

```asm
0x94b0  ldarg.0
0x94b1  ldfld    bool Microsoft.ReportingServices.Diagnostics.Dumper::m_isInitialized
0x94b6  brfalse.s loc_94B9
0x94b8  ret
0x94b9  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94be  ldc.i4.s 0xB
0x94c0  bne.un.s loc_94CD
0x94c2  ldstr    aRsDumperClassB// "RS dumper class being used without bein"...
0x94c7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x94cc  throw
0x94cd  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94d2  ldc.i4.1
0x94d3  beq.s    loc_94FE
0x94d5  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94da  brfalse.s loc_94FE
0x94dc  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94e1  ldc.i4.s 0xA
0x94e3  beq.s    loc_94FE
0x94e5  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94ea  ldc.i4.3
0x94eb  beq.s    loc_94FE
0x94ed  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94f2  ldc.i4.4
0x94f3  beq.s    loc_94FE
0x94f5  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x94fa  ldc.i4.5
0x94fb  beq.s    loc_94FE
0x94fd  ret
0x94fe  call     bool [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumpClient::IsInitialized()
0x9503  brtrue.s loc_950A
0x9505  call     void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumpClient::Initialize()
0x950a  ldsfld   object Microsoft.ReportingServices.Diagnostics.Dumper::m_lockObj
0x950f  stloc.0
0x9510  ldc.i4.0
0x9511  stloc.1
0x9512  ldloc.0
0x9513  ldloca.s 1
0x9515  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x951a  ldarg.0
0x951b  call     instance void Microsoft.ReportingServices.Diagnostics.Dumper::InitializeSettings()
0x9520  leave.s  loc_952C
0x9522  ldloc.1
0x9523  brfalse.s loc_952B
0x9525  ldloc.0
0x9526  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x952b  endfinally
0x952c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9531  ldc.i4.4
0x9532  ldstr    aSettingUnhandl// "Setting unhandled exception handler"
0x9537  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x953c  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x9541  ldarg.0
0x9542  ldftn    instance void Microsoft.ReportingServices.Diagnostics.Dumper::DefaultExceptionHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs args)
0x9548  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x954d  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x9552  ldarg.0
0x9553  ldftn    instance void Microsoft.ReportingServices.Diagnostics.Dumper::RSExceptionHandler(object sender, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs e)
0x9559  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs>::.ctor(object, native int)
0x955e  call     void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::add_ExceptionCreated(class [mscorlib]System.EventHandler`1<class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs>)
0x9563  ldarg.0
0x9564  ldc.i4.1
0x9565  stfld    bool Microsoft.ReportingServices.Diagnostics.Dumper::m_isInitialized
0x956a  ret
```
