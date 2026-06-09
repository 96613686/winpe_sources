# std::vector<PCLmWriter::PDFImageData,std::allocator<PCLmWriter::PDFImageData>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180016d64`
- end: `0x180016d9c`
- name: `??1_Reallocation_guard@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@QEAA@XZ`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016a6c`
- `0x18001db83`

## callees

- `0x18000edc0`
- `0x18000edf4`
- `0x180016d64`

## pseudocode

```c
__int64 __fastcall std::vector<PCLmWriter::PDFImageData>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  __int64 result; // rax

  if ( a1[1] )
  {
    std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(a1[3], a1[4]);
    return std::_Deallocate<16>(a1[1], 72LL * a1[2]);
  }
  return result;
}

```

## disassembly

```asm
0x180016d64  push    rbx
0x180016d66  sub     rsp, 20h
0x180016d6a  cmp     qword ptr [rcx+8], 0
0x180016d6f  mov     rbx, rcx
0x180016d72  jz      short loc_180016D96
0x180016d74  mov     rdx, [rcx+20h]
0x180016d78  mov     rcx, [rcx+18h]
0x180016d7c  call    ??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)
0x180016d81  mov     rax, [rbx+10h]
0x180016d85  mov     rcx, [rbx+8]
0x180016d89  lea     rdx, [rax+rax*8]
0x180016d8d  shl     rdx, 3
0x180016d91  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016d96  add     rsp, 20h
0x180016d9a  pop     rbx
0x180016d9b  retn
```
