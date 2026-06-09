# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180036286`
- end: `0x1800362d9`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x180036286`

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
0x180036286  mov     [rsp+arg_8], rdx
0x18003628b  push    rbp
0x18003628c  sub     rsp, 20h
0x180036290  mov     rbp, rdx
0x180036293  mov     rcx, [rbp+58h]
0x180036297  mov     [rbp+58h], rcx
0x18003629b  xor     eax, eax
0x18003629d  add     rcx, 1
0x1800362a1  jz      short loc_1800362C4
0x1800362a3  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800362ad  cmp     rcx, rax
0x1800362b0  ja      short loc_1800362BF
0x1800362b2  add     rcx, rcx; Size
0x1800362b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800362ba  test    rax, rax
0x1800362bd  jnz     short loc_1800362C4
0x1800362bf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800362c4  mov     [rbp+68h], rax
0x1800362c8  mov     rax, 0
0x1800362d2  add     rsp, 20h
0x1800362d6  pop     rbp
0x1800362d7  retn
```
