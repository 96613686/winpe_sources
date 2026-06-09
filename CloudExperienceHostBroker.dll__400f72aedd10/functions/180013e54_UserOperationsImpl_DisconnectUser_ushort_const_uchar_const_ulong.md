# UserOperationsImpl::DisconnectUser(ushort const *,uchar const *,ulong)

- ea: `0x180013e54`
- end: `0x1800143c0`
- name: `?DisconnectUser@UserOperationsImpl@@AEAAJPEBGPEBEK@Z`
- size: `1388`
- prototype: `__int64 __fastcall(UserOperationsImpl *this, const unsigned __int16 *, unsigned __int8 *, ULONG)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012dc0`

## callees

- `0x180002a3c`
- `0x180005fe0`
- `0x180006330`
- `0x180008344`
- `0x180009f30`
- `0x18000e6f4`
- `0x180010978`
- `0x180011968`
- `0x1800119d0`
- `0x180012184`
- `0x180012470`
- `0x180013e54`
- `0x180017d10`
- `0x180017e44`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800141ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014234`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800141ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014234`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014199`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014199`
- `ntdll!RtlInitString` at `0x180013f3d`
- `ntdll!RtlInitString` at `0x180013f55`
- `ntdll!RtlInitString` at `0x180013f3d`
- `ntdll!RtlInitString` at `0x180013f55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001410d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001410d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800140b9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800140b9`
- `SspiCli!LsaConnectUntrusted` at `0x180013fdd`
- `SspiCli!LsaConnectUntrusted` at `0x180013fdd`
- `SspiCli!LsaLogonUser` at `0x18001409f`
- `SspiCli!LsaLogonUser` at `0x18001409f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180014001`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180014001`
- `CRYPT32!CryptBinaryToStringW` at `0x180014212`
- `CRYPT32!CryptBinaryToStringW` at `0x180014269`
- `CRYPT32!CryptBinaryToStringW` at `0x180014212`
- `CRYPT32!CryptBinaryToStringW` at `0x180014269`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800142a6`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18001430c`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x1800142a6`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18001430c`
- `CRYPTSP!CryptGenRandom` at `0x1800141e2`
- `CRYPTSP!CryptGenRandom` at `0x1800141e2`
- `CRYPTSP!CryptAcquireContextW` at `0x180014185`
- `CRYPTSP!CryptAcquireContextW` at `0x180014185`

## string_xrefs

- `0x180014015`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x1800140cf`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
__int64 __fastcall UserOperationsImpl::DisconnectUser(
        UserOperationsImpl *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        ULONG a4)
{
  _lambda_7bc21641c3dbb0019505230e296066f9_ *v7; // rax
  NTSTATUS v8; // eax
  unsigned int LastError; // ebx
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  unsigned __int64 v12; // r9
  NTSTATUS v13; // eax
  const char *v14; // r9
  __int64 v15; // rdx
  HRESULT v16; // eax
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, const unsigned __int16 *, const wchar_t *, _QWORD); // rbx
  int v19; // eax
  HANDLE ProcessHeap; // rax
  BYTE *v21; // rax
  WCHAR *v22; // rax
  unsigned __int16 *v23; // rax
  int v24; // eax
  __int64 *AuthenticationInformation; // [rsp+20h] [rbp-E0h]
  bool v27; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchString; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pcchMaxChars; // [rsp+78h] [rbp-88h] BYREF
  int SubStatus; // [rsp+7Ch] [rbp-84h] BYREF
  ULONG AuthenticationPackage; // [rsp+80h] [rbp-80h] BYREF
  CRED_PROTECTION_TYPE ProtectionType; // [rsp+84h] [rbp-7Ch] BYREF
  void *LsaHandle; // [rsp+88h] [rbp-78h] BYREF
  BYTE *pbBinary; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hHeap; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR pszCredentials; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hToken; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+C0h] [rbp-40h] BYREF
  ULONG ProfileBufferLength; // [rsp+C4h] [rbp-3Ch] BYREF
  HCRYPTPROV phProv; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v43; // [rsp+D0h] [rbp-30h] BYREF
  PVOID ProfileBuffer; // [rsp+D8h] [rbp-28h] BYREF
  struct _LUID LogonId; // [rsp+E0h] [rbp-20h] BYREF
  struct _STRING v46; // [rsp+E8h] [rbp-18h] BYREF
  _STRING DestinationString; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v48[112]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v49[96]; // [rsp+180h] [rbp+80h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v52[42]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v52);
  v52[0] = &MSAClientTraceTelemetry::DisconnectAccountOobe::`vftable';
  MSAClientTraceTelemetry::DisconnectAccountOobe::StartActivity((MSAClientTraceTelemetry::DisconnectAccountOobe *)v52);
  hToken = 0;
  v27 = 0;
  LsaHandle = 0;
  ppv = 0;
  v37 = 0;
  pbBinary = 0;
  pszCredentials = 0;
  v43 = 0;
  v40 = 32;
  pcchString = 0;
  pcchMaxChars = 0;
  ProtectionType = CredUnprotected;
  SubStatus = 0;
  SourceContext = 0;
  ProfileBuffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  hHeap = 0;
  phProv = 0;
  DestinationString = 0;
  RtlInitString(&DestinationString, "DisconnectAccountOobe");
  v46 = 0;
  RtlInitString(&v46, "CloudAP");
  AuthenticationPackage = 0;
  v7 = _lambda_7bc21641c3dbb0019505230e296066f9_::_lambda_7bc21641c3dbb0019505230e296066f9_(
         (_lambda_7bc21641c3dbb0019505230e296066f9_ *)v49,
         &v27,
         &ProfileBuffer,
         &SubStatus,
         &LsaHandle,
         &pbBinary,
         &pszCredentials,
         &v43,
         &v40,
         &pcchString,
         &pcchMaxChars,
         &hHeap,
         &phProv);
  wil::ScopeExit<_lambda_7bc21641c3dbb0019505230e296066f9_>(v48, v7);
  v8 = LsaConnectUntrusted(&LsaHandle);
  LastError = v8 | 0x10000000;
  if ( v8 >= 0 )
  {
    v11 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&v46, &AuthenticationPackage);
    LastError = v11 | 0x10000000;
    if ( v11 >= 0 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hToken,
        0);
      v13 = LsaLogonUser(
              LsaHandle,
              (PLSA_STRING)&DestinationString,
              Interactive,
              AuthenticationPackage,
              a3,
              a4,
              0,
              &SourceContext,
              &ProfileBuffer,
              &ProfileBufferLength,
              &LogonId,
              &hToken,
              &Quotas,
              &SubStatus);
      LastError = v13 | 0x10000000;
      if ( v13 >= 0 )
      {
        if ( ImpersonateLoggedOnUser(hToken) )
        {
          v27 = 1;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          v16 = CoCreateInstance(
                  &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
                  0,
                  1u,
                  &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
                  &ppv);
          LastError = v16;
          if ( v16 < 0 )
          {
            v12 = (unsigned int)v16;
            v10 = 582;
            goto LABEL_6;
          }
          v17 = ppv;
          v18 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
          AuthenticationInformation = &v37;
          v19 = v18(v17, a2, L"MicrosoftAccount", 0);
          LastError = v19;
          if ( v19 < 0 )
          {
            v12 = (unsigned int)v19;
            v10 = 588;
            goto LABEL_6;
          }
          if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
          {
            ProcessHeap = GetProcessHeap();
            hHeap = ProcessHeap;
            if ( ProcessHeap )
            {
              v21 = (BYTE *)HeapAlloc(ProcessHeap, 0, 0x20u);
              pbBinary = v21;
              if ( !v21 )
              {
                LastError = -2147024882;
                v10 = 606;
                goto LABEL_5;
              }
              if ( CryptGenRandom(phProv, 0x20u, v21) )
              {
                if ( CryptBinaryToStringW(pbBinary, 0x20u, 0x40000001u, 0, &pcchString) )
                {
                  v22 = (WCHAR *)HeapAlloc(hHeap, 0, 2LL * pcchString);
                  pszCredentials = v22;
                  if ( !v22 )
                  {
                    LastError = -2147024882;
                    v10 = 626;
                    goto LABEL_5;
                  }
                  if ( CryptBinaryToStringW(pbBinary, 0x20u, 0x40000001u, v22, &pcchString) )
                  {
                    if ( CredProtectW(0, pszCredentials, ++pcchString, 0, &pcchMaxChars, &ProtectionType) )
                    {
                      LastError = -2147418113;
                      v10 = 648;
                      goto LABEL_5;
                    }
                    v23 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2LL * pcchMaxChars);
                    v43 = v23;
                    if ( !v23 )
                    {
                      LastError = -2147024882;
                      v10 = 652;
                      goto LABEL_5;
                    }
                    if ( CredProtectW(0, pszCredentials, pcchString, v23, &pcchMaxChars, &ProtectionType) )
                    {
                      LODWORD(AuthenticationInformation) = a4;
                      v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int8 *))(*(_QWORD *)v37 + 40LL))(
                              v37,
                              0,
                              v43,
                              a3);
                      LastError = v24;
                      if ( v24 >= 0 )
                      {
                        wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
                        LastError = 0;
                        goto LABEL_39;
                      }
                      v12 = (unsigned int)v24;
                      v10 = 667;
                      goto LABEL_6;
                    }
                    v15 = 661;
                  }
                  else
                  {
                    v15 = 634;
                  }
                }
                else
                {
                  v15 = 621;
                }
              }
              else
              {
                v15 = 612;
              }
            }
            else
            {
              v15 = 602;
            }
          }
          else
          {
            v15 = 598;
          }
        }
        else
        {
          v15 = 574;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v15,
                      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
                      v14);
        goto LABEL_39;
      }
      v10 = 572;
    }
    else
    {
      v10 = 556;
    }
  }
  else
  {
    v10 = 554;
  }
LABEL_5:
  v12 = LastError;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
    (const char *)v12,
    (int)AuthenticationInformation);
LABEL_39:
  wil::details::ScopeExitFn<_lambda_7bc21641c3dbb0019505230e296066f9_>::~ScopeExitFn<_lambda_7bc21641c3dbb0019505230e296066f9_>(v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  MSAClientTraceTelemetry::DisconnectAccountOobe::~DisconnectAccountOobe((MSAClientTraceTelemetry::DisconnectAccountOobe *)v52);
  return LastError;
}

```

## disassembly

```asm
0x180013e54  mov     [rsp-8+arg_0], rbx
0x180013e59  push    rbp
0x180013e5a  push    rsi
0x180013e5b  push    rdi
0x180013e5c  push    r12
0x180013e5e  push    r13
0x180013e60  push    r14
0x180013e62  push    r15
0x180013e64  lea     rbp, [rsp-280h]
0x180013e6c  sub     rsp, 380h
0x180013e73  mov     rax, cs:__security_cookie
0x180013e7a  xor     rax, rsp
0x180013e7d  mov     [rbp+2B0h+var_40], rax
0x180013e84  mov     r14d, r9d
0x180013e87  mov     rsi, r8
0x180013e8a  mov     r15, rdx
0x180013e8d  lea     rdx, SourceString; "DisconnectAccountOobe"
0x180013e94  lea     rcx, [rbp+2B0h+var_190]; struct wil::details::IFailureCallback *
0x180013e9b  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180013ea0  lea     rax, ??_7DisconnectAccountOobe@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::DisconnectAccountOobe::`vftable'
0x180013ea7  mov     [rbp+2B0h+var_190], rax
0x180013eae  lea     rcx, [rbp+2B0h+var_190]; this
0x180013eb5  call    ?StartActivity@DisconnectAccountOobe@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::DisconnectAccountOobe::StartActivity(void)
0x180013eba  nop
0x180013ebb  xor     r12d, r12d
0x180013ebe  mov     [rbp+2B0h+hToken], r12
0x180013ec2  mov     [rsp+3B0h+var_340], r12b
0x180013ec7  mov     [rbp+2B0h+LsaHandle], r12
0x180013ecb  mov     [rbp+2B0h+ppv], r12
0x180013ecf  mov     [rbp+2B0h+var_308], r12
0x180013ed3  mov     [rbp+2B0h+pbBinary], r12
0x180013ed7  mov     [rbp+2B0h+pszCredentials], r12
0x180013edb  mov     [rbp+2B0h+var_2E0], r12
0x180013edf  lea     r13d, [r12+20h]
0x180013ee4  mov     [rbp+2B0h+var_2F0], r13d
0x180013ee8  mov     [rsp+3B0h+pcchString], r12d
0x180013eed  mov     [rsp+3B0h+pcchMaxChars], r12d
0x180013ef2  mov     [rbp+2B0h+ProtectionType], r12d
0x180013ef6  mov     [rsp+3B0h+var_334], r12d
0x180013efb  xorps   xmm0, xmm0
0x180013efe  movups  xmmword ptr [rbp+2B0h+var_1D0.SourceName], xmm0
0x180013f05  mov     [rbp+2B0h+var_2D8], r12
0x180013f09  mov     [rbp+2B0h+var_2EC], r12d
0x180013f0d  mov     qword ptr [rbp+2B0h+var_2D0.LowPart], r12
0x180013f11  movups  xmmword ptr [rbp+2B0h+var_1C0.PagedPoolLimit], xmm0
0x180013f18  movups  xmmword ptr [rbp+2B0h+var_1C0.MinimumWorkingSetSize], xmm0
0x180013f1f  movups  xmmword ptr [rbp+2B0h+var_1C0.PagefileLimit], xmm0
0x180013f26  mov     [rbp+2B0h+hHeap], r12
0x180013f2a  mov     [rbp+2B0h+phProv], r12
0x180013f2e  movups  xmmword ptr [rbp+2B0h+DestinationString.Length], xmm0
0x180013f32  lea     rdx, SourceString; "DisconnectAccountOobe"
0x180013f39  lea     rcx, [rbp+2B0h+DestinationString]; DestinationString
0x180013f3d  call    cs:__imp_RtlInitString
0x180013f43  xorps   xmm0, xmm0
0x180013f46  movups  xmmword ptr [rbp+2B0h+var_2C8.Length], xmm0
0x180013f4a  lea     rdx, aCloudap; "CloudAP"
0x180013f51  lea     rcx, [rbp+2B0h+var_2C8]; DestinationString
0x180013f55  call    cs:__imp_RtlInitString
0x180013f5b  mov     [rbp+2B0h+AuthenticationPackage], r12d
0x180013f5f  lea     rax, [rbp+2B0h+phProv]
0x180013f63  mov     [rsp+3B0h+Quotas], rax; unsigned __int64 *
0x180013f68  lea     rax, [rbp+2B0h+hHeap]
0x180013f6c  mov     [rsp+3B0h+Token], rax; void **
0x180013f71  lea     rax, [rsp+3B0h+pcchMaxChars]
0x180013f76  mov     [rsp+3B0h+LogonId], rax; unsigned int *
0x180013f7b  lea     rax, [rsp+3B0h+pcchString]
0x180013f80  mov     [rsp+3B0h+ProfileBufferLength], rax; unsigned int *
0x180013f85  lea     rax, [rbp+2B0h+var_2F0]
0x180013f89  mov     [rsp+3B0h+ProfileBuffer], rax; unsigned int *
0x180013f8e  lea     rax, [rbp+2B0h+var_2E0]
0x180013f92  mov     [rsp+3B0h+SourceContext], rax; unsigned __int16 **
0x180013f97  lea     rax, [rbp+2B0h+pszCredentials]
0x180013f9b  mov     [rsp+3B0h+LocalGroups], rax; unsigned __int16 **
0x180013fa0  lea     rax, [rbp+2B0h+pbBinary]
0x180013fa4  mov     qword ptr [rsp+3B0h+AuthenticationInformationLength], rax; unsigned __int8 **
0x180013fa9  lea     rax, [rbp+2B0h+LsaHandle]
0x180013fad  mov     [rsp+3B0h+AuthenticationInformation], rax; int
0x180013fb2  lea     r9, [rsp+3B0h+var_334]; int *
0x180013fb7  lea     r8, [rbp+2B0h+var_2D8]; void **
0x180013fbb  lea     rdx, [rsp+3B0h+var_340]; bool *
0x180013fc0  lea     rcx, [rbp+2B0h+var_230]; this
0x180013fc7  call    ??0_lambda_7bc21641c3dbb0019505230e296066f9_@@QEAA@AEA_NAEAPEAXAEAJ1AEAPEAEAEAPEAG4AEBKAEAK61AEA_K@Z; _lambda_7bc21641c3dbb0019505230e296066f9_::_lambda_7bc21641c3dbb0019505230e296066f9_(bool &,void * &,long &,void * &,uchar * &,ushort * &,ushort * &,ulong const &,ulong &,ulong &,void * &,unsigned __int64 &)
0x180013fcc  mov     rdx, rax
0x180013fcf  lea     rcx, [rbp+2B0h+var_2A0]
0x180013fd3  call    ??$ScopeExit@V_lambda_7bc21641c3dbb0019505230e296066f9_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_7bc21641c3dbb0019505230e296066f9_@@@details@0@$$QEAV_lambda_7bc21641c3dbb0019505230e296066f9_@@@Z; wil::ScopeExit<_lambda_7bc21641c3dbb0019505230e296066f9_>(_lambda_7bc21641c3dbb0019505230e296066f9_ &&)
0x180013fd8  nop
0x180013fd9  lea     rcx, [rbp+2B0h+LsaHandle]; LsaHandle
0x180013fdd  call    cs:__imp_LsaConnectUntrusted
0x180013fe3  mov     ebx, eax
0x180013fe5  mov     edi, 10000000h
0x180013fea  or      ebx, edi
0x180013fec  jge     short loc_180013FF5
0x180013fee  mov     edx, 22Ah
0x180013ff3  jmp     short loc_180014012
0x180013ff5  lea     r8, [rbp+2B0h+AuthenticationPackage]; AuthenticationPackage
0x180013ff9  lea     rdx, [rbp+2B0h+var_2C8]; PackageName
0x180013ffd  mov     rcx, [rbp+2B0h+LsaHandle]; LsaHandle
0x180014001  call    cs:__imp_LsaLookupAuthenticationPackage
0x180014007  mov     ebx, eax
0x180014009  or      ebx, edi
0x18001400b  jge     short loc_18001402D
0x18001400d  mov     edx, 22Ch; void *
0x180014012  mov     r9d, ebx; char *
0x180014015  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x18001401c  mov     rcx, [rbp+2B8h]; this
0x180014023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014028  jmp     loc_180014360
0x18001402d  xor     edx, edx
0x18001402f  lea     rcx, [rbp+2B0h+hToken]
0x180014033  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180014038  lea     rax, [rsp+3B0h+var_334]
0x18001403d  mov     [rsp+3B0h+SubStatus], rax; SubStatus
0x180014042  lea     rax, [rbp+2B0h+var_1C0]
0x180014049  mov     [rsp+3B0h+Quotas], rax; Quotas
0x18001404e  lea     rax, [rbp+2B0h+hToken]
0x180014052  mov     [rsp+3B0h+Token], rax; Token
0x180014057  lea     rax, [rbp+2B0h+var_2D0]
0x18001405b  mov     [rsp+3B0h+LogonId], rax; LogonId
0x180014060  lea     rax, [rbp+2B0h+var_2EC]
0x180014064  mov     [rsp+3B0h+ProfileBufferLength], rax; ProfileBufferLength
0x180014069  lea     rax, [rbp+2B0h+var_2D8]
0x18001406d  mov     [rsp+3B0h+ProfileBuffer], rax; ProfileBuffer
0x180014072  lea     rax, [rbp+2B0h+var_1D0]
0x180014079  mov     [rsp+3B0h+SourceContext], rax; SourceContext
0x18001407e  mov     [rsp+3B0h+LocalGroups], r12; LocalGroups
0x180014083  mov     [rsp+3B0h+AuthenticationInformationLength], r14d; AuthenticationInformationLength
0x180014088  mov     [rsp+3B0h+AuthenticationInformation], rsi; AuthenticationInformation
0x18001408d  mov     r9d, [rbp+2B0h+AuthenticationPackage]; AuthenticationPackage
0x180014091  mov     r8d, 2; LogonType
0x180014097  lea     rdx, [rbp+2B0h+DestinationString]; OriginName
0x18001409b  mov     rcx, [rbp+2B0h+LsaHandle]; LsaHandle
0x18001409f  call    cs:__imp_LsaLogonUser
0x1800140a5  mov     ebx, eax
0x1800140a7  or      ebx, edi
0x1800140a9  jge     short loc_1800140B5
0x1800140ab  mov     edx, 23Ch
0x1800140b0  jmp     loc_180014012
0x1800140b5  mov     rcx, [rbp+2B0h+hToken]; hToken
0x1800140b9  call    cs:__imp_ImpersonateLoggedOnUser
0x1800140bf  test    eax, eax
0x1800140c1  jnz     short loc_1800140E2
0x1800140c3  mov     edx, 23Eh; void *
0x1800140c8  mov     rcx, [rbp+2B8h]; this
0x1800140cf  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800140d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800140db  mov     ebx, eax
0x1800140dd  jmp     loc_180014360
0x1800140e2  mov     [rsp+3B0h+var_340], 1
0x1800140e7  lea     rcx, [rbp+2B0h+ppv]
0x1800140eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800140f0  lea     rax, [rbp+2B0h+ppv]
0x1800140f4  mov     [rsp+3B0h+AuthenticationInformation], rax; ppv
0x1800140f9  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180014100  xor     edx, edx; pUnkOuter
0x180014102  lea     r8d, [rdx+1]; dwClsContext
0x180014106  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18001410d  call    cs:__imp_CoCreateInstance
0x180014113  mov     ebx, eax
0x180014115  test    eax, eax
0x180014117  jns     short loc_180014126
0x180014119  mov     r9d, eax
0x18001411c  mov     edx, 246h
0x180014121  jmp     loc_180014015
0x180014126  mov     rdi, [rbp+2B0h+ppv]
0x18001412a  mov     rax, [rdi]
0x18001412d  mov     rbx, [rax+30h]
0x180014131  lea     rcx, [rbp+2B0h+var_308]
0x180014135  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001413a  lea     rax, [rbp+2B0h+var_308]
0x18001413e  mov     [rsp+3B0h+AuthenticationInformation], rax
0x180014143  xor     r9d, r9d
0x180014146  lea     r8, aMicrosoftaccou; "MicrosoftAccount"
0x18001414d  mov     rdx, r15
0x180014150  mov     rcx, rdi
0x180014153  mov     rax, rbx
0x180014156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001415b  mov     ebx, eax
0x18001415d  test    eax, eax
0x18001415f  jns     short loc_18001416E
0x180014161  mov     r9d, eax
0x180014164  mov     edx, 24Ch
0x180014169  jmp     loc_180014015
0x18001416e  mov     dword ptr [rsp+3B0h+AuthenticationInformation], 0F0000040h; dwFlags
0x180014176  mov     r9d, 18h; dwProvType
0x18001417c  xor     r8d, r8d; szProvider
0x18001417f  xor     edx, edx; szContainer
0x180014181  lea     rcx, [rbp+2B0h+phProv]; phProv
0x180014185  call    cs:__imp_CryptAcquireContextW
0x18001418b  test    eax, eax
0x18001418d  jnz     short loc_180014199
0x18001418f  mov     edx, 256h
0x180014194  jmp     loc_1800140C8
0x180014199  call    cs:__imp_GetProcessHeap
0x18001419f  mov     [rbp+2B0h+hHeap], rax
0x1800141a3  test    rax, rax
0x1800141a6  jnz     short loc_1800141B2
0x1800141a8  mov     edx, 25Ah
0x1800141ad  jmp     loc_1800140C8
0x1800141b2  mov     r8, r13; dwBytes
0x1800141b5  xor     edx, edx; dwFlags
0x1800141b7  mov     rcx, rax; hHeap
0x1800141ba  call    cs:__imp_HeapAlloc
0x1800141c0  mov     [rbp+2B0h+pbBinary], rax
0x1800141c4  test    rax, rax
0x1800141c7  jnz     short loc_1800141D8
0x1800141c9  mov     ebx, 8007000Eh
0x1800141ce  mov     edx, 25Eh
0x1800141d3  jmp     loc_180014012
0x1800141d8  mov     r8, rax; pbBuffer
0x1800141db  mov     edx, r13d; dwLen
0x1800141de  mov     rcx, [rbp+2B0h+phProv]; hProv
0x1800141e2  call    cs:__imp_CryptGenRandom
0x1800141e8  test    eax, eax
0x1800141ea  jnz     short loc_1800141F6
0x1800141ec  mov     edx, 264h
0x1800141f1  jmp     loc_1800140C8
0x1800141f6  lea     rax, [rsp+3B0h+pcchString]
0x1800141fb  mov     [rsp+3B0h+AuthenticationInformation], rax; pcchString
0x180014200  xor     r9d, r9d; pszString
0x180014203  mov     ebx, 40000001h
0x180014208  mov     r8d, ebx; dwFlags
0x18001420b  mov     edx, r13d; cbBinary
0x18001420e  mov     rcx, [rbp+2B0h+pbBinary]; pbBinary
0x180014212  call    cs:__imp_CryptBinaryToStringW
0x180014218  test    eax, eax
0x18001421a  jnz     short loc_180014226
0x18001421c  mov     edx, 26Dh
0x180014221  jmp     loc_1800140C8
0x180014226  mov     r8d, [rsp+3B0h+pcchString]
0x18001422b  add     r8, r8; dwBytes
0x18001422e  xor     edx, edx; dwFlags
0x180014230  mov     rcx, [rbp+2B0h+hHeap]; hHeap
0x180014234  call    cs:__imp_HeapAlloc
0x18001423a  mov     [rbp+2B0h+pszCredentials], rax
0x18001423e  test    rax, rax
0x180014241  jnz     short loc_180014252
0x180014243  mov     ebx, 8007000Eh
0x180014248  mov     edx, 272h
0x18001424d  jmp     loc_180014012
0x180014252  lea     rcx, [rsp+3B0h+pcchString]
0x180014257  mov     [rsp+3B0h+AuthenticationInformation], rcx; pcchString
0x18001425c  mov     r9, rax; pszString
0x18001425f  mov     r8d, ebx; dwFlags
0x180014262  mov     edx, r13d; cbBinary
0x180014265  mov     rcx, [rbp+2B0h+pbBinary]; pbBinary
0x180014269  call    cs:__imp_CryptBinaryToStringW
0x18001426f  test    eax, eax
0x180014271  jnz     short loc_18001427D
0x180014273  mov     edx, 27Ah
0x180014278  jmp     loc_1800140C8
0x18001427d  mov     r8d, [rsp+3B0h+pcchString]
0x180014282  inc     r8d; cchCredentials
0x180014285  mov     [rsp+3B0h+pcchString], r8d
0x18001428a  lea     rax, [rbp+2B0h+ProtectionType]
0x18001428e  mov     qword ptr [rsp+3B0h+AuthenticationInformationLength], rax; ProtectionType
0x180014293  lea     rax, [rsp+3B0h+pcchMaxChars]
0x180014298  mov     [rsp+3B0h+AuthenticationInformation], rax; pcchMaxChars
0x18001429d  xor     r9d, r9d; pszProtectedCredentials
0x1800142a0  mov     rdx, [rbp+2B0h+pszCredentials]; pszCredentials
0x1800142a4  xor     ecx, ecx; fAsSelf
0x1800142a6  call    cs:__imp_CredProtectW
0x1800142ac  test    eax, eax
0x1800142ae  jz      short loc_1800142BF
0x1800142b0  mov     ebx, 8000FFFFh
0x1800142b5  mov     edx, 288h
0x1800142ba  jmp     loc_180014012
0x1800142bf  mov     r8d, [rsp+3B0h+pcchMaxChars]
0x1800142c4  add     r8, r8; dwBytes
0x1800142c7  xor     edx, edx; dwFlags
0x1800142c9  mov     rcx, [rbp+2B0h+hHeap]; hHeap
0x1800142cd  call    cs:__imp_HeapAlloc
0x1800142d3  mov     [rbp+2B0h+var_2E0], rax
0x1800142d7  test    rax, rax
0x1800142da  jnz     short loc_1800142EB
0x1800142dc  mov     ebx, 8007000Eh
0x1800142e1  mov     edx, 28Ch
0x1800142e6  jmp     loc_180014012
0x1800142eb  lea     rcx, [rbp+2B0h+ProtectionType]
0x1800142ef  mov     qword ptr [rsp+3B0h+AuthenticationInformationLength], rcx; ProtectionType
0x1800142f4  lea     rcx, [rsp+3B0h+pcchMaxChars]
0x1800142f9  mov     [rsp+3B0h+AuthenticationInformation], rcx; pcchMaxChars
0x1800142fe  mov     r9, rax; pszProtectedCredentials
0x180014301  mov     r8d, [rsp+3B0h+pcchString]; cchCredentials
0x180014306  mov     rdx, [rbp+2B0h+pszCredentials]; pszCredentials
0x18001430a  xor     ecx, ecx; fAsSelf
0x18001430c  call    cs:__imp_CredProtectW
0x180014312  test    eax, eax
0x180014314  jnz     short loc_180014320
0x180014316  mov     edx, 295h
0x18001431b  jmp     loc_1800140C8
0x180014320  mov     rcx, [rbp+2B0h+var_308]
0x180014324  mov     rax, [rcx]
0x180014327  mov     dword ptr [rsp+3B0h+AuthenticationInformation], r14d
0x18001432c  mov     r9, rsi
0x18001432f  mov     r8, [rbp+2B0h+var_2E0]
0x180014333  xor     edx, edx
0x180014335  mov     rax, [rax+28h]
0x180014339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001433e  mov     ebx, eax
0x180014340  test    eax, eax
  ... truncated ...
```
