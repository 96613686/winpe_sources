# ParquetWriterOutputter::SetupOutputStreamWriter(void)

- ea: `0x180016560`
- end: `0x180016ac4`
- name: `?SetupOutputStreamWriter@ParquetWriterOutputter@@AEAAXXZ`
- size: `1380`
- prototype: `void __fastcall(ParquetWriterOutputter *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180018bf0`

## callees

- `0x18000f550`
- `0x180010640`
- `0x180010860`
- `0x180010b10`
- `0x180012430`
- `0x180012920`
- `0x180012df0`
- `0x180016560`
- `0x180019b70`
- `0x180019f90`
- `0x18001b0a0`
- `0x18001b0c0`
- `0x18001b100`
- `0x18001eb10`
- `0x180021790`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c190`
- `0x18030c3f0`
- `0x18032b080`
- `0x18032b170`
- `0x180334640`

## string_xrefs

- `0x180016a74`: `Unsupported parquet compression type: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ParquetWriterOutputter::SetupOutputStreamWriter(ParquetWriterOutputter *this)
{
  int v2; // r8d
  unsigned int v3; // ebx
  _BYTE *v4; // r9
  size_t v5; // r8
  __int64 v6; // rax
  _QWORD *v7; // rax
  size_t v8; // r8
  unsigned __int64 v9; // rdx
  _BYTE *v10; // rcx
  unsigned __int64 v11; // rdx
  void *v12; // rcx
  unsigned __int64 v13; // rdx
  void *v14; // rcx
  unsigned __int64 v15; // rdx
  void *v16; // rcx
  std::_Ref_count_base *v17; // rdi
  volatile signed __int32 *v18; // rcx
  __int64 v19; // rbx
  _QWORD *v20; // rax
  parquet::ParquetFileWriter **v21; // rax
  parquet::ParquetFileWriter **v22; // rsi
  parquet::ParquetFileWriter *v23; // rdx
  parquet::ParquetFileWriter *v24; // rbx
  parquet::ParquetFileWriter *v25; // rbx
  parquet::ParquetFileWriter *v26; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base *v28[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+78h] [rbp-90h] BYREF
  __m128i v31; // [rsp+88h] [rbp-80h]
  _QWORD Src[2]; // [rsp+98h] [rbp-70h] BYREF
  __m128i v33; // [rsp+A8h] [rbp-60h]
  _QWORD v34[2]; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-40h]
  _QWORD *v36; // [rsp+D8h] [rbp-30h]
  __int128 v37; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v38; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE *v39; // [rsp+108h] [rbp+0h] BYREF
  __m128i v40; // [rsp+118h] [rbp+10h]
  __int64 v41; // [rsp+128h] [rbp+20h]
  __int128 *v42; // [rsp+130h] [rbp+28h]
  __int128 *v43; // [rsp+138h] [rbp+30h]
  std::_Ref_count_base **v44; // [rsp+140h] [rbp+38h]
  _BYTE pExceptionObject[32]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v46[60]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v47[3]; // [rsp+34Dh] [rbp+245h] BYREF

  v41 = -2;
  _CheckForDebuggerJustMyCode(&byte_1804EA0FE);
  memset(v46, 0, 0x1C8u);
  parquet::WriterProperties::Builder::Builder((parquet::WriterProperties::Builder *)v46);
  v46[1] = this;
  v2 = *(_DWORD *)(*((_QWORD *)this + 3) + 148LL);
  v3 = 2;
  switch ( v2 )
  {
    case 0:
      HIDWORD(v46[13]) = 0;
      break;
    case 1:
      HIDWORD(v46[13]) = 1;
      break;
    case 2:
      HIDWORD(v46[13]) = 2;
      break;
    case 3:
      HIDWORD(v46[13]) = 7;
      break;
    case 4:
      HIDWORD(v46[13]) = 3;
      break;
    case 5:
      HIDWORD(v46[13]) = 5;
      break;
    case 6:
      HIDWORD(v46[13]) = 4;
      break;
    default:
      std::exception::exception((std::exception *)pExceptionObject, "Unsupported parquet compression type: %d", v2);
      throw (std::exception *)pExceptionObject;
  }
  v27 = 0u;
  LODWORD(v46[6]) = 0;
  LOBYTE(v46[14]) = 1;
  v46[5] = ParquetWriterConfig::GetDataPageSize(*((ParquetWriterConfig **)this + 18));
  v46[2] = ParquetWriterConfig::GetDictionaryPageSizeLimit(*((ParquetWriterConfig **)this + 18));
  v46[3] = ParquetWriterConfig::GetMaxRowCountInColumnChunkBuffer(*((ParquetWriterConfig **)this + 18));
  v4 = v47;
  do
  {
    *--v4 = v3 % 0xA + 48;
    v3 /= 0xAu;
  }
  while ( v3 );
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v34[0]) = 0;
  if ( v4 != v47 )
    std::string::assign(v34, v4, v47 - v4);
  v33 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(Src[0]) = 0;
  std::string::assign(Src, "parquet-cpp version 1.5.1-SNAPSHOT", 0x22u);
  v5 = -1;
  do
    ++v5;
  while ( ParquetWriterOutputter::ParquetCreatorSuffix[v5] );
  v6 = std::string::append(Src, (void *)"-MicrosoftSql-rev.", v5);
  v31 = 0u;
  v30 = *(_OWORD *)v6;
  v31 = *(__m128i *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 15;
  *(_BYTE *)v6 = 0;
  v7 = (_QWORD *)std::operator+<char>(&v39, &v30, v34);
  if ( &v46[7] != v7 )
  {
    v8 = v7[2];
    if ( v7[3] >= 0x10u )
      v7 = (_QWORD *)*v7;
    std::string::assign(&v46[7], v7, v8);
  }
  parquet::WriterProperties::Builder::build(v46, &v27);
  if ( v40.m128i_i64[1] >= 0x10uLL )
  {
    v9 = v40.m128i_i64[1] + 1;
    v10 = v39;
    if ( (unsigned __int64)(v40.m128i_i64[1] + 1) >= 0x1000 )
    {
      v9 = v40.m128i_i64[1] + 40;
      v10 = (_BYTE *)*((_QWORD *)v39 - 1);
      if ( (unsigned __int64)(v39 - v10 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v10, v9);
  }
  v40 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v39) = 0;
  if ( v31.m128i_i64[1] >= 0x10uLL )
  {
    v11 = v31.m128i_i64[1] + 1;
    v12 = (void *)v30;
    if ( (unsigned __int64)(v31.m128i_i64[1] + 1) >= 0x1000 )
    {
      v11 = v31.m128i_i64[1] + 40;
      v12 = *(void **)(v30 - 8);
      if ( (unsigned __int64)(v30 - (_QWORD)v12 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v12, v11);
  }
  v31 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v30) = 0;
  if ( v33.m128i_i64[1] >= 0x10uLL )
  {
    v13 = v33.m128i_i64[1] + 1;
    v14 = (void *)Src[0];
    if ( (unsigned __int64)(v33.m128i_i64[1] + 1) >= 0x1000 )
    {
      v13 = v33.m128i_i64[1] + 40;
      v14 = *(void **)(Src[0] - 8LL);
      if ( (unsigned __int64)(Src[0] - (_QWORD)v14 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v14, v13);
  }
  v33 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(Src[0]) = 0;
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v15 = si128.m128i_i64[1] + 1;
    v16 = (void *)v34[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v15 = si128.m128i_i64[1] + 40;
      v16 = *(void **)(v34[0] - 8LL);
      if ( (unsigned __int64)(v34[0] - (_QWORD)v16 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v16, v15);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v34[0]) = 0;
  ParquetFileWrite::Create(*((ParquetFileWrite **)this + 2));
  v42 = &v38;
  v38 = 0;
  v43 = &v37;
  v37 = 0;
  v17 = (std::_Ref_count_base *)*((_QWORD *)&v27 + 1);
  if ( *((_QWORD *)&v27 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL));
    v17 = (std::_Ref_count_base *)*((_QWORD *)&v27 + 1);
  }
  v37 = v27;
  v44 = v28;
  *(_OWORD *)v28 = 0;
  v18 = (volatile signed __int32 *)*((_QWORD *)this + 16);
  if ( v18 )
  {
    _InterlockedIncrement(v18 + 2);
    v18 = (volatile signed __int32 *)*((_QWORD *)this + 16);
    v17 = (std::_Ref_count_base *)*((_QWORD *)&v27 + 1);
  }
  v28[0] = *((std::_Ref_count_base **)this + 15);
  v28[1] = (std::_Ref_count_base *)v18;
  v29 = 0;
  v19 = *((_QWORD *)this + 2);
  if ( v19 )
  {
    v20 = operator new(0x18u);
    v36 = v20;
    if ( v20 )
    {
      v20[1] = 0;
      *((_DWORD *)v20 + 2) = 1;
      *((_DWORD *)v20 + 3) = 1;
      *v20 = &std::_Ref_count_resource<ParquetFileWrite *,std::default_delete<ParquetFileWrite>>::`vftable';
      v20[2] = v19;
    }
    else
    {
      v20 = 0;
    }
    *(_QWORD *)&v29 = v19;
    *((_QWORD *)&v29 + 1) = v20;
    *((_QWORD *)this + 2) = 0;
  }
  v21 = (parquet::ParquetFileWriter **)parquet::ParquetFileWriter::Open(
                                         (unsigned int)&v26,
                                         (unsigned int)&v29,
                                         (unsigned int)v28,
                                         (unsigned int)&v37,
                                         (__int64)&v38);
  v22 = (parquet::ParquetFileWriter **)((char *)this + 136);
  if ( v22 != v21 )
  {
    v23 = *v21;
    *v21 = 0;
    v24 = *v22;
    *v22 = v23;
    if ( v24 )
    {
      parquet::ParquetFileWriter::~ParquetFileWriter(v24);
      operator delete(v24, 0x18u);
    }
  }
  v25 = v26;
  if ( v26 )
  {
    parquet::ParquetFileWriter::~ParquetFileWriter(v26);
    operator delete(v25, 0x18u);
  }
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  parquet::WriterProperties::Builder::~Builder((parquet::WriterProperties::Builder *)v46);
}

```

## disassembly

```asm
0x180016560  mov     rax, rsp
0x180016563  push    rbp
0x180016564  push    rdi
0x180016565  push    r14
0x180016567  lea     rbp, [rax-268h]
0x18001656e  sub     rsp, 350h
0x180016575  mov     [rbp+260h+var_240], 0FFFFFFFFFFFFFFFEh
0x18001657d  mov     [rax+10h], rbx
0x180016581  mov     [rax+18h], rsi
0x180016585  mov     rax, cs:__security_cookie
0x18001658c  xor     rax, rsp
0x18001658f  mov     [rbp+260h+var_18], rax
0x180016596  mov     rsi, rcx
0x180016599  lea     rcx, byte_1804EA0FE
0x1800165a0  call    __CheckForDebuggerJustMyCode
0x1800165a5  xor     edx, edx; Val
0x1800165a7  mov     r8d, 1C8h; Size
0x1800165ad  lea     rcx, [rbp+260h+var_200]; void *
0x1800165b1  call    memset
0x1800165b6  lea     rcx, [rbp+260h+var_200]; this
0x1800165ba  call    ??0Builder@WriterProperties@parquet@@QEAA@XZ; parquet::WriterProperties::Builder::Builder(void)
0x1800165bf  nop
0x1800165c0  mov     [rbp+260h+var_1F8], rsi
0x1800165c4  mov     rax, [rsi+18h]
0x1800165c8  movsxd  r8, dword ptr [rax+94h]; int
0x1800165cf  cmp     r8d, 6; switch 7 cases
0x1800165d3  ja      def_1800165F3; jumptable 00000001800165F3 default case
0x1800165d9  lea     rdx, cs:180000000h
0x1800165e0  mov     ecx, ds:(jpt_1800165F3 - 180000000h)[rdx+r8*4]
0x1800165e8  add     rcx, rdx
0x1800165eb  mov     ebx, 2
0x1800165f0  xor     r14d, r14d
0x1800165f3  jmp     rcx; switch jump
0x1800165f5  mov     [rbp+260h+var_194], r14d; jumptable 00000001800165F3 case 0
0x1800165fc  jmp     short loc_180016640
0x1800165fe  mov     [rbp+260h+var_194], 1; jumptable 00000001800165F3 case 1
0x180016608  jmp     short loc_180016640
0x18001660a  mov     [rbp+260h+var_194], ebx; jumptable 00000001800165F3 case 2
0x180016610  jmp     short loc_180016640
0x180016612  mov     [rbp+260h+var_194], 7; jumptable 00000001800165F3 case 3
0x18001661c  jmp     short loc_180016640
0x18001661e  mov     [rbp+260h+var_194], 3; jumptable 00000001800165F3 case 4
0x180016628  jmp     short loc_180016640
0x18001662a  mov     [rbp+260h+var_194], 5; jumptable 00000001800165F3 case 5
0x180016634  jmp     short loc_180016640
0x180016636  mov     [rbp+260h+var_194], 4; jumptable 00000001800165F3 case 6
0x180016640  xor     eax, eax
0x180016642  mov     qword ptr [rsp+360h+var_328+8], rax
0x180016647  mov     [rsp+360h+var_318], rax
0x18001664c  mov     [rbp+260h+var_1D0], r14d
0x180016653  mov     [rbp+260h+var_190], 1
0x18001665a  mov     rcx, [rsi+90h]; this
0x180016661  call    ?GetDataPageSize@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetDataPageSize(void)
0x180016666  mov     [rbp+260h+var_1D8], rax
0x18001666d  mov     rcx, [rsi+90h]; this
0x180016674  call    ?GetDictionaryPageSizeLimit@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetDictionaryPageSizeLimit(void)
0x180016679  mov     [rbp+260h+var_1F0], rax
0x18001667d  mov     rcx, [rsi+90h]; this
0x180016684  call    ?GetMaxRowCountInColumnChunkBuffer@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetMaxRowCountInColumnChunkBuffer(void)
0x180016689  mov     [rbp+260h+var_1E8], rax
0x18001668d  lea     r9, [rbp+260h+var_1B]
0x180016694  nop     dword ptr [rax+00h]
0x180016698  nop     dword ptr [rax+rax+00000000h]
0x1800166a0  dec     r9
0x1800166a3  mov     eax, 0CCCCCCCDh
0x1800166a8  mul     ebx
0x1800166aa  shr     edx, 3
0x1800166ad  movzx   eax, dl
0x1800166b0  shl     al, 2
0x1800166b3  lea     ecx, [rax+rdx]
0x1800166b6  add     cl, cl
0x1800166b8  sub     bl, cl
0x1800166ba  add     bl, 30h ; '0'
0x1800166bd  mov     [r9], bl
0x1800166c0  mov     ebx, edx
0x1800166c2  test    edx, edx
0x1800166c4  jnz     short loc_1800166A0
0x1800166c6  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800166ce  movdqu  [rbp+260h+var_2A0], xmm0
0x1800166d3  mov     byte ptr [rbp+260h+var_2B0], r14b
0x1800166d7  lea     rax, [rbp+260h+var_1B]
0x1800166de  cmp     r9, rax
0x1800166e1  jz      short loc_1800166FA
0x1800166e3  lea     r8, [rbp+260h+var_1B]
0x1800166ea  sub     r8, r9; Size
0x1800166ed  mov     rdx, r9; Src
0x1800166f0  lea     rcx, [rbp+260h+var_2B0]; void *
0x1800166f4  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800166f9  nop
0x1800166fa  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180016702  movdqu  [rbp+260h+var_2C0], xmm0
0x180016707  mov     byte ptr [rbp+260h+Src], 0
0x18001670b  mov     r8d, 22h ; '"'; Size
0x180016711  lea     rdx, aParquetCppVers; "parquet-cpp version 1.5.1-SNAPSHOT"
0x180016718  lea     rcx, [rbp+260h+Src]; void *
0x18001671c  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180016721  nop
0x180016722  lea     rdx, ?ParquetCreatorSuffix@ParquetWriterOutputter@@0QBDB; "-MicrosoftSql-rev."
0x180016729  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180016730  inc     r8; Size
0x180016733  cmp     byte ptr [rdx+r8], 0
0x180016738  jnz     short loc_180016730
0x18001673a  lea     rcx, [rbp+260h+Src]; Src
0x18001673e  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180016743  mov     qword ptr [rbp+260h+var_2E0], r14
0x180016747  mov     qword ptr [rbp+260h+var_2E0+8], r14
0x18001674b  movups  xmm0, xmmword ptr [rax]
0x18001674e  movups  xmmword ptr [rsp+360h+var_2F8+8], xmm0
0x180016753  movups  xmm1, xmmword ptr [rax+10h]
0x180016757  movups  [rbp+260h+var_2E0], xmm1
0x18001675b  mov     [rax+10h], r14
0x18001675f  mov     qword ptr [rax+18h], 0Fh
0x180016767  mov     byte ptr [rax], 0
0x18001676a  lea     r8, [rbp+260h+var_2B0]
0x18001676e  lea     rdx, [rsp+360h+var_2F8+8]
0x180016773  lea     rcx, [rbp+260h+var_260]
0x180016777  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18001677c  nop
0x18001677d  lea     rcx, [rbp+260h+var_1C8]
0x180016784  cmp     rcx, rax
0x180016787  jz      short loc_1800167A6
0x180016789  mov     r8, [rax+10h]; Size
0x18001678d  cmp     qword ptr [rax+18h], 10h
0x180016792  jb      short loc_180016797
0x180016794  mov     rax, [rax]
0x180016797  mov     rdx, rax; Src
0x18001679a  lea     rcx, [rbp+260h+var_1C8]; void *
0x1800167a1  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800167a6  lea     rdx, [rsp+360h+var_328+8]
0x1800167ab  lea     rcx, [rbp+260h+var_200]
0x1800167af  call    ?build@Builder@WriterProperties@parquet@@QEAA?AV?$shared_ptr@VWriterProperties@parquet@@@std@@XZ; parquet::WriterProperties::Builder::build(void)
0x1800167b4  nop
0x1800167b5  mov     rdx, [rbp+260h+var_248]
0x1800167b9  cmp     rdx, 10h
0x1800167bd  jb      short loc_1800167F0
0x1800167bf  inc     rdx
0x1800167c2  mov     rcx, [rbp+260h+var_260]
0x1800167c6  mov     rax, rcx
0x1800167c9  cmp     rdx, 1000h
0x1800167d0  jb      short loc_1800167EB
0x1800167d2  add     rdx, 27h ; '''; unsigned __int64
0x1800167d6  mov     rcx, [rcx-8]; void *
0x1800167da  sub     rax, rcx
0x1800167dd  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800167e1  cmp     rax, 1Fh
0x1800167e5  ja      loc_180016A95
0x1800167eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800167f0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800167f8  movdqu  xmmword ptr [rbp+10h], xmm0
0x1800167fd  mov     byte ptr [rbp+260h+var_260], 0
0x180016801  mov     rdx, qword ptr [rbp+260h+var_2E0+8]
0x180016805  cmp     rdx, 10h
0x180016809  jb      short loc_18001683D
0x18001680b  inc     rdx
0x18001680e  mov     rcx, qword ptr [rsp+360h+var_2F8+8]
0x180016813  mov     rax, rcx
0x180016816  cmp     rdx, 1000h
0x18001681d  jb      short loc_180016838
0x18001681f  add     rdx, 27h ; '''; unsigned __int64
0x180016823  mov     rcx, [rcx-8]; void *
0x180016827  sub     rax, rcx
0x18001682a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001682e  cmp     rax, 1Fh
0x180016832  ja      loc_180016A9B
0x180016838  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001683d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180016845  movdqu  [rbp+260h+var_2E0], xmm0
0x18001684a  mov     [rsp+360h+var_2F8+8], 0
0x18001684f  mov     rdx, qword ptr [rbp+260h+var_2C0+8]
0x180016853  cmp     rdx, 10h
0x180016857  jb      short loc_18001688A
0x180016859  inc     rdx
0x18001685c  mov     rcx, [rbp+260h+Src]
0x180016860  mov     rax, rcx
0x180016863  cmp     rdx, 1000h
0x18001686a  jb      short loc_180016885
0x18001686c  add     rdx, 27h ; '''; unsigned __int64
0x180016870  mov     rcx, [rcx-8]; void *
0x180016874  sub     rax, rcx
0x180016877  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001687b  cmp     rax, 1Fh
0x18001687f  ja      loc_180016AA1
0x180016885  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001688a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180016892  movdqu  [rbp+260h+var_2C0], xmm0
0x180016897  mov     byte ptr [rbp+260h+Src], 0
0x18001689b  mov     rdx, qword ptr [rbp+260h+var_2A0+8]
0x18001689f  cmp     rdx, 10h
0x1800168a3  jb      short loc_1800168D6
0x1800168a5  inc     rdx
0x1800168a8  mov     rcx, [rbp+260h+var_2B0]
0x1800168ac  mov     rax, rcx
0x1800168af  cmp     rdx, 1000h
0x1800168b6  jb      short loc_1800168D1
0x1800168b8  add     rdx, 27h ; '''; unsigned __int64
0x1800168bc  mov     rcx, [rcx-8]; void *
0x1800168c0  sub     rax, rcx
0x1800168c3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800168c7  cmp     rax, 1Fh
0x1800168cb  ja      loc_180016A6E
0x1800168d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800168d6  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800168de  movdqu  [rbp+260h+var_2A0], xmm0
0x1800168e3  mov     byte ptr [rbp+260h+var_2B0], 0
0x1800168e7  mov     rcx, [rsi+10h]; this
0x1800168eb  call    ?Create@ParquetFileWrite@@QEAAXXZ; ParquetFileWrite::Create(void)
0x1800168f0  lea     rax, [rbp+260h+var_270]
0x1800168f4  mov     [rbp+260h+var_238], rax
0x1800168f8  xorps   xmm0, xmm0
0x1800168fb  movdqu  [rbp+260h+var_270], xmm0
0x180016900  lea     rax, [rbp+260h+var_280]
0x180016904  mov     [rbp+260h+var_230], rax
0x180016908  movdqa  [rbp+260h+var_280], xmm0
0x18001690d  mov     rdi, [rsp+360h+var_318]
0x180016912  test    rdi, rdi
0x180016915  jz      short loc_180016920
0x180016917  lock inc dword ptr [rdi+8]
0x18001691b  mov     rdi, [rsp+360h+var_318]
0x180016920  movaps  xmm0, [rsp+360h+var_328+8]
0x180016925  movdqa  [rbp+260h+var_280], xmm0
0x18001692a  lea     rax, [rsp+360h+var_318+8]
0x18001692f  mov     [rbp+260h+var_228], rax
0x180016933  xorps   xmm0, xmm0
0x180016936  movdqu  xmmword ptr [rsp+360h+var_318+8], xmm0
0x18001693c  mov     rcx, [rsi+80h]
0x180016943  test    rcx, rcx
0x180016946  jz      short loc_180016958
0x180016948  lock inc dword ptr [rcx+8]
0x18001694c  mov     rcx, [rsi+80h]
0x180016953  mov     rdi, [rsp+360h+var_318]
0x180016958  mov     rax, [rsi+78h]
0x18001695c  mov     [rsp+360h+var_318+8], rax
0x180016961  mov     qword ptr [rsp+360h+var_308], rcx
0x180016966  movdqu  [rsp+360h+var_308+8], xmm0
0x18001696c  mov     rbx, [rsi+10h]
0x180016970  test    rbx, rbx
0x180016973  jz      short loc_1800169BD
0x180016975  mov     ecx, 18h; Size
0x18001697a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001697f  mov     [rbp+260h+var_290], rax
0x180016983  test    rax, rax
0x180016986  jz      short loc_1800169AC
0x180016988  xor     ecx, ecx
0x18001698a  mov     [rax+8], rcx
0x18001698e  mov     dword ptr [rax+8], 1
0x180016995  mov     dword ptr [rax+0Ch], 1
0x18001699c  lea     rcx, ??_7?$_Ref_count_resource@PEAVParquetFileWrite@@U?$default_delete@VParquetFileWrite@@@std@@@std@@6B@; const std::_Ref_count_resource<ParquetFileWrite *,std::default_delete<ParquetFileWrite>>::`vftable'
0x1800169a3  mov     [rax], rcx
0x1800169a6  mov     [rax+10h], rbx
0x1800169aa  jmp     short loc_1800169AF
0x1800169ac  mov     rax, r14
0x1800169af  mov     qword ptr [rsp+360h+var_308+8], rbx
0x1800169b4  mov     qword ptr [rsp+360h+var_2F8], rax
0x1800169b9  mov     [rsi+10h], r14
0x1800169bd  lea     rax, [rbp+260h+var_270]
0x1800169c1  mov     [rsp+360h+var_340], rax
0x1800169c6  lea     r9, [rbp+260h+var_280]
0x1800169ca  lea     r8, [rsp+360h+var_318+8]
0x1800169cf  lea     rdx, [rsp+360h+var_308+8]
0x1800169d4  lea     rcx, [rsp+360h+var_330]
0x1800169d9  call    ?Open@ParquetFileWriter@parquet@@SA?AV?$unique_ptr@VParquetFileWriter@parquet@@U?$default_delete@VParquetFileWriter@parquet@@@std@@@std@@V?$shared_ptr@VOutputStream@io@arrow@@@4@V?$shared_ptr@VGroupNode@schema@parquet@@@4@V?$shared_ptr@VWriterProperties@parquet@@@4@V?$shared_ptr@$$CBVKeyValueMetadata@arrow@@@4@@Z; parquet::ParquetFileWriter::Open(std::shared_ptr<arrow::io::OutputStream>,std::shared_ptr<parquet::schema::GroupNode>,std::shared_ptr<parquet::WriterProperties>,std::shared_ptr<arrow::KeyValueMetadata const>)
0x1800169de  add     rsi, 88h
0x1800169e5  cmp     rsi, rax
0x1800169e8  jz      short loc_180016A10
0x1800169ea  mov     rdx, [rax]
0x1800169ed  mov     [rax], r14
0x1800169f0  mov     rbx, [rsi]
0x1800169f3  mov     [rsi], rdx
0x1800169f6  test    rbx, rbx
0x1800169f9  jz      short loc_180016A10
0x1800169fb  mov     rcx, rbx; this
0x1800169fe  call    ??1ParquetFileWriter@parquet@@QEAA@XZ; parquet::ParquetFileWriter::~ParquetFileWriter(void)
0x180016a03  mov     edx, 18h; unsigned __int64
0x180016a08  mov     rcx, rbx; void *
0x180016a0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016a10  mov     rbx, [rsp+360h+var_330]
0x180016a15  test    rbx, rbx
0x180016a18  jz      short loc_180016A30
0x180016a1a  mov     rcx, rbx; this
0x180016a1d  call    ??1ParquetFileWriter@parquet@@QEAA@XZ; parquet::ParquetFileWriter::~ParquetFileWriter(void)
0x180016a22  mov     edx, 18h; unsigned __int64
0x180016a27  mov     rcx, rbx; void *
0x180016a2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016a2f  nop
0x180016a30  test    rdi, rdi
0x180016a33  jz      short loc_180016A3E
0x180016a35  mov     rcx, rdi; this
0x180016a38  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016a3d  nop
0x180016a3e  lea     rcx, [rbp+260h+var_200]; this
0x180016a42  call    ??1Builder@WriterProperties@parquet@@UEAA@XZ; parquet::WriterProperties::Builder::~Builder(void)
0x180016a47  mov     rcx, [rbp+260h+var_18]
0x180016a4e  xor     rcx, rsp; StackCookie
0x180016a51  call    __security_check_cookie
0x180016a56  lea     r11, [rsp+360h+var_10]
0x180016a5e  mov     rbx, [r11+28h]
0x180016a62  mov     rsi, [r11+30h]
0x180016a66  mov     rsp, r11
0x180016a69  pop     r14
0x180016a6b  pop     rdi
  ... truncated ...
```
