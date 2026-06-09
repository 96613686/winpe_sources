# _DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$2

- ea: `0x140019136`
- end: `0x140019142`
- name: `_DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fa84`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 152);
}

```

## disassembly

```asm
0x140019136  lea     rcx, [rdx+98h]
0x14001913d  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
