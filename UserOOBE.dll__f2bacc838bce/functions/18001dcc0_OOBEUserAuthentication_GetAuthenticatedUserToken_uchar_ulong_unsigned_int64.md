# OOBEUserAuthentication::GetAuthenticatedUserToken(uchar *,ulong,unsigned __int64 *)

- ea: `0x18001dcc0`
- end: `0x18001e264`
- name: `?GetAuthenticatedUserToken@OOBEUserAuthentication@@UEAAJPEAEKPEA_K@Z`
- size: `1444`
- prototype: `__int64 __fastcall(OOBEUserAuthentication *__hidden this, unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800067b0`
- `0x180007114`
- `0x180007134`
- `0x18000a5a4`
- `0x18000a5e8`
- `0x18000bed4`
- `0x18000e2a0`
- `0x18000e2bc`
- `0x18000e528`
- `0x18001d5ec`
- `0x18001dac0`
- `0x18001db6c`
- `0x18001dcc0`
- `0x18001e8bc`
- `0x18001e8e0`
- `0x18001e99c`
- `0x18001e9d8`
- `0x18002d2d4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e122`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001e059`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001e059`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001e049`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001e049`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e14b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e14b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001df28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e013`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e07e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e0af`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001df28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e013`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e07e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e0af`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001dec7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001df82`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001dec7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001df82`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18001e0cc`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18001e0cc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de9e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001de9e`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18001ddbf`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18001ddbf`
- `SspiCli!SeciFreeCallContext` at `0x18001dfc9`
- `SspiCli!SeciFreeCallContext` at `0x18001e038`
- `SspiCli!SeciFreeCallContext` at `0x18001e0a3`
- `SspiCli!SeciFreeCallContext` at `0x18001e10f`
- `SspiCli!SeciFreeCallContext` at `0x18001e18e`
- `SspiCli!SeciFreeCallContext` at `0x18001e1c1`
- `SspiCli!SeciFreeCallContext` at `0x18001e1f0`
- `SspiCli!SeciFreeCallContext` at `0x18001dfc9`
- `SspiCli!SeciFreeCallContext` at `0x18001e038`
- `SspiCli!SeciFreeCallContext` at `0x18001e0a3`
- `SspiCli!SeciFreeCallContext` at `0x18001e10f`
- `SspiCli!SeciFreeCallContext` at `0x18001e18e`
- `SspiCli!SeciFreeCallContext` at `0x18001e1c1`
- `SspiCli!SeciFreeCallContext` at `0x18001e1f0`

## string_xrefs

- `0x18001df99`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e001`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e06b`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e0de`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e15d`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e22b`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e23d`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001e251`: `shell\oobe\user\dll\oobeuserauthentication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall OOBEUserAuthentication::GetAuthenticatedUserToken(
        OOBEUserAuthentication *this,
        unsigned __int8 *a2,
        unsigned int a3,
        HANDLE *a4)
{
  char v5; // r13
  void **v6; // r12
  void **v7; // rax
  void *v8; // rcx
  int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  void *v12; // rcx
  int v13; // eax
  _QWORD *v14; // rbx
  const char *v15; // r9
  HRESULT v16; // eax
  void *v17; // rsi
  void (__fastcall *v18)(void *, _QWORD, unsigned __int8 *, _QWORD); // rdi
  HRESULT v19; // eax
  const char *v20; // r9
  unsigned int LastError; // ebx
  __int64 v22; // rdx
  __int64 v23; // rcx
  CallerIdentity *v24; // rcx
  void **v25; // r8
  int CallingProcessHandle; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  DWORD ProcessId; // eax
  const char *v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rcx
  const char *v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  HANDLE v36; // rbx
  HANDLE v37; // rdi
  HANDLE CurrentProcess; // rax
  const char *v39; // r9
  __int64 v41; // rdx
  __int64 v42; // rcx
  int nSubAuthority2; // [rsp+20h] [rbp-108h]
  int nSubAuthority2a; // [rsp+20h] [rbp-108h]
  int nSubAuthority2b; // [rsp+20h] [rbp-108h]
  int v46; // [rsp+60h] [rbp-C8h] BYREF
  HANDLE Process; // [rsp+68h] [rbp-C0h] BYREF
  char v48; // [rsp+71h] [rbp-B7h]
  unsigned int v49; // [rsp+74h] [rbp-B4h]
  HANDLE TokenHandle; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+80h] [rbp-A8h] BYREF
  DWORD pSessionId; // [rsp+84h] [rbp-A4h] BYREF
  void *v53; // [rsp+88h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+90h] [rbp-98h] BYREF
  void *LogonSid; // [rsp+98h] [rbp-90h] BYREF
  unsigned __int8 *v56; // [rsp+A0h] [rbp-88h]
  LPHANDLE lpTargetHandle; // [rsp+A8h] [rbp-80h]
  OOBEUserAuthentication *v58; // [rsp+B0h] [rbp-78h] BYREF
  __int16 v59; // [rsp+B8h] [rbp-70h]
  OOBEUserAuthentication *v60; // [rsp+C0h] [rbp-68h]
  char v61; // [rsp+C8h] [rbp-60h]
  int *v62; // [rsp+D0h] [rbp-58h]
  char v63; // [rsp+D8h] [rbp-50h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+E0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    lpTargetHandle = a4;
    v49 = a3;
    v56 = a2;
    *a4 = 0;
    TokenHandle = 0;
    v46 = 0;
    v62 = &v46;
    v63 = 1;
    v60 = this;
    v5 = 1;
    v61 = 1;
    v6 = (void **)((char *)this + 16);
    if ( *((_QWORD *)this + 2) )
    {
      v5 = 0;
      v61 = 0;
    }
    else
    {
      v7 = (void **)wil::MakeAndInitializeOrThrow<LSAWrapper,>(&LogonSid);
      v8 = *v7;
      *v7 = 0;
      v53 = *v6;
      *v6 = v8;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<OOBEBrokerManager>::InternalRelease(&LogonSid);
    }
    v51 = 0;
    (*(void (__fastcall **)(void *, const char *, unsigned int *))(*(_QWORD *)*v6 + 24LL))(*v6, "Negotiate", &v51);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl) )
    {
      v9 = SeciAllocateAndSetCallFlags(0x2000, &v46);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_NtStatus(retaddr, v10, v11, (const char *)(unsigned int)v9, nSubAuthority2);
    }
    OOBEUserAuthentication::_RemoveBlankPasswordRestriction(this, 1);
    v58 = this;
    v59 = 258;
    v53 = 0;
    v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, 0x28u, &v53);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
        (const char *)(unsigned int)v13,
        nSubAuthority2);
    v14 = v53;
    *(_DWORD *)v53 = 2;
    LogonSid = OOBEUserAuthentication::s_GetLogonSid();
    v14[1] = LogonSid;
    *((_DWORD *)v14 + 4) = -1073741817;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 512;
    pSid = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBC,
        (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
        v15);
    v14[3] = pSid;
    *((_DWORD *)v14 + 8) = 7;
    v16 = CoImpersonateClient();
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
        (const char *)(unsigned int)v16,
        nSubAuthority2a);
    v48 = 1;
    v17 = *v6;
    v18 = *(void (__fastcall **)(void *, _QWORD, unsigned __int8 *, _QWORD))(*(_QWORD *)*v6 + 40LL);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    nSubAuthority2b = (int)v14;
    v18(v17, v51, v56, v49);
    CoRevertToSelf();
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&pSid);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&LogonSid);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v53);
    wil::details::ScopeExitFnGuard__lambda_e4e34b0e61aec955ecbac6caff6a9835___::operator()(&v58);
    if ( v5 )
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v6);
    Process = 0;
    pSessionId = 0;
    v19 = CoImpersonateClient();
  }
  catch ( ... )
  {
    v49 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0xCA,
            (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
            v20);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl) )
    {
      if ( v46 )
        SeciFreeCallContext(v42, v41);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v49;
  }
  LastError = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)(unsigned int)v19,
      nSubAuthority2b);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
      && v46 )
    {
      SeciFreeCallContext(v23, v22);
    }
LABEL_38:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  v48 = 1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &Process,
    0);
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(v24, (unsigned int)&Process, v25);
  LastError = CallingProcessHandle;
  if ( CallingProcessHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      nSubAuthority2b);
    CoRevertToSelf();
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
      && v46 )
    {
      SeciFreeCallContext(v28, v27);
    }
    goto LABEL_38;
  }
  ProcessId = GetProcessId(Process);
  if ( !ProcessIdToSessionId(ProcessId, &pSessionId) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD6,
                  (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
                  v30);
    CoRevertToSelf();
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
      && v46 )
    {
      SeciFreeCallContext(v32, v31);
    }
    goto LABEL_38;
  }
  CoRevertToSelf();
  if ( !SetTokenInformation(TokenHandle, TokenSessionId, &pSessionId, 4u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDA,
                  (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
                  v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
      && v46 )
    {
      SeciFreeCallContext(v35, v34);
    }
    goto LABEL_38;
  }
  v36 = Process;
  v37 = TokenHandle;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v37, v36, lpTargetHandle, 0xEu, 0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE2,
                  (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
                  v39);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
      && v46 )
    {
      ((void (*)(void))SeciFreeCallContext)();
    }
    goto LABEL_38;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl'::`2'::impl)
    && v46 )
  {
    ((void (*)(void))SeciFreeCallContext)();
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18001dcc0  mov     r11, rsp
0x18001dcc3  push    rbx
0x18001dcc4  push    rsi
0x18001dcc5  push    rdi
0x18001dcc6  push    r12
0x18001dcc8  push    r13
0x18001dcca  push    r14
0x18001dccc  push    r15
0x18001dcce  sub     rsp, 0F0h
0x18001dcd5  mov     rax, cs:__security_cookie
0x18001dcdc  xor     rax, rsp
0x18001dcdf  mov     [rsp+128h+var_40], rax
0x18001dce7  mov     [rsp+128h+lpTargetHandle], r9
0x18001dcef  mov     [rsp+128h+var_B4], r8d
0x18001dcf4  mov     [rsp+128h+var_88], rdx
0x18001dcfc  mov     rbx, rcx
0x18001dcff  xor     r14d, r14d
0x18001dd02  mov     [r9], r14
0x18001dd05  mov     [rsp+128h+TokenHandle], r14
0x18001dd0a  mov     [rsp+128h+var_C8], r14d
0x18001dd0f  lea     rax, [rsp+128h+var_C8]
0x18001dd14  mov     [r11-58h], rax
0x18001dd18  mov     byte ptr [r11-50h], 1
0x18001dd1d  mov     [r11-68h], rcx
0x18001dd21  mov     r13b, 1
0x18001dd24  mov     [r11-60h], r13b
0x18001dd28  lea     r12, [rcx+10h]
0x18001dd2c  cmp     [r12], r14
0x18001dd30  jnz     short loc_18001DD70
0x18001dd32  lea     rcx, [r11-90h]
0x18001dd39  call    ??$MakeAndInitializeOrThrow@VLSAWrapper@@$$V@wil@@YA?AV?$ComPtr@VLSAWrapper@@@WRL@Microsoft@@XZ; wil::MakeAndInitializeOrThrow<LSAWrapper,>(void)
0x18001dd3e  mov     rcx, [rax]
0x18001dd41  mov     [rax], r14
0x18001dd44  mov     rax, [r12]
0x18001dd48  mov     [rsp+128h+var_A0], rax
0x18001dd50  mov     [r12], rcx
0x18001dd54  lea     rcx, [rsp+128h+var_A0]
0x18001dd5c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dd61  lea     rcx, [rsp+128h+var_90]
0x18001dd69  call    ?InternalRelease@?$ComPtr@VOOBEBrokerManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OOBEBrokerManager>::InternalRelease(void)
0x18001dd6e  jmp     short loc_18001DD7B
0x18001dd70  mov     r13b, r14b
0x18001dd73  mov     [rsp+128h+var_60], r14b
0x18001dd7b  mov     [rsp+128h+var_A8], r14d
0x18001dd83  mov     rcx, [r12]
0x18001dd87  mov     rax, [rcx]
0x18001dd8a  lea     r8, [rsp+128h+var_A8]
0x18001dd92  lea     rdx, aNegotiate; "Negotiate"
0x18001dd99  mov     rax, [rax+18h]
0x18001dd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dda2  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl(void)'::`2'::impl
0x18001dda9  mov     rcx, r15
0x18001ddac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001ddb1  test    al, al
0x18001ddb3  jz      short loc_18001DDD9
0x18001ddb5  lea     rdx, [rsp+128h+var_C8]
0x18001ddba  mov     ecx, 2000h
0x18001ddbf  call    cs:__imp_SeciAllocateAndSetCallFlags
0x18001ddc5  mov     rcx, [rsp+128h]; this
0x18001ddcd  test    eax, eax
0x18001ddcf  jns     short loc_18001DDD9
0x18001ddd1  mov     r9d, eax; char *
0x18001ddd4  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001ddd9  mov     dl, 1; bool
0x18001dddb  mov     rcx, rbx; this
0x18001ddde  call    ?_RemoveBlankPasswordRestriction@OOBEUserAuthentication@@AEAAX_N@Z; OOBEUserAuthentication::_RemoveBlankPasswordRestriction(bool)
0x18001dde3  mov     [rsp+128h+var_78], rbx
0x18001ddeb  mov     [rsp+128h+var_70], 102h
0x18001ddf5  mov     [rsp+128h+var_A0], r14
0x18001ddfd  lea     r9, [rsp+128h+var_A0]; void **
0x18001de05  mov     edx, 40h ; '@'; unsigned int
0x18001de0a  lea     r8d, [rdx-18h]; unsigned __int64
0x18001de0e  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001de13  mov     rcx, [rsp+128h]; this
0x18001de1b  test    eax, eax
0x18001de1d  js      loc_18001E228
0x18001de23  mov     rbx, [rsp+128h+var_A0]
0x18001de2b  mov     dword ptr [rbx], 2
0x18001de31  call    ?s_GetLogonSid@OOBEUserAuthentication@@CAPEAXXZ; OOBEUserAuthentication::s_GetLogonSid(void)
0x18001de36  mov     [rsp+128h+var_90], rax
0x18001de3e  mov     [rbx+8], rax
0x18001de42  mov     dword ptr [rbx+10h], 0C0000007h
0x18001de49  mov     dword ptr [rsp+128h+pIdentifierAuthority.Value], r14d
0x18001de51  mov     word ptr [rsp+128h+pIdentifierAuthority.Value+4], 200h
0x18001de5b  mov     [rsp+128h+var_98], r14
0x18001de63  lea     rax, [rsp+128h+var_98]
0x18001de6b  mov     [rsp+128h+pSid], rax; pSid
0x18001de70  mov     [rsp+128h+nSubAuthority7], r14d; nSubAuthority7
0x18001de75  mov     [rsp+128h+nSubAuthority6], r14d; nSubAuthority6
0x18001de7a  mov     [rsp+128h+nSubAuthority5], r14d; nSubAuthority5
0x18001de7f  mov     [rsp+128h+nSubAuthority4], r14d; nSubAuthority4
0x18001de84  mov     [rsp+128h+nSubAuthority3], r14d; nSubAuthority3
0x18001de89  mov     [rsp+128h+nSubAuthority2], r14d; int
0x18001de8e  xor     r9d, r9d; nSubAuthority1
0x18001de91  xor     r8d, r8d; nSubAuthority0
0x18001de94  mov     dl, 1; nSubAuthorityCount
0x18001de96  lea     rcx, [rsp+128h+pIdentifierAuthority]; pIdentifierAuthority
0x18001de9e  call    cs:__imp_AllocateAndInitializeSid
0x18001dea4  mov     rcx, [rsp+128h]; this
0x18001deac  test    eax, eax
0x18001deae  jz      loc_18001E23D
0x18001deb4  mov     rax, [rsp+128h+var_98]
0x18001debc  mov     [rbx+18h], rax
0x18001dec0  mov     dword ptr [rbx+20h], 7
0x18001dec7  call    cs:__imp_CoImpersonateClient
0x18001decd  mov     rcx, [rsp+128h]; this
0x18001ded5  test    eax, eax
0x18001ded7  js      loc_18001E24E
0x18001dedd  mov     [rsp+128h+var_B7], 1
0x18001dee2  mov     rsi, [r12]
0x18001dee6  mov     rax, [rsi]
0x18001dee9  mov     rdi, [rax+28h]
0x18001deed  xor     edx, edx
0x18001deef  lea     rcx, [rsp+128h+TokenHandle]
0x18001def4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001def9  lea     rax, [rsp+128h+TokenHandle]
0x18001defe  mov     qword ptr [rsp+128h+nSubAuthority3], rax
0x18001df03  mov     qword ptr [rsp+128h+nSubAuthority2], rbx; int
0x18001df08  mov     r9d, [rsp+128h+var_B4]
0x18001df0d  mov     r8, [rsp+128h+var_88]
0x18001df15  mov     edx, [rsp+128h+var_A8]
0x18001df1c  mov     rcx, rsi
0x18001df1f  mov     rax, rdi
0x18001df22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df27  nop
0x18001df28  call    cs:__imp_CoRevertToSelf
0x18001df2e  nop
0x18001df2f  lea     rcx, [rsp+128h+var_98]
0x18001df37  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001df3c  nop
0x18001df3d  lea     rcx, [rsp+128h+var_90]
0x18001df45  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001df4a  nop
0x18001df4b  lea     rcx, [rsp+128h+var_A0]
0x18001df53  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001df58  nop
0x18001df59  lea     rcx, [rsp+128h+var_78]
0x18001df61  call    wil__details__ScopeExitFnGuard__lambda_e4e34b0e61aec955ecbac6caff6a9835_____operator__
0x18001df66  nop
0x18001df67  test    r13b, r13b
0x18001df6a  jz      short loc_18001DF75
0x18001df6c  mov     rcx, r12
0x18001df6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001df74  nop
0x18001df75  mov     [rsp+128h+Process], r14
0x18001df7a  mov     [rsp+128h+pSessionId], r14d
0x18001df82  call    cs:__imp_CoImpersonateClient
0x18001df88  mov     ebx, eax
0x18001df8a  test    eax, eax
0x18001df8c  jns     short loc_18001DFD5
0x18001df8e  mov     rcx, [rsp+128h]; this
0x18001df96  mov     r9d, eax; char *
0x18001df99  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001dfa0  mov     edx, 0D0h; void *
0x18001dfa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfaa  nop
0x18001dfab  lea     rcx, [rsp+128h+Process]
0x18001dfb0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dfb5  nop
0x18001dfb6  mov     rcx, r15
0x18001dfb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001dfbe  test    al, al
0x18001dfc0  jz      short loc_18001DFD0
0x18001dfc2  cmp     [rsp+128h+var_C8], r14d
0x18001dfc7  jz      short loc_18001DFD0
0x18001dfc9  call    cs:__imp_SeciFreeCallContext
0x18001dfcf  nop
0x18001dfd0  jmp     loc_18001E195
0x18001dfd5  mov     [rsp+128h+var_B7], 1
0x18001dfda  xor     edx, edx
0x18001dfdc  lea     rcx, [rsp+128h+Process]
0x18001dfe1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001dfe6  lea     rdx, [rsp+128h+Process]; unsigned int
0x18001dfeb  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x18001dff0  mov     ebx, eax
0x18001dff2  test    eax, eax
0x18001dff4  jns     short loc_18001E044
0x18001dff6  mov     rcx, [rsp+128h]; this
0x18001dffe  mov     r9d, eax; char *
0x18001e001  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001e008  mov     edx, 0D5h; void *
0x18001e00d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e012  nop
0x18001e013  call    cs:__imp_CoRevertToSelf
0x18001e019  nop
0x18001e01a  lea     rcx, [rsp+128h+Process]
0x18001e01f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e024  nop
0x18001e025  mov     rcx, r15
0x18001e028  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e02d  test    al, al
0x18001e02f  jz      short loc_18001E03F
0x18001e031  cmp     [rsp+128h+var_C8], r14d
0x18001e036  jz      short loc_18001E03F
0x18001e038  call    cs:__imp_SeciFreeCallContext
0x18001e03e  nop
0x18001e03f  jmp     loc_18001E195
0x18001e044  mov     rcx, [rsp+128h+Process]; Process
0x18001e049  call    cs:__imp_GetProcessId
0x18001e04f  mov     ecx, eax; dwProcessId
0x18001e051  lea     rdx, [rsp+128h+pSessionId]; pSessionId
0x18001e059  call    cs:__imp_ProcessIdToSessionId
0x18001e05f  test    eax, eax
0x18001e061  jnz     short loc_18001E0AF
0x18001e063  mov     rcx, [rsp+128h]; this
0x18001e06b  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001e072  mov     edx, 0D6h; void *
0x18001e077  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e07c  mov     ebx, eax
0x18001e07e  call    cs:__imp_CoRevertToSelf
0x18001e084  nop
0x18001e085  lea     rcx, [rsp+128h+Process]
0x18001e08a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e08f  nop
0x18001e090  mov     rcx, r15
0x18001e093  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e098  test    al, al
0x18001e09a  jz      short loc_18001E0AA
0x18001e09c  cmp     [rsp+128h+var_C8], r14d
0x18001e0a1  jz      short loc_18001E0AA
0x18001e0a3  call    cs:__imp_SeciFreeCallContext
0x18001e0a9  nop
0x18001e0aa  jmp     loc_18001E195
0x18001e0af  call    cs:__imp_CoRevertToSelf
0x18001e0b5  mov     r9d, 4; TokenInformationLength
0x18001e0bb  lea     r8, [rsp+128h+pSessionId]; TokenInformation
0x18001e0c3  lea     edx, [r9+8]; TokenInformationClass
0x18001e0c7  mov     rcx, [rsp+128h+TokenHandle]; TokenHandle
0x18001e0cc  call    cs:__imp_SetTokenInformation
0x18001e0d2  test    eax, eax
0x18001e0d4  jnz     short loc_18001E118
0x18001e0d6  mov     rcx, [rsp+128h]; this
0x18001e0de  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001e0e5  mov     edx, 0DAh; void *
0x18001e0ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e0ef  mov     ebx, eax
0x18001e0f1  lea     rcx, [rsp+128h+Process]
0x18001e0f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e0fb  nop
0x18001e0fc  mov     rcx, r15
0x18001e0ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e104  test    al, al
0x18001e106  jz      short loc_18001E116
0x18001e108  cmp     [rsp+128h+var_C8], r14d
0x18001e10d  jz      short loc_18001E116
0x18001e10f  call    cs:__imp_SeciFreeCallContext
0x18001e115  nop
0x18001e116  jmp     short loc_18001E195
0x18001e118  mov     rbx, [rsp+128h+Process]
0x18001e11d  mov     rdi, [rsp+128h+TokenHandle]
0x18001e122  call    cs:__imp_GetCurrentProcess
0x18001e128  mov     [rsp+128h+nSubAuthority4], r14d; dwOptions
0x18001e12d  mov     [rsp+128h+nSubAuthority3], r14d; bInheritHandle
0x18001e132  mov     [rsp+128h+nSubAuthority2], 0Eh; dwDesiredAccess
0x18001e13a  mov     r9, [rsp+128h+lpTargetHandle]; lpTargetHandle
0x18001e142  mov     r8, rbx; hTargetProcessHandle
0x18001e145  mov     rdx, rdi; hSourceHandle
0x18001e148  mov     rcx, rax; hSourceProcessHandle
0x18001e14b  call    cs:__imp_DuplicateHandle
0x18001e151  test    eax, eax
0x18001e153  jnz     short loc_18001E1A3
0x18001e155  mov     rcx, [rsp+128h]; this
0x18001e15d  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001e164  mov     edx, 0E2h; void *
0x18001e169  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e16e  mov     ebx, eax
0x18001e170  lea     rcx, [rsp+128h+Process]
0x18001e175  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e17a  nop
0x18001e17b  mov     rcx, r15
0x18001e17e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e183  test    al, al
0x18001e185  jz      short loc_18001E195
0x18001e187  cmp     [rsp+128h+var_C8], r14d
0x18001e18c  jz      short loc_18001E195
0x18001e18e  call    cs:__imp_SeciFreeCallContext
0x18001e194  nop
0x18001e195  lea     rcx, [rsp+128h+TokenHandle]
0x18001e19a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e19f  mov     eax, ebx
0x18001e1a1  jmp     short loc_18001E205
0x18001e1a3  lea     rcx, [rsp+128h+Process]
0x18001e1a8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e1ad  nop
0x18001e1ae  mov     rcx, r15
0x18001e1b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e1b6  test    al, al
0x18001e1b8  jz      short loc_18001E1C8
0x18001e1ba  cmp     [rsp+128h+var_C8], r14d
0x18001e1bf  jz      short loc_18001E1C8
0x18001e1c1  call    cs:__imp_SeciFreeCallContext
0x18001e1c7  nop
0x18001e1c8  lea     rcx, [rsp+128h+TokenHandle]
0x18001e1cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e1d2  xor     eax, eax
0x18001e1d4  jmp     short loc_18001E205
0x18001e1d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::GetImpl(void)'::`2'::impl
0x18001e1dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HelloPolicyPreventsPinResetFix>::__private_IsEnabled(void)
0x18001e1e2  xor     r14d, r14d
0x18001e1e5  test    al, al
  ... truncated ...
```
