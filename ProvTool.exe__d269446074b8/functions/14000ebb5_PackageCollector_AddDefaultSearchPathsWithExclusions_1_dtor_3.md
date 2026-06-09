# _PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$3

- ea: `0x14000ebb5`
- end: `0x14000ebc1`
- name: `_PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000ac50`

## pseudocode

```c
void __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  expanded_wstring::~expanded_wstring((expanded_wstring *)(a2 + 128));
}

```

## disassembly

```asm
0x14000ebb5  lea     rcx, [rdx+80h]; this
0x14000ebbc  jmp     ??1expanded_wstring@@QEAA@XZ; expanded_wstring::~expanded_wstring(void)
```
