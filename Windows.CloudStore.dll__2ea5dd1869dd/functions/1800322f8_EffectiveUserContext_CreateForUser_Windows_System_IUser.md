# EffectiveUserContext::CreateForUser(Windows::System::IUser *)

- ea: `0x1800322f8`
- end: `0x18003290f`
- name: `?CreateForUser@EffectiveUserContext@@SA?AV1@PEAUIUser@System@Windows@@@Z`
- size: `1559`
- prototype: `char *__fastcall(char *, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f814`
- `0x18008be8c`

## callees

- `0x180016cf4`
- `0x180024300`
- `0x180031fb0`
- `0x1800320d4`
- `0x1800320f0`
- `0x1800322f8`
- `0x180032a50`
- `0x180032b98`
- `0x1800856d4`
- `0x1800d1d50`
- `0x1801201a0`
- `0x180120850`
- `0x18012392c`
- `0x180178038`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800328bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800328bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032903`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800324f5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800324f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800324e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800324e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032342`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032342`
- `ntdll!RtlIsMultiSessionSku` at `0x180032507`
- `ntdll!RtlIsMultiSessionSku` at `0x180032507`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180032515`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180032515`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x18003282b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x18003282b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800326f9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800326f9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180032458`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180032458`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180032540`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180032540`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x180032798`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x180032798`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800323b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800323b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032399`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180032595`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800327e7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180032595`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800327e7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003241d`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003241d`

## string_xrefs

- `0x18003263b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180032654`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180032669`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003267e`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180032693`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800326a8`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800326bd`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003270a`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003271c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003275a`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003283c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18003284e`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180032866`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180032878`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800328c2`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800328d4`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800328f1`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char *__fastcall EffectiveUserContext::CreateForUser(char *a1, __int64 a2, __int64 a3, const char *a4)
{
  HANDLE CurrentProcess; // rax
  bool *v7; // r8
  int IsProcessAppContainer; // eax
  void **v9; // rax
  char *v10; // rsi
  HRESULT v11; // eax
  int ActivationFactory; // eax
  int v13; // eax
  void *v14; // r14
  __int64 *i; // rbx
  char v16; // bl
  void *v17; // rcx
  int v18; // eax
  void *v19; // rcx
  DWORD CurrentProcessId; // eax
  BOOL v22; // eax
  const char *v23; // r9
  wil::details::in1diag3 *v24; // rcx
  int v25; // eax
  const char *v26; // r9
  const char *v27; // r9
  int ConstrainedUserToken; // eax
  const char *v29; // r9
  int SessionUserToken; // eax
  const char *v31; // r9
  const char *v32; // r9
  int ImpersonationTokenForContext; // eax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-59h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-59h]
  char v36[8]; // [rsp+30h] [rbp-49h] BYREF
  HANDLE p_hExistingToken; // [rsp+38h] [rbp-41h] BYREF
  void *phNewToken; // [rsp+40h] [rbp-39h] BYREF
  char v39; // [rsp+48h] [rbp-31h]
  void *Block; // [rsp+50h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-21h] BYREF
  HANDLE hExistingToken; // [rsp+60h] [rbp-19h] BYREF
  HANDLE v43; // [rsp+68h] [rbp-11h] BYREF
  __int64 v44; // [rsp+70h] [rbp-9h] BYREF
  char *v45; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v45 = a1;
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      a4);
  v36[0] = 0;
  CurrentProcess = GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v36, v7);
  if ( IsProcessAppContainer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)IsProcessAppContainer,
      TokenType);
  v9 = (void **)CloudStoreUtilities::OpenCurrentThreadAccessToken(&p_hExistingToken);
  v10 = (char *)*v9;
  v45 = (char *)*v9;
  *v9 = 0;
  std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&p_hExistingToken);
  v44 = 0;
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    goto LABEL_65;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v44);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)ActivationFactory,
      TokenType);
  v43 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(*(_QWORD *)v44 + 136LL))(v44, a2, &v43);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)v13,
      TokenType);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v10);
  v14 = *(void **)Block;
  for ( i = qword_18022B6A0; ; ++i )
  {
    if ( i == winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::AppExtensions::AppExtension>>> )
    {
      v16 = 0;
      goto LABEL_11;
    }
    if ( IsWellKnownSid(v14, *(WELL_KNOWN_SID_TYPE *)i) )
      break;
  }
  v16 = 1;
LABEL_11:
  v17 = Block;
  Block = 0;
  if ( v17 )
    operator delete(v17);
  if ( !v16 )
  {
    p_hExistingToken = 0;
    v18 = UMgrQueryUserContext(0, &p_hExistingToken);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v18,
        TokenType);
    if ( p_hExistingToken == v43 )
    {
      EffectiveUserContext::EffectiveUserContext(a1, a2, v43, &v45);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v19 = v45;
      if ( (unsigned __int64)(v45 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        return a1;
LABEL_39:
      CloseHandle(v19);
      return a1;
    }
  }
  hObject = 0;
  if ( !v36[0] )
  {
    LODWORD(Block) = 0;
    CurrentProcessId = GetCurrentProcessId();
    v22 = ProcessIdToSessionId(CurrentProcessId, (DWORD *)&Block);
    v24 = retaddr;
    if ( v22 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku(retaddr)
        && (_DWORD)Block == (unsigned int)RtlGetCurrentServiceSessionId() )
      {
        hExistingToken = 0;
        p_hExistingToken = &hExistingToken;
        phNewToken = 0;
        v39 = 1;
        v25 = UMgrQueryUserToken(v43, &phNewToken);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x208,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            (const char *)(unsigned int)v25,
            TokenType);
        if ( v39 )
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            p_hExistingToken,
            phNewToken);
        p_hExistingToken = &hObject;
        phNewToken = 0;
        v39 = 1;
        if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x209,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            v26);
        if ( v39 )
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            p_hExistingToken,
            phNewToken);
        if ( (char *)hExistingToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hExistingToken);
      }
      else
      {
        p_hExistingToken = 0;
        if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x215,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            v29);
        hstringHeader.Reserved.Reserved1 = &p_hExistingToken;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        SessionUserToken = UMgrQuerySessionUserToken((unsigned int)Block, &hstringHeader.Reserved.Reserved2[8]);
        if ( SessionUserToken < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x216,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            (const char *)(unsigned int)SessionUserToken,
            TokenType);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
        hExistingToken = 0;
        hstringHeader.Reserved.Reserved1 = &hExistingToken;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        if ( !DuplicateTokenEx(
                p_hExistingToken,
                0x2000000u,
                0,
                SecurityImpersonation,
                TokenImpersonation,
                (PHANDLE)&hstringHeader.Reserved.Reserved2[8]) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x219,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            v31);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
        if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x21A,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            v32);
        hstringHeader.Reserved.Reserved1 = &hObject;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        ImpersonationTokenForContext = UMgrGetImpersonationTokenForContext(
                                         hExistingToken,
                                         v43,
                                         &hstringHeader.Reserved.Reserved2[8]);
        if ( ImpersonationTokenForContext < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x21B,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
            (const char *)(unsigned int)ImpersonationTokenForContext,
            TokenTypea);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
        std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&hExistingToken);
        std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&p_hExistingToken);
      }
      goto LABEL_32;
    }
LABEL_65:
    wil::details::in1diag3::Throw_GetLastError(
      v24,
      (void *)0x201,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      v23);
  }
  if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      v27);
  p_hExistingToken = &hObject;
  phNewToken = 0;
  v39 = 1;
  ConstrainedUserToken = UMgrGetConstrainedUserToken(0, v43, 0, &phNewToken);
  if ( ConstrainedUserToken < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)ConstrainedUserToken,
      TokenType);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hExistingToken);
  if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)0x80070006LL,
      TokenType);
LABEL_32:
  if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      v26);
  EffectiveUserContext::EffectiveUserContext(a1, a2, v43, &hObject);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v19 = v10;
    goto LABEL_39;
  }
  return a1;
}

```

## disassembly

```asm
0x1800322f8  mov     [rsp-8+arg_10], rbx
0x1800322fd  mov     [rsp-8+arg_18], rsi
0x180032302  push    rbp
0x180032303  push    rdi
0x180032304  push    r12
0x180032306  push    r14
0x180032308  push    r15
0x18003230a  lea     rbp, [rsp-37h]
0x18003230f  sub     rsp, 0B0h
0x180032316  mov     rax, cs:__security_cookie
0x18003231d  xor     rax, rsp
0x180032320  mov     [rbp+57h+var_28], rax
0x180032324  mov     r15, rdx
0x180032327  mov     rdi, rcx
0x18003232a  mov     [rbp+57h+var_58], rcx
0x18003232e  xor     r12d, r12d
0x180032331  mov     rcx, [rbp+5Fh]; this
0x180032335  test    rdx, rdx
0x180032338  jz      loc_18003263B
0x18003233e  mov     [rbp+57h+var_A0], r12b
0x180032342  call    cs:__imp_GetCurrentProcess
0x180032348  mov     rcx, rax; ProcessHandle
0x18003234b  lea     rdx, [rbp+57h+var_A0]; void *
0x18003234f  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180032354  mov     rcx, [rbp+5Fh]; this
0x180032358  test    eax, eax
0x18003235a  js      loc_180032666
0x180032360  lea     rcx, [rbp+57h+var_98]
0x180032364  call    ?OpenCurrentThreadAccessToken@CloudStoreUtilities@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@XZ; CloudStoreUtilities::OpenCurrentThreadAccessToken(void)
0x180032369  mov     rsi, [rax]
0x18003236c  mov     [rbp+57h+var_58], rsi
0x180032370  mov     [rax], r12
0x180032373  lea     rcx, [rbp+57h+var_98]
0x180032377  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x18003237c  nop
0x18003237d  mov     [rbp+57h+var_60], r12
0x180032381  mov     [rbp+57h+string], r12
0x180032385  lea     r9, [rbp+57h+string]; string
0x180032389  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003238d  lea     edx, [r12+23h]; length
0x180032392  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180032399  call    cs:__imp_WindowsCreateStringReference
0x18003239f  test    eax, eax
0x1800323a1  js      loc_1800328AF
0x1800323a7  lea     r8, [rbp+57h+var_60]
0x1800323ab  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800323b2  mov     rcx, [rbp+57h+string]
0x1800323b6  call    cs:__imp_RoGetActivationFactory
0x1800323bc  mov     rcx, [rbp+5Fh]; this
0x1800323c0  test    eax, eax
0x1800323c2  js      loc_18003267B
0x1800323c8  mov     [rbp+57h+var_68], r12
0x1800323cc  mov     rcx, [rbp+57h+var_60]
0x1800323d0  mov     rax, [rcx]
0x1800323d3  lea     r8, [rbp+57h+var_68]
0x1800323d7  mov     rdx, r15
0x1800323da  mov     rax, [rax+88h]
0x1800323e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323e6  mov     rcx, [rbp+5Fh]; this
0x1800323ea  test    eax, eax
0x1800323ec  js      loc_180032690
0x1800323f2  mov     rdx, rsi
0x1800323f5  lea     rcx, [rbp+57h+Block]
0x1800323f9  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1800323fe  mov     rax, [rbp+57h+Block]
0x180032402  mov     r14, [rax]
0x180032405  lea     rbx, qword_18022B6A0
0x18003240c  lea     rax, ??$guid_v@U?$AsyncOperationCompletedHandler@U?$IVectorView@UAppExtension@AppExtensions@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::AppExtensions::AppExtension>>>
0x180032413  cmp     rbx, rax
0x180032416  jz      short loc_180032431
0x180032418  mov     edx, [rbx]; WellKnownSidType
0x18003241a  mov     rcx, r14; pSid
0x18003241d  call    cs:__imp_IsWellKnownSid
0x180032423  test    eax, eax
0x180032425  jnz     loc_18003264D
0x18003242b  add     rbx, 8
0x18003242f  jmp     short loc_18003240C
0x180032431  mov     bl, r12b
0x180032434  mov     rcx, [rbp+57h+Block]; Block
0x180032438  mov     [rbp+57h+Block], r12
0x18003243c  test    rcx, rcx
0x18003243f  jz      short loc_180032446
0x180032441  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032446  test    bl, bl
0x180032448  jnz     loc_1800324D7
0x18003244e  mov     [rbp+57h+var_98], r12
0x180032452  lea     rdx, [rbp+57h+var_98]
0x180032456  xor     ecx, ecx
0x180032458  call    cs:__imp_UMgrQueryUserContext
0x18003245e  mov     rcx, [rbp+5Fh]; this
0x180032462  test    eax, eax
0x180032464  js      loc_1800326A5
0x18003246a  mov     r8, [rbp+57h+var_68]
0x18003246e  cmp     [rbp+57h+var_98], r8
0x180032472  jnz     short loc_1800324D7
0x180032474  lea     r9, [rbp+57h+var_58]
0x180032478  mov     rdx, r15
0x18003247b  mov     rcx, rdi
0x18003247e  call    ??0EffectiveUserContext@@AEAA@PEAUIUser@System@Windows@@_K$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; EffectiveUserContext::EffectiveUserContext(Windows::System::IUser *,unsigned __int64,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180032483  nop
0x180032484  mov     rcx, [rbp+57h+var_60]
0x180032488  test    rcx, rcx
0x18003248b  jz      short loc_18003249A
0x18003248d  mov     rax, [rcx]
0x180032490  mov     rax, [rax+10h]
0x180032494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032499  nop
0x18003249a  mov     rcx, [rbp+57h+var_58]
0x18003249e  lea     rax, [rcx-1]
0x1800324a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800324a6  jbe     loc_180032630
0x1800324ac  mov     rax, rdi
0x1800324af  mov     rcx, [rbp+57h+var_28]
0x1800324b3  xor     rcx, rsp; StackCookie
0x1800324b6  call    __security_check_cookie
0x1800324bb  lea     r11, [rsp+0D0h+var_20]
0x1800324c3  mov     rbx, [r11+40h]
0x1800324c7  mov     rsi, [r11+48h]
0x1800324cb  mov     rsp, r11
0x1800324ce  pop     r15
0x1800324d0  pop     r14
0x1800324d2  pop     r12
0x1800324d4  pop     rdi
0x1800324d5  pop     rbp
0x1800324d6  retn
0x1800324d7  mov     [rbp+57h+hObject], r12
0x1800324db  cmp     [rbp+57h+var_A0], r12b
0x1800324df  jnz     loc_1800326CF
0x1800324e5  mov     dword ptr [rbp+57h+Block], r12d
0x1800324e9  call    cs:__imp_GetCurrentProcessId
0x1800324ef  mov     ecx, eax; dwProcessId
0x1800324f1  lea     rdx, [rbp+57h+Block]; pSessionId
0x1800324f5  call    cs:__imp_ProcessIdToSessionId
0x1800324fb  mov     rcx, [rbp+5Fh]
0x1800324ff  test    eax, eax
0x180032501  jz      loc_1800328C2
0x180032507  call    cs:__imp_RtlIsMultiSessionSku
0x18003250d  test    al, al
0x18003250f  jz      loc_18003276C
0x180032515  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18003251b  cmp     dword ptr [rbp+57h+Block], eax
0x18003251e  jnz     loc_18003276C
0x180032524  mov     [rbp+57h+hExistingToken], r12
0x180032528  lea     rax, [rbp+57h+hExistingToken]
0x18003252c  mov     [rbp+57h+var_98], rax
0x180032530  mov     [rbp+57h+var_90], r12
0x180032534  mov     [rbp+57h+var_88], 1
0x180032538  lea     rdx, [rbp+57h+var_90]
0x18003253c  mov     rcx, [rbp+57h+var_68]
0x180032540  call    cs:__imp_UMgrQueryUserToken
0x180032546  mov     rcx, [rbp+5Fh]; this
0x18003254a  test    eax, eax
0x18003254c  js      loc_1800326BA
0x180032552  cmp     [rbp+57h+var_88], r12b
0x180032556  jz      short loc_180032565
0x180032558  mov     rdx, [rbp+57h+var_90]
0x18003255c  mov     rcx, [rbp+57h+var_98]
0x180032560  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032565  lea     rax, [rbp+57h+hObject]
0x180032569  mov     [rbp+57h+var_98], rax
0x18003256d  mov     [rbp+57h+var_90], r12
0x180032571  mov     [rbp+57h+var_88], 1
0x180032575  lea     rax, [rbp+57h+var_90]
0x180032579  mov     [rsp+0D0h+phNewToken], rax; phNewToken
0x18003257e  mov     r9d, 2; ImpersonationLevel
0x180032584  mov     [rsp+0D0h+TokenType], r9d; TokenType
0x180032589  xor     r8d, r8d; lpTokenAttributes
0x18003258c  mov     edx, 2000000h; dwDesiredAccess
0x180032591  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x180032595  call    cs:__imp_DuplicateTokenEx
0x18003259b  mov     rcx, [rbp+5Fh]; this
0x18003259f  test    eax, eax
0x1800325a1  jz      loc_1800328D4
0x1800325a7  cmp     [rbp+57h+var_88], r12b
0x1800325ab  jz      short loc_1800325BB
0x1800325ad  mov     rdx, [rbp+57h+var_90]
0x1800325b1  mov     rcx, [rbp+57h+var_98]
0x1800325b5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800325ba  nop
0x1800325bb  mov     rcx, [rbp+57h+hExistingToken]; hObject
0x1800325bf  lea     rax, [rcx-1]
0x1800325c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800325c7  jbe     loc_1800328E6
0x1800325cd  mov     rax, [rbp+57h+hObject]
0x1800325d1  dec     rax
0x1800325d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800325d8  setnbe  al
0x1800325db  mov     rcx, [rbp+5Fh]; this
0x1800325df  test    al, al
0x1800325e1  jnz     short loc_180032654
0x1800325e3  lea     r9, [rbp+57h+hObject]
0x1800325e7  mov     r8, [rbp+57h+var_68]
0x1800325eb  mov     rdx, r15
0x1800325ee  mov     rcx, rdi
0x1800325f1  call    ??0EffectiveUserContext@@AEAA@PEAUIUser@System@Windows@@_K$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; EffectiveUserContext::EffectiveUserContext(Windows::System::IUser *,unsigned __int64,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800325f6  nop
0x1800325f7  mov     rcx, [rbp+57h+hObject]; hObject
0x1800325fb  lea     rax, [rcx-1]
0x1800325ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180032603  jbe     loc_180032903
0x180032609  mov     rcx, [rbp+57h+var_60]
0x18003260d  test    rcx, rcx
0x180032610  jz      short loc_18003261F
0x180032612  mov     rax, [rcx]
0x180032615  mov     rax, [rax+10h]
0x180032619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003261e  nop
0x18003261f  lea     rdx, [rsi-1]
0x180032623  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180032627  ja      loc_1800324AC
0x18003262d  mov     rcx, rsi; hObject
0x180032630  call    cs:__imp_CloseHandle
0x180032636  jmp     loc_1800324AC
0x18003263b  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032642  mov     edx, 1D8h; void *
0x180032647  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003264d  mov     bl, 1
0x18003264f  jmp     loc_180032434
0x180032654  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003265b  mov     edx, 21Eh; void *
0x180032660  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180032666  mov     r9d, eax; char *
0x180032669  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032670  mov     edx, 1DBh; void *
0x180032675  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003267b  mov     r9d, eax; char *
0x18003267e  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032685  mov     edx, 1E0h; void *
0x18003268a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032690  mov     r9d, eax; char *
0x180032693  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003269a  mov     edx, 1E2h; void *
0x18003269f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800326a5  mov     r9d, eax; char *
0x1800326a8  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800326af  mov     edx, 1EFh; void *
0x1800326b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800326ba  mov     r9d, eax; char *
0x1800326bd  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800326c4  mov     edx, 208h; void *
0x1800326c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800326cf  mov     rbx, [rbp+5Fh]
0x1800326d3  call    IsUMgrGetImpersonationTokenForContextPresent
0x1800326d8  test    al, al
0x1800326da  jz      short loc_18003271C
0x1800326dc  lea     rax, [rbp+57h+hObject]
0x1800326e0  mov     [rbp+57h+var_98], rax
0x1800326e4  mov     [rbp+57h+var_90], r12
0x1800326e8  mov     [rbp+57h+var_88], 1
0x1800326ec  lea     r9, [rbp+57h+var_90]
0x1800326f0  xor     r8d, r8d
0x1800326f3  mov     rdx, [rbp+57h+var_68]
0x1800326f7  xor     ecx, ecx
0x1800326f9  call    cs:__imp_UMgrGetConstrainedUserToken
0x1800326ff  mov     rcx, [rbp+5Fh]; this
0x180032703  test    eax, eax
0x180032705  jns     short loc_180032731
0x180032707  mov     r9d, eax; char *
0x18003270a  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032711  mov     edx, 1FAh; void *
0x180032716  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003271c  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032723  mov     edx, 1F9h; void *
0x180032728  mov     rcx, rbx; this
0x18003272b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180032731  lea     rcx, [rbp+57h+var_98]
0x180032735  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18003273a  mov     rax, [rbp+57h+hObject]
0x18003273e  dec     rax
0x180032741  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180032745  setnbe  al
0x180032748  mov     rcx, [rbp+5Fh]; this
0x18003274c  test    al, al
0x18003274e  jz      loc_1800325CD
0x180032754  mov     r9d, 80070006h; char *
0x18003275a  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180032761  mov     edx, 1FBh; void *
0x180032766  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003276c  mov     [rbp+57h+var_98], r12
0x180032770  mov     rbx, [rbp+5Fh]
0x180032774  call    IsUMgrGetImpersonationTokenForContextPresent
0x180032779  test    al, al
0x18003277b  jz      loc_18003284E
0x180032781  lea     rax, [rbp+57h+var_98]
0x180032785  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180032789  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x18003278d  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180032791  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]
0x180032795  mov     ecx, dword ptr [rbp+57h+Block]
0x180032798  call    cs:__imp_UMgrQuerySessionUserToken
0x18003279e  mov     rcx, [rbp+5Fh]; this
0x1800327a2  test    eax, eax
0x1800327a4  js      loc_180032863
0x1800327aa  lea     rcx, [rbp+57h+hstringHeader]
0x1800327ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800327b3  mov     [rbp+57h+hExistingToken], r12
0x1800327b7  lea     rax, [rbp+57h+hExistingToken]
0x1800327bb  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800327bf  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x1800327c3  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
  ... truncated ...
```
