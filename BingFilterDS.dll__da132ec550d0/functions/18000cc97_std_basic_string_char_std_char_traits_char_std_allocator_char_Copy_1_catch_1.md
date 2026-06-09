# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000cc97`
- end: `0x18000ccde`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x18000cc97`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000cc97  mov     [rsp+arg_8], rdx
0x18000cc9c  push    rbp
0x18000cc9d  sub     rsp, 20h
0x18000cca1  mov     rbp, rdx
0x18000cca4  mov     rcx, [rbp+58h]
0x18000cca8  mov     [rbp+58h], rcx
0x18000ccac  xor     eax, eax
0x18000ccae  add     rcx, 1; Size
0x18000ccb2  jz      short loc_18000CCC9
0x18000ccb4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ccb8  ja      short loc_18000CCC4
0x18000ccba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ccbf  test    rax, rax
0x18000ccc2  jnz     short loc_18000CCC9
0x18000ccc4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ccc9  mov     [rbp+68h], rax
0x18000cccd  mov     rax, 0
0x18000ccd7  add     rsp, 20h
0x18000ccdb  pop     rbp
0x18000ccdc  retn
```
