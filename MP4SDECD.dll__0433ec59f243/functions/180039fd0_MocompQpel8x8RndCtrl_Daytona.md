# MocompQpel8x8RndCtrl_Daytona

- ea: `0x180039fd0`
- end: `0x18003a00c`
- name: `MocompQpel8x8RndCtrl_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel8x8RndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 8u, a6, a7, 1u);
}

```

## disassembly

```asm
0x180039fd0  sub     rsp, 58h
0x180039fd4  mov     eax, [rsp+58h+arg_30]
0x180039fdb  mov     [rsp+58h+var_18], 1
0x180039fe0  mov     [rsp+58h+var_20], eax
0x180039fe4  mov     eax, [rsp+58h+arg_28]
0x180039feb  mov     [rsp+58h+var_28], eax
0x180039fef  mov     eax, [rsp+58h+arg_20]
0x180039ff6  mov     [rsp+58h+var_30], 8
0x180039ffe  mov     [rsp+58h+var_38], eax
0x18003a002  call    MocompQpel_Daytona
0x18003a007  add     rsp, 58h
0x18003a00b  retn
```
