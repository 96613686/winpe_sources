# Uev::Repository::IsFolderOwnerTheCurrentUser(boost::filesystem::path const &)

- ea: `0x14008ba34`
- end: `0x14008c09a`
- name: `?IsFolderOwnerTheCurrentUser@Repository@Uev@@AEBA_NAEBVpath@filesystem@boost@@@Z`
- size: `1638`
- prototype: `bool(Uev::Repository *__hidden this, const struct boost::filesystem::path *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008a6fc`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d260`
- `0x140010a70`
- `0x1400131ec`
- `0x1400133e4`
- `0x140014a10`
- `0x140015190`
- `0x14001a310`
- `0x140020568`
- `0x1400205f4`
- `0x140023dd4`
- `0x1400245f0`
- `0x1400259f8`
- `0x140046e04`
- `0x140046f94`
- `0x14008ba34`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14008bbdb`
- `ADVAPI32!OpenProcessToken` at `0x14008bbdb`
- `ADVAPI32!GetTokenInformation` at `0x14008bc3b`
- `ADVAPI32!GetTokenInformation` at `0x14008bc3b`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14008bbad`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14008bbad`
- `KERNEL32!GetCurrentProcess` at `0x14008bbc6`
- `KERNEL32!GetCurrentProcess` at `0x14008bbc6`
- `KERNEL32!GetLastError` at `0x14008bc94`
- `KERNEL32!GetLastError` at `0x14008bd86`
- `KERNEL32!GetLastError` at `0x14008bc94`
- `KERNEL32!GetLastError` at `0x14008bd86`
- `KERNEL32!LocalFree` at `0x14008be4d`
- `KERNEL32!LocalFree` at `0x14008be4d`

## string_xrefs

- `0x14008c069`: `Attempting to use an invalid handle.`
- `0x14008be91`: `Repository::IsFolderOwnerTheCurrentUser() - GetNamedSecurityInfo failed with error `
- `0x14008bda6`: `Repository::IsFolderOwnerTheCurrentUser() - OpenProcessToken failed with error `
- `0x14008bcb4`: `Repository::IsFolderOwnerTheCurrentUser() - GetTokenInformation failed with error `
- `0x14008baef`: `Failed to read RepositoryOwnerCheckEnabled from registry.  Using default value of not enabled.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char __fastcall Uev::Repository::IsFolderOwnerTheCurrentUser(
        Uev::Repository *this,
        const struct boost::filesystem::path *a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rbx
  __int128 *v5; // r9
  char v6; // si
  DWORD NamedSecurityInfoW; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v9; // rbx
  _QWORD *v10; // rdi
  _QWORD *v11; // rbx
  void *v12; // rax
  __int64 v13; // rax
  __int128 v14; // xmm6
  __m128i v15; // xmm7
  __int128 *v16; // r9
  _QWORD *v17; // rbx
  void *v18; // rax
  __int64 v19; // rax
  __int128 v20; // xmm6
  __m128i v21; // xmm7
  __int128 *v22; // r9
  _QWORD *v23; // rbx
  void *v24; // rax
  __int64 v25; // rax
  __int128 v26; // xmm6
  __m128i v27; // xmm7
  __int128 *v28; // r9
  __int64 v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rdx
  DWORD LastError; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v37; // [rsp+50h] [rbp-B8h] BYREF
  __m128i v38; // [rsp+60h] [rbp-A8h]
  __int128 v39; // [rsp+70h] [rbp-98h] BYREF
  __int64 (__fastcall *v40)(); // [rsp+80h] [rbp-88h]
  unsigned __int64 v41; // [rsp+88h] [rbp-80h]
  HANDLE v42; // [rsp+90h] [rbp-78h] BYREF
  __int128 pExceptionObject; // [rsp+98h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-60h]
  __int64 v45; // [rsp+B0h] [rbp-58h]
  _QWORD *v46; // [rsp+D8h] [rbp-30h]
  _BYTE v47[272]; // [rsp+E8h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+1F8h] [rbp+F0h] BYREF
  PSID ppsidOwner; // [rsp+200h] [rbp+F8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+208h] [rbp+100h] BYREF
  _BYTE v51[4]; // [rsp+210h] [rbp+108h] BYREF
  DWORD ReturnLength; // [rsp+214h] [rbp+10Ch] BYREF
  __int64 v53; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v54[128]; // [rsp+228h] [rbp+120h] BYREF

  Uev::ScopeTracker::ScopeTracker(
    (Uev::ScopeTracker *)v54,
    L"CscChangeManager",
    L"Repository::IsFolderOwnerTheCurrentUser()");
  v53 = 0;
  v51[0] = 0;
  v3 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
  if ( !(unsigned __int8)Uev::Setting<bool>::Get(v3 + 13792, v51, &v53)
    && (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 4) != 0 )
  {
    v4 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v39 = 0;
    v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,wchar_t *>(
      &v39,
      L"Failed to read RepositoryOwnerCheckEnabled from registry.  Using default value of not enabled.",
      0x5Eu);
    pExceptionObject = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, L"CscChangeManager", 0x10u);
    v5 = &v39;
    if ( v41 > 7 )
      v5 = (__int128 *)v39;
    Uev::LogImpl::Write(*v4, 4, &pExceptionObject, v5);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    std::wstring::_Tidy_deallocate(&v39);
  }
  if ( !v51[0] )
    goto LABEL_31;
  v6 = 0;
  ppsidOwner = 0;
  hMem = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const struct boost::filesystem::path **)a2;
  NamedSecurityInfoW = GetNamedSecurityInfoW((LPCWSTR)a2, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &hMem);
  LastError = NamedSecurityInfoW;
  if ( !NamedSecurityInfoW )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      v9 = TokenHandle;
      v42 = TokenHandle;
      ReturnLength = 0;
      v10 = operator new[](0x54u);
      v46 = v10;
      if ( v9 == (HANDLE)-1LL || !v9 )
      {
        std::wstring::wstring(&v37, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(&pExceptionObject, &v37);
        throw (Uev::SmartHandleException *)&pExceptionObject;
      }
      if ( GetTokenInformation(v9, TokenUser, v10, 0x54u, &ReturnLength) && ReturnLength <= 0x54 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, PSID, _QWORD, void *))(*(_QWORD *)Uev::Repository::s_ADSMethods + 16LL))(
               Uev::Repository::s_ADSMethods,
               ppsidOwner,
               *v10,
               Uev::Repository::s_LocalAdminGroupSid);
      }
      else if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 8) != 0 )
      {
        v11 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance();
        LastError = GetLastError();
        v12 = (void *)boost::lexical_cast<std::wstring,unsigned long>(&v39, &LastError);
        v13 = std::wstring::_Insert<wchar_t>(v12);
        v14 = *(_OWORD *)v13;
        v37 = *(_OWORD *)v13;
        v38 = *(__m128i *)(v13 + 16);
        v15 = v38;
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 7;
        *(_WORD *)v13 = 0;
        pExceptionObject = 0;
        v44 = 0;
        v45 = 0;
        std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, L"CscChangeManager", 0x10u);
        v16 = &v37;
        if ( _mm_srli_si128(v15, 8).m128i_u64[0] > 7 )
          v16 = (__int128 *)v14;
        Uev::LogImpl::Write(*v11, 8, &pExceptionObject, v16);
        std::wstring::_Tidy_deallocate(&pExceptionObject);
        std::wstring::_Tidy_deallocate(&v37);
        std::wstring::_Tidy_deallocate(&v39);
      }
      operator delete(v10);
      Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(&v42);
    }
    else if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 8) != 0 )
    {
      v17 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance();
      LastError = GetLastError();
      v18 = (void *)boost::lexical_cast<std::wstring,unsigned long>(&v39, &LastError);
      v19 = std::wstring::_Insert<wchar_t>(v18);
      v20 = *(_OWORD *)v19;
      v37 = *(_OWORD *)v19;
      v38 = *(__m128i *)(v19 + 16);
      v21 = v38;
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      pExceptionObject = 0;
      v44 = 0;
      v45 = 0;
      std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, L"CscChangeManager", 0x10u);
      v22 = &v37;
      if ( _mm_srli_si128(v21, 8).m128i_u64[0] > 7 )
        v22 = (__int128 *)v20;
      Uev::LogImpl::Write(*v17, 8, &pExceptionObject, v22);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
      std::wstring::_Tidy_deallocate(&v37);
      std::wstring::_Tidy_deallocate(&v39);
    }
    LocalFree(hMem);
    goto LABEL_32;
  }
  if ( NamedSecurityInfoW == 50 )
  {
LABEL_31:
    v6 = 1;
    goto LABEL_32;
  }
  if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 8) != 0 )
  {
    v23 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v24 = (void *)boost::lexical_cast<std::wstring,unsigned long>(&v39, &LastError);
    v25 = std::wstring::_Insert<wchar_t>(v24);
    v26 = *(_OWORD *)v25;
    v37 = *(_OWORD *)v25;
    v38 = *(__m128i *)(v25 + 16);
    v27 = v38;
    *(_QWORD *)(v25 + 16) = 0;
    *(_QWORD *)(v25 + 24) = 7;
    *(_WORD *)v25 = 0;
    pExceptionObject = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, L"CscChangeManager", 0x10u);
    v28 = &v37;
    if ( _mm_srli_si128(v27, 8).m128i_u64[0] > 7 )
      v28 = (__int128 *)v26;
    Uev::LogImpl::Write(*v23, 8, &pExceptionObject, v28);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    std::wstring::_Tidy_deallocate(&v37);
    std::wstring::_Tidy_deallocate(&v39);
  }
LABEL_32:
  if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance() + 32LL) & 8) != 0 )
  {
    v29 = Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v37 = 0;
    v38 = 0u;
    std::wstring::_Construct<1,wchar_t *>(&v37, L"Repository::IsFolderOwnerTheCurrentUser() - isOwner = %1%.", 0x3Au);
    v31 = Uev::Log::fmt(v30, v47, &v37);
    v32 = L"true";
    if ( !v6 )
      v32 = L"false";
    v42 = (HANDLE)v32;
    *(_QWORD *)&v39 = &v42;
    *((_QWORD *)&v39 + 1) = boost::on_process_enter;
    v40 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,wchar_t const * const>;
    v33 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
            v31,
            &v39);
    pExceptionObject = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, L"CscChangeManager", 0x10u);
    Uev::Log::Write(v29, v34, &pExceptionObject, v33);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
    std::wstring::_Tidy_deallocate(&v37);
  }
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v54);
  return v6;
}

```

## disassembly

```asm
0x14008ba34  mov     rax, rsp
0x14008ba37  push    rbp
0x14008ba38  push    rbx
0x14008ba39  push    rsi
0x14008ba3a  push    rdi
0x14008ba3b  push    r13
0x14008ba3d  push    r14
0x14008ba3f  lea     rbp, [rax-208h]
0x14008ba46  sub     rsp, 2D8h
0x14008ba4d  movaps  xmmword ptr [rax-48h], xmm6
0x14008ba51  movaps  xmmword ptr [rax-58h], xmm7
0x14008ba55  mov     rax, cs:__security_cookie
0x14008ba5c  xor     rax, rsp
0x14008ba5f  mov     [rbp+200h+var_60], rax
0x14008ba66  mov     rdi, rdx
0x14008ba69  xor     r14d, r14d
0x14008ba6c  lea     r8, aRepositoryIsfo_1; "Repository::IsFolderOwnerTheCurrentUser"...
0x14008ba73  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008ba7a  lea     rcx, [rbp+200h+var_E0]; this
0x14008ba81  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008ba86  nop
0x14008ba87  mov     [rbp+200h+var_F0], r14
0x14008ba8e  mov     [rbp+200h+var_F8], r14b
0x14008ba95  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14008ba9a  lea     rcx, [rax+35E0h]
0x14008baa1  lea     r8, [rbp+200h+var_F0]
0x14008baa8  lea     rdx, [rbp+200h+var_F8]
0x14008baaf  call    ?Get@?$Setting@_N@Uev@@QEBA_NAEA_NAEAUSettingInfo@2@@Z; Uev::Setting<bool>::Get(bool &,Uev::SettingInfo &)
0x14008bab4  lea     r13d, [r14+7]
0x14008bab8  test    al, al
0x14008baba  jnz     loc_14008BB59
0x14008bac0  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bac5  mov     rcx, [rax]
0x14008bac8  test    byte ptr [rcx+20h], 4
0x14008bacc  jbe     loc_14008BB59
0x14008bad2  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bad7  mov     rbx, rax
0x14008bada  xorps   xmm0, xmm0
0x14008badd  movups  [rsp+300h+var_2A0+8], xmm0
0x14008bae2  mov     [rsp+300h+var_288], r14
0x14008bae7  mov     [rbp+200h+var_280], r14
0x14008baeb  lea     r8d, [r14+5Eh]
0x14008baef  lea     rdx, aFailedToReadRe; "Failed to read RepositoryOwnerCheckEnab"...
0x14008baf6  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bafb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008bb00  nop
0x14008bb01  xorps   xmm0, xmm0
0x14008bb04  movups  [rbp+200h+pExceptionObject], xmm0
0x14008bb08  mov     [rbp+200h+var_260], r14
0x14008bb0c  mov     [rbp+200h+var_258], r14
0x14008bb10  lea     r8d, [r14+10h]
0x14008bb14  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008bb1b  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bb1f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008bb24  nop
0x14008bb25  lea     r9, [rsp+300h+var_2A0+8]
0x14008bb2a  cmp     [rbp+200h+var_280], r13
0x14008bb2e  cmova   r9, qword ptr [rsp+300h+var_2A0+8]
0x14008bb34  lea     r8, [rbp+200h+pExceptionObject]
0x14008bb38  lea     edx, [r14+4]
0x14008bb3c  mov     rcx, [rbx]
0x14008bb3f  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008bb44  nop
0x14008bb45  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bb49  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bb4e  nop
0x14008bb4f  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bb54  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bb59  cmp     [rbp+200h+var_F8], r14b
0x14008bb60  jz      loc_14008BF33
0x14008bb66  mov     sil, r14b
0x14008bb69  mov     [rbp+200h+ppsidOwner], r14
0x14008bb70  mov     [rbp+200h+hMem], r14
0x14008bb77  cmp     [rdi+18h], r13
0x14008bb7b  jbe     short loc_14008BB80
0x14008bb7d  mov     rdi, [rdi]
0x14008bb80  lea     rax, [rbp+200h+hMem]
0x14008bb87  mov     [rsp+300h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x14008bb8c  mov     [rsp+300h+ppSacl], r14; ppSacl
0x14008bb91  mov     [rsp+300h+ppDacl], r14; ppDacl
0x14008bb96  mov     [rsp+300h+ppsidGroup], r14; ppsidGroup
0x14008bb9b  lea     r9, [rbp+200h+ppsidOwner]; ppsidOwner
0x14008bba2  mov     edx, 1; ObjectType
0x14008bba7  mov     r8d, edx; SecurityInfo
0x14008bbaa  mov     rcx, rdi; pObjectName
0x14008bbad  call    cs:__imp_GetNamedSecurityInfoW
0x14008bbb3  mov     dword ptr [rsp+300h+var_2C0], eax
0x14008bbb7  test    eax, eax
0x14008bbb9  jnz     loc_14008BE58
0x14008bbbf  mov     [rbp+200h+TokenHandle], r14
0x14008bbc6  call    cs:__imp_GetCurrentProcess
0x14008bbcc  mov     rcx, rax; ProcessHandle
0x14008bbcf  lea     r8, [rbp+200h+TokenHandle]; TokenHandle
0x14008bbd6  mov     edx, 20008h; DesiredAccess
0x14008bbdb  call    cs:__imp_OpenProcessToken
0x14008bbe1  test    eax, eax
0x14008bbe3  jz      loc_14008BD6C
0x14008bbe9  mov     rbx, [rbp+200h+TokenHandle]
0x14008bbf0  mov     [rbp+200h+var_278], rbx
0x14008bbf4  mov     [rbp+200h+ReturnLength], r14d
0x14008bbfb  mov     ecx, 54h ; 'T'; unsigned __int64
0x14008bc00  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14008bc05  mov     rdi, rax
0x14008bc08  mov     [rbp+200h+var_230], rax
0x14008bc0c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14008bc10  jz      loc_14008C069
0x14008bc16  test    rbx, rbx
0x14008bc19  jz      loc_14008C069
0x14008bc1f  lea     rax, [rbp+200h+ReturnLength]
0x14008bc26  mov     [rsp+300h+ppsidGroup], rax; ReturnLength
0x14008bc2b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x14008bc31  mov     r8, rdi; TokenInformation
0x14008bc34  lea     edx, [r9-53h]; TokenInformationClass
0x14008bc38  mov     rcx, rbx; TokenHandle
0x14008bc3b  call    cs:__imp_GetTokenInformation
0x14008bc41  test    eax, eax
0x14008bc43  jz      short loc_14008BC7A
0x14008bc45  cmp     [rbp+200h+ReturnLength], 54h ; 'T'
0x14008bc4c  ja      short loc_14008BC7A
0x14008bc4e  mov     rcx, qword ptr cs:?s_ADSMethods@Repository@Uev@@0V?$shared_ptr@VIADSMethods@Uev@@@std@@A; std::shared_ptr<Uev::IADSMethods> Uev::Repository::s_ADSMethods
0x14008bc55  mov     rax, [rcx]
0x14008bc58  mov     r9, cs:?s_LocalAdminGroupSid@Repository@Uev@@0PEAXEA; void * Uev::Repository::s_LocalAdminGroupSid
0x14008bc5f  mov     r8, [rdi]
0x14008bc62  mov     rdx, [rbp+200h+ppsidOwner]
0x14008bc69  mov     rax, [rax+10h]
0x14008bc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bc72  mov     sil, al
0x14008bc75  jmp     loc_14008BD55
0x14008bc7a  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bc7f  mov     rcx, [rax]
0x14008bc82  test    byte ptr [rcx+20h], 8
0x14008bc86  jbe     loc_14008BD55
0x14008bc8c  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bc91  mov     rbx, rax
0x14008bc94  call    cs:__imp_GetLastError
0x14008bc9a  mov     dword ptr [rsp+300h+var_2C0], eax
0x14008bc9e  lea     rdx, [rsp+300h+var_2C0]
0x14008bca3  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bca8  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; boost::lexical_cast<std::wstring,ulong>(ulong const &)
0x14008bcad  nop
0x14008bcae  mov     r9d, 52h ; 'R'
0x14008bcb4  lea     r8, aRepositoryIsfo_0; "Repository::IsFolderOwnerTheCurrentUser"...
0x14008bcbb  xor     edx, edx
0x14008bcbd  mov     rcx, rax; Src
0x14008bcc0  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008bcc5  movups  xmm6, xmmword ptr [rax]
0x14008bcc8  movups  [rsp+300h+var_2C0+8], xmm6
0x14008bccd  movups  xmm7, xmmword ptr [rax+10h]
0x14008bcd1  movups  [rsp+300h+var_2B0+8], xmm7
0x14008bcd6  mov     [rax+10h], r14
0x14008bcda  mov     [rax+18h], r13
0x14008bcde  mov     [rax], r14w
0x14008bce2  xorps   xmm0, xmm0
0x14008bce5  movups  [rbp+200h+pExceptionObject], xmm0
0x14008bce9  mov     [rbp+200h+var_260], r14
0x14008bced  mov     [rbp+200h+var_258], r14
0x14008bcf1  mov     r8d, 10h
0x14008bcf7  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008bcfe  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bd02  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008bd07  nop
0x14008bd08  lea     r9, [rsp+300h+var_2C0+8]
0x14008bd0d  movq    rdx, xmm6
0x14008bd12  psrldq  xmm7, 8
0x14008bd17  movq    rax, xmm7
0x14008bd1c  cmp     rax, r13
0x14008bd1f  cmova   r9, rdx
0x14008bd23  lea     r8, [rbp+200h+pExceptionObject]
0x14008bd27  mov     edx, 8
0x14008bd2c  mov     rcx, [rbx]
0x14008bd2f  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008bd34  nop
0x14008bd35  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bd39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bd3e  nop
0x14008bd3f  lea     rcx, [rsp+300h+var_2C0+8]
0x14008bd44  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bd49  nop
0x14008bd4a  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bd4f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bd54  nop
0x14008bd55  mov     rcx, rdi; Block
0x14008bd58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14008bd5d  nop
0x14008bd5e  lea     rcx, [rbp+200h+var_278]
0x14008bd62  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x14008bd67  jmp     loc_14008BE46
0x14008bd6c  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bd71  mov     rcx, [rax]
0x14008bd74  test    byte ptr [rcx+20h], 8
0x14008bd78  jbe     loc_14008BE46
0x14008bd7e  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bd83  mov     rbx, rax
0x14008bd86  call    cs:__imp_GetLastError
0x14008bd8c  mov     dword ptr [rsp+300h+var_2C0], eax
0x14008bd90  lea     rdx, [rsp+300h+var_2C0]
0x14008bd95  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bd9a  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; boost::lexical_cast<std::wstring,ulong>(ulong const &)
0x14008bd9f  nop
0x14008bda0  mov     r9d, 4Fh ; 'O'
0x14008bda6  lea     r8, aRepositoryIsfo_3; "Repository::IsFolderOwnerTheCurrentUser"...
0x14008bdad  xor     edx, edx
0x14008bdaf  mov     rcx, rax; Src
0x14008bdb2  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008bdb7  movups  xmm6, xmmword ptr [rax]
0x14008bdba  movups  [rsp+300h+var_2C0+8], xmm6
0x14008bdbf  movups  xmm7, xmmword ptr [rax+10h]
0x14008bdc3  movups  [rsp+300h+var_2B0+8], xmm7
0x14008bdc8  mov     [rax+10h], r14
0x14008bdcc  mov     [rax+18h], r13
0x14008bdd0  mov     [rax], r14w
0x14008bdd4  xorps   xmm0, xmm0
0x14008bdd7  movups  [rbp+200h+pExceptionObject], xmm0
0x14008bddb  mov     [rbp+200h+var_260], r14
0x14008bddf  mov     [rbp+200h+var_258], r14
0x14008bde3  mov     r8d, 10h
0x14008bde9  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008bdf0  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bdf4  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008bdf9  nop
0x14008bdfa  lea     r9, [rsp+300h+var_2C0+8]
0x14008bdff  movq    rdx, xmm6
0x14008be04  psrldq  xmm7, 8
0x14008be09  movq    rax, xmm7
0x14008be0e  cmp     rax, r13
0x14008be11  cmova   r9, rdx
0x14008be15  lea     r8, [rbp+200h+pExceptionObject]
0x14008be19  mov     edx, 8
0x14008be1e  mov     rcx, [rbx]
0x14008be21  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008be26  nop
0x14008be27  lea     rcx, [rbp+200h+pExceptionObject]
0x14008be2b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008be30  nop
0x14008be31  lea     rcx, [rsp+300h+var_2C0+8]
0x14008be36  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008be3b  nop
0x14008be3c  lea     rcx, [rsp+300h+var_2A0+8]
0x14008be41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008be46  mov     rcx, [rbp+200h+hMem]; hMem
0x14008be4d  call    cs:__imp_LocalFree
0x14008be53  jmp     loc_14008BF36
0x14008be58  cmp     eax, 32h ; '2'
0x14008be5b  jz      loc_14008BF33
0x14008be61  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008be66  mov     rcx, [rax]
0x14008be69  test    byte ptr [rcx+20h], 8
0x14008be6d  jbe     loc_14008BF36
0x14008be73  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008be78  mov     rbx, rax
0x14008be7b  lea     rdx, [rsp+300h+var_2C0]
0x14008be80  lea     rcx, [rsp+300h+var_2A0+8]
0x14008be85  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; boost::lexical_cast<std::wstring,ulong>(ulong const &)
0x14008be8a  nop
0x14008be8b  mov     r9d, 53h ; 'S'
0x14008be91  lea     r8, aRepositoryIsfo_2; "Repository::IsFolderOwnerTheCurrentUser"...
0x14008be98  xor     edx, edx
0x14008be9a  mov     rcx, rax; Src
0x14008be9d  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008bea2  movups  xmm6, xmmword ptr [rax]
0x14008bea5  movups  [rsp+300h+var_2C0+8], xmm6
0x14008beaa  movups  xmm7, xmmword ptr [rax+10h]
0x14008beae  movups  [rsp+300h+var_2B0+8], xmm7
0x14008beb3  mov     [rax+10h], r14
0x14008beb7  mov     [rax+18h], r13
0x14008bebb  mov     [rax], r14w
0x14008bebf  xorps   xmm0, xmm0
0x14008bec2  movups  [rbp+200h+pExceptionObject], xmm0
0x14008bec6  mov     [rbp+200h+var_260], r14
0x14008beca  mov     [rbp+200h+var_258], r14
0x14008bece  mov     r8d, 10h
0x14008bed4  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008bedb  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bedf  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008bee4  nop
0x14008bee5  lea     r9, [rsp+300h+var_2C0+8]
0x14008beea  movq    rdx, xmm6
0x14008beef  psrldq  xmm7, 8
0x14008bef4  movq    rax, xmm7
0x14008bef9  cmp     rax, r13
0x14008befc  cmova   r9, rdx
0x14008bf00  lea     r8, [rbp+200h+pExceptionObject]
0x14008bf04  mov     edx, 8
0x14008bf09  mov     rcx, [rbx]
0x14008bf0c  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008bf11  nop
0x14008bf12  lea     rcx, [rbp+200h+pExceptionObject]
0x14008bf16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bf1b  nop
0x14008bf1c  lea     rcx, [rsp+300h+var_2C0+8]
0x14008bf21  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bf26  nop
0x14008bf27  lea     rcx, [rsp+300h+var_2A0+8]
0x14008bf2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bf31  jmp     short loc_14008BF36
0x14008bf33  mov     sil, 1
0x14008bf36  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008bf3b  mov     rcx, [rax]
0x14008bf3e  test    byte ptr [rcx+20h], 8
0x14008bf42  jbe     loc_14008C02D
  ... truncated ...
```
