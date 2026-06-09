# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1

- ea: `0x18001291c`
- end: `0x18001296c`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1`
- size: `80`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800069e0`
- `0x180008088`
- `0x180008208`
- `0x18001291c`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_1(
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
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_180006A86;
}

```

## disassembly

```asm
0x18001291c  mov     [rsp+arg_8], rdx
0x180012921  push    rbp
0x180012922  sub     rsp, 20h
0x180012926  mov     rbp, rdx
0x180012929  mov     rcx, [rbp+68h]
0x18001292d  mov     [rbp+68h], rcx
0x180012931  xor     eax, eax
0x180012933  add     rcx, 1
0x180012937  jz      short loc_18001295A
0x180012939  mov     rax, 7FFFFFFFFFFFFFFFh
0x180012943  cmp     rcx, rax
0x180012946  ja      short loc_180012955
0x180012948  add     rcx, rcx; Size
0x18001294b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012950  test    rax, rax
0x180012953  jnz     short loc_18001295A
0x180012955  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001295a  mov     [rbp+78h], rax
0x18001295e  lea     rax, loc_180006A86
0x180012965  add     rsp, 20h
0x180012969  pop     rbp
0x18001296a  retn
```
