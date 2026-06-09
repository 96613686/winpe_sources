# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000ab00`
- end: `0x18000ab44`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001730`
- `0x180001908`
- `0x180001a68`
- `0x18000ab00`

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
  return &loc_180001991;
}

```

## disassembly

```asm
0x18000ab00  mov     [rsp+arg_8], rdx
0x18000ab05  push    rbp
0x18000ab06  sub     rsp, 20h
0x18000ab0a  mov     rbp, rdx
0x18000ab0d  mov     rcx, [rbp+68h]
0x18000ab11  mov     [rbp+68h], rcx
0x18000ab15  xor     eax, eax
0x18000ab17  add     rcx, 1; Size
0x18000ab1b  jz      short loc_18000AB32
0x18000ab1d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ab21  ja      short loc_18000AB2D
0x18000ab23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab28  test    rax, rax
0x18000ab2b  jnz     short loc_18000AB32
0x18000ab2d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ab32  mov     [rbp+78h], rax
0x18000ab36  lea     rax, loc_180001991
0x18000ab3d  add     rsp, 20h
0x18000ab41  pop     rbp
0x18000ab42  retn
```
