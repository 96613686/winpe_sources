# _MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$24

- ea: `0x18000eee6`
- end: `0x18000eef2`
- name: `_MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$24`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000adb8`

## pseudocode

```c
__int64 __fastcall MosQueryPackagesFromPathInternal_Unified_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  return std::string::~string(a2 + 136);
}

```

## disassembly

```asm
0x18000eee6  lea     rcx, [rdx+88h]
0x18000eeed  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
