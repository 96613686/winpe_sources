# MocompQpel16x16RndCtrl_Daytona

- ea: `0x180039d10`
- end: `0x180039d4c`
- name: `MocompQpel16x16RndCtrl_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel16x16RndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 0x10u, a6, a7, 1u);
}

```

## disassembly

```asm
0x180039d10  sub     rsp, 58h
0x180039d14  mov     eax, [rsp+58h+arg_30]
0x180039d1b  mov     [rsp+58h+var_18], 1
0x180039d20  mov     [rsp+58h+var_20], eax
0x180039d24  mov     eax, [rsp+58h+arg_28]
0x180039d2b  mov     [rsp+58h+var_28], eax
0x180039d2f  mov     eax, [rsp+58h+arg_20]
0x180039d36  mov     [rsp+58h+var_30], 10h
0x180039d3e  mov     [rsp+58h+var_38], eax
0x180039d42  call    MocompQpel_Daytona
0x180039d47  add     rsp, 58h
0x180039d4b  retn
```
