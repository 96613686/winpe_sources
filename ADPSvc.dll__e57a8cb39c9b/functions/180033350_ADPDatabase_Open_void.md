# ADPDatabase::Open(void)

- ea: `0x180033350`
- end: `0x18003380c`
- name: `?Open@ADPDatabase@@UEAAXXZ`
- size: `1212`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180002250`
- `0x180003516`
- `0x180003748`
- `0x18000c37c`
- `0x18000e1d0`
- `0x180013830`
- `0x1800170fc`
- `0x180017960`
- `0x180025a28`
- `0x180025dbc`
- `0x180025e14`
- `0x18002667c`
- `0x18002862c`
- `0x18002a0a8`
- `0x18002a5f4`
- `0x18002a6ac`
- `0x18002ff1c`
- `0x1800305f4`
- `0x180031bdc`
- `0x18003240c`
- `0x180032da4`
- `0x180033350`
- `0x1800338d0`
- `0x180033db8`
- `0x18003474c`
- `0x180034a18`
- `0x180034bc8`
- `0x180058b0c`
- `0x1800a9e4c`
- `0x1800aa164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003371f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003371f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800333e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800333e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800333d1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800333d1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003339f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003339f`

## pseudocode

```c
void __fastcall ADPDatabase::Open(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *Ptr; // rbx
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  struct sqlite3 **v6; // rbx
  int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const char **v13; // rcx
  __int64 DbPath; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int128 *v18; // rcx
  __int128 *v19; // rcx
  struct sqlite3 *v20; // rcx
  struct sqlite3 *v21; // r14
  int v22; // eax
  __int64 v23; // rax
  const char *v24; // rax
  int v25; // edx
  struct sqlite3 *v26; // rax
  struct sqlite3 *v27; // [rsp+30h] [rbp-D0h] BYREF
  union _RTL_RUN_ONCE *v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  BOOL fPending[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h]
  _BYTE Src[32]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v35; // [rsp+A8h] [rbp-58h]
  const char *v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h]
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v40; // [rsp+100h] [rbp+0h]
  unsigned __int64 v41; // [rsp+108h] [rbp+8h]
  unsigned __int8 pExceptionObject[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 v43[16]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v44; // [rsp+140h] [rbp+40h]

  fPending[0] = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, fPending, 0) )
    __fastfail(5u);
  if ( fPending[0] )
  {
    v28 = &InitOnce;
    v29 = 4;
    sqlite3_initialize();
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  AcquireSRWLockExclusive(this + 3);
  v28 = (union _RTL_RUN_ONCE *)&this[3];
  if ( this[16].Ptr <= (PVOID)7 )
    Ptr = this + 13;
  else
    Ptr = (RTL_SRWLOCK *)this[13].Ptr;
  v3 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v3 > 5u )
  {
    *(_QWORD *)fPending = Ptr;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)v3,
      (unsigned int)&word_18010053E,
      v4,
      v5,
      (__int64)fPending);
  }
  v6 = (struct sqlite3 **)&this[4];
  if ( !this[4].Ptr )
  {
    *(_OWORD *)v43 = 0;
    v44 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl'::`2'::impl) )
      ADPDatabase::EnsureEncryptionKey((ADPDatabase *)this, v43, v7);
    v33 = 0;
    v34 = 0;
    v35 = 7;
    LOWORD(v33) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl'::`2'::impl) )
    {
      DbPath = ADPDatabase::GetDbPath((__int64)&v36);
      v15 = std::operator+<wchar_t>(pExceptionObject, DbPath, L"\\");
      v16 = std::operator+<wchar_t>(v38, v15, &this[13]);
      v17 = std::operator+<wchar_t>(Src, v16, L".db");
      std::wstring::operator=(&v33, v17);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v38);
      std::wstring::~wstring(pExceptionObject);
      v13 = &v36;
    }
    else
    {
      v8 = ADPDatabase::GetDbPath((__int64)Src);
      v9 = std::operator+<wchar_t>(v38, v8, L"\\");
      v10 = std::operator+<wchar_t>(pExceptionObject, v9, &this[13]);
      v11 = std::operator+<wchar_t>(fPending, v10, L"_unencrypted");
      v12 = std::operator+<wchar_t>(&v36, v11, L".db");
      std::wstring::operator=(&v33, v12);
      std::wstring::~wstring(&v36);
      std::wstring::~wstring(fPending);
      std::wstring::~wstring(pExceptionObject);
      std::wstring::~wstring(v38);
      v13 = (const char **)Src;
    }
    std::wstring::~wstring(v13);
    v39 = 0;
    v40 = 0;
    v41 = 15;
    LOBYTE(v39) = 0;
    v18 = &v33;
    if ( v35 > 7 )
      v18 = (__int128 *)v33;
    *(_QWORD *)fPending = v18;
    v31 = v34;
    to_utf8(fPending, &v39);
    v19 = &v39;
    if ( v41 > 0xF )
      v19 = (__int128 *)v39;
    v27 = 0;
    fPending[0] = 1;
    if ( (unsigned int)openDatabase(v19, &v27, 6) )
    {
      v26 = unique_sqlite3::get((unique_sqlite3 *)&v27);
      sqlite3_error::sqlite3_error((sqlite3_error *)Src, v26);
      sqlite3_error::sqlite3_error(v38, Src);
      throw (sqlite3_error *)v38;
    }
    if ( v6 == &v27 )
    {
      v20 = v27;
    }
    else
    {
      if ( *v6 )
        unique_sqlite3::release_or_terminate(*v6);
      *v6 = v27;
      v20 = 0;
    }
    if ( v20 )
      unique_sqlite3::release_or_terminate(v20);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl'::`2'::impl) )
    {
      v21 = *v6;
      v22 = sqlite3_key_v2(*v6, 0, v43, 32);
      fPending[0] = v22;
      if ( v22 )
      {
        if ( (unsigned int)(v22 - 7) <= 1 )
        {
          v36 = "key failed with {}";
          v37 = 18;
          v23 = std::format<int &>(Src);
          v24 = (const char *)std::string::c_str(v23);
          sqlite3_error::sqlite3_error((sqlite3_error *)v38, v25, v24);
          std::string::~string(Src);
          sqlite3_error::sqlite3_error(pExceptionObject, v38);
          throw (sqlite3_error *)pExceptionObject;
        }
        sqlite3_error::sqlite3_error((sqlite3_error *)Src, v21);
        sqlite3_error::sqlite3_error(v38, Src);
        throw (sqlite3_error *)v38;
      }
    }
    sqlite3_db_config_cpp(*v6);
    v36 = "PRAGMA journal_mode=WAL;";
    v37 = 24;
    sqlite3_exec_single_text_result_cpp(Src, *v6, &v36);
    std::string::~string(Src);
    ADPDatabase::VerifyDatabaseStaticConfigurationUnderLock((ADPDatabase *)this);
    ADPDatabase::CreateOrUpdateDatabase((ADPDatabase *)this, *v6);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DatabaseValidation>::GetImpl'::`2'::impl) )
      ADPDatabase::ValidateSchema((ADPDatabase *)this, *v6);
    std::string::~string(&v39);
    std::wstring::~wstring(&v33);
  }
  if ( this != (RTL_SRWLOCK *)-24LL )
    ReleaseSRWLockExclusive(this + 3);
}

```

## disassembly

```asm
0x180033350  mov     [rsp-8+arg_8], rbx
0x180033355  mov     [rsp-8+arg_10], rsi
0x18003335a  push    rbp
0x18003335b  push    rdi
0x18003335c  push    r14
0x18003335e  lea     rbp, [rsp-60h]
0x180033363  sub     rsp, 160h
0x18003336a  mov     rax, cs:__security_cookie
0x180033371  xor     rax, rsp
0x180033374  mov     [rbp+70h+var_20], rax
0x180033378  mov     rdi, rcx
0x18003337b  mov     [rsp+170h+fPending], 0
0x180033383  mov     [rsp+170h+fPending], 0
0x18003338b  xor     r9d, r9d; lpContext
0x18003338e  lea     r8, [rsp+170h+fPending]; fPending
0x180033393  xor     edx, edx; dwFlags
0x180033395  lea     rbx, InitOnce
0x18003339c  mov     rcx, rbx; lpInitOnce
0x18003339f  call    cs:__imp___std_init_once_begin_initialize
0x1800333a5  test    eax, eax
0x1800333a7  jnz     short loc_1800333AE
0x1800333a9  lea     ecx, [rax+5]
0x1800333ac  int     29h; Win8: RtlFailFast(ecx)
0x1800333ae  cmp     [rsp+170h+fPending], 0
0x1800333b3  jz      short loc_1800333DF
0x1800333b5  mov     [rsp+170h+var_138], rbx
0x1800333ba  mov     [rsp+170h+var_130], 4
0x1800333c3  call    sqlite3_initialize
0x1800333c8  nop
0x1800333c9  xor     r8d, r8d; lpContext
0x1800333cc  xor     edx, edx; dwFlags
0x1800333ce  mov     rcx, rbx; lpInitOnce
0x1800333d1  call    cs:__imp_InitOnceComplete
0x1800333d7  test    eax, eax
0x1800333d9  jz      loc_1800337CF
0x1800333df  lea     rsi, [rdi+18h]
0x1800333e3  mov     rcx, rsi; SRWLock
0x1800333e6  call    cs:__imp_AcquireSRWLockExclusive
0x1800333ec  mov     [rsp+170h+var_138], rsi
0x1800333f1  lea     r14, [rdi+68h]
0x1800333f5  cmp     qword ptr [r14+18h], 7
0x1800333fa  jbe     short loc_180033401
0x1800333fc  mov     rbx, [r14]
0x1800333ff  jmp     short loc_180033404
0x180033401  mov     rbx, r14
0x180033404  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180033409  mov     rcx, [rax+8]
0x18003340d  mov     eax, [rcx]
0x18003340f  cmp     eax, 5
0x180033412  jbe     short loc_18003342F
0x180033414  mov     qword ptr [rsp+170h+fPending], rbx
0x180033419  lea     rax, [rsp+170h+fPending]
0x18003341e  mov     [rsp+170h+var_150], rax
0x180033423  lea     rdx, word_18010053E
0x18003342a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003342f  lea     rbx, [rdi+20h]
0x180033433  cmp     qword ptr [rbx], 0
0x180033437  jnz     loc_180033717
0x18003343d  xorps   xmm0, xmm0
0x180033440  movups  xmmword ptr [rbp+70h+var_40], xmm0
0x180033444  movups  [rbp+70h+var_30], xmm0
0x180033448  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55934612@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612> `wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl(void)'::`2'::impl
0x18003344f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(void)
0x180033454  test    al, al
0x180033456  jz      short loc_180033464
0x180033458  lea     rdx, [rbp+70h+var_40]; unsigned __int8 *
0x18003345c  mov     rcx, rdi; this
0x18003345f  call    ?EnsureEncryptionKey@ADPDatabase@@AEAAXQEAEH@Z; ADPDatabase::EnsureEncryptionKey(uchar * const,int)
0x180033464  xorps   xmm0, xmm0
0x180033467  movups  [rbp+70h+var_E0], xmm0
0x18003346b  mov     [rbp+70h+var_D0], 0
0x180033473  mov     [rbp+70h+var_C8], 7
0x18003347b  xor     eax, eax
0x18003347d  mov     word ptr [rbp+70h+var_E0], ax
0x180033481  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55934612@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612> `wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl(void)'::`2'::impl
0x180033488  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(void)
0x18003348d  test    al, al
0x18003348f  jnz     loc_180033528
0x180033495  lea     rcx, [rsp+170h+Src]
0x18003349a  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x18003349f  nop
0x1800334a0  lea     r8, asc_1800ECD70; "\\"
0x1800334a7  mov     rdx, rax
0x1800334aa  lea     rcx, [rbp+70h+var_A0]
0x1800334ae  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800334b3  nop
0x1800334b4  mov     r8, r14
0x1800334b7  mov     rdx, rax
0x1800334ba  lea     rcx, [rbp+70h+pExceptionObject]
0x1800334be  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800334c3  nop
0x1800334c4  lea     r8, aUnencrypted; "_unencrypted"
0x1800334cb  mov     rdx, rax
0x1800334ce  lea     rcx, [rsp+170h+fPending]
0x1800334d3  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800334d8  nop
0x1800334d9  lea     r8, aDb; ".db"
0x1800334e0  mov     rdx, rax
0x1800334e3  lea     rcx, [rbp+70h+var_C0]
0x1800334e7  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800334ec  mov     rdx, rax
0x1800334ef  lea     rcx, [rbp+70h+var_E0]
0x1800334f3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800334f8  lea     rcx, [rbp+70h+var_C0]
0x1800334fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033501  nop
0x180033502  lea     rcx, [rsp+170h+fPending]
0x180033507  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003350c  nop
0x18003350d  lea     rcx, [rbp+70h+pExceptionObject]
0x180033511  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033516  nop
0x180033517  lea     rcx, [rbp+70h+var_A0]
0x18003351b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033520  nop
0x180033521  lea     rcx, [rsp+170h+Src]
0x180033526  jmp     short loc_180033599
0x180033528  lea     rcx, [rbp+70h+var_C0]
0x18003352c  call    ?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ADPDatabase::GetDbPath(void)
0x180033531  nop
0x180033532  lea     r8, asc_1800ECD70; "\\"
0x180033539  mov     rdx, rax
0x18003353c  lea     rcx, [rbp+70h+pExceptionObject]
0x180033540  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180033545  nop
0x180033546  mov     r8, r14
0x180033549  mov     rdx, rax
0x18003354c  lea     rcx, [rbp+70h+var_A0]
0x180033550  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180033555  nop
0x180033556  lea     r8, aDb; ".db"
0x18003355d  mov     rdx, rax
0x180033560  lea     rcx, [rsp+170h+Src]
0x180033565  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18003356a  mov     rdx, rax
0x18003356d  lea     rcx, [rbp+70h+var_E0]
0x180033571  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180033576  lea     rcx, [rsp+170h+Src]
0x18003357b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033580  nop
0x180033581  lea     rcx, [rbp+70h+var_A0]
0x180033585  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003358a  nop
0x18003358b  lea     rcx, [rbp+70h+pExceptionObject]
0x18003358f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033594  nop
0x180033595  lea     rcx, [rbp+70h+var_C0]
0x180033599  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003359e  xorps   xmm0, xmm0
0x1800335a1  movups  [rbp+70h+var_80], xmm0
0x1800335a5  mov     [rbp+70h+var_70], 0
0x1800335ad  mov     [rbp+70h+var_68], 0Fh
0x1800335b5  mov     byte ptr [rbp+70h+var_80], 0
0x1800335b9  lea     rcx, [rbp+70h+var_E0]
0x1800335bd  cmp     [rbp+70h+var_C8], 7
0x1800335c2  cmova   rcx, qword ptr [rbp+70h+var_E0]
0x1800335c7  mov     rax, [rbp+70h+var_D0]
0x1800335cb  mov     qword ptr [rsp+170h+fPending], rcx
0x1800335d0  mov     [rsp+170h+var_118], rax
0x1800335d5  lea     rdx, [rbp+70h+var_80]
0x1800335d9  lea     rcx, [rsp+170h+fPending]
0x1800335de  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x1800335e3  lea     rcx, [rbp+70h+var_80]
0x1800335e7  cmp     [rbp+70h+var_68], 0Fh
0x1800335ec  cmova   rcx, qword ptr [rbp+70h+var_80]
0x1800335f1  mov     [rsp+170h+var_140], 0
0x1800335fa  mov     [rsp+170h+fPending], 1
0x180033602  xor     r9d, r9d
0x180033605  lea     r8d, [r9+6]
0x180033609  lea     rdx, [rsp+170h+var_140]
0x18003360e  call    openDatabase
0x180033613  test    eax, eax
0x180033615  jnz     loc_1800337D5
0x18003361b  lea     rax, [rsp+170h+var_140]
0x180033620  cmp     rbx, rax
0x180033623  jz      short loc_18003363E
0x180033625  mov     rcx, [rbx]; struct sqlite3 *
0x180033628  test    rcx, rcx
0x18003362b  jz      short loc_180033632
0x18003362d  call    ?release_or_terminate@unique_sqlite3@@CAXPEAUsqlite3@@@Z; unique_sqlite3::release_or_terminate(sqlite3 *)
0x180033632  mov     rax, [rsp+170h+var_140]
0x180033637  mov     [rbx], rax
0x18003363a  xor     ecx, ecx
0x18003363c  jmp     short loc_180033643
0x18003363e  mov     rcx, [rsp+170h+var_140]; struct sqlite3 *
0x180033643  test    rcx, rcx
0x180033646  jz      short loc_18003364D
0x180033648  call    ?release_or_terminate@unique_sqlite3@@CAXPEAUsqlite3@@@Z; unique_sqlite3::release_or_terminate(sqlite3 *)
0x18003364d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55934612@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612> `wil::Feature<__WilFeatureTraits_Feature_55934612>::GetImpl(void)'::`2'::impl
0x180033654  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55934612@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55934612>::__private_IsEnabled(void)
0x180033659  test    al, al
0x18003365b  jz      short loc_180033692
0x18003365d  mov     r14, [rbx]
0x180033660  mov     r9d, 20h ; ' '
0x180033666  lea     r8, [rbp+70h+var_40]
0x18003366a  xor     edx, edx
0x18003366c  mov     rcx, r14
0x18003366f  call    sqlite3_key_v2
0x180033674  mov     [rsp+170h+fPending], eax
0x180033678  test    eax, eax
0x18003367a  jz      short loc_180033692
0x18003367c  add     eax, 0FFFFFFF9h
0x18003367f  lea     rcx, [rsp+170h+Src]; this
0x180033684  cmp     eax, 1
0x180033687  ja      loc_1800337A7
0x18003368d  jmp     loc_180033749
0x180033692  xor     r9d, r9d
0x180033695  mov     edx, 3EEh
0x18003369a  lea     r8d, [r9+1]
0x18003369e  mov     rcx, [rbx]; struct sqlite3 *
0x1800336a1  call    sqlite3_db_config_cpp
0x1800336a6  lea     rax, aPragmaJournalM; "PRAGMA journal_mode=WAL;"
0x1800336ad  mov     [rbp+70h+var_C0], rax
0x1800336b1  mov     [rbp+70h+var_B8], 18h
0x1800336b9  lea     r8, [rbp+70h+var_C0]
0x1800336bd  mov     rdx, [rbx]
0x1800336c0  lea     rcx, [rsp+170h+Src]
0x1800336c5  call    ?sqlite3_exec_single_text_result_cpp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; sqlite3_exec_single_text_result_cpp(sqlite3 *,std::string_view)
0x1800336ca  lea     rcx, [rsp+170h+Src]
0x1800336cf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800336d4  mov     rcx, rdi; this
0x1800336d7  call    ?VerifyDatabaseStaticConfigurationUnderLock@ADPDatabase@@AEAAXXZ; ADPDatabase::VerifyDatabaseStaticConfigurationUnderLock(void)
0x1800336dc  mov     rdx, [rbx]; struct sqlite3 *
0x1800336df  mov     rcx, rdi; this
0x1800336e2  call    ?CreateOrUpdateDatabase@ADPDatabase@@AEAAXPEAUsqlite3@@@Z; ADPDatabase::CreateOrUpdateDatabase(sqlite3 *)
0x1800336e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DatabaseValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DatabaseValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation> `wil::Feature<__WilFeatureTraits_Feature_DatabaseValidation>::GetImpl(void)'::`2'::impl
0x1800336ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DatabaseValidation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation>::__private_IsEnabled(void)
0x1800336f3  test    al, al
0x1800336f5  jz      short loc_180033703
0x1800336f7  mov     rdx, [rbx]; struct sqlite3 *
0x1800336fa  mov     rcx, rdi; this
0x1800336fd  call    ?ValidateSchema@ADPDatabase@@AEAAXPEAUsqlite3@@@Z; ADPDatabase::ValidateSchema(sqlite3 *)
0x180033702  nop
0x180033703  lea     rcx, [rbp+70h+var_80]
0x180033707  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003370c  nop
0x18003370d  lea     rcx, [rbp+70h+var_E0]
0x180033711  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033716  nop
0x180033717  test    rsi, rsi
0x18003371a  jz      short loc_180033725
0x18003371c  mov     rcx, rsi; SRWLock
0x18003371f  call    cs:__imp_ReleaseSRWLockExclusive
0x180033725  mov     rcx, [rbp+70h+var_20]
0x180033729  xor     rcx, rsp; StackCookie
0x18003372c  call    __security_check_cookie
0x180033731  lea     r11, [rsp+170h+var_10]
0x180033739  mov     rbx, [r11+28h]
0x18003373d  mov     rsi, [r11+30h]
0x180033741  mov     rsp, r11
0x180033744  pop     r14
0x180033746  pop     rdi
0x180033747  pop     rbp
0x180033748  retn
0x180033749  lea     rax, aKeyFailedWith; "key failed with {}"
0x180033750  mov     [rbp+70h+var_C0], rax
0x180033754  mov     [rbp+70h+var_B8], 12h
0x18003375c  lea     r8, [rsp+170h+fPending]
0x180033761  lea     rdx, [rbp+70h+var_C0]
0x180033765  call    ??$format@AEAH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@U?$basic_format_string@DAEAH@0@AEAH@Z; std::format<int &>(std::basic_format_string<char,int &>,int &)
0x18003376a  mov     rcx, rax
0x18003376d  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180033772  mov     r8, rax; char *
0x180033775  lea     rcx, [rbp+70h+var_A0]; this
0x180033779  call    ??0sqlite3_error@@QEAA@HPEBD@Z; sqlite3_error::sqlite3_error(int,char const *)
0x18003377e  nop
0x18003377f  lea     rcx, [rsp+170h+Src]
0x180033784  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033789  lea     rdx, [rbp+70h+var_A0]
0x18003378d  lea     rcx, [rbp+70h+pExceptionObject]
0x180033791  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x180033796  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18003379d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800337a1  call    _CxxThrowException_0
0x1800337a7  mov     rdx, r14; struct sqlite3 *
0x1800337aa  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x1800337af  nop
0x1800337b0  lea     rdx, [rsp+170h+Src]
0x1800337b5  lea     rcx, [rbp+70h+var_A0]
0x1800337b9  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x1800337be  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x1800337c5  lea     rcx, [rbp+70h+var_A0]; pExceptionObject
0x1800337c9  call    _CxxThrowException_0
0x1800337cf  call    __std_init_once_link_alternate_names_and_abort
0x1800337d5  lea     rcx, [rsp+170h+var_140]; this
0x1800337da  call    ?get@unique_sqlite3@@QEBAPEAUsqlite3@@XZ; unique_sqlite3::get(void)
0x1800337df  mov     rdx, rax; struct sqlite3 *
0x1800337e2  lea     rcx, [rsp+170h+Src]; this
0x1800337e7  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x1800337ec  nop
0x1800337ed  lea     rdx, [rsp+170h+Src]
0x1800337f2  lea     rcx, [rbp+70h+var_A0]
0x1800337f6  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x1800337fb  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x180033802  lea     rcx, [rbp+70h+var_A0]; pExceptionObject
0x180033806  call    _CxxThrowException_0
```
