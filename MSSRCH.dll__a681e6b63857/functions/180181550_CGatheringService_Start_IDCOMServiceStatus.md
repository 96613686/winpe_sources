# CGatheringService::Start(IDCOMServiceStatus *)

- ea: `0x180181550`
- end: `0x180181dc9`
- name: `?Start@CGatheringService@@UEAAJPEAUIDCOMServiceStatus@@@Z`
- size: `2169`
- prototype: `__int64 __fastcall(CGatheringService *__hidden this, struct IDCOMServiceStatus *)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801429c0`

## callees

- `0x18000f880`
- `0x180013d40`
- `0x180014ff0`
- `0x180019bb0`
- `0x180022710`
- `0x1800269b0`
- `0x180026b58`
- `0x18002dc6c`
- `0x180052460`
- `0x180056610`
- `0x18005edc4`
- `0x180061f78`
- `0x1800758b0`
- `0x180079c44`
- `0x180079d34`
- `0x1800b2d2c`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800d057c`
- `0x1800d34f4`
- `0x1800d3584`
- `0x1800e4dac`
- `0x1800eb1b0`
- `0x1800f84fc`
- `0x1800fa9f0`
- `0x1801244c0`
- `0x18012540e`
- `0x1801490c8`
- `0x18016951c`
- `0x18017c55c`
- `0x18017f890`
- `0x18018146c`
- `0x180181550`
- `0x18018203c`
- `0x180196dc8`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180181d3a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180181d3a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180181c51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180181c51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180181caf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180181caf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181ca2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181ca2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180181898`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180181898`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018165a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018165a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180181bba`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180181bba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180181bd7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180181bd7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181976`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801819ba`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181a01`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181a48`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181976`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801819ba`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181a01`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180181a48`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180181bf0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180181bf0`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180181ab2`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180181af1`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180181ab2`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180181af1`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180181b45`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180181b45`

## string_xrefs

- `0x180181c43`: `Local\WindowsSearchService_EfsRegKeysMutex`

## pseudocode

```c
__int64 __fastcall CGatheringService::Start(CGatheringService *this, struct IDCOMServiceStatus *a2)
{
  CSyncReadWrite *v4; // rbx
  CLanguageResourcePools **v5; // r14
  HRESULT Instance; // eax
  unsigned int v7; // esi
  CLanguageResourcePools *v9; // rsi
  struct _ACL *v10; // r14
  const wchar_t *v11; // r8
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, DWORD *); // r14
  __int64 (__fastcall *v14)(_QWORD, GUID *, DWORD *); // rsi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  int started; // eax
  const char *Error; // r14
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 i; // r12
  signed int v25; // esi
  HANDLE v26; // rax
  PACL v27; // rcx
  CGatheringService *v28; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  DWORD cbSid[2]; // [rsp+30h] [rbp-D0h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+40h] [rbp-C0h] BYREF
  char *v34; // [rsp+58h] [rbp-A8h]
  char *v35; // [rsp+60h] [rbp-A0h]
  _BYTE v36[8]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h]
  _DWORD pSid[17]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v39[68]; // [rsp+154h] [rbp+54h] BYREF
  _BYTE v40[68]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v41[2212]; // [rsp+1DCh] [rbp+DCh] BYREF
  _EXPLICIT_ACCESS_W pExplicitAccess[4]; // [rsp+A80h] [rbp+980h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B40h] [rbp+A40h] BYREF
  __int64 v44; // [rsp+B60h] [rbp+A60h]
  wil::details::in1diag3 *retaddr; // [rsp+BA8h] [rbp+AA8h]

  v4 = (CGatheringService *)((char *)this + 3656);
  v34 = (char *)this + 3656;
  CSyncReadWrite::GetReadAccess((CGatheringService *)((char *)this + 3656));
  cbSid[0] = 0;
  if ( !CRegistry::GetValue(this, L"RegVersion", cbSid) || HIWORD(cbSid[0]) != 1026 )
  {
    _o__ultow_s(67239936, pSecurityDescriptor, 20);
    CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)pSid, *((struct CEventLog **)this + 49));
    CSearchEventEntry::ReportError((CSearchEventEntry *)pSid, 0xC0000BDA, pSecurityDescriptor, 0);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x3BA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)0x8007064DLL,
      ppv);
    CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)pSid);
    CSyncReadWrite::ReleaseReadAccess(v4);
    return 2147944013LL;
  }
  TLMString<64,64,32767>::TLMString<64,64,32767>(v36, (char *)this + 760);
  AppendBackSlashIf((struct CLMString *)v36);
  CLMString::Append((CLMString *)v36, L"lnk", 0xFFFFFFFF);
  CLMString::Append((CLMString *)v36, L"*.tmp", 0xFFFFFFFF);
  RemovePattern(lpFileName);
  v35 = (char *)this + 208;
  CSyncReadWrite::GetWriteAccess((CGatheringService *)((char *)this + 208));
  v5 = (CLanguageResourcePools **)((char *)this + 3992);
  Instance = CoCreateInstance(
               &CLSID_CGatherLanguageResourcePool,
               0,
               0x17u,
               &GUID_c7310685_ac80_11d1_8df3_00c04fb6ef4f,
               (LPVOID *)this + 499);
  v7 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)Instance,
      ppva);
    CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
    CSyncReadWrite::ReleaseReadAccess(v4);
    return v7;
  }
  v9 = *v5;
  v10 = (struct _ACL *)((char *)*v5 + 32);
  pDacl = v10;
  CSyncReadWrite::GetWriteAccess((CSyncReadWrite *)v10);
  v7 = CLanguageResourcePools::lokInitialize(v9);
  CSyncReadWrite::ReleaseWriteAccess((CSyncReadWrite *)v10);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v7,
      ppva);
    CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
    CSyncReadWrite::ReleaseReadAccess(v4);
    return v7;
  }
  v12 = CGatherApplicationCollection::Init(*((CGatherApplicationCollection **)this + 47), this, v11, a2);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)v12,
      ppva);
    CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
    CSyncReadWrite::ReleaseReadAccess(v4);
    return v7;
  }
  if ( *((_BYTE *)this + 368) )
  {
    *(_QWORD *)cbSid = 0;
    v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, DWORD *))*((_QWORD *)this + 47);
    v14 = **v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(cbSid);
    v15 = v14(v13, &GUID_b05651e5_9b10_425e_b616_1fcd828db3b1, cbSid);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v15,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(cbSid);
      CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
      CSyncReadWrite::ReleaseReadAccess(v4);
      return v7;
    }
    v16 = DefaultCatalogCreator::Create(*(struct IGatherApplications2 **)cbSid);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v16,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(cbSid);
      CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
      CSyncReadWrite::ReleaseReadAccess(v4);
      return v7;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    {
      v17 = winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(&pDacl);
      winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchConfigManager>::IsNewCatalogSetup(v17);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&pDacl);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(cbSid);
  }
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
  {
    v18 = CGatheringService::SetupPerUserCatalog(this);
    v7 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v18,
        ppva);
      CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
      CSyncReadWrite::ReleaseReadAccess(v4);
      return v7;
    }
  }
  started = CRobotThreadPool::SetThreads(*((CRobotThreadPool **)this + 488), *((_DWORD *)this + 971));
  LODWORD(Error) = started;
  v21 = retaddr;
  if ( started >= 0 )
  {
    started = TThread<CTimerThread>::StartThread(*((LPVOID *)this + 498));
    LODWORD(Error) = started;
    v21 = retaddr;
    if ( started >= 0 )
    {
      memset_0(pSid, 0, 0x110u);
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid) )
      {
        Error = (const char *)(unsigned int)ResultFromLastError();
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x469,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          Error,
          ppva);
      }
      cbSid[0] = 68;
      if ( (int)Error >= 0 && !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v39, cbSid) )
      {
        Error = (const char *)(unsigned int)ResultFromLastError();
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x472,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          Error,
          ppva);
      }
      cbSid[0] = 68;
      if ( (int)Error >= 0 && !CreateWellKnownSid(WinBuiltinPowerUsersSid, 0, v40, cbSid) )
      {
        Error = (const char *)(unsigned int)ResultFromLastError();
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x47B,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          Error,
          ppva);
      }
      cbSid[0] = 68;
      if ( (int)Error >= 0 && !CreateWellKnownSid(WinBuiltinUsersSid, 0, v41, cbSid) )
      {
        Error = (const char *)(unsigned int)ResultFromLastError();
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x484,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          Error,
          ppva);
      }
      pDacl = 0;
      if ( (int)Error >= 0 )
      {
        memset_0(pExplicitAccess, 0, sizeof(pExplicitAccess));
        BuildExplicitAccessWithNameW(pExplicitAccess, 0, 0x1F0001u, GRANT_ACCESS, 3u);
        pExplicitAccess[0].Trustee.TrusteeForm = TRUSTEE_IS_SID;
        pExplicitAccess[0].Trustee.ptstrName = (LPWCH)pSid;
        v23 = 1;
        for ( i = 1; i != 4; ++i )
        {
          BuildExplicitAccessWithNameW(&pExplicitAccess[v23], 0, 0x100001u, GRANT_ACCESS, 3u);
          pExplicitAccess[v23].Trustee.TrusteeForm = TRUSTEE_IS_SID;
          pExplicitAccess[v23++].Trustee.ptstrName = (LPWCH)&pSid[17 * i];
        }
        *(_QWORD *)&MutexAttributes.nLength = &pDacl;
        MutexAttributes.lpSecurityDescriptor = 0;
        LOBYTE(MutexAttributes.bInheritHandle) = 1;
        v25 = SetEntriesInAclW(4u, pExplicitAccess, 0, (PACL *)&MutexAttributes.lpSecurityDescriptor);
        wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&MutexAttributes);
        if ( v25 )
        {
          if ( v25 > 0 )
            LODWORD(Error) = (unsigned __int16)v25 | 0x80070000;
          else
            LODWORD(Error) = v25;
        }
        if ( (int)Error < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4A2,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)Error,
            ppva);
      }
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      v44 = 0;
      if ( (int)Error >= 0 )
      {
        if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
          || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)
          || !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u) )
        {
          Error = (const char *)(unsigned int)ResultFromLastError();
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x4AD,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            Error,
            ppva);
        }
        if ( (int)Error >= 0 )
        {
          *(_QWORD *)&MutexAttributes.nLength = 24;
          *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
          MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor;
          v26 = CreateMutexW(&MutexAttributes, 0, L"Local\\WindowsSearchService_EfsRegKeysMutex");
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            (char *)this + 4160,
            v26);
          if ( ((*((_QWORD *)this + 520) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            Error = (const char *)(unsigned int)ResultFromLastError();
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x4BB,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
              Error,
              ppva);
          }
        }
      }
      v27 = pDacl;
      pDacl = 0;
      if ( v27 )
        LocalFree(v27);
      goto LABEL_56;
    }
    v22 = 1115;
  }
  else
  {
    v22 = 1109;
  }
  wil::details::in1diag3::_Log_Hr(
    v21,
    (void *)v22,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
    (const char *)(unsigned int)started,
    ppva);
LABEL_56:
  SetEvent(*((HANDLE *)this + 517));
  if ( (int)Error >= 0 )
  {
    CGatheringService::CleanupPreviousTempPath(this);
  }
  else
  {
    CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)pSid, *((struct CEventLog **)this + 49));
    CSearchEventEntry::SetError((CSearchEventEntry *)pSid, (int)Error);
    CSearchEventEntry::ReportError((CSearchEventEntry *)pSid, 0xC0000BD6, 0);
    CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)pSid);
  }
  CGatheringService::FlushWorkingSet(v28);
  CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 208));
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v36);
  CSyncReadWrite::ReleaseReadAccess(v4);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180181550  mov     [rsp-8+arg_10], rbx
0x180181555  push    rbp
0x180181556  push    rsi
0x180181557  push    rdi
0x180181558  push    r12
0x18018155a  push    r13
0x18018155c  push    r14
0x18018155e  push    r15
0x180181560  lea     rbp, [rsp-0A70h]
0x180181568  sub     rsp, 0B70h
0x18018156f  mov     rax, cs:__security_cookie
0x180181576  xor     rax, rsp
0x180181579  mov     [rbp+0AA0h+var_38], rax
0x180181580  mov     r12, rdx
0x180181583  mov     r15, rcx
0x180181586  lea     rbx, [rcx+0E48h]
0x18018158d  mov     [rsp+0BA0h+var_B48], rbx
0x180181592  mov     rcx, rbx; this
0x180181595  call    ?GetReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetReadAccess(void)
0x18018159a  nop
0x18018159b  xor     r13d, r13d
0x18018159e  mov     [rsp+0BA0h+cbSid], r13d
0x1801815a3  lea     r8, [rsp+0BA0h+cbSid]; unsigned int *
0x1801815a8  lea     rdx, aRegversion; "RegVersion"
0x1801815af  mov     rcx, r15; this
0x1801815b2  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1801815b7  test    eax, eax
0x1801815b9  jz      loc_180181D24
0x1801815bf  mov     eax, [rsp+0BA0h+cbSid]
0x1801815c3  shr     eax, 10h
0x1801815c6  mov     ecx, 402h
0x1801815cb  cmp     ax, cx
0x1801815ce  jnz     loc_180181D24
0x1801815d4  lea     rdx, [r15+2F8h]
0x1801815db  lea     rcx, [rsp+0BA0h+var_B30]
0x1801815e0  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x1801815e5  nop
0x1801815e6  lea     rcx, [rsp+0BA0h+var_B30]; struct CLMString *
0x1801815eb  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x1801815f0  or      edi, 0FFFFFFFFh
0x1801815f3  mov     r8d, edi; unsigned int
0x1801815f6  lea     rdx, aLnk; "lnk"
0x1801815fd  lea     rcx, [rsp+0BA0h+var_B30]; this
0x180181602  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180181607  mov     r8d, edi; unsigned int
0x18018160a  lea     rdx, aTmp_0; "*.tmp"
0x180181611  lea     rcx, [rsp+0BA0h+var_B30]; this
0x180181616  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18018161b  mov     rcx, [rsp+0BA0h+lpFileName]; lpFileName
0x180181620  call    ?RemovePattern@@YAXPEB_W@Z; RemovePattern(wchar_t const *)
0x180181625  lea     rdi, [r15+0D0h]
0x18018162c  mov     [rsp+0BA0h+var_B40], rdi
0x180181631  mov     rcx, rdi; this
0x180181634  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x180181639  nop
0x18018163a  lea     r14, [r15+0F98h]
0x180181641  mov     qword ptr [rsp+0BA0h+ppv], r14; int
0x180181646  lea     r9, _GUID_c7310685_ac80_11d1_8df3_00c04fb6ef4f; riid
0x18018164d  xor     edx, edx; pUnkOuter
0x18018164f  lea     r8d, [r13+17h]; dwClsContext
0x180181653  lea     rcx, CLSID_CGatherLanguageResourcePool; rclsid
0x18018165a  call    cs:__imp_CoCreateInstance
0x180181660  mov     esi, eax
0x180181662  test    eax, eax
0x180181664  jns     short loc_1801816A6
0x180181666  mov     rcx, [rbp+0AA8h]; this
0x18018166d  mov     r9d, eax; char *
0x180181670  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180181677  mov     edx, 3D4h; void *
0x18018167c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180181681  nop
0x180181682  mov     rcx, rdi; this
0x180181685  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x18018168a  nop
0x18018168b  lea     rcx, [rsp+0BA0h+var_B30]
0x180181690  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180181695  nop
0x180181696  mov     rcx, rbx; this
0x180181699  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x18018169e  nop
0x18018169f  mov     eax, esi
0x1801816a1  jmp     loc_180181D9F
0x1801816a6  mov     rsi, [r14]
0x1801816a9  lea     r14, [rsi+20h]
0x1801816ad  mov     [rsp+0BA0h+pDacl], r14
0x1801816b2  mov     rcx, r14; this
0x1801816b5  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1801816ba  nop
0x1801816bb  mov     rcx, rsi; this
0x1801816be  call    ?lokInitialize@CLanguageResourcePools@@QEAAJXZ; CLanguageResourcePools::lokInitialize(void)
0x1801816c3  mov     esi, eax
0x1801816c5  mov     rcx, r14; this
0x1801816c8  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1801816cd  nop
0x1801816ce  test    esi, esi
0x1801816d0  jns     short loc_18018170D
0x1801816d2  mov     rcx, [rbp+0AA8h]; this
0x1801816d9  mov     r9d, esi; char *
0x1801816dc  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801816e3  mov     edx, 3D7h; void *
0x1801816e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801816ed  nop
0x1801816ee  mov     rcx, rdi; this
0x1801816f1  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1801816f6  nop
0x1801816f7  lea     rcx, [rsp+0BA0h+var_B30]
0x1801816fc  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180181701  nop
0x180181702  mov     rcx, rbx; this
0x180181705  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x18018170a  nop
0x18018170b  jmp     short loc_18018169F
0x18018170d  mov     r9, r12; struct IDCOMServiceStatus *
0x180181710  mov     rdx, r15; struct CRegistry *
0x180181713  mov     rcx, [r15+178h]; this
0x18018171a  call    ?Init@CGatherApplicationCollection@@QEAAJPEAVCRegistry@@PEB_WPEAUIDCOMServiceStatus@@@Z; CGatherApplicationCollection::Init(CRegistry *,wchar_t const *,IDCOMServiceStatus *)
0x18018171f  mov     esi, eax
0x180181721  test    eax, eax
0x180181723  jns     short loc_180181763
0x180181725  mov     rcx, [rbp+0AA8h]; this
0x18018172c  mov     r9d, eax; char *
0x18018172f  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180181736  mov     edx, 3DAh; void *
0x18018173b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180181740  nop
0x180181741  mov     rcx, rdi; this
0x180181744  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x180181749  nop
0x18018174a  lea     rcx, [rsp+0BA0h+var_B30]
0x18018174f  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180181754  nop
0x180181755  mov     rcx, rbx; this
0x180181758  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x18018175d  nop
0x18018175e  jmp     loc_18018169F
0x180181763  cmp     [r15+170h], r13b
0x18018176a  jz      loc_180181884
0x180181770  mov     qword ptr [rsp+0BA0h+cbSid], r13
0x180181775  mov     r14, [r15+178h]
0x18018177c  mov     rax, [r14]
0x18018177f  mov     rsi, [rax]
0x180181782  lea     rcx, [rsp+0BA0h+cbSid]
0x180181787  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18018178c  lea     r8, [rsp+0BA0h+cbSid]
0x180181791  lea     rdx, _GUID_b05651e5_9b10_425e_b616_1fcd828db3b1
0x180181798  mov     rcx, r14
0x18018179b  mov     rax, rsi
0x18018179e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801817a3  mov     esi, eax
0x1801817a5  test    eax, eax
0x1801817a7  jns     short loc_1801817F2
0x1801817a9  mov     rcx, [rbp+0AA8h]; this
0x1801817b0  mov     r9d, eax; char *
0x1801817b3  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801817ba  mov     edx, 3E2h; void *
0x1801817bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801817c4  nop
0x1801817c5  lea     rcx, [rsp+0BA0h+cbSid]
0x1801817ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801817cf  nop
0x1801817d0  mov     rcx, rdi; this
0x1801817d3  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1801817d8  nop
0x1801817d9  lea     rcx, [rsp+0BA0h+var_B30]
0x1801817de  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801817e3  nop
0x1801817e4  mov     rcx, rbx; this
0x1801817e7  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x1801817ec  nop
0x1801817ed  jmp     loc_18018169F
0x1801817f2  mov     rcx, qword ptr [rsp+0BA0h+cbSid]; struct IGatherApplications2 *
0x1801817f7  call    ?Create@DefaultCatalogCreator@@SAJPEAUIGatherApplications2@@@Z; DefaultCatalogCreator::Create(IGatherApplications2 *)
0x1801817fc  mov     esi, eax
0x1801817fe  test    eax, eax
0x180181800  jns     short loc_18018184B
0x180181802  mov     rcx, [rbp+0AA8h]; this
0x180181809  mov     r9d, eax; char *
0x18018180c  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180181813  mov     edx, 3E3h; void *
0x180181818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018181d  nop
0x18018181e  lea     rcx, [rsp+0BA0h+cbSid]
0x180181823  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180181828  nop
0x180181829  mov     rcx, rdi; this
0x18018182c  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x180181831  nop
0x180181832  lea     rcx, [rsp+0BA0h+var_B30]
0x180181837  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18018183c  nop
0x18018183d  mov     rcx, rbx; this
0x180181840  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x180181845  nop
0x180181846  jmp     loc_18018169F
0x18018184b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180181852  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180181857  test    al, al
0x180181859  jz      short loc_18018187A
0x18018185b  lea     rcx, [rsp+0BA0h+pDacl]
0x180181860  call    ?GetInstance@SemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@SA?AU12345@XZ; winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(void)
0x180181865  nop
0x180181866  mov     rcx, rax
0x180181869  call    ?IsNewCatalogSetup@?$consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager@UISemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchConfigManager>::IsNewCatalogSetup(bool)
0x18018186e  nop
0x18018186f  lea     rcx, [rsp+0BA0h+pDacl]; this
0x180181874  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180181879  nop
0x18018187a  lea     rcx, [rsp+0BA0h+cbSid]
0x18018187f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180181884  xor     r9d, r9d; Context
0x180181887  xor     r8d, r8d; Parameter
0x18018188a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180181891  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180181898  call    cs:__imp_InitOnceExecuteOnce
0x18018189e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r13b; bool g_isPerUserCatalogEnabled
0x1801818a5  jz      short loc_1801818F3
0x1801818a7  mov     rcx, r15; this
0x1801818aa  call    ?SetupPerUserCatalog@CGatheringService@@QEAAJXZ; CGatheringService::SetupPerUserCatalog(void)
0x1801818af  mov     esi, eax
0x1801818b1  test    eax, eax
0x1801818b3  jns     short loc_1801818F3
0x1801818b5  mov     rcx, [rbp+0AA8h]; this
0x1801818bc  mov     r9d, eax; char *
0x1801818bf  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801818c6  mov     edx, 44Fh; void *
0x1801818cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801818d0  nop
0x1801818d1  mov     rcx, rdi; this
0x1801818d4  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1801818d9  nop
0x1801818da  lea     rcx, [rsp+0BA0h+var_B30]
0x1801818df  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801818e4  nop
0x1801818e5  mov     rcx, rbx; this
0x1801818e8  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x1801818ed  nop
0x1801818ee  jmp     loc_18018169F
0x1801818f3  mov     edx, [r15+0F2Ch]; unsigned int
0x1801818fa  mov     rcx, [r15+0F40h]; this
0x180181901  call    ?SetThreads@CRobotThreadPool@@QEAAJK@Z; CRobotThreadPool::SetThreads(ulong)
0x180181906  mov     r14d, eax
0x180181909  mov     rcx, [rbp+0AA8h]
0x180181910  test    eax, eax
0x180181912  jns     short loc_18018191B
0x180181914  mov     edx, 455h
0x180181919  jmp     short loc_18018193A
0x18018191b  mov     rcx, [r15+0F90h]; lpParameter
0x180181922  call    ?StartThread@?$TThread@VCTimerThread@@@@QEAAJK@Z; TThread<CTimerThread>::StartThread(ulong)
0x180181927  mov     r14d, eax
0x18018192a  mov     rcx, [rbp+0AA8h]; this
0x180181931  test    eax, eax
0x180181933  jns     short loc_18018194E
0x180181935  mov     edx, 45Bh; void *
0x18018193a  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180181941  mov     r9d, eax; char *
0x180181944  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180181949  jmp     loc_180181CA8
0x18018194e  xor     edx, edx; Val
0x180181950  mov     r8d, 110h; Size
0x180181956  lea     rcx, [rbp+0AA0h+pSid]; void *
0x18018195a  call    memset_0
0x18018195f  mov     esi, 44h ; 'D'
0x180181964  mov     [rsp+0BA0h+cbSid], esi
0x180181968  lea     r9, [rsp+0BA0h+cbSid]; cbSid
0x18018196d  lea     r8, [rbp+0AA0h+pSid]; pSid
0x180181971  xor     edx, edx; DomainSid
0x180181973  lea     ecx, [rsi-2Eh]; WellKnownSidType
0x180181976  call    cs:__imp_CreateWellKnownSid
0x18018197c  test    eax, eax
0x18018197e  jnz     short loc_1801819A3
0x180181980  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180181985  mov     r14d, eax
0x180181988  mov     rcx, [rbp+0AA8h]; this
0x18018198f  mov     r9d, eax; char *
0x180181992  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180181999  mov     edx, 469h; void *
0x18018199e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801819a3  mov     [rsp+0BA0h+cbSid], esi
0x1801819a7  test    r14d, r14d
0x1801819aa  js      short loc_1801819E7
0x1801819ac  lea     r9, [rsp+0BA0h+cbSid]; cbSid
0x1801819b1  lea     r8, [rbp+0AA0h+var_A4C]; pSid
0x1801819b5  xor     edx, edx; DomainSid
0x1801819b7  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1801819ba  call    cs:__imp_CreateWellKnownSid
0x1801819c0  test    eax, eax
0x1801819c2  jnz     short loc_1801819E7
0x1801819c4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801819c9  mov     r14d, eax
0x1801819cc  mov     rcx, [rbp+0AA8h]; this
0x1801819d3  mov     r9d, eax; char *
0x1801819d6  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801819dd  mov     edx, 472h; void *
0x1801819e2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801819e7  mov     [rsp+0BA0h+cbSid], esi
0x1801819eb  test    r14d, r14d
0x1801819ee  js      short loc_180181A2E
0x1801819f0  lea     r9, [rsp+0BA0h+cbSid]; cbSid
0x1801819f5  lea     r8, [rbp+0AA0h+var_A08]; pSid
0x1801819fc  xor     edx, edx; DomainSid
  ... truncated ...
```
