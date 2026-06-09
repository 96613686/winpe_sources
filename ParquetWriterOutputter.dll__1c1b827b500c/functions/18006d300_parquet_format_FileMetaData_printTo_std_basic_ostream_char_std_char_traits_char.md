# parquet::format::FileMetaData::printTo(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18006d300`
- end: `0x18006d906`
- name: `?printTo@FileMetaData@format@parquet@@UEBAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `1542`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18005e0b0`
- `0x18005f730`
- `0x180060670`
- `0x1800612f0`
- `0x180061ec0`
- `0x1800632b0`
- `0x1800636c0`
- `0x180064d10`
- `0x18006d300`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18006d603`: `created_by=`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall parquet::format::FileMetaData::printTo(__int64 a1, __int64 a2)
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
  _QWORD *v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  void *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // r8
  unsigned __int64 v31; // rdx
  void *v32; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // r8
  unsigned __int64 v36; // rdx
  void *v37; // rcx
  __int64 v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // r8
  unsigned __int64 v41; // rdx
  void *v42; // rcx
  __int64 v43; // rax
  _QWORD *v44; // rax
  __int64 v45; // r8
  unsigned __int64 v46; // rdx
  void *v47; // rcx
  __int64 v48; // rax
  _QWORD *v49; // rax
  __int64 v50; // r8
  unsigned __int64 v51; // rdx
  void *v52; // rcx
  _QWORD Src[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v55; // [rsp+48h] [rbp-18h]

  v4 = 0;
  std::operator<<<std::char_traits<char>>(a2, "FileMetaData(");
  v5 = (_QWORD *)apache::thrift::to_string<int>(Src);
  v6 = std::operator<<<std::char_traits<char>>(a2, "version=");
  v7 = v5[2];
  if ( v5[3] >= 0x10u )
    v5 = (_QWORD *)*v5;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v6, v5, v7);
  if ( v55 >= 0x10 )
  {
    v8 = v55 + 1;
    v9 = (void *)Src[0];
    if ( v55 + 1 >= 0x1000 )
    {
      v8 = v55 + 40;
      v9 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v9 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v9, v8);
  }
  v10 = (_QWORD *)apache::thrift::to_string<parquet::format::SchemaElement>(Src);
  v11 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v12 = std::operator<<<std::char_traits<char>>(v11, "schema=");
  v13 = v10[2];
  if ( v10[3] >= 0x10u )
    v10 = (_QWORD *)*v10;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, v10, v13);
  if ( v55 >= 0x10 )
  {
    v14 = v55 + 1;
    v15 = (void *)Src[0];
    if ( v55 + 1 >= 0x1000 )
    {
      v14 = v55 + 40;
      v15 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v15 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v15, v14);
  }
  v16 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v17 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v18 = std::operator<<<std::char_traits<char>>(v17, "num_rows=");
  v19 = v16[2];
  if ( v16[3] >= 0x10u )
    v16 = (_QWORD *)*v16;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v18, v16, v19);
  if ( v55 >= 0x10 )
  {
    v20 = v55 + 1;
    v21 = (void *)Src[0];
    if ( v55 + 1 >= 0x1000 )
    {
      v20 = v55 + 40;
      v21 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v21 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v21, v20);
  }
  v22 = (_QWORD *)apache::thrift::to_string<parquet::format::RowGroup>(Src);
  v23 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v24 = std::operator<<<std::char_traits<char>>(v23, "row_groups=");
  v25 = v22[2];
  if ( v22[3] >= 0x10u )
    v22 = (_QWORD *)*v22;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v24, v22, v25);
  if ( v55 >= 0x10 )
  {
    v26 = v55 + 1;
    v27 = (void *)Src[0];
    if ( v55 + 1 >= 0x1000 )
    {
      v26 = v55 + 40;
      v27 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v27 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v27, v26);
  }
  v28 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v28, "key_value_metadata=");
  if ( (*(_BYTE *)(a1 + 440) & 1) != 0 )
  {
    v29 = (_QWORD *)apache::thrift::to_string<parquet::format::KeyValue>(Src);
    v4 = 1;
    v30 = v29[2];
    if ( v29[3] >= 0x10u )
      v29 = (_QWORD *)*v29;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v29, v30);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    if ( v55 >= 0x10 )
    {
      v31 = v55 + 1;
      v32 = (void *)Src[0];
      if ( v55 + 1 >= 0x1000 )
      {
        v31 = v55 + 40;
        v32 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v32 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v32, v31);
    }
  }
  v33 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v33, "created_by=");
  if ( (*(_BYTE *)(a1 + 440) & 2) != 0 )
  {
    v34 = (_QWORD *)apache::thrift::to_string<std::string>(Src, a1 + 104);
    v4 |= 2u;
    v35 = v34[2];
    if ( v34[3] >= 0x10u )
      v34 = (_QWORD *)*v34;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v34, v35);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v55 >= 0x10 )
    {
      v36 = v55 + 1;
      v37 = (void *)Src[0];
      if ( v55 + 1 >= 0x1000 )
      {
        v36 = v55 + 40;
        v37 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v37 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v37, v36);
    }
  }
  v38 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v38, "column_orders=");
  if ( (*(_BYTE *)(a1 + 440) & 4) != 0 )
  {
    v39 = (_QWORD *)apache::thrift::to_string<parquet::format::ColumnOrder>(Src);
    v4 |= 4u;
    v40 = v39[2];
    if ( v39[3] >= 0x10u )
      v39 = (_QWORD *)*v39;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v39, v40);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    if ( v55 >= 0x10 )
    {
      v41 = v55 + 1;
      v42 = (void *)Src[0];
      if ( v55 + 1 >= 0x1000 )
      {
        v41 = v55 + 40;
        v42 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v42 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v42, v41);
    }
  }
  v43 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v43, "encryption_algorithm=");
  if ( (*(_BYTE *)(a1 + 440) & 8) != 0 )
  {
    v44 = (_QWORD *)apache::thrift::to_string<parquet::format::EncryptionAlgorithm>(Src);
    v4 |= 8u;
    v45 = v44[2];
    if ( v44[3] >= 0x10u )
      v44 = (_QWORD *)*v44;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v44, v45);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 8) != 0 )
  {
    v4 &= ~8u;
    if ( v55 >= 0x10 )
    {
      v46 = v55 + 1;
      v47 = (void *)Src[0];
      if ( v55 + 1 >= 0x1000 )
      {
        v46 = v55 + 40;
        v47 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v47 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v47, v46);
    }
  }
  v48 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v48, "footer_signing_key_metadata=");
  if ( (*(_BYTE *)(a1 + 440) & 0x10) != 0 )
  {
    v49 = (_QWORD *)apache::thrift::to_string<std::string>(Src, a1 + 408);
    v4 |= 0x10u;
    v50 = v49[2];
    if ( v49[3] >= 0x10u )
      v49 = (_QWORD *)*v49;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v49, v50);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x10) != 0 && v55 >= 0x10 )
  {
    v51 = v55 + 1;
    v52 = (void *)Src[0];
    if ( v55 + 1 >= 0x1000 )
    {
      v51 = v55 + 40;
      v52 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v52 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v52, v51);
  }
  return std::operator<<<std::char_traits<char>>(a2, ")");
}

```

## disassembly

```asm
0x18006d300  mov     rax, rsp
0x18006d303  push    rbp
0x18006d304  push    rdi
0x18006d305  push    r14
0x18006d307  mov     rbp, rsp
0x18006d30a  sub     rsp, 60h
0x18006d30e  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18006d316  mov     [rax+18h], rbx
0x18006d31a  mov     [rax+20h], rsi
0x18006d31e  mov     rax, cs:__security_cookie
0x18006d325  xor     rax, rsp
0x18006d328  mov     [rbp+var_10], rax
0x18006d32c  mov     rdi, rdx
0x18006d32f  mov     r14, rcx
0x18006d332  xor     ebx, ebx
0x18006d334  mov     [rbp+var_40], ebx
0x18006d337  lea     rdx, aFilemetadata_0; "FileMetaData("
0x18006d33e  mov     rcx, rdi
0x18006d341  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d346  lea     rdx, [r14+10h]
0x18006d34a  lea     rcx, [rbp+Src]; Src
0x18006d34e  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006d353  mov     rsi, rax
0x18006d356  lea     rdx, aVersion; "version="
0x18006d35d  mov     rcx, rdi
0x18006d360  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d365  mov     r8, [rsi+10h]
0x18006d369  cmp     qword ptr [rsi+18h], 10h
0x18006d36e  jb      short loc_18006D373
0x18006d370  mov     rsi, [rsi]
0x18006d373  mov     rdx, rsi
0x18006d376  mov     rcx, rax
0x18006d379  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d37e  nop
0x18006d37f  mov     rdx, [rbp+var_18]
0x18006d383  cmp     rdx, 10h
0x18006d387  jb      short loc_18006D3BA
0x18006d389  inc     rdx
0x18006d38c  mov     rcx, [rbp+Src]
0x18006d390  mov     rax, rcx
0x18006d393  cmp     rdx, 1000h
0x18006d39a  jb      short loc_18006D3B5
0x18006d39c  add     rdx, 27h ; '''; unsigned __int64
0x18006d3a0  mov     rcx, [rcx-8]; void *
0x18006d3a4  sub     rax, rcx
0x18006d3a7  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d3ab  cmp     rax, 1Fh
0x18006d3af  ja      loc_18006D8D6
0x18006d3b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d3ba  lea     rdx, [r14+18h]
0x18006d3be  lea     rcx, [rbp+Src]; void *
0x18006d3c2  call    ??$to_string@VSchemaElement@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@VSchemaElement@format@parquet@@V?$allocator@VSchemaElement@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::SchemaElement>(std::vector<parquet::format::SchemaElement> const &)
0x18006d3c7  mov     rsi, rax
0x18006d3ca  lea     rdx, asc_18037DE74; ", "
0x18006d3d1  mov     rcx, rdi
0x18006d3d4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d3d9  mov     rcx, rax
0x18006d3dc  lea     rdx, aSchema_0; "schema="
0x18006d3e3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d3e8  mov     r8, [rsi+10h]
0x18006d3ec  cmp     qword ptr [rsi+18h], 10h
0x18006d3f1  jb      short loc_18006D3F6
0x18006d3f3  mov     rsi, [rsi]
0x18006d3f6  mov     rdx, rsi
0x18006d3f9  mov     rcx, rax
0x18006d3fc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d401  nop
0x18006d402  mov     rdx, [rbp+var_18]
0x18006d406  cmp     rdx, 10h
0x18006d40a  jb      short loc_18006D43D
0x18006d40c  inc     rdx
0x18006d40f  mov     rcx, [rbp+Src]
0x18006d413  mov     rax, rcx
0x18006d416  cmp     rdx, 1000h
0x18006d41d  jb      short loc_18006D438
0x18006d41f  add     rdx, 27h ; '''; unsigned __int64
0x18006d423  mov     rcx, [rcx-8]; void *
0x18006d427  sub     rax, rcx
0x18006d42a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d42e  cmp     rax, 1Fh
0x18006d432  ja      loc_18006D8DC
0x18006d438  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d43d  lea     rdx, [r14+30h]
0x18006d441  lea     rcx, [rbp+Src]; Src
0x18006d445  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006d44a  mov     rsi, rax
0x18006d44d  lea     rdx, asc_18037DE74; ", "
0x18006d454  mov     rcx, rdi
0x18006d457  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d45c  mov     rcx, rax
0x18006d45f  lea     rdx, aNumRows; "num_rows="
0x18006d466  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d46b  mov     r8, [rsi+10h]
0x18006d46f  cmp     qword ptr [rsi+18h], 10h
0x18006d474  jb      short loc_18006D479
0x18006d476  mov     rsi, [rsi]
0x18006d479  mov     rdx, rsi
0x18006d47c  mov     rcx, rax
0x18006d47f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d484  nop
0x18006d485  mov     rdx, [rbp+var_18]
0x18006d489  cmp     rdx, 10h
0x18006d48d  jb      short loc_18006D4C0
0x18006d48f  inc     rdx
0x18006d492  mov     rcx, [rbp+Src]
0x18006d496  mov     rax, rcx
0x18006d499  cmp     rdx, 1000h
0x18006d4a0  jb      short loc_18006D4BB
0x18006d4a2  add     rdx, 27h ; '''; unsigned __int64
0x18006d4a6  mov     rcx, [rcx-8]; void *
0x18006d4aa  sub     rax, rcx
0x18006d4ad  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d4b1  cmp     rax, 1Fh
0x18006d4b5  ja      loc_18006D8E2
0x18006d4bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d4c0  lea     rdx, [r14+38h]
0x18006d4c4  lea     rcx, [rbp+Src]; void *
0x18006d4c8  call    ??$to_string@VRowGroup@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@VRowGroup@format@parquet@@V?$allocator@VRowGroup@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::RowGroup>(std::vector<parquet::format::RowGroup> const &)
0x18006d4cd  mov     rsi, rax
0x18006d4d0  lea     rdx, asc_18037DE74; ", "
0x18006d4d7  mov     rcx, rdi
0x18006d4da  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d4df  mov     rcx, rax
0x18006d4e2  lea     rdx, aRowGroups; "row_groups="
0x18006d4e9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d4ee  mov     r8, [rsi+10h]
0x18006d4f2  cmp     qword ptr [rsi+18h], 10h
0x18006d4f7  jb      short loc_18006D4FC
0x18006d4f9  mov     rsi, [rsi]
0x18006d4fc  mov     rdx, rsi
0x18006d4ff  mov     rcx, rax
0x18006d502  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d507  nop
0x18006d508  mov     rdx, [rbp+var_18]
0x18006d50c  cmp     rdx, 10h
0x18006d510  jb      short loc_18006D543
0x18006d512  inc     rdx
0x18006d515  mov     rcx, [rbp+Src]
0x18006d519  mov     rax, rcx
0x18006d51c  cmp     rdx, 1000h
0x18006d523  jb      short loc_18006D53E
0x18006d525  add     rdx, 27h ; '''; unsigned __int64
0x18006d529  mov     rcx, [rcx-8]; void *
0x18006d52d  sub     rax, rcx
0x18006d530  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d534  cmp     rax, 1Fh
0x18006d538  ja      loc_18006D8E8
0x18006d53e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d543  lea     rdx, asc_18037DE74; ", "
0x18006d54a  mov     rcx, rdi
0x18006d54d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d552  mov     rcx, rax
0x18006d555  lea     rdx, aKeyValueMetada_0; "key_value_metadata="
0x18006d55c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d561  test    byte ptr [r14+1B8h], 1
0x18006d569  jz      short loc_18006D59C
0x18006d56b  lea     rdx, [r14+50h]
0x18006d56f  lea     rcx, [rbp+Src]; void *
0x18006d573  call    ??$to_string@VKeyValue@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@VKeyValue@format@parquet@@V?$allocator@VKeyValue@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::KeyValue>(std::vector<parquet::format::KeyValue> const &)
0x18006d578  nop
0x18006d579  mov     ebx, 1
0x18006d57e  mov     [rbp+var_40], ebx
0x18006d581  mov     r8, [rax+10h]
0x18006d585  cmp     qword ptr [rax+18h], 10h
0x18006d58a  jb      short loc_18006D58F
0x18006d58c  mov     rax, [rax]
0x18006d58f  mov     rdx, rax
0x18006d592  mov     rcx, rdi
0x18006d595  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d59a  jmp     short loc_18006D5AB
0x18006d59c  lea     rdx, aNull_0; "<null>"
0x18006d5a3  mov     rcx, rdi
0x18006d5a6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d5ab  test    bl, 1
0x18006d5ae  jz      short loc_18006D5F1
0x18006d5b0  and     ebx, 0FFFFFFFEh
0x18006d5b3  mov     [rbp+var_40], ebx
0x18006d5b6  mov     rdx, [rbp+var_18]
0x18006d5ba  cmp     rdx, 10h
0x18006d5be  jb      short loc_18006D5F1
0x18006d5c0  inc     rdx
0x18006d5c3  mov     rcx, [rbp+Src]
0x18006d5c7  mov     rax, rcx
0x18006d5ca  cmp     rdx, 1000h
0x18006d5d1  jb      short loc_18006D5EC
0x18006d5d3  add     rdx, 27h ; '''; unsigned __int64
0x18006d5d7  mov     rcx, [rcx-8]; void *
0x18006d5db  sub     rax, rcx
0x18006d5de  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d5e2  cmp     rax, 1Fh
0x18006d5e6  ja      loc_18006D8EE
0x18006d5ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d5f1  lea     rdx, asc_18037DE74; ", "
0x18006d5f8  mov     rcx, rdi
0x18006d5fb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d600  mov     rcx, rax
0x18006d603  lea     rdx, aCreatedBy_0; "created_by="
0x18006d60a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d60f  test    byte ptr [r14+1B8h], 2
0x18006d617  jz      short loc_18006D648
0x18006d619  lea     rdx, [r14+68h]
0x18006d61d  lea     rcx, [rbp+Src]
0x18006d621  call    ??$to_string@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@@Z; apache::thrift::to_string<std::string>(std::string const &)
0x18006d626  nop
0x18006d627  or      ebx, 2
0x18006d62a  mov     [rbp+var_40], ebx
0x18006d62d  mov     r8, [rax+10h]
0x18006d631  cmp     qword ptr [rax+18h], 10h
0x18006d636  jb      short loc_18006D63B
0x18006d638  mov     rax, [rax]
0x18006d63b  mov     rdx, rax
0x18006d63e  mov     rcx, rdi
0x18006d641  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d646  jmp     short loc_18006D657
0x18006d648  lea     rdx, aNull_0; "<null>"
0x18006d64f  mov     rcx, rdi
0x18006d652  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d657  test    bl, 2
0x18006d65a  jz      short loc_18006D69D
0x18006d65c  and     ebx, 0FFFFFFFDh
0x18006d65f  mov     [rbp+var_40], ebx
0x18006d662  mov     rdx, [rbp+var_18]
0x18006d666  cmp     rdx, 10h
0x18006d66a  jb      short loc_18006D69D
0x18006d66c  inc     rdx
0x18006d66f  mov     rcx, [rbp+Src]
0x18006d673  mov     rax, rcx
0x18006d676  cmp     rdx, 1000h
0x18006d67d  jb      short loc_18006D698
0x18006d67f  add     rdx, 27h ; '''; unsigned __int64
0x18006d683  mov     rcx, [rcx-8]; void *
0x18006d687  sub     rax, rcx
0x18006d68a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d68e  cmp     rax, 1Fh
0x18006d692  ja      loc_18006D8F4
0x18006d698  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d69d  lea     rdx, asc_18037DE74; ", "
0x18006d6a4  mov     rcx, rdi
0x18006d6a7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d6ac  mov     rcx, rax
0x18006d6af  lea     rdx, aColumnOrders; "column_orders="
0x18006d6b6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d6bb  test    byte ptr [r14+1B8h], 4
0x18006d6c3  jz      short loc_18006D6F7
0x18006d6c5  lea     rdx, [r14+88h]
0x18006d6cc  lea     rcx, [rbp+Src]; void *
0x18006d6d0  call    ??$to_string@VColumnOrder@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@VColumnOrder@format@parquet@@V?$allocator@VColumnOrder@format@parquet@@@std@@@3@@Z; apache::thrift::to_string<parquet::format::ColumnOrder>(std::vector<parquet::format::ColumnOrder> const &)
0x18006d6d5  nop
0x18006d6d6  or      ebx, 4
0x18006d6d9  mov     [rbp+var_40], ebx
0x18006d6dc  mov     r8, [rax+10h]
0x18006d6e0  cmp     qword ptr [rax+18h], 10h
0x18006d6e5  jb      short loc_18006D6EA
0x18006d6e7  mov     rax, [rax]
0x18006d6ea  mov     rdx, rax
0x18006d6ed  mov     rcx, rdi
0x18006d6f0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006d6f5  jmp     short loc_18006D706
0x18006d6f7  lea     rdx, aNull_0; "<null>"
0x18006d6fe  mov     rcx, rdi
0x18006d701  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d706  test    bl, 4
0x18006d709  jz      short loc_18006D74C
0x18006d70b  and     ebx, 0FFFFFFFBh
0x18006d70e  mov     [rbp+var_40], ebx
0x18006d711  mov     rdx, [rbp+var_18]
0x18006d715  cmp     rdx, 10h
0x18006d719  jb      short loc_18006D74C
0x18006d71b  inc     rdx
0x18006d71e  mov     rcx, [rbp+Src]
0x18006d722  mov     rax, rcx
0x18006d725  cmp     rdx, 1000h
0x18006d72c  jb      short loc_18006D747
0x18006d72e  add     rdx, 27h ; '''; unsigned __int64
0x18006d732  mov     rcx, [rcx-8]; void *
0x18006d736  sub     rax, rcx
0x18006d739  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006d73d  cmp     rax, 1Fh
0x18006d741  ja      loc_18006D8FA
0x18006d747  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d74c  lea     rdx, asc_18037DE74; ", "
0x18006d753  mov     rcx, rdi
0x18006d756  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d75b  mov     rcx, rax
0x18006d75e  lea     rdx, aEncryptionAlgo_0; "encryption_algorithm="
0x18006d765  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006d76a  test    byte ptr [r14+1B8h], 8
0x18006d772  jz      short loc_18006D7A6
0x18006d774  lea     rdx, [r14+0A0h]
0x18006d77b  lea     rcx, [rbp+Src]; Src
0x18006d77f  call    ??$to_string@VEncryptionAlgorithm@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVEncryptionAlgorithm@format@parquet@@@Z; apache::thrift::to_string<parquet::format::EncryptionAlgorithm>(parquet::format::EncryptionAlgorithm const &)
0x18006d784  nop
0x18006d785  or      ebx, 8
0x18006d788  mov     [rbp+var_40], ebx
0x18006d78b  mov     r8, [rax+10h]
0x18006d78f  cmp     qword ptr [rax+18h], 10h
0x18006d794  jb      short loc_18006D799
0x18006d796  mov     rax, [rax]
0x18006d799  mov     rdx, rax
0x18006d79c  mov     rcx, rdi
  ... truncated ...
```
