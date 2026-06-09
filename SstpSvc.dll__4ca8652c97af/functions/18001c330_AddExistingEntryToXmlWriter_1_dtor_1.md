# _AddExistingEntryToXmlWriter_::_1_::dtor$1

- ea: `0x18001c330`
- end: `0x18001c33c`
- name: `_AddExistingEntryToXmlWriter_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000fb60`

## pseudocode

```c
__int64 __fastcall AddExistingEntryToXmlWriter_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 48);
}

```

## disassembly

```asm
0x18001c330  lea     rcx, [rdx+30h]
0x18001c337  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
