# std::vector<PCLmWriter::PDFImageData,std::allocator<PCLmWriter::PDFImageData>>::_Change_array(PCLmWriter::PDFImageData * const,unsigned __int64,unsigned __int64)

- ea: `0x180017620`
- end: `0x180017695`
- name: `?_Change_array@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEAAXQEAUPDFImageData@PCLmWriter@@_K1@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016a6c`

## callees

- `0x18000edc0`
- `0x18000edf4`
- `0x180017620`

## pseudocode

```c
__int64 __fastcall std::vector<PCLmWriter::PDFImageData>::_Change_array(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 result; // rax

  v6 = *a1;
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(v6, a1[1]);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
  }
  *a1 = a2;
  a1[1] = a2 + 72 * a3;
  result = 9 * a4;
  a1[2] = a2 + 72 * a4;
  return result;
}

```

## disassembly

```asm
0x180017620  push    rbx
0x180017622  push    rsi
0x180017623  push    rdi
0x180017624  push    r14
0x180017626  sub     rsp, 28h
0x18001762a  mov     rbx, rcx
0x18001762d  mov     rsi, r9
0x180017630  mov     rcx, [rcx]
0x180017633  mov     r14, r8
0x180017636  mov     rdi, rdx
0x180017639  test    rcx, rcx
0x18001763c  jz      short loc_180017670
0x18001763e  mov     rdx, [rbx+8]
0x180017642  call    ??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)
0x180017647  mov     rax, [rbx+10h]
0x18001764b  mov     rcx, 8E38E38E38E38E39h
0x180017655  sub     rax, [rbx]
0x180017658  sar     rax, 3
0x18001765c  imul    rax, rcx
0x180017660  mov     rcx, [rbx]
0x180017663  lea     rdx, [rax+rax*8]
0x180017667  shl     rdx, 3
0x18001766b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017670  lea     rax, [r14+r14*8]
0x180017674  mov     [rbx], rdi
0x180017677  lea     rcx, [rdi+rax*8]
0x18001767b  mov     [rbx+8], rcx
0x18001767f  lea     rax, [rsi+rsi*8]
0x180017683  lea     rcx, [rdi+rax*8]
0x180017687  mov     [rbx+10h], rcx
0x18001768b  add     rsp, 28h
0x18001768f  pop     r14
0x180017691  pop     rdi
0x180017692  pop     rsi
0x180017693  pop     rbx
0x180017694  retn
```
