# parquet::format::PageHeader::printTo(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18006e930`
- end: `0x18006eead`
- name: `?printTo@PageHeader@format@parquet@@UEBAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `1405`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18005e0b0`
- `0x180060a80`
- `0x180060c30`
- `0x180061140`
- `0x1800619b0`
- `0x18006e930`
- `0x180075ee0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18006ea0c`: `uncompressed_page_size=`
- `0x18006ea8f`: `compressed_page_size=`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall parquet::format::PageHeader::printTo(__int64 a1, __int64 a2)
{
  char v4; // bl
  _QWORD *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  void *v15; // rcx
  _QWORD *v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  void *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  void *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // r8
  unsigned __int64 v30; // rdx
  void *v31; // rcx
  __int64 v32; // rax
  _QWORD *v33; // rax
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  void *v36; // rcx
  __int64 v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // r8
  unsigned __int64 v40; // rdx
  void *v41; // rcx
  __int64 v42; // rax
  _QWORD *v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rdx
  void *v46; // rcx
  _QWORD Src[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v49; // [rsp+48h] [rbp-18h]

  v4 = 0;
  std::operator<<<std::char_traits<char>>(a2, "PageHeader(");
  v5 = (_QWORD *)parquet::format::to_string(Src);
  v6 = std::operator<<<std::char_traits<char>>(a2, "type=");
  v7 = v5[2];
  if ( v5[3] >= 0x10u )
    v5 = (_QWORD *)*v5;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v6, v5, v7);
  if ( v49 >= 0x10 )
  {
    v8 = v49 + 1;
    v9 = (void *)Src[0];
    if ( v49 + 1 >= 0x1000 )
    {
      v8 = v49 + 40;
      v9 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v9 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v9, v8);
  }
  v10 = (_QWORD *)apache::thrift::to_string<int>(Src);
  v11 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v12 = std::operator<<<std::char_traits<char>>(v11, "uncompressed_page_size=");
  v13 = v10[2];
  if ( v10[3] >= 0x10u )
    v10 = (_QWORD *)*v10;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, v10, v13);
  if ( v49 >= 0x10 )
  {
    v14 = v49 + 1;
    v15 = (void *)Src[0];
    if ( v49 + 1 >= 0x1000 )
    {
      v14 = v49 + 40;
      v15 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v15 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v15, v14);
  }
  v16 = (_QWORD *)apache::thrift::to_string<int>(Src);
  v17 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v18 = std::operator<<<std::char_traits<char>>(v17, "compressed_page_size=");
  v19 = v16[2];
  if ( v16[3] >= 0x10u )
    v16 = (_QWORD *)*v16;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v18, v16, v19);
  if ( v49 >= 0x10 )
  {
    v20 = v49 + 1;
    v21 = (void *)Src[0];
    if ( v49 + 1 >= 0x1000 )
    {
      v20 = v49 + 40;
      v21 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v21 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v21, v20);
  }
  v22 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v22, "crc=");
  if ( (*(_BYTE *)(a1 + 608) & 1) != 0 )
  {
    v23 = (_QWORD *)apache::thrift::to_string<int>(Src);
    v4 = 1;
    v24 = v23[2];
    if ( v23[3] >= 0x10u )
      v23 = (_QWORD *)*v23;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v23, v24);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    if ( v49 >= 0x10 )
    {
      v25 = v49 + 1;
      v26 = (void *)Src[0];
      if ( v49 + 1 >= 0x1000 )
      {
        v25 = v49 + 40;
        v26 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v26 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v26, v25);
    }
  }
  v27 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v27, "data_page_header=");
  if ( (*(_BYTE *)(a1 + 608) & 2) != 0 )
  {
    v28 = (_QWORD *)apache::thrift::to_string<parquet::format::DataPageHeader>(Src);
    v4 |= 2u;
    v29 = v28[2];
    if ( v28[3] >= 0x10u )
      v28 = (_QWORD *)*v28;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v28, v29);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v49 >= 0x10 )
    {
      v30 = v49 + 1;
      v31 = (void *)Src[0];
      if ( v49 + 1 >= 0x1000 )
      {
        v30 = v49 + 40;
        v31 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v31 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v31, v30);
    }
  }
  v32 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v32, "index_page_header=");
  if ( (*(_BYTE *)(a1 + 608) & 4) != 0 )
  {
    v33 = (_QWORD *)apache::thrift::to_string<parquet::format::IndexPageHeader>(Src);
    v4 |= 4u;
    v34 = v33[2];
    if ( v33[3] >= 0x10u )
      v33 = (_QWORD *)*v33;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v33, v34);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    if ( v49 >= 0x10 )
    {
      v35 = v49 + 1;
      v36 = (void *)Src[0];
      if ( v49 + 1 >= 0x1000 )
      {
        v35 = v49 + 40;
        v36 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v36 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v36, v35);
    }
  }
  v37 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v37, "dictionary_page_header=");
  if ( (*(_BYTE *)(a1 + 608) & 8) != 0 )
  {
    v38 = (_QWORD *)apache::thrift::to_string<parquet::format::DictionaryPageHeader>(Src);
    v4 |= 8u;
    v39 = v38[2];
    if ( v38[3] >= 0x10u )
      v38 = (_QWORD *)*v38;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v38, v39);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 8) != 0 )
  {
    v4 &= ~8u;
    if ( v49 >= 0x10 )
    {
      v40 = v49 + 1;
      v41 = (void *)Src[0];
      if ( v49 + 1 >= 0x1000 )
      {
        v40 = v49 + 40;
        v41 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v41 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v41, v40);
    }
  }
  v42 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v42, "data_page_header_v2=");
  if ( (*(_BYTE *)(a1 + 608) & 0x10) != 0 )
  {
    v43 = (_QWORD *)apache::thrift::to_string<parquet::format::DataPageHeaderV2>(Src);
    v4 |= 0x10u;
    v44 = v43[2];
    if ( v43[3] >= 0x10u )
      v43 = (_QWORD *)*v43;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v43, v44);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x10) != 0 && v49 >= 0x10 )
  {
    v45 = v49 + 1;
    v46 = (void *)Src[0];
    if ( v49 + 1 >= 0x1000 )
    {
      v45 = v49 + 40;
      v46 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v46 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v46, v45);
  }
  return std::operator<<<std::char_traits<char>>(a2, ")");
}

```

## disassembly

```asm
0x18006e930  mov     rax, rsp
0x18006e933  push    rbp
0x18006e934  push    rdi
0x18006e935  push    r14
0x18006e937  mov     rbp, rsp
0x18006e93a  sub     rsp, 60h
0x18006e93e  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18006e946  mov     [rax+18h], rbx
0x18006e94a  mov     [rax+20h], rsi
0x18006e94e  mov     rax, cs:__security_cookie
0x18006e955  xor     rax, rsp
0x18006e958  mov     [rbp+var_10], rax
0x18006e95c  mov     rdi, rdx
0x18006e95f  mov     r14, rcx
0x18006e962  xor     ebx, ebx
0x18006e964  mov     [rbp+var_40], ebx
0x18006e967  lea     rdx, aPageheader; "PageHeader("
0x18006e96e  mov     rcx, rdi
0x18006e971  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e976  lea     rdx, [r14+10h]
0x18006e97a  lea     rcx, [rbp+Src]; void *
0x18006e97e  call    ?to_string@format@parquet@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4type@PageType@12@@Z; parquet::format::to_string(parquet::format::PageType::type const &)
0x18006e983  mov     rsi, rax
0x18006e986  lea     rdx, aType_2; "type="
0x18006e98d  mov     rcx, rdi
0x18006e990  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e995  mov     r8, [rsi+10h]
0x18006e999  cmp     qword ptr [rsi+18h], 10h
0x18006e99e  jb      short loc_18006E9A3
0x18006e9a0  mov     rsi, [rsi]
0x18006e9a3  mov     rdx, rsi
0x18006e9a6  mov     rcx, rax
0x18006e9a9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006e9ae  nop
0x18006e9af  mov     rdx, [rbp+var_18]
0x18006e9b3  cmp     rdx, 10h
0x18006e9b7  jb      short loc_18006E9EA
0x18006e9b9  inc     rdx
0x18006e9bc  mov     rcx, [rbp+Src]
0x18006e9c0  mov     rax, rcx
0x18006e9c3  cmp     rdx, 1000h
0x18006e9ca  jb      short loc_18006E9E5
0x18006e9cc  add     rdx, 27h ; '''; unsigned __int64
0x18006e9d0  mov     rcx, [rcx-8]; void *
0x18006e9d4  sub     rax, rcx
0x18006e9d7  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006e9db  cmp     rax, 1Fh
0x18006e9df  ja      loc_18006EE83
0x18006e9e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006e9ea  lea     rdx, [r14+14h]
0x18006e9ee  lea     rcx, [rbp+Src]; Src
0x18006e9f2  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006e9f7  mov     rsi, rax
0x18006e9fa  lea     rdx, asc_18037DE74; ", "
0x18006ea01  mov     rcx, rdi
0x18006ea04  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ea09  mov     rcx, rax
0x18006ea0c  lea     rdx, aUncompressedPa; "uncompressed_page_size="
0x18006ea13  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ea18  mov     r8, [rsi+10h]
0x18006ea1c  cmp     qword ptr [rsi+18h], 10h
0x18006ea21  jb      short loc_18006EA26
0x18006ea23  mov     rsi, [rsi]
0x18006ea26  mov     rdx, rsi
0x18006ea29  mov     rcx, rax
0x18006ea2c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ea31  nop
0x18006ea32  mov     rdx, [rbp+var_18]
0x18006ea36  cmp     rdx, 10h
0x18006ea3a  jb      short loc_18006EA6D
0x18006ea3c  inc     rdx
0x18006ea3f  mov     rcx, [rbp+Src]
0x18006ea43  mov     rax, rcx
0x18006ea46  cmp     rdx, 1000h
0x18006ea4d  jb      short loc_18006EA68
0x18006ea4f  add     rdx, 27h ; '''; unsigned __int64
0x18006ea53  mov     rcx, [rcx-8]; void *
0x18006ea57  sub     rax, rcx
0x18006ea5a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006ea5e  cmp     rax, 1Fh
0x18006ea62  ja      loc_18006EE89
0x18006ea68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ea6d  lea     rdx, [r14+18h]
0x18006ea71  lea     rcx, [rbp+Src]; Src
0x18006ea75  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006ea7a  mov     rsi, rax
0x18006ea7d  lea     rdx, asc_18037DE74; ", "
0x18006ea84  mov     rcx, rdi
0x18006ea87  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ea8c  mov     rcx, rax
0x18006ea8f  lea     rdx, aCompressedPage_0; "compressed_page_size="
0x18006ea96  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ea9b  mov     r8, [rsi+10h]
0x18006ea9f  cmp     qword ptr [rsi+18h], 10h
0x18006eaa4  jb      short loc_18006EAA9
0x18006eaa6  mov     rsi, [rsi]
0x18006eaa9  mov     rdx, rsi
0x18006eaac  mov     rcx, rax
0x18006eaaf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006eab4  nop
0x18006eab5  mov     rdx, [rbp+var_18]
0x18006eab9  cmp     rdx, 10h
0x18006eabd  jb      short loc_18006EAF0
0x18006eabf  inc     rdx
0x18006eac2  mov     rcx, [rbp+Src]
0x18006eac6  mov     rax, rcx
0x18006eac9  cmp     rdx, 1000h
0x18006ead0  jb      short loc_18006EAEB
0x18006ead2  add     rdx, 27h ; '''; unsigned __int64
0x18006ead6  mov     rcx, [rcx-8]; void *
0x18006eada  sub     rax, rcx
0x18006eadd  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006eae1  cmp     rax, 1Fh
0x18006eae5  ja      loc_18006EE8F
0x18006eaeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006eaf0  lea     rdx, asc_18037DE74; ", "
0x18006eaf7  mov     rcx, rdi
0x18006eafa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006eaff  mov     rcx, rax
0x18006eb02  lea     rdx, aCrc; "crc="
0x18006eb09  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006eb0e  test    byte ptr [r14+260h], 1
0x18006eb16  jz      short loc_18006EB49
0x18006eb18  lea     rdx, [r14+1Ch]
0x18006eb1c  lea     rcx, [rbp+Src]; Src
0x18006eb20  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006eb25  nop
0x18006eb26  mov     ebx, 1
0x18006eb2b  mov     [rbp+var_40], ebx
0x18006eb2e  mov     r8, [rax+10h]
0x18006eb32  cmp     qword ptr [rax+18h], 10h
0x18006eb37  jb      short loc_18006EB3C
0x18006eb39  mov     rax, [rax]
0x18006eb3c  mov     rdx, rax
0x18006eb3f  mov     rcx, rdi
0x18006eb42  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006eb47  jmp     short loc_18006EB58
0x18006eb49  lea     rdx, aNull_0; "<null>"
0x18006eb50  mov     rcx, rdi
0x18006eb53  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006eb58  test    bl, 1
0x18006eb5b  jz      short loc_18006EB9E
0x18006eb5d  and     ebx, 0FFFFFFFEh
0x18006eb60  mov     [rbp+var_40], ebx
0x18006eb63  mov     rdx, [rbp+var_18]
0x18006eb67  cmp     rdx, 10h
0x18006eb6b  jb      short loc_18006EB9E
0x18006eb6d  inc     rdx
0x18006eb70  mov     rcx, [rbp+Src]
0x18006eb74  mov     rax, rcx
0x18006eb77  cmp     rdx, 1000h
0x18006eb7e  jb      short loc_18006EB99
0x18006eb80  add     rdx, 27h ; '''; unsigned __int64
0x18006eb84  mov     rcx, [rcx-8]; void *
0x18006eb88  sub     rax, rcx
0x18006eb8b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006eb8f  cmp     rax, 1Fh
0x18006eb93  ja      loc_18006EE95
0x18006eb99  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006eb9e  lea     rdx, asc_18037DE74; ", "
0x18006eba5  mov     rcx, rdi
0x18006eba8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ebad  mov     rcx, rax
0x18006ebb0  lea     rdx, aDataPageHeader; "data_page_header="
0x18006ebb7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ebbc  test    byte ptr [r14+260h], 2
0x18006ebc4  jz      short loc_18006EBF5
0x18006ebc6  lea     rdx, [r14+20h]
0x18006ebca  lea     rcx, [rbp+Src]; Src
0x18006ebce  call    ??$to_string@VDataPageHeader@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVDataPageHeader@format@parquet@@@Z; apache::thrift::to_string<parquet::format::DataPageHeader>(parquet::format::DataPageHeader const &)
0x18006ebd3  nop
0x18006ebd4  or      ebx, 2
0x18006ebd7  mov     [rbp+var_40], ebx
0x18006ebda  mov     r8, [rax+10h]
0x18006ebde  cmp     qword ptr [rax+18h], 10h
0x18006ebe3  jb      short loc_18006EBE8
0x18006ebe5  mov     rax, [rax]
0x18006ebe8  mov     rdx, rax
0x18006ebeb  mov     rcx, rdi
0x18006ebee  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ebf3  jmp     short loc_18006EC04
0x18006ebf5  lea     rdx, aNull_0; "<null>"
0x18006ebfc  mov     rcx, rdi
0x18006ebff  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ec04  test    bl, 2
0x18006ec07  jz      short loc_18006EC4A
0x18006ec09  and     ebx, 0FFFFFFFDh
0x18006ec0c  mov     [rbp+var_40], ebx
0x18006ec0f  mov     rdx, [rbp+var_18]
0x18006ec13  cmp     rdx, 10h
0x18006ec17  jb      short loc_18006EC4A
0x18006ec19  inc     rdx
0x18006ec1c  mov     rcx, [rbp+Src]
0x18006ec20  mov     rax, rcx
0x18006ec23  cmp     rdx, 1000h
0x18006ec2a  jb      short loc_18006EC45
0x18006ec2c  add     rdx, 27h ; '''; unsigned __int64
0x18006ec30  mov     rcx, [rcx-8]; void *
0x18006ec34  sub     rax, rcx
0x18006ec37  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006ec3b  cmp     rax, 1Fh
0x18006ec3f  ja      loc_18006EE9B
0x18006ec45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ec4a  lea     rdx, asc_18037DE74; ", "
0x18006ec51  mov     rcx, rdi
0x18006ec54  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ec59  mov     rcx, rax
0x18006ec5c  lea     rdx, aIndexPageHeade_0; "index_page_header="
0x18006ec63  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ec68  test    byte ptr [r14+260h], 4
0x18006ec70  jz      short loc_18006ECA4
0x18006ec72  lea     rdx, [r14+110h]
0x18006ec79  lea     rcx, [rbp+Src]; Src
0x18006ec7d  call    ??$to_string@VIndexPageHeader@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVIndexPageHeader@format@parquet@@@Z; apache::thrift::to_string<parquet::format::IndexPageHeader>(parquet::format::IndexPageHeader const &)
0x18006ec82  nop
0x18006ec83  or      ebx, 4
0x18006ec86  mov     [rbp+var_40], ebx
0x18006ec89  mov     r8, [rax+10h]
0x18006ec8d  cmp     qword ptr [rax+18h], 10h
0x18006ec92  jb      short loc_18006EC97
0x18006ec94  mov     rax, [rax]
0x18006ec97  mov     rdx, rax
0x18006ec9a  mov     rcx, rdi
0x18006ec9d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006eca2  jmp     short loc_18006ECB3
0x18006eca4  lea     rdx, aNull_0; "<null>"
0x18006ecab  mov     rcx, rdi
0x18006ecae  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ecb3  test    bl, 4
0x18006ecb6  jz      short loc_18006ECF9
0x18006ecb8  and     ebx, 0FFFFFFFBh
0x18006ecbb  mov     [rbp+var_40], ebx
0x18006ecbe  mov     rdx, [rbp+var_18]
0x18006ecc2  cmp     rdx, 10h
0x18006ecc6  jb      short loc_18006ECF9
0x18006ecc8  inc     rdx
0x18006eccb  mov     rcx, [rbp+Src]
0x18006eccf  mov     rax, rcx
0x18006ecd2  cmp     rdx, 1000h
0x18006ecd9  jb      short loc_18006ECF4
0x18006ecdb  add     rdx, 27h ; '''; unsigned __int64
0x18006ecdf  mov     rcx, [rcx-8]; void *
0x18006ece3  sub     rax, rcx
0x18006ece6  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006ecea  cmp     rax, 1Fh
0x18006ecee  ja      loc_18006EEA1
0x18006ecf4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ecf9  lea     rdx, asc_18037DE74; ", "
0x18006ed00  mov     rcx, rdi
0x18006ed03  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ed08  mov     rcx, rax
0x18006ed0b  lea     rdx, aDictionaryPage_2; "dictionary_page_header="
0x18006ed12  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ed17  test    byte ptr [r14+260h], 8
0x18006ed1f  jz      short loc_18006ED53
0x18006ed21  lea     rdx, [r14+130h]
0x18006ed28  lea     rcx, [rbp+Src]; Src
0x18006ed2c  call    ??$to_string@VDictionaryPageHeader@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVDictionaryPageHeader@format@parquet@@@Z; apache::thrift::to_string<parquet::format::DictionaryPageHeader>(parquet::format::DictionaryPageHeader const &)
0x18006ed31  nop
0x18006ed32  or      ebx, 8
0x18006ed35  mov     [rbp+var_40], ebx
0x18006ed38  mov     r8, [rax+10h]
0x18006ed3c  cmp     qword ptr [rax+18h], 10h
0x18006ed41  jb      short loc_18006ED46
0x18006ed43  mov     rax, [rax]
0x18006ed46  mov     rdx, rax
0x18006ed49  mov     rcx, rdi
0x18006ed4c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ed51  jmp     short loc_18006ED62
0x18006ed53  lea     rdx, aNull_0; "<null>"
0x18006ed5a  mov     rcx, rdi
0x18006ed5d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ed62  test    bl, 8
0x18006ed65  jz      short loc_18006EDA8
0x18006ed67  and     ebx, 0FFFFFFF7h
0x18006ed6a  mov     [rbp+var_40], ebx
0x18006ed6d  mov     rdx, [rbp+var_18]
0x18006ed71  cmp     rdx, 10h
0x18006ed75  jb      short loc_18006EDA8
0x18006ed77  inc     rdx
0x18006ed7a  mov     rcx, [rbp+Src]
0x18006ed7e  mov     rax, rcx
0x18006ed81  cmp     rdx, 1000h
0x18006ed88  jb      short loc_18006EDA3
0x18006ed8a  add     rdx, 27h ; '''; unsigned __int64
0x18006ed8e  mov     rcx, [rcx-8]; void *
0x18006ed92  sub     rax, rcx
0x18006ed95  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006ed99  cmp     rax, 1Fh
0x18006ed9d  ja      loc_18006EEA7
0x18006eda3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006eda8  lea     rdx, asc_18037DE74; ", "
0x18006edaf  mov     rcx, rdi
0x18006edb2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006edb7  mov     rcx, rax
0x18006edba  lea     rdx, aDataPageHeader_0; "data_page_header_v2="
0x18006edc1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006edc6  test    byte ptr [r14+260h], 10h
0x18006edce  jz      short loc_18006EE02
0x18006edd0  lea     rdx, [r14+160h]
  ... truncated ...
```
