# SspirProcessSecurityContext2

- ea: `0x180002e70`
- end: `0x180002fa6`
- name: `SspirProcessSecurityContext2`
- size: `310`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _OWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirProcessSecurityContext2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6,
        __int128 *a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        _OWORD *a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22)
{
  SspiSrvCallBegin(a2);
  return SspirProcessSecurityContext(
           a1,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           a10,
           a11,
           a12,
           a13,
           a14,
           a15,
           a16,
           a17,
           a18,
           a19,
           a20,
           a21,
           a22);
}

```

## disassembly

```asm
0x180002e70  mov     [rsp+arg_0], rbx
0x180002e75  mov     [rsp+arg_8], rsi
0x180002e7a  push    rdi
0x180002e7b  sub     rsp, 0B0h
0x180002e82  mov     rbx, rcx
0x180002e85  mov     rdi, r9
0x180002e88  mov     rcx, rdx
0x180002e8b  mov     rsi, r8
0x180002e8e  call    SspiSrvCallBegin
0x180002e93  mov     rax, [rsp+0B8h+arg_A8]
0x180002e9b  mov     r8, rdi
0x180002e9e  mov     [rsp+0B8h+var_18], rax
0x180002ea6  mov     rdx, rsi
0x180002ea9  mov     rax, [rsp+0B8h+arg_A0]
0x180002eb1  mov     rcx, rbx
0x180002eb4  mov     r9, [rsp+0B8h+arg_20]
0x180002ebc  mov     [rsp+0B8h+var_20], rax
0x180002ec4  mov     rax, [rsp+0B8h+arg_98]
0x180002ecc  mov     [rsp+0B8h+var_28], rax
0x180002ed4  mov     rax, [rsp+0B8h+arg_90]
0x180002edc  mov     [rsp+0B8h+var_30], rax
0x180002ee4  mov     rax, [rsp+0B8h+arg_88]
0x180002eec  mov     [rsp+0B8h+var_38], rax
0x180002ef4  mov     rax, [rsp+0B8h+arg_80]
0x180002efc  mov     [rsp+0B8h+var_40], rax
0x180002f01  mov     rax, [rsp+0B8h+arg_78]
0x180002f09  mov     [rsp+0B8h+var_48], rax
0x180002f0e  mov     rax, [rsp+0B8h+arg_70]
0x180002f16  mov     [rsp+0B8h+var_50], rax
0x180002f1b  mov     rax, [rsp+0B8h+arg_68]
0x180002f23  mov     [rsp+0B8h+var_58], rax
0x180002f28  mov     rax, [rsp+0B8h+arg_60]
0x180002f30  mov     [rsp+0B8h+var_60], rax
0x180002f35  mov     rax, [rsp+0B8h+arg_58]
0x180002f3d  mov     [rsp+0B8h+var_68], rax
0x180002f42  mov     rax, [rsp+0B8h+arg_50]
0x180002f4a  mov     [rsp+0B8h+var_70], rax
0x180002f4f  mov     rax, [rsp+0B8h+arg_48]
0x180002f57  mov     [rsp+0B8h+var_78], rax
0x180002f5c  mov     eax, [rsp+0B8h+arg_40]
0x180002f63  mov     [rsp+0B8h+var_80], eax
0x180002f67  mov     eax, [rsp+0B8h+arg_38]
0x180002f6e  mov     [rsp+0B8h+var_88], eax
0x180002f72  mov     rax, [rsp+0B8h+arg_30]
0x180002f7a  mov     [rsp+0B8h+var_90], rax
0x180002f7f  mov     rax, [rsp+0B8h+arg_28]
0x180002f87  mov     [rsp+0B8h+var_98], rax
0x180002f8c  call    SspirProcessSecurityContext
0x180002f91  lea     r11, [rsp+0B8h+var_8]
0x180002f99  mov     rbx, [r11+10h]
0x180002f9d  mov     rsi, [r11+18h]
0x180002fa1  mov     rsp, r11
0x180002fa4  pop     rdi
0x180002fa5  retn
```
