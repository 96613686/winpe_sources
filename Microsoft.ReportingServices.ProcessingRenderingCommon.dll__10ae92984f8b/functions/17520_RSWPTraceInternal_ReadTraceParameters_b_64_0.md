# RSWPTraceInternal::<ReadTraceParameters>b__64_0

- ea: `0x17520`
- end: `0x17623`
- name: `RSWPTraceInternal::<ReadTraceParameters>b__64_0`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x117c0`
- `0x17520`

## string_xrefs

- `0x17526`: `Setting trace directory {0}`
- `0x17552`: `Creating trace directory {0}`
- `0x175c1`: `Cannot write to log directory at {0}`

## pseudocode

```c

```

## disassembly

```asm
0x17520  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x17525  ldc.i4.4
0x17526  ldstr    aSettingTraceDi// "Setting trace directory {0}"
0x1752b  ldc.i4.1
0x1752c  newarr   [mscorlib]System.Object
0x17531  dup
0x17532  ldc.i4.0
0x17533  ldarg.0
0x17534  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x17539  stelem.ref
0x1753a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1753f  ldarg.0
0x17540  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x17545  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1754a  brtrue.s loc_17579
0x1754c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x17551  ldc.i4.3
0x17552  ldstr    aCreatingTraceD// "Creating trace directory {0}"
0x17557  ldc.i4.1
0x17558  newarr   [mscorlib]System.Object
0x1755d  dup
0x1755e  ldc.i4.0
0x1755f  ldarg.0
0x17560  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x17565  stelem.ref
0x17566  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1756b  ldarg.0
0x1756c  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x17571  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x17576  pop
0x17577  br.s     loc_175B8
0x17579  ldarg.0
0x1757a  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x1757f  ldstr    aFlag// "\\_flag_"
0x17584  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x17589  stloc.1
0x1758a  ldloca.s 1
0x1758c  constrained. [mscorlib]System.Guid
0x17592  callvirt instance string [mscorlib]System.Object::ToString()
0x17597  call     string [mscorlib]System.String::Concat(string, string, string)
0x1759c  stloc.0
0x1759d  ldloc.0
0x1759e  ldc.i4.1
0x1759f  ldc.i4.2
0x175a0  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x175a5  stloc.2
0x175a6  leave.s  loc_175B2
0x175a8  ldloc.2
0x175a9  brfalse.s loc_175B1
0x175ab  ldloc.2
0x175ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x175b1  endfinally
0x175b2  ldloc.0
0x175b3  call     void [mscorlib]System.IO.File::Delete(string)
0x175b8  leave.s  loc_17622
0x175ba  pop
0x175bb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x175c0  ldc.i4.1
0x175c1  ldstr    aCannotWriteToL// "Cannot write to log directory at {0}"
0x175c6  ldc.i4.1
0x175c7  newarr   [mscorlib]System.Object
0x175cc  dup
0x175cd  ldc.i4.0
0x175ce  ldarg.0
0x175cf  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x175d4  stelem.ref
0x175d5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x175da  ldarg.0
0x175db  ldstr    aTemp// "TEMP"
0x175e0  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x175e5  stfld    string RSWPTraceInternal::m_traceDirectory
0x175ea  ldarg.0
0x175eb  ldarg.0
0x175ec  ldfld    string RSWPTraceInternal::m_traceDirectory
0x175f1  ldstr    aLogfiles// "LogFiles"
0x175f6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x175fb  stfld    string RSWPTraceInternal::m_traceDirectory
0x17600  ldarg.0
0x17601  ldfld    string RSWPTraceInternal::m_traceDirectory
0x17606  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1760b  brtrue.s loc_17619
0x1760d  ldarg.0
0x1760e  ldfld    string RSWPTraceInternal::m_traceDirectory
0x17613  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x17618  pop
0x17619  ldarg.0
0x1761a  ldc.i4.1
0x1761b  stfld    bool RSWPTraceInternal::m_traceFileInNewLocation
0x17620  leave.s  loc_17622
0x17622  ret
```
