# MocompQpel8x8_Daytona

- ea: `0x18003a020`
- end: `0x18003a05c`
- name: `MocompQpel8x8_Daytona`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025ae8`

## pseudocode

```c
__int64 __fastcall MocompQpel8x8_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  return MocompQpel_Daytona(a1, a2, a3, a4, a5, 8u, a6, a7, 0);
}

```

## disassembly

```asm
0x18003a020  sub     rsp, 58h
0x18003a024  mov     eax, [rsp+58h+arg_30]
0x18003a02b  mov     [rsp+58h+var_18], 0
0x18003a030  mov     [rsp+58h+var_20], eax
0x18003a034  mov     eax, [rsp+58h+arg_28]
0x18003a03b  mov     [rsp+58h+var_28], eax
0x18003a03f  mov     eax, [rsp+58h+arg_20]
0x18003a046  mov     [rsp+58h+var_30], 8
0x18003a04e  mov     [rsp+58h+var_38], eax
0x18003a052  call    MocompQpel_Daytona
0x18003a057  add     rsp, 58h
0x18003a05b  retn
```
