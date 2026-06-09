# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x140014000`
- end: `0x140014059`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001530`
- `0x140014000`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001404b`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001404b`

## pseudocode

```c
void __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 && (v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0) )
    std::_Xbad_alloc();
  else
    *(_QWORD *)(a2 + 32) = v4;
}

```

## disassembly

```asm
0x140014000  mov     [rsp+arg_8], rdx
0x140014005  push    rbp
0x140014006  sub     rsp, 20h
0x14001400a  mov     rbp, rdx
0x14001400d  mov     rcx, [rbp+68h]
0x140014011  mov     [rbp+68h], rcx
0x140014015  xor     eax, eax
0x140014017  add     rcx, 1
0x14001401b  jnz     short loc_14001401F
0x14001401d  jmp     short loc_14001403B
0x14001401f  mov     rax, 7FFFFFFFFFFFFFFFh
0x140014029  cmp     rcx, rax
0x14001402c  ja      short loc_14001404B
0x14001402e  add     rcx, rcx; Size
0x140014031  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014036  test    rax, rax
0x140014039  jz      short loc_14001404B
0x14001403b  mov     [rbp+20h], rax
0x14001403f  mov     rax, 0
0x140014049  jmp     short loc_140014052
0x14001404b  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140014051  nop
0x140014052  add     rsp, 20h
0x140014056  pop     rbp
0x140014057  retn
```
