# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001fb66`
- end: `0x18001fbb4`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800015e0`
- `0x18001fb66`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001fb93`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001fb93`

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
0x18001fb66  mov     [rsp+arg_8], rdx
0x18001fb6b  push    rbp
0x18001fb6c  sub     rsp, 20h
0x18001fb70  mov     rbp, rdx
0x18001fb73  mov     rcx, [rbp+58h]
0x18001fb77  mov     [rbp+58h], rcx
0x18001fb7b  xor     eax, eax
0x18001fb7d  add     rcx, 1; Size
0x18001fb81  jz      short loc_18001FB9F
0x18001fb83  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fb87  ja      short loc_18001FB93
0x18001fb89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb8e  test    rax, rax
0x18001fb91  jnz     short loc_18001FB9F
0x18001fb93  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001fb9a  nop     dword ptr [rax+rax+00h]
0x18001fb9f  mov     [rbp+68h], rax
0x18001fba3  mov     rax, 0
0x18001fbad  add     rsp, 20h
0x18001fbb1  pop     rbp
0x18001fbb2  retn
```
