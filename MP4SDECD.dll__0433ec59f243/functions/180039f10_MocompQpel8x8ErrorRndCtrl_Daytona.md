# MocompQpel8x8ErrorRndCtrl_Daytona

- ea: `0x180039f10`
- end: `0x180039f60`
- name: `MocompQpel8x8ErrorRndCtrl_Daytona`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003a064`

## pseudocode

```c
__int64 __fastcall MocompQpel8x8ErrorRndCtrl_Daytona(
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

  return MocompQpelError_Daytona(a1, a2, a4, a3, a5, a6, v9, 8u, a7, a8, 1u);
}

```

## disassembly

```asm
0x180039f10  sub     rsp, 68h
0x180039f14  mov     eax, [rsp+68h+arg_38]
0x180039f1b  mov     r10, r9
0x180039f1e  mov     [rsp+68h+var_18], 1
0x180039f23  mov     r9, r8
0x180039f26  mov     [rsp+68h+var_20], eax
0x180039f2a  mov     r8, r10
0x180039f2d  mov     eax, [rsp+68h+arg_30]
0x180039f34  mov     [rsp+68h+var_28], eax
0x180039f38  mov     eax, [rsp+68h+arg_28]
0x180039f3f  mov     [rsp+68h+var_30], 8
0x180039f47  mov     [rsp+68h+var_40], eax
0x180039f4b  mov     eax, [rsp+68h+arg_20]
0x180039f52  mov     [rsp+68h+var_48], eax
0x180039f56  call    MocompQpelError_Daytona
0x180039f5b  add     rsp, 68h
0x180039f5f  retn
```
