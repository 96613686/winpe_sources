# System.Windows.Forms.CommonUnsafeNativeMethods::TryGetDpiAwarenessContextForWindow

- ea: `0x8faf0`
- end: `0x8fb30`
- name: `System.Windows.Forms.CommonUnsafeNativeMethods::TryGetDpiAwarenessContextForWindow`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8f8d0`
- `0x8fa40`
- `0x8fa50`
- `0x8faf0`
- `0x8fb30`

## string_xrefs

- `0x8faf2`: `user32.dll`
- `0x8fb03`: `user32.dll`

## pseudocode

```c

```

## disassembly

```asm
0x8faf0  ldc.i4.0
0x8faf1  stloc.0
0x8faf2  ldstr    aUser32Dll// "user32.dll"
0x8faf7  ldstr    aGetwindowdpiaw// "GetWindowDpiAwarenessContext"
0x8fafc  call     bool System.Windows.Forms.ApiHelper::IsApiAvailable(string libName, string procName)
0x8fb01  brfalse.s loc_8FB29
0x8fb03  ldstr    aUser32Dll// "user32.dll"
0x8fb08  ldstr    aGetawarenessfr// "GetAwarenessFromDpiAwarenessContext"
0x8fb0d  call     bool System.Windows.Forms.ApiHelper::IsApiAvailable(string libName, string procName)
0x8fb12  brfalse.s loc_8FB29
0x8fb14  ldarg.0
0x8fb15  call     native int System.Windows.Forms.CommonUnsafeNativeMethods::GetWindowDpiAwarenessContext(native int hWnd)
0x8fb1a  stloc.1
0x8fb1b  ldloc.1
0x8fb1c  call     valuetype DPI_AWARENESS System.Windows.Forms.CommonUnsafeNativeMethods::GetAwarenessFromDpiAwarenessContext(native int dpiAwarenessContext)
0x8fb21  stloc.2
0x8fb22  ldloc.2
0x8fb23  call     valuetype System.Windows.Forms.DpiAwarenessContext System.Windows.Forms.CommonUnsafeNativeMethods::ConvertToDpiAwarenessContext(valuetype DPI_AWARENESS dpiAwareness)
0x8fb28  stloc.0
0x8fb29  leave.s  loc_8FB2E
0x8fb2b  pop
0x8fb2c  leave.s  loc_8FB2E
0x8fb2e  ldloc.0
0x8fb2f  ret
```
