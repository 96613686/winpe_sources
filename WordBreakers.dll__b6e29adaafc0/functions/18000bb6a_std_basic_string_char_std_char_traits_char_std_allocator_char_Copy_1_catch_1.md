# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000bb6a`
- end: `0x18000bbb1`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001e88`
- `0x180002038`
- `0x18000bb6a`

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
0x18000bb6a  mov     [rsp+arg_8], rdx
0x18000bb6f  push    rbp
0x18000bb70  sub     rsp, 20h
0x18000bb74  mov     rbp, rdx
0x18000bb77  mov     rcx, [rbp+58h]
0x18000bb7b  mov     [rbp+58h], rcx
0x18000bb7f  xor     eax, eax
0x18000bb81  add     rcx, 1; Size
0x18000bb85  jz      short loc_18000BB9C
0x18000bb87  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bb8b  ja      short loc_18000BB97
0x18000bb8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb92  test    rax, rax
0x18000bb95  jnz     short loc_18000BB9C
0x18000bb97  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000bb9c  mov     [rbp+68h], rax
0x18000bba0  mov     rax, 0
0x18000bbaa  add     rsp, 20h
0x18000bbae  pop     rbp
0x18000bbaf  retn
```
