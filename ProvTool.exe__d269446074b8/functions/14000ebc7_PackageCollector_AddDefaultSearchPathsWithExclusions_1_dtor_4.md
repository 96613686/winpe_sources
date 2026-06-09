# _PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$4

- ea: `0x14000ebc7`
- end: `0x14000ebd3`
- name: `_PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003938`

## pseudocode

```c
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 144);
}

```

## disassembly

```asm
0x14000ebc7  lea     rcx, [rdx+90h]
0x14000ebce  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
