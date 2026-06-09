# std::_Construct_in_place<PCLmWriter::PCLmPageImageCalculator,std::shared_ptr<PCLmWriter::PDFDocumentWriter> &,std::shared_ptr<PCLmWriter::IPDFFactory> &>(PCLmWriter::PCLmPageImageCalculator &,std::shared_ptr<PCLmWriter::PDFDocumentWriter> &,std::shared_ptr<PCLmWriter::IPDFFactory> &)

- ea: `0x18000ec60`
- end: `0x18000ec97`
- name: `??$_Construct_in_place@VPCLmPageImageCalculator@PCLmWriter@@AEAV?$shared_ptr@VPDFDocumentWriter@PCLmWriter@@@std@@AEAV?$shared_ptr@VIPDFFactory@PCLmWriter@@@4@@std@@YAXAEAVPCLmPageImageCalculator@PCLmWriter@@AEAV?$shared_ptr@VPDFDocumentWriter@PCLmWriter@@@0@AEAV?$shared_ptr@VIPDFFactory@PCLmWriter@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f924`

## callees

- `0x18000e7c8`
- `0x180016cc8`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<PCLmWriter::PCLmPageImageCalculator,std::shared_ptr<PCLmWriter::PDFDocumentWriter> &,std::shared_ptr<PCLmWriter::IPDFFactory> &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r9
  _QWORD *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r10
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v8, a3);
  v4 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v9, v3);
  return PCLmWriter::PCLmPageImageCalculator::PCLmPageImageCalculator(v6, (__int64)v4, v5);
}

```

## disassembly

```asm
0x18000ec60  sub     rsp, 48h
0x18000ec64  mov     r9, rdx
0x18000ec67  mov     r10, rcx
0x18000ec6a  mov     rdx, r8
0x18000ec6d  lea     rcx, [rsp+48h+var_28]
0x18000ec72  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18000ec77  mov     rdx, r9
0x18000ec7a  lea     rcx, [rsp+48h+var_18]
0x18000ec7f  mov     r8, rax
0x18000ec82  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18000ec87  mov     rdx, rax
0x18000ec8a  mov     rcx, r10
0x18000ec8d  call    ??0PCLmPageImageCalculator@PCLmWriter@@QEAA@V?$shared_ptr@VPDFDocumentWriter@PCLmWriter@@@std@@V?$shared_ptr@VIPDFFactory@PCLmWriter@@@3@@Z; PCLmWriter::PCLmPageImageCalculator::PCLmPageImageCalculator(std::shared_ptr<PCLmWriter::PDFDocumentWriter>,std::shared_ptr<PCLmWriter::IPDFFactory>)
0x18000ec92  add     rsp, 48h
0x18000ec96  retn
```
