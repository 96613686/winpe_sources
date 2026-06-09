# _DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$0

- ea: `0x140019112`
- end: `0x14001911e`
- name: `_DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fa84`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 88);
}

```

## disassembly

```asm
0x140019112  lea     rcx, [rdx+58h]
0x140019119  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
