# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000a603`
- end: `0x18000a651`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001184`
- `0x18000a603`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a630`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a630`

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
0x18000a603  mov     [rsp+arg_8], rdx
0x18000a608  push    rbp
0x18000a609  sub     rsp, 20h
0x18000a60d  mov     rbp, rdx
0x18000a610  mov     rcx, [rbp+58h]
0x18000a614  mov     [rbp+58h], rcx
0x18000a618  xor     eax, eax
0x18000a61a  add     rcx, 1; Size
0x18000a61e  jz      short loc_18000A63C
0x18000a620  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a624  ja      short loc_18000A630
0x18000a626  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a62b  test    rax, rax
0x18000a62e  jnz     short loc_18000A63C
0x18000a630  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a637  nop     dword ptr [rax+rax+00h]
0x18000a63c  mov     [rbp+68h], rax
0x18000a640  mov     rax, 0
0x18000a64a  add     rsp, 20h
0x18000a64e  pop     rbp
0x18000a64f  retn
```
