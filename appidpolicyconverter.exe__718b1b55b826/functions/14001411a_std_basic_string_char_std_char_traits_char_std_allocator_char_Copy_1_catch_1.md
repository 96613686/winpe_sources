# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14001411a`
- end: `0x140014167`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001530`
- `0x14001411a`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140014159`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140014159`

## pseudocode

```c
void __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
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
  if ( v5 && (v4 = operator new(v5)) == 0 )
    std::_Xbad_alloc();
  else
    *(_QWORD *)(a2 + 32) = v4;
}

```

## disassembly

```asm
0x14001411a  mov     [rsp+arg_8], rdx
0x14001411f  push    rbp
0x140014120  sub     rsp, 20h
0x140014124  mov     rbp, rdx
0x140014127  mov     rcx, [rbp+58h]
0x14001412b  mov     [rbp+58h], rcx
0x14001412f  xor     eax, eax
0x140014131  add     rcx, 1; Size
0x140014135  jnz     short loc_140014139
0x140014137  jmp     short loc_140014149
0x140014139  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001413d  ja      short loc_140014159
0x14001413f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014144  test    rax, rax
0x140014147  jz      short loc_140014159
0x140014149  mov     [rbp+20h], rax
0x14001414d  mov     rax, 0
0x140014157  jmp     short loc_140014160
0x140014159  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14001415f  nop
0x140014160  add     rsp, 20h
0x140014164  pop     rbp
0x140014165  retn
```
