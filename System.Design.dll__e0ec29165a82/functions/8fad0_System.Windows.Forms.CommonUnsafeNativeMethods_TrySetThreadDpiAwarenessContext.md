# System.Windows.Forms.CommonUnsafeNativeMethods::TrySetThreadDpiAwarenessContext

- ea: `0x8fad0`
- end: `0x8faea`
- name: `System.Windows.Forms.CommonUnsafeNativeMethods::TrySetThreadDpiAwarenessContext`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1120e0`

## callees

- `0x8f8d0`
- `0x8fa60`
- `0x8fad0`

## string_xrefs

- `0x8fad0`: `user32.dll`
- `0x8fad5`: `SetThreadDpiAwarenessContext`

## pseudocode

```c

```

## disassembly

```asm
0x8fad0  ldstr    aUser32Dll// "user32.dll"
0x8fad5  ldstr    aSetthreaddpiaw// "SetThreadDpiAwarenessContext"
0x8fada  call     bool System.Windows.Forms.ApiHelper::IsApiAvailable(string libName, string procName)
0x8fadf  brfalse.s loc_8FAE8
0x8fae1  ldarg.0
0x8fae2  call     valuetype System.Windows.Forms.DpiAwarenessContext System.Windows.Forms.CommonUnsafeNativeMethods::SetThreadDpiAwarenessContext(valuetype System.Windows.Forms.DpiAwarenessContext dpiContext)
0x8fae7  ret
0x8fae8  ldc.i4.0
0x8fae9  ret
```
