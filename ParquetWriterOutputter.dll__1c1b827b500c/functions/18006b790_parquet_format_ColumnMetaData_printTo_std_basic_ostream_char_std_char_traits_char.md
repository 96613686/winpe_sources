# parquet::format::ColumnMetaData::printTo(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18006b790`
- end: `0x18006c06f`
- name: `?printTo@ColumnMetaData@format@parquet@@UEBAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `2271`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18005f790`
- `0x180061ec0`
- `0x180062ea0`
- `0x180063ee0`
- `0x180064ab0`
- `0x180064d10`
- `0x18006b790`
- `0x180075c60`
- `0x180075f80`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18006b8ef`: `path_in_schema=`
- `0x18006ba78`: `total_uncompressed_size=`
- `0x18006bafb`: `total_compressed_size=`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall parquet::format::ColumnMetaData::printTo(__int64 a1, __int64 a2)
{
  char v4; // bl
  _QWORD *v5; // r14
  __int64 v6; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  _QWORD *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  void *v15; // rcx
  _QWORD *v16; // r14
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  void *v21; // rcx
  _QWORD *v22; // r14
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  void *v27; // rcx
  _QWORD *v28; // r14
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  void *v33; // rcx
  _QWORD *v34; // r14
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r8
  unsigned __int64 v38; // rdx
  void *v39; // rcx
  _QWORD *v40; // r14
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // r8
  unsigned __int64 v44; // rdx
  void *v45; // rcx
  __int64 v46; // rax
  _QWORD *v47; // rax
  __int64 v48; // r8
  unsigned __int64 v49; // rdx
  void *v50; // rcx
  _QWORD *v51; // r14
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  unsigned __int64 v55; // rdx
  void *v56; // rcx
  __int64 v57; // rax
  _QWORD *v58; // rax
  __int64 v59; // r8
  unsigned __int64 v60; // rdx
  void *v61; // rcx
  __int64 v62; // rax
  _QWORD *v63; // rax
  __int64 v64; // r8
  unsigned __int64 v65; // rdx
  void *v66; // rcx
  __int64 v67; // rax
  _QWORD *v68; // rax
  __int64 v69; // r8
  unsigned __int64 v70; // rdx
  void *v71; // rcx
  __int64 v72; // rax
  _QWORD *v73; // rax
  __int64 v74; // r8
  unsigned __int64 v75; // rdx
  void *v76; // rcx
  __int64 v77; // rax
  _QWORD *v78; // rax
  __int64 v79; // r8
  unsigned __int64 v80; // rdx
  void *v81; // rcx
  _QWORD Src[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v84; // [rsp+48h] [rbp-18h]

  v4 = 0;
  std::operator<<<std::char_traits<char>>(a2, "ColumnMetaData(");
  v5 = (_QWORD *)parquet::format::to_string(Src);
  v6 = std::operator<<<std::char_traits<char>>(a2, "type=");
  v7 = v5[2];
  if ( v5[3] >= 0x10u )
    v5 = (_QWORD *)*v5;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v6, v5, v7);
  if ( v84 >= 0x10 )
  {
    v8 = v84 + 1;
    v9 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v8 = v84 + 40;
      v9 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v9 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v9, v8);
  }
  v10 = (_QWORD *)apache::thrift::to_string<enum parquet::format::Encoding::type>(Src);
  v11 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v12 = std::operator<<<std::char_traits<char>>(v11, "encodings=");
  v13 = v10[2];
  if ( v10[3] >= 0x10u )
    v10 = (_QWORD *)*v10;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, v10, v13);
  if ( v84 >= 0x10 )
  {
    v14 = v84 + 1;
    v15 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v14 = v84 + 40;
      v15 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v15 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v15, v14);
  }
  v16 = (_QWORD *)apache::thrift::to_string<std::string>(Src);
  v17 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v18 = std::operator<<<std::char_traits<char>>(v17, "path_in_schema=");
  v19 = v16[2];
  if ( v16[3] >= 0x10u )
    v16 = (_QWORD *)*v16;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v18, v16, v19);
  if ( v84 >= 0x10 )
  {
    v20 = v84 + 1;
    v21 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v20 = v84 + 40;
      v21 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v21 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v21, v20);
  }
  v22 = (_QWORD *)parquet::format::to_string(Src);
  v23 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v24 = std::operator<<<std::char_traits<char>>(v23, "codec=");
  v25 = v22[2];
  if ( v22[3] >= 0x10u )
    v22 = (_QWORD *)*v22;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v24, v22, v25);
  if ( v84 >= 0x10 )
  {
    v26 = v84 + 1;
    v27 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v26 = v84 + 40;
      v27 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v27 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v27, v26);
  }
  v28 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v29 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v30 = std::operator<<<std::char_traits<char>>(v29, "num_values=");
  v31 = v28[2];
  if ( v28[3] >= 0x10u )
    v28 = (_QWORD *)*v28;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, v28, v31);
  if ( v84 >= 0x10 )
  {
    v32 = v84 + 1;
    v33 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v32 = v84 + 40;
      v33 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v33 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v33, v32);
  }
  v34 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v35 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v36 = std::operator<<<std::char_traits<char>>(v35, "total_uncompressed_size=");
  v37 = v34[2];
  if ( v34[3] >= 0x10u )
    v34 = (_QWORD *)*v34;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, v34, v37);
  if ( v84 >= 0x10 )
  {
    v38 = v84 + 1;
    v39 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v38 = v84 + 40;
      v39 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v39 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v39, v38);
  }
  v40 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v41 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v42 = std::operator<<<std::char_traits<char>>(v41, "total_compressed_size=");
  v43 = v40[2];
  if ( v40[3] >= 0x10u )
    v40 = (_QWORD *)*v40;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, v40, v43);
  if ( v84 >= 0x10 )
  {
    v44 = v84 + 1;
    v45 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v44 = v84 + 40;
      v45 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v45 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v45, v44);
  }
  v46 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v46, "key_value_metadata=");
  if ( (*(_BYTE *)(a1 + 368) & 1) != 0 )
  {
    v47 = (_QWORD *)apache::thrift::to_string<parquet::format::KeyValue>(Src);
    v4 = 1;
    v48 = v47[2];
    if ( v47[3] >= 0x10u )
      v47 = (_QWORD *)*v47;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v47, v48);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    if ( v84 >= 0x10 )
    {
      v49 = v84 + 1;
      v50 = (void *)Src[0];
      if ( v84 + 1 >= 0x1000 )
      {
        v49 = v84 + 40;
        v50 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v50 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v50, v49);
    }
  }
  v51 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v52 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v53 = std::operator<<<std::char_traits<char>>(v52, "data_page_offset=");
  v54 = v51[2];
  if ( v51[3] >= 0x10u )
    v51 = (_QWORD *)*v51;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v53, v51, v54);
  if ( v84 >= 0x10 )
  {
    v55 = v84 + 1;
    v56 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v55 = v84 + 40;
      v56 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v56 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v56, v55);
  }
  v57 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v57, "index_page_offset=");
  if ( (*(_BYTE *)(a1 + 368) & 2) != 0 )
  {
    v58 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
    v4 |= 2u;
    v59 = v58[2];
    if ( v58[3] >= 0x10u )
      v58 = (_QWORD *)*v58;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v58, v59);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v84 >= 0x10 )
    {
      v60 = v84 + 1;
      v61 = (void *)Src[0];
      if ( v84 + 1 >= 0x1000 )
      {
        v60 = v84 + 40;
        v61 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v61 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v61, v60);
    }
  }
  v62 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v62, "dictionary_page_offset=");
  if ( (*(_BYTE *)(a1 + 368) & 4) != 0 )
  {
    v63 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
    v4 |= 4u;
    v64 = v63[2];
    if ( v63[3] >= 0x10u )
      v63 = (_QWORD *)*v63;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v63, v64);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    if ( v84 >= 0x10 )
    {
      v65 = v84 + 1;
      v66 = (void *)Src[0];
      if ( v84 + 1 >= 0x1000 )
      {
        v65 = v84 + 40;
        v66 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v66 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v66, v65);
    }
  }
  v67 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v67, "statistics=");
  if ( (*(_BYTE *)(a1 + 368) & 8) != 0 )
  {
    v68 = (_QWORD *)apache::thrift::to_string<parquet::format::Statistics>(Src);
    v4 |= 8u;
    v69 = v68[2];
    if ( v68[3] >= 0x10u )
      v68 = (_QWORD *)*v68;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v68, v69);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 8) != 0 )
  {
    v4 &= ~8u;
    if ( v84 >= 0x10 )
    {
      v70 = v84 + 1;
      v71 = (void *)Src[0];
      if ( v84 + 1 >= 0x1000 )
      {
        v70 = v84 + 40;
        v71 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v71 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v71, v70);
    }
  }
  v72 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v72, "encoding_stats=");
  if ( (*(_BYTE *)(a1 + 368) & 0x10) != 0 )
  {
    v73 = (_QWORD *)apache::thrift::to_string<parquet::format::PageEncodingStats>(Src);
    v4 |= 0x10u;
    v74 = v73[2];
    if ( v73[3] >= 0x10u )
      v73 = (_QWORD *)*v73;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v73, v74);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x10) != 0 )
  {
    v4 &= ~0x10u;
    if ( v84 >= 0x10 )
    {
      v75 = v84 + 1;
      v76 = (void *)Src[0];
      if ( v84 + 1 >= 0x1000 )
      {
        v75 = v84 + 40;
        v76 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v76 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v76, v75);
    }
  }
  v77 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v77, "bloom_filter_offset=");
  if ( (*(_BYTE *)(a1 + 368) & 0x20) != 0 )
  {
    v78 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
    v4 |= 0x20u;
    v79 = v78[2];
    if ( v78[3] >= 0x10u )
      v78 = (_QWORD *)*v78;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v78, v79);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x20) != 0 && v84 >= 0x10 )
  {
    v80 = v84 + 1;
    v81 = (void *)Src[0];
    if ( v84 + 1 >= 0x1000 )
    {
      v80 = v84 + 40;
      v81 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v81 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v81, v80);
  }
  return std::operator<<<std::char_traits<char>>(a2, ")");
}

```

## disassembly

```asm
0x18006b790  mov     rax, rsp
0x18006b793  push    rbp
0x18006b794  push    rdi
0x18006b795  push    r14
0x18006b797  mov     rbp, rsp
0x18006b79a  sub     rsp, 60h
0x18006b79e  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18006b7a6  mov     [rax+18h], rbx
0x18006b7aa  mov     [rax+20h], rsi
0x18006b7ae  mov     rax, cs:__security_cookie
0x18006b7b5  xor     rax, rsp
0x18006b7b8  mov     [rbp+var_10], rax
0x18006b7bc  mov     rdi, rdx
0x18006b7bf  mov     rsi, rcx
0x18006b7c2  xor     ebx, ebx
0x18006b7c4  mov     [rbp+var_40], ebx
0x18006b7c7  lea     rdx, aColumnmetadata_0; "ColumnMetaData("
0x18006b7ce  mov     rcx, rdi
0x18006b7d1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b7d6  lea     rdx, [rsi+10h]
0x18006b7da  lea     rcx, [rbp+Src]; void *
0x18006b7de  call    ?to_string@format@parquet@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4type@Type@12@@Z; parquet::format::to_string(parquet::format::Type::type const &)
0x18006b7e3  mov     r14, rax
0x18006b7e6  lea     rdx, aType_2; "type="
0x18006b7ed  mov     rcx, rdi
0x18006b7f0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b7f5  mov     r8, [r14+10h]
0x18006b7f9  cmp     qword ptr [r14+18h], 10h
0x18006b7fe  jb      short loc_18006B803
0x18006b800  mov     r14, [r14]
0x18006b803  mov     rdx, r14
0x18006b806  mov     rcx, rax
0x18006b809  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b80e  nop
0x18006b80f  mov     rdx, [rbp+var_18]
0x18006b813  cmp     rdx, 10h
0x18006b817  jb      short loc_18006B84A
0x18006b819  inc     rdx
0x18006b81c  mov     rcx, [rbp+Src]
0x18006b820  mov     rax, rcx
0x18006b823  cmp     rdx, 1000h
0x18006b82a  jb      short loc_18006B845
0x18006b82c  add     rdx, 27h ; '''; unsigned __int64
0x18006b830  mov     rcx, [rcx-8]; void *
0x18006b834  sub     rax, rcx
0x18006b837  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b83b  cmp     rax, 1Fh
0x18006b83f  ja      loc_18006C021
0x18006b845  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b84a  lea     rdx, [rsi+18h]
0x18006b84e  lea     rcx, [rbp+Src]; void *
0x18006b852  call    ??$to_string@W4type@Encoding@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@W4type@Encoding@format@parquet@@V?$allocator@W4type@Encoding@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::Encoding::type>(std::vector<parquet::format::Encoding::type> const &)
0x18006b857  mov     r14, rax
0x18006b85a  lea     rdx, asc_18037DE74; ", "
0x18006b861  mov     rcx, rdi
0x18006b864  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b869  mov     rcx, rax
0x18006b86c  lea     rdx, aEncodings; "encodings="
0x18006b873  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b878  mov     r8, [r14+10h]
0x18006b87c  cmp     qword ptr [r14+18h], 10h
0x18006b881  jb      short loc_18006B886
0x18006b883  mov     r14, [r14]
0x18006b886  mov     rdx, r14
0x18006b889  mov     rcx, rax
0x18006b88c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b891  nop
0x18006b892  mov     rdx, [rbp+var_18]
0x18006b896  cmp     rdx, 10h
0x18006b89a  jb      short loc_18006B8CD
0x18006b89c  inc     rdx
0x18006b89f  mov     rcx, [rbp+Src]
0x18006b8a3  mov     rax, rcx
0x18006b8a6  cmp     rdx, 1000h
0x18006b8ad  jb      short loc_18006B8C8
0x18006b8af  add     rdx, 27h ; '''; unsigned __int64
0x18006b8b3  mov     rcx, [rcx-8]; void *
0x18006b8b7  sub     rax, rcx
0x18006b8ba  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b8be  cmp     rax, 1Fh
0x18006b8c2  ja      loc_18006C027
0x18006b8c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b8cd  lea     rdx, [rsi+30h]
0x18006b8d1  lea     rcx, [rbp+Src]; void *
0x18006b8d5  call    ??$to_string@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@3@@Z; apache::thrift::to_string<std::string>(std::vector<std::string> const &)
0x18006b8da  mov     r14, rax
0x18006b8dd  lea     rdx, asc_18037DE74; ", "
0x18006b8e4  mov     rcx, rdi
0x18006b8e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b8ec  mov     rcx, rax
0x18006b8ef  lea     rdx, aPathInSchema_0; "path_in_schema="
0x18006b8f6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b8fb  mov     r8, [r14+10h]
0x18006b8ff  cmp     qword ptr [r14+18h], 10h
0x18006b904  jb      short loc_18006B909
0x18006b906  mov     r14, [r14]
0x18006b909  mov     rdx, r14
0x18006b90c  mov     rcx, rax
0x18006b90f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b914  nop
0x18006b915  mov     rdx, [rbp+var_18]
0x18006b919  cmp     rdx, 10h
0x18006b91d  jb      short loc_18006B950
0x18006b91f  inc     rdx
0x18006b922  mov     rcx, [rbp+Src]
0x18006b926  mov     rax, rcx
0x18006b929  cmp     rdx, 1000h
0x18006b930  jb      short loc_18006B94B
0x18006b932  add     rdx, 27h ; '''; unsigned __int64
0x18006b936  mov     rcx, [rcx-8]; void *
0x18006b93a  sub     rax, rcx
0x18006b93d  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b941  cmp     rax, 1Fh
0x18006b945  ja      loc_18006C02D
0x18006b94b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b950  lea     rdx, [rsi+48h]
0x18006b954  lea     rcx, [rbp+Src]; void *
0x18006b958  call    ?to_string@format@parquet@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4type@CompressionCodec@12@@Z; parquet::format::to_string(parquet::format::CompressionCodec::type const &)
0x18006b95d  mov     r14, rax
0x18006b960  lea     rdx, asc_18037DE74; ", "
0x18006b967  mov     rcx, rdi
0x18006b96a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b96f  mov     rcx, rax
0x18006b972  lea     rdx, aCodec; "codec="
0x18006b979  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b97e  mov     r8, [r14+10h]
0x18006b982  cmp     qword ptr [r14+18h], 10h
0x18006b987  jb      short loc_18006B98C
0x18006b989  mov     r14, [r14]
0x18006b98c  mov     rdx, r14
0x18006b98f  mov     rcx, rax
0x18006b992  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b997  nop
0x18006b998  mov     rdx, [rbp+var_18]
0x18006b99c  cmp     rdx, 10h
0x18006b9a0  jb      short loc_18006B9D3
0x18006b9a2  inc     rdx
0x18006b9a5  mov     rcx, [rbp+Src]
0x18006b9a9  mov     rax, rcx
0x18006b9ac  cmp     rdx, 1000h
0x18006b9b3  jb      short loc_18006B9CE
0x18006b9b5  add     rdx, 27h ; '''; unsigned __int64
0x18006b9b9  mov     rcx, [rcx-8]; void *
0x18006b9bd  sub     rax, rcx
0x18006b9c0  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b9c4  cmp     rax, 1Fh
0x18006b9c8  ja      loc_18006C033
0x18006b9ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b9d3  lea     rdx, [rsi+50h]
0x18006b9d7  lea     rcx, [rbp+Src]; Src
0x18006b9db  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006b9e0  mov     r14, rax
0x18006b9e3  lea     rdx, asc_18037DE74; ", "
0x18006b9ea  mov     rcx, rdi
0x18006b9ed  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b9f2  mov     rcx, rax
0x18006b9f5  lea     rdx, aNumValues_0; "num_values="
0x18006b9fc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ba01  mov     r8, [r14+10h]
0x18006ba05  cmp     qword ptr [r14+18h], 10h
0x18006ba0a  jb      short loc_18006BA0F
0x18006ba0c  mov     r14, [r14]
0x18006ba0f  mov     rdx, r14
0x18006ba12  mov     rcx, rax
0x18006ba15  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ba1a  nop
0x18006ba1b  mov     rdx, [rbp+var_18]
0x18006ba1f  cmp     rdx, 10h
0x18006ba23  jb      short loc_18006BA56
0x18006ba25  inc     rdx
0x18006ba28  mov     rcx, [rbp+Src]
0x18006ba2c  mov     rax, rcx
0x18006ba2f  cmp     rdx, 1000h
0x18006ba36  jb      short loc_18006BA51
0x18006ba38  add     rdx, 27h ; '''; unsigned __int64
0x18006ba3c  mov     rcx, [rcx-8]; void *
0x18006ba40  sub     rax, rcx
0x18006ba43  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006ba47  cmp     rax, 1Fh
0x18006ba4b  ja      loc_18006C039
0x18006ba51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ba56  lea     rdx, [rsi+58h]
0x18006ba5a  lea     rcx, [rbp+Src]; Src
0x18006ba5e  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006ba63  mov     r14, rax
0x18006ba66  lea     rdx, asc_18037DE74; ", "
0x18006ba6d  mov     rcx, rdi
0x18006ba70  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ba75  mov     rcx, rax
0x18006ba78  lea     rdx, aTotalUncompres_0; "total_uncompressed_size="
0x18006ba7f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ba84  mov     r8, [r14+10h]
0x18006ba88  cmp     qword ptr [r14+18h], 10h
0x18006ba8d  jb      short loc_18006BA92
0x18006ba8f  mov     r14, [r14]
0x18006ba92  mov     rdx, r14
0x18006ba95  mov     rcx, rax
0x18006ba98  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ba9d  nop
0x18006ba9e  mov     rdx, [rbp+var_18]
0x18006baa2  cmp     rdx, 10h
0x18006baa6  jb      short loc_18006BAD9
0x18006baa8  inc     rdx
0x18006baab  mov     rcx, [rbp+Src]
0x18006baaf  mov     rax, rcx
0x18006bab2  cmp     rdx, 1000h
0x18006bab9  jb      short loc_18006BAD4
0x18006babb  add     rdx, 27h ; '''; unsigned __int64
0x18006babf  mov     rcx, [rcx-8]; void *
0x18006bac3  sub     rax, rcx
0x18006bac6  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006baca  cmp     rax, 1Fh
0x18006bace  ja      loc_18006C03F
0x18006bad4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006bad9  lea     rdx, [rsi+60h]
0x18006badd  lea     rcx, [rbp+Src]; Src
0x18006bae1  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006bae6  mov     r14, rax
0x18006bae9  lea     rdx, asc_18037DE74; ", "
0x18006baf0  mov     rcx, rdi
0x18006baf3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006baf8  mov     rcx, rax
0x18006bafb  lea     rdx, aTotalCompresse_0; "total_compressed_size="
0x18006bb02  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006bb07  mov     r8, [r14+10h]
0x18006bb0b  cmp     qword ptr [r14+18h], 10h
0x18006bb10  jb      short loc_18006BB15
0x18006bb12  mov     r14, [r14]
0x18006bb15  mov     rdx, r14
0x18006bb18  mov     rcx, rax
0x18006bb1b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006bb20  nop
0x18006bb21  mov     rdx, [rbp+var_18]
0x18006bb25  cmp     rdx, 10h
0x18006bb29  jb      short loc_18006BB5C
0x18006bb2b  inc     rdx
0x18006bb2e  mov     rcx, [rbp+Src]
0x18006bb32  mov     rax, rcx
0x18006bb35  cmp     rdx, 1000h
0x18006bb3c  jb      short loc_18006BB57
0x18006bb3e  add     rdx, 27h ; '''; unsigned __int64
0x18006bb42  mov     rcx, [rcx-8]; void *
0x18006bb46  sub     rax, rcx
0x18006bb49  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006bb4d  cmp     rax, 1Fh
0x18006bb51  ja      loc_18006C045
0x18006bb57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006bb5c  lea     rdx, asc_18037DE74; ", "
0x18006bb63  mov     rcx, rdi
0x18006bb66  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006bb6b  mov     rcx, rax
0x18006bb6e  lea     rdx, aKeyValueMetada_0; "key_value_metadata="
0x18006bb75  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006bb7a  test    byte ptr [rsi+170h], 1
0x18006bb81  jz      short loc_18006BBB4
0x18006bb83  lea     rdx, [rsi+68h]
0x18006bb87  lea     rcx, [rbp+Src]; void *
0x18006bb8b  call    ??$to_string@VKeyValue@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@VKeyValue@format@parquet@@V?$allocator@VKeyValue@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::KeyValue>(std::vector<parquet::format::KeyValue> const &)
0x18006bb90  nop
0x18006bb91  mov     ebx, 1
0x18006bb96  mov     [rbp+var_40], ebx
0x18006bb99  mov     r8, [rax+10h]
0x18006bb9d  cmp     qword ptr [rax+18h], 10h
0x18006bba2  jb      short loc_18006BBA7
0x18006bba4  mov     rax, [rax]
0x18006bba7  mov     rdx, rax
0x18006bbaa  mov     rcx, rdi
0x18006bbad  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006bbb2  jmp     short loc_18006BBC3
0x18006bbb4  lea     rdx, aNull_0; "<null>"
0x18006bbbb  mov     rcx, rdi
0x18006bbbe  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006bbc3  test    bl, 1
0x18006bbc6  jz      short loc_18006BC09
0x18006bbc8  and     ebx, 0FFFFFFFEh
0x18006bbcb  mov     [rbp+var_40], ebx
0x18006bbce  mov     rdx, [rbp+var_18]
0x18006bbd2  cmp     rdx, 10h
0x18006bbd6  jb      short loc_18006BC09
0x18006bbd8  inc     rdx
0x18006bbdb  mov     rcx, [rbp+Src]
0x18006bbdf  mov     rax, rcx
0x18006bbe2  cmp     rdx, 1000h
0x18006bbe9  jb      short loc_18006BC04
0x18006bbeb  add     rdx, 27h ; '''; unsigned __int64
0x18006bbef  mov     rcx, [rcx-8]; void *
0x18006bbf3  sub     rax, rcx
0x18006bbf6  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006bbfa  cmp     rax, 1Fh
0x18006bbfe  ja      loc_18006C04B
0x18006bc04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006bc09  lea     rdx, [rsi+80h]
0x18006bc10  lea     rcx, [rbp+Src]; Src
0x18006bc14  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006bc19  mov     r14, rax
0x18006bc1c  lea     rdx, asc_18037DE74; ", "
0x18006bc23  mov     rcx, rdi
0x18006bc26  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006bc2b  mov     rcx, rax
0x18006bc2e  lea     rdx, aDataPageOffset; "data_page_offset="
  ... truncated ...
```
