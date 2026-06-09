# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$2

- ea: `0x18000f0ab`
- end: `0x18000f0b7`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004910`

## pseudocode

```c
void __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::unique_ptr<HrtfPersonalizationParams>::~unique_ptr<HrtfPersonalizationParams>((HrtfPersonalizationParams **)(a2 + 88));
}

```

## disassembly

```asm
0x18000f0ab  lea     rcx, [rdx+58h]
0x18000f0b2  jmp     ??1?$unique_ptr@UHrtfPersonalizationParams@@U?$default_delete@UHrtfPersonalizationParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<HrtfPersonalizationParams>::~unique_ptr<HrtfPersonalizationParams>(void)
```
