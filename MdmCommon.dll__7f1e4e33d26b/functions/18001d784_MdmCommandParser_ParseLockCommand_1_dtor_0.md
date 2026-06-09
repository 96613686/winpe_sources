# _MdmCommandParser::ParseLockCommand_::_1_::dtor$0

- ea: `0x18001d784`
- end: `0x18001d790`
- name: `_MdmCommandParser::ParseLockCommand_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e50`

## pseudocode

```c
void __fastcall MdmCommandParser::ParseLockCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 88);
}

```

## disassembly

```asm
0x18001d784  lea     rcx, [rdx+58h]
0x18001d78b  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
