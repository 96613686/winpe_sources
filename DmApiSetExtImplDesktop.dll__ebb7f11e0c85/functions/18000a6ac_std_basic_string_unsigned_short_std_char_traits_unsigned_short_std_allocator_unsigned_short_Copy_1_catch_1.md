# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000a6ac`
- end: `0x18000a706`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001184`
- `0x18000a6ac`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a6e5`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a6e5`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000a6ac  mov     [rsp+arg_8], rdx
0x18000a6b1  push    rbp
0x18000a6b2  sub     rsp, 20h
0x18000a6b6  mov     rbp, rdx
0x18000a6b9  mov     rcx, [rbp+58h]
0x18000a6bd  mov     [rbp+58h], rcx
0x18000a6c1  xor     eax, eax
0x18000a6c3  add     rcx, 1
0x18000a6c7  jz      short loc_18000A6F1
0x18000a6c9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a6d3  cmp     rcx, rax
0x18000a6d6  ja      short loc_18000A6E5
0x18000a6d8  add     rcx, rcx; Size
0x18000a6db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6e0  test    rax, rax
0x18000a6e3  jnz     short loc_18000A6F1
0x18000a6e5  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a6ec  nop     dword ptr [rax+rax+00h]
0x18000a6f1  mov     [rbp+68h], rax
0x18000a6f5  mov     rax, 0
0x18000a6ff  add     rsp, 20h
0x18000a703  pop     rbp
0x18000a704  retn
```
