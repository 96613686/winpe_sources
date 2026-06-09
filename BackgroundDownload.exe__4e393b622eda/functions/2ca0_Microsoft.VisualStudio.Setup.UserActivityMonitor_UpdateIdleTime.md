# Microsoft.VisualStudio.Setup.UserActivityMonitor::UpdateIdleTime

- ea: `0x2ca0`
- end: `0x2cd8`
- name: `Microsoft.VisualStudio.Setup.UserActivityMonitor::UpdateIdleTime`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2bb0`
- `0x2c00`

## callees

- `0xb30`
- `0xc30`
- `0x2ca0`

## pseudocode

```c

```

## disassembly

```asm
0x2ca0  ldloca.s 0
0x2ca2  initobj  Windows.Win32.UI.Input.KeyboardAndMouse.LASTINPUTINFO
0x2ca8  ldloca.s 0
0x2caa  ldloc.0
0x2cab  call     T0x2B00003B
0x2cb0  stfld    unsigned int32 Windows.Win32.UI.Input.KeyboardAndMouse.LASTINPUTINFO::cbSize
0x2cb5  ldloca.s 0
0x2cb7  ldc.i4.0
0x2cb8  stfld    unsigned int32 Windows.Win32.UI.Input.KeyboardAndMouse.LASTINPUTINFO::dwTime
0x2cbd  ldloca.s 0
0x2cbf  call     valuetype Windows.Win32.Foundation.BOOL Windows.Win32.PInvoke::GetLastInputInfo(valuetype Windows.Win32.UI.Input.KeyboardAndMouse.LASTINPUTINFO& plii)
0x2cc4  call     bool Windows.Win32.Foundation.BOOL::op_Implicit(valuetype Windows.Win32.Foundation.BOOL value)
0x2cc9  brfalse.s loc_2CD7
0x2ccb  ldarg.0
0x2ccc  ldloc.0
0x2ccd  ldfld    unsigned int32 Windows.Win32.UI.Input.KeyboardAndMouse.LASTINPUTINFO::dwTime
0x2cd2  stfld    unsigned int32 Microsoft.VisualStudio.Setup.UserActivityMonitor::lastInputTime
0x2cd7  ret
```
