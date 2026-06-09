# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1800116e7`
- end: `0x18001172f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800018f4`
- `0x1800116e7`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180011714`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180011714`

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
0x1800116e7  mov     [rsp+arg_8], rdx
0x1800116ec  push    rbp
0x1800116ed  sub     rsp, 20h
0x1800116f1  mov     rbp, rdx
0x1800116f4  mov     rcx, [rbp+58h]
0x1800116f8  mov     [rbp+58h], rcx
0x1800116fc  xor     eax, eax
0x1800116fe  add     rcx, 1; Size
0x180011702  jz      short loc_18001171A
0x180011704  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011708  ja      short loc_180011714
0x18001170a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001170f  test    rax, rax
0x180011712  jnz     short loc_18001171A
0x180011714  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001171a  mov     [rbp+68h], rax
0x18001171e  mov     rax, 0
0x180011728  add     rsp, 20h
0x18001172c  pop     rbp
0x18001172d  retn
```
