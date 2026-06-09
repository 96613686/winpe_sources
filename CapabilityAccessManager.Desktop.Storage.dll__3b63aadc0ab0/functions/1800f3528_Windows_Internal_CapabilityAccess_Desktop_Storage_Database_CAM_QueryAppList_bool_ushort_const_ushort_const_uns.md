# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::QueryAppList(bool,ushort const *,ushort const *,unsigned __int64 *,CAMStorageAppConsent * *)

- ea: `0x1800f3528`
- end: `0x1800f39be`
- name: `?QueryAppList@CAM@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAX_NPEBG1PEA_KPEAPEAUCAMStorageAppConsent@@@Z`
- size: `1174`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM *__hidden this, bool, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *, struct CAMStorageAppConsent **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ee3c0`

## callees

- `0x1800edb4c`
- `0x1800ee9c8`
- `0x1800f3528`
- `0x1800f463c`
- `0x1800f6f6c`
- `0x1800f719c`
- `0x1800f73a4`
- `0x1800f73fc`
- `0x1800f75c0`
- `0x1800ffb60`
- `0x1800ffb94`
- `0x1800ffcc4`
- `0x1800fff20`
- `0x180100048`
- `0x1801000a8`
- `0x180100108`
- `0x180100908`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f366c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f366c`

## string_xrefs

- `0x1800f3949`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f3970`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f3982`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::QueryAppList(
        Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM *this,
        const wchar_t *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  char v8; // di
  unsigned int v9; // ebx
  const char *v10; // rdx
  int Row; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // r9
  int ColumnUInt32; // eax
  __int64 v16; // r14
  const char *v17; // r9
  char *v18; // r15
  int v19; // eax
  const char *v20; // rdx
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rdx
  int v24; // esi
  int ColumnUInt64; // eax
  int ColumnText16; // eax
  __int64 v27; // r8
  const char *v28; // r9
  int v29; // eax
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  int v34; // ebx
  __int64 v35; // rdx
  unsigned int v36; // ebx
  int v37; // ebx
  char *v38; // rdi
  int v39; // ebx
  __int64 v40; // rax
  bool v41[8]; // [rsp+28h] [rbp-A1h] BYREF
  struct sqlite3_stmt *v42; // [rsp+30h] [rbp-99h] BYREF
  struct _GUID v43; // [rsp+38h] [rbp-91h] BYREF
  wchar_t *v44; // [rsp+48h] [rbp-81h] BYREF
  __int64 v45; // [rsp+50h] [rbp-79h] BYREF
  __int64 v46; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int64 v47; // [rsp+60h] [rbp-69h] BYREF
  wchar_t *v48; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v49[6]; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v50[15]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+57h]
  char v52; // [rsp+128h] [rbp+5Fh]

  v52 = (char)this;
  v8 = (char)this;
  v9 = 0;
  *(_DWORD *)&v41[4] = 0;
  v42 = 0;
  v50[0] = &std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable';
  v50[1] = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection;
  v50[7] = v50;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
    (__int64)v50,
    0);
  v10 = "SELECT COUNT(*) FROM AppWithConsentID WHERE Capability=? AND User=?; ";
  if ( !v8 )
    v10 = "SELECT COUNT(*) FROM App WHERE Capability=? AND User=?; ";
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
    v10,
    (struct StateRepository::Statement *)&v42);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v42, 1, a2);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v42, 2, a3);
  v43.Data1 = -1720105589;
  *(_DWORD *)&v43.Data2 = 1255537413;
  *(_DWORD *)v43.Data4 = -1986708083;
  *(_DWORD *)&v43.Data4[4] = -194973310;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
    &v43);
  v41[0] = 0;
  Row = StateRepository::Statement::FetchRow(&v42, v41);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)Row,
      *(int *)v41);
  if ( !v41[0] )
    goto LABEL_29;
  *(_DWORD *)&v41[4] = 0;
  ColumnUInt32 = StateRepository::Statement::GetColumnUInt32(
                   (StateRepository::Statement *)&v42,
                   v12,
                   (unsigned int *)&v41[4]);
  if ( ColumnUInt32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)ColumnUInt32,
      *(int *)v41);
  v16 = *(unsigned int *)&v41[4];
  if ( *(_DWORD *)&v41[4] )
  {
    v18 = (char *)LocalAlloc(0, 24LL * *(unsigned int *)&v41[4]);
    if ( !v18 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x37F,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        v17);
    if ( v42 )
      StateRepository::StatementCache::Add(
        (StateRepository::StatementCache *)(v49[0] + 40LL),
        (struct StateRepository::Statement *)&v42);
    v19 = StateRepository::Statement::Reset((StateRepository::Statement *)&v42);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)(unsigned int)v19,
        *(int *)v41);
    v20 = "SELECT Value, PackageFamily, ConsentID FROM AppWithConsentID WHERE Capability=? AND User=?; ";
    if ( !v8 )
      v20 = "SELECT Value, PackageFamily FROM App WHERE Capability=? AND User=?; ";
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
      v20,
      (struct StateRepository::Statement *)&v42);
    StateRepository::Statement::Bind((StateRepository::Statement *)&v42, 1, a2);
    StateRepository::Statement::Bind((StateRepository::Statement *)&v42, 2, a3);
    v23 = 0;
    v47 = 0;
    v48 = 0;
    v44 = 0;
    v24 = 0;
    if ( (_DWORD)v16 )
    {
      while ( 1 )
      {
        StateRepository::Statement::FetchRow(&v42, v41);
        if ( !v41[0] )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x39E,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
            (const char *)0x8000FFFFLL,
            *(int *)v41);
        ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v42, 0, &v47);
        if ( ColumnUInt64 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3A0,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
            (const char *)(unsigned int)ColumnUInt64,
            *(int *)v41);
        ColumnText16 = StateRepository::Statement::GetColumnText16(
                         (StateRepository::Statement *)&v42,
                         1,
                         (const wchar_t **)&v48);
        if ( ColumnText16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3A1,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
            (const char *)(unsigned int)ColumnText16,
            *(int *)v41);
        if ( v8 )
        {
          v29 = StateRepository::Statement::GetColumnText16(
                  (StateRepository::Statement *)&v42,
                  2,
                  (const wchar_t **)&v44);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3A5,
              (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
              (const char *)(unsigned int)v29,
              *(int *)v41);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v45,
            (char *)v44,
            v30,
            v31);
          v34 = v9 | 2;
          *(_DWORD *)&v41[4] = v34;
          v35 = v45;
          if ( !v45 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v33);
          *(_DWORD *)&v41[4] = v34 & 0xFFFFFFFD;
          v36 = v34 & 0xFFFFFFFC | 1;
          v45 = 0;
        }
        else
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v46,
            (char *)&dword_18012216C,
            v27,
            v28);
          v37 = v9 | 8;
          *(_DWORD *)&v41[4] = v37;
          v35 = v46;
          if ( !v46 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0xFF8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v33);
          *(_DWORD *)&v41[4] = v37 & 0xFFFFFFF7;
          v36 = v37 & 0xFFFFFFF3 | 4;
          v46 = 0;
        }
        v38 = &v18[24 * v24];
        *((_QWORD *)v38 + 1) = v35;
        *((_QWORD *)v38 + 2) = v47;
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v43,
          (char *)v48,
          v32,
          v33);
        v39 = v36 | 0x20;
        *(_DWORD *)&v41[4] = v39;
        v40 = *(_QWORD *)&v43.Data1;
        v23 = 0;
        if ( !*(_QWORD *)&v43.Data1 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xFF8,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v22);
        *(_DWORD *)&v41[4] = v39 & 0xFFFFFFDF;
        v9 = v39 & 0xFFFFFFCF | 0x10;
        *(_QWORD *)&v43.Data1 = 0;
        *(_QWORD *)v38 = v40;
        if ( ++v24 >= (unsigned int)v16 )
          break;
        v8 = v52;
      }
    }
    if ( v42 )
      StateRepository::StatementCache::Add(
        (StateRepository::StatementCache *)(v49[0] + 40LL),
        (struct StateRepository::Statement *)&v42);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
      v23,
      v21,
      v22);
    *a5 = (unsigned __int64)v18;
    *(_QWORD *)a4 = v16;
  }
  else
  {
LABEL_29:
    *(_QWORD *)a4 = 0;
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49,
      v12,
      v13,
      v14);
  }
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v49);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
}

```

## disassembly

```asm
0x1800f3528  mov     rax, rsp
0x1800f352b  mov     [rax+18h], rbx
0x1800f352f  mov     [rax+10h], rdx
0x1800f3533  mov     [rax+8], cl
0x1800f3536  push    rbp
0x1800f3537  push    rsi
0x1800f3538  push    rdi
0x1800f3539  push    r12
0x1800f353b  push    r13
0x1800f353d  push    r14
0x1800f353f  push    r15
0x1800f3541  lea     rbp, [rax-57h]
0x1800f3545  sub     rsp, 0E0h
0x1800f354c  mov     r13, r9
0x1800f354f  mov     rsi, r8
0x1800f3552  mov     r14, rdx
0x1800f3555  mov     dil, cl
0x1800f3558  xor     r15d, r15d
0x1800f355b  mov     ebx, r15d
0x1800f355e  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f3562  mov     [rsp+110h+var_E8], r15
0x1800f3567  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZV12@$$V@std@@6B@; const std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable'
0x1800f356e  mov     [rbp+4Fh+var_78], rax
0x1800f3572  lea     rax, ?GetDatabaseConnection@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection(void)
0x1800f3579  mov     [rbp+4Fh+var_70], rax
0x1800f357d  lea     rax, [rbp+4Fh+var_78]
0x1800f3581  mov     [rbp+4Fh+var_40], rax
0x1800f3585  xor     r8d, r8d
0x1800f3588  lea     rdx, [rbp+4Fh+var_78]
0x1800f358c  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f3590  call    ??0DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@V?$function@$$A6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ@std@@I@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(std::function<std::shared_ptr<StateRepository::Database> (void)>,uint)
0x1800f3595  nop
0x1800f3596  lea     rax, aSelectCountFro_2; "SELECT COUNT(*) FROM App WHERE Capabili"...
0x1800f359d  lea     rdx, aSelectCountFro_1; "SELECT COUNT(*) FROM AppWithConsentID W"...
0x1800f35a4  test    dil, dil
0x1800f35a7  cmovz   rdx, rax; char *
0x1800f35ab  lea     r8, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x1800f35b0  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f35b4  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f35b9  mov     r8, r14; wchar_t *
0x1800f35bc  lea     edx, [r15+1]; int
0x1800f35c0  lea     rcx, [rsp+110h+var_E8]; this
0x1800f35c5  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f35ca  mov     r8, rsi; wchar_t *
0x1800f35cd  lea     edx, [r15+2]; int
0x1800f35d1  lea     rcx, [rsp+110h+var_E8]; this
0x1800f35d6  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f35db  mov     [rsp+110h+var_E0.Data1], 9979458Bh
0x1800f35e3  mov     dword ptr [rsp+110h+var_E0.Data2], 4AD5FB05h
0x1800f35eb  mov     dword ptr [rsp+110h+var_E0.Data4], 89953D8Dh
0x1800f35f3  mov     dword ptr [rsp+110h+var_E0.Data4+4], 0F460F182h
0x1800f35fb  lea     rdx, [rsp+110h+var_E0]; struct _GUID
0x1800f3600  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f3604  call    ?BeginExclusiveTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXU_GUID@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(_GUID)
0x1800f3609  mov     [rsp+110h+var_F0], r15b; int
0x1800f360e  lea     rdx, [rsp+110h+var_F0]; bool *
0x1800f3613  lea     rcx, [rsp+110h+var_E8]; this
0x1800f3618  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f361d  mov     rcx, [rbp+57h]; this
0x1800f3621  test    eax, eax
0x1800f3623  js      loc_1800F38F8
0x1800f3629  cmp     [rsp+110h+var_F0], r15b
0x1800f362e  jz      loc_1800F38A3
0x1800f3634  mov     dword ptr [rsp+110h+var_F0+4], r15d
0x1800f3639  lea     r8, [rsp+110h+var_F0+4]; unsigned int *
0x1800f363e  lea     rcx, [rsp+110h+var_E8]; this
0x1800f3643  call    ?GetColumnUInt32@Statement@StateRepository@@QEBAJHPEAI@Z; StateRepository::Statement::GetColumnUInt32(int,uint *)
0x1800f3648  mov     rcx, [rbp+57h]; this
0x1800f364c  test    eax, eax
0x1800f364e  js      loc_1800F390D
0x1800f3654  mov     r14d, dword ptr [rsp+110h+var_F0+4]
0x1800f3659  test    r14d, r14d
0x1800f365c  jz      loc_1800F38A3
0x1800f3662  lea     rdx, [r14+r14*2]
0x1800f3666  shl     rdx, 3; uBytes
0x1800f366a  xor     ecx, ecx; uFlags
0x1800f366c  call    cs:__imp_LocalAlloc
0x1800f3672  mov     r15, rax
0x1800f3675  mov     rcx, [rbp+57h]; this
0x1800f3679  test    rax, rax
0x1800f367c  jz      loc_1800F3922
0x1800f3682  cmp     [rsp+110h+var_E8], 0
0x1800f3688  jz      short loc_1800F369C
0x1800f368a  mov     rcx, [rbp+4Fh+var_A8]
0x1800f368e  add     rcx, 28h ; '('; this
0x1800f3692  lea     rdx, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x1800f3697  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800f369c  lea     rcx, [rsp+110h+var_E8]; this
0x1800f36a1  call    ?Reset@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Reset(void)
0x1800f36a6  mov     rcx, [rbp+57h]; this
0x1800f36aa  test    eax, eax
0x1800f36ac  js      loc_1800F3934
0x1800f36b2  lea     rax, aSelectValuePac_0; "SELECT Value, PackageFamily FROM App WH"...
0x1800f36b9  lea     rdx, aSelectValuePac; "SELECT Value, PackageFamily, ConsentID "...
0x1800f36c0  test    dil, dil
0x1800f36c3  cmovz   rdx, rax; char *
0x1800f36c7  lea     r8, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x1800f36cc  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f36d0  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f36d5  mov     r8, [rbp+4Fh+arg_8]; wchar_t *
0x1800f36d9  mov     edx, 1; int
0x1800f36de  lea     rcx, [rsp+110h+var_E8]; this
0x1800f36e3  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f36e8  mov     r8, rsi; wchar_t *
0x1800f36eb  mov     edx, 2; int
0x1800f36f0  lea     rcx, [rsp+110h+var_E8]; this
0x1800f36f5  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f36fa  xor     edx, edx
0x1800f36fc  mov     [rbp+4Fh+var_B8], rdx
0x1800f3700  mov     [rbp+4Fh+var_B0], rdx
0x1800f3704  mov     [rsp+110h+var_D0], rdx
0x1800f3709  mov     esi, edx
0x1800f370b  test    r14d, r14d
0x1800f370e  jz      loc_1800F3874
0x1800f3714  lea     rdx, [rsp+110h+var_F0]; bool *
0x1800f3719  lea     rcx, [rsp+110h+var_E8]; this
0x1800f371e  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f3723  cmp     [rsp+110h+var_F0], 0
0x1800f3728  setz    al
0x1800f372b  mov     rcx, [rbp+57h]; this
0x1800f372f  test    al, al
0x1800f3731  jnz     loc_1800F38E0
0x1800f3737  lea     r8, [rbp+4Fh+var_B8]; unsigned __int64 *
0x1800f373b  xor     edx, edx; int
0x1800f373d  lea     rcx, [rsp+110h+var_E8]; this
0x1800f3742  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f3747  mov     rcx, [rbp+57h]; this
0x1800f374b  test    eax, eax
0x1800f374d  js      loc_1800F39A9
0x1800f3753  lea     r8, [rbp+4Fh+var_B0]; wchar_t **
0x1800f3757  mov     edx, 1; int
0x1800f375c  lea     rcx, [rsp+110h+var_E8]; this
0x1800f3761  call    ?GetColumnText16@Statement@StateRepository@@QEBAJHPEAPEB_W@Z; StateRepository::Statement::GetColumnText16(int,wchar_t const * *)
0x1800f3766  mov     rcx, [rbp+57h]; this
0x1800f376a  test    eax, eax
0x1800f376c  js      loc_1800F3994
0x1800f3772  test    dil, dil
0x1800f3775  jz      short loc_1800F37D1
0x1800f3777  lea     r8, [rsp+110h+var_D0]; wchar_t **
0x1800f377c  mov     edx, 2; int
0x1800f3781  lea     rcx, [rsp+110h+var_E8]; this
0x1800f3786  call    ?GetColumnText16@Statement@StateRepository@@QEBAJHPEAPEB_W@Z; StateRepository::Statement::GetColumnText16(int,wchar_t const * *)
0x1800f378b  mov     rcx, [rbp+57h]; this
0x1800f378f  test    eax, eax
0x1800f3791  js      loc_1800F395B
0x1800f3797  mov     rdx, [rsp+110h+var_D0]
0x1800f379c  lea     rcx, [rbp+4Fh+var_C8]
0x1800f37a0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f37a5  or      ebx, 2
0x1800f37a8  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f37ac  mov     rcx, [rbp+57h]; this
0x1800f37b0  mov     rdx, [rbp+4Fh+var_C8]
0x1800f37b4  test    rdx, rdx
0x1800f37b7  jz      loc_1800F3949
0x1800f37bd  and     ebx, 0FFFFFFFDh
0x1800f37c0  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f37c4  or      ebx, 1
0x1800f37c7  mov     [rbp+4Fh+var_C8], 0
0x1800f37cf  jmp     short loc_1800F380B
0x1800f37d1  lea     rdx, dword_18012216C
0x1800f37d8  lea     rcx, [rbp+4Fh+var_C0]
0x1800f37dc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f37e1  or      ebx, 8
0x1800f37e4  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f37e8  mov     rcx, [rbp+57h]; this
0x1800f37ec  mov     rdx, [rbp+4Fh+var_C0]
0x1800f37f0  test    rdx, rdx
0x1800f37f3  jz      loc_1800F3982
0x1800f37f9  and     ebx, 0FFFFFFF7h
0x1800f37fc  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f3800  or      ebx, 4
0x1800f3803  mov     [rbp+4Fh+var_C0], 0
0x1800f380b  mov     eax, esi
0x1800f380d  lea     rcx, [rax+rax*2]
0x1800f3811  lea     rdi, [r15+rcx*8]
0x1800f3815  mov     ecx, 8
0x1800f381a  mov     rax, rdi
0x1800f381d  mov     [rax+rcx], rdx
0x1800f3821  mov     rax, [rbp+4Fh+var_B8]
0x1800f3825  mov     [rdi+10h], rax
0x1800f3829  mov     rdx, [rbp+4Fh+var_B0]
0x1800f382d  lea     rcx, [rsp+110h+var_E0]
0x1800f3832  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f3837  or      ebx, 20h
0x1800f383a  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f383e  mov     rcx, [rbp+57h]; this
0x1800f3842  mov     rax, qword ptr [rsp+110h+var_E0.Data1]
0x1800f3847  xor     edx, edx
0x1800f3849  test    rax, rax
0x1800f384c  jz      loc_1800F3970
0x1800f3852  and     ebx, 0FFFFFFDFh
0x1800f3855  mov     dword ptr [rsp+110h+var_F0+4], ebx
0x1800f3859  or      ebx, 10h
0x1800f385c  mov     qword ptr [rsp+110h+var_E0.Data1], rdx
0x1800f3861  mov     [rdi], rax
0x1800f3864  inc     esi
0x1800f3866  cmp     esi, r14d
0x1800f3869  jnb     short loc_1800F3874
0x1800f386b  mov     dil, [rbp+4Fh+arg_0]
0x1800f386f  jmp     loc_1800F3714
0x1800f3874  cmp     [rsp+110h+var_E8], rdx
0x1800f3879  jz      short loc_1800F388D
0x1800f387b  mov     rcx, [rbp+4Fh+var_A8]
0x1800f387f  add     rcx, 28h ; '('; this
0x1800f3883  lea     rdx, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x1800f3888  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800f388d  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f3891  call    ?CommitTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(void)
0x1800f3896  mov     rax, [rbp+4Fh+arg_20]
0x1800f389a  mov     [rax], r15
0x1800f389d  mov     [r13+0], r14
0x1800f38a1  jmp     short loc_1800F38B1
0x1800f38a3  mov     [r13+0], r15
0x1800f38a7  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f38ab  call    ?CommitTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(void)
0x1800f38b0  nop
0x1800f38b1  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800f38b5  call    ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800f38ba  nop
0x1800f38bb  lea     rcx, [rsp+110h+var_E8]; this
0x1800f38c0  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f38c5  mov     rbx, [rsp+110h+arg_10]
0x1800f38cd  add     rsp, 0E0h
0x1800f38d4  pop     r15
0x1800f38d6  pop     r14
0x1800f38d8  pop     r13
0x1800f38da  pop     r12
0x1800f38dc  pop     rdi
0x1800f38dd  pop     rsi
0x1800f38de  pop     rbp
0x1800f38df  retn
0x1800f38e0  mov     r9d, 8000FFFFh; char *
0x1800f38e6  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f38ed  mov     edx, 39Eh; void *
0x1800f38f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f38f8  mov     r9d, eax; char *
0x1800f38fb  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3902  mov     edx, 35Dh; void *
0x1800f3907  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f390d  mov     r9d, eax; char *
0x1800f3910  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3917  mov     edx, 36Ch; void *
0x1800f391c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3922  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3929  mov     edx, 37Fh; void *
0x1800f392e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800f3934  mov     r9d, eax; char *
0x1800f3937  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f393e  mov     edx, 382h; void *
0x1800f3943  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3949  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f3950  mov     edx, 0FF8h; void *
0x1800f3955  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800f395b  mov     r9d, eax; char *
0x1800f395e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3965  mov     edx, 3A5h; void *
0x1800f396a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3970  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f3977  mov     edx, 0FF8h; void *
0x1800f397c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800f3982  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f3989  mov     edx, 0FF8h; void *
0x1800f398e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800f3994  mov     r9d, eax; char *
0x1800f3997  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f399e  mov     edx, 3A1h; void *
0x1800f39a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f39a9  mov     r9d, eax; char *
0x1800f39ac  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f39b3  mov     edx, 3A0h; void *
0x1800f39b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
