# _CPITRTaskHandler::Worker_::_1_::dtor$8

- ea: `0x180010cba`
- end: `0x180010cc6`
- name: `_CPITRTaskHandler::Worker_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000364c`

## pseudocode

```c
void __fastcall CPITRTaskHandler::Worker_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 296);
}

```

## disassembly

```asm
0x180010cba  lea     rcx, [rdx+128h]
0x180010cc1  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
