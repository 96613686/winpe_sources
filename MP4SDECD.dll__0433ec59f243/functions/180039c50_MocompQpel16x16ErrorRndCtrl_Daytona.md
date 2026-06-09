# MocompQpel16x16ErrorRndCtrl_Daytona

- ea: `0x180039c50`
- end: `0x180039ca0`
- name: `MocompQpel16x16ErrorRndCtrl_Daytona`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003a064`

## pseudocode

```c
__int64 __fastcall MocompQpel16x16ErrorRndCtrl_Daytona(
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

  return MocompQpelError_Daytona(a1, a2, a4, a3, a5, a6, v9, 0x10u, a7, a8, 1u);
}

```

## disassembly

```asm
0x180039c50  sub     rsp, 68h
0x180039c54  mov     eax, [rsp+68h+arg_38]
0x180039c5b  mov     r10, r9
0x180039c5e  mov     [rsp+68h+var_18], 1
0x180039c63  mov     r9, r8
0x180039c66  mov     [rsp+68h+var_20], eax
0x180039c6a  mov     r8, r10
0x180039c6d  mov     eax, [rsp+68h+arg_30]
0x180039c74  mov     [rsp+68h+var_28], eax
0x180039c78  mov     eax, [rsp+68h+arg_28]
0x180039c7f  mov     [rsp+68h+var_30], 10h
0x180039c87  mov     [rsp+68h+var_40], eax
0x180039c8b  mov     eax, [rsp+68h+arg_20]
0x180039c92  mov     [rsp+68h+var_48], eax
0x180039c96  call    MocompQpelError_Daytona
0x180039c9b  add     rsp, 68h
0x180039c9f  retn
```
