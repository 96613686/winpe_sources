# PCLmWriter::PDFDocumentWriter::~PDFDocumentWriter(void)

- ea: `0x18000f808`
- end: `0x18000f890`
- name: `??1PDFDocumentWriter@PCLmWriter@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010280`

## callees

- `0x18000edc0`
- `0x18000efa8`
- `0x18000f808`
- `0x1800101cc`
- `0x1800106c8`

## pseudocode

```c
void __fastcall PCLmWriter::PDFDocumentWriter::~PDFDocumentWriter(PCLmWriter::PDFDocumentWriter *this)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  v2 = *((_QWORD *)this + 15);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 17) - v2) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
  }
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy((_QWORD *)this + 12);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    (_QWORD *)this + 5,
    (__int64)this + 40);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x18000f808  push    rbx
0x18000f80a  sub     rsp, 20h
0x18000f80e  mov     rbx, rcx
0x18000f811  mov     rcx, [rcx+78h]
0x18000f815  test    rcx, rcx
0x18000f818  jz      short loc_18000F84B
0x18000f81a  mov     rdx, [rbx+88h]
0x18000f821  sub     rdx, rcx
0x18000f824  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000f828  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f82d  mov     qword ptr [rbx+78h], 0
0x18000f835  mov     qword ptr [rbx+80h], 0
0x18000f840  mov     qword ptr [rbx+88h], 0
0x18000f84b  lea     rcx, [rbx+60h]
0x18000f84f  call    ?_Tidy@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(void)
0x18000f854  mov     rcx, [rbx+40h]; this
0x18000f858  test    rcx, rcx
0x18000f85b  jz      short loc_18000F862
0x18000f85d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f862  lea     rcx, [rbx+28h]
0x18000f866  mov     rdx, rcx
0x18000f869  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x18000f86e  mov     rcx, [rbx+18h]; this
0x18000f872  test    rcx, rcx
0x18000f875  jz      short loc_18000F87C
0x18000f877  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f87c  mov     rcx, [rbx+8]; this
0x18000f880  test    rcx, rcx
0x18000f883  jz      short loc_18000F88A
0x18000f885  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f88a  add     rsp, 20h
0x18000f88e  pop     rbx
0x18000f88f  retn
```
