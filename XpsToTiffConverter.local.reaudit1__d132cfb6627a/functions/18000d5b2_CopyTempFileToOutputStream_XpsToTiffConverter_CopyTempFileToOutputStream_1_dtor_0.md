# _CopyTempFileToOutputStream::XpsToTiffConverter::CopyTempFileToOutputStream_::_1_::dtor$0

- ea: `0x18000d5b2`
- end: `0x18000d5be`
- name: `_CopyTempFileToOutputStream::XpsToTiffConverter::CopyTempFileToOutputStream_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009d6c`

## pseudocode

```c
__int64 __fastcall CopyTempFileToOutputStream::XpsToTiffConverter::CopyTempFileToOutputStream_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 48);
}

```

## disassembly

```asm
0x18000d5b2  lea     rcx, [rdx+30h]
0x18000d5b9  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
