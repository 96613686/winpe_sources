# _MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor$2

- ea: `0x18000f04e`
- end: `0x18000f05a`
- name: `_MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180006c44`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 80));
}

```

## disassembly

```asm
0x18000f04e  lea     rcx, [rdx+50h]
0x18000f055  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
