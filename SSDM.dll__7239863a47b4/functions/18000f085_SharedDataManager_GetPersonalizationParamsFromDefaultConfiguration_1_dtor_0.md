# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$0

- ea: `0x18000f085`
- end: `0x18000f091`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004a04`

## pseudocode

```c
void __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::vector<unsigned char *>::~vector<unsigned char *>(a2 + 56);
}

```

## disassembly

```asm
0x18000f085  lea     rcx, [rdx+38h]
0x18000f08c  jmp     ??1?$vector@PEAEV?$allocator@PEAE@std@@@std@@QEAA@XZ; std::vector<uchar *>::~vector<uchar *>(void)
```
