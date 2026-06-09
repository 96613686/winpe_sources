# DereferenceSession(_MINIPORT_INTERFACE_CONTEXT *)

- ea: `0x1400018f0`
- end: `0x14000192d`
- name: `?DereferenceSession@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z`
- size: `61`
- prototype: `void __fastcall(struct _MINIPORT_INTERFACE_CONTEXT *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x140001b34`
- `0x1400031d8`
- `0x1400061b0`
- `0x140006d90`
- `0x140007180`
- `0x14000f6c0`
- `0x14000f970`
- `0x140010b00`
- `0x140011330`
- `0x1400140c0`
- `0x1400212ec`
- `0x14002253c`
- `0x140026698`
- `0x140026e44`
- `0x140031e20`
- `0x14003c670`
- `0x14003cdf8`
- `0x14003fa34`
- `0x14003ffbc`

## callees

- `0x140047e90`

## pseudocode

```c
void __fastcall DereferenceSession(struct _MINIPORT_INTERFACE_CONTEXT *a1)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, const char *))(WdfFunctions_01031 + 1648))(
    WdfDriverGlobals,
    *((_QWORD *)a1 + 1),
    0,
    289,
    "onecoreuap\\net\\wwan\\wmbclass\\mbbcx\\src\\adapter.cpp");
}

```

## disassembly

```asm
0x1400018f0  sub     rsp, 38h
0x1400018f4  mov     rax, cs:WdfFunctions_01031
0x1400018fb  lea     rdx, aOnecoreuapNetW_0; "onecoreuap\\net\\wwan\\wmbclass\\mbbcx"...
0x140001902  mov     [rsp+38h+var_18], rdx
0x140001907  mov     r9d, 121h
0x14000190d  mov     rdx, [rcx+8]
0x140001911  xor     r8d, r8d
0x140001914  mov     rcx, cs:WdfDriverGlobals
0x14000191b  mov     rax, [rax+670h]
0x140001922  call    _guard_dispatch_icall
0x140001927  add     rsp, 38h
0x14000192b  retn
```
