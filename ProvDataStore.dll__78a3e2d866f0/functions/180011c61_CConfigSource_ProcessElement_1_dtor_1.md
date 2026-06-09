# _CConfigSource::ProcessElement_::_1_::dtor$1

- ea: `0x180011c61`
- end: `0x180011c6d`
- name: `_CConfigSource::ProcessElement_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cbb4`

## pseudocode

```c
__int64 __fastcall CConfigSource::ProcessElement_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 216);
}

```

## disassembly

```asm
0x180011c61  lea     rcx, [rdx+0D8h]
0x180011c68  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
