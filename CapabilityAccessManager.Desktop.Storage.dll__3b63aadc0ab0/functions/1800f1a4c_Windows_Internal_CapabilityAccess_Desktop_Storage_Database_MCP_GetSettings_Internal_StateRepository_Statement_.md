# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::MCP::GetSettings_Internal(StateRepository::Statement &,StateRepository::Statement &,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &,unsigned __int64 *,MCPStorageConsent * *)

- ea: `0x1800f1a4c`
- end: `0x1800f23b3`
- name: `?GetSettings_Internal@MCP@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXAEAVStatement@StateRepository@@0AEAVDatabaseWrapper@Shared@4567@PEA_KPEAPEAUMCPStorageConsent@@@Z`
- size: `2407`
- prototype: `void __fastcall(struct sqlite3_stmt **this, struct sqlite3_stmt **, StateRepository::Database **, struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f15c4`
- `0x1800f1808`

## callees

- `0x180003060`
- `0x1800e793c`
- `0x1800ed70c`
- `0x1800edb4c`
- `0x1800ee9c8`
- `0x1800f1a4c`
- `0x1800f23bc`
- `0x1800f25b4`
- `0x1800f463c`
- `0x1800f47d8`
- `0x1800f73a4`
- `0x1800f73fc`
- `0x1800f9d28`
- `0x1800ffcc4`
- `0x180100048`
- `0x1801000a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f1b61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f1b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f20e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f214e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f20e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f214e`

## string_xrefs

- `0x1800f2251`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2263`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2275`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2287`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2302`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2314`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2326`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f2338`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::MCP::GetSettings_Internal(
        struct sqlite3_stmt **this,
        struct sqlite3_stmt **a2,
        StateRepository::Database **a3,
        struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *a4,
        unsigned __int64 *a5)
{
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v5; // r14
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v6; // rsi
  struct sqlite3_stmt **v7; // r15
  unsigned int v9; // r12d
  const char *v10; // r9
  int Row; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // r9
  int ColumnUInt32; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  const char *v19; // r9
  _QWORD *v20; // r13
  HLOCAL v21; // rsi
  HLOCAL v22; // rbx
  HLOCAL v23; // r14
  HLOCAL v24; // rdi
  int ColumnUInt64; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // r8
  const char *v31; // r9
  char *v32; // rdx
  __int64 v33; // r8
  const char *v34; // r9
  int v35; // r12d
  __int64 v36; // rax
  unsigned int v37; // r12d
  char *v38; // rdx
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // r12d
  __int64 v42; // rax
  char *v43; // rcx
  HLOCAL v44; // rax
  char *v45; // rdx
  int v46; // r12d
  HLOCAL v47; // rax
  char *v48; // rdx
  const char *v49; // r9
  int v50; // r12d
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v56; // r9
  char *StringForForeignKey; // r15
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v58; // r9
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v59; // r9
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v60; // r9
  __int64 v61; // r8
  const char *v62; // r9
  __int64 v63; // r8
  const char *v64; // r9
  int v65; // r12d
  __int64 v66; // rax
  char *v67; // r15
  unsigned int v68; // r12d
  __int64 v69; // rax
  void *v70; // rax
  int v71; // r12d
  char *v72; // rax
  int v73; // r12d
  bool v74[4]; // [rsp+20h] [rbp-E0h] BYREF
  char *v75; // [rsp+28h] [rbp-D8h] BYREF
  char *v76; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v77; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v78; // [rsp+40h] [rbp-C0h]
  unsigned int v79; // [rsp+48h] [rbp-B8h] BYREF
  char *v80; // [rsp+50h] [rbp-B0h] BYREF
  char *v81; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v82; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v84; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v85; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v86; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v87; // [rsp+90h] [rbp-70h] BYREF
  struct StateRepository::Statement *v88; // [rsp+98h] [rbp-68h]
  __int64 v89; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h] BYREF
  char *v93; // [rsp+C0h] [rbp-40h]
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v94; // [rsp+C8h] [rbp-38h]
  unsigned __int64 *v95; // [rsp+D0h] [rbp-30h]
  char *v96[4]; // [rsp+D8h] [rbp-28h] BYREF
  char *v97[4]; // [rsp+F8h] [rbp-8h] BYREF
  char *v98[4]; // [rsp+118h] [rbp+18h] BYREF
  char *v99[4]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v5 = a4;
  v94 = a4;
  v6 = (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)a3;
  v78 = (unsigned __int64)a3;
  v7 = a2;
  v88 = (struct StateRepository::Statement *)a2;
  v95 = a5;
  v9 = 0;
  LODWORD(v75) = 0;
  if ( !*(_QWORD *)*a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)retaddr);
  if ( !StateRepository::Database::IsInAutoCommitMode(*a3) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x589,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      v10);
  v82.Data1 = 1969881767;
  *(_DWORD *)&v82.Data2 = 1132382260;
  *(_DWORD *)v82.Data4 = -1642186565;
  *(_DWORD *)&v82.Data4[4] = -1008871855;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(v6, &v82);
  v74[0] = 0;
  Row = StateRepository::Statement::FetchRow(this, v74);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)Row,
      *(int *)v74);
  if ( !v74[0] )
    goto LABEL_65;
  v79 = 0;
  ColumnUInt32 = StateRepository::Statement::GetColumnUInt32((StateRepository::Statement *)this, v12, &v79);
  if ( ColumnUInt32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A7,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)ColumnUInt32,
      *(int *)v74);
  v16 = v79;
  if ( v79 )
  {
    *(_QWORD *)&v82.Data1 = v79;
    v20 = LocalAlloc(0, 40LL * v79);
    if ( !v20 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x5BA,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        v19);
    v85 = 0;
    v75 = 0;
    v80 = 0;
    v76 = 0;
    v81 = 0;
    v77 = 0;
    if ( v16 )
    {
      v21 = hMem;
      v22 = v84;
      v23 = v86;
      v24 = v87;
      do
      {
        StateRepository::Statement::FetchRow(v7, v74);
        if ( !v74[0] )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5C6,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
            (const char *)0x8000FFFFLL,
            *(int *)v74);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl'::`2'::impl) )
        {
          ColumnUInt64 = StateRepository::Statement::GetColumnUInt64(
                           (StateRepository::Statement *)v7,
                           0,
                           (unsigned __int64 *)&v75);
          if ( ColumnUInt64 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5CD,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)ColumnUInt64,
              *(int *)v74);
          v26 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  1,
                  (unsigned __int64 *)&v80);
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5CE,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v26,
              *(int *)v74);
          v27 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  2,
                  (unsigned __int64 *)&v76);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5CF,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v27,
              *(int *)v74);
          v28 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  3,
                  (unsigned __int64 *)&v81);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5D0,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v28,
              *(int *)v74);
          v29 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)v7, 5, &v85);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5D5,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v29,
              *(int *)v74);
          Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(
            v99,
            "Clients",
            v75,
            v78);
          Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(
            v98,
            "Servers",
            v80,
            v78);
          Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(
            v97,
            "Resources",
            v81,
            v78);
          Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(
            v96,
            "Operations",
            v76,
            v78);
          v76 = (char *)(5LL * v77);
          v20[5 * v77 + 4] = v85;
          v32 = (char *)v99;
          if ( v99[3] > (char *)7 )
            v32 = v99[0];
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v89,
            v32,
            v30,
            v31);
          v35 = v9 | 0x20;
          LODWORD(v75) = v35;
          v36 = v89;
          if ( !v89 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v34);
          v37 = v35 & 0xFFFFFFCF | 0x10;
          v89 = 0;
          v20[(_QWORD)v76] = v36;
          v38 = (char *)v98;
          if ( v98[3] > (char *)7 )
            v38 = v98[0];
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v90,
            v38,
            v33,
            v34);
          v41 = v37 | 0x80;
          LODWORD(v75) = v41;
          v42 = v90;
          if ( !v90 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v40);
          LODWORD(v75) = v41 & 0xFFFFFF7F;
          v9 = v41 & 0xFFFFFF3F | 0x40;
          v90 = 0;
          v43 = v76;
          v20[(_QWORD)v76 + 1] = v42;
          if ( v97[2] )
          {
            v45 = (char *)v97;
            if ( v97[3] > (char *)7 )
              v45 = v97[0];
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &hMem,
              v45,
              v39,
              v40);
            v46 = v9 | 0x200;
            LODWORD(v75) = v46;
            v44 = hMem;
            if ( !hMem )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0xFF8,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v40);
            LODWORD(v75) = v46 & 0xFFFFFDFF;
            v9 = v46 & 0xFFFFFCFE | 0x101;
            v21 = 0;
            hMem = 0;
            v43 = v76;
          }
          else
          {
            v44 = 0;
          }
          v20[(_QWORD)v43 + 2] = v44;
          if ( (v9 & 1) != 0 )
          {
            v9 &= ~1u;
            if ( v21 )
            {
              LocalFree(v21);
              v21 = hMem;
            }
          }
          if ( v96[2] )
          {
            v48 = (char *)v96;
            if ( v96[3] > (char *)7 )
              v48 = v96[0];
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v84,
              v48,
              v39,
              v40);
            v50 = v9 | 0x800;
            LODWORD(v75) = v50;
            v47 = v84;
            if ( !v84 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0xFF8,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v49);
            LODWORD(v75) = v50 & 0xFFFFF7FF;
            v9 = v50 & 0xFFFFF3FD | 0x402;
            v22 = 0;
            v84 = 0;
          }
          else
          {
            v47 = 0;
          }
          v20[(_QWORD)v76 + 3] = v47;
          if ( (v9 & 2) != 0 )
          {
            v9 &= ~2u;
            if ( v22 )
            {
              LocalFree(v22);
              v22 = v84;
            }
          }
          std::wstring::~wstring(v96);
          std::wstring::~wstring(v97);
          std::wstring::~wstring(v98);
          std::wstring::~wstring(v99);
        }
        else
        {
          v51 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  0,
                  (unsigned __int64 *)&v75);
          if ( v51 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5EA,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v51,
              *(int *)v74);
          v52 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  1,
                  (unsigned __int64 *)&v80);
          if ( v52 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5EB,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v52,
              *(int *)v74);
          v53 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  2,
                  (unsigned __int64 *)&v81);
          if ( v53 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5EC,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v53,
              *(int *)v74);
          v54 = StateRepository::Statement::GetColumnUInt64(
                  (StateRepository::Statement *)v7,
                  3,
                  (unsigned __int64 *)&v76);
          if ( v54 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5ED,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v54,
              *(int *)v74);
          v55 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)v7, 5, &v85);
          if ( v55 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5F2,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v55,
              *(int *)v74);
          StringForForeignKey = (char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey(
                                          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Clients",
                                          v75,
                                          v78,
                                          v56);
          v80 = (char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey(
                          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Servers",
                          v80,
                          v78,
                          v58);
          v81 = (char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey(
                          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Resources",
                          v81,
                          v78,
                          v59);
          v93 = (char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey(
                          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Operations",
                          v76,
                          v78,
                          v60);
          v76 = (char *)(5LL * v77);
          v20[(_QWORD)v76 + 4] = v85;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v91,
            StringForForeignKey,
            v61,
            v62);
          v65 = v9 | 0x2000;
          LODWORD(v75) = v65;
          v66 = v91;
          if ( !v91 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v64);
          v91 = 0;
          v67 = v76;
          v20[(_QWORD)v76] = v66;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v92,
            v80,
            v63,
            v64);
          v68 = v65 & 0xFFFF4FFF | 0x9000;
          LODWORD(v75) = v68;
          v69 = v92;
          if ( !v92 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v19);
          LODWORD(v75) = v68 & 0xFFFF7FFF;
          v9 = v68 & 0xFFFF3FFF | 0x4000;
          v92 = 0;
          v20[(_QWORD)v67 + 1] = v69;
          v70 = v81;
          if ( v81 )
          {
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v86,
              v81,
              v18,
              v19);
            v71 = v9 | 0x20000;
            LODWORD(v75) = v71;
            v70 = v86;
            if ( !v86 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0xFF8,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v19);
            LODWORD(v75) = v71 & 0xFFFDFFFF;
            v9 = v71 & 0xFFFCFFFB | 0x10004;
            v23 = 0;
            v86 = 0;
          }
          v20[(_QWORD)v67 + 2] = v70;
          if ( (v9 & 4) != 0 )
          {
            v9 &= ~4u;
            if ( v23 )
            {
              LocalFree(v23);
              v23 = v86;
            }
          }
          v72 = v93;
          if ( v93 )
          {
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v87,
              v93,
              v18,
              v19);
            v73 = v9 | 0x80000;
            LODWORD(v75) = v73;
            v72 = (char *)v87;
            if ( !v87 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0xFF8,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v19);
            LODWORD(v75) = v73 & 0xFFF7FFFF;
            v9 = v73 & 0xFFF3FFF7 | 0x40008;
            v24 = 0;
            v87 = 0;
          }
          v20[(_QWORD)v67 + 3] = v72;
          if ( (v9 & 8) != 0 )
          {
            v9 &= ~8u;
            if ( v24 )
            {
              LocalFree(v24);
              v24 = v87;
            }
          }
          v7 = (struct sqlite3_stmt **)v88;
        }
        v75 = 0;
        v80 = 0;
        v81 = 0;
        v76 = 0;
        ++v77;
      }
      while ( v77 < v79 );
      v6 = (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v78;
      v5 = v94;
    }
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(v6, v17, v18, v19);
    *v95 = (unsigned __int64)v20;
    *(_QWORD *)v5 = *(_QWORD *)&v82.Data1;
  }
  else
  {
LABEL_65:
    *(_QWORD *)v5 = 0;
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(v6, v12, v13, v14);
  }
}

```

## disassembly

```asm
0x1800f1a4c  push    rbp
0x1800f1a4e  push    rbx
0x1800f1a4f  push    rsi
0x1800f1a50  push    rdi
0x1800f1a51  push    r12
0x1800f1a53  push    r13
0x1800f1a55  push    r14
0x1800f1a57  push    r15
0x1800f1a59  lea     rbp, [rsp-68h]
0x1800f1a5e  sub     rsp, 168h
0x1800f1a65  mov     rax, cs:__security_cookie
0x1800f1a6c  xor     rax, rsp
0x1800f1a6f  mov     [rbp+0A0h+var_48], rax
0x1800f1a73  mov     r14, r9
0x1800f1a76  mov     [rbp+0A0h+var_D8], r9
0x1800f1a7a  mov     rsi, r8
0x1800f1a7d  mov     [rsp+1A0h+var_160], r8
0x1800f1a82  mov     r15, rdx
0x1800f1a85  mov     [rbp+0A0h+var_108], rdx
0x1800f1a89  mov     rbx, rcx
0x1800f1a8c  mov     rax, [rbp+0A0h+arg_20]
0x1800f1a93  mov     [rbp+0A0h+var_D0], rax
0x1800f1a97  xor     r12d, r12d
0x1800f1a9a  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1a9f  mov     rcx, [r8]; this
0x1800f1aa2  cmp     [rcx], r12
0x1800f1aa5  setz    al
0x1800f1aa8  mov     r9, [rbp+0A8h]; char *
0x1800f1aaf  test    al, al
0x1800f1ab1  jnz     loc_1800F21EB
0x1800f1ab7  mov     rdi, [rbp+0A8h]
0x1800f1abe  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800f1ac3  test    al, al
0x1800f1ac5  jz      loc_1800F2200
0x1800f1acb  mov     [rsp+1A0h+var_140.Data1], 756A02A7h
0x1800f1ad3  mov     dword ptr [rsp+1A0h+var_140.Data2], 437EC834h
0x1800f1adb  mov     dword ptr [rsp+1A0h+var_140.Data4], 9E1E38BBh
0x1800f1ae3  mov     dword ptr [rsp+1A0h+var_140.Data4+4], 0C3DDD651h
0x1800f1aeb  lea     rdx, [rsp+1A0h+var_140]; struct _GUID
0x1800f1af0  mov     rcx, rsi; this
0x1800f1af3  call    ?BeginExclusiveTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXU_GUID@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(_GUID)
0x1800f1af8  xor     edi, edi
0x1800f1afa  mov     [rsp+1A0h+var_180], dil; int
0x1800f1aff  lea     rdx, [rsp+1A0h+var_180]; bool *
0x1800f1b04  mov     rcx, rbx; this
0x1800f1b07  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f1b0c  mov     rcx, [rbp+0A8h]; this
0x1800f1b13  test    eax, eax
0x1800f1b15  js      loc_1800F2215
0x1800f1b1b  cmp     [rsp+1A0h+var_180], dil
0x1800f1b20  jz      loc_1800F21A8
0x1800f1b26  mov     [rsp+1A0h+var_158], edi
0x1800f1b2a  lea     r8, [rsp+1A0h+var_158]; unsigned int *
0x1800f1b2f  mov     rcx, rbx; this
0x1800f1b32  call    ?GetColumnUInt32@Statement@StateRepository@@QEBAJHPEAI@Z; StateRepository::Statement::GetColumnUInt32(int,uint *)
0x1800f1b37  mov     rcx, [rbp+0A8h]; this
0x1800f1b3e  test    eax, eax
0x1800f1b40  js      loc_1800F222A
0x1800f1b46  mov     ebx, [rsp+1A0h+var_158]
0x1800f1b4a  test    ebx, ebx
0x1800f1b4c  jz      loc_1800F21A8
0x1800f1b52  mov     qword ptr [rsp+1A0h+var_140.Data1], rbx
0x1800f1b57  lea     rdx, [rbx+rbx*4]
0x1800f1b5b  shl     rdx, 3; uBytes
0x1800f1b5f  xor     ecx, ecx; uFlags
0x1800f1b61  call    cs:__imp_LocalAlloc
0x1800f1b67  mov     r13, rax
0x1800f1b6a  mov     rcx, [rbp+0A8h]; this
0x1800f1b71  test    rax, rax
0x1800f1b74  jz      loc_1800F223F
0x1800f1b7a  mov     [rbp+0A0h+var_120], rdi
0x1800f1b7e  mov     [rsp+1A0h+var_178], rdi
0x1800f1b83  mov     [rsp+1A0h+var_150], rdi
0x1800f1b88  mov     [rsp+1A0h+var_170], rdi
0x1800f1b8d  mov     [rsp+1A0h+var_148], rdi
0x1800f1b92  mov     [rsp+1A0h+var_168], edi
0x1800f1b96  test    ebx, ebx
0x1800f1b98  jz      loc_1800F218F
0x1800f1b9e  mov     rsi, [rsp+1A0h+hMem]
0x1800f1ba3  mov     rbx, [rsp+1A0h+var_128]
0x1800f1ba8  mov     r14, [rbp+0A0h+var_118]
0x1800f1bac  mov     rdi, [rbp+0A0h+var_110]
0x1800f1bb0  lea     rdx, [rsp+1A0h+var_180]; bool *
0x1800f1bb5  mov     rcx, r15; this
0x1800f1bb8  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f1bbd  cmp     [rsp+1A0h+var_180], 0
0x1800f1bc2  setz    al
0x1800f1bc5  mov     rcx, [rbp+0A8h]; this
0x1800f1bcc  test    al, al
0x1800f1bce  jnz     loc_1800F21D3
0x1800f1bd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58336780@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780> `wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl(void)'::`2'::impl
0x1800f1bdb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(void)
0x1800f1be0  lea     r8, [rsp+1A0h+var_178]; unsigned __int64 *
0x1800f1be5  xor     edx, edx; int
0x1800f1be7  mov     rcx, r15; this
0x1800f1bea  test    al, al
0x1800f1bec  jz      loc_1800F1EDC
0x1800f1bf2  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1bf7  mov     rcx, [rbp+0A8h]; this
0x1800f1bfe  test    eax, eax
0x1800f1c00  js      loc_1800F22ED
0x1800f1c06  lea     r8, [rsp+1A0h+var_150]; unsigned __int64 *
0x1800f1c0b  mov     edx, 1; int
0x1800f1c10  mov     rcx, r15; this
0x1800f1c13  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1c18  mov     rcx, [rbp+0A8h]; this
0x1800f1c1f  test    eax, eax
0x1800f1c21  js      loc_1800F22D8
0x1800f1c27  lea     r8, [rsp+1A0h+var_170]; unsigned __int64 *
0x1800f1c2c  mov     edx, 2; int
0x1800f1c31  mov     rcx, r15; this
0x1800f1c34  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1c39  mov     rcx, [rbp+0A8h]; this
0x1800f1c40  test    eax, eax
0x1800f1c42  js      loc_1800F22C3
0x1800f1c48  lea     r8, [rsp+1A0h+var_148]; unsigned __int64 *
0x1800f1c4d  mov     edx, 3; int
0x1800f1c52  mov     rcx, r15; this
0x1800f1c55  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1c5a  mov     rcx, [rbp+0A8h]; this
0x1800f1c61  test    eax, eax
0x1800f1c63  js      loc_1800F22AE
0x1800f1c69  lea     r8, [rbp+0A0h+var_120]; unsigned __int64 *
0x1800f1c6d  mov     edx, 5; int
0x1800f1c72  mov     rcx, r15; this
0x1800f1c75  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1c7a  mov     rcx, [rbp+0A8h]; this
0x1800f1c81  test    eax, eax
0x1800f1c83  js      loc_1800F2299
0x1800f1c89  mov     r9, [rsp+1A0h+var_160]
0x1800f1c8e  mov     r8, [rsp+1A0h+var_178]
0x1800f1c93  lea     rdx, aClients; "Clients"
0x1800f1c9a  lea     rcx, [rbp+0A0h+var_68]
0x1800f1c9e  call    ?GetStringForForeignKey2@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(char const *,unsigned __int64,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f1ca3  nop
0x1800f1ca4  mov     r9, [rsp+1A0h+var_160]
0x1800f1ca9  mov     r8, [rsp+1A0h+var_150]
0x1800f1cae  lea     rdx, aServers; "Servers"
0x1800f1cb5  lea     rcx, [rbp+0A0h+var_88]
0x1800f1cb9  call    ?GetStringForForeignKey2@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(char const *,unsigned __int64,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f1cbe  nop
0x1800f1cbf  mov     r9, [rsp+1A0h+var_160]
0x1800f1cc4  mov     r8, [rsp+1A0h+var_148]
0x1800f1cc9  lea     rdx, aResources; "Resources"
0x1800f1cd0  lea     rcx, [rbp+0A0h+var_A8]
0x1800f1cd4  call    ?GetStringForForeignKey2@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(char const *,unsigned __int64,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f1cd9  nop
0x1800f1cda  mov     r9, [rsp+1A0h+var_160]
0x1800f1cdf  mov     r8, [rsp+1A0h+var_170]
0x1800f1ce4  lea     rdx, aOperations; "Operations"
0x1800f1ceb  lea     rcx, [rbp+0A0h+var_C8]
0x1800f1cef  call    ?GetStringForForeignKey2@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey2(char const *,unsigned __int64,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f1cf4  nop
0x1800f1cf5  mov     eax, [rsp+1A0h+var_168]
0x1800f1cf9  lea     rcx, [rax+rax*4]
0x1800f1cfd  mov     [rsp+1A0h+var_170], rcx
0x1800f1d02  mov     rax, [rbp+0A0h+var_120]
0x1800f1d06  mov     [r13+rcx*8+20h], rax
0x1800f1d0b  lea     rdx, [rbp+0A0h+var_68]
0x1800f1d0f  cmp     [rbp+0A0h+var_50], 7
0x1800f1d14  cmova   rdx, [rbp+0A0h+var_68]
0x1800f1d19  lea     rcx, [rbp+0A0h+var_100]
0x1800f1d1d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f1d22  or      r12d, 20h
0x1800f1d26  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1d2b  mov     rcx, [rbp+0A8h]; this
0x1800f1d32  mov     rax, [rbp+0A0h+var_100]
0x1800f1d36  test    rax, rax
0x1800f1d39  jz      loc_1800F2287
0x1800f1d3f  and     r12d, 0FFFFFFDFh
0x1800f1d43  or      r12d, 10h
0x1800f1d47  mov     [rbp+0A0h+var_100], 0
0x1800f1d4f  mov     rcx, [rsp+1A0h+var_170]
0x1800f1d54  mov     [r13+rcx*8+0], rax
0x1800f1d59  lea     rdx, [rbp+0A0h+var_88]
0x1800f1d5d  cmp     [rbp+0A0h+var_70], 7
0x1800f1d62  cmova   rdx, [rbp+0A0h+var_88]
0x1800f1d67  lea     rcx, [rbp+0A0h+var_F8]
0x1800f1d6b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f1d70  bts     r12d, 7
0x1800f1d75  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1d7a  mov     rcx, [rbp+0A8h]; this
0x1800f1d81  mov     rax, [rbp+0A0h+var_F8]
0x1800f1d85  test    rax, rax
0x1800f1d88  jz      loc_1800F2275
0x1800f1d8e  btr     r12d, 7
0x1800f1d93  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1d98  or      r12d, 40h
0x1800f1d9c  mov     [rbp+0A0h+var_F8], 0
0x1800f1da4  mov     rcx, [rsp+1A0h+var_170]
0x1800f1da9  mov     [r13+rcx*8+8], rax
0x1800f1dae  cmp     [rbp+0A0h+var_98], 0
0x1800f1db3  jnz     short loc_1800F1DB9
0x1800f1db5  xor     eax, eax
0x1800f1db7  jmp     short loc_1800F1E0D
0x1800f1db9  lea     rdx, [rbp+0A0h+var_A8]
0x1800f1dbd  cmp     [rbp+0A0h+var_90], 7
0x1800f1dc2  cmova   rdx, [rbp+0A0h+var_A8]
0x1800f1dc7  lea     rcx, [rsp+1A0h+hMem]
0x1800f1dcc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f1dd1  bts     r12d, 9
0x1800f1dd6  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1ddb  mov     rcx, [rbp+0A8h]; this
0x1800f1de2  mov     rax, [rsp+1A0h+hMem]
0x1800f1de7  test    rax, rax
0x1800f1dea  jz      loc_1800F2263
0x1800f1df0  btr     r12d, 9
0x1800f1df5  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1dfa  or      r12d, 101h
0x1800f1e01  xor     esi, esi
0x1800f1e03  mov     [rsp+1A0h+hMem], rsi
0x1800f1e08  mov     rcx, [rsp+1A0h+var_170]
0x1800f1e0d  mov     [r13+rcx*8+10h], rax
0x1800f1e12  test    r12b, 1
0x1800f1e16  jz      short loc_1800F1E2F
0x1800f1e18  and     r12d, 0FFFFFFFEh
0x1800f1e1c  test    rsi, rsi
0x1800f1e1f  jz      short loc_1800F1E2F
0x1800f1e21  mov     rcx, rsi; hMem
0x1800f1e24  call    cs:__imp_LocalFree
0x1800f1e2a  mov     rsi, [rsp+1A0h+hMem]
0x1800f1e2f  cmp     [rbp+0A0h+var_B8], 0
0x1800f1e34  jnz     short loc_1800F1E3A
0x1800f1e36  xor     eax, eax
0x1800f1e38  jmp     short loc_1800F1E89
0x1800f1e3a  lea     rdx, [rbp+0A0h+var_C8]
0x1800f1e3e  cmp     [rbp+0A0h+var_B0], 7
0x1800f1e43  cmova   rdx, [rbp+0A0h+var_C8]
0x1800f1e48  lea     rcx, [rsp+1A0h+var_128]
0x1800f1e4d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f1e52  bts     r12d, 0Bh
0x1800f1e57  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1e5c  mov     rcx, [rbp+0A8h]; this
0x1800f1e63  mov     rax, [rsp+1A0h+var_128]
0x1800f1e68  test    rax, rax
0x1800f1e6b  jz      loc_1800F2251
0x1800f1e71  btr     r12d, 0Bh
0x1800f1e76  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1800f1e7b  or      r12d, 402h
0x1800f1e82  xor     ebx, ebx
0x1800f1e84  mov     [rsp+1A0h+var_128], rbx
0x1800f1e89  mov     rcx, [rsp+1A0h+var_170]
0x1800f1e8e  mov     [r13+rcx*8+18h], rax
0x1800f1e93  test    r12b, 2
0x1800f1e97  jz      short loc_1800F1EB0
0x1800f1e99  and     r12d, 0FFFFFFFDh
0x1800f1e9d  test    rbx, rbx
0x1800f1ea0  jz      short loc_1800F1EB0
0x1800f1ea2  mov     rcx, rbx; hMem
0x1800f1ea5  call    cs:__imp_LocalFree
0x1800f1eab  mov     rbx, [rsp+1A0h+var_128]
0x1800f1eb0  lea     rcx, [rbp+0A0h+var_C8]
0x1800f1eb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f1eb9  nop
0x1800f1eba  lea     rcx, [rbp+0A0h+var_A8]
0x1800f1ebe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f1ec3  nop
0x1800f1ec4  lea     rcx, [rbp+0A0h+var_88]
0x1800f1ec8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f1ecd  nop
0x1800f1ece  lea     rcx, [rbp+0A0h+var_68]
0x1800f1ed2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f1ed7  jmp     loc_1800F215C
0x1800f1edc  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1ee1  mov     rcx, [rbp+0A8h]; this
0x1800f1ee8  test    eax, eax
0x1800f1eea  js      loc_1800F239E
0x1800f1ef0  lea     r8, [rsp+1A0h+var_150]; unsigned __int64 *
0x1800f1ef5  mov     edx, 1; int
0x1800f1efa  mov     rcx, r15; this
0x1800f1efd  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1f02  mov     rcx, [rbp+0A8h]; this
0x1800f1f09  test    eax, eax
0x1800f1f0b  js      loc_1800F2389
0x1800f1f11  lea     r8, [rsp+1A0h+var_148]; unsigned __int64 *
0x1800f1f16  mov     edx, 2; int
0x1800f1f1b  mov     rcx, r15; this
0x1800f1f1e  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1f23  mov     rcx, [rbp+0A8h]; this
0x1800f1f2a  test    eax, eax
0x1800f1f2c  js      loc_1800F2374
0x1800f1f32  lea     r8, [rsp+1A0h+var_170]; unsigned __int64 *
0x1800f1f37  mov     edx, 3; int
0x1800f1f3c  mov     rcx, r15; this
0x1800f1f3f  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1f44  mov     rcx, [rbp+0A8h]; this
0x1800f1f4b  test    eax, eax
0x1800f1f4d  js      loc_1800F235F
0x1800f1f53  lea     r8, [rbp+0A0h+var_120]; unsigned __int64 *
0x1800f1f57  mov     edx, 5; int
0x1800f1f5c  mov     rcx, r15; this
0x1800f1f5f  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f1f64  mov     rcx, [rbp+0A8h]; this
0x1800f1f6b  test    eax, eax
0x1800f1f6d  js      loc_1800F234A
0x1800f1f73  mov     r8, [rsp+1A0h+var_160]; unsigned __int64
0x1800f1f78  mov     rdx, [rsp+1A0h+var_178]; char *
0x1800f1f7d  lea     rcx, aClients; "Clients"
0x1800f1f84  call    ?GetStringForForeignKey@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAPEBGPEBD_KAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetStringForForeignKey(char const *,unsigned __int64,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f1f89  mov     r15, rax
  ... truncated ...
```
