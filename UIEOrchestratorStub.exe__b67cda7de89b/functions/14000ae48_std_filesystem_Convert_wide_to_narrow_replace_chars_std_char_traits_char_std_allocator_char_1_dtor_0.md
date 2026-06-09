# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x14000ae48`
- end: `0x14000ae6e`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000877c`
- `0x14000ae48`

## pseudocode

```c
void __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::string::~string(*(char ***)(a2 + 112));
  }
}

```

## disassembly

```asm
0x14000ae48  push    rbp
0x14000ae4a  sub     rsp, 20h
0x14000ae4e  mov     rbp, rdx
0x14000ae51  mov     eax, [rbp+30h]
0x14000ae54  and     eax, 1
0x14000ae57  test    eax, eax
0x14000ae59  jz      short loc_14000AE68
0x14000ae5b  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14000ae5f  mov     rcx, [rbp+70h]
0x14000ae63  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000ae68  add     rsp, 20h
0x14000ae6c  pop     rbp
0x14000ae6d  retn
```
