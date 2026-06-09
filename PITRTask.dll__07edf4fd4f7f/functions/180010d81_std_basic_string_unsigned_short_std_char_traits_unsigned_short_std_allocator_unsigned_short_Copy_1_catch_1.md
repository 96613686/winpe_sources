# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180010d81`
- end: `0x180010dd4`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800014b4`
- `0x180001658`
- `0x180010d81`

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
0x180010d81  mov     [rsp+arg_8], rdx
0x180010d86  push    rbp
0x180010d87  sub     rsp, 20h
0x180010d8b  mov     rbp, rdx
0x180010d8e  mov     rcx, [rbp+58h]
0x180010d92  mov     [rbp+58h], rcx
0x180010d96  xor     eax, eax
0x180010d98  add     rcx, 1
0x180010d9c  jz      short loc_180010DBF
0x180010d9e  mov     rax, 7FFFFFFFFFFFFFFFh
0x180010da8  cmp     rcx, rax
0x180010dab  ja      short loc_180010DBA
0x180010dad  add     rcx, rcx; Size
0x180010db0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010db5  test    rax, rax
0x180010db8  jnz     short loc_180010DBF
0x180010dba  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180010dbf  mov     [rbp+68h], rax
0x180010dc3  mov     rax, 0
0x180010dcd  add     rsp, 20h
0x180010dd1  pop     rbp
0x180010dd2  retn
```
