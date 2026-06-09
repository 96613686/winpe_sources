# _AddExistingEntryToXmlWriter_::_1_::dtor$0

- ea: `0x18001c378`
- end: `0x18001c384`
- name: `_AddExistingEntryToXmlWriter_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000fb54`

## pseudocode

```c
__int64 __fastcall AddExistingEntryToXmlWriter_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::~set<std::wstring,_lessstr,std::allocator<std::wstring>>(*(_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x18001c378  mov     rcx, [rdx+50h]
0x18001c37f  jmp     ??1?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::~set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
```
