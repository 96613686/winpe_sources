# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$1

- ea: `0x18000f097`
- end: `0x18000f0a5`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f09e`

## pseudocode

```c
void __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 88));
}

```

## disassembly

```asm
0x18000f097  mov     rcx, [rdx+58h]
0x18000f09e  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
