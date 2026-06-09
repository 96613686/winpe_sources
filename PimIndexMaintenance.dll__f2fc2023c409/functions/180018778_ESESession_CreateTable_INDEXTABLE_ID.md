# ESESession::_CreateTable(_INDEXTABLE_ID)

- ea: `0x180018778`
- end: `0x180018bdc`
- name: `?_CreateTable@ESESession@@AEAAJW4_INDEXTABLE_ID@@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016db0`
- `0x180018f58`

## callees

- `0x180002da8`
- `0x180003f90`
- `0x1800086a0`
- `0x18000a998`
- `0x18000c51c`
- `0x180010638`
- `0x180016524`
- `0x180016614`
- `0x180016860`
- `0x1800178b0`
- `0x1800179c8`
- `0x180017d74`
- `0x180018778`
- `0x18001968c`
- `0x18002120a`

## import_xrefs

- `ESENT!JetCreateTableColumnIndexA` at `0x180018af9`
- `ESENT!JetCreateTableColumnIndexA` at `0x180018af9`
- `ESENT!JetOpenTableA` at `0x18001883f`
- `ESENT!JetOpenTableA` at `0x18001883f`
- `ESENT!JetCloseTable` at `0x180018b0b`
- `ESENT!JetCloseTable` at `0x180018b0b`

## string_xrefs

- `0x1800187c6`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x1800187ea`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_CreateTable(__int64 a1, int a2)
{
  __int64 v3; // r15
  int HresultFromJetError; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 TableDefinitionFromTableId; // r13
  char **IndexDataFromTableId; // rax
  JET_DBID v12; // edx
  JET_SESID v13; // rcx
  JET_ERR v14; // eax
  unsigned int v15; // r9d
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  struct tagJET_UNICODEINDEX v22; // rbx
  unsigned int v23; // eax
  size_t v24; // r10
  __int64 v25; // rdi
  unsigned int *v26; // r12
  int v27; // eax
  __int64 v28; // r9
  unsigned int v29; // edi
  unsigned int v30; // eax
  JET_COLUMNCREATE_A *v31; // rdi
  int v32; // eax
  __int64 v33; // rdx
  JET_INDEXCREATE_A *v34; // r12
  size_t v35; // r10
  JET_DBID v36; // edx
  JET_SESID v37; // rcx
  JET_ERR v38; // eax
  JET_ERR v39; // eax
  unsigned int v40; // eax
  auto_JET_TABLEID *v41; // rcx
  _QWORD v43[3]; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v44[3]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v45; // [rsp+70h] [rbp-59h] BYREF
  int v46; // [rsp+78h] [rbp-51h]
  __int64 v47; // [rsp+80h] [rbp-49h]
  char *v48; // [rsp+88h] [rbp-41h]
  __int64 v49; // [rsp+90h] [rbp-39h]
  JET_TABLECREATE_A ptablecreate; // [rsp+A0h] [rbp-29h] BYREF
  unsigned int v51; // [rsp+130h] [rbp+67h] BYREF
  unsigned int v52; // [rsp+140h] [rbp+77h] BYREF
  struct tagJET_UNICODEINDEX v53; // [rsp+148h] [rbp+7Fh] BYREF

  v45 = *(_QWORD *)(a1 + 56);
  v3 = a2;
  v47 = a1 + 64;
  v46 = 0;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v45);
  v6 = HresultFromJetError;
  if ( HresultFromJetError < 0 )
  {
    v7 = 1135;
    v8 = 1;
LABEL_36:
    Log_HREvent(
      (unsigned int)HresultFromJetError,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v7);
    goto LABEL_37;
  }
  v9 = 48 * v3;
  v49 = 48 * v3;
  if ( *(_QWORD *)(48 * v3 + a1 + 112) != -1 )
    Log_AssertionEvent(
      v5,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1137);
  TableDefinitionFromTableId = GetTableDefinitionFromTableId((unsigned int)v3);
  IndexDataFromTableId = (char **)GetIndexDataFromTableId((unsigned int)v3);
  v12 = *(_DWORD *)(a1 + 24);
  v13 = *(_QWORD *)(a1 + 56);
  v48 = *IndexDataFromTableId;
  v14 = JetOpenTableA(v13, v12, v48, 0, 0, 0x10000u, (JET_TABLEID *)(48 * v3 + a1 + 112));
  if ( v14 != -1305 )
  {
    if ( v14 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v14);
      v6 = HresultFromJetError;
      v7 = 1239;
      v8 = 0;
      goto LABEL_36;
    }
    goto LABEL_34;
  }
  utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v43);
  if ( utl::vector<tag_JET_COLUMNCREATE_A,utl::allocator<tag_JET_COLUMNCREATE_A>>::_Resize<,0>(
         v43,
         *(unsigned int *)(TableDefinitionFromTableId + 24)) )
  {
    v15 = 0;
    if ( *(_DWORD *)(TableDefinitionFromTableId + 24) )
    {
      v16 = v43[0];
      do
      {
        v17 = *(_QWORD *)(TableDefinitionFromTableId + 16);
        v18 = 56LL * v15;
        v19 = 32LL * v15++;
        *(_OWORD *)(v18 + v16) = 0;
        *(_OWORD *)(v18 + v16 + 16) = 0;
        *(_OWORD *)(v18 + v16 + 32) = 0;
        *(_QWORD *)(v18 + v16 + 48) = 0;
        *(_DWORD *)(v18 + v16) = 56;
        *(_QWORD *)(v18 + v16 + 8) = *(_QWORD *)(v19 + v17 + 8);
        *(_DWORD *)(v18 + v16 + 16) = *(_DWORD *)(v19 + v17 + 16);
        *(_DWORD *)(v18 + v16 + 20) = *(_DWORD *)(v19 + v17 + 20);
        *(_DWORD *)(v18 + v16 + 24) = *(_DWORD *)(v19 + v17 + 24);
        *(_DWORD *)(v18 + v16 + 44) = 1200;
      }
      while ( v15 < *(_DWORD *)(TableDefinitionFromTableId + 24) );
    }
    utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v44);
    if ( !utl::vector<tagJET_INDEXCREATE_A,utl::allocator<tagJET_INDEXCREATE_A>>::_Resize<,0>(
            v44,
            *(unsigned int *)(TableDefinitionFromTableId + 40)) )
    {
      v6 = -2147024882;
      v20 = 1173;
      v21 = 2147942414LL;
LABEL_30:
      v33 = 0;
      goto LABEL_31;
    }
    v22 = g_pimIMIndex_UnicodeIdx;
    v23 = 0;
    v53 = 0;
    v24 = 80;
    while ( 1 )
    {
      v51 = v23;
      if ( v23 >= *(_DWORD *)(TableDefinitionFromTableId + 40) )
        break;
      v25 = v23;
      v26 = (unsigned int *)(v44[0] + 80LL * v23);
      memset_0(v26, 0, v24);
      if ( (*(_DWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 48 * v25 + 24) & 0x800) != 0 )
      {
        v53 = v22;
        *((_QWORD *)v26 + 5) = &v53;
      }
      *v26 = 80;
      *((_QWORD *)v26 + 1) = *(_QWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 48 * v25 + 8);
      *((_QWORD *)v26 + 2) = *(_QWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 48 * v25 + 16);
      v27 = ULongLongToULong(*(_QWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 48 * v25 + 32), v26 + 6);
      v29 = v27;
      if ( v27 < 0 )
      {
        Log_HREvent(
          (unsigned int)v27,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
          1200);
        utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v44);
        utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v43);
        v6 = v29;
        goto LABEL_37;
      }
      v30 = v51;
      v26[7] = *(_DWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 8 * v28 + 24);
      v23 = v30 + 1;
      v26[8] = v24;
      v26[16] = 0;
      *((_QWORD *)v26 + 7) = 0;
    }
    v31 = (JET_COLUMNCREATE_A *)v43[0];
    v51 = 0;
    v32 = ULongLongToULong(0x6DB6DB6DB6DB6DB7LL * ((__int64)(v43[1] - v43[0]) >> 3), &v51);
    v6 = v32;
    if ( v32 < 0 )
    {
      v20 = 1209;
LABEL_22:
      v33 = 1;
      v21 = (unsigned int)v32;
LABEL_31:
      Log_HREvent(
        v21,
        v33,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        v20);
      utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v44);
      goto LABEL_32;
    }
    v52 = 0;
    v34 = (JET_INDEXCREATE_A *)v44[0];
    v32 = ULongLongToULong(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v44[1] - v44[0]) >> 4), &v52);
    v6 = v32;
    if ( v32 < 0 )
    {
      v20 = 1212;
      goto LABEL_22;
    }
    memset_0(&ptablecreate, 0, v35);
    v36 = *(_DWORD *)(a1 + 24);
    v37 = *(_QWORD *)(a1 + 56);
    ptablecreate.szTableName = v48;
    ptablecreate.cColumns = v51;
    ptablecreate.cIndexes = v52;
    ptablecreate.grbit = *(_DWORD *)(TableDefinitionFromTableId + 44);
    ptablecreate.cbStruct = 80;
    ptablecreate.ulPages = 10;
    ptablecreate.ulDensity = 80;
    ptablecreate.rgcolumncreate = v31;
    ptablecreate.rgindexcreate = v34;
    v38 = JetCreateTableColumnIndexA(v37, v36, &ptablecreate);
    if ( v38 < 0 )
    {
      v6 = MakeHresultFromJetError(v38);
      v20 = 1231;
      v21 = v6;
      goto LABEL_30;
    }
    v39 = JetCloseTable(*(_QWORD *)(a1 + 56), ptablecreate.tableid);
    if ( v39 < 0 )
    {
      v40 = MakeHresultFromJetError(v39);
      Log_HREvent(
        v40,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        1234);
    }
    utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v44);
    utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v43);
    v9 = v49;
LABEL_34:
    v41 = (auto_JET_TABLEID *)(v9 + a1 + 104);
    *(_QWORD *)v41 = *(_QWORD *)(a1 + 56);
    auto_JET_TABLEID::close(v41);
    auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v45);
    return 0;
  }
  v6 = -2147024882;
  Log_HREvent(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    1156);
LABEL_32:
  utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(v43);
LABEL_37:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v45);
  return v6;
}

```

## disassembly

```asm
0x180018778  mov     [rsp-8+arg_8], rbx
0x18001877d  push    rbp
0x18001877e  push    rsi
0x18001877f  push    rdi
0x180018780  push    r12
0x180018782  push    r13
0x180018784  push    r14
0x180018786  push    r15
0x180018788  lea     rbp, [rsp-27h]
0x18001878d  sub     rsp, 0F0h
0x180018794  mov     rax, [rcx+38h]
0x180018798  mov     r14, rcx
0x18001879b  mov     [rbp+57h+var_B0], rax
0x18001879f  xor     r12d, r12d
0x1800187a2  lea     rax, [rcx+40h]
0x1800187a6  movsxd  r15, edx
0x1800187a9  lea     rcx, [rbp+57h+var_B0]; this
0x1800187ad  mov     [rbp+57h+var_A0], rax
0x1800187b1  mov     [rbp+57h+var_A8], r12d
0x1800187b5  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x1800187ba  mov     ebx, eax
0x1800187bc  test    eax, eax
0x1800187be  jns     short loc_1800187D7
0x1800187c0  mov     r9d, 46Fh
0x1800187c6  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800187cd  lea     edx, [r12+1]
0x1800187d2  jmp     loc_180018BAF
0x1800187d7  lea     rdi, [r15+r15*2]
0x1800187db  shl     rdi, 4
0x1800187df  lea     rbx, [r14+70h]
0x1800187e3  add     rbx, rdi
0x1800187e6  mov     [rbp+57h+var_90], rdi
0x1800187ea  lea     rsi, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800187f1  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800187f5  jz      short loc_180018805
0x1800187f7  mov     r8d, 471h
0x1800187fd  mov     rdx, rsi
0x180018800  call    Log_AssertionEvent
0x180018805  mov     ecx, r15d
0x180018808  call    ?GetTableDefinitionFromTableId@@YAPEBUDatabaseTableDefinition@@W4_INDEXTABLE_ID@@@Z; GetTableDefinitionFromTableId(_INDEXTABLE_ID)
0x18001880d  mov     ecx, r15d
0x180018810  mov     r13, rax
0x180018813  call    ?GetIndexDataFromTableId@@YAPEBU_IndexSourceData@IndexedFiltering@@W4_INDEXTABLE_ID@@@Z; GetIndexDataFromTableId(_INDEXTABLE_ID)
0x180018818  mov     edx, [r14+18h]; dbid
0x18001881c  xor     r9d, r9d; pvParameters
0x18001881f  mov     rcx, [r14+38h]; sesid
0x180018823  mov     [rsp+120h+ptableid], rbx; ptableid
0x180018828  mov     rax, [rax]
0x18001882b  mov     r8, rax; szTableName
0x18001882e  mov     [rsp+120h+grbit], 10000h; grbit
0x180018836  mov     [rbp+57h+var_98], rax
0x18001883a  mov     [rsp+120h+cbParameters], r12d; cbParameters
0x18001883f  call    cs:__imp_JetOpenTableA
0x180018845  cmp     eax, 0FFFFFAE7h
0x18001884a  jnz     loc_180018B77
0x180018850  lea     rcx, [rsp+120h+var_E0]
0x180018855  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18001885a  mov     edx, [r13+18h]
0x18001885e  lea     rcx, [rsp+120h+var_E0]
0x180018863  call    ??$_Resize@$$V$0A@@?$vector@Utag_JET_COLUMNCREATE_A@@V?$allocator@Utag_JET_COLUMNCREATE_A@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tag_JET_COLUMNCREATE_A,utl::allocator<tag_JET_COLUMNCREATE_A>>::_Resize<,0>(unsigned __int64)
0x180018868  test    al, al
0x18001886a  jnz     short loc_180018888
0x18001886c  mov     ebx, 8007000Eh
0x180018871  mov     r9d, 484h
0x180018877  mov     ecx, ebx
0x180018879  mov     r8, rsi
0x18001887c  xor     edx, edx
0x18001887e  call    Log_HREvent
0x180018883  jmp     loc_180018B6B
0x180018888  mov     r9d, r12d
0x18001888b  mov     r15d, 1
0x180018891  cmp     [r13+18h], r12d
0x180018895  jbe     short loc_180018903
0x180018897  mov     rdi, [rsp+120h+var_E0]
0x18001889c  mov     rcx, [r13+10h]
0x1800188a0  xorps   xmm0, xmm0
0x1800188a3  mov     eax, r9d
0x1800188a6  imul    rdx, rax, 38h ; '8'
0x1800188aa  xor     eax, eax
0x1800188ac  mov     r8d, r9d
0x1800188af  shl     r8, 5
0x1800188b3  add     r9d, r15d
0x1800188b6  movups  xmmword ptr [rdx+rdi], xmm0
0x1800188ba  movups  xmmword ptr [rdx+rdi+10h], xmm0
0x1800188bf  movups  xmmword ptr [rdx+rdi+20h], xmm0
0x1800188c4  mov     [rdx+rdi+30h], rax
0x1800188c9  mov     dword ptr [rdx+rdi], 38h ; '8'
0x1800188d0  mov     rax, [r8+rcx+8]
0x1800188d5  mov     [rdx+rdi+8], rax
0x1800188da  mov     eax, [r8+rcx+10h]
0x1800188df  mov     [rdx+rdi+10h], eax
0x1800188e3  mov     eax, [r8+rcx+14h]
0x1800188e8  mov     [rdx+rdi+14h], eax
0x1800188ec  mov     eax, [r8+rcx+18h]
0x1800188f1  mov     [rdx+rdi+18h], eax
0x1800188f5  mov     dword ptr [rdx+rdi+2Ch], 4B0h
0x1800188fd  cmp     r9d, [r13+18h]
0x180018901  jb      short loc_18001889C
0x180018903  lea     rcx, [rbp+57h+var_C8]
0x180018907  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18001890c  mov     edx, [r13+28h]
0x180018910  lea     rcx, [rbp+57h+var_C8]
0x180018914  call    ??$_Resize@$$V$0A@@?$vector@UtagJET_INDEXCREATE_A@@V?$allocator@UtagJET_INDEXCREATE_A@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tagJET_INDEXCREATE_A,utl::allocator<tagJET_INDEXCREATE_A>>::_Resize<,0>(unsigned __int64)
0x180018919  test    al, al
0x18001891b  jnz     short loc_18001892F
0x18001891d  mov     ebx, 8007000Eh
0x180018922  mov     r9d, 495h
0x180018928  mov     ecx, ebx
0x18001892a  jmp     loc_180018B58
0x18001892f  mov     rbx, cs:?g_pimIMIndex_UnicodeIdx@@3UtagJET_UNICODEINDEX@@B; tagJET_UNICODEINDEX const g_pimIMIndex_UnicodeIdx
0x180018936  mov     eax, r12d
0x180018939  mov     [rbp+57h+arg_18], r12
0x18001893d  mov     r10d, 50h ; 'P'
0x180018943  mov     [rbp+57h+arg_0], eax
0x180018946  cmp     eax, [r13+28h]
0x18001894a  jnb     loc_180018A2A
0x180018950  mov     edi, eax
0x180018952  mov     r8, r10; Size
0x180018955  xor     edx, edx; Val
0x180018957  lea     r12, [rdi+rdi*4]
0x18001895b  shl     r12, 4
0x18001895f  add     r12, [rbp+57h+var_C8]
0x180018963  mov     rcx, r12; void *
0x180018966  call    memset_0
0x18001896b  mov     rax, [r13+20h]
0x18001896f  lea     r9, [rdi+rdi*2]
0x180018973  add     r9, r9
0x180018976  test    dword ptr [rax+r9*8+18h], 800h
0x18001897f  jz      short loc_18001898E
0x180018981  lea     rax, [rbp+57h+arg_18]
0x180018985  mov     [rbp+57h+arg_18], rbx
0x180018989  mov     [r12+28h], rax
0x18001898e  mov     r10d, 50h ; 'P'
0x180018994  lea     rdx, [r12+18h]; unsigned int *
0x180018999  mov     [r12], r10d
0x18001899d  mov     rax, [r13+20h]
0x1800189a1  mov     rcx, [rax+r9*8+8]
0x1800189a6  mov     [r12+8], rcx
0x1800189ab  mov     rax, [r13+20h]
0x1800189af  mov     rcx, [rax+r9*8+10h]
0x1800189b4  mov     [r12+10h], rcx
0x1800189b9  mov     rcx, [r13+20h]
0x1800189bd  mov     rcx, [rcx+r9*8+20h]; unsigned __int64
0x1800189c2  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800189c7  mov     edi, eax
0x1800189c9  test    eax, eax
0x1800189cb  js      short loc_1800189FD
0x1800189cd  mov     rax, [r13+20h]
0x1800189d1  mov     ecx, [rax+r9*8+18h]
0x1800189d6  mov     eax, [rbp+57h+arg_0]
0x1800189d9  mov     [r12+1Ch], ecx
0x1800189de  add     eax, r15d
0x1800189e1  mov     [r12+20h], r10d
0x1800189e6  mov     dword ptr [r12+40h], 0
0x1800189ef  mov     qword ptr [r12+38h], 0
0x1800189f8  jmp     loc_180018943
0x1800189fd  mov     r9d, 4B0h
0x180018a03  mov     r8, rsi
0x180018a06  mov     edx, r15d
0x180018a09  mov     ecx, edi
0x180018a0b  call    Log_HREvent
0x180018a10  lea     rcx, [rbp+57h+var_C8]
0x180018a14  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018a19  lea     rcx, [rsp+120h+var_E0]
0x180018a1e  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018a23  mov     ebx, edi
0x180018a25  jmp     loc_180018BB6
0x180018a2a  mov     rcx, [rsp+120h+var_D8]
0x180018a2f  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x180018a33  mov     rdi, [rsp+120h+var_E0]
0x180018a38  mov     rax, 6DB6DB6DB6DB6DB7h
0x180018a42  sub     rcx, rdi
0x180018a45  xor     r12d, r12d
0x180018a48  sar     rcx, 3
0x180018a4c  imul    rcx, rax; unsigned __int64
0x180018a50  mov     [rbp+57h+arg_0], r12d
0x180018a54  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180018a59  mov     ebx, eax
0x180018a5b  test    eax, eax
0x180018a5d  jns     short loc_180018A6F
0x180018a5f  mov     r9d, 4B9h
0x180018a65  mov     edx, r15d
0x180018a68  mov     ecx, eax
0x180018a6a  jmp     loc_180018B5A
0x180018a6f  mov     rcx, [rbp+57h+var_C0]
0x180018a73  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180018a77  mov     [rbp+57h+arg_10], r12d
0x180018a7b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180018a85  mov     r12, [rbp+57h+var_C8]
0x180018a89  sub     rcx, r12
0x180018a8c  sar     rcx, 4
0x180018a90  imul    rcx, rax; unsigned __int64
0x180018a94  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180018a99  mov     ebx, eax
0x180018a9b  test    eax, eax
0x180018a9d  jns     short loc_180018AA7
0x180018a9f  mov     r9d, 4BCh
0x180018aa5  jmp     short loc_180018A65
0x180018aa7  mov     r8, r10; Size
0x180018aaa  lea     rcx, [rbp+57h+ptablecreate]; void *
0x180018aae  xor     edx, edx; Val
0x180018ab0  call    memset_0
0x180018ab5  mov     rax, [rbp+57h+var_98]
0x180018ab9  lea     r8, [rbp+57h+ptablecreate]; ptablecreate
0x180018abd  mov     edx, [r14+18h]; dbid
0x180018ac1  mov     rcx, [r14+38h]; sesid
0x180018ac5  mov     [rbp+57h+ptablecreate.szTableName], rax
0x180018ac9  mov     eax, [rbp+57h+arg_0]
0x180018acc  mov     [rbp+57h+ptablecreate.cColumns], eax
0x180018acf  mov     eax, [rbp+57h+arg_10]
0x180018ad2  mov     [rbp+57h+ptablecreate.cIndexes], eax
0x180018ad5  mov     eax, [r13+2Ch]
0x180018ad9  mov     [rbp+57h+ptablecreate.grbit], eax
0x180018adc  mov     [rbp+57h+ptablecreate.cbStruct], 50h ; 'P'
0x180018ae3  mov     [rbp+57h+ptablecreate.ulPages], 0Ah
0x180018aea  mov     [rbp+57h+ptablecreate.ulDensity], 50h ; 'P'
0x180018af1  mov     [rbp+57h+ptablecreate.rgcolumncreate], rdi
0x180018af5  mov     [rbp+57h+ptablecreate.rgindexcreate], r12
0x180018af9  call    cs:__imp_JetCreateTableColumnIndexA
0x180018aff  test    eax, eax
0x180018b01  js      short loc_180018B47
0x180018b03  mov     rdx, [rbp+57h+ptablecreate.tableid]; tableid
0x180018b07  mov     rcx, [r14+38h]; sesid
0x180018b0b  call    cs:__imp_JetCloseTable
0x180018b11  test    eax, eax
0x180018b13  jns     short loc_180018B2E
0x180018b15  mov     ecx, eax; int
0x180018b17  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018b1c  mov     ecx, eax
0x180018b1e  mov     r9d, 4D2h
0x180018b24  mov     r8, rsi
0x180018b27  xor     edx, edx
0x180018b29  call    Log_HREvent
0x180018b2e  lea     rcx, [rbp+57h+var_C8]
0x180018b32  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018b37  lea     rcx, [rsp+120h+var_E0]
0x180018b3c  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018b41  mov     rdi, [rbp+57h+var_90]
0x180018b45  jmp     short loc_180018B7B
0x180018b47  mov     ecx, eax; int
0x180018b49  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018b4e  mov     ebx, eax
0x180018b50  mov     r9d, 4CFh
0x180018b56  mov     ecx, eax
0x180018b58  xor     edx, edx
0x180018b5a  mov     r8, rsi
0x180018b5d  call    Log_HREvent
0x180018b62  lea     rcx, [rbp+57h+var_C8]
0x180018b66  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018b6b  lea     rcx, [rsp+120h+var_E0]
0x180018b70  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180018b75  jmp     short loc_180018BB6
0x180018b77  test    eax, eax
0x180018b79  js      short loc_180018B9B
0x180018b7b  mov     rax, [r14+38h]
0x180018b7f  lea     rcx, [r14+68h]
0x180018b83  add     rcx, rdi; this
0x180018b86  mov     [rcx], rax
0x180018b89  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180018b8e  lea     rcx, [rbp+57h+var_B0]; this
0x180018b92  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180018b97  xor     eax, eax
0x180018b99  jmp     short loc_180018BC1
0x180018b9b  mov     ecx, eax; int
0x180018b9d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ba2  mov     ebx, eax
0x180018ba4  mov     r9d, 4D7h
0x180018baa  mov     r8, rsi
0x180018bad  xor     edx, edx
0x180018baf  mov     ecx, eax
0x180018bb1  call    Log_HREvent
0x180018bb6  lea     rcx, [rbp+57h+var_B0]; this
0x180018bba  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180018bbf  mov     eax, ebx
0x180018bc1  mov     rbx, [rsp+120h+arg_8]
0x180018bc9  add     rsp, 0F0h
0x180018bd0  pop     r15
0x180018bd2  pop     r14
0x180018bd4  pop     r13
0x180018bd6  pop     r12
0x180018bd8  pop     rdi
0x180018bd9  pop     rsi
0x180018bda  pop     rbp
0x180018bdb  retn
```
