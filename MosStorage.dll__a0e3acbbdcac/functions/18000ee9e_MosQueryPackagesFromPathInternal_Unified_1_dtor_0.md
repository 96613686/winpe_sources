# _MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$0

- ea: `0x18000ee9e`
- end: `0x18000eeaa`
- name: `_MosQueryPackagesFromPathInternal_Unified_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ae20`

## pseudocode

```c
void __fastcall MosQueryPackagesFromPathInternal_Unified_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  FileReader::~FileReader((void **)(a2 + 104));
}

```

## disassembly

```asm
0x18000ee9e  lea     rcx, [rdx+68h]; this
0x18000eea5  jmp     ??1FileReader@@QEAA@XZ; FileReader::~FileReader(void)
```
