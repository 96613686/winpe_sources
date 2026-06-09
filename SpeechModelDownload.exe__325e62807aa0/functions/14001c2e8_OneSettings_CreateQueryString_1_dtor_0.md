# _OneSettings::CreateQueryString_::_1_::dtor$0

- ea: `0x14001c2e8`
- end: `0x14001c2f4`
- name: `_OneSettings::CreateQueryString_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400154d4`

## pseudocode

```c
__int64 __fastcall OneSettings::CreateQueryString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(a2 + 176);
}

```

## disassembly

```asm
0x14001c2e8  lea     rcx, [rdx+0B0h]
0x14001c2ef  jmp     ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
```
