# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x18000c256`
- end: `0x18000c27c`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008eb8`
- `0x18000c256`

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
0x18000c256  push    rbp
0x18000c258  sub     rsp, 20h
0x18000c25c  mov     rbp, rdx
0x18000c25f  mov     eax, [rbp+30h]
0x18000c262  and     eax, 1
0x18000c265  test    eax, eax
0x18000c267  jz      short loc_18000C276
0x18000c269  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000c26d  mov     rcx, [rbp+70h]
0x18000c271  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000c276  add     rsp, 20h
0x18000c27a  pop     rbp
0x18000c27b  retn
```
