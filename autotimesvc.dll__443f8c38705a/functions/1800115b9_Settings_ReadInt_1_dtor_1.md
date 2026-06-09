# _Settings::ReadInt_::_1_::dtor$1

- ea: `0x1800115b9`
- end: `0x1800115c5`
- name: `_Settings::ReadInt_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000deec`

## pseudocode

```c
__int64 __fastcall Settings::ReadInt_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::optional<std::vector<std::wstring>>::~optional<std::vector<std::wstring>>(a2 + 64);
}

```

## disassembly

```asm
0x1800115b9  lea     rcx, [rdx+40h]
0x1800115c0  jmp     ??1?$optional@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAA@XZ; std::optional<std::vector<std::wstring>>::~optional<std::vector<std::wstring>>(void)
```
