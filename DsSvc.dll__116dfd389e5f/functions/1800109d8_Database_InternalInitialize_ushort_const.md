# Database::InternalInitialize(ushort const *)

- ea: `0x1800109d8`
- end: `0x1800111ba`
- name: `?InternalInitialize@Database@@AEAAJPEBG@Z`
- size: `2018`
- prototype: `__int64 __fastcall(Database *__hidden this, PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010844`

## callees

- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c040`
- `0x18000c158`
- `0x18000c728`
- `0x18000c93c`
- `0x1800102d8`
- `0x1800109d8`
- `0x1800111c0`
- `0x1800114e4`
- `0x180011620`
- `0x180015814`
- `0x180015a9c`
- `0x180019a94`
- `0x18001a654`

## import_xrefs

- `ESENT!JetCreateDatabaseW` at `0x180010fae`
- `ESENT!JetCreateDatabaseW` at `0x180010fae`
- `ESENT!JetAttachDatabaseW` at `0x180010f8d`
- `ESENT!JetAttachDatabaseW` at `0x180010f8d`
- `ESENT!JetSetSystemParameterW` at `0x180010a77`
- `ESENT!JetSetSystemParameterW` at `0x180010afe`
- `ESENT!JetSetSystemParameterW` at `0x180010bc0`
- `ESENT!JetSetSystemParameterW` at `0x180010c14`
- `ESENT!JetSetSystemParameterW` at `0x180010c67`
- `ESENT!JetSetSystemParameterW` at `0x180010cba`
- `ESENT!JetSetSystemParameterW` at `0x180010d0d`
- `ESENT!JetSetSystemParameterW` at `0x180010d5d`
- `ESENT!JetSetSystemParameterW` at `0x180010dad`
- `ESENT!JetSetSystemParameterW` at `0x180010e01`
- `ESENT!JetSetSystemParameterW` at `0x180010e58`
- `ESENT!JetSetSystemParameterW` at `0x180010ead`
- `ESENT!JetSetSystemParameterW` at `0x180010a77`
- `ESENT!JetSetSystemParameterW` at `0x180010afe`
- `ESENT!JetSetSystemParameterW` at `0x180010bc0`
- `ESENT!JetSetSystemParameterW` at `0x180010c14`
- `ESENT!JetSetSystemParameterW` at `0x180010c67`
- `ESENT!JetSetSystemParameterW` at `0x180010cba`
- `ESENT!JetSetSystemParameterW` at `0x180010d0d`
- `ESENT!JetSetSystemParameterW` at `0x180010d5d`
- `ESENT!JetSetSystemParameterW` at `0x180010dad`
- `ESENT!JetSetSystemParameterW` at `0x180010e01`
- `ESENT!JetSetSystemParameterW` at `0x180010e58`
- `ESENT!JetSetSystemParameterW` at `0x180010ead`
- `ESENT!JetCreateInstanceW` at `0x180010b6d`
- `ESENT!JetCreateInstanceW` at `0x180010b6d`
- `ESENT!JetInit` at `0x180010eee`
- `ESENT!JetInit` at `0x180010eee`
- `ESENT!JetBeginSessionW` at `0x180010f40`
- `ESENT!JetBeginSessionW` at `0x180010f40`
- `ESENT!JetOpenDatabaseW` at `0x180011046`
- `ESENT!JetOpenDatabaseW` at `0x180011046`

## string_xrefs

- `0x180010b66`: `DS_Token_DB`
- `0x180010a0b`: `DSTokenDB2.dat`

## pseudocode

```c
__int64 __fastcall Database::InternalInitialize(Database *this, PCWSTR pszPathIn)
{
  const unsigned __int16 *v4; // rax
  unsigned __int16 **v5; // r9
  int DestinationDir; // ebx
  DSUtils *v7; // r12
  DSLogger *v8; // rax
  const unsigned __int16 *v9; // rdx
  JET_ERR v10; // eax
  int v11; // edi
  DSLogger *v12; // rax
  int v13; // eax
  unsigned int v14; // edi
  JET_ERR v15; // eax
  int v16; // edi
  DSLogger *v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  JET_ERR InstanceW; // ebx
  DSLogger *v21; // rax
  JET_ERR v22; // ebx
  DSLogger *v23; // rax
  JET_ERR v24; // ebx
  DSLogger *v25; // rax
  JET_ERR v26; // ebx
  DSLogger *v27; // rax
  JET_ERR v28; // ebx
  DSLogger *v29; // rax
  JET_ERR v30; // ebx
  DSLogger *v31; // rax
  JET_ERR v32; // ebx
  DSLogger *v33; // rax
  JET_ERR v34; // ebx
  DSLogger *v35; // rax
  JET_ERR v36; // ebx
  DSLogger *v37; // rax
  JET_ERR v38; // ebx
  DSLogger *v39; // rax
  JET_ERR v40; // ebx
  DSLogger *v41; // rax
  JET_ERR v42; // ebx
  DSLogger *v43; // rax
  JET_SESID *v44; // r14
  JET_ERR v45; // ebx
  DSLogger *v46; // rax
  char v47; // r15
  JET_ERR v48; // edi
  JET_ERR DatabaseW; // ebx
  DSLogger *v50; // rax
  unsigned int v51; // r8d
  DSLogger *v52; // rax
  DSLogger *v53; // rax
  unsigned __int64 v54; // rax
  DSLogger *v55; // rax
  JET_PCWSTR szParam; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParama; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamb; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamc; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamd; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParame; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamf; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamg; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamh; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParami; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szParamj; // [rsp+20h] [rbp-48h]
  JET_PCWSTR szFilename; // [rsp+70h] [rbp+8h] BYREF
  struct tagJET_TABLECREATE_W *v69; // [rsp+80h] [rbp+18h] BYREF

  *((_BYTE *)this + 44) = 0;
  szFilename = 0;
  v4 = (const unsigned __int16 *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&szFilename);
  DestinationDir = DSUtils::CombinePath(pszPathIn, L"DSTokenDB2.dat", v4, v5);
  if ( DestinationDir < 0 )
    goto LABEL_64;
  v7 = (DSUtils *)szFilename;
  v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogInformation(v8, L"Database::InternalInitialize", 0x7Eu, L"Initialize Database %s", v7);
  DestinationDir = DSUtils::MakeDestinationDir(v7, v9);
  if ( DestinationDir < 0 )
    goto LABEL_64;
  v10 = JetSetSystemParameterW(0, 0xFFFFFFFFFFFFFFFFuLL, 0x82u, 1u, 0);
  v11 = v10;
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1030 )
  {
    v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParama) = v11;
    DSLogger::LogError(v12, L"Database::InternalInitialize", 0x87u, L"JET_ERR : %d", szParama);
    if ( v11 == -1011 )
      goto LABEL_52;
    v13 = -v11;
    if ( v11 > 0 )
      LOWORD(v13) = v11;
    v14 = v11 & 0x8E5E0000;
    DestinationDir = v14 | (unsigned __int16)v13 | 0xE5E0000;
    if ( ((v14 | (unsigned __int16)v13) & 0x80000000) != 0 )
      goto LABEL_64;
  }
  v15 = JetSetSystemParameterW(0, 0xFFFFFFFFFFFFFFFFuLL, 0x81u, 0xC0u, 0);
  v16 = v15;
  if ( ((v15 + 0x80000000) & 0x80000000) != 0 || v15 == -1030 )
    goto LABEL_15;
  v17 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  LODWORD(szParam) = v16;
  DSLogger::LogError(v17, L"Database::InternalInitialize", 0x8Au, L"JET_ERR : %d", szParam);
  if ( v16 == -1011 )
  {
LABEL_52:
    DestinationDir = -2147024882;
    goto LABEL_64;
  }
  v18 = -v16;
  if ( v16 > 0 )
    LOWORD(v18) = v16;
  v19 = v16 & 0x8E5E0000;
  DestinationDir = v19 | (unsigned __int16)v18 | 0xE5E0000;
  if ( ((v19 | (unsigned __int16)v18) & 0x80000000) != 0 )
    goto LABEL_64;
LABEL_15:
  InstanceW = JetCreateInstanceW((JET_INSTANCE *)this + 6, L"DS_Token_DB");
  if ( InstanceW < 0 )
  {
    v21 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParam) = InstanceW;
    DSLogger::LogError(v21, L"Database::InternalInitialize", 0x8Cu, L"JET_ERR : %d", szParam);
    DestinationDir = JetToHResult(InstanceW);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v22 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0x11u, 1u, 0);
  if ( v22 < 0 )
  {
    v23 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamb) = v22;
    DSLogger::LogError(v23, L"Database::InternalInitialize", 0x92u, L"JET_ERR : %d", szParamb);
    DestinationDir = JetToHResult(v22);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v24 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0xBu, 0x40u, 0);
  if ( v24 < 0 )
  {
    v25 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamc) = v24;
    DSLogger::LogError(v25, L"Database::InternalInitialize", 0x93u, L"JET_ERR : %d", szParamc);
    DestinationDir = JetToHResult(v24);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v26 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0x4Du, 1u, 0);
  if ( v26 < 0 )
  {
    v27 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamd) = v26;
    DSLogger::LogError(v27, L"Database::InternalInitialize", 0x94u, L"JET_ERR : %d", szParamd);
    DestinationDir = JetToHResult(v26);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v28 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0x2Du, 1u, 0);
  if ( v28 < 0 )
  {
    v29 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParame) = v28;
    DSLogger::LogError(v29, L"Database::InternalInitialize", 0x97u, L"JET_ERR : %d", szParame);
    DestinationDir = JetToHResult(v28);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v30 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0x36u, 1u, 0);
  if ( v30 < 0 )
  {
    v31 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamf) = v30;
    DSLogger::LogError(v31, L"Database::InternalInitialize", 0x98u, L"JET_ERR : %d", szParamf);
    DestinationDir = JetToHResult(v30);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v32 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, pszPathIn);
  if ( v32 < 0 )
  {
    v33 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamg) = v32;
    DSLogger::LogError(v33, L"Database::InternalInitialize", 0x9Bu, L"JET_ERR : %d", szParamg);
    DestinationDir = JetToHResult(v32);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v34 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 1u, 0, pszPathIn);
  if ( v34 < 0 )
  {
    v35 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamh) = v34;
    DSLogger::LogError(v35, L"Database::InternalInitialize", 0x9Cu, L"JET_ERR : %d", szParamh);
    DestinationDir = JetToHResult(v34);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v36 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 2u, 0, pszPathIn);
  if ( v36 < 0 )
  {
    v37 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParami) = v36;
    DSLogger::LogError(v37, L"Database::InternalInitialize", 0x9Du, L"JET_ERR : %d", szParami);
    DestinationDir = JetToHResult(v36);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v38 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 3u, 0, L"DSS");
  if ( v38 < 0 )
  {
    v39 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParamj) = v38;
    DSLogger::LogError(v39, L"Database::InternalInitialize", 0x9Eu, L"JET_ERR : %d", szParamj);
    DestinationDir = JetToHResult(v38);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v40 = JetSetSystemParameterW((JET_INSTANCE *)this + 6, 0xFFFFFFFFFFFFFFFFuLL, 0xB8u, 3u, 0);
  if ( v40 < 0 )
  {
    v41 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParam) = v40;
    DSLogger::LogError(v41, L"Database::InternalInitialize", 0xA5u, L"JET_ERR : %d", szParam);
    DestinationDir = JetToHResult(v40);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v42 = JetInit((JET_INSTANCE *)this + 6);
  if ( v42 < 0 )
  {
    v43 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParam) = v42;
    DSLogger::LogError(v43, L"Database::InternalInitialize", 0xA8u, L"JET_ERR : %d", szParam);
    DestinationDir = JetToHResult(v42);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v44 = (JET_SESID *)((char *)this + 56);
  v45 = JetBeginSessionW(*((_QWORD *)this + 6), (JET_SESID *)this + 7, &szUserName, &szUserName);
  if ( v45 < 0 )
  {
    v46 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParam) = v45;
    DSLogger::LogError(v46, L"Database::InternalInitialize", 0xACu, L"JET_ERR : %d", szParam);
    DestinationDir = JetToHResult(v45);
    if ( DestinationDir < 0 )
      goto LABEL_64;
  }
  v47 = 0;
  v48 = JetAttachDatabaseW(*v44, (JET_PCWSTR)v7, 0x10u);
  if ( v48 == -1811 )
  {
    DatabaseW = JetCreateDatabaseW(*v44, (JET_PCWSTR)v7, 0, (JET_DBID *)this + 16, 0);
    if ( DatabaseW >= 0 )
      goto LABEL_51;
    v50 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v51 = 183;
  }
  else
  {
    if ( v48 < 0 )
    {
      v52 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
      LODWORD(szParam) = v48;
      DSLogger::LogError(v52, L"Database::InternalInitialize", 0xBCu, L"JET_ERR : %d", szParam);
      DestinationDir = JetToHResult(v48);
      if ( DestinationDir < 0 )
        goto LABEL_64;
    }
    if ( v48 == 1415 )
    {
      v53 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
      DSLogger::LogWarning(
        v53,
        L"Database::InternalInitialize",
        0xC0u,
        L"Secondary indexes are detected to be in corrupted state, rebuild indexes!");
      v47 = 1;
    }
    DatabaseW = JetOpenDatabaseW(*v44, (JET_PCWSTR)v7, 0, (JET_DBID *)this + 16, 0);
    if ( DatabaseW >= 0 )
      goto LABEL_51;
    v50 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v51 = 196;
  }
  LODWORD(szParam) = DatabaseW;
  DSLogger::LogError(v50, L"Database::InternalInitialize", v51, L"JET_ERR : %d", szParam);
  DestinationDir = JetToHResult(DatabaseW);
  if ( DestinationDir < 0 )
    goto LABEL_64;
LABEL_51:
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 72,
                           v7) )
    goto LABEL_52;
  *((_DWORD *)this + 2) = 20;
  v54 = (__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 2)) >> 4;
  if ( v54 < 0x14
    && !(unsigned __int8)utl::vector<tlx::smart_ptr<DbSession,&void tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<DbSession,&void tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>>>::_SetCapacity() )
  {
    goto LABEL_52;
  }
  v69 = 0;
  DestinationDir = DbTableDescription<SharingToken>::GetTableDefinition(&v69);
  if ( DestinationDir < 0 )
    goto LABEL_64;
  DestinationDir = Database::CreateTable(this, v69);
  if ( DestinationDir < 0 )
    goto LABEL_64;
  if ( v47 )
    _InterlockedExchange(&DbTableAccess<SharingToken>::s_fIndexCorrupted, 1);
  v69 = 0;
  DestinationDir = DbTableDescription<SharingTargetTableAdapter>::GetTableDefinition(&v69);
  if ( DestinationDir < 0 || (DestinationDir = Database::CreateTable(this, v69), DestinationDir < 0) || !v47 )
  {
    if ( DestinationDir >= 0 )
      goto LABEL_65;
LABEL_64:
    v55 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(szParam) = DestinationDir;
    DSLogger::LogError(v55, L"Database::InternalInitialize", 0xD2u, L"Database::Initialize failed! hr=0x%x.", szParam);
    Database::InternalUninitialize(this);
    goto LABEL_65;
  }
  _InterlockedExchange(&DbTableAccess<SharingTargetTableAdapter>::s_fIndexCorrupted, 1);
LABEL_65:
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&szFilename);
  return (unsigned int)DestinationDir;
}

```

## disassembly

```asm
0x1800109d8  mov     [rsp+arg_8], rbx
0x1800109dd  push    rbp
0x1800109de  push    rsi
0x1800109df  push    rdi
0x1800109e0  push    r12
0x1800109e2  push    r13
0x1800109e4  push    r14
0x1800109e6  push    r15
0x1800109e8  sub     rsp, 30h
0x1800109ec  xor     r13d, r13d
0x1800109ef  mov     rsi, rcx
0x1800109f2  mov     [rcx+2Ch], r13b
0x1800109f6  mov     r14, rdx
0x1800109f9  lea     rcx, [rsp+68h+szFilename]
0x1800109fe  mov     [rsp+68h+szFilename], r13
0x180010a03  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180010a08  mov     r8, rax; unsigned __int16 *
0x180010a0b  lea     rdx, pszMore; "DSTokenDB2.dat"
0x180010a12  mov     rcx, r14; pszPathIn
0x180010a15  call    ?CombinePath@DSUtils@@YAJPEBG0PEAPEAG@Z; DSUtils::CombinePath(ushort const *,ushort const *,ushort * *)
0x180010a1a  mov     ebx, eax
0x180010a1c  test    eax, eax
0x180010a1e  js      loc_18001116C
0x180010a24  mov     r12, [rsp+68h+szFilename]
0x180010a29  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010a2e  lea     r9, aInitializeData; "Initialize Database %s"
0x180010a35  mov     [rsp+68h+szParam], r12
0x180010a3a  lea     r8d, [r13+7Eh]; unsigned int
0x180010a3e  mov     rcx, rax; this
0x180010a41  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010a48  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x180010a4d  mov     rcx, r12; this
0x180010a50  call    ?MakeDestinationDir@DSUtils@@YAJPEBG@Z; DSUtils::MakeDestinationDir(ushort const *)
0x180010a55  mov     ebx, eax
0x180010a57  test    eax, eax
0x180010a59  js      loc_18001116C
0x180010a5f  lea     ebp, [r13+1]
0x180010a63  mov     [rsp+68h+szParam], r13; szParam
0x180010a68  mov     r9d, ebp; lParam
0x180010a6b  mov     r8d, 82h; paramid
0x180010a71  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010a75  xor     ecx, ecx; pinstance
0x180010a77  call    cs:__imp_JetSetSystemParameterW
0x180010a7d  mov     ebx, 80000000h
0x180010a82  lea     r15, aJetErrD; "JET_ERR : %d"
0x180010a89  mov     edi, eax
0x180010a8b  lea     ecx, [rax+rbx]
0x180010a8e  test    ebx, ecx
0x180010a90  jnz     short loc_180010AE9
0x180010a92  cmp     eax, 0FFFFFBFAh
0x180010a97  jz      short loc_180010AE9
0x180010a99  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010a9e  mov     r9, r15; unsigned __int16 *
0x180010aa1  mov     dword ptr [rsp+68h+szParam], edi
0x180010aa5  mov     r8d, 87h; unsigned int
0x180010aab  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010ab2  mov     rcx, rax; this
0x180010ab5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010aba  cmp     edi, 0FFFFFC0Dh
0x180010ac0  jz      loc_180011098
0x180010ac6  mov     eax, edi
0x180010ac8  neg     eax
0x180010aca  cmovs   eax, edi
0x180010acd  and     edi, 8E5E0000h
0x180010ad3  movzx   ebx, ax
0x180010ad6  or      ebx, edi
0x180010ad8  or      ebx, 0E5E0000h
0x180010ade  jl      loc_18001116C
0x180010ae4  mov     ebx, 80000000h
0x180010ae9  mov     r9d, 0C0h; lParam
0x180010aef  mov     [rsp+68h+szParam], r13; szParam
0x180010af4  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010af8  xor     ecx, ecx; pinstance
0x180010afa  lea     r8d, [r9-3Fh]; paramid
0x180010afe  call    cs:__imp_JetSetSystemParameterW
0x180010b04  mov     edi, eax
0x180010b06  lea     ecx, [rax+rbx]
0x180010b09  test    ebx, ecx
0x180010b0b  jnz     short loc_180010B5F
0x180010b0d  cmp     eax, 0FFFFFBFAh
0x180010b12  jz      short loc_180010B5F
0x180010b14  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010b19  mov     r9, r15; unsigned __int16 *
0x180010b1c  mov     dword ptr [rsp+68h+szParam], edi
0x180010b20  mov     r8d, 8Ah; unsigned int
0x180010b26  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010b2d  mov     rcx, rax; this
0x180010b30  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010b35  cmp     edi, 0FFFFFC0Dh
0x180010b3b  jz      loc_180011098
0x180010b41  mov     eax, edi
0x180010b43  neg     eax
0x180010b45  cmovs   eax, edi
0x180010b48  and     edi, 8E5E0000h
0x180010b4e  movzx   ebx, ax
0x180010b51  or      ebx, edi
0x180010b53  or      ebx, 0E5E0000h
0x180010b59  jl      loc_18001116C
0x180010b5f  lea     rdi, [rsi+30h]
0x180010b63  mov     rcx, rdi; pinstance
0x180010b66  lea     rdx, szInstanceName; "DS_Token_DB"
0x180010b6d  call    cs:__imp_JetCreateInstanceW
0x180010b73  mov     ebx, eax
0x180010b75  test    eax, eax
0x180010b77  jns     short loc_180010BAB
0x180010b79  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010b7e  mov     r9, r15; unsigned __int16 *
0x180010b81  mov     dword ptr [rsp+68h+szParam], ebx
0x180010b85  mov     r8d, 8Ch; unsigned int
0x180010b8b  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010b92  mov     rcx, rax; this
0x180010b95  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010b9a  mov     ecx, ebx; int
0x180010b9c  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010ba1  mov     ebx, eax
0x180010ba3  test    eax, eax
0x180010ba5  js      loc_18001116C
0x180010bab  mov     r9, rbp; lParam
0x180010bae  mov     [rsp+68h+szParam], r13; szParam
0x180010bb3  mov     r8d, 11h; paramid
0x180010bb9  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010bbd  mov     rcx, rdi; pinstance
0x180010bc0  call    cs:__imp_JetSetSystemParameterW
0x180010bc6  mov     ebx, eax
0x180010bc8  test    eax, eax
0x180010bca  jns     short loc_180010BFE
0x180010bcc  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010bd1  mov     r9, r15; unsigned __int16 *
0x180010bd4  mov     dword ptr [rsp+68h+szParam], ebx
0x180010bd8  mov     r8d, 92h; unsigned int
0x180010bde  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010be5  mov     rcx, rax; this
0x180010be8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010bed  mov     ecx, ebx; int
0x180010bef  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010bf4  mov     ebx, eax
0x180010bf6  test    eax, eax
0x180010bf8  js      loc_18001116C
0x180010bfe  mov     r9d, 40h ; '@'; lParam
0x180010c04  mov     [rsp+68h+szParam], r13; szParam
0x180010c09  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010c0d  mov     rcx, rdi; pinstance
0x180010c10  lea     r8d, [r9-35h]; paramid
0x180010c14  call    cs:__imp_JetSetSystemParameterW
0x180010c1a  mov     ebx, eax
0x180010c1c  test    eax, eax
0x180010c1e  jns     short loc_180010C52
0x180010c20  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010c25  mov     r9, r15; unsigned __int16 *
0x180010c28  mov     dword ptr [rsp+68h+szParam], ebx
0x180010c2c  mov     r8d, 93h; unsigned int
0x180010c32  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010c39  mov     rcx, rax; this
0x180010c3c  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010c41  mov     ecx, ebx; int
0x180010c43  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010c48  mov     ebx, eax
0x180010c4a  test    eax, eax
0x180010c4c  js      loc_18001116C
0x180010c52  mov     r9, rbp; lParam
0x180010c55  mov     [rsp+68h+szParam], r13; szParam
0x180010c5a  mov     r8d, 4Dh ; 'M'; paramid
0x180010c60  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010c64  mov     rcx, rdi; pinstance
0x180010c67  call    cs:__imp_JetSetSystemParameterW
0x180010c6d  mov     ebx, eax
0x180010c6f  test    eax, eax
0x180010c71  jns     short loc_180010CA5
0x180010c73  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010c78  mov     r9, r15; unsigned __int16 *
0x180010c7b  mov     dword ptr [rsp+68h+szParam], ebx
0x180010c7f  mov     r8d, 94h; unsigned int
0x180010c85  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010c8c  mov     rcx, rax; this
0x180010c8f  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010c94  mov     ecx, ebx; int
0x180010c96  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010c9b  mov     ebx, eax
0x180010c9d  test    eax, eax
0x180010c9f  js      loc_18001116C
0x180010ca5  mov     r9, rbp; lParam
0x180010ca8  mov     [rsp+68h+szParam], r13; szParam
0x180010cad  mov     r8d, 2Dh ; '-'; paramid
0x180010cb3  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010cb7  mov     rcx, rdi; pinstance
0x180010cba  call    cs:__imp_JetSetSystemParameterW
0x180010cc0  mov     ebx, eax
0x180010cc2  test    eax, eax
0x180010cc4  jns     short loc_180010CF8
0x180010cc6  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010ccb  mov     r9, r15; unsigned __int16 *
0x180010cce  mov     dword ptr [rsp+68h+szParam], ebx
0x180010cd2  mov     r8d, 97h; unsigned int
0x180010cd8  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010cdf  mov     rcx, rax; this
0x180010ce2  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010ce7  mov     ecx, ebx; int
0x180010ce9  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010cee  mov     ebx, eax
0x180010cf0  test    eax, eax
0x180010cf2  js      loc_18001116C
0x180010cf8  mov     r9, rbp; lParam
0x180010cfb  mov     [rsp+68h+szParam], r13; szParam
0x180010d00  mov     r8d, 36h ; '6'; paramid
0x180010d06  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010d0a  mov     rcx, rdi; pinstance
0x180010d0d  call    cs:__imp_JetSetSystemParameterW
0x180010d13  mov     ebx, eax
0x180010d15  test    eax, eax
0x180010d17  jns     short loc_180010D4B
0x180010d19  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010d1e  mov     r9, r15; unsigned __int16 *
0x180010d21  mov     dword ptr [rsp+68h+szParam], ebx
0x180010d25  mov     r8d, 98h; unsigned int
0x180010d2b  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010d32  mov     rcx, rax; this
0x180010d35  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010d3a  mov     ecx, ebx; int
0x180010d3c  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010d41  mov     ebx, eax
0x180010d43  test    eax, eax
0x180010d45  js      loc_18001116C
0x180010d4b  xor     r9d, r9d; lParam
0x180010d4e  mov     [rsp+68h+szParam], r14; szParam
0x180010d53  xor     r8d, r8d; paramid
0x180010d56  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010d5a  mov     rcx, rdi; pinstance
0x180010d5d  call    cs:__imp_JetSetSystemParameterW
0x180010d63  mov     ebx, eax
0x180010d65  test    eax, eax
0x180010d67  jns     short loc_180010D9B
0x180010d69  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010d6e  mov     r9, r15; unsigned __int16 *
0x180010d71  mov     dword ptr [rsp+68h+szParam], ebx
0x180010d75  mov     r8d, 9Bh; unsigned int
0x180010d7b  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010d82  mov     rcx, rax; this
0x180010d85  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010d8a  mov     ecx, ebx; int
0x180010d8c  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010d91  mov     ebx, eax
0x180010d93  test    eax, eax
0x180010d95  js      loc_18001116C
0x180010d9b  xor     r9d, r9d; lParam
0x180010d9e  mov     [rsp+68h+szParam], r14; szParam
0x180010da3  mov     r8d, ebp; paramid
0x180010da6  or      rdx, 0FFFFFFFFFFFFFFFFh; sesid
0x180010daa  mov     rcx, rdi; pinstance
0x180010dad  call    cs:__imp_JetSetSystemParameterW
0x180010db3  mov     ebx, eax
0x180010db5  test    eax, eax
0x180010db7  jns     short loc_180010DEB
0x180010db9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010dbe  mov     r9, r15; unsigned __int16 *
0x180010dc1  mov     dword ptr [rsp+68h+szParam], ebx
0x180010dc5  mov     r8d, 9Ch; unsigned int
0x180010dcb  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010dd2  mov     rcx, rax; this
0x180010dd5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010dda  mov     ecx, ebx; int
0x180010ddc  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010de1  mov     ebx, eax
0x180010de3  test    eax, eax
0x180010de5  js      loc_18001116C
0x180010deb  xor     r9d, r9d; lParam
0x180010dee  mov     [rsp+68h+szParam], r14; szParam
0x180010df3  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010df7  mov     rcx, rdi; pinstance
0x180010dfa  mov     rdx, r14; sesid
0x180010dfd  lea     r8d, [r9+2]; paramid
0x180010e01  call    cs:__imp_JetSetSystemParameterW
0x180010e07  mov     ebx, eax
0x180010e09  test    eax, eax
0x180010e0b  jns     short loc_180010E3F
0x180010e0d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010e12  mov     r9, r15; unsigned __int16 *
0x180010e15  mov     dword ptr [rsp+68h+szParam], ebx
0x180010e19  mov     r8d, 9Dh; unsigned int
0x180010e1f  lea     rdx, aDatabaseIntern_0; "Database::InternalInitialize"
0x180010e26  mov     rcx, rax; this
0x180010e29  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010e2e  mov     ecx, ebx; int
0x180010e30  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180010e35  mov     ebx, eax
0x180010e37  test    eax, eax
0x180010e39  js      loc_18001116C
0x180010e3f  xor     r9d, r9d; lParam
0x180010e42  lea     rax, szParam; "DSS"
0x180010e49  mov     rdx, r14; sesid
0x180010e4c  mov     [rsp+68h+szParam], rax; szParam
0x180010e51  mov     rcx, rdi; pinstance
0x180010e54  lea     r8d, [r9+3]; paramid
0x180010e58  call    cs:__imp_JetSetSystemParameterW
0x180010e5e  mov     ebx, eax
0x180010e60  test    eax, eax
0x180010e62  jns     short loc_180010E96
0x180010e64  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010e69  mov     r9, r15; unsigned __int16 *
0x180010e6c  mov     dword ptr [rsp+68h+szParam], ebx
0x180010e70  mov     r8d, 9Eh; unsigned int
  ... truncated ...
```
