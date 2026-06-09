# PCLmWriter::PCLmPageImageCalculator::~PCLmPageImageCalculator(void)

- ea: `0x18000f728`
- end: `0x18000f7ad`
- name: `??1PCLmPageImageCalculator@PCLmWriter@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(PCLmWriter::PCLmPageImageCalculator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010260`

## callees

- `0x18000df30`
- `0x18000edc0`
- `0x18000edf4`
- `0x18000f728`
- `0x1800101cc`

## pseudocode

```c
void __fastcall PCLmWriter::PCLmPageImageCalculator::~PCLmPageImageCalculator(
        PCLmWriter::PCLmPageImageCalculator *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 13);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 9);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease((__int64 *)this + 3);
  if ( *(_QWORD *)this )
  {
    std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(*(_QWORD *)this, *((_QWORD *)this + 1));
    std::_Deallocate<16>(*(_QWORD *)this, 8 * ((__int64)(*((_QWORD *)this + 2) - *(_QWORD *)this) >> 3));
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18000f728  push    rbx
0x18000f72a  sub     rsp, 20h
0x18000f72e  mov     rbx, rcx
0x18000f731  mov     rcx, [rcx+68h]; this
0x18000f735  test    rcx, rcx
0x18000f738  jz      short loc_18000F73F
0x18000f73a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f73f  mov     rcx, [rbx+48h]; this
0x18000f743  test    rcx, rcx
0x18000f746  jz      short loc_18000F74D
0x18000f748  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f74d  lea     rcx, [rbx+18h]
0x18000f751  call    ?InternalRelease@?$ComPtr@UIPCLmWriter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(void)
0x18000f756  mov     rcx, [rbx]
0x18000f759  test    rcx, rcx
0x18000f75c  jz      short loc_18000F7A7
0x18000f75e  mov     rdx, [rbx+8]
0x18000f762  call    ??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)
0x18000f767  mov     rax, [rbx+10h]
0x18000f76b  mov     rcx, 8E38E38E38E38E39h
0x18000f775  sub     rax, [rbx]
0x18000f778  sar     rax, 3
0x18000f77c  imul    rax, rcx
0x18000f780  mov     rcx, [rbx]
0x18000f783  lea     rdx, [rax+rax*8]
0x18000f787  shl     rdx, 3
0x18000f78b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f790  mov     qword ptr [rbx], 0
0x18000f797  mov     qword ptr [rbx+8], 0
0x18000f79f  mov     qword ptr [rbx+10h], 0
0x18000f7a7  add     rsp, 20h
0x18000f7ab  pop     rbx
0x18000f7ac  retn
```
