# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14001aa81`
- end: `0x14001aac9`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ba8`
- `0x14001aa81`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001aaae`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001aaae`

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
0x14001aa81  mov     [rsp+arg_8], rdx
0x14001aa86  push    rbp
0x14001aa87  sub     rsp, 20h
0x14001aa8b  mov     rbp, rdx
0x14001aa8e  mov     rcx, [rbp+58h]
0x14001aa92  mov     [rbp+58h], rcx
0x14001aa96  xor     eax, eax
0x14001aa98  add     rcx, 1; Size
0x14001aa9c  jz      short loc_14001AAB4
0x14001aa9e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001aaa2  ja      short loc_14001AAAE
0x14001aaa4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001aaa9  test    rax, rax
0x14001aaac  jnz     short loc_14001AAB4
0x14001aaae  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14001aab4  mov     [rbp+68h], rax
0x14001aab8  mov     rax, 0
0x14001aac2  add     rsp, 20h
0x14001aac6  pop     rbp
0x14001aac7  retn
```
