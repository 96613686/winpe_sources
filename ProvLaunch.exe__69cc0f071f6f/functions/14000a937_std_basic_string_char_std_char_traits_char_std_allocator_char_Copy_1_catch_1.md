# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14000a937`
- end: `0x14000a97f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001864`
- `0x14000a937`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000a964`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000a964`

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
0x14000a937  mov     [rsp+arg_8], rdx
0x14000a93c  push    rbp
0x14000a93d  sub     rsp, 20h
0x14000a941  mov     rbp, rdx
0x14000a944  mov     rcx, [rbp+58h]
0x14000a948  mov     [rbp+58h], rcx
0x14000a94c  xor     eax, eax
0x14000a94e  add     rcx, 1; Size
0x14000a952  jz      short loc_14000A96A
0x14000a954  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a958  ja      short loc_14000A964
0x14000a95a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a95f  test    rax, rax
0x14000a962  jnz     short loc_14000A96A
0x14000a964  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000a96a  mov     [rbp+68h], rax
0x14000a96e  mov     rax, 0
0x14000a978  add     rsp, 20h
0x14000a97c  pop     rbp
0x14000a97d  retn
```
