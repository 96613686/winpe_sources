# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::InitializeTrace

- ea: `0x11b0`
- end: `0x1289`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::InitializeTrace`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x430`
- `0x1340`

## callees

- `0x11b0`

## string_xrefs

- `0x11b5`: `Switch in config file`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldstr    aEventviewertra// "EventViewerTrace"
0x11b5  ldstr    aSwitchInConfig// "Switch in config file"
0x11ba  newobj   instance void [System]System.Diagnostics.BooleanSwitch::.ctor(string, string)
0x11bf  callvirt instance bool [System]System.Diagnostics.BooleanSwitch::get_Enabled()
0x11c4  brfalse  loc_1288
0x11c9  call     string [mscorlib]System.Environment::get_CommandLine()
0x11ce  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x11d3  ldstr    aDevenvExe// "devenv.exe"
0x11d8  callvirt instance bool [mscorlib]System.String::Contains(string)
0x11dd  brtrue   loc_1288
0x11e2  ldsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x11e7  brtrue   loc_127C
0x11ec  ldc.i4.5
0x11ed  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x11f2  stloc.0
0x11f3  ldloc.0
0x11f4  ldstr    aEventviewerLog// "eventviewer.log"
0x11f9  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x11fe  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Create(string)
0x1203  stloc.1
0x1204  leave.s  loc_125B
0x1206  pop
0x1207  ldstr    aEventviewer// "eventviewer"
0x120c  stloc.3
0x120d  ldloc.3
0x120e  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x1213  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1218  stloc.s  4
0x121a  ldloca.s 4
0x121c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1221  ldtoken  [mscorlib]System.Int32
0x1226  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122b  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x1230  castclass [mscorlib]System.IFormatProvider
0x1235  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x123a  call     string [mscorlib]System.String::Concat(string, string)
0x123f  stloc.3
0x1240  ldloc.3
0x1241  ldstr    aLog// "log"
0x1246  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x124b  stloc.3
0x124c  ldloc.0
0x124d  ldloc.3
0x124e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1253  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Create(string)
0x1258  stloc.1
0x1259  leave.s  loc_125B
0x125b  ldloc.1
0x125c  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.DateTimeTraceListener::.ctor(class [mscorlib]System.IO.Stream)
0x1261  stloc.2
0x1262  ldloc.2
0x1263  dup
0x1264  callvirt instance valuetype [System]System.Diagnostics.TraceOptions [System]System.Diagnostics.TraceListener::get_TraceOutputOptions()
0x1269  ldc.i4.2
0x126a  or
0x126b  callvirt instance void [System]System.Diagnostics.TraceListener::set_TraceOutputOptions(valuetype [System]System.Diagnostics.TraceOptions)
0x1270  call     class [System]System.Diagnostics.TraceListenerCollection [System]System.Diagnostics.Trace::get_Listeners()
0x1275  ldloc.2
0x1276  callvirt instance int32 [System]System.Diagnostics.TraceListenerCollection::Add(class [System]System.Diagnostics.TraceListener)
0x127b  pop
0x127c  ldsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x1281  ldc.i4.1
0x1282  add
0x1283  stsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x1288  ret
```
