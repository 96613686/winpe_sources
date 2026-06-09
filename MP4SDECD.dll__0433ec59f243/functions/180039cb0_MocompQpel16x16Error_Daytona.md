# MocompQpel16x16Error_Daytona

- ea: `0x180039cb0`
- end: `0x180039d00`
- name: `MocompQpel16x16Error_Daytona`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003a064`

## pseudocode

```c
__int64 __fastcall MocompQpel16x16Error_Daytona(
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

  return MocompQpelError_Daytona(a1, a2, a4, a3, a5, a6, v9, 0x10u, a7, a8, 0);
}

```

## disassembly

```asm
0x180039cb0  sub     rsp, 68h
0x180039cb4  mov     eax, [rsp+68h+arg_38]
0x180039cbb  mov     r10, r9
0x180039cbe  mov     [rsp+68h+var_18], 0
0x180039cc3  mov     r9, r8
0x180039cc6  mov     [rsp+68h+var_20], eax
0x180039cca  mov     r8, r10
0x180039ccd  mov     eax, [rsp+68h+arg_30]
0x180039cd4  mov     [rsp+68h+var_28], eax
0x180039cd8  mov     eax, [rsp+68h+arg_28]
0x180039cdf  mov     [rsp+68h+var_30], 10h
0x180039ce7  mov     [rsp+68h+var_40], eax
0x180039ceb  mov     eax, [rsp+68h+arg_20]
0x180039cf2  mov     [rsp+68h+var_48], eax
0x180039cf6  call    MocompQpelError_Daytona
0x180039cfb  add     rsp, 68h
0x180039cff  retn
```
