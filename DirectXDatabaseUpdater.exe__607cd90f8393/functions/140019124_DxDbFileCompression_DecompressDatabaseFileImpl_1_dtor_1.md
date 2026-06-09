# _DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$1

- ea: `0x140019124`
- end: `0x140019130`
- name: `_DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fa84`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 176);
}

```

## disassembly

```asm
0x140019124  lea     rcx, [rdx+0B0h]
0x14001912b  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
