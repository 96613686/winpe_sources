# _MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$2

- ea: `0x18000eec2`
- end: `0x18000eece`
- name: `_MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ae20`

## pseudocode

```c
void __fastcall MosQueryPackagesFromPathInternal_Unified_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  FileReader::~FileReader((void **)(a2 + 88));
}

```

## disassembly

```asm
0x18000eec2  lea     rcx, [rdx+58h]; this
0x18000eec9  jmp     ??1FileReader@@QEAA@XZ; FileReader::~FileReader(void)
```
