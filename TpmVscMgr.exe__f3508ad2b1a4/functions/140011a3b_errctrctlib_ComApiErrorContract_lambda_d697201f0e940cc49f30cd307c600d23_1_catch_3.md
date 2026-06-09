# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$3

- ea: `0x140011a3b`
- end: `0x140011a63`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$3`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  return 0;
}

```

## disassembly

```asm
0x140011a3b  mov     [rsp+arg_8], rdx
0x140011a40  push    rbp
0x140011a41  sub     rsp, 20h
0x140011a45  mov     rbp, rdx
0x140011a48  mov     rax, [rbp+30h]
0x140011a4c  mov     ecx, [rax+18h]
0x140011a4f  mov     [rbp+50h], ecx
0x140011a52  mov     rax, 0
0x140011a5c  add     rsp, 20h
0x140011a60  pop     rbp
0x140011a61  retn
```
