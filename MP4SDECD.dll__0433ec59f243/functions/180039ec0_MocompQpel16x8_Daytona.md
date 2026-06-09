# MocompQpel16x8_Daytona

- ea: `0x180039ec0`
- end: `0x180039efc`
- name: `MocompQpel16x8_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel16x8_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 0, a6, a7, 0);
}

```

## disassembly

```asm
0x180039ec0  sub     rsp, 58h
0x180039ec4  mov     eax, [rsp+58h+arg_30]
0x180039ecb  mov     [rsp+58h+var_18], 0
0x180039ed0  mov     [rsp+58h+var_20], eax
0x180039ed4  mov     eax, [rsp+58h+arg_28]
0x180039edb  mov     [rsp+58h+var_28], eax
0x180039edf  mov     eax, [rsp+58h+arg_20]
0x180039ee6  mov     [rsp+58h+var_30], 0
0x180039eee  mov     [rsp+58h+var_38], eax
0x180039ef2  call    MocompQpel_Daytona
0x180039ef7  add     rsp, 58h
0x180039efb  retn
```
