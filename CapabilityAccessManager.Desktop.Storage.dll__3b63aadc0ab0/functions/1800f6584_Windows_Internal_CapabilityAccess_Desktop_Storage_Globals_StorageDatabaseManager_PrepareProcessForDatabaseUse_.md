# Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::PrepareProcessForDatabaseUse(uint,uint)

- ea: `0x1800f6584`
- end: `0x1800f6946`
- name: `?PrepareProcessForDatabaseUse@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAXII@Z`
- size: `962`
- prototype: `void __fastcall(char, char, __int64, const char *)`
- caller_count: `2`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x1800ee300`
- `0x1800f6a20`

## callees

- `0x180003060`
- `0x1800e4e0a`
- `0x1800e793c`
- `0x1800e8a1c`
- `0x1800eabf4`
- `0x1800ec618`
- `0x1800ed70c`
- `0x1800edb4c`
- `0x1800f2a54`
- `0x1800f44fc`
- `0x1800f4818`
- `0x1800f5c78`
- `0x1800f5f4c`
- `0x1800f62a0`
- `0x1800f62d8`
- `0x1800f6448`
- `0x1800f6584`
- `0x1800f719c`
- `0x1800f73fc`
- `0x1800f7480`
- `0x1800f8808`
- `0x1800fae48`
- `0x1800fbc58`
- `0x18010165c`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f6854`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f6854`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6641`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6641`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f666d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6685`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f68b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f666d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6685`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f68b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f6694`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f6694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6707`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f66f2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f66f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800f6737`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800f6737`

## string_xrefs

- `0x1800f6817`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::PrepareProcessForDatabaseUse(
        char a1,
        char a2,
        __int64 a3,
        const char *a4)
{
  void **v5; // rbx
  PSRWLOCK *v6; // rax
  char v7; // si
  RTL_SRWLOCK *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  struct Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry *v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  void **StorageDatabaseDirectory; // rax
  BOOL DirectoryW; // edi
  __int64 v17; // rdx
  __int64 v18; // r8
  const char *v19; // r9
  void **StorageDatabaseFullPath; // rax
  unsigned int v21; // r14d
  PSRWLOCK v22; // rdi
  void **v23; // rax
  int v24; // eax
  volatile signed __int32 *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  int v28; // edi
  unsigned int v29; // r8d
  const char *v30; // r9
  volatile signed __int32 *v31; // rdi
  int v32; // [rsp+20h] [rbp-99h]
  PSRWLOCK v33; // [rsp+80h] [rbp-39h] BYREF
  volatile signed __int32 *v34; // [rsp+88h] [rbp-31h]
  PSRWLOCK SRWLock[2]; // [rsp+90h] [rbp-29h] BYREF
  _DWORD v36[4]; // [rsp+A0h] [rbp-19h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v38; // [rsp+C0h] [rbp+7h]
  __int128 v39; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  LODWORD(SRWLock[0]) = 0;
  if ( !Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      a4);
  if ( (a1 & 2) != 0 )
  {
    if ( (unsigned __int64)qword_18013FA38 < 0x2B )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath);
    }
    else
    {
      v5 = &Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath;
      if ( (unsigned __int64)qword_18013FA38 > 7 )
        v5 = (void **)Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath;
      *(_QWORD *)&dwFlags = 43;
      memmove_0(v5, L"C:\\Data\\Test\\Bin\\TestConsentStorageDatabase", 0x56u);
      *((_WORD *)v5 + 43) = 0;
    }
  }
  if ( (a2 & 1) != 0 )
  {
    v6 = &v33;
    v7 = 1;
    v8 = 0;
  }
  else
  {
    v8 = &Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock;
    AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock);
    v6 = SRWLock;
    v7 = 2;
  }
  SRWLock[1] = v8;
  *v6 = 0;
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
  }
  if ( (v7 & 1) != 0 )
  {
    v7 &= ~1u;
    if ( v33 )
      ReleaseSRWLockExclusive(v33);
  }
  if ( WaitForSingleObject(
         Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady,
         0) )
  {
    std::make_shared<StateRepository::Database,>(&v33);
    if ( (a2 & 2) == 0 )
    {
      Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetRuntimeTargetSchemaVersion();
      v12 = Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance();
      v14 = StateRepository::Initialize(v13, *((_QWORD *)v12 + 1));
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
          (const char *)(unsigned int)v14,
          v32);
    }
    StorageDatabaseDirectory = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(
                                 Src,
                                 v9,
                                 v10,
                                 v11);
    if ( (unsigned __int64)StorageDatabaseDirectory[3] > 7 )
      StorageDatabaseDirectory = (void **)*StorageDatabaseDirectory;
    DirectoryW = CreateDirectoryW((LPCWSTR)StorageDatabaseDirectory, 0);
    std::wstring::~wstring(Src);
    if ( !DirectoryW && GetLastError() != 183 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        v19);
    if ( (a2 & 4) != 0 )
      goto LABEL_29;
    StorageDatabaseFullPath = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(
                                Src,
                                v17,
                                v18,
                                v19);
    v7 |= 4u;
    if ( (unsigned __int64)StorageDatabaseFullPath[3] > 7 )
      StorageDatabaseFullPath = (void **)*StorageDatabaseFullPath;
    if ( !PathFileExistsW((LPCWSTR)StorageDatabaseFullPath) )
LABEL_29:
      v21 = 1;
    else
      v21 = 0;
    if ( (v7 & 4) != 0 )
      std::wstring::~wstring(Src);
    v22 = v33;
    v23 = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(
            Src,
            v17,
            v18,
            v19);
    if ( (unsigned __int64)v23[3] > 7 )
      v23 = (void **)*v23;
    v24 = StateRepository::Database::Open(v22, v23);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v24,
        v32);
    std::wstring::~wstring(Src);
    StateRepository::Database::SetCheckpointOnClose((StateRepository::Database *)v22, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
      LODWORD(v22[2].Ptr) = 1;
    v38 = 0;
    v39 = 0;
    v25 = v34;
    if ( v34 )
      _InterlockedIncrement(v34 + 2);
    Src[0] = v22;
    Src[1] = (void *)v25;
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::Initialize(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)Src,
      0);
    v36[0] = 616853135;
    v36[1] = 1199010983;
    v36[2] = -619739485;
    v36[3] = -217602342;
    v27 = StateRepository::Database::BeginTransaction(v22, v26, v36);
    v28 = v27;
    if ( v27 >= 0 )
      v28 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v27,
        v32);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v28,
        v32);
    Windows::Internal::CapabilityAccess::Desktop::Storage::Database::PrepareDatabase(v21, &v33);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)Src);
    if ( !SetEvent(Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v29, v30);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)Src);
    v31 = v34;
    if ( v34 )
    {
      if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( !_InterlockedDecrement(v31 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
  }
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
}

```

## disassembly

```asm
0x1800f6584  push    rbp
0x1800f6586  push    rbx
0x1800f6587  push    rsi
0x1800f6588  push    rdi
0x1800f6589  push    r14
0x1800f658b  lea     rbp, [rsp-37h]
0x1800f6590  sub     rsp, 0F0h
0x1800f6597  mov     rax, cs:__security_cookie
0x1800f659e  xor     rax, rsp
0x1800f65a1  mov     [rbp+57h+var_30], rax
0x1800f65a5  mov     r14d, edx
0x1800f65a8  mov     edi, ecx
0x1800f65aa  mov     dword ptr [rbp+57h+SRWLock], 0
0x1800f65b1  mov     eax, cs:?m_initState@GlobalManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState
0x1800f65b7  nop
0x1800f65b8  mov     rcx, [rbp+5Fh]; this
0x1800f65bc  cmp     eax, 1
0x1800f65bf  jb      loc_1800F68DF
0x1800f65c5  test    dil, 2
0x1800f65c9  jz      short loc_1800F6624
0x1800f65cb  mov     rax, cs:qword_18013FA38
0x1800f65d2  mov     edx, 2Bh ; '+'
0x1800f65d7  cmp     rax, rdx
0x1800f65da  jb      short loc_1800F6611
0x1800f65dc  lea     rbx, ?m_databaseRedirectedPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath
0x1800f65e3  cmp     rax, 7
0x1800f65e7  cmova   rbx, cs:?m_databaseRedirectedPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath
0x1800f65ef  mov     cs:dwFlags, rdx
0x1800f65f6  lea     r8d, [rdx+2Bh]; Size
0x1800f65fa  lea     rdx, aCDataTestBinTe; "C:\\Data\\Test\\Bin\\TestConsentStorage"...
0x1800f6601  mov     rcx, rbx; void *
0x1800f6604  call    memmove_0
0x1800f6609  xor     eax, eax
0x1800f660b  mov     [rbx+56h], ax
0x1800f660f  jmp     short loc_1800F6624
0x1800f6611  lea     r9, aCDataTestBinTe; "C:\\Data\\Test\\Bin\\TestConsentStorage"...
0x1800f6618  lea     rcx, ?m_databaseRedirectedPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath
0x1800f661f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800f6624  test    r14b, 1
0x1800f6628  jz      short loc_1800F6637
0x1800f662a  lea     rax, [rbp+57h+var_90]
0x1800f662e  mov     esi, 1
0x1800f6633  xor     ebx, ebx
0x1800f6635  jmp     short loc_1800F6650
0x1800f6637  lea     rbx, ?m_databaseLock@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock
0x1800f663e  mov     rcx, rbx; SRWLock
0x1800f6641  call    cs:__imp_AcquireSRWLockExclusive
0x1800f6647  lea     rax, [rbp+57h+SRWLock]
0x1800f664b  mov     esi, 2
0x1800f6650  mov     [rbp+57h+var_78], rbx
0x1800f6654  mov     qword ptr [rax], 0
0x1800f665b  test    sil, 2
0x1800f665f  jz      short loc_1800F6673
0x1800f6661  and     esi, 0FFFFFFFDh
0x1800f6664  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800f6668  test    rcx, rcx
0x1800f666b  jz      short loc_1800F6673
0x1800f666d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6673  test    sil, 1
0x1800f6677  jz      short loc_1800F668B
0x1800f6679  and     esi, 0FFFFFFFEh
0x1800f667c  mov     rcx, [rbp+57h+var_90]; SRWLock
0x1800f6680  test    rcx, rcx
0x1800f6683  jz      short loc_1800F668B
0x1800f6685  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f668b  xor     edx, edx; dwMilliseconds
0x1800f668d  mov     rcx, cs:?m_databaseReady@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hHandle
0x1800f6694  call    cs:__imp_WaitForSingleObject
0x1800f669a  test    eax, eax
0x1800f669c  jz      loc_1800F68AC
0x1800f66a2  lea     rcx, [rbp+57h+var_90]
0x1800f66a6  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x1800f66ab  nop
0x1800f66ac  test    r14b, 2
0x1800f66b0  jnz     short loc_1800F66DA
0x1800f66b2  call    ?GetRuntimeTargetSchemaVersion@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAHXZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetRuntimeTargetSchemaVersion(void)
0x1800f66b7  call    ?Instance@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@KAPEAV1234567@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance(void)
0x1800f66bc  and     edi, 1
0x1800f66bf  add     edi, edi
0x1800f66c1  mov     [rsp+110h+var_98], edi
0x1800f66c5  mov     rdx, [rax+8]
0x1800f66c9  call    ?Initialize@StateRepository@@YAJP6AXXZPEBU_tlgProvider_t@@PEB_WP6AXHPEBD@Z4444P6AXPEAX3@ZP6AX53I@ZHP6AJW4Partition@1@PEAPEA_W@Z222W4InitializeFlags@1@@Z; StateRepository::Initialize(void (*)(void),_tlgProvider_t const *,wchar_t const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),int,long (*)(StateRepository::Partition,wchar_t * *),wchar_t const *,wchar_t const *,wchar_t const *,StateRepository::InitializeFlags)
0x1800f66ce  mov     rcx, [rbp+5Fh]; this
0x1800f66d2  test    eax, eax
0x1800f66d4  js      loc_1800F68F1
0x1800f66da  lea     rcx, [rbp+57h+Src]; Src
0x1800f66de  call    ?GetStorageDatabaseDirectory@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(void)
0x1800f66e3  cmp     qword ptr [rax+18h], 7
0x1800f66e8  jbe     short loc_1800F66ED
0x1800f66ea  mov     rax, [rax]
0x1800f66ed  xor     edx, edx; lpSecurityAttributes
0x1800f66ef  mov     rcx, rax; lpPathName
0x1800f66f2  call    cs:__imp_CreateDirectoryW
0x1800f66f8  mov     edi, eax
0x1800f66fa  lea     rcx, [rbp+57h+Src]
0x1800f66fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f6703  test    edi, edi
0x1800f6705  jnz     short loc_1800F6718
0x1800f6707  call    cs:__imp_GetLastError
0x1800f670d  cmp     eax, 0B7h
0x1800f6712  jnz     loc_1800F6906
0x1800f6718  test    r14b, 4
0x1800f671c  jnz     short loc_1800F6746
0x1800f671e  lea     rcx, [rbp+57h+Src]; Src
0x1800f6722  call    ?GetStorageDatabaseFullPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(void)
0x1800f6727  or      esi, 4
0x1800f672a  cmp     qword ptr [rax+18h], 7
0x1800f672f  jbe     short loc_1800F6734
0x1800f6731  mov     rax, [rax]
0x1800f6734  mov     rcx, rax; pszPath
0x1800f6737  call    cs:__imp_PathFileExistsW
0x1800f673d  test    eax, eax
0x1800f673f  jz      short loc_1800F6746
0x1800f6741  xor     r14d, r14d
0x1800f6744  jmp     short loc_1800F674C
0x1800f6746  mov     r14d, 1
0x1800f674c  test    sil, 4
0x1800f6750  jz      short loc_1800F675B
0x1800f6752  lea     rcx, [rbp+57h+Src]
0x1800f6756  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f675b  mov     rdi, [rbp+57h+var_90]
0x1800f675f  lea     rcx, [rbp+57h+Src]; Src
0x1800f6763  call    ?GetStorageDatabaseFullPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(void)
0x1800f6768  nop
0x1800f6769  cmp     qword ptr [rax+18h], 7
0x1800f676e  jbe     short loc_1800F6773
0x1800f6770  mov     rax, [rax]
0x1800f6773  mov     rdx, rax
0x1800f6776  mov     rcx, rdi
0x1800f6779  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x1800f677e  mov     rcx, [rbp+5Fh]; this
0x1800f6782  test    eax, eax
0x1800f6784  js      loc_1800F691C
0x1800f678a  lea     rcx, [rbp+57h+Src]
0x1800f678e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f6793  xor     edx, edx; bool
0x1800f6795  mov     rcx, rdi; this
0x1800f6798  call    ?SetCheckpointOnClose@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::SetCheckpointOnClose(bool)
0x1800f679d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800f67a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800f67a9  test    al, al
0x1800f67ab  jz      short loc_1800F67B4
0x1800f67ad  mov     dword ptr [rdi+10h], 1
0x1800f67b4  xorps   xmm0, xmm0
0x1800f67b7  movdqu  [rbp+57h+var_50], xmm0
0x1800f67bc  movdqu  [rbp+57h+var_40], xmm0
0x1800f67c1  mov     rax, [rbp+57h+var_88]
0x1800f67c5  test    rax, rax
0x1800f67c8  jz      short loc_1800F67CE
0x1800f67ca  lock inc dword ptr [rax+8]
0x1800f67ce  mov     [rbp+57h+Src], rdi
0x1800f67d2  mov     [rbp+57h+var_58], rax
0x1800f67d6  xor     edx, edx; unsigned int
0x1800f67d8  lea     rcx, [rbp+57h+Src]; this
0x1800f67dc  call    ?Initialize@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@AEAAXI@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::Initialize(uint)
0x1800f67e1  nop
0x1800f67e2  mov     [rbp+57h+var_70], 24C46E8Fh
0x1800f67e9  mov     [rbp+57h+var_6C], 477774A7h
0x1800f67f0  mov     [rbp+57h+var_68], 0DB0F86A3h
0x1800f67f7  mov     [rbp+57h+var_64], 0F307A6DAh
0x1800f67fe  lea     r8, [rbp+57h+var_70]
0x1800f6802  mov     rcx, rdi
0x1800f6805  call    ?BeginTransaction@Database@StateRepository@@QEAAJW4BeginTransactionLock@12@AEBU_GUID@@P6AJPEAX@Z2@Z; StateRepository::Database::BeginTransaction(StateRepository::Database::BeginTransactionLock,_GUID const &,long (*)(void *),void *)
0x1800f680a  mov     edi, eax
0x1800f680c  test    eax, eax
0x1800f680e  jns     short loc_1800F682A
0x1800f6810  mov     rcx, [rbp+5Fh]; this
0x1800f6814  mov     r9d, eax; char *
0x1800f6817  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f681e  mov     edx, 1F1h; void *
0x1800f6823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6828  jmp     short loc_1800F682C
0x1800f682a  xor     edi, edi
0x1800f682c  mov     rcx, [rbp+5Fh]; this
0x1800f6830  test    edi, edi
0x1800f6832  js      loc_1800F6931
0x1800f6838  lea     rdx, [rbp+57h+var_90]
0x1800f683c  mov     ecx, r14d
0x1800f683f  call    ?PrepareDatabase@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXIAEBV?$shared_ptr@VDatabase@StateRepository@@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::PrepareDatabase(uint,std::shared_ptr<StateRepository::Database> const &)
0x1800f6844  lea     rcx, [rbp+57h+Src]; this
0x1800f6848  call    ?CommitTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(void)
0x1800f684d  mov     rcx, cs:?m_databaseReady@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x1800f6854  call    cs:__imp_SetEvent
0x1800f685a  mov     rcx, [rbp+5Fh]; this
0x1800f685e  test    eax, eax
0x1800f6860  jz      short loc_1800F68D4
0x1800f6862  lea     rcx, [rbp+57h+Src]; this
0x1800f6866  call    ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800f686b  nop
0x1800f686c  mov     rdi, [rbp+57h+var_88]
0x1800f6870  test    rdi, rdi
0x1800f6873  jz      short loc_1800F68AC
0x1800f6875  or      esi, 0FFFFFFFFh
0x1800f6878  mov     eax, esi
0x1800f687a  lock xadd [rdi+8], eax
0x1800f687f  add     eax, esi
0x1800f6881  jnz     short loc_1800F68AC
0x1800f6883  mov     rax, [rdi]
0x1800f6886  mov     rcx, rdi
0x1800f6889  mov     rax, [rax]
0x1800f688c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6891  mov     eax, esi
0x1800f6893  lock xadd [rdi+0Ch], eax
0x1800f6898  add     eax, esi
0x1800f689a  jnz     short loc_1800F68AC
0x1800f689c  mov     rax, [rdi]
0x1800f689f  mov     rcx, rdi
0x1800f68a2  mov     rax, [rax+8]
0x1800f68a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f68ab  nop
0x1800f68ac  test    rbx, rbx
0x1800f68af  jz      short loc_1800F68BA
0x1800f68b1  mov     rcx, rbx; SRWLock
0x1800f68b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f68ba  mov     rcx, [rbp+57h+var_30]
0x1800f68be  xor     rcx, rsp; StackCookie
0x1800f68c1  call    __security_check_cookie
0x1800f68c6  add     rsp, 0F0h
0x1800f68cd  pop     r14
0x1800f68cf  pop     rdi
0x1800f68d0  pop     rsi
0x1800f68d1  pop     rbx
0x1800f68d2  pop     rbp
0x1800f68d3  retn
0x1800f68d4  mov     edx, 0A01h; void *
0x1800f68d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f68df  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f68e6  mov     edx, 181h; void *
0x1800f68eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800f68f1  mov     r9d, eax; char *
0x1800f68f4  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f68fb  mov     edx, 1BAh; void *
0x1800f6900  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6906  mov     rcx, [rbp+5Fh]; this
0x1800f690a  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6911  mov     edx, 1C1h; void *
0x1800f6916  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800f691c  mov     r9d, eax; char *
0x1800f691f  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6926  mov     edx, 1CDh; void *
0x1800f692b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6931  mov     r9d, edi; char *
0x1800f6934  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f693b  mov     edx, 1E5h; void *
0x1800f6940  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
