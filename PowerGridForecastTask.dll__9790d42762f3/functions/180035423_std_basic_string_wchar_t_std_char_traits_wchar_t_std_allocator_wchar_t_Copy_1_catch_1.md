# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1

- ea: `0x180035423`
- end: `0x180035473`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1`
- size: `80`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x18000bbe0`
- `0x180035423`

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
  return &loc_18000BC87;
}

```

## disassembly

```asm
0x180035423  mov     [rsp+arg_8], rdx
0x180035428  push    rbp
0x180035429  sub     rsp, 20h
0x18003542d  mov     rbp, rdx
0x180035430  mov     rcx, [rbp+68h]
0x180035434  mov     [rbp+68h], rcx
0x180035438  xor     eax, eax
0x18003543a  add     rcx, 1
0x18003543e  jz      short loc_180035461
0x180035440  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003544a  cmp     rcx, rax
0x18003544d  ja      short loc_18003545C
0x18003544f  add     rcx, rcx; Size
0x180035452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035457  test    rax, rax
0x18003545a  jnz     short loc_180035461
0x18003545c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180035461  mov     [rbp+78h], rax
0x180035465  lea     rax, loc_18000BC87
0x18003546c  add     rsp, 20h
0x180035470  pop     rbp
0x180035471  retn
```
