# NGenTask.TaskExecutive::IsBatteryLowOrCritical

- ea: `0x1e30`
- end: `0x1f13`
- name: `NGenTask.TaskExecutive::IsBatteryLowOrCritical`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x2c0`
- `0x310`

## callees

- `0x1e30`
- `0x2c30`
- `0x3200`

## string_xrefs

- `0x1e3a`: `GetSystemPowerStatus failed with error {0}`
- `0x1e85`: `ACLineStatus is unknown, assuming on battery`
- `0x1e98`: `ACLineStatus is invalid ({0}), assuming on battery`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldloca.s 0
0x1e32  call     bool NGenTask.Win32Native::GetSystemPowerStatus([out] valuetype SYSTEM_POWER_STATUS& lpSystemPowerStatus)
0x1e37  brtrue.s loc_1E59
0x1e39  ldc.i4.0
0x1e3a  ldstr    aGetsystempower// "GetSystemPowerStatus failed with error "...
0x1e3f  ldc.i4.1
0x1e40  newarr   [mscorlib]System.Object
0x1e45  dup
0x1e46  ldc.i4.0
0x1e47  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1e4c  box      [mscorlib]System.Int32
0x1e51  stelem.ref
0x1e52  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1e57  ldc.i4.1
0x1e58  ret
0x1e59  ldloc.0
0x1e5a  ldfld    unsigned int8 SYSTEM_POWER_STATUS::ACLineStatus
0x1e5f  stloc.1
0x1e60  ldloc.1
0x1e61  brfalse.s loc_1EA8
0x1e63  ldloc.1
0x1e64  ldc.i4.1
0x1e65  beq.s    loc_1E71
0x1e67  ldloc.1
0x1e68  ldc.i4   0xFF
0x1e6d  beq.s    loc_1E84
0x1e6f  br.s     loc_1E97
0x1e71  ldc.i4.3
0x1e72  ldstr    aNotOnBattery// "Not on battery"
0x1e77  ldc.i4.0
0x1e78  newarr   [mscorlib]System.Object
0x1e7d  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1e82  ldc.i4.0
0x1e83  ret
0x1e84  ldc.i4.1
0x1e85  ldstr    aAclinestatusIs// "ACLineStatus is unknown, assuming on ba"...
0x1e8a  ldc.i4.0
0x1e8b  newarr   [mscorlib]System.Object
0x1e90  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1e95  br.s     loc_1EA8
0x1e97  ldc.i4.1
0x1e98  ldstr    aAclinestatusIs_0// "ACLineStatus is invalid ({0}), assuming"...
0x1e9d  ldc.i4.0
0x1e9e  newarr   [mscorlib]System.Object
0x1ea3  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1ea8  ldloc.0
0x1ea9  ldfld    unsigned int8 SYSTEM_POWER_STATUS::BatteryFlag
0x1eae  ldc.i4   0xFF
0x1eb3  bne.un.s loc_1EC8
0x1eb5  ldc.i4.1
0x1eb6  ldstr    aBatteryStatusU// "Battery status unknown, assuming low ba"...
0x1ebb  ldc.i4.0
0x1ebc  newarr   [mscorlib]System.Object
0x1ec1  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1ec6  ldc.i4.1
0x1ec7  ret
0x1ec8  ldloc.0
0x1ec9  ldfld    unsigned int8 SYSTEM_POWER_STATUS::BatteryFlag
0x1ece  ldc.i4.6
0x1ecf  and
0x1ed0  brfalse.s loc_1EE5
0x1ed2  ldc.i4.2
0x1ed3  ldstr    aLowOrCriticalB// "Low or critical battery level, aborting"
0x1ed8  ldc.i4.0
0x1ed9  newarr   [mscorlib]System.Object
0x1ede  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1ee3  ldc.i4.1
0x1ee4  ret
0x1ee5  ldloc.0
0x1ee6  ldfld    unsigned int8 SYSTEM_POWER_STATUS::SystemStatusFlag
0x1eeb  brfalse.s loc_1F00
0x1eed  ldc.i4.2
0x1eee  ldstr    aBatterySaverOn// "Battery saver on, aborting"
0x1ef3  ldc.i4.0
0x1ef4  newarr   [mscorlib]System.Object
0x1ef9  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1efe  ldc.i4.1
0x1eff  ret
0x1f00  ldc.i4.3
0x1f01  ldstr    aBatteryLevelOk// "Battery level OK"
0x1f06  ldc.i4.0
0x1f07  newarr   [mscorlib]System.Object
0x1f0c  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1f11  ldc.i4.0
0x1f12  ret
```
