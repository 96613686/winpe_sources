# _RegistryConfig::ParseCommand_::_1_::dtor$7

- ea: `0x14000ac68`
- end: `0x14000ac74`
- name: `_RegistryConfig::ParseCommand_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007c34`

## pseudocode

```c
__int64 __fastcall RegistryConfig::ParseCommand_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x14000ac68  mov     rcx, [rdx+50h]
0x14000ac6f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
