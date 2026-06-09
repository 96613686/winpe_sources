# PCLmWriter::PDFDocumentWriter::AddNewPage(float,float,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180014a14`
- end: `0x1800152ec`
- name: `?AddNewPage@PDFDocumentWriter@PCLmWriter@@QEAAXMMV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1@Z`
- size: `2264`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x180010290`

## callees

- `0x1800015f0`
- `0x18000e7c8`
- `0x18000ee2c`
- `0x18000ee6c`
- `0x18000ee94`
- `0x18000efa8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f448`
- `0x18000f8d4`
- `0x1800101cc`
- `0x180010618`
- `0x1800106c8`
- `0x180010718`
- `0x180013028`
- `0x180013780`
- `0x1800137c4`
- `0x18001391c`
- `0x180013be0`
- `0x180014158`
- `0x1800146b0`
- `0x18001496c`
- `0x1800149b0`
- `0x180014a14`
- `0x18001583c`
- `0x1800159d0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall PCLmWriter::PDFDocumentWriter::AddNewPage(
        _QWORD *a1,
        float a2,
        float a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rax
  __int64 v9; // r10
  __int64 v10; // r8
  unsigned int v11; // r12d
  unsigned int v12; // r13d
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD); // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rax
  std::_Ref_count_base *v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rbx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  std::_Ref_count_base *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  int v38; // [rsp+28h] [rbp-E0h]
  __int64 v39; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base *v40; // [rsp+50h] [rbp-B8h]
  __int64 v41; // [rsp+58h] [rbp-B0h] BYREF
  std::_Ref_count_base *v42; // [rsp+60h] [rbp-A8h]
  __int64 v43; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h]
  __int64 v45; // [rsp+78h] [rbp-90h]
  _BYTE v46[16]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v47[8]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v48; // [rsp+98h] [rbp-70h]
  __int64 v49; // [rsp+A0h] [rbp-68h]
  std::_Ref_count_base *v50[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v51[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-48h]
  __int64 v53; // [rsp+C8h] [rbp-40h]
  __int64 v54; // [rsp+D0h] [rbp-38h] BYREF
  std::_Ref_count_base *v55; // [rsp+D8h] [rbp-30h]
  _BYTE v56[16]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v57[16]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v58[8]; // [rsp+100h] [rbp-8h] BYREF
  std::_Ref_count_base *v59; // [rsp+108h] [rbp+0h]
  _BYTE v60[8]; // [rsp+110h] [rbp+8h] BYREF
  std::_Ref_count_base *v61; // [rsp+118h] [rbp+10h]
  _BYTE v62[8]; // [rsp+120h] [rbp+18h] BYREF
  std::_Ref_count_base *v63; // [rsp+128h] [rbp+20h]
  _BYTE v64[8]; // [rsp+130h] [rbp+28h] BYREF
  std::_Ref_count_base *v65; // [rsp+138h] [rbp+30h]
  _BYTE v66[8]; // [rsp+140h] [rbp+38h] BYREF
  std::_Ref_count_base *v67; // [rsp+148h] [rbp+40h]
  _BYTE v68[8]; // [rsp+150h] [rbp+48h] BYREF
  std::_Ref_count_base *v69; // [rsp+158h] [rbp+50h]
  _BYTE v70[8]; // [rsp+160h] [rbp+58h] BYREF
  std::_Ref_count_base *v71; // [rsp+168h] [rbp+60h]
  _BYTE v72[8]; // [rsp+170h] [rbp+68h] BYREF
  std::_Ref_count_base *v73; // [rsp+178h] [rbp+70h]
  _BYTE v74[8]; // [rsp+180h] [rbp+78h] BYREF
  std::_Ref_count_base *v75; // [rsp+188h] [rbp+80h]
  _BYTE v76[8]; // [rsp+190h] [rbp+88h] BYREF
  std::_Ref_count_base *v77; // [rsp+198h] [rbp+90h]
  _BYTE v78[8]; // [rsp+1A0h] [rbp+98h] BYREF
  std::_Ref_count_base *v79; // [rsp+1A8h] [rbp+A0h]
  _BYTE v80[24]; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v81; // [rsp+1C8h] [rbp+C0h]
  _BYTE v82[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  std::_Ref_count_base *v83; // [rsp+1D8h] [rbp+D0h]
  _QWORD v84[4]; // [rsp+1F0h] [rbp+E8h] BYREF

  v81 = a4;
  v8 = std::_String_val<std::_Simple_types<char>>::_Myptr(a6);
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, v8, *(unsigned int *)(v10 + 16));
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v47);
  PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier((__int64)a1, &v41);
  v11 = v41;
  v12 = HIDWORD(v41);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v46);
  v13 = *a1;
  v14 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD, _DWORD))(*(_QWORD *)*a1 + 24LL);
  std::string::string(v82, "/Page");
  v14(v13, v78, v82, 0, 0);
  std::string::_Tidy_deallocate(v82);
  std::string::string(v84, "/Type");
  v15 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v46, v84);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v15, v78);
  std::string::_Tidy_deallocate(v84);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(&v43);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*a1 + 16LL))(*a1, v76, 0, 0, 0);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*a1 + 16LL))(*a1, v74, 0, 0, 0);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*a1 + 16LL))(
    *a1,
    v72,
    (unsigned int)(int)a2,
    0,
    0);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*a1 + 16LL))(
    *a1,
    v70,
    (unsigned int)(int)a3,
    0,
    0);
  v16 = (v44 - v43) >> 4;
  if ( v16 <= 4 )
  {
    if ( v16 < 4 )
    {
      if ( (unsigned __int64)((v45 - v43) >> 4) >= 4 )
        v44 = std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
                v44,
                4 - v16,
                &v43);
      else
        std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Resize_reallocate<std::_Value_init_tag>(&v43);
    }
  }
  else
  {
    v17 = v43 + 64;
    std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(v43 + 64, v44);
    v44 = v17;
  }
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v43, v76);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v43 + 16, v74);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v43 + 32, v72);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v43 + 48, v70);
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int64 *, _QWORD, _DWORD))(*(_QWORD *)*a1 + 32LL))(*a1, v68, &v43, 0, 0);
  std::string::string(v82, "/MediaBox");
  v18 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v46, v82);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v18, v68);
  std::string::_Tidy_deallocate(v82);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v57);
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD, _DWORD))(*(_QWORD *)*a1 + 40LL))(*a1, v66, a4, 0, 0);
  std::string::string(v82, "/XObject");
  v19 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v57, v82);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v19, v66);
  std::string::_Tidy_deallocate(v82);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *, _QWORD, _DWORD))(*(_QWORD *)*a1 + 40LL))(*a1, v64, v57, 0, 0);
  std::string::string(v82, "/Resources");
  v20 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v46, v82);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v20, v64);
  std::string::_Tidy_deallocate(v82);
  v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **, _QWORD, _QWORD))(*(_QWORD *)*a1 + 56LL))(
                    *a1,
                    v50,
                    *((unsigned int *)a1 + 19),
                    *((unsigned int *)a1 + 20));
  v84[0] = *v21;
  v22 = (std::_Ref_count_base *)v21[1];
  v84[1] = v22;
  *v21 = 0;
  v21[1] = 0;
  if ( v50[1] )
    std::_Ref_count_base::_Decref(v50[1]);
  std::string::string(v82, "/Parent");
  v23 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v46, v82);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v23, v84);
  std::string::_Tidy_deallocate(v82);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v56);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*a1 + 16LL))(
    *a1,
    v62,
    *(unsigned int *)(a5 + 16),
    0,
    0);
  std::string::string(v82, "/Length");
  v24 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v56, v82);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v24, v62);
  std::string::_Tidy_deallocate(v82);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v80);
  std::_String_val<std::_Simple_types<char>>::_Myptr(a5);
  v25 = std::_String_val<std::_Simple_types<char>>::_Myptr(a5);
  std::vector<unsigned char>::_Assign_counted_range<char const *>(v80, v26, v25 + *(_QWORD *)(a5 + 16) - v26);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *))(*(_QWORD *)*a1 + 80LL))(*a1, v60, v80);
  *(_OWORD *)v50 = 0;
  v27 = *(_QWORD *)PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier((__int64)a1, &v41);
  v41 = v27;
  LOBYTE(v38) = 0;
  v28 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _BYTE *, _BYTE *, int, _DWORD, _DWORD))(*(_QWORD *)*a1 + 48LL))(
          *a1,
          &v39,
          v56,
          v60,
          v38,
          v27,
          HIDWORD(v27));
  std::shared_ptr<PCLmWriter::IByteStream>::operator=(v50, v28);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  v29 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD))(*(_QWORD *)*a1 + 56LL))(
          *a1,
          &v39,
          (unsigned int)v27,
          HIDWORD(v27));
  v54 = *(_QWORD *)v29;
  v55 = *(std::_Ref_count_base **)(v29 + 8);
  *(_QWORD *)v29 = 0;
  *(_QWORD *)(v29 + 8) = 0;
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v51);
  if ( v52 == v53 )
  {
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const> const &>(
      v51,
      v52,
      &v54);
  }
  else
  {
    std::_Construct_in_place<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const> const &>(
      v52,
      &v54);
    v52 += 16;
  }
  v30 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, _BYTE *, _QWORD, _DWORD))(*(_QWORD *)*a1 + 32LL))(
                     *a1,
                     &v39,
                     v51,
                     0,
                     0);
  std::string::string(v82, "/Contents");
  v31 = (_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v46, v82);
  v32 = *v30;
  v33 = v30[1];
  *v30 = 0;
  v30[1] = 0;
  *v31 = v32;
  v34 = (std::_Ref_count_base *)v31[1];
  v31[1] = v33;
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  std::string::_Tidy_deallocate(v82);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *, _QWORD, unsigned int))(*(_QWORD *)*a1 + 40LL))(
    *a1,
    v58,
    v46,
    v11,
    v12);
  v35 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)*a1 + 56LL))(*a1, v82, v11, v12);
  v41 = *(_QWORD *)v35;
  v42 = *(std::_Ref_count_base **)(v35 + 8);
  *(_QWORD *)v35 = 0;
  *(_QWORD *)(v35 + 8) = 0;
  if ( v83 )
    std::_Ref_count_base::_Decref(v83);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v39, v58);
  if ( v48 == v49 )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
      v47,
      v48,
      &v39);
  else
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
      v47,
      &v39);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v39, v50);
  if ( v48 == v49 )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
      v47,
      v48,
      &v39);
  else
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
      v47,
      &v39);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  PCLmWriter::PDFDocumentWriter::WritePDFObjects(a1, v47);
  v36 = a1[13];
  if ( v36 == a1[14] )
  {
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const> const &>(
      a1 + 12,
      a1[13],
      &v41);
  }
  else
  {
    std::_Construct_in_place<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const> const &>(
      v36,
      &v41);
    a1[13] += 16LL;
  }
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(v51);
  if ( v55 )
    std::_Ref_count_base::_Decref(v55);
  if ( v50[1] )
    std::_Ref_count_base::_Decref(v50[1]);
  if ( v61 )
    std::_Ref_count_base::_Decref(v61);
  std::vector<unsigned char>::_Tidy(v80);
  if ( v63 )
    std::_Ref_count_base::_Decref(v63);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v56,
    v56);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( v65 )
    std::_Ref_count_base::_Decref(v65);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v57,
    v57);
  if ( v69 )
    std::_Ref_count_base::_Decref(v69);
  if ( v71 )
    std::_Ref_count_base::_Decref(v71);
  if ( v73 )
    std::_Ref_count_base::_Decref(v73);
  if ( v75 )
    std::_Ref_count_base::_Decref(v75);
  if ( v77 )
    std::_Ref_count_base::_Decref(v77);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(&v43);
  if ( v79 )
    std::_Ref_count_base::_Decref(v79);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v46,
    v46);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(v47);
  return std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
           a4,
           a4);
}

```

## disassembly

```asm
0x180014a14  mov     rax, rsp
0x180014a17  push    rbp
0x180014a18  push    rbx
0x180014a19  push    rsi
0x180014a1a  push    rdi
0x180014a1b  push    r12
0x180014a1d  push    r13
0x180014a1f  push    r14
0x180014a21  push    r15
0x180014a23  lea     rbp, [rax-178h]
0x180014a2a  sub     rsp, 238h
0x180014a31  movaps  xmmword ptr [rax-58h], xmm6
0x180014a35  movaps  xmmword ptr [rax-68h], xmm7
0x180014a39  mov     rax, cs:__security_cookie
0x180014a40  xor     rax, rsp
0x180014a43  mov     [rbp+170h+var_68], rax
0x180014a4a  mov     r14, r9
0x180014a4d  movaps  xmm7, xmm2
0x180014a50  movaps  xmm6, xmm1
0x180014a53  mov     rsi, rcx
0x180014a56  mov     [rbp+170h+var_B0], r9
0x180014a5d  mov     r15, [rbp+170h+arg_20]
0x180014a64  mov     r8, [rbp+170h+arg_28]
0x180014a6b  mov     r10, [rcx+10h]
0x180014a6f  mov     rcx, r8
0x180014a72  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180014a77  mov     rdx, [r10]
0x180014a7a  mov     r9, [rdx+18h]
0x180014a7e  mov     r8d, [r8+10h]
0x180014a82  mov     rdx, rax
0x180014a85  mov     rcx, r10
0x180014a88  mov     rax, r9
0x180014a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a90  lea     rcx, [rbp+170h+var_1E8]
0x180014a94  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180014a99  nop
0x180014a9a  lea     rdx, [rsp+270h+var_220]
0x180014a9f  mov     rcx, rsi
0x180014aa2  call    ?GenerateObjectIdentifier@PDFDocumentWriter@PCLmWriter@@QEAA?AU?$pair@II@std@@XZ; PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(void)
0x180014aa7  mov     r12d, dword ptr [rsp+270h+var_220]
0x180014aac  mov     r13d, dword ptr [rsp+270h+var_220+4]
0x180014ab1  lea     rcx, [rsp+270h+var_1F8]
0x180014ab6  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180014abb  nop
0x180014abc  mov     rdi, [rsi]
0x180014abf  mov     rax, [rdi]
0x180014ac2  mov     rbx, [rax+18h]
0x180014ac6  lea     rdx, aPage; "/Page"
0x180014acd  lea     rcx, [rbp+170h+var_A8]
0x180014ad4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014ad9  nop
0x180014ada  mov     [rsp+270h+var_250], 0
0x180014ae2  xor     r9d, r9d
0x180014ae5  lea     r8, [rbp+170h+var_A8]
0x180014aec  lea     rdx, [rbp+170h+var_D8]
0x180014af3  mov     rcx, rdi
0x180014af6  mov     rax, rbx
0x180014af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014afe  nop
0x180014aff  lea     rcx, [rbp+170h+var_A8]
0x180014b06  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014b0b  lea     rdx, aType; "/Type"
0x180014b12  lea     rcx, [rbp+170h+var_88]
0x180014b19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014b1e  nop
0x180014b1f  lea     rdx, [rbp+170h+var_88]
0x180014b26  lea     rcx, [rsp+270h+var_1F8]
0x180014b2b  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014b30  mov     rcx, rax
0x180014b33  lea     rdx, [rbp+170h+var_D8]
0x180014b3a  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014b3f  nop
0x180014b40  lea     rcx, [rbp+170h+var_88]
0x180014b47  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014b4c  lea     rcx, [rsp+270h+var_210]
0x180014b51  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180014b56  nop
0x180014b57  mov     rcx, [rsi]
0x180014b5a  mov     rax, [rcx]
0x180014b5d  xor     ebx, ebx
0x180014b5f  mov     [rsp+270h+var_250], ebx
0x180014b63  xor     r9d, r9d
0x180014b66  xor     r8d, r8d
0x180014b69  lea     rdx, [rbp+170h+var_E8]
0x180014b70  mov     rax, [rax+10h]
0x180014b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b79  nop
0x180014b7a  mov     rcx, [rsi]
0x180014b7d  mov     rax, [rcx]
0x180014b80  mov     [rsp+270h+var_250], ebx
0x180014b84  xor     r9d, r9d
0x180014b87  xor     r8d, r8d
0x180014b8a  lea     rdx, [rbp+170h+var_F8]
0x180014b8e  mov     rax, [rax+10h]
0x180014b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b97  nop
0x180014b98  mov     rcx, [rsi]
0x180014b9b  mov     rax, [rcx]
0x180014b9e  cvttss2si r8d, xmm6
0x180014ba3  mov     [rsp+270h+var_250], ebx
0x180014ba7  xor     r9d, r9d
0x180014baa  lea     rdx, [rbp+170h+var_108]
0x180014bae  mov     rax, [rax+10h]
0x180014bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb7  nop
0x180014bb8  mov     rcx, [rsi]
0x180014bbb  mov     rax, [rcx]
0x180014bbe  cvttss2si r8d, xmm7
0x180014bc3  mov     [rsp+270h+var_250], ebx
0x180014bc7  xor     r9d, r9d
0x180014bca  lea     rdx, [rbp+170h+var_118]
0x180014bce  mov     rax, [rax+10h]
0x180014bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bd7  nop
0x180014bd8  mov     r8, [rsp+270h+var_210]
0x180014bdd  mov     r9, [rsp+270h+var_208]
0x180014be2  mov     rcx, r9
0x180014be5  sub     rcx, r8
0x180014be8  sar     rcx, 4
0x180014bec  lea     edx, [rbx+4]
0x180014bef  cmp     rcx, rdx
0x180014bf2  jbe     short loc_180014C0C
0x180014bf4  lea     rbx, [r8+40h]
0x180014bf8  mov     rdx, r9
0x180014bfb  mov     rcx, rbx
0x180014bfe  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x180014c03  mov     [rsp+270h+var_208], rbx
0x180014c08  xor     ebx, ebx
0x180014c0a  jmp     short loc_180014C40
0x180014c0c  jnb     short loc_180014C40
0x180014c0e  mov     rax, [rsp+270h+var_200]
0x180014c13  sub     rax, r8
0x180014c16  sar     rax, 4
0x180014c1a  cmp     rax, rdx
0x180014c1d  jnb     short loc_180014C2B
0x180014c1f  lea     rcx, [rsp+270h+var_210]
0x180014c24  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180014c29  jmp     short loc_180014C40
0x180014c2b  sub     rdx, rcx
0x180014c2e  lea     r8, [rsp+270h+var_210]
0x180014c33  mov     rcx, r9
0x180014c36  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@PEAV10@_KAEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,unsigned __int64,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x180014c3b  mov     [rsp+270h+var_208], rax
0x180014c40  lea     rdx, [rbp+170h+var_E8]
0x180014c47  mov     rcx, [rsp+270h+var_210]
0x180014c4c  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014c51  mov     rcx, [rsp+270h+var_210]
0x180014c56  add     rcx, 10h
0x180014c5a  lea     rdx, [rbp+170h+var_F8]
0x180014c5e  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014c63  mov     rcx, [rsp+270h+var_210]
0x180014c68  add     rcx, 20h ; ' '
0x180014c6c  lea     rdx, [rbp+170h+var_108]
0x180014c70  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014c75  mov     rcx, [rsp+270h+var_210]
0x180014c7a  add     rcx, 30h ; '0'
0x180014c7e  lea     rdx, [rbp+170h+var_118]
0x180014c82  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014c87  mov     rcx, [rsi]
0x180014c8a  mov     rax, [rcx]
0x180014c8d  mov     [rsp+270h+var_250], ebx
0x180014c91  xor     r9d, r9d
0x180014c94  lea     r8, [rsp+270h+var_210]
0x180014c99  lea     rdx, [rbp+170h+var_128]
0x180014c9d  mov     rax, [rax+20h]
0x180014ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca6  nop
0x180014ca7  lea     rdx, aMediabox; "/MediaBox"
0x180014cae  lea     rcx, [rbp+170h+var_A8]
0x180014cb5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014cba  nop
0x180014cbb  lea     rdx, [rbp+170h+var_A8]
0x180014cc2  lea     rcx, [rsp+270h+var_1F8]
0x180014cc7  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014ccc  mov     rcx, rax
0x180014ccf  lea     rdx, [rbp+170h+var_128]
0x180014cd3  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014cd8  nop
0x180014cd9  lea     rcx, [rbp+170h+var_A8]
0x180014ce0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014ce5  lea     rcx, [rbp+170h+var_188]
0x180014ce9  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180014cee  nop
0x180014cef  mov     rcx, [rsi]
0x180014cf2  mov     rax, [rcx]
0x180014cf5  mov     [rsp+270h+var_250], ebx
0x180014cf9  xor     r9d, r9d
0x180014cfc  mov     r8, r14
0x180014cff  lea     rdx, [rbp+170h+var_138]
0x180014d03  mov     rax, [rax+28h]
0x180014d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d0c  nop
0x180014d0d  lea     rdx, aXobject; "/XObject"
0x180014d14  lea     rcx, [rbp+170h+var_A8]
0x180014d1b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014d20  nop
0x180014d21  lea     rdx, [rbp+170h+var_A8]
0x180014d28  lea     rcx, [rbp+170h+var_188]
0x180014d2c  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014d31  mov     rcx, rax
0x180014d34  lea     rdx, [rbp+170h+var_138]
0x180014d38  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180014d3d  nop
0x180014d3e  lea     rcx, [rbp+170h+var_A8]
0x180014d45  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014d4a  mov     rcx, [rsi]
0x180014d4d  mov     rax, [rcx]
0x180014d50  mov     [rsp+270h+var_250], ebx
0x180014d54  xor     r9d, r9d
0x180014d57  lea     r8, [rbp+170h+var_188]
0x180014d5b  lea     rdx, [rbp+170h+var_148]
0x180014d5f  mov     rax, [rax+28h]
0x180014d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d68  nop
0x180014d69  lea     rdx, aResources; "/Resources"
0x180014d70  lea     rcx, [rbp+170h+var_A8]
0x180014d77  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014d7c  nop
0x180014d7d  lea     rdx, [rbp+170h+var_A8]
0x180014d84  lea     rcx, [rsp+270h+var_1F8]
0x180014d89  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014d8e  mov     rcx, rax
0x180014d91  lea     rdx, [rbp+170h+var_148]
0x180014d95  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180014d9a  nop
0x180014d9b  lea     rcx, [rbp+170h+var_A8]
0x180014da2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014da7  mov     rcx, [rsi]
0x180014daa  mov     rax, [rcx]
0x180014dad  mov     r9d, [rsi+50h]
0x180014db1  mov     r8d, [rsi+4Ch]
0x180014db5  lea     rdx, [rbp+170h+var_1D0]
0x180014db9  mov     rax, [rax+38h]
0x180014dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc2  mov     rcx, [rax]
0x180014dc5  mov     [rbp+170h+var_88], rcx
0x180014dcc  mov     rdi, [rax+8]
0x180014dd0  mov     [rbp+170h+var_80], rdi
0x180014dd7  mov     [rax], rbx
0x180014dda  mov     [rax+8], rbx
0x180014dde  mov     rcx, [rbp+170h+var_1D0+8]; this
0x180014de2  test    rcx, rcx
0x180014de5  jz      short loc_180014DEC
0x180014de7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014dec  lea     rdx, aParent; "/Parent"
0x180014df3  lea     rcx, [rbp+170h+var_A8]
0x180014dfa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014dff  nop
0x180014e00  lea     rdx, [rbp+170h+var_A8]
0x180014e07  lea     rcx, [rsp+270h+var_1F8]
0x180014e0c  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014e11  mov     rcx, rax
0x180014e14  lea     rdx, [rbp+170h+var_88]
0x180014e1b  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180014e20  nop
0x180014e21  lea     rcx, [rbp+170h+var_A8]
0x180014e28  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014e2d  lea     rcx, [rbp+170h+var_198]
0x180014e31  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180014e36  nop
0x180014e37  mov     rcx, [rsi]
0x180014e3a  mov     rax, [rcx]
0x180014e3d  mov     [rsp+270h+var_250], ebx
0x180014e41  xor     r9d, r9d
0x180014e44  mov     r8d, [r15+10h]
0x180014e48  lea     rdx, [rbp+170h+var_158]
0x180014e4c  mov     rax, [rax+10h]
0x180014e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e55  nop
0x180014e56  lea     rdx, aLength; "/Length"
0x180014e5d  lea     rcx, [rbp+170h+var_A8]
0x180014e64  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014e69  nop
0x180014e6a  lea     rdx, [rbp+170h+var_A8]
0x180014e71  lea     rcx, [rbp+170h+var_198]
0x180014e75  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180014e7a  mov     rcx, rax
0x180014e7d  lea     rdx, [rbp+170h+var_158]
0x180014e81  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180014e86  nop
0x180014e87  lea     rcx, [rbp+170h+var_A8]
0x180014e8e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014e93  lea     rcx, [rbp+170h+var_C8]
0x180014e9a  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180014e9f  nop
0x180014ea0  mov     rcx, r15
0x180014ea3  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180014ea8  mov     rdx, rax
0x180014eab  mov     rcx, r15
0x180014eae  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180014eb3  mov     r8, [r15+10h]
0x180014eb7  sub     r8, rdx
0x180014eba  add     r8, rax
0x180014ebd  lea     rcx, [rbp+170h+var_C8]
0x180014ec4  call    ??$_Assign_counted_range@PEBD@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBD_K@Z; std::vector<uchar>::_Assign_counted_range<char const *>(char const *,unsigned __int64)
0x180014ec9  mov     rcx, [rsi]
0x180014ecc  mov     rax, [rcx]
0x180014ecf  lea     r8, [rbp+170h+var_C8]
0x180014ed6  lea     rdx, [rbp+170h+var_168]
0x180014eda  mov     rax, [rax+50h]
  ... truncated ...
```
