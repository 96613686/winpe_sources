# MocompQpel16x8ErrorRndCtrl_Daytona

- ea: `0x180039db0`
- end: `0x180039e00`
- name: `MocompQpel16x8ErrorRndCtrl_Daytona`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003a064`

## pseudocode

```c
__int64 __fastcall MocompQpel16x8ErrorRndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8)
{
  int v9; // [rsp+30h] [rbp-38h]

  return MocompQpelError_Daytona(a1, a2, a4, a3, a5, a6, v9, 0, a7, a8, 1u);
}

```

## disassembly

```asm
0x180039db0  sub     rsp, 68h
0x180039db4  mov     eax, [rsp+68h+arg_38]
0x180039dbb  mov     r10, r9
0x180039dbe  mov     [rsp+68h+var_18], 1
0x180039dc3  mov     r9, r8
0x180039dc6  mov     [rsp+68h+var_20], eax
0x180039dca  mov     r8, r10
0x180039dcd  mov     eax, [rsp+68h+arg_30]
0x180039dd4  mov     [rsp+68h+var_28], eax
0x180039dd8  mov     eax, [rsp+68h+arg_28]
0x180039ddf  mov     [rsp+68h+var_30], 0
0x180039de7  mov     [rsp+68h+var_40], eax
0x180039deb  mov     eax, [rsp+68h+arg_20]
0x180039df2  mov     [rsp+68h+var_48], eax
0x180039df6  call    MocompQpelError_Daytona
0x180039dfb  add     rsp, 68h
0x180039dff  retn
```
