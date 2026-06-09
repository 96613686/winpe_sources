# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000cfff`
- end: `0x18000d052`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x18000cfff`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000cfff  mov     [rsp+arg_8], rdx
0x18000d004  push    rbp
0x18000d005  sub     rsp, 20h
0x18000d009  mov     rbp, rdx
0x18000d00c  mov     rcx, [rbp+58h]
0x18000d010  mov     [rbp+58h], rcx
0x18000d014  xor     eax, eax
0x18000d016  add     rcx, 1
0x18000d01a  jz      short loc_18000D03D
0x18000d01c  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d026  cmp     rcx, rax
0x18000d029  ja      short loc_18000D038
0x18000d02b  add     rcx, rcx; Size
0x18000d02e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d033  test    rax, rax
0x18000d036  jnz     short loc_18000D03D
0x18000d038  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d03d  mov     [rbp+68h], rax
0x18000d041  mov     rax, 0
0x18000d04b  add     rsp, 20h
0x18000d04f  pop     rbp
0x18000d050  retn
```
