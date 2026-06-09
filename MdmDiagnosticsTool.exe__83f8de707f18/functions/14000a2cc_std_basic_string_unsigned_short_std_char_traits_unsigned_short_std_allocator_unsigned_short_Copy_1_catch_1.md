# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x14000a2cc`
- end: `0x14000a31f`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014e4`
- `0x140001688`
- `0x14000a2cc`

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
0x14000a2cc  mov     [rsp+arg_8], rdx
0x14000a2d1  push    rbp
0x14000a2d2  sub     rsp, 20h
0x14000a2d6  mov     rbp, rdx
0x14000a2d9  mov     rcx, [rbp+58h]
0x14000a2dd  mov     [rbp+58h], rcx
0x14000a2e1  xor     eax, eax
0x14000a2e3  add     rcx, 1
0x14000a2e7  jz      short loc_14000A30A
0x14000a2e9  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000a2f3  cmp     rcx, rax
0x14000a2f6  ja      short loc_14000A305
0x14000a2f8  add     rcx, rcx; Size
0x14000a2fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a300  test    rax, rax
0x14000a303  jnz     short loc_14000A30A
0x14000a305  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000a30a  mov     [rbp+68h], rax
0x14000a30e  mov     rax, 0
0x14000a318  add     rsp, 20h
0x14000a31c  pop     rbp
0x14000a31d  retn
```
