# _OneSettingsInternal::Common::trim_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor$0

- ea: `0x14001c212`
- end: `0x14001c238`
- name: `_OneSettingsInternal::Common::trim_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140013a2c`
- `0x14001c212`

## pseudocode

```c
__int64 __fastcall OneSettingsInternal::Common::trim_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring((char **)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x14001c212  push    rbp
0x14001c214  sub     rsp, 20h
0x14001c218  mov     rbp, rdx
0x14001c21b  mov     eax, [rbp+20h]
0x14001c21e  and     eax, 1
0x14001c221  test    eax, eax
0x14001c223  jz      short loc_14001C232
0x14001c225  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001c229  lea     rcx, [rbp+50h]
0x14001c22d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c232  add     rsp, 20h
0x14001c236  pop     rbp
0x14001c237  retn
```
