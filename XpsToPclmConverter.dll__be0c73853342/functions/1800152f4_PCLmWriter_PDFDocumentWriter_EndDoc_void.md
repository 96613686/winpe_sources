# PCLmWriter::PDFDocumentWriter::EndDoc(void)

- ea: `0x1800152f4`
- end: `0x180015836`
- name: `?EndDoc@PDFDocumentWriter@PCLmWriter@@QEAAXXZ`
- size: `1346`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18000ea00`

## callees

- `0x1800015f0`
- `0x18000e7c8`
- `0x18000ee6c`
- `0x18000ee94`
- `0x18000efa8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f448`
- `0x18000f8d4`
- `0x1800101cc`
- `0x1800106c8`
- `0x180010718`
- `0x180013780`
- `0x1800149b0`
- `0x1800152f4`
- `0x1800159d0`
- `0x180015b6c`
- `0x180015bf0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall PCLmWriter::PDFDocumentWriter::EndDoc(PCLmWriter::PDFDocumentWriter *this)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD); // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  std::_Ref_count_base *v8; // r15
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD); // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rax
  std::_Ref_count_base *v14; // rdi
  __int64 *v15; // rax
  std::_Ref_count_base *v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rbx
  _BYTE *v19; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-C8h]
  _BYTE v21[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  _BYTE v24[16]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v29; // [rsp+90h] [rbp-70h]
  _QWORD v30[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v32; // [rsp+B0h] [rbp-50h]
  _BYTE v33[8]; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v34; // [rsp+C0h] [rbp-40h]
  _BYTE v35[8]; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v36; // [rsp+D0h] [rbp-30h]
  _BYTE v37[8]; // [rsp+D8h] [rbp-28h] BYREF
  std::_Ref_count_base *v38; // [rsp+E0h] [rbp-20h]
  _BYTE v39[8]; // [rsp+E8h] [rbp-18h] BYREF
  std::_Ref_count_base *v40; // [rsp+F0h] [rbp-10h]
  _BYTE v41[8]; // [rsp+F8h] [rbp-8h] BYREF
  std::_Ref_count_base *v42; // [rsp+100h] [rbp+0h]
  _BYTE v43[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v44[8]; // [rsp+128h] [rbp+28h] BYREF
  std::_Ref_count_base *v45; // [rsp+130h] [rbp+30h]
  _BYTE v46[32]; // [rsp+148h] [rbp+48h] BYREF

  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v21);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v24);
  v2 = *(_QWORD *)this;
  v3 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD))(**(_QWORD **)this + 24LL);
  std::string::string(v43, "/Pages");
  v3(v2, v41, v43, 0, 0);
  std::string::_Tidy_deallocate(v43);
  std::string::string(v44, "/Type");
  v4 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v24, v44);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v4, v41);
  std::string::_Tidy_deallocate(v44);
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD, _DWORD))(**(_QWORD **)this + 16LL))(
    *(_QWORD *)this,
    v39,
    (__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 12)) >> 4,
    0,
    0);
  std::string::string(v43, "/Count");
  v5 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v24, v43);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v5, v39);
  std::string::_Tidy_deallocate(v43);
  (*(void (__fastcall **)(_QWORD, _BYTE *, char *, _QWORD, _DWORD))(**(_QWORD **)this + 32LL))(
    *(_QWORD *)this,
    v37,
    (char *)this + 96,
    0,
    0);
  std::string::string(v43, "/Kids");
  v6 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v24, v43);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v6, v37);
  std::string::_Tidy_deallocate(v43);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *, _QWORD, _DWORD))(**(_QWORD **)this + 40LL))(
    *(_QWORD *)this,
    v35,
    v24,
    *((unsigned int *)this + 19),
    *((_DWORD *)this + 20));
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD))(**(_QWORD **)this + 56LL))(
                   *(_QWORD *)this,
                   &v28,
                   *((unsigned int *)this + 19),
                   *((unsigned int *)this + 20));
  v30[0] = *v7;
  v8 = (std::_Ref_count_base *)v7[1];
  v30[1] = v8;
  *v7 = 0;
  v7[1] = 0;
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v19, v35);
  if ( v22 == v23 )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
      v21,
      v22,
      &v19);
  else
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
      v21,
      &v19);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v25);
  v9 = *(_QWORD *)this;
  v10 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD))(**(_QWORD **)this + 24LL);
  std::string::string(v43, "/Catalog");
  v10(v9, v33, v43, 0, 0);
  std::string::_Tidy_deallocate(v43);
  std::string::string(v44, "/Type");
  v11 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v25, v44);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v11, v33);
  std::string::_Tidy_deallocate(v44);
  std::string::string(v44, "/Pages");
  v12 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v25, v44);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v12, v30);
  std::string::_Tidy_deallocate(v44);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *, _QWORD, _DWORD))(**(_QWORD **)this + 40LL))(
    *(_QWORD *)this,
    v31,
    v25,
    *((unsigned int *)this + 21),
    *((_DWORD *)this + 22));
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v19, v31);
  if ( v22 == v23 )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
      v21,
      v22,
      &v19);
  else
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
      v21,
      &v19);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  PCLmWriter::PDFDocumentWriter::WritePDFObjects(this, v21);
  v13 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD))(**(_QWORD **)this + 56LL))(
                     *(_QWORD *)this,
                     &v26,
                     *((unsigned int *)this + 21),
                     *((unsigned int *)this + 22));
  v28 = *v13;
  v14 = (std::_Ref_count_base *)v13[1];
  v29 = v14;
  *v13 = 0;
  v13[1] = 0;
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  v15 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(**(_QWORD **)this + 16LL))(
                     *(_QWORD *)this,
                     v44,
                     0,
                     0,
                     0);
  v26 = *v15;
  v16 = (std::_Ref_count_base *)v15[1];
  v27 = v16;
  *v15 = 0;
  v15[1] = 0;
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  v19 = v43;
  v17 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v43, &v26);
  std::string::string(v46, "/Size");
  PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(this, v46, v17);
  std::string::_Tidy_deallocate(v46);
  v19 = v43;
  v18 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v43, &v28);
  std::string::string(v46, "/Root");
  PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(this, v46, v18);
  std::string::_Tidy_deallocate(v46);
  PCLmWriter::PDFDocumentWriter::_AddXRef(this);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v25,
    v25);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v24,
    v24);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(v21);
}

```

## disassembly

```asm
0x1800152f4  push    rbp
0x1800152f6  push    rbx
0x1800152f7  push    rsi
0x1800152f8  push    rdi
0x1800152f9  push    r14
0x1800152fb  push    r15
0x1800152fd  lea     rbp, [rsp-78h]
0x180015302  sub     rsp, 178h
0x180015309  mov     rax, cs:__security_cookie
0x180015310  xor     rax, rsp
0x180015313  mov     [rbp+0A0h+var_38], rax
0x180015317  mov     rsi, rcx
0x18001531a  lea     rcx, [rsp+1A0h+var_160]
0x18001531f  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180015324  nop
0x180015325  lea     rcx, [rsp+1A0h+var_148]
0x18001532a  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x18001532f  nop
0x180015330  mov     rdi, [rsi]
0x180015333  mov     rax, [rdi]
0x180015336  mov     rbx, [rax+18h]
0x18001533a  lea     rdx, aPages; "/Pages"
0x180015341  lea     rcx, [rbp+0A0h+var_98]
0x180015345  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001534a  nop
0x18001534b  mov     [rsp+1A0h+var_180], 0
0x180015353  xor     r9d, r9d
0x180015356  lea     r8, [rbp+0A0h+var_98]
0x18001535a  lea     rdx, [rbp+0A0h+var_A8]
0x18001535e  mov     rcx, rdi
0x180015361  mov     rax, rbx
0x180015364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015369  nop
0x18001536a  lea     rcx, [rbp+0A0h+var_98]
0x18001536e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015373  lea     rdx, aType; "/Type"
0x18001537a  lea     rcx, [rbp+0A0h+var_78]
0x18001537e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015383  nop
0x180015384  lea     rdx, [rbp+0A0h+var_78]
0x180015388  lea     rcx, [rsp+1A0h+var_148]
0x18001538d  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180015392  mov     rcx, rax
0x180015395  lea     rdx, [rbp+0A0h+var_A8]
0x180015399  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x18001539e  nop
0x18001539f  lea     rcx, [rbp+0A0h+var_78]
0x1800153a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800153a8  mov     rcx, [rsi]
0x1800153ab  mov     rax, [rcx]
0x1800153ae  mov     r8, [rsi+68h]
0x1800153b2  sub     r8, [rsi+60h]
0x1800153b6  sar     r8, 4
0x1800153ba  mov     [rsp+1A0h+var_180], 0
0x1800153c2  xor     r9d, r9d
0x1800153c5  lea     rdx, [rbp+0A0h+var_B8]
0x1800153c9  mov     rax, [rax+10h]
0x1800153cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d2  nop
0x1800153d3  lea     rdx, aCount; "/Count"
0x1800153da  lea     rcx, [rbp+0A0h+var_98]
0x1800153de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800153e3  nop
0x1800153e4  lea     rdx, [rbp+0A0h+var_98]
0x1800153e8  lea     rcx, [rsp+1A0h+var_148]
0x1800153ed  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x1800153f2  mov     rcx, rax
0x1800153f5  lea     rdx, [rbp+0A0h+var_B8]
0x1800153f9  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x1800153fe  nop
0x1800153ff  lea     rcx, [rbp+0A0h+var_98]
0x180015403  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015408  mov     rcx, [rsi]
0x18001540b  mov     rax, [rcx]
0x18001540e  mov     [rsp+1A0h+var_180], 0
0x180015416  xor     r9d, r9d
0x180015419  lea     r8, [rsi+60h]
0x18001541d  lea     rdx, [rbp+0A0h+var_C8]
0x180015421  mov     rax, [rax+20h]
0x180015425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001542a  nop
0x18001542b  lea     rdx, aKids; "/Kids"
0x180015432  lea     rcx, [rbp+0A0h+var_98]
0x180015436  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001543b  nop
0x18001543c  lea     rdx, [rbp+0A0h+var_98]
0x180015440  lea     rcx, [rsp+1A0h+var_148]
0x180015445  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x18001544a  mov     rcx, rax
0x18001544d  lea     rdx, [rbp+0A0h+var_C8]
0x180015451  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180015456  nop
0x180015457  lea     rcx, [rbp+0A0h+var_98]
0x18001545b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015460  mov     r10, [rsi]
0x180015463  mov     rax, [r10]
0x180015466  mov     ecx, [rsi+50h]
0x180015469  mov     [rsp+1A0h+var_180], ecx
0x18001546d  mov     r9d, [rsi+4Ch]
0x180015471  lea     r8, [rsp+1A0h+var_148]
0x180015476  lea     rdx, [rbp+0A0h+var_D8]
0x18001547a  mov     rcx, r10
0x18001547d  mov     rax, [rax+28h]
0x180015481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015486  nop
0x180015487  mov     rcx, [rsi]
0x18001548a  mov     rax, [rcx]
0x18001548d  mov     r9d, [rsi+50h]
0x180015491  mov     r8d, [rsi+4Ch]
0x180015495  lea     rdx, [rbp+0A0h+var_118]
0x180015499  mov     rax, [rax+38h]
0x18001549d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a2  mov     rcx, [rax]
0x1800154a5  mov     [rbp+0A0h+var_108], rcx
0x1800154a9  mov     r15, [rax+8]
0x1800154ad  mov     [rbp+0A0h+var_100], r15
0x1800154b1  mov     qword ptr [rax], 0
0x1800154b8  mov     qword ptr [rax+8], 0
0x1800154c0  mov     rcx, [rbp+0A0h+var_110]; this
0x1800154c4  test    rcx, rcx
0x1800154c7  jz      short loc_1800154CE
0x1800154c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800154ce  lea     rdx, [rbp+0A0h+var_D8]
0x1800154d2  lea     rcx, [rsp+1A0h+var_170]
0x1800154d7  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800154dc  nop
0x1800154dd  mov     rdx, [rsp+1A0h+var_158]
0x1800154e2  lea     rcx, [rsp+1A0h+var_160]
0x1800154e7  cmp     rdx, [rsp+1A0h+var_150]
0x1800154ec  jz      short loc_1800154FA
0x1800154ee  lea     rdx, [rsp+1A0h+var_170]
0x1800154f3  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> &&)
0x1800154f8  jmp     short loc_180015505
0x1800154fa  lea     r8, [rsp+1A0h+var_170]
0x1800154ff  call    ??$_Emplace_reallocate@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> &&)
0x180015504  nop
0x180015505  mov     rcx, [rsp+1A0h+var_168]; this
0x18001550a  test    rcx, rcx
0x18001550d  jz      short loc_180015514
0x18001550f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015514  lea     rcx, [rsp+1A0h+var_138]
0x180015519  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x18001551e  nop
0x18001551f  mov     rdi, [rsi]
0x180015522  mov     rax, [rdi]
0x180015525  mov     rbx, [rax+18h]
0x180015529  lea     rdx, aCatalog; "/Catalog"
0x180015530  lea     rcx, [rbp+0A0h+var_98]
0x180015534  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015539  nop
0x18001553a  mov     [rsp+1A0h+var_180], 0
0x180015542  xor     r9d, r9d
0x180015545  lea     r8, [rbp+0A0h+var_98]
0x180015549  lea     rdx, [rbp+0A0h+var_E8]
0x18001554d  mov     rcx, rdi
0x180015550  mov     rax, rbx
0x180015553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015558  nop
0x180015559  lea     rcx, [rbp+0A0h+var_98]
0x18001555d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015562  lea     rdx, aType; "/Type"
0x180015569  lea     rcx, [rbp+0A0h+var_78]
0x18001556d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015572  nop
0x180015573  lea     rdx, [rbp+0A0h+var_78]
0x180015577  lea     rcx, [rsp+1A0h+var_138]
0x18001557c  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180015581  mov     rcx, rax
0x180015584  lea     rdx, [rbp+0A0h+var_E8]
0x180015588  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x18001558d  nop
0x18001558e  lea     rcx, [rbp+0A0h+var_78]
0x180015592  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015597  lea     rdx, aPages; "/Pages"
0x18001559e  lea     rcx, [rbp+0A0h+var_78]
0x1800155a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800155a7  nop
0x1800155a8  lea     rdx, [rbp+0A0h+var_78]
0x1800155ac  lea     rcx, [rsp+1A0h+var_138]
0x1800155b1  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x1800155b6  mov     rcx, rax
0x1800155b9  lea     rdx, [rbp+0A0h+var_108]
0x1800155bd  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x1800155c2  nop
0x1800155c3  lea     rcx, [rbp+0A0h+var_78]
0x1800155c7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800155cc  mov     r10, [rsi]
0x1800155cf  mov     rax, [r10]
0x1800155d2  mov     ecx, [rsi+58h]
0x1800155d5  mov     [rsp+1A0h+var_180], ecx
0x1800155d9  mov     r9d, [rsi+54h]
0x1800155dd  lea     r8, [rsp+1A0h+var_138]
0x1800155e2  lea     rdx, [rbp+0A0h+var_F8]
0x1800155e6  mov     rcx, r10
0x1800155e9  mov     rax, [rax+28h]
0x1800155ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f2  nop
0x1800155f3  lea     rdx, [rbp+0A0h+var_F8]
0x1800155f7  lea     rcx, [rsp+1A0h+var_170]
0x1800155fc  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180015601  nop
0x180015602  mov     rdx, [rsp+1A0h+var_158]
0x180015607  lea     rcx, [rsp+1A0h+var_160]
0x18001560c  cmp     rdx, [rsp+1A0h+var_150]
0x180015611  jz      short loc_18001561F
0x180015613  lea     rdx, [rsp+1A0h+var_170]
0x180015618  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> &&)
0x18001561d  jmp     short loc_18001562A
0x18001561f  lea     r8, [rsp+1A0h+var_170]
0x180015624  call    ??$_Emplace_reallocate@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> &&)
0x180015629  nop
0x18001562a  mov     rcx, [rsp+1A0h+var_168]; this
0x18001562f  test    rcx, rcx
0x180015632  jz      short loc_180015639
0x180015634  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015639  lea     rdx, [rsp+1A0h+var_160]
0x18001563e  mov     rcx, rsi
0x180015641  call    ?WritePDFObjects@PDFDocumentWriter@PCLmWriter@@QEAAXAEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@@Z; PCLmWriter::PDFDocumentWriter::WritePDFObjects(std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &)
0x180015646  mov     rcx, [rsi]
0x180015649  mov     rax, [rcx]
0x18001564c  mov     r9d, [rsi+58h]
0x180015650  mov     r8d, [rsi+54h]
0x180015654  lea     rdx, [rsp+1A0h+var_128]
0x180015659  mov     rax, [rax+38h]
0x18001565d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015662  mov     rcx, [rax]
0x180015665  mov     [rbp+0A0h+var_118], rcx
0x180015669  mov     rdi, [rax+8]
0x18001566d  mov     [rbp+0A0h+var_110], rdi
0x180015671  mov     qword ptr [rax], 0
0x180015678  mov     qword ptr [rax+8], 0
0x180015680  mov     rcx, [rbp+0A0h+var_120]; this
0x180015684  test    rcx, rcx
0x180015687  jz      short loc_18001568E
0x180015689  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001568e  mov     rcx, [rsi]
0x180015691  mov     rax, [rcx]
0x180015694  mov     [rsp+1A0h+var_180], 0
0x18001569c  xor     r9d, r9d
0x18001569f  xor     r8d, r8d
0x1800156a2  lea     rdx, [rbp+0A0h+var_78]
0x1800156a6  mov     rax, [rax+10h]
0x1800156aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156af  mov     rcx, [rax]
0x1800156b2  mov     [rsp+1A0h+var_128], rcx
0x1800156b7  mov     r14, [rax+8]
0x1800156bb  mov     [rbp+0A0h+var_120], r14
0x1800156bf  mov     qword ptr [rax], 0
0x1800156c6  mov     qword ptr [rax+8], 0
0x1800156ce  mov     rcx, [rbp+0A0h+var_70]; this
0x1800156d2  test    rcx, rcx
0x1800156d5  jz      short loc_1800156DC
0x1800156d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800156dc  lea     rax, [rbp+0A0h+var_98]
0x1800156e0  mov     [rsp+1A0h+var_170], rax
0x1800156e5  lea     rdx, [rsp+1A0h+var_128]
0x1800156ea  lea     rcx, [rbp+0A0h+var_98]
0x1800156ee  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800156f3  mov     rbx, rax
0x1800156f6  lea     rdx, aSize; "/Size"
0x1800156fd  lea     rcx, [rbp+0A0h+var_58]
0x180015701  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015706  nop
0x180015707  mov     r8, rbx
0x18001570a  lea     rdx, [rbp+0A0h+var_58]
0x18001570e  mov     rcx, rsi
0x180015711  call    ?_AddTrailerEntry@PDFDocumentWriter@PCLmWriter@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@4@@Z; PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(std::string const &,std::shared_ptr<PCLmWriter::IObject const>)
0x180015716  nop
0x180015717  lea     rcx, [rbp+0A0h+var_58]
0x18001571b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015720  lea     rax, [rbp+0A0h+var_98]
0x180015724  mov     [rsp+1A0h+var_170], rax
0x180015729  lea     rdx, [rbp+0A0h+var_118]
0x18001572d  lea     rcx, [rbp+0A0h+var_98]
0x180015731  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180015736  mov     rbx, rax
0x180015739  lea     rdx, aRoot; "/Root"
0x180015740  lea     rcx, [rbp+0A0h+var_58]
0x180015744  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015749  nop
0x18001574a  mov     r8, rbx
0x18001574d  lea     rdx, [rbp+0A0h+var_58]
0x180015751  mov     rcx, rsi
0x180015754  call    ?_AddTrailerEntry@PDFDocumentWriter@PCLmWriter@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@4@@Z; PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(std::string const &,std::shared_ptr<PCLmWriter::IObject const>)
0x180015759  nop
0x18001575a  lea     rcx, [rbp+0A0h+var_58]
0x18001575e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015763  mov     rcx, rsi; this
0x180015766  call    ?_AddXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ; PCLmWriter::PDFDocumentWriter::_AddXRef(void)
0x18001576b  nop
0x18001576c  test    r14, r14
0x18001576f  jz      short loc_18001577A
0x180015771  mov     rcx, r14; this
0x180015774  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015779  nop
0x18001577a  test    rdi, rdi
0x18001577d  jz      short loc_180015788
0x18001577f  mov     rcx, rdi; this
0x180015782  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015787  nop
  ... truncated ...
```
