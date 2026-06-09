# PCLmWriter::PCLmWriter::_HandlePCLmPage(IPageBitmapProvider *,float,float,char const *)

- ea: `0x180010290`
- end: `0x18001045c`
- name: `?_HandlePCLmPage@PCLmWriter@1@AEAAXPEAUIPageBitmapProvider@@MMPEBD@Z`
- size: `460`
- prototype: `void(PCLmWriter::PCLmWriter *__hidden this, struct IPageBitmapProvider *, float, float, const char *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18000e964`

## callees

- `0x1800015f0`
- `0x18000e7c8`
- `0x18000e87c`
- `0x18000ee6c`
- `0x18000ee94`
- `0x18000efa8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f448`
- `0x18000fe14`
- `0x1800101cc`
- `0x180010290`
- `0x180010618`
- `0x1800106c8`
- `0x180010718`
- `0x180014a14`
- `0x1800159d0`
- `0x180016da4`
- `0x180017350`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PCLmWriter::PCLmWriter::_HandlePCLmPage(
        PCLmWriter::PCLmWriter *this,
        struct IPageBitmapProvider *a2,
        float a3,
        float a4,
        const char *a5)
{
  __int64 v6; // r14
  _QWORD *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned __int64 i; // rbx
  __int64 v11; // [rsp+38h] [rbp-51h] BYREF
  std::_Ref_count_base *v12; // [rsp+40h] [rbp-49h]
  _BYTE v13[8]; // [rsp+48h] [rbp-41h] BYREF
  std::_Ref_count_base *v14; // [rsp+50h] [rbp-39h]
  _BYTE v15[16]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v16; // [rsp+68h] [rbp-21h] BYREF
  __int64 v17; // [rsp+78h] [rbp-11h]

  PCLmWriter::PCLmPageImageCalculator::ReInitialize(
    *((PCLmWriter::PCLmPageImageCalculator **)this + 4),
    *((_DWORD *)this + 20),
    a2);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v15);
  v6 = *((_QWORD *)this + 4);
  v16 = *(_OWORD *)(v6 + 32);
  v17 = *(_QWORD *)(v6 + 48);
  PCLmWriter::PCLmWriter::PopulatePageObjects(this, v6, &v16, v15);
  v7 = (_QWORD *)*((_QWORD *)this + 2);
  std::string::string(&v16, a5);
  v8 = *((_QWORD *)this + 6);
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(
    &v11,
    v15);
  PCLmWriter::PDFDocumentWriter::AddNewPage(v7, a3, a4, (__int64)&v11, v8, (__int64)&v16);
  std::string::_Tidy_deallocate(&v16);
  v9 = *((_QWORD *)this + 6);
  *(_QWORD *)(v9 + 16) = 0;
  *(_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v9) = 0;
  for ( i = 0; i < 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(v6 + 8) - *(_QWORD *)v6) >> 3); ++i )
  {
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(&v16);
    PCLmWriter::PCLmPageImageCalculator::GetNextImage(*((__int64 **)this + 4), &v11);
    std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v13, &v11);
    if ( *((_QWORD *)&v16 + 1) == v17 )
      std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
        &v16,
        *((_QWORD *)&v16 + 1),
        v13);
    else
      std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
        &v16,
        v13);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    PCLmWriter::PDFDocumentWriter::WritePDFObjects(*((_QWORD *)this + 2), &v16);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(&v16);
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v15,
    v15);
}

```

## disassembly

```asm
0x180010290  mov     rax, rsp
0x180010293  push    rbp
0x180010294  push    rbx
0x180010295  push    rsi
0x180010296  push    rdi
0x180010297  push    r14
0x180010299  lea     rbp, [rax-57h]
0x18001029d  sub     rsp, 0B0h
0x1800102a4  movaps  xmmword ptr [rax-38h], xmm6
0x1800102a8  movaps  xmmword ptr [rax-48h], xmm7
0x1800102ac  mov     rax, cs:__security_cookie
0x1800102b3  xor     rax, rsp
0x1800102b6  mov     [rbp+4Fh+var_50], rax
0x1800102ba  movaps  xmm7, xmm3
0x1800102bd  movaps  xmm6, xmm2
0x1800102c0  mov     rsi, rcx
0x1800102c3  mov     rbx, [rbp+4Fh+arg_20]
0x1800102c7  mov     r8, rdx; struct IPageBitmapProvider *
0x1800102ca  mov     edx, [rcx+50h]; unsigned int
0x1800102cd  mov     rcx, [rcx+20h]; this
0x1800102d1  call    ?ReInitialize@PCLmPageImageCalculator@PCLmWriter@@QEAAXIPEAUIPageBitmapProvider@@@Z; PCLmWriter::PCLmPageImageCalculator::ReInitialize(uint,IPageBitmapProvider *)
0x1800102d6  lea     rcx, [rbp+4Fh+var_80]
0x1800102da  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x1800102df  nop
0x1800102e0  mov     r14, [rsi+20h]
0x1800102e4  movups  xmm0, xmmword ptr [r14+20h]
0x1800102e9  movups  [rbp+4Fh+var_70], xmm0
0x1800102ed  movsd   xmm1, qword ptr [r14+30h]
0x1800102f3  movsd   [rbp+4Fh+var_60], xmm1
0x1800102f8  lea     r9, [rbp+4Fh+var_80]
0x1800102fc  lea     r8, [rbp+4Fh+var_70]
0x180010300  mov     rdx, r14
0x180010303  mov     rcx, rsi
0x180010306  call    ?PopulatePageObjects@PCLmWriter@1@AEAAXAEBV?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEBUPDF_MATRIX@1@AEAV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@3@@Z; PCLmWriter::PCLmWriter::PopulatePageObjects(std::vector<PCLmWriter::PDFImageData> const &,PCLmWriter::PDF_MATRIX const &,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> &)
0x18001030b  mov     rdi, [rsi+10h]
0x18001030f  mov     rdx, rbx
0x180010312  lea     rcx, [rbp+4Fh+var_70]
0x180010316  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001031b  nop
0x18001031c  mov     rbx, [rsi+30h]
0x180010320  lea     rdx, [rbp+4Fh+var_80]
0x180010324  lea     rcx, [rbp+4Fh+var_A0]
0x180010328  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &&)
0x18001032d  lea     rax, [rbp+4Fh+var_70]
0x180010331  mov     [rsp+0D0h+var_A8], rax
0x180010336  mov     [rsp+0D0h+var_B0], rbx
0x18001033b  lea     r9, [rbp+4Fh+var_A0]
0x18001033f  movaps  xmm2, xmm7
0x180010342  movaps  xmm1, xmm6
0x180010345  mov     rcx, rdi
0x180010348  call    ?AddNewPage@PDFDocumentWriter@PCLmWriter@@QEAAXMMV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1@Z; PCLmWriter::PDFDocumentWriter::AddNewPage(float,float,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,std::string const &,std::string const &)
0x18001034d  nop
0x18001034e  lea     rcx, [rbp+4Fh+var_70]
0x180010352  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010357  mov     rcx, [rsi+30h]
0x18001035b  mov     qword ptr [rcx+10h], 0
0x180010363  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180010368  mov     byte ptr [rax], 0
0x18001036b  xor     ebx, ebx
0x18001036d  mov     rax, [r14+8]
0x180010371  sub     rax, [r14]
0x180010374  sar     rax, 3
0x180010378  mov     rdi, 8E38E38E38E38E39h
0x180010382  imul    rax, rdi
0x180010386  test    rax, rax
0x180010389  jz      loc_180010427
0x18001038f  lea     rcx, [rbp+4Fh+var_70]
0x180010393  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180010398  nop
0x180010399  lea     rdx, [rbp+4Fh+var_A0]
0x18001039d  mov     rcx, [rsi+20h]
0x1800103a1  call    ?GetNextImage@PCLmPageImageCalculator@PCLmWriter@@QEAA?AV?$shared_ptr@$$CBVIStreamObject@PCLmWriter@@@std@@XZ; PCLmWriter::PCLmPageImageCalculator::GetNextImage(void)
0x1800103a6  nop
0x1800103a7  lea     rdx, [rbp+4Fh+var_A0]
0x1800103ab  lea     rcx, [rbp+4Fh+var_90]
0x1800103af  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800103b4  nop
0x1800103b5  mov     rdx, qword ptr [rbp+4Fh+var_70+8]
0x1800103b9  lea     rcx, [rbp+4Fh+var_70]
0x1800103bd  cmp     rdx, [rbp+4Fh+var_60]
0x1800103c1  jz      short loc_1800103CE
0x1800103c3  lea     rdx, [rbp+4Fh+var_90]
0x1800103c7  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> &&)
0x1800103cc  jmp     short loc_1800103D8
0x1800103ce  lea     r8, [rbp+4Fh+var_90]
0x1800103d2  call    ??$_Emplace_reallocate@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> &&)
0x1800103d7  nop
0x1800103d8  mov     rcx, [rbp+4Fh+var_88]; this
0x1800103dc  test    rcx, rcx
0x1800103df  jz      short loc_1800103E6
0x1800103e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103e6  lea     rdx, [rbp+4Fh+var_70]
0x1800103ea  mov     rcx, [rsi+10h]
0x1800103ee  call    ?WritePDFObjects@PDFDocumentWriter@PCLmWriter@@QEAAXAEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@@Z; PCLmWriter::PDFDocumentWriter::WritePDFObjects(std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &)
0x1800103f3  nop
0x1800103f4  mov     rcx, [rbp+4Fh+var_98]; this
0x1800103f8  test    rcx, rcx
0x1800103fb  jz      short loc_180010403
0x1800103fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010402  nop
0x180010403  lea     rcx, [rbp+4Fh+var_70]
0x180010407  call    ?_Tidy@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(void)
0x18001040c  inc     rbx
0x18001040f  mov     rax, [r14+8]
0x180010413  sub     rax, [r14]
0x180010416  sar     rax, 3
0x18001041a  imul    rax, rdi
0x18001041e  cmp     rbx, rax
0x180010421  jb      loc_18001038F
0x180010427  lea     rdx, [rbp+4Fh+var_80]
0x18001042b  lea     rcx, [rbp+4Fh+var_80]
0x18001042f  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x180010434  mov     rcx, [rbp+4Fh+var_50]
0x180010438  xor     rcx, rsp; StackCookie
0x18001043b  call    __security_check_cookie
0x180010440  lea     r11, [rsp+0D0h+var_20]
0x180010448  movaps  xmm6, xmmword ptr [r11-10h]
0x18001044d  movaps  xmm7, xmmword ptr [r11-20h]
0x180010452  mov     rsp, r11
0x180010455  pop     r14
0x180010457  pop     rdi
0x180010458  pop     rsi
0x180010459  pop     rbx
0x18001045a  pop     rbp
0x18001045b  retn
```
