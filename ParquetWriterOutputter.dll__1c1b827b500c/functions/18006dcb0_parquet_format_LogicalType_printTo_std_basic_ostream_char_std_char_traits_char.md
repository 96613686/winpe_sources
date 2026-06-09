# parquet::format::LogicalType::printTo(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18006dcb0`
- end: `0x18006e638`
- name: `?printTo@LogicalType@format@parquet@@UEBAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `2440`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18005fd50`
- `0x180060de0`
- `0x180060f90`
- `0x180061800`
- `0x180061b60`
- `0x180061d10`
- `0x1800622d0`
- `0x180062630`
- `0x180062cf0`
- `0x180064090`
- `0x180064240`
- `0x1800645a0`
- `0x180064900`
- `0x18006dcb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18006e3c7`: `JSON=`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall parquet::format::LogicalType::printTo(__int64 a1, __int64 a2)
{
  __int16 v4; // bx
  _QWORD *v5; // rax
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  void *v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // rdx
  void *v28; // rcx
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  void *v33; // rcx
  __int64 v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // r8
  unsigned __int64 v37; // rdx
  void *v38; // rcx
  __int64 v39; // rax
  _QWORD *v40; // rax
  __int64 v41; // r8
  unsigned __int64 v42; // rdx
  void *v43; // rcx
  __int64 v44; // rax
  _QWORD *v45; // rax
  __int64 v46; // r8
  unsigned __int64 v47; // rdx
  void *v48; // rcx
  __int64 v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // r8
  unsigned __int64 v52; // rdx
  void *v53; // rcx
  __int64 v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // r8
  unsigned __int64 v57; // rdx
  void *v58; // rcx
  __int64 v59; // rax
  _QWORD *v60; // rax
  __int64 v61; // r8
  unsigned __int64 v62; // rdx
  void *v63; // rcx
  __int64 v64; // rax
  _QWORD *v65; // rax
  __int64 v66; // r8
  unsigned __int64 v67; // rdx
  void *v68; // rcx
  _QWORD Src[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v71; // [rsp+48h] [rbp-18h]

  v4 = 0;
  std::operator<<<std::char_traits<char>>(a2, "LogicalType(");
  std::operator<<<std::char_traits<char>>(a2, "STRING=");
  if ( (*(_BYTE *)(a1 + 736) & 1) != 0 )
  {
    v5 = (_QWORD *)apache::thrift::to_string<parquet::format::StringType>(Src);
    v4 = 1;
    v6 = v5[2];
    if ( v5[3] >= 0x10u )
      v5 = (_QWORD *)*v5;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v5, v6);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    if ( v71 >= 0x10 )
    {
      v7 = v71 + 1;
      v8 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v7 = v71 + 40;
        v8 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v8 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v8, v7);
    }
  }
  v9 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v9, "MAP=");
  if ( (*(_BYTE *)(a1 + 736) & 2) != 0 )
  {
    v10 = (_QWORD *)apache::thrift::to_string<parquet::format::MapType>(Src);
    v4 |= 2u;
    v11 = v10[2];
    if ( v10[3] >= 0x10u )
      v10 = (_QWORD *)*v10;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v10, v11);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v71 >= 0x10 )
    {
      v12 = v71 + 1;
      v13 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v12 = v71 + 40;
        v13 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v13 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13, v12);
    }
  }
  v14 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v14, "LIST=");
  if ( (*(_BYTE *)(a1 + 736) & 4) != 0 )
  {
    v15 = (_QWORD *)apache::thrift::to_string<parquet::format::ListType>(Src);
    v4 |= 4u;
    v16 = v15[2];
    if ( v15[3] >= 0x10u )
      v15 = (_QWORD *)*v15;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v15, v16);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    if ( v71 >= 0x10 )
    {
      v17 = v71 + 1;
      v18 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v17 = v71 + 40;
        v18 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v18 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v18, v17);
    }
  }
  v19 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v19, "ENUM=");
  if ( (*(_BYTE *)(a1 + 736) & 8) != 0 )
  {
    v20 = (_QWORD *)apache::thrift::to_string<parquet::format::EnumType>(Src);
    v4 |= 8u;
    v21 = v20[2];
    if ( v20[3] >= 0x10u )
      v20 = (_QWORD *)*v20;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v20, v21);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 8) != 0 )
  {
    v4 &= ~8u;
    if ( v71 >= 0x10 )
    {
      v22 = v71 + 1;
      v23 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v22 = v71 + 40;
        v23 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v23 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v23, v22);
    }
  }
  v24 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v24, "DECIMAL=");
  if ( (*(_BYTE *)(a1 + 736) & 0x10) != 0 )
  {
    v25 = (_QWORD *)apache::thrift::to_string<parquet::format::DecimalType>(Src);
    v4 |= 0x10u;
    v26 = v25[2];
    if ( v25[3] >= 0x10u )
      v25 = (_QWORD *)*v25;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v25, v26);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x10) != 0 )
  {
    v4 &= ~0x10u;
    if ( v71 >= 0x10 )
    {
      v27 = v71 + 1;
      v28 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v27 = v71 + 40;
        v28 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v28 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v28, v27);
    }
  }
  v29 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v29, "DATE=");
  if ( (*(_BYTE *)(a1 + 736) & 0x20) != 0 )
  {
    v30 = (_QWORD *)apache::thrift::to_string<parquet::format::DateType>(Src);
    v4 |= 0x20u;
    v31 = v30[2];
    if ( v30[3] >= 0x10u )
      v30 = (_QWORD *)*v30;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v30, v31);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x20) != 0 )
  {
    v4 &= ~0x20u;
    if ( v71 >= 0x10 )
    {
      v32 = v71 + 1;
      v33 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v32 = v71 + 40;
        v33 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v33 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v33, v32);
    }
  }
  v34 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v34, "TIME=");
  if ( (*(_BYTE *)(a1 + 736) & 0x40) != 0 )
  {
    v35 = (_QWORD *)apache::thrift::to_string<parquet::format::TimeType>(Src);
    v4 |= 0x40u;
    v36 = v35[2];
    if ( v35[3] >= 0x10u )
      v35 = (_QWORD *)*v35;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v35, v36);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x40) != 0 )
  {
    v4 &= ~0x40u;
    if ( v71 >= 0x10 )
    {
      v37 = v71 + 1;
      v38 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v37 = v71 + 40;
        v38 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v38 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v38, v37);
    }
  }
  v39 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v39, "TIMESTAMP=");
  if ( *(char *)(a1 + 736) >= 0 )
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  else
  {
    v40 = (_QWORD *)apache::thrift::to_string<parquet::format::TimestampType>(Src);
    v4 |= 0x80u;
    v41 = v40[2];
    if ( v40[3] >= 0x10u )
      v40 = (_QWORD *)*v40;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v40, v41);
  }
  if ( (v4 & 0x80u) != 0 )
  {
    v4 &= ~0x80u;
    if ( v71 >= 0x10 )
    {
      v42 = v71 + 1;
      v43 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v42 = v71 + 40;
        v43 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v43 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v43, v42);
    }
  }
  v44 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v44, "INTEGER=");
  if ( (*(_BYTE *)(a1 + 737) & 1) != 0 )
  {
    v45 = (_QWORD *)apache::thrift::to_string<parquet::format::IntType>(Src);
    v4 |= 0x100u;
    v46 = v45[2];
    if ( v45[3] >= 0x10u )
      v45 = (_QWORD *)*v45;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v45, v46);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x100) != 0 )
  {
    v4 &= ~0x100u;
    if ( v71 >= 0x10 )
    {
      v47 = v71 + 1;
      v48 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v47 = v71 + 40;
        v48 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v48 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v48, v47);
    }
  }
  v49 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v49, "UNKNOWN=");
  if ( (*(_BYTE *)(a1 + 737) & 2) != 0 )
  {
    v50 = (_QWORD *)apache::thrift::to_string<parquet::format::NullType>(Src);
    v4 |= 0x200u;
    v51 = v50[2];
    if ( v50[3] >= 0x10u )
      v50 = (_QWORD *)*v50;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v50, v51);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x200) != 0 )
  {
    v4 &= ~0x200u;
    if ( v71 >= 0x10 )
    {
      v52 = v71 + 1;
      v53 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v52 = v71 + 40;
        v53 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v53 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v53, v52);
    }
  }
  v54 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v54, "JSON=");
  if ( (*(_BYTE *)(a1 + 737) & 4) != 0 )
  {
    v55 = (_QWORD *)apache::thrift::to_string<parquet::format::JsonType>(Src);
    v4 |= 0x400u;
    v56 = v55[2];
    if ( v55[3] >= 0x10u )
      v55 = (_QWORD *)*v55;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v55, v56);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x400) != 0 )
  {
    v4 &= ~0x400u;
    if ( v71 >= 0x10 )
    {
      v57 = v71 + 1;
      v58 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v57 = v71 + 40;
        v58 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v58 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v58, v57);
    }
  }
  v59 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v59, "BSON=");
  if ( (*(_BYTE *)(a1 + 737) & 8) != 0 )
  {
    v60 = (_QWORD *)apache::thrift::to_string<parquet::format::BsonType>(Src);
    v4 |= 0x800u;
    v61 = v60[2];
    if ( v60[3] >= 0x10u )
      v60 = (_QWORD *)*v60;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v60, v61);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x800) != 0 )
  {
    v4 &= ~0x800u;
    if ( v71 >= 0x10 )
    {
      v62 = v71 + 1;
      v63 = (void *)Src[0];
      if ( v71 + 1 >= 0x1000 )
      {
        v62 = v71 + 40;
        v63 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v63 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v63, v62);
    }
  }
  v64 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v64, "UUID=");
  if ( (*(_BYTE *)(a1 + 737) & 0x10) != 0 )
  {
    v65 = (_QWORD *)apache::thrift::to_string<parquet::format::UUIDType>(Src);
    v4 |= 0x1000u;
    v66 = v65[2];
    if ( v65[3] >= 0x10u )
      v65 = (_QWORD *)*v65;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v65, v66);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x1000) != 0 && v71 >= 0x10 )
  {
    v67 = v71 + 1;
    v68 = (void *)Src[0];
    if ( v71 + 1 >= 0x1000 )
    {
      v67 = v71 + 40;
      v68 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v68 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v68, v67);
  }
  return std::operator<<<std::char_traits<char>>(a2, ")");
}

```

## disassembly

```asm
0x18006dcb0  push    rbp
0x18006dcb2  push    rsi
0x18006dcb3  push    rdi
0x18006dcb4  mov     rbp, rsp
0x18006dcb7  sub     rsp, 60h
0x18006dcbb  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18006dcc3  mov     [rsp+60h+arg_10], rbx
0x18006dccb  mov     rax, cs:__security_cookie
0x18006dcd2  xor     rax, rsp
0x18006dcd5  mov     [rbp+var_10], rax
0x18006dcd9  mov     rdi, rdx
0x18006dcdc  mov     rsi, rcx
0x18006dcdf  xor     ebx, ebx
0x18006dce1  mov     [rbp+var_40], ebx
0x18006dce4  lea     rdx, aLogicaltype_0; "LogicalType("
0x18006dceb  mov     rcx, rdi
0x18006dcee  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dcf3  lea     rdx, aString_3; "STRING="
0x18006dcfa  mov     rcx, rdi
0x18006dcfd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dd02  test    byte ptr [rsi+2E0h], 1
0x18006dd09  jz      short loc_18006DD3C
0x18006dd0b  lea     rdx, [rsi+10h]
0x18006dd0f  lea     rcx, [rbp+Src]; Src
0x18006dd13  call    ??$to_string@VStringType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVStringType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::StringType>(parquet::format::StringType const &)
0x18006dd18  nop
0x18006dd19  mov     ebx, 1
0x18006dd1e  mov     [rbp+var_40], ebx
0x18006dd21  mov     r8, [rax+10h]
0x18006dd25  cmp     qword ptr [rax+18h], 10h
0x18006dd2a  jb      short loc_18006DD2F
0x18006dd2c  mov     rax, [rax]
0x18006dd2f  mov     rdx, rax
0x18006dd32  mov     rcx, rdi
0x18006dd35  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006dd3a  jmp     short loc_18006DD4B
0x18006dd3c  lea     rdx, aNull_0; "<null>"
0x18006dd43  mov     rcx, rdi
0x18006dd46  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dd4b  test    bl, 1
0x18006dd4e  jz      short loc_18006DD91
0x18006dd50  and     ebx, 0FFFFFFFEh
0x18006dd53  mov     [rbp+var_40], ebx
0x18006dd56  mov     rdx, [rbp+var_18]
0x18006dd5a  cmp     rdx, 10h
0x18006dd5e  jb      short loc_18006DD91
0x18006dd60  inc     rdx
0x18006dd63  mov     rcx, [rbp+Src]
0x18006dd67  mov     rax, rcx
0x18006dd6a  cmp     rdx, 1000h
0x18006dd71  jb      short loc_18006DD8C
0x18006dd73  add     rdx, 27h ; '''; unsigned __int64
0x18006dd77  mov     rcx, [rcx-8]; void *
0x18006dd7b  sub     rax, rcx
0x18006dd7e  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006dd82  cmp     rax, 1Fh
0x18006dd86  ja      loc_18006E5F0
0x18006dd8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006dd91  lea     rdx, asc_18037DE74; ", "
0x18006dd98  mov     rcx, rdi
0x18006dd9b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dda0  mov     rcx, rax
0x18006dda3  lea     rdx, aMap; "MAP="
0x18006ddaa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ddaf  test    byte ptr [rsi+2E0h], 2
0x18006ddb6  jz      short loc_18006DDE7
0x18006ddb8  lea     rdx, [rsi+30h]
0x18006ddbc  lea     rcx, [rbp+Src]; Src
0x18006ddc0  call    ??$to_string@VMapType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVMapType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::MapType>(parquet::format::MapType const &)
0x18006ddc5  nop
0x18006ddc6  or      ebx, 2
0x18006ddc9  mov     [rbp+var_40], ebx
0x18006ddcc  mov     r8, [rax+10h]
0x18006ddd0  cmp     qword ptr [rax+18h], 10h
0x18006ddd5  jb      short loc_18006DDDA
0x18006ddd7  mov     rax, [rax]
0x18006ddda  mov     rdx, rax
0x18006dddd  mov     rcx, rdi
0x18006dde0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006dde5  jmp     short loc_18006DDF6
0x18006dde7  lea     rdx, aNull_0; "<null>"
0x18006ddee  mov     rcx, rdi
0x18006ddf1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ddf6  test    bl, 2
0x18006ddf9  jz      short loc_18006DE3D
0x18006ddfb  and     ebx, 0FFFFFFFDh
0x18006ddfe  mov     [rbp+var_40], ebx
0x18006de01  mov     rax, [rbp+var_18]
0x18006de05  cmp     rax, 10h
0x18006de09  jb      short loc_18006DE3D
0x18006de0b  lea     rdx, [rax+1]
0x18006de0f  mov     rcx, [rbp+Src]
0x18006de13  mov     rax, rcx
0x18006de16  cmp     rdx, 1000h
0x18006de1d  jb      short loc_18006DE38
0x18006de1f  add     rdx, 27h ; '''; unsigned __int64
0x18006de23  mov     rcx, [rcx-8]; void *
0x18006de27  sub     rax, rcx
0x18006de2a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006de2e  cmp     rax, 1Fh
0x18006de32  ja      loc_18006E5F6
0x18006de38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006de3d  lea     rdx, asc_18037DE74; ", "
0x18006de44  mov     rcx, rdi
0x18006de47  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006de4c  mov     rcx, rax
0x18006de4f  lea     rdx, aList_0; "LIST="
0x18006de56  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006de5b  test    byte ptr [rsi+2E0h], 4
0x18006de62  jz      short loc_18006DE93
0x18006de64  lea     rdx, [rsi+50h]
0x18006de68  lea     rcx, [rbp+Src]; Src
0x18006de6c  call    ??$to_string@VListType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVListType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::ListType>(parquet::format::ListType const &)
0x18006de71  nop
0x18006de72  or      ebx, 4
0x18006de75  mov     [rbp+var_40], ebx
0x18006de78  mov     r8, [rax+10h]
0x18006de7c  cmp     qword ptr [rax+18h], 10h
0x18006de81  jb      short loc_18006DE86
0x18006de83  mov     rax, [rax]
0x18006de86  mov     rdx, rax
0x18006de89  mov     rcx, rdi
0x18006de8c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006de91  jmp     short loc_18006DEA2
0x18006de93  lea     rdx, aNull_0; "<null>"
0x18006de9a  mov     rcx, rdi
0x18006de9d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dea2  test    bl, 4
0x18006dea5  jz      short loc_18006DEE9
0x18006dea7  and     ebx, 0FFFFFFFBh
0x18006deaa  mov     [rbp+var_40], ebx
0x18006dead  mov     rax, [rbp+var_18]
0x18006deb1  cmp     rax, 10h
0x18006deb5  jb      short loc_18006DEE9
0x18006deb7  lea     rdx, [rax+1]
0x18006debb  mov     rcx, [rbp+Src]
0x18006debf  mov     rax, rcx
0x18006dec2  cmp     rdx, 1000h
0x18006dec9  jb      short loc_18006DEE4
0x18006decb  add     rdx, 27h ; '''; unsigned __int64
0x18006decf  mov     rcx, [rcx-8]; void *
0x18006ded3  sub     rax, rcx
0x18006ded6  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006deda  cmp     rax, 1Fh
0x18006dede  ja      loc_18006E5FC
0x18006dee4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006dee9  lea     rdx, asc_18037DE74; ", "
0x18006def0  mov     rcx, rdi
0x18006def3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006def8  mov     rcx, rax
0x18006defb  lea     rdx, aEnum_2; "ENUM="
0x18006df02  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006df07  test    byte ptr [rsi+2E0h], 8
0x18006df0e  jz      short loc_18006DF3F
0x18006df10  lea     rdx, [rsi+70h]
0x18006df14  lea     rcx, [rbp+Src]; Src
0x18006df18  call    ??$to_string@VEnumType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVEnumType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::EnumType>(parquet::format::EnumType const &)
0x18006df1d  nop
0x18006df1e  or      ebx, 8
0x18006df21  mov     [rbp+var_40], ebx
0x18006df24  mov     r8, [rax+10h]
0x18006df28  cmp     qword ptr [rax+18h], 10h
0x18006df2d  jb      short loc_18006DF32
0x18006df2f  mov     rax, [rax]
0x18006df32  mov     rdx, rax
0x18006df35  mov     rcx, rdi
0x18006df38  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006df3d  jmp     short loc_18006DF4E
0x18006df3f  lea     rdx, aNull_0; "<null>"
0x18006df46  mov     rcx, rdi
0x18006df49  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006df4e  test    bl, 8
0x18006df51  jz      short loc_18006DF95
0x18006df53  and     ebx, 0FFFFFFF7h
0x18006df56  mov     [rbp+var_40], ebx
0x18006df59  mov     rax, [rbp+var_18]
0x18006df5d  cmp     rax, 10h
0x18006df61  jb      short loc_18006DF95
0x18006df63  lea     rdx, [rax+1]
0x18006df67  mov     rcx, [rbp+Src]
0x18006df6b  mov     rax, rcx
0x18006df6e  cmp     rdx, 1000h
0x18006df75  jb      short loc_18006DF90
0x18006df77  add     rdx, 27h ; '''; unsigned __int64
0x18006df7b  mov     rcx, [rcx-8]; void *
0x18006df7f  sub     rax, rcx
0x18006df82  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006df86  cmp     rax, 1Fh
0x18006df8a  ja      loc_18006E602
0x18006df90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006df95  lea     rdx, asc_18037DE74; ", "
0x18006df9c  mov     rcx, rdi
0x18006df9f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dfa4  mov     rcx, rax
0x18006dfa7  lea     rdx, aDecimal; "DECIMAL="
0x18006dfae  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dfb3  test    byte ptr [rsi+2E0h], 10h
0x18006dfba  jz      short loc_18006DFEE
0x18006dfbc  lea     rdx, [rsi+90h]
0x18006dfc3  lea     rcx, [rbp+Src]; Src
0x18006dfc7  call    ??$to_string@VDecimalType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVDecimalType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::DecimalType>(parquet::format::DecimalType const &)
0x18006dfcc  nop
0x18006dfcd  or      ebx, 10h
0x18006dfd0  mov     [rbp+var_40], ebx
0x18006dfd3  mov     r8, [rax+10h]
0x18006dfd7  cmp     qword ptr [rax+18h], 10h
0x18006dfdc  jb      short loc_18006DFE1
0x18006dfde  mov     rax, [rax]
0x18006dfe1  mov     rdx, rax
0x18006dfe4  mov     rcx, rdi
0x18006dfe7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006dfec  jmp     short loc_18006DFFD
0x18006dfee  lea     rdx, aNull_0; "<null>"
0x18006dff5  mov     rcx, rdi
0x18006dff8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006dffd  test    bl, 10h
0x18006e000  jz      short loc_18006E044
0x18006e002  and     ebx, 0FFFFFFEFh
0x18006e005  mov     [rbp+var_40], ebx
0x18006e008  mov     rax, [rbp+var_18]
0x18006e00c  cmp     rax, 10h
0x18006e010  jb      short loc_18006E044
0x18006e012  lea     rdx, [rax+1]
0x18006e016  mov     rcx, [rbp+Src]
0x18006e01a  mov     rax, rcx
0x18006e01d  cmp     rdx, 1000h
0x18006e024  jb      short loc_18006E03F
0x18006e026  add     rdx, 27h ; '''; unsigned __int64
0x18006e02a  mov     rcx, [rcx-8]; void *
0x18006e02e  sub     rax, rcx
0x18006e031  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006e035  cmp     rax, 1Fh
0x18006e039  ja      loc_18006E608
0x18006e03f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006e044  lea     rdx, asc_18037DE74; ", "
0x18006e04b  mov     rcx, rdi
0x18006e04e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e053  mov     rcx, rax
0x18006e056  lea     rdx, aDate_2; "DATE="
0x18006e05d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e062  test    byte ptr [rsi+2E0h], 20h
0x18006e069  jz      short loc_18006E09D
0x18006e06b  lea     rdx, [rsi+0B8h]
0x18006e072  lea     rcx, [rbp+Src]; Src
0x18006e076  call    ??$to_string@VDateType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVDateType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::DateType>(parquet::format::DateType const &)
0x18006e07b  nop
0x18006e07c  or      ebx, 20h
0x18006e07f  mov     [rbp+var_40], ebx
0x18006e082  mov     r8, [rax+10h]
0x18006e086  cmp     qword ptr [rax+18h], 10h
0x18006e08b  jb      short loc_18006E090
0x18006e08d  mov     rax, [rax]
0x18006e090  mov     rdx, rax
0x18006e093  mov     rcx, rdi
0x18006e096  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006e09b  jmp     short loc_18006E0AC
0x18006e09d  lea     rdx, aNull_0; "<null>"
0x18006e0a4  mov     rcx, rdi
0x18006e0a7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e0ac  test    bl, 20h
0x18006e0af  jz      short loc_18006E0F3
0x18006e0b1  and     ebx, 0FFFFFFDFh
0x18006e0b4  mov     [rbp+var_40], ebx
0x18006e0b7  mov     rax, [rbp+var_18]
0x18006e0bb  cmp     rax, 10h
0x18006e0bf  jb      short loc_18006E0F3
0x18006e0c1  lea     rdx, [rax+1]
0x18006e0c5  mov     rcx, [rbp+Src]
0x18006e0c9  mov     rax, rcx
0x18006e0cc  cmp     rdx, 1000h
0x18006e0d3  jb      short loc_18006E0EE
0x18006e0d5  add     rdx, 27h ; '''; unsigned __int64
0x18006e0d9  mov     rcx, [rcx-8]; void *
0x18006e0dd  sub     rax, rcx
0x18006e0e0  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006e0e4  cmp     rax, 1Fh
0x18006e0e8  ja      loc_18006E60E
0x18006e0ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006e0f3  lea     rdx, asc_18037DE74; ", "
0x18006e0fa  mov     rcx, rdi
0x18006e0fd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e102  mov     rcx, rax
0x18006e105  lea     rdx, aTime; "TIME="
0x18006e10c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006e111  test    byte ptr [rsi+2E0h], 40h
0x18006e118  jz      short loc_18006E14C
0x18006e11a  lea     rdx, [rsi+0D8h]
0x18006e121  lea     rcx, [rbp+Src]; Src
0x18006e125  call    ??$to_string@VTimeType@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVTimeType@format@parquet@@@Z; apache::thrift::to_string<parquet::format::TimeType>(parquet::format::TimeType const &)
0x18006e12a  nop
0x18006e12b  or      ebx, 40h
0x18006e12e  mov     [rbp+var_40], ebx
0x18006e131  mov     r8, [rax+10h]
0x18006e135  cmp     qword ptr [rax+18h], 10h
0x18006e13a  jb      short loc_18006E13F
0x18006e13c  mov     rax, [rax]
0x18006e13f  mov     rdx, rax
0x18006e142  mov     rcx, rdi
0x18006e145  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006e14a  jmp     short loc_18006E15B
  ... truncated ...
```
