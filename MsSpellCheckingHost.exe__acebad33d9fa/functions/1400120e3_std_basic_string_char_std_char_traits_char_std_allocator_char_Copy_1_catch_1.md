# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1400120e3`
- end: `0x14001212a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014fc`
- `0x140001758`
- `0x1400120e3`

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
0x1400120e3  mov     [rsp+arg_8], rdx
0x1400120e8  push    rbp
0x1400120e9  sub     rsp, 20h
0x1400120ed  mov     rbp, rdx
0x1400120f0  mov     rcx, [rbp+58h]
0x1400120f4  mov     [rbp+58h], rcx
0x1400120f8  xor     eax, eax
0x1400120fa  add     rcx, 1; Size
0x1400120fe  jz      short loc_140012115
0x140012100  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140012104  ja      short loc_140012110
0x140012106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001210b  test    rax, rax
0x14001210e  jnz     short loc_140012115
0x140012110  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140012115  mov     [rbp+68h], rax
0x140012119  mov     rax, 0
0x140012123  add     rsp, 20h
0x140012127  pop     rbp
0x140012128  retn
```
