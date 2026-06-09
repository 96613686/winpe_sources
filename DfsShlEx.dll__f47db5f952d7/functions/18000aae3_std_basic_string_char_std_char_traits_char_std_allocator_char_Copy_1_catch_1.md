# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000aae3`
- end: `0x18000ab27`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001164`
- `0x180001348`
- `0x1800014a8`
- `0x18000aae3`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_1800013D1;
}

```

## disassembly

```asm
0x18000aae3  mov     [rsp+arg_8], rdx
0x18000aae8  push    rbp
0x18000aae9  sub     rsp, 20h
0x18000aaed  mov     rbp, rdx
0x18000aaf0  mov     rcx, [rbp+68h]
0x18000aaf4  mov     [rbp+68h], rcx
0x18000aaf8  xor     eax, eax
0x18000aafa  add     rcx, 1; Size
0x18000aafe  jz      short loc_18000AB15
0x18000ab00  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ab04  ja      short loc_18000AB10
0x18000ab06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab0b  test    rax, rax
0x18000ab0e  jnz     short loc_18000AB15
0x18000ab10  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ab15  mov     [rbp+78h], rax
0x18000ab19  lea     rax, loc_1800013D1
0x18000ab20  add     rsp, 20h
0x18000ab24  pop     rbp
0x18000ab25  retn
```
