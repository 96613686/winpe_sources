# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180019ccc`
- end: `0x180019d14`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800021a4`
- `0x180019ccc`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180019cf9`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180019cf9`

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
0x180019ccc  mov     [rsp+arg_8], rdx
0x180019cd1  push    rbp
0x180019cd2  sub     rsp, 20h
0x180019cd6  mov     rbp, rdx
0x180019cd9  mov     rcx, [rbp+58h]
0x180019cdd  mov     [rbp+58h], rcx
0x180019ce1  xor     eax, eax
0x180019ce3  add     rcx, 1; Size
0x180019ce7  jz      short loc_180019CFF
0x180019ce9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180019ced  ja      short loc_180019CF9
0x180019cef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019cf4  test    rax, rax
0x180019cf7  jnz     short loc_180019CFF
0x180019cf9  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019cff  mov     [rbp+68h], rax
0x180019d03  mov     rax, 0
0x180019d0d  add     rsp, 20h
0x180019d11  pop     rbp
0x180019d12  retn
```
