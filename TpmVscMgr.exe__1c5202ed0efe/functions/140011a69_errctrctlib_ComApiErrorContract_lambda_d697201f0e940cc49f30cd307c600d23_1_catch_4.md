# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$4

- ea: `0x140011a69`
- end: `0x140011ab7`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$4`
- size: `78`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011a69`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  signed int v2; // ecx

  v2 = *(_DWORD *)(*(_QWORD *)(a2 + 56) + 24LL);
  if ( (v2 & 0xE0000000) == 0xE0000000 )
  {
    v2 = (unsigned __int16)v2 | 0x800F0000;
  }
  else if ( v2 > 0 )
  {
    v2 = (unsigned __int16)v2 | 0x80070000;
  }
  *(_DWORD *)(a2 + 80) = v2;
  return 0;
}

```

## disassembly

```asm
0x140011a69  mov     [rsp+arg_8], rdx
0x140011a6e  push    rbp
0x140011a6f  sub     rsp, 20h
0x140011a73  mov     rbp, rdx
0x140011a76  mov     rax, [rbp+38h]
0x140011a7a  mov     ecx, [rax+18h]
0x140011a7d  mov     eax, ecx
0x140011a7f  and     eax, 0E0000000h
0x140011a84  cmp     eax, 0E0000000h
0x140011a89  jnz     short loc_140011A96
0x140011a8b  movzx   ecx, cx
0x140011a8e  or      ecx, 800F0000h
0x140011a94  jmp     short loc_140011AA3
0x140011a96  test    ecx, ecx
0x140011a98  jle     short loc_140011AA3
0x140011a9a  movzx   ecx, cx
0x140011a9d  or      ecx, 80070000h
0x140011aa3  mov     [rbp+50h], ecx
0x140011aa6  mov     rax, 0
0x140011ab0  add     rsp, 20h
0x140011ab4  pop     rbp
0x140011ab5  retn
```
