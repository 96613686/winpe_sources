# System.Windows.Forms.CommonUnsafeNativeMethods::TryGetThreadDpiAwarenessContext

- ea: `0x8fab0`
- end: `0x8fac9`
- name: `System.Windows.Forms.CommonUnsafeNativeMethods::TryGetThreadDpiAwarenessContext`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8f8d0`
- `0x8fa30`
- `0x8fab0`

## string_xrefs

- `0x8fab0`: `user32.dll`
- `0x8fab5`: `GetThreadDpiAwarenessContext`

## pseudocode

```c

```

## disassembly

```asm
0x8fab0  ldstr    aUser32Dll// "user32.dll"
0x8fab5  ldstr    aGetthreaddpiaw// "GetThreadDpiAwarenessContext"
0x8faba  call     bool System.Windows.Forms.ApiHelper::IsApiAvailable(string libName, string procName)
0x8fabf  brfalse.s loc_8FAC7
0x8fac1  call     valuetype System.Windows.Forms.DpiAwarenessContext System.Windows.Forms.CommonUnsafeNativeMethods::GetThreadDpiAwarenessContext()
0x8fac6  ret
0x8fac7  ldc.i4.0
0x8fac8  ret
```
