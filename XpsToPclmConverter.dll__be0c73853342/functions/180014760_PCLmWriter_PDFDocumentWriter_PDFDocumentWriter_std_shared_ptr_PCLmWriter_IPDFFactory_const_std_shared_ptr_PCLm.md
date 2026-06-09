# PCLmWriter::PDFDocumentWriter::PDFDocumentWriter(std::shared_ptr<PCLmWriter::IPDFFactory> const &,std::shared_ptr<PCLmWriter::IByteStream> const &)

- ea: `0x180014760`
- end: `0x18001483c`
- name: `??0PDFDocumentWriter@PCLmWriter@@QEAA@AEBV?$shared_ptr@VIPDFFactory@PCLmWriter@@@std@@AEBV?$shared_ptr@VIByteStream@PCLmWriter@@@3@@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ecc0`

## callees

- `0x180001f6c`
- `0x18000e7c8`
- `0x18000f448`
- `0x18001009c`
- `0x1800101cc`
- `0x1800138d8`
- `0x180014760`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PCLmWriter::PDFDocumentWriter::PDFDocumentWriter(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  std::_Ref_count_base *v5; // rcx
  _DWORD *v7; // [rsp+48h] [rbp+20h]

  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)a1, a2);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)(v3 + 16), v4);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 1;
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>((_QWORD *)(a1 + 96));
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>((_QWORD *)(a1 + 120));
  v7 = operator new(0x20u);
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<std::map<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>>>::`vftable';
  std::_Construct_in_place<std::map<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>>,>(v7 + 4);
  *(_QWORD *)(a1 + 56) = v7 + 4;
  v5 = *(std::_Ref_count_base **)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v7;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x180014760  mov     [rsp+arg_8], rbx
0x180014765  mov     [rsp+arg_10], rsi
0x18001476a  mov     [rsp+arg_0], rcx
0x18001476f  push    rdi
0x180014770  sub     rsp, 20h
0x180014774  mov     rsi, rcx
0x180014777  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18001477c  nop
0x18001477d  add     rcx, 10h
0x180014781  mov     rdx, r8
0x180014784  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180014789  nop
0x18001478a  lea     rcx, [rsi+28h]
0x18001478e  mov     qword ptr [rcx], 0
0x180014795  mov     qword ptr [rcx+8], 0
0x18001479d  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800147a2  nop
0x1800147a3  mov     qword ptr [rsi+38h], 0
0x1800147ab  mov     qword ptr [rsi+40h], 0
0x1800147b3  mov     ebx, 1
0x1800147b8  mov     [rsi+48h], rbx
0x1800147bc  mov     qword ptr [rsi+50h], 0
0x1800147c4  mov     dword ptr [rsi+58h], 0
0x1800147cb  lea     rcx, [rsi+60h]
0x1800147cf  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x1800147d4  nop
0x1800147d5  lea     rcx, [rsi+78h]
0x1800147d9  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x1800147de  nop
0x1800147df  lea     ecx, [rbx+1Fh]; Size
0x1800147e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800147e7  mov     rdi, rax
0x1800147ea  mov     [rsp+28h+arg_18], rax
0x1800147ef  xorps   xmm0, xmm0
0x1800147f2  movups  xmmword ptr [rax], xmm0
0x1800147f5  mov     [rax+8], ebx
0x1800147f8  mov     [rax+0Ch], ebx
0x1800147fb  lea     rax, ??_7?$_Ref_count_obj2@V?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>>>::`vftable'
0x180014802  mov     [rdi], rax
0x180014805  lea     rbx, [rdi+10h]
0x180014809  mov     rcx, rbx
0x18001480c  call    ??$_Construct_in_place@V?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@std@@$$V@std@@YAXAEAV?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@0@@Z; std::_Construct_in_place<std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>>,>(std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>> &)
0x180014811  nop
0x180014812  mov     [rsi+38h], rbx
0x180014816  mov     rcx, [rsi+40h]; this
0x18001481a  mov     [rsi+40h], rdi
0x18001481e  test    rcx, rcx
0x180014821  jz      short loc_180014829
0x180014823  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014828  nop
0x180014829  mov     rax, rsi
0x18001482c  mov     rbx, [rsp+28h+arg_8]
0x180014831  mov     rsi, [rsp+28h+arg_10]
0x180014836  add     rsp, 20h
0x18001483a  pop     rdi
0x18001483b  retn
```
