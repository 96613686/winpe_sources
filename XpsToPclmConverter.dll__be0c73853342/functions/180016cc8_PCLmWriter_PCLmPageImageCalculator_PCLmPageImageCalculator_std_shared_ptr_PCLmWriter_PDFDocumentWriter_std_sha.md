# PCLmWriter::PCLmPageImageCalculator::PCLmPageImageCalculator(std::shared_ptr<PCLmWriter::PDFDocumentWriter>,std::shared_ptr<PCLmWriter::IPDFFactory>)

- ea: `0x180016cc8`
- end: `0x180016d5c`
- name: `??0PCLmPageImageCalculator@PCLmWriter@@QEAA@V?$shared_ptr@VPDFDocumentWriter@PCLmWriter@@@std@@V?$shared_ptr@VIPDFFactory@PCLmWriter@@@3@@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ec60`

## callees

- `0x18000e7c8`
- `0x18000f448`
- `0x1800101cc`
- `0x180016cc8`

## pseudocode

```c
__int64 __fastcall PCLmWriter::PCLmPageImageCalculator::PCLmPageImageCalculator(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  _QWORD *v7; // r8
  __int64 v8; // r9
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx

  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>((_QWORD *)a1);
  *(_QWORD *)(v5 + 24) = 0;
  *(_QWORD *)(v5 + 32) = 1065353216;
  *(_DWORD *)(v5 + 40) = 0;
  *(_QWORD *)(v5 + 44) = 1065353216;
  *(_QWORD *)(v5 + 52) = 0;
  *(_DWORD *)(v5 + 60) = 0;
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)(v5 + 64), v6);
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)(a1 + 96), v7);
  v9 = *(std::_Ref_count_base **)(v8 + 8);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return a1;
}

```

## disassembly

```asm
0x180016cc8  mov     [rsp+arg_0], rbx
0x180016ccd  push    rdi
0x180016cce  sub     rsp, 20h
0x180016cd2  mov     rdi, r8
0x180016cd5  mov     r9, rdx
0x180016cd8  mov     rbx, rcx
0x180016cdb  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180016ce0  mov     qword ptr [rcx+18h], 0
0x180016ce8  mov     qword ptr [rcx+20h], 3F800000h
0x180016cf0  mov     dword ptr [rcx+28h], 0
0x180016cf7  mov     qword ptr [rcx+2Ch], 3F800000h
0x180016cff  mov     qword ptr [rcx+34h], 0
0x180016d07  mov     dword ptr [rcx+3Ch], 0
0x180016d0e  add     rcx, 40h ; '@'
0x180016d12  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180016d17  lea     rcx, [rbx+60h]
0x180016d1b  mov     qword ptr [rbx+50h], 0
0x180016d23  mov     rdx, r8
0x180016d26  mov     dword ptr [rbx+58h], 0
0x180016d2d  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180016d32  mov     rcx, [r9+8]; this
0x180016d36  test    rcx, rcx
0x180016d39  jz      short loc_180016D40
0x180016d3b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d40  mov     rcx, [rdi+8]; this
0x180016d44  test    rcx, rcx
0x180016d47  jz      short loc_180016D4E
0x180016d49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d4e  mov     rax, rbx
0x180016d51  mov     rbx, [rsp+28h+arg_0]
0x180016d56  add     rsp, 20h
0x180016d5a  pop     rdi
0x180016d5b  retn
```
