# _ConvertOnePlugin_::_1_::dtor$1

- ea: `0x140013d0d`
- end: `0x140013d19`
- name: `_ConvertOnePlugin_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140002774`

## pseudocode

```c
__int64 __fastcall ConvertOnePlugin_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x140013d0d  lea     rcx, [rdx+70h]
0x140013d14  jmp     ??1?$unique_ptr@U_APPID_POLICY@@U?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAA@XZ; std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>(void)
```
