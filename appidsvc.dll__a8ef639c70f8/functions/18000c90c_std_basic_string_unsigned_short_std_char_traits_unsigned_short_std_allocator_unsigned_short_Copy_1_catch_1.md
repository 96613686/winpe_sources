# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000c90c`
- end: `0x18000c964`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011c8`
- `0x180001308`
- `0x18000c90c`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 32) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000c90c  mov     [rsp+arg_8], rdx
0x18000c911  push    rbp
0x18000c912  sub     rsp, 20h
0x18000c916  mov     rbp, rdx
0x18000c919  mov     rcx, [rbp+68h]
0x18000c91d  mov     [rbp+68h], rcx
0x18000c921  xor     eax, eax
0x18000c923  add     rcx, 1
0x18000c927  jnz     short loc_18000C92B
0x18000c929  jmp     short loc_18000C947
0x18000c92b  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c935  cmp     rcx, rax
0x18000c938  ja      short loc_18000C957
0x18000c93a  add     rcx, rcx; Size
0x18000c93d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c942  test    rax, rax
0x18000c945  jz      short loc_18000C957
0x18000c947  mov     [rbp+20h], rax
0x18000c94b  mov     rax, 0
0x18000c955  jmp     short loc_18000C95D
0x18000c957  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c95d  add     rsp, 20h
0x18000c961  pop     rbp
0x18000c962  retn
```
