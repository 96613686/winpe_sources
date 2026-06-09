# _MapPlatformConfig::GetChinaVariant_::_1_::dtor$0

- ea: `0x18000f006`
- end: `0x18000f012`
- name: `_MapPlatformConfig::GetChinaVariant_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180006c44`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetChinaVariant_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 40));
}

```

## disassembly

```asm
0x18000f006  lea     rcx, [rdx+28h]
0x18000f00d  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
