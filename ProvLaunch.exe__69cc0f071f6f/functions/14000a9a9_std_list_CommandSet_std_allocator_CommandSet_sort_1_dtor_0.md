# _std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$0

- ea: `0x14000a9a9`
- end: `0x14000a9b5`
- name: `_std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003560`

## pseudocode

```c
void __fastcall std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::list<CommandSet>::~list<CommandSet>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x14000a9a9  lea     rcx, [rdx+30h]; void *
0x14000a9b0  jmp     ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
```
