# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x14001235b`
- end: `0x1400123ae`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014fc`
- `0x140001758`
- `0x14001235b`

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
0x14001235b  mov     [rsp+arg_8], rdx
0x140012360  push    rbp
0x140012361  sub     rsp, 20h
0x140012365  mov     rbp, rdx
0x140012368  mov     rcx, [rbp+58h]
0x14001236c  mov     [rbp+58h], rcx
0x140012370  xor     eax, eax
0x140012372  add     rcx, 1
0x140012376  jz      short loc_140012399
0x140012378  mov     rax, 7FFFFFFFFFFFFFFFh
0x140012382  cmp     rcx, rax
0x140012385  ja      short loc_140012394
0x140012387  add     rcx, rcx; Size
0x14001238a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001238f  test    rax, rax
0x140012392  jnz     short loc_140012399
0x140012394  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140012399  mov     [rbp+68h], rax
0x14001239d  mov     rax, 0
0x1400123a7  add     rsp, 20h
0x1400123ab  pop     rbp
0x1400123ac  retn
```
