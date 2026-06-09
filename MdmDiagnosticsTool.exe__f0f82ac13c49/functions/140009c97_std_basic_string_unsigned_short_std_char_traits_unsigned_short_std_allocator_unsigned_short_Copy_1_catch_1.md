# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x140009c97`
- end: `0x140009cea`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014b4`
- `0x140001658`
- `0x140009c97`

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
0x140009c97  mov     [rsp+arg_8], rdx
0x140009c9c  push    rbp
0x140009c9d  sub     rsp, 20h
0x140009ca1  mov     rbp, rdx
0x140009ca4  mov     rcx, [rbp+58h]
0x140009ca8  mov     [rbp+58h], rcx
0x140009cac  xor     eax, eax
0x140009cae  add     rcx, 1
0x140009cb2  jz      short loc_140009CD5
0x140009cb4  mov     rax, 7FFFFFFFFFFFFFFFh
0x140009cbe  cmp     rcx, rax
0x140009cc1  ja      short loc_140009CD0
0x140009cc3  add     rcx, rcx; Size
0x140009cc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009ccb  test    rax, rax
0x140009cce  jnz     short loc_140009CD5
0x140009cd0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140009cd5  mov     [rbp+68h], rax
0x140009cd9  mov     rax, 0
0x140009ce3  add     rsp, 20h
0x140009ce7  pop     rbp
0x140009ce8  retn
```
