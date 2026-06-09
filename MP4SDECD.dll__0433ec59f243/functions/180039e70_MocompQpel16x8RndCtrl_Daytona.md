# MocompQpel16x8RndCtrl_Daytona

- ea: `0x180039e70`
- end: `0x180039eac`
- name: `MocompQpel16x8RndCtrl_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel16x8RndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 0, a6, a7, 1u);
}

```

## disassembly

```asm
0x180039e70  sub     rsp, 58h
0x180039e74  mov     eax, [rsp+58h+arg_30]
0x180039e7b  mov     [rsp+58h+var_18], 1
0x180039e80  mov     [rsp+58h+var_20], eax
0x180039e84  mov     eax, [rsp+58h+arg_28]
0x180039e8b  mov     [rsp+58h+var_28], eax
0x180039e8f  mov     eax, [rsp+58h+arg_20]
0x180039e96  mov     [rsp+58h+var_30], 0
0x180039e9e  mov     [rsp+58h+var_38], eax
0x180039ea2  call    MocompQpel_Daytona
0x180039ea7  add     rsp, 58h
0x180039eab  retn
```
