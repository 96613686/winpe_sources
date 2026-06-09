# _DdcCommandHandlerDesktop::LockDevice_::_1_::dtor$0

- ea: `0x18000bd57`
- end: `0x18000bd63`
- name: `_DdcCommandHandlerDesktop::LockDevice_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027e4`

## pseudocode

```c
void __fastcall DdcCommandHandlerDesktop::LockDevice_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>((char **)(a2 + 72));
}

```

## disassembly

```asm
0x18000bd57  lea     rcx, [rdx+48h]
0x18000bd5e  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
