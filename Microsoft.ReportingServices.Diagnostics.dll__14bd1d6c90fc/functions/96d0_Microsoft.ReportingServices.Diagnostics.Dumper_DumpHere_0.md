# Microsoft.ReportingServices.Diagnostics.Dumper::DumpHere_0

- ea: `0x96d0`
- end: `0x9843`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::DumpHere_0`
- size: `371`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x9570`
- `0x96a0`
- `0xfe40`

## callees

- `0x33d0`
- `0x9580`
- `0x9600`
- `0x96d0`
- `0xa930`
- `0x103f0`
- `0x10410`

## pseudocode

```c

```

## disassembly

```asm
0x96d0  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x96d5  stloc.0
0x96d6  ldloc.0
0x96d7  ldarg.3
0x96d8  stfld    bool <>c__DisplayClass26_0::unhandledException
0x96dd  ldloc.0
0x96de  ldarg.1
0x96df  stfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x96e4  ldloc.0
0x96e5  ldarg.2
0x96e6  stfld    string <>c__DisplayClass26_0::assertionMessage
0x96eb  ldloc.0
0x96ec  ldarg.0
0x96ed  stfld    class Microsoft.ReportingServices.Diagnostics.Dumper <>c__DisplayClass26_0::<>4__this
0x96f2  ldarg.0
0x96f3  ldflda   int32 Microsoft.ReportingServices.Diagnostics.Dumper::m_recursionGuard
0x96f8  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x96fd  pop
0x96fe  ldloc.0
0x96ff  ldnull
0x9700  stfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x9705  newobj   instance void <>c__DisplayClass26_1::.ctor()
0x970a  stloc.1
0x970b  ldloc.1
0x970c  ldloc.0
0x970d  stfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x9712  ldloc.1
0x9713  call     class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumpClient::GetDumper()
0x9718  stfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x971d  ldarg.0
0x971e  ldfld    int32 Microsoft.ReportingServices.Diagnostics.Dumper::m_recursionGuard
0x9723  ldc.i4.1
0x9724  ble.s    loc_972B
0x9726  leave    loc_9842
0x972b  ldarg.0
0x972c  ldc.i4.0
0x972d  stfld    valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags Microsoft.ReportingServices.Diagnostics.Dumper::m_unsetSqlDumperFlags
0x9732  ldloc.1
0x9733  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x9738  ldarg.0
0x9739  ldfld    string Microsoft.ReportingServices.Diagnostics.Dumper::m_dumpLocation
0x973e  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetDirectory(string)
0x9743  ldloc.1
0x9744  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x9749  ldarg.0
0x974a  ldfld    valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.MiniDumpFlags Microsoft.ReportingServices.Diagnostics.Dumper::m_sqlMiniDumpFlags
0x974f  ldc.i4.0
0x9750  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetMiniDumpFlags(valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.MiniDumpFlags, valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.MiniDumpFlags)
0x9755  ldloc.1
0x9756  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x975b  call     valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags Microsoft.ReportingServices.Diagnostics.Dumper::get_SqlDumperFlagRetriver()
0x9760  ldarg.0
0x9761  ldfld    valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags Microsoft.ReportingServices.Diagnostics.Dumper::m_unsetSqlDumperFlags
0x9766  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetFlags(valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags, valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags)
0x976b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9770  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceFileName()
0x9775  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x977a  brtrue.s loc_9796
0x977c  ldloc.1
0x977d  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x9782  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9787  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceFileName()
0x978c  ldc.i4   0x80000
0x9791  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetLogFile(string, int32)
0x9796  ldloc.1
0x9797  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x979c  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x97a1  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceName()
0x97a6  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetInstanceName(string)
0x97ab  ldloc.1
0x97ac  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x97b1  call     string Microsoft.ReportingServices.Diagnostics.Dumper::get_ServiceName()
0x97b6  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetServiceName(string)
0x97bb  ldloc.1
0x97bc  ldftn    instance void <>c__DisplayClass26_1::<DumpHere>b__0()
0x97c2  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0x97c7  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::RunFromRestrictedCasContext(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0x97cc  leave.s  loc_9842
0x97ce  ldloc.1
0x97cf  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x97d4  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x97d9  brfalse.s loc_9821
0x97db  ldc.i4.0
0x97dc  stloc.2
0x97dd  br.s     loc_9811
0x97df  ldloc.1
0x97e0  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x97e5  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x97ea  ldloc.2
0x97eb  ldelema  [mscorlib]System.Runtime.InteropServices.GCHandle
0x97f0  call     instance bool [mscorlib]System.Runtime.InteropServices.GCHandle::get_IsAllocated()
0x97f5  brfalse.s loc_980D
0x97f7  ldloc.1
0x97f8  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x97fd  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x9802  ldloc.2
0x9803  ldelema  [mscorlib]System.Runtime.InteropServices.GCHandle
0x9808  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x980d  ldloc.2
0x980e  ldc.i4.1
0x980f  add
0x9810  stloc.2
0x9811  ldloc.2
0x9812  ldloc.1
0x9813  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x9818  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x981d  ldlen
0x981e  conv.i4
0x981f  blt.s    loc_97DF
0x9821  ldarg.0
0x9822  ldflda   int32 Microsoft.ReportingServices.Diagnostics.Dumper::m_recursionGuard
0x9827  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x982c  pop
0x982d  endfinally
0x982e  ldloc.1
0x982f  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x9834  brfalse.s loc_9841
0x9836  ldloc.1
0x9837  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x983c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9841  endfinally
0x9842  ret
```
