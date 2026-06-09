# _RegistryConfig::Parse_::_1_::dtor$3

- ea: `0x14000ad45`
- end: `0x14000ad51`
- name: `_RegistryConfig::Parse_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003560`

## pseudocode

```c
void __fastcall RegistryConfig::Parse_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::list<CommandSet>::~list<CommandSet>((_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x14000ad45  lea     rcx, [rdx+40h]; void *
0x14000ad4c  jmp     ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
```
