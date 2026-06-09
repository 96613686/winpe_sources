# System.Windows.Threading.DispatcherTimer::set_Interval

- ea: `0x3e1b0`
- end: `0x3e2a9`
- name: `System.Windows.Threading.DispatcherTimer::set_Interval`
- size: `249`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf530`
- `0xf630`
- `0x38ed0`

## callees

- `0xed20`
- `0x2c100`
- `0x3ca70`
- `0x3e1b0`

## string_xrefs

- `0x3e244`: `**** WPF has detected evidence that this app (or a component ****\n**** it uses) has changed the floating point control word.   ****\n**** This is not supported in a .NET app.  Please ask the    ****\n**** app (or component) author to fix it.                    ****\n`

## pseudocode

```c

```

## disassembly

```asm
0x3e1b0  ldc.i4.0
0x3e1b1  stloc.0
0x3e1b2  ldarga.s 1
0x3e1b4  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3e1b9  ldc.r8   0.0
0x3e1c2  bge.un.s loc_3E1D9
0x3e1c4  ldstr    aValue// "value"
0x3e1c9  ldstr    aTimespanperiod// "TimeSpanPeriodOutOfRange_TooSmall"
0x3e1ce  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x3e1d3  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x3e1d8  throw
0x3e1d9  ldarga.s 1
0x3e1db  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3e1e0  ldc.r8   2.147483647e9
0x3e1e9  ble.un.s loc_3E254
0x3e1eb  ldarga.s 1
0x3e1ed  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x3e1f2  stloc.1
0x3e1f3  ldloc.1
0x3e1f4  ldc.i8   0x1387FFFFD8F0
0x3e1fd  ble.s    loc_3E214
0x3e1ff  ldstr    aValue// "value"
0x3e204  ldstr    aTimespanperiod_0// "TimeSpanPeriodOutOfRange_TooLarge"
0x3e209  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x3e20e  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x3e213  throw
0x3e214  ldloc.1
0x3e215  ldc.i4.1
0x3e216  conv.i8
0x3e217  sub
0x3e218  dup
0x3e219  stloc.1
0x3e21a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromTicks(int64)
0x3e21f  starg.s  1
0x3e221  ldarga.s 1
0x3e223  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3e228  ldc.r8   2.147483647e9
0x3e231  bgt.s    loc_3E214
0x3e233  call     bool MS.Internal.AvTrace::IsDebuggerAttached()
0x3e238  brfalse.s loc_3E254
0x3e23a  ldsfld   bool System.Windows.Threading.DispatcherTimer::HasNotifiedFPCW
0x3e23f  brtrue.s loc_3E254
0x3e241  ldc.i4.s 0x28
0x3e243  ldnull
0x3e244  ldstr    aWpfHasDetected// "**** WPF has detected evidence that thi"...
0x3e249  call     void [mscorlib]System.Diagnostics.Debugger::Log(int32, string, string)
0x3e24e  ldc.i4.1
0x3e24f  stsfld   bool System.Windows.Threading.DispatcherTimer::HasNotifiedFPCW
0x3e254  ldarg.0
0x3e255  ldfld    object System.Windows.Threading.DispatcherTimer::_instanceLock
0x3e25a  stloc.2
0x3e25b  ldc.i4.0
0x3e25c  stloc.3
0x3e25d  ldloc.2
0x3e25e  ldloca.s 3
0x3e260  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x3e265  ldarg.0
0x3e266  ldarg.1
0x3e267  stfld    valuetype [mscorlib]System.TimeSpan System.Windows.Threading.DispatcherTimer::_interval
0x3e26c  ldarg.0
0x3e26d  ldfld    bool System.Windows.Threading.DispatcherTimer::_isEnabled
0x3e272  brfalse.s loc_3E28E
0x3e274  ldarg.0
0x3e275  call     int32 [mscorlib]System.Environment::get_TickCount()
0x3e27a  ldarg.0
0x3e27b  ldflda   valuetype [mscorlib]System.TimeSpan System.Windows.Threading.DispatcherTimer::_interval
0x3e280  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3e285  conv.i4
0x3e286  add
0x3e287  stfld    int32 System.Windows.Threading.DispatcherTimer::_dueTimeInTicks
0x3e28c  ldc.i4.1
0x3e28d  stloc.0
0x3e28e  leave.s  loc_3E29A
0x3e290  ldloc.3
0x3e291  brfalse.s loc_3E299
0x3e293  ldloc.2
0x3e294  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3e299  endfinally
0x3e29a  ldloc.0
0x3e29b  brfalse.s loc_3E2A8
0x3e29d  ldarg.0
0x3e29e  ldfld    class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherTimer::_dispatcher
0x3e2a3  callvirt instance void System.Windows.Threading.Dispatcher::UpdateWin32Timer()
0x3e2a8  ret
```
