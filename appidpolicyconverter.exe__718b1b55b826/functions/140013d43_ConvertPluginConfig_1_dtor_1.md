# _ConvertPluginConfig_::_1_::dtor$1

- ea: `0x140013d43`
- end: `0x140013d4f`
- name: `_ConvertPluginConfig_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140002854`

## pseudocode

```c
__int64 __fastcall ConvertPluginConfig_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<APPID_EXECUTION_CATEGORY_>::~vector<APPID_EXECUTION_CATEGORY_>(a2 + 144);
}

```

## disassembly

```asm
0x140013d43  lea     rcx, [rdx+90h]
0x140013d4a  jmp     ??1?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@std@@QEAA@XZ; std::vector<APPID_EXECUTION_CATEGORY_>::~vector<APPID_EXECUTION_CATEGORY_>(void)
```
