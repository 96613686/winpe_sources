# SspirLogonUser2

- ea: `0x180002c70`
- end: `0x180002d56`
- name: `SspirLogonUser2`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, unsigned int, int, __int64, __int64, unsigned int *, int, __int64, __int64, _QWORD *, __int64, __int64, _QWORD *, _OWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016d0`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirLogonUser2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        unsigned int *a9,
        int a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        __int64 a15,
        _QWORD *a16,
        _OWORD *a17)
{
  SspiSrvCallBegin(a2);
  return SspirLogonUser(a1, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17);
}

```

## disassembly

```asm
0x180002c70  mov     [rsp+arg_0], rbx
0x180002c75  mov     [rsp+arg_8], rsi
0x180002c7a  push    rdi
0x180002c7b  sub     rsp, 80h
0x180002c82  mov     rbx, rcx
0x180002c85  mov     rdi, r9
0x180002c88  mov     rcx, rdx
0x180002c8b  mov     rsi, r8
0x180002c8e  call    SspiSrvCallBegin
0x180002c93  mov     rax, [rsp+88h+arg_80]
0x180002c9b  mov     r8, rdi
0x180002c9e  mov     r9d, [rsp+88h+arg_20]
0x180002ca6  mov     rdx, rsi
0x180002ca9  mov     [rsp+88h+var_10], rax
0x180002cae  mov     rcx, rbx
0x180002cb1  mov     rax, [rsp+88h+arg_78]
0x180002cb9  mov     [rsp+88h+var_18], rax
0x180002cbe  mov     rax, [rsp+88h+arg_70]
0x180002cc6  mov     [rsp+88h+var_20], rax
0x180002ccb  mov     rax, [rsp+88h+arg_68]
0x180002cd3  mov     [rsp+88h+var_28], rax
0x180002cd8  mov     rax, [rsp+88h+arg_60]
0x180002ce0  mov     [rsp+88h+var_30], rax
0x180002ce5  mov     rax, [rsp+88h+arg_58]
0x180002ced  mov     [rsp+88h+var_38], rax
0x180002cf2  mov     rax, [rsp+88h+arg_50]
0x180002cfa  mov     [rsp+88h+var_40], rax
0x180002cff  mov     eax, [rsp+88h+arg_48]
0x180002d06  mov     [rsp+88h+var_48], eax
0x180002d0a  mov     rax, [rsp+88h+arg_40]
0x180002d12  mov     [rsp+88h+var_50], rax
0x180002d17  mov     rax, [rsp+88h+arg_38]
0x180002d1f  mov     [rsp+88h+var_58], rax
0x180002d24  mov     rax, [rsp+88h+arg_30]
0x180002d2c  mov     [rsp+88h+var_60], rax
0x180002d31  mov     eax, [rsp+88h+arg_28]
0x180002d38  mov     [rsp+88h+var_68], eax
0x180002d3c  call    SspirLogonUser
0x180002d41  lea     r11, [rsp+88h+var_8]
0x180002d49  mov     rbx, [r11+10h]
0x180002d4d  mov     rsi, [r11+18h]
0x180002d51  mov     rsp, r11
0x180002d54  pop     rdi
0x180002d55  retn
```
