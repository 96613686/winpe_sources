# MocompQpel16x16_Daytona

- ea: `0x180039d60`
- end: `0x180039d9c`
- name: `MocompQpel16x16_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel16x16_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 0x10u, a6, a7, 0);
}

```

## disassembly

```asm
0x180039d60  sub     rsp, 58h
0x180039d64  mov     eax, [rsp+58h+arg_30]
0x180039d6b  mov     [rsp+58h+var_18], 0
0x180039d70  mov     [rsp+58h+var_20], eax
0x180039d74  mov     eax, [rsp+58h+arg_28]
0x180039d7b  mov     [rsp+58h+var_28], eax
0x180039d7f  mov     eax, [rsp+58h+arg_20]
0x180039d86  mov     [rsp+58h+var_30], 10h
0x180039d8e  mov     [rsp+58h+var_38], eax
0x180039d92  call    MocompQpel_Daytona
0x180039d97  add     rsp, 58h
0x180039d9b  retn
```
