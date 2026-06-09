# parquet::format::ColumnChunk::printTo(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18006af30`
- end: `0x18006b5b2`
- name: `?printTo@ColumnChunk@format@parquet@@UEBAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `1666`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18005e0b0`
- `0x18005f730`
- `0x180060310`
- `0x1800604c0`
- `0x180064d10`
- `0x18006af30`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18006af76`: `file_path=`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall parquet::format::ColumnChunk::printTo(__int64 a1, __int64 a2)
{
  char v4; // bl
  _QWORD *v5; // rax
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  _QWORD *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  void *v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  void *v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r8
  unsigned __int64 v23; // rdx
  void *v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rax
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  void *v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // r8
  unsigned __int64 v33; // rdx
  void *v34; // rcx
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // r8
  unsigned __int64 v38; // rdx
  void *v39; // rcx
  __int64 v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // r8
  unsigned __int64 v43; // rdx
  void *v44; // rcx
  __int64 v45; // rax
  _QWORD *v46; // rax
  __int64 v47; // r8
  unsigned __int64 v48; // rdx
  void *v49; // rcx
  _QWORD Src[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v52; // [rsp+48h] [rbp-18h]

  v4 = 0;
  std::operator<<<std::char_traits<char>>(a2, "ColumnChunk(");
  std::operator<<<std::char_traits<char>>(a2, "file_path=");
  if ( (*(_BYTE *)(a1 + 680) & 1) != 0 )
  {
    v5 = (_QWORD *)apache::thrift::to_string<std::string>(Src, a1 + 16);
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
    if ( v52 >= 0x10 )
    {
      v7 = v52 + 1;
      v8 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v7 = v52 + 40;
        v8 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v8 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v8, v7);
    }
  }
  v9 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
  v10 = std::operator<<<std::char_traits<char>>(a2, ", ");
  v11 = std::operator<<<std::char_traits<char>>(v10, "file_offset=");
  v12 = v9[2];
  if ( v9[3] >= 0x10u )
    v9 = (_QWORD *)*v9;
  std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, v9, v12);
  if ( v52 >= 0x10 )
  {
    v13 = v52 + 1;
    v14 = (void *)Src[0];
    if ( v52 + 1 >= 0x1000 )
    {
      v13 = v52 + 40;
      v14 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v14 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v14, v13);
  }
  v15 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v15, "meta_data=");
  if ( (*(_BYTE *)(a1 + 680) & 2) != 0 )
  {
    v16 = (_QWORD *)apache::thrift::to_string<parquet::format::ColumnMetaData>(Src);
    v4 |= 2u;
    v17 = v16[2];
    if ( v16[3] >= 0x10u )
      v16 = (_QWORD *)*v16;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v16, v17);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v52 >= 0x10 )
    {
      v18 = v52 + 1;
      v19 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v18 = v52 + 40;
        v19 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v19 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v19, v18);
    }
  }
  v20 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v20, "offset_index_offset=");
  if ( (*(_BYTE *)(a1 + 680) & 4) != 0 )
  {
    v21 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
    v4 |= 4u;
    v22 = v21[2];
    if ( v21[3] >= 0x10u )
      v21 = (_QWORD *)*v21;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v21, v22);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    if ( v52 >= 0x10 )
    {
      v23 = v52 + 1;
      v24 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v23 = v52 + 40;
        v24 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v24 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v24, v23);
    }
  }
  v25 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v25, "offset_index_length=");
  if ( (*(_BYTE *)(a1 + 680) & 8) != 0 )
  {
    v26 = (_QWORD *)apache::thrift::to_string<int>(Src);
    v4 |= 8u;
    v27 = v26[2];
    if ( v26[3] >= 0x10u )
      v26 = (_QWORD *)*v26;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v26, v27);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 8) != 0 )
  {
    v4 &= ~8u;
    if ( v52 >= 0x10 )
    {
      v28 = v52 + 1;
      v29 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v28 = v52 + 40;
        v29 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v29 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v29, v28);
    }
  }
  v30 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v30, "column_index_offset=");
  if ( (*(_BYTE *)(a1 + 680) & 0x10) != 0 )
  {
    v31 = (_QWORD *)apache::thrift::to_string<__int64>(Src);
    v4 |= 0x10u;
    v32 = v31[2];
    if ( v31[3] >= 0x10u )
      v31 = (_QWORD *)*v31;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v31, v32);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x10) != 0 )
  {
    v4 &= ~0x10u;
    if ( v52 >= 0x10 )
    {
      v33 = v52 + 1;
      v34 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v33 = v52 + 40;
        v34 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v34 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v34, v33);
    }
  }
  v35 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v35, "column_index_length=");
  if ( (*(_BYTE *)(a1 + 680) & 0x20) != 0 )
  {
    v36 = (_QWORD *)apache::thrift::to_string<int>(Src);
    v4 |= 0x20u;
    v37 = v36[2];
    if ( v36[3] >= 0x10u )
      v36 = (_QWORD *)*v36;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v36, v37);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x20) != 0 )
  {
    v4 &= ~0x20u;
    if ( v52 >= 0x10 )
    {
      v38 = v52 + 1;
      v39 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v38 = v52 + 40;
        v39 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v39 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v39, v38);
    }
  }
  v40 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v40, "crypto_metadata=");
  if ( (*(_BYTE *)(a1 + 680) & 0x40) != 0 )
  {
    v41 = (_QWORD *)apache::thrift::to_string<parquet::format::ColumnCryptoMetaData>(Src);
    v4 |= 0x40u;
    v42 = v41[2];
    if ( v41[3] >= 0x10u )
      v41 = (_QWORD *)*v41;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v41, v42);
  }
  else
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  if ( (v4 & 0x40) != 0 )
  {
    v4 &= ~0x40u;
    if ( v52 >= 0x10 )
    {
      v43 = v52 + 1;
      v44 = (void *)Src[0];
      if ( v52 + 1 >= 0x1000 )
      {
        v43 = v52 + 40;
        v44 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v44 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v44, v43);
    }
  }
  v45 = std::operator<<<std::char_traits<char>>(a2, ", ");
  std::operator<<<std::char_traits<char>>(v45, "encrypted_column_metadata=");
  if ( *(char *)(a1 + 680) >= 0 )
  {
    std::operator<<<std::char_traits<char>>(a2, "<null>");
  }
  else
  {
    v46 = (_QWORD *)apache::thrift::to_string<std::string>(Src, a1 + 648);
    v4 |= 0x80u;
    v47 = v46[2];
    if ( v46[3] >= 0x10u )
      v46 = (_QWORD *)*v46;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(a2, v46, v47);
  }
  if ( v4 < 0 && v52 >= 0x10 )
  {
    v48 = v52 + 1;
    v49 = (void *)Src[0];
    if ( v52 + 1 >= 0x1000 )
    {
      v48 = v52 + 40;
      v49 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v49 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v49, v48);
  }
  return std::operator<<<std::char_traits<char>>(a2, ")");
}

```

## disassembly

```asm
0x18006af30  mov     rax, rsp
0x18006af33  push    rbp
0x18006af34  push    rdi
0x18006af35  push    r14
0x18006af37  mov     rbp, rsp
0x18006af3a  sub     rsp, 60h
0x18006af3e  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18006af46  mov     [rax+18h], rbx
0x18006af4a  mov     [rax+20h], rsi
0x18006af4e  mov     rax, cs:__security_cookie
0x18006af55  xor     rax, rsp
0x18006af58  mov     [rbp+var_10], rax
0x18006af5c  mov     rdi, rdx
0x18006af5f  mov     rsi, rcx
0x18006af62  xor     ebx, ebx
0x18006af64  mov     [rbp+var_40], ebx
0x18006af67  lea     rdx, aColumnchunk_0; "ColumnChunk("
0x18006af6e  mov     rcx, rdi
0x18006af71  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006af76  lea     rdx, aFilePath_0; "file_path="
0x18006af7d  mov     rcx, rdi
0x18006af80  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006af85  test    byte ptr [rsi+2A8h], 1
0x18006af8c  jz      short loc_18006AFBF
0x18006af8e  lea     rdx, [rsi+10h]
0x18006af92  lea     rcx, [rbp+Src]
0x18006af96  call    ??$to_string@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@@Z; apache::thrift::to_string<std::string>(std::string const &)
0x18006af9b  nop
0x18006af9c  mov     ebx, 1
0x18006afa1  mov     [rbp+var_40], ebx
0x18006afa4  mov     r8, [rax+10h]
0x18006afa8  cmp     qword ptr [rax+18h], 10h
0x18006afad  jb      short loc_18006AFB2
0x18006afaf  mov     rax, [rax]
0x18006afb2  mov     rdx, rax
0x18006afb5  mov     rcx, rdi
0x18006afb8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006afbd  jmp     short loc_18006AFCE
0x18006afbf  lea     rdx, aNull_0; "<null>"
0x18006afc6  mov     rcx, rdi
0x18006afc9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006afce  test    bl, 1
0x18006afd1  jz      short loc_18006B014
0x18006afd3  and     ebx, 0FFFFFFFEh
0x18006afd6  mov     [rbp+var_40], ebx
0x18006afd9  mov     rdx, [rbp+var_18]
0x18006afdd  cmp     rdx, 10h
0x18006afe1  jb      short loc_18006B014
0x18006afe3  inc     rdx
0x18006afe6  mov     rcx, [rbp+Src]
0x18006afea  mov     rax, rcx
0x18006afed  cmp     rdx, 1000h
0x18006aff4  jb      short loc_18006B00F
0x18006aff6  add     rdx, 27h ; '''; unsigned __int64
0x18006affa  mov     rcx, [rcx-8]; void *
0x18006affe  sub     rax, rcx
0x18006b001  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b005  cmp     rax, 1Fh
0x18006b009  ja      loc_18006B582
0x18006b00f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b014  lea     rdx, [rsi+30h]
0x18006b018  lea     rcx, [rbp+Src]; Src
0x18006b01c  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006b021  mov     r14, rax
0x18006b024  lea     rdx, asc_18037DE74; ", "
0x18006b02b  mov     rcx, rdi
0x18006b02e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b033  mov     rcx, rax
0x18006b036  lea     rdx, aFileOffset_0; "file_offset="
0x18006b03d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b042  mov     r8, [r14+10h]
0x18006b046  cmp     qword ptr [r14+18h], 10h
0x18006b04b  jb      short loc_18006B050
0x18006b04d  mov     r14, [r14]
0x18006b050  mov     rdx, r14
0x18006b053  mov     rcx, rax
0x18006b056  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b05b  nop
0x18006b05c  mov     rdx, [rbp+var_18]
0x18006b060  cmp     rdx, 10h
0x18006b064  jb      short loc_18006B097
0x18006b066  inc     rdx
0x18006b069  mov     rcx, [rbp+Src]
0x18006b06d  mov     rax, rcx
0x18006b070  cmp     rdx, 1000h
0x18006b077  jb      short loc_18006B092
0x18006b079  add     rdx, 27h ; '''; unsigned __int64
0x18006b07d  mov     rcx, [rcx-8]; void *
0x18006b081  sub     rax, rcx
0x18006b084  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b088  cmp     rax, 1Fh
0x18006b08c  ja      loc_18006B588
0x18006b092  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b097  lea     rdx, asc_18037DE74; ", "
0x18006b09e  mov     rcx, rdi
0x18006b0a1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b0a6  mov     rcx, rax
0x18006b0a9  lea     rdx, aMetaData_0; "meta_data="
0x18006b0b0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b0b5  test    byte ptr [rsi+2A8h], 2
0x18006b0bc  jz      short loc_18006B0ED
0x18006b0be  lea     rdx, [rsi+38h]
0x18006b0c2  lea     rcx, [rbp+Src]; Src
0x18006b0c6  call    ??$to_string@VColumnMetaData@format@parquet@@@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVColumnMetaData@format@parquet@@@Z; apache::thrift::to_string<parquet::format::ColumnMetaData>(parquet::format::ColumnMetaData const &)
0x18006b0cb  nop
0x18006b0cc  or      ebx, 2
0x18006b0cf  mov     [rbp+var_40], ebx
0x18006b0d2  mov     r8, [rax+10h]
0x18006b0d6  cmp     qword ptr [rax+18h], 10h
0x18006b0db  jb      short loc_18006B0E0
0x18006b0dd  mov     rax, [rax]
0x18006b0e0  mov     rdx, rax
0x18006b0e3  mov     rcx, rdi
0x18006b0e6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b0eb  jmp     short loc_18006B0FC
0x18006b0ed  lea     rdx, aNull_0; "<null>"
0x18006b0f4  mov     rcx, rdi
0x18006b0f7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b0fc  test    bl, 2
0x18006b0ff  jz      short loc_18006B142
0x18006b101  and     ebx, 0FFFFFFFDh
0x18006b104  mov     [rbp+var_40], ebx
0x18006b107  mov     rdx, [rbp+var_18]
0x18006b10b  cmp     rdx, 10h
0x18006b10f  jb      short loc_18006B142
0x18006b111  inc     rdx
0x18006b114  mov     rcx, [rbp+Src]
0x18006b118  mov     rax, rcx
0x18006b11b  cmp     rdx, 1000h
0x18006b122  jb      short loc_18006B13D
0x18006b124  add     rdx, 27h ; '''; unsigned __int64
0x18006b128  mov     rcx, [rcx-8]; void *
0x18006b12c  sub     rax, rcx
0x18006b12f  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b133  cmp     rax, 1Fh
0x18006b137  ja      loc_18006B58E
0x18006b13d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b142  lea     rdx, asc_18037DE74; ", "
0x18006b149  mov     rcx, rdi
0x18006b14c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b151  mov     rcx, rax
0x18006b154  lea     rdx, aOffsetIndexOff; "offset_index_offset="
0x18006b15b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b160  test    byte ptr [rsi+2A8h], 4
0x18006b167  jz      short loc_18006B19B
0x18006b169  lea     rdx, [rsi+1C0h]
0x18006b170  lea     rcx, [rbp+Src]; Src
0x18006b174  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006b179  nop
0x18006b17a  or      ebx, 4
0x18006b17d  mov     [rbp+var_40], ebx
0x18006b180  mov     r8, [rax+10h]
0x18006b184  cmp     qword ptr [rax+18h], 10h
0x18006b189  jb      short loc_18006B18E
0x18006b18b  mov     rax, [rax]
0x18006b18e  mov     rdx, rax
0x18006b191  mov     rcx, rdi
0x18006b194  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b199  jmp     short loc_18006B1AA
0x18006b19b  lea     rdx, aNull_0; "<null>"
0x18006b1a2  mov     rcx, rdi
0x18006b1a5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b1aa  test    bl, 4
0x18006b1ad  jz      short loc_18006B1F0
0x18006b1af  and     ebx, 0FFFFFFFBh
0x18006b1b2  mov     [rbp+var_40], ebx
0x18006b1b5  mov     rdx, [rbp+var_18]
0x18006b1b9  cmp     rdx, 10h
0x18006b1bd  jb      short loc_18006B1F0
0x18006b1bf  inc     rdx
0x18006b1c2  mov     rcx, [rbp+Src]
0x18006b1c6  mov     rax, rcx
0x18006b1c9  cmp     rdx, 1000h
0x18006b1d0  jb      short loc_18006B1EB
0x18006b1d2  add     rdx, 27h ; '''; unsigned __int64
0x18006b1d6  mov     rcx, [rcx-8]; void *
0x18006b1da  sub     rax, rcx
0x18006b1dd  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b1e1  cmp     rax, 1Fh
0x18006b1e5  ja      loc_18006B594
0x18006b1eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b1f0  lea     rdx, asc_18037DE74; ", "
0x18006b1f7  mov     rcx, rdi
0x18006b1fa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b1ff  mov     rcx, rax
0x18006b202  lea     rdx, aOffsetIndexLen_0; "offset_index_length="
0x18006b209  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b20e  test    byte ptr [rsi+2A8h], 8
0x18006b215  jz      short loc_18006B249
0x18006b217  lea     rdx, [rsi+1C8h]
0x18006b21e  lea     rcx, [rbp+Src]; Src
0x18006b222  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006b227  nop
0x18006b228  or      ebx, 8
0x18006b22b  mov     [rbp+var_40], ebx
0x18006b22e  mov     r8, [rax+10h]
0x18006b232  cmp     qword ptr [rax+18h], 10h
0x18006b237  jb      short loc_18006B23C
0x18006b239  mov     rax, [rax]
0x18006b23c  mov     rdx, rax
0x18006b23f  mov     rcx, rdi
0x18006b242  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b247  jmp     short loc_18006B258
0x18006b249  lea     rdx, aNull_0; "<null>"
0x18006b250  mov     rcx, rdi
0x18006b253  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b258  test    bl, 8
0x18006b25b  jz      short loc_18006B29E
0x18006b25d  and     ebx, 0FFFFFFF7h
0x18006b260  mov     [rbp+var_40], ebx
0x18006b263  mov     rdx, [rbp+var_18]
0x18006b267  cmp     rdx, 10h
0x18006b26b  jb      short loc_18006B29E
0x18006b26d  inc     rdx
0x18006b270  mov     rcx, [rbp+Src]
0x18006b274  mov     rax, rcx
0x18006b277  cmp     rdx, 1000h
0x18006b27e  jb      short loc_18006B299
0x18006b280  add     rdx, 27h ; '''; unsigned __int64
0x18006b284  mov     rcx, [rcx-8]; void *
0x18006b288  sub     rax, rcx
0x18006b28b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b28f  cmp     rax, 1Fh
0x18006b293  ja      loc_18006B59A
0x18006b299  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b29e  lea     rdx, asc_18037DE74; ", "
0x18006b2a5  mov     rcx, rdi
0x18006b2a8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b2ad  mov     rcx, rax
0x18006b2b0  lea     rdx, aColumnIndexOff_0; "column_index_offset="
0x18006b2b7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b2bc  test    byte ptr [rsi+2A8h], 10h
0x18006b2c3  jz      short loc_18006B2F7
0x18006b2c5  lea     rdx, [rsi+1D0h]
0x18006b2cc  lea     rcx, [rbp+Src]; Src
0x18006b2d0  call    ??$to_string@_J@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_J@Z; apache::thrift::to_string<__int64>(__int64 const &)
0x18006b2d5  nop
0x18006b2d6  or      ebx, 10h
0x18006b2d9  mov     [rbp+var_40], ebx
0x18006b2dc  mov     r8, [rax+10h]
0x18006b2e0  cmp     qword ptr [rax+18h], 10h
0x18006b2e5  jb      short loc_18006B2EA
0x18006b2e7  mov     rax, [rax]
0x18006b2ea  mov     rdx, rax
0x18006b2ed  mov     rcx, rdi
0x18006b2f0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b2f5  jmp     short loc_18006B306
0x18006b2f7  lea     rdx, aNull_0; "<null>"
0x18006b2fe  mov     rcx, rdi
0x18006b301  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b306  test    bl, 10h
0x18006b309  jz      short loc_18006B34C
0x18006b30b  and     ebx, 0FFFFFFEFh
0x18006b30e  mov     [rbp+var_40], ebx
0x18006b311  mov     rdx, [rbp+var_18]
0x18006b315  cmp     rdx, 10h
0x18006b319  jb      short loc_18006B34C
0x18006b31b  inc     rdx
0x18006b31e  mov     rcx, [rbp+Src]
0x18006b322  mov     rax, rcx
0x18006b325  cmp     rdx, 1000h
0x18006b32c  jb      short loc_18006B347
0x18006b32e  add     rdx, 27h ; '''; unsigned __int64
0x18006b332  mov     rcx, [rcx-8]; void *
0x18006b336  sub     rax, rcx
0x18006b339  add     rax, 0FFFFFFFFFFFFFFF8h
0x18006b33d  cmp     rax, 1Fh
0x18006b341  ja      loc_18006B5A0
0x18006b347  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b34c  lea     rdx, asc_18037DE74; ", "
0x18006b353  mov     rcx, rdi
0x18006b356  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b35b  mov     rcx, rax
0x18006b35e  lea     rdx, aColumnIndexLen; "column_index_length="
0x18006b365  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b36a  test    byte ptr [rsi+2A8h], 20h
0x18006b371  jz      short loc_18006B3A5
0x18006b373  lea     rdx, [rsi+1D8h]
0x18006b37a  lea     rcx, [rbp+Src]; Src
0x18006b37e  call    ??$to_string@H@thrift@apache@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBH@Z; apache::thrift::to_string<int>(int const &)
0x18006b383  nop
0x18006b384  or      ebx, 20h
0x18006b387  mov     [rbp+var_40], ebx
0x18006b38a  mov     r8, [rax+10h]
0x18006b38e  cmp     qword ptr [rax+18h], 10h
0x18006b393  jb      short loc_18006B398
0x18006b395  mov     rax, [rax]
0x18006b398  mov     rdx, rax
0x18006b39b  mov     rcx, rdi
0x18006b39e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006b3a3  jmp     short loc_18006B3B4
0x18006b3a5  lea     rdx, aNull_0; "<null>"
0x18006b3ac  mov     rcx, rdi
0x18006b3af  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006b3b4  test    bl, 20h
0x18006b3b7  jz      short loc_18006B3FA
0x18006b3b9  and     ebx, 0FFFFFFDFh
0x18006b3bc  mov     [rbp+var_40], ebx
0x18006b3bf  mov     rdx, [rbp+var_18]
0x18006b3c3  cmp     rdx, 10h
  ... truncated ...
```
