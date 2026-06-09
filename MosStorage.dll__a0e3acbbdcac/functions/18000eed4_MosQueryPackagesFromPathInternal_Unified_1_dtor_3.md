# _MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$3

- ea: `0x18000eed4`
- end: `0x18000eee0`
- name: `_MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000adb8`

## pseudocode

```c
__int64 __fastcall MosQueryPackagesFromPathInternal_Unified_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::string::~string(a2 + 168);
}

```

## disassembly

```asm
0x18000eed4  lea     rcx, [rdx+0A8h]
0x18000eedb  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
