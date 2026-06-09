# PCLmWriter::PCLmWriter::PopulatePageObjects(std::vector<PCLmWriter::PDFImageData,std::allocator<PCLmWriter::PDFImageData>> const &,PCLmWriter::PDF_MATRIX const &,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> &)

- ea: `0x18000fe14`
- end: `0x18000ff42`
- name: `?PopulatePageObjects@PCLmWriter@1@AEAAXAEBV?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEBUPDF_MATRIX@1@AEAV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@3@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180010290`

## callees

- `0x18000f1b8`
- `0x18000f398`
- `0x18000f8d4`
- `0x18000fe14`
- `0x1800101cc`
- `0x180017c6c`
- `0x18001806c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall PCLmWriter::PCLmWriter::PopulatePageObjects(
        __int64 a1,
        __int64 *a2,
        const struct PCLmWriter::PDF_MATRIX *a3,
        __int64 *a4)
{
  __int64 v7; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 i; // rsi
  _QWORD *v10; // rax
  std::_Ref_count_base *v11; // rbp
  _QWORD *v12; // rax
  PCLmWriter::PDFContentBuilder *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-88h] BYREF
  std::_Ref_count_base *v18; // [rsp+48h] [rbp-80h]
  _BYTE v19[16]; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v20[104]; // [rsp+60h] [rbp-68h] BYREF

  PCLmWriter::PDFContentBuilder::SetTransformFirstEntry(*(PCLmWriter::PDFContentBuilder **)(a1 + 48), a3);
  v7 = *a2;
  result = 0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3);
  if ( result )
  {
    for ( i = 0; i < result; ++i )
    {
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 56LL))(
                        *(_QWORD *)(a1 + 64),
                        v17,
                        *(unsigned int *)(v7 + 72 * i + 32),
                        *(unsigned int *)(v7 + 72 * i + 36));
      v16[0] = *v10;
      v11 = (std::_Ref_count_base *)v10[1];
      v16[1] = v11;
      *v10 = 0;
      v10[1] = 0;
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      v12 = (_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
                        a4,
                        (__int64)v19,
                        *a2 + 72 * i);
      std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(*v12 + 64LL, v16);
      v13 = *(PCLmWriter::PDFContentBuilder **)(a1 + 48);
      v14 = *a2 + 72 * i;
      v15 = std::string::string(v20);
      PCLmWriter::PDFContentBuilder::DrawImage(v13, v15, (const struct PCLmWriter::PDF_MATRIX *)(v14 + 40));
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
      v7 = *a2;
      result = 0x8E38E38E38E38E39uLL * ((a2[1] - *a2) >> 3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe14  push    rbx
0x18000fe16  push    rbp
0x18000fe17  push    rsi
0x18000fe18  push    rdi
0x18000fe19  push    r12
0x18000fe1b  push    r13
0x18000fe1d  push    r14
0x18000fe1f  push    r15
0x18000fe21  sub     rsp, 88h
0x18000fe28  mov     r12, r9
0x18000fe2b  mov     r14, rdx
0x18000fe2e  mov     r15, rcx
0x18000fe31  mov     rdx, r8; struct PCLmWriter::PDF_MATRIX *
0x18000fe34  mov     rcx, [rcx+30h]; this
0x18000fe38  call    ?SetTransformFirstEntry@PDFContentBuilder@PCLmWriter@@QEAAXAEBUPDF_MATRIX@2@@Z; PCLmWriter::PDFContentBuilder::SetTransformFirstEntry(PCLmWriter::PDF_MATRIX const &)
0x18000fe3d  mov     rdx, [r14]
0x18000fe40  mov     rax, [r14+8]
0x18000fe44  sub     rax, rdx
0x18000fe47  sar     rax, 3
0x18000fe4b  mov     r13, 8E38E38E38E38E39h
0x18000fe55  imul    rax, r13
0x18000fe59  test    rax, rax
0x18000fe5c  jz      loc_18000FF2E
0x18000fe62  xor     esi, esi
0x18000fe64  mov     rcx, [r15+40h]
0x18000fe68  lea     rbx, [rsi+rsi*8]
0x18000fe6c  mov     rax, [rcx]
0x18000fe6f  mov     r9d, [rdx+rbx*8+24h]
0x18000fe74  mov     r8d, [rdx+rbx*8+20h]
0x18000fe79  lea     rdx, [rsp+0C8h+var_88]
0x18000fe7e  mov     rax, [rax+38h]
0x18000fe82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe87  mov     rcx, [rax]
0x18000fe8a  mov     [rsp+0C8h+var_98], rcx
0x18000fe8f  mov     rbp, [rax+8]
0x18000fe93  mov     [rsp+0C8h+var_90], rbp
0x18000fe98  mov     qword ptr [rax], 0
0x18000fe9f  mov     qword ptr [rax+8], 0
0x18000fea7  mov     rcx, [rsp+0C8h+var_80]; this
0x18000feac  test    rcx, rcx
0x18000feaf  jz      short loc_18000FEB6
0x18000feb1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000feb6  mov     rax, [r14]
0x18000feb9  lea     r8, [rax+rbx*8]
0x18000febd  lea     rdx, [rsp+0C8h+var_78]
0x18000fec2  mov     rcx, r12
0x18000fec5  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(std::string const &)
0x18000feca  mov     rcx, [rax]
0x18000fecd  add     rcx, 40h ; '@'
0x18000fed1  lea     rdx, [rsp+0C8h+var_98]
0x18000fed6  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x18000fedb  mov     rdi, [r15+30h]
0x18000fedf  mov     rax, [r14]
0x18000fee2  lea     rbx, [rax+rbx*8]
0x18000fee6  mov     rdx, rbx
0x18000fee9  lea     rcx, [rsp+0C8h+var_68]
0x18000feee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18000fef3  lea     r8, [rbx+28h]
0x18000fef7  mov     rdx, rax
0x18000fefa  mov     rcx, rdi; this
0x18000fefd  call    ?DrawImage@PDFContentBuilder@PCLmWriter@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUPDF_MATRIX@2@@Z; PCLmWriter::PDFContentBuilder::DrawImage(std::string,PCLmWriter::PDF_MATRIX const &)
0x18000ff02  nop
0x18000ff03  test    rbp, rbp
0x18000ff06  jz      short loc_18000FF10
0x18000ff08  mov     rcx, rbp; this
0x18000ff0b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ff10  inc     rsi
0x18000ff13  mov     rdx, [r14]
0x18000ff16  mov     rax, [r14+8]
0x18000ff1a  sub     rax, rdx
0x18000ff1d  sar     rax, 3
0x18000ff21  imul    rax, r13
0x18000ff25  cmp     rsi, rax
0x18000ff28  jb      loc_18000FE64
0x18000ff2e  add     rsp, 88h
0x18000ff35  pop     r15
0x18000ff37  pop     r14
0x18000ff39  pop     r13
0x18000ff3b  pop     r12
0x18000ff3d  pop     rdi
0x18000ff3e  pop     rsi
0x18000ff3f  pop     rbp
0x18000ff40  pop     rbx
0x18000ff41  retn
```
