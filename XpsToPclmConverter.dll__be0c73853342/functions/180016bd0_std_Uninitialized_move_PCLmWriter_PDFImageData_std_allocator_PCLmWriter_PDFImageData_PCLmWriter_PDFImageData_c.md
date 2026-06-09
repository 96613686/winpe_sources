# std::_Uninitialized_move<PCLmWriter::PDFImageData *,std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData *,std::allocator<PCLmWriter::PDFImageData> &)

- ea: `0x180016bd0`
- end: `0x180016c0d`
- name: `??$_Uninitialized_move@PEAUPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAPEAUPDFImageData@PCLmWriter@@QEAU12@0PEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016a6c`

## callees

- `0x18000edf4`
- `0x180016bd0`
- `0x180016c68`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<PCLmWriter::PDFImageData *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 i; // r9
  __int64 v6; // r8

  v4 = a1;
  for ( i = a2; v4 != i; v4 = v6 + 72 )
  {
    std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData>(
      a1,
      a3,
      v4,
      i);
    a3 += 72;
  }
  std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180016bd0  push    rbx
0x180016bd2  sub     rsp, 20h
0x180016bd6  mov     rbx, r8
0x180016bd9  mov     r8, rcx
0x180016bdc  mov     r9, rdx
0x180016bdf  cmp     rcx, rdx
0x180016be2  jz      short loc_180016BF9
0x180016be4  mov     rdx, rbx
0x180016be7  call    ??$construct@UPDFImageData@PCLmWriter@@U12@@?$_Default_allocator_traits@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@SAXAEAV?$allocator@UPDFImageData@PCLmWriter@@@1@QEAUPDFImageData@PCLmWriter@@$$QEAU34@@Z; std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData>(std::allocator<PCLmWriter::PDFImageData> &,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData &&)
0x180016bec  add     rbx, 48h ; 'H'
0x180016bf0  add     r8, 48h ; 'H'
0x180016bf4  cmp     r8, r9
0x180016bf7  jnz     short loc_180016BE4
0x180016bf9  mov     rdx, rbx
0x180016bfc  mov     rcx, rbx
0x180016bff  call    ??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)
0x180016c04  mov     rax, rbx
0x180016c07  add     rsp, 20h
0x180016c0b  pop     rbx
0x180016c0c  retn
```
