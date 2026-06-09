# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18001fbe5`
- end: `0x18001fc3f`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800015e0`
- `0x18001fbe5`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001fc1e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001fc1e`

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
0x18001fbe5  mov     [rsp+arg_8], rdx
0x18001fbea  push    rbp
0x18001fbeb  sub     rsp, 20h
0x18001fbef  mov     rbp, rdx
0x18001fbf2  mov     rcx, [rbp+58h]
0x18001fbf6  mov     [rbp+58h], rcx
0x18001fbfa  xor     eax, eax
0x18001fbfc  add     rcx, 1
0x18001fc00  jz      short loc_18001FC2A
0x18001fc02  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001fc0c  cmp     rcx, rax
0x18001fc0f  ja      short loc_18001FC1E
0x18001fc11  add     rcx, rcx; Size
0x18001fc14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fc19  test    rax, rax
0x18001fc1c  jnz     short loc_18001FC2A
0x18001fc1e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001fc25  nop     dword ptr [rax+rax+00h]
0x18001fc2a  mov     [rbp+68h], rax
0x18001fc2e  mov     rax, 0
0x18001fc38  add     rsp, 20h
0x18001fc3c  pop     rbp
0x18001fc3d  retn
```
