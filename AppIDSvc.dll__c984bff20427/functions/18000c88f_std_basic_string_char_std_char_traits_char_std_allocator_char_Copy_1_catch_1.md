# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000c88f`
- end: `0x18000c8db`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011c8`
- `0x180001308`
- `0x18000c88f`

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
  *(_QWORD *)(a2 + 32) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000c88f  mov     [rsp+arg_8], rdx
0x18000c894  push    rbp
0x18000c895  sub     rsp, 20h
0x18000c899  mov     rbp, rdx
0x18000c89c  mov     rcx, [rbp+58h]
0x18000c8a0  mov     [rbp+58h], rcx
0x18000c8a4  xor     eax, eax
0x18000c8a6  add     rcx, 1; Size
0x18000c8aa  jnz     short loc_18000C8AE
0x18000c8ac  jmp     short loc_18000C8BE
0x18000c8ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c8b2  ja      short loc_18000C8CE
0x18000c8b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c8b9  test    rax, rax
0x18000c8bc  jz      short loc_18000C8CE
0x18000c8be  mov     [rbp+20h], rax
0x18000c8c2  mov     rax, 0
0x18000c8cc  jmp     short loc_18000C8D4
0x18000c8ce  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c8d4  add     rsp, 20h
0x18000c8d8  pop     rbp
0x18000c8d9  retn
```
