# _OneSettings::CreateQueryString_::_1_::dtor$4

- ea: `0x14001c31e`
- end: `0x14001c32a`
- name: `_OneSettings::CreateQueryString_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013a2c`

## pseudocode

```c
__int64 __fastcall OneSettings::CreateQueryString_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 176));
}

```

## disassembly

```asm
0x14001c31e  lea     rcx, [rdx+0B0h]
0x14001c325  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
