# _ConvertPluginConfig_::_1_::dtor$3

- ea: `0x140013d67`
- end: `0x140013d73`
- name: `_ConvertPluginConfig_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140002894`

## pseudocode

```c
void __fastcall ConvertPluginConfig_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::~vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>((std::_Container_base0 *)(a2 + 96));
}

```

## disassembly

```asm
0x140013d67  lea     rcx, [rdx+60h]
0x140013d6e  jmp     ??1?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::~vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>(void)
```
