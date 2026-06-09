# _WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$2

- ea: `0x18000d651`
- end: `0x18000d65d`
- name: `_WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009d6c`

## pseudocode

```c
__int64 __fastcall WritePage::XpsToTiffConverter::WritePage_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 112);
}

```

## disassembly

```asm
0x18000d651  lea     rcx, [rdx+70h]
0x18000d658  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
