# ProcessWebAuthNCommand

- ea: `0x18001dfb8`
- end: `0x18001e81e`
- name: `ProcessWebAuthNCommand`
- size: `2150`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dd350`

## callees

- `0x180007f90`
- `0x18000a8c0`
- `0x18000ab38`
- `0x18000b040`
- `0x18001687c`
- `0x1800187d0`
- `0x18001df88`
- `0x18001dfb8`
- `0x18001e824`
- `0x18001e848`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180022d34`
- `0x18002bbf4`
- `0x18002d194`
- `0x180037f6c`
- `0x18003a3c0`
- `0x18003b150`
- `0x1800466ec`
- `0x1800467e0`
- `0x180048b70`
- `0x180052df0`
- `0x18005378c`
- `0x1800537a4`
- `0x18006f750`
- `0x180077f4c`
- `0x18007e064`
- `0x1800d8900`
- `0x1800d8b90`
- `0x1800d92c0`
- `0x1800d990c`
- `0x1800dbb00`
- `0x1800dbbfc`
- `0x1800dbdb8`
- `0x1800dbee8`
- `0x1800dc14c`
- `0x1800dc260`
- `0x1800dc3e4`
- `0x1800dc6c8`
- `0x1800dca50`
- `0x1800dcc20`
- `0x1800e3d50`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e6bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e6bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e191`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e757`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e191`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e757`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e14d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e795`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e14d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e795`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e699`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e699`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e5b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e5b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e7cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e7cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e07b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e07b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e70f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e70f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e499`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e57b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e499`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e57b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e153`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e153`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e2d3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e2d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e3d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e3d0`

## string_xrefs

- `0x18001e2ad`: `onecore\ds\security\fido\ctap\transports\ctapsrv.cpp`
- `0x18001e544`: `onecore\ds\security\fido\ctap\transports\ctapsrv.cpp`
- `0x18001e7eb`: `ProcessWebAuthNCommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProcessWebAuthNCommand(__int64 a1, void *a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v8; // r13
  __int64 v9; // rax
  RTL_SRWLOCK *v10; // r14
  HANDLE EventW; // r12
  int v12; // eax
  HANDLE *v13; // r15
  unsigned int CtapRpcToken; // ebx
  WebAuthnCommandStack *v15; // rcx
  int CallerProcessInfo; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  HLOCAL v20; // rcx
  unsigned int v21; // esi
  _BYTE *v22; // rdx
  int AssertionRequest; // ebx
  int v24; // edx
  HLOCAL v25; // rcx
  bool v26; // zf
  HLOCAL v27; // rcx
  const unsigned __int16 *v28; // rbx
  int CredentialRequest; // ebx
  int UsageSession; // eax
  HLOCAL v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  unsigned int v34; // eax
  DWORD v35; // eax
  unsigned int Ptr_high; // eax
  HLOCAL v37; // rax
  HLOCAL v38; // rsi
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  char v42[8]; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v43; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int TokenInformation; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+5Ch] [rbp-A4h] BYREF
  void *v48; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v49; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PVOID pv; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v52; // [rsp+80h] [rbp-80h]
  char v53[8]; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL *p_hMem; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  char v56; // [rsp+A0h] [rbp-60h]
  __int64 v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  int v59; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v60; // [rsp+C8h] [rbp-38h]
  const wchar_t *v61; // [rsp+D0h] [rbp-30h]
  _BYTE v62[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v63; // [rsp+1F0h] [rbp+F0h] BYREF
  OLECHAR sz[40]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v63 = a4;
  v57 = a1;
  v52 = a5;
  memset_0(&v59, 0, 0x110u);
  v8 = *(_QWORD *)(a3 + 56);
  v58 = *(_QWORD *)(v8 + 152);
  v9 = v58;
  v10 = 0;
  pv = 0;
  EventW = 0;
  v48 = 0;
  *a5 = 0;
  *a4 = 0;
  if ( !v9 || !*(_QWORD *)(v9 + 32) || !qword_1801AF1C8 )
  {
    CtapRpcToken = 87;
    goto LABEL_18;
  }
  InitOnceExecuteOnce(&InitOnce, WebAuthNTimeoutInitOnceCallback, 0, 0);
  v12 = dword_1801AF1AC;
  *(_DWORD *)(v8 + 12) = dword_1801AF1AC;
  if ( !v12 )
    *(_DWORD *)(v8 + 12) = 604800000;
  v13 = (HANDLE *)(a3 + 64);
  CtapRpcToken = GetCtapRpcToken(a2, (_QWORD *)(a3 + 64));
  if ( !CtapRpcToken )
  {
    CtapRpcToken = CtapSrvCheckWebAuthNCallerToken(*v13);
    if ( !CtapRpcToken )
    {
      CtapRpcToken = CtapSrvQueryTokenSecurityAttributes(*v13);
      if ( !CtapRpcToken )
      {
        CtapSrvExtractTokenSecurityPublisher(0, a3 + 80);
        CtapSrvGetCallerProcessImageName(a2, (WCHAR **)&v48);
        if ( !*(_QWORD *)(a3 + 80) && v48 )
          CtapSrvGetPublisherFromImageName(a2);
        CtapRpcToken = CtapSrvGetApplication(0, *(_QWORD *)(a3 + 80) != 0, v48, a3 + 72);
        if ( !CtapRpcToken )
        {
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
          {
            AcquireSRWLockExclusive(&stru_1801AF050);
            GetTickCount64();
            if ( qword_1801AF1B8 )
              CtapRpcToken = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) != 0
                           ? 1791
                           : -2147417829;
            else
              qword_1801AF1B8 = a3;
            ReleaseSRWLockExclusive(&stru_1801AF050);
            if ( CtapRpcToken )
              goto LABEL_18;
            goto LABEL_68;
          }
          Block = 0;
          wil::impersonate_token(&hMem, *v13);
          v43 = 0;
          if ( wil::open_current_access_token_nothrow(&v43) < 0 )
          {
            CtapRpcToken = GetLastError();
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v43);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hMem);
            goto LABEL_18;
          }
          if ( (int)wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v43) < 0 )
          {
            CtapRpcToken = GetLastError();
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v43);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hMem);
            goto LABEL_24;
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v43);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hMem);
          std::wstring::wstring(v62);
          v42[0] = 0;
          memset_0(sz, 0, 0x4Eu);
          CallerProcessInfo = CtapUtilsGetCallerProcessInfo(a2, (int)*v13, (struct WEBAUTHN_CALLER_INFO *)(a3 + 88));
          if ( CallerProcessInfo >= 0 )
          {
            if ( *(_BYTE *)(a3 + 90) && !*(_BYTE *)(a3 + 89) )
            {
              std::wstring::operator=(v62, a3 + 128);
              goto LABEL_32;
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1029,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports\\ctapsrv.cpp",
              (const char *)(unsigned int)CallerProcessInfo,
              ReturnLength);
          }
          if ( StringFromGUID2((const GUID *const)(*(_QWORD *)(a3 + 56) + 16LL), sz, 39) )
          {
            v17 = -1;
            do
              ++v17;
            while ( sz[v17] );
            std::wstring::_Assign<unsigned short>(v62, sz);
          }
LABEL_32:
          v18 = std::wstring::wstring(&p_hMem, v62);
          if ( (unsigned int)WebAuthnCommandStack::CommandAllowed(v19, v42, v18) || !v42[0] )
          {
            CtapRpcToken = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) != 0
                         ? 1791
                         : -2147417829;
            goto LABEL_47;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::GetImpl'::`2'::impl) )
          {
            v47 = 0;
            v21 = *(_DWORD *)(a3 + 92);
            if ( !v21 )
            {
              v21 = 0;
              wil::impersonate_token(v53, *v13);
              TokenHandle = 0;
              if ( wil::open_current_access_token_nothrow(&TokenHandle) >= 0 )
              {
                TokenInformation = 0;
                v49 = 0;
                if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &v49) )
                  v21 = TokenInformation;
              }
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v53);
            }
            v43 = 0;
            hMem = 0;
            v22 = *(_BYTE **)(v8 + 144);
            if ( *v22 == 1 )
            {
              p_hMem = &v43;
              v55 = 0;
              v56 = 1;
              CredentialRequest = CtapCborDecodeMakeCredentialRequest(
                                    *(_DWORD *)(v8 + 136) - 1,
                                    (int)v22 + 1,
                                    (unsigned int)&v55,
                                    0,
                                    0);
              wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
              if ( CredentialRequest )
              {
LABEL_49:
                CtapRpcToken = 87;
LABEL_50:
                v25 = hMem;
                v26 = hMem == 0;
                hMem = 0;
                if ( !v26 )
                  LocalFree(v25);
                v27 = v43;
                v43 = 0;
                if ( v27 )
                  LocalFree(v27);
                goto LABEL_47;
              }
              v28 = *(const unsigned __int16 **)(*((_QWORD *)v43 + 4) + 8LL);
            }
            else
            {
              if ( *v22 != 2 )
              {
                CtapRpcToken = 87;
                hMem = 0;
                v43 = 0;
LABEL_47:
                std::wstring::_Tidy_deallocate(v62);
LABEL_24:
                if ( Block )
                  operator delete(Block);
                goto LABEL_18;
              }
              p_hMem = &hMem;
              v55 = 0;
              v56 = 1;
              AssertionRequest = CtapCborDecodeGetAssertionRequest(
                                   *(_DWORD *)(v8 + 136) - 1,
                                   (int)v22 + 1,
                                   (unsigned int)&v55,
                                   0,
                                   0);
              wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
              if ( AssertionRequest )
                goto LABEL_49;
              v28 = (const unsigned __int16 *)*((_QWORD *)hMem + 1);
            }
            if ( (int)CheckPasskeyCAMCapability((unsigned int)L"passkeys", v24, v21, (_DWORD)v28, (__int64)&v47) < 0
              || v47 != 3 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl)
                && (byte_1801AEA01 & 0x10) != 0 )
              {
                McGenEventWrite_EventWriteTransfer(v32, &EVENT_CTAP_FUNCTION_CAPABILITYDENIED, v33, 1, &v63);
              }
              CtapRpcToken = -2147417829;
              goto LABEL_50;
            }
            UsageSession = createUsageSession(v21, L"passkeys", v28);
            if ( UsageSession < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x109B,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports\\ctapsrv.cpp",
                (const char *)(unsigned int)UsageSession,
                ReturnLengtha);
            v31 = hMem;
            hMem = 0;
            if ( v31 )
              LocalFree(v31);
            v20 = v43;
            v43 = 0;
            if ( v20 )
              LocalFree(v20);
          }
          CtapRpcToken = WebAuthnCommandStack::AddCommand(
                           (WebAuthnCommandStack *)v20,
                           (struct _CTAPDEVICE_COMMAND_INFO *)a3);
          if ( !CtapRpcToken )
          {
            std::wstring::_Tidy_deallocate(v62);
            if ( Block )
              operator delete(Block);
LABEL_68:
            EventW = CreateEventW(0, 0, 0, 0);
            if ( EventW )
            {
              v59 = 1;
              v60 = L"WebAuthNProvider";
              v61 = L"MicrosoftWebAuthNProvider";
              CtapRpcToken = CtapDeviceCreateControlBlock(&v59, a3, EventW, &pv);
              v10 = (RTL_SRWLOCK *)pv;
              if ( !CtapRpcToken )
              {
                CtapRpcToken = CtapDeviceTrySubmitThreadpoolCallback(ProcessWebAuthNCommandCallback, pv);
                if ( !CtapRpcToken )
                {
                  v34 = WaitForSingleProviderOrRpcCancel(v57, a3, EventW);
                  if ( v34 )
                  {
                    CtapSrvLogError(v34, "CancelWebAuthNAuthenticator", "WaitFor");
                    SetEvent(*(HANDLE *)(a3 + 40));
                    ((void (__fastcall *)(_QWORD))qword_1801AF1C8)(*(_QWORD *)(v58 + 32));
                    v35 = WaitForSingleObject(EventW, 0x7D0u);
                    CtapSrvLogError(v35, "CancelWebAuthNAuthenticator", "dwWait");
                  }
                  AcquireSRWLockExclusive(v10 + 2);
                  if ( (unsigned int)(LODWORD(v10[40].Ptr) - 4) <= 2 )
                  {
                    CtapRpcToken = HIDWORD(v10[40].Ptr);
                    Ptr_high = HIDWORD(v10[42].Ptr);
                    if ( Ptr_high )
                    {
                      v37 = LocalAlloc(0x40u, Ptr_high);
                      v38 = v37;
                      if ( v37 )
                      {
                        memcpy_0(v37, v10[43].Ptr, HIDWORD(v10[42].Ptr));
                        *v63 = v38;
                        *v52 = HIDWORD(v10[42].Ptr);
                      }
                      else
                      {
                        CtapRpcToken = _GetNonzeroLastError();
                      }
                    }
                  }
                  else
                  {
                    CtapRpcToken = 1223;
                  }
                  ReleaseSRWLockExclusive(v10 + 2);
                }
              }
            }
            else
            {
              CtapRpcToken = _GetNonzeroLastError();
            }
            goto LABEL_18;
          }
          goto LABEL_47;
        }
      }
    }
  }
LABEL_18:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
  {
    WebAuthnCommandStack::PopCommand(v15, (struct _CTAPDEVICE_COMMAND_INFO *)a3);
  }
  else
  {
    AcquireSRWLockExclusive(&stru_1801AF050);
    if ( qword_1801AF1B8 == a3 )
      qword_1801AF1B8 = 0;
    ReleaseSRWLockExclusive(&stru_1801AF050);
  }
  CtapDeviceFreeControlBlock(v10);
  if ( EventW )
    CloseHandle(EventW);
  FidoFree(0);
  FidoFree(v48);
  CtapSrvLogError(CtapRpcToken, "ProcessWebAuthNCommand", "Stop");
  return CtapRpcToken;
}

```

## disassembly

```asm
0x18001dfb8  push    rbp
0x18001dfba  push    rbx
0x18001dfbb  push    rsi
0x18001dfbc  push    rdi
0x18001dfbd  push    r12
0x18001dfbf  push    r13
0x18001dfc1  push    r14
0x18001dfc3  push    r15
0x18001dfc5  lea     rbp, [rsp-168h]
0x18001dfcd  sub     rsp, 268h
0x18001dfd4  mov     rax, cs:__security_cookie
0x18001dfdb  xor     rax, rsp
0x18001dfde  mov     [rbp+1A0h+var_50], rax
0x18001dfe5  mov     rbx, r9
0x18001dfe8  mov     [rbp+1A0h+var_B0], rbx
0x18001dfef  mov     rdi, r8
0x18001dff2  mov     rsi, rdx
0x18001dff5  mov     [rbp+1A0h+var_1F0], rcx
0x18001dff9  mov     rax, [rbp+1A0h+arg_20]
0x18001e000  mov     [rbp+1A0h+var_220], rax
0x18001e004  xor     edx, edx; Val
0x18001e006  mov     r8d, 110h; Size
0x18001e00c  lea     rcx, [rbp+1A0h+var_1E0]; void *
0x18001e010  call    memset_0
0x18001e015  mov     r13, [rdi+38h]
0x18001e019  mov     rax, [r13+98h]
0x18001e020  mov     [rbp+1A0h+var_1E8], rax
0x18001e024  xor     edx, edx
0x18001e026  mov     r14d, edx
0x18001e029  mov     [rsp+2A0h+pv], rdx
0x18001e02e  mov     r12d, edx
0x18001e031  mov     r15d, edx
0x18001e034  mov     [rsp+2A0h+var_270], rdx
0x18001e039  mov     [rsp+2A0h+var_240], rdx
0x18001e03e  mov     rcx, [rbp+1A0h+var_220]
0x18001e042  mov     [rcx], edx
0x18001e044  mov     [rbx], rdx
0x18001e047  test    rax, rax
0x18001e04a  jz      loc_18001E784
0x18001e050  cmp     [rax+20h], rdx
0x18001e054  jz      loc_18001E784
0x18001e05a  cmp     cs:qword_1801AF1C8, rdx
0x18001e061  jz      loc_18001E784
0x18001e067  xor     r9d, r9d; Context
0x18001e06a  xor     r8d, r8d; Parameter
0x18001e06d  lea     rdx, _WebAuthNTimeoutInitOnceCallback; InitFn
0x18001e074  lea     rcx, InitOnce; InitOnce
0x18001e07b  call    cs:__imp_InitOnceExecuteOnce
0x18001e081  mov     eax, cs:dword_1801AF1AC
0x18001e087  mov     [r13+0Ch], eax
0x18001e08b  test    eax, eax
0x18001e08d  jnz     short loc_18001E097
0x18001e08f  mov     dword ptr [r13+0Ch], 240C8400h
0x18001e097  lea     r15, [rdi+40h]
0x18001e09b  mov     rdx, r15
0x18001e09e  mov     rcx, rsi; BindingHandle
0x18001e0a1  call    _GetCtapRpcToken
0x18001e0a6  mov     ebx, eax
0x18001e0a8  test    eax, eax
0x18001e0aa  jnz     loc_18001E19F
0x18001e0b0  mov     rcx, [r15]; TokenHandle
0x18001e0b3  call    _CtapSrvCheckWebAuthNCallerToken
0x18001e0b8  mov     ebx, eax
0x18001e0ba  test    eax, eax
0x18001e0bc  jnz     loc_18001E19F
0x18001e0c2  lea     rdx, [rsp+2A0h+var_270]
0x18001e0c7  mov     rcx, [r15]; TokenHandle
0x18001e0ca  call    _CtapSrvQueryTokenSecurityAttributes
0x18001e0cf  mov     ebx, eax
0x18001e0d1  test    eax, eax
0x18001e0d3  jnz     loc_18001E19F
0x18001e0d9  lea     rbx, [rdi+50h]
0x18001e0dd  mov     rdx, rbx
0x18001e0e0  mov     rcx, [rsp+2A0h+var_270]
0x18001e0e5  call    _CtapSrvExtractTokenSecurityPublisher
0x18001e0ea  lea     rdx, [rsp+2A0h+var_240]
0x18001e0ef  mov     rcx, rsi; BindingHandle
0x18001e0f2  call    _CtapSrvGetCallerProcessImageName
0x18001e0f7  xor     eax, eax
0x18001e0f9  cmp     [rbx], rax
0x18001e0fc  jnz     short loc_18001E115
0x18001e0fe  mov     rdx, [rsp+2A0h+var_240]
0x18001e103  test    rdx, rdx
0x18001e106  jz      short loc_18001E115
0x18001e108  mov     r8, rbx
0x18001e10b  mov     rcx, rsi; BindingHandle
0x18001e10e  call    _CtapSrvGetPublisherFromImageName
0x18001e113  xor     eax, eax
0x18001e115  lea     r9, [rdi+48h]
0x18001e119  mov     edx, eax
0x18001e11b  cmp     [rbx], rax
0x18001e11e  setnz   dl
0x18001e121  mov     r8, [rsp+2A0h+var_240]
0x18001e126  mov     rcx, [rsp+2A0h+var_270]
0x18001e12b  call    _CtapSrvGetApplication
0x18001e130  mov     ebx, eax
0x18001e132  test    eax, eax
0x18001e134  jnz     short loc_18001E19F
0x18001e136  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x18001e13d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x18001e142  test    al, al
0x18001e144  jnz     short loc_18001E1C5
0x18001e146  lea     rcx, stru_1801AF050; SRWLock
0x18001e14d  call    cs:__imp_AcquireSRWLockExclusive
0x18001e153  call    cs:__imp_GetTickCount64
0x18001e159  xor     r15d, r15d
0x18001e15c  cmp     cs:qword_1801AF1B8, r15
0x18001e163  jz      short loc_18001E183
0x18001e165  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18001e16c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18001e171  neg     al
0x18001e173  sbb     ebx, ebx
0x18001e175  and     ebx, 7FFF05E4h
0x18001e17b  add     ebx, 8001011Bh
0x18001e181  jmp     short loc_18001E18A
0x18001e183  mov     cs:qword_1801AF1B8, rdi
0x18001e18a  lea     rcx, stru_1801AF050; SRWLock
0x18001e191  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e197  test    ebx, ebx
0x18001e199  jz      loc_18001E5AF
0x18001e19f  mov     r15, [rsp+2A0h+var_270]
0x18001e1a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x18001e1ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x18001e1b0  test    al, al
0x18001e1b2  jz      loc_18001E78E
0x18001e1b8  mov     rdx, rdi; struct _CTAPDEVICE_COMMAND_INFO *
0x18001e1bb  call    ?PopCommand@WebAuthnCommandStack@@QEAAKPEAU_CTAPDEVICE_COMMAND_INFO@@@Z; WebAuthnCommandStack::PopCommand(_CTAPDEVICE_COMMAND_INFO *)
0x18001e1c0  jmp     loc_18001E7BC
0x18001e1c5  xor     ebx, ebx
0x18001e1c7  mov     [rsp+2A0h+Block], rbx
0x18001e1cc  mov     rdx, [r15]
0x18001e1cf  lea     rcx, [rsp+2A0h+hMem]
0x18001e1d4  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18001e1d9  mov     [rsp+2A0h+var_260], rbx
0x18001e1de  lea     rcx, [rsp+2A0h+var_260]
0x18001e1e3  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x18001e1e8  test    eax, eax
0x18001e1ea  jns     short loc_18001E20B
0x18001e1ec  call    cs:__imp_GetLastError
0x18001e1f2  mov     ebx, eax
0x18001e1f4  lea     rcx, [rsp+2A0h+var_260]
0x18001e1f9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e1fe  lea     rcx, [rsp+2A0h+hMem]
0x18001e203  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001e208  nop
0x18001e209  jmp     short loc_18001E19F
0x18001e20b  mov     rdx, [rsp+2A0h+var_260]
0x18001e210  lea     rcx, [rsp+2A0h+Block]
0x18001e215  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18001e21a  test    eax, eax
0x18001e21c  jns     short loc_18001E253
0x18001e21e  call    cs:__imp_GetLastError
0x18001e224  mov     ebx, eax
0x18001e226  lea     rcx, [rsp+2A0h+var_260]
0x18001e22b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e230  lea     rcx, [rsp+2A0h+hMem]
0x18001e235  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001e23a  nop
0x18001e23b  mov     rcx, [rsp+2A0h+Block]; Block
0x18001e240  test    rcx, rcx
0x18001e243  jz      loc_18001E19F
0x18001e249  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e24e  jmp     loc_18001E19F
0x18001e253  lea     rcx, [rsp+2A0h+var_260]
0x18001e258  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e25d  lea     rcx, [rsp+2A0h+hMem]
0x18001e262  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001e267  lea     rcx, [rbp+1A0h+var_D0]
0x18001e26e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e273  nop
0x18001e274  mov     [rsp+2A0h+var_268], bl
0x18001e278  xor     edx, edx; Val
0x18001e27a  lea     r8d, [rdx+4Eh]; Size
0x18001e27e  lea     rcx, [rbp+1A0h+sz]; void *
0x18001e285  call    memset_0
0x18001e28a  lea     r8, [rdi+58h]
0x18001e28e  mov     rdx, [r15]
0x18001e291  mov     rcx, rsi
0x18001e294  call    ?CtapUtilsGetCallerProcessInfo@@YAJPEAXQEAXAEAV?$unique_struct@UWEBAUTHN_CALLER_INFO@@P6AXPEAU1@@Z$1?FreeCallerInfo@@YAX0@ZP6AX0@Z$1?InitCallerInfo@@YAX0@Z@wil@@@Z; CtapUtilsGetCallerProcessInfo(void *,void * const,wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)> &)
0x18001e299  mov     rcx, [rbp+1A8h]; this
0x18001e2a0  xor     edx, edx
0x18001e2a2  test    eax, eax
0x18001e2a4  jns     loc_18001E35D
0x18001e2aa  mov     r9d, eax; char *
0x18001e2ad  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001e2b4  mov     edx, 1029h; void *
0x18001e2b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e2be  mov     rcx, [rdi+38h]
0x18001e2c2  add     rcx, 10h; rguid
0x18001e2c6  mov     r8d, 27h ; '''; cchMax
0x18001e2cc  lea     rdx, [rbp+1A0h+sz]; lpsz
0x18001e2d3  call    cs:__imp_StringFromGUID2
0x18001e2d9  xor     ebx, ebx
0x18001e2db  test    eax, eax
0x18001e2dd  jz      short loc_18001E307
0x18001e2df  lea     rax, [rbp+1A0h+sz]
0x18001e2e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e2ea  inc     r8
0x18001e2ed  cmp     [rax+r8*2], bx
0x18001e2f2  jnz     short loc_18001E2EA
0x18001e2f4  lea     rdx, [rbp+1A0h+sz]
0x18001e2fb  lea     rcx, [rbp+1A0h+var_D0]
0x18001e302  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001e307  lea     rdx, [rbp+1A0h+var_D0]
0x18001e30e  lea     rcx, [rbp+1A0h+var_210]
0x18001e312  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e317  mov     r8, rax
0x18001e31a  lea     rdx, [rsp+2A0h+var_268]
0x18001e31f  call    ?CommandAllowed@WebAuthnCommandStack@@QEBAKPEA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAuthnCommandStack::CommandAllowed(bool *,std::wstring)
0x18001e324  test    eax, eax
0x18001e326  jnz     loc_18001E762
0x18001e32c  cmp     [rsp+2A0h+var_268], bl
0x18001e330  jz      loc_18001E762
0x18001e336  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::GetImpl(void)'::`2'::impl
0x18001e33d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::__private_IsEnabled(void)
0x18001e342  test    al, al
0x18001e344  jz      loc_18001E581
0x18001e34a  mov     [rsp+2A0h+var_244], ebx
0x18001e34e  mov     esi, [rdi+5Ch]
0x18001e351  test    esi, esi
0x18001e353  jz      short loc_18001E386
0x18001e355  xor     r15d, r15d
0x18001e358  jmp     loc_18001E3F0
0x18001e35d  cmp     [rdi+5Ah], dl
0x18001e360  jz      loc_18001E2BE
0x18001e366  cmp     [rdi+59h], dl
0x18001e369  jnz     loc_18001E2BE
0x18001e36f  lea     rdx, [rdi+80h]
0x18001e376  lea     rcx, [rbp+1A0h+var_D0]
0x18001e37d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001e382  xor     ebx, ebx
0x18001e384  jmp     short loc_18001E307
0x18001e386  mov     esi, ebx
0x18001e388  mov     rdx, [r15]
0x18001e38b  lea     rcx, [rbp+1A0h+var_218]
0x18001e38f  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18001e394  xor     r15d, r15d
0x18001e397  mov     [rsp+2A0h+TokenHandle], r15
0x18001e39c  lea     rcx, [rsp+2A0h+TokenHandle]
0x18001e3a1  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x18001e3a6  test    eax, eax
0x18001e3a8  js      short loc_18001E3DD
0x18001e3aa  mov     [rsp+2A0h+TokenInformation], r15d
0x18001e3af  mov     [rsp+2A0h+var_238], r15d
0x18001e3b4  lea     rax, [rsp+2A0h+var_238]
0x18001e3b9  mov     qword ptr [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18001e3be  lea     r9d, [r15+4]; TokenInformationLength
0x18001e3c2  lea     r8, [rsp+2A0h+TokenInformation]; TokenInformation
0x18001e3c7  lea     edx, [r15+0Ch]; TokenInformationClass
0x18001e3cb  mov     rcx, [rsp+2A0h+TokenHandle]; TokenHandle
0x18001e3d0  call    cs:__imp_GetTokenInformation
0x18001e3d6  test    eax, eax
0x18001e3d8  cmovnz  esi, [rsp+2A0h+TokenInformation]
0x18001e3dd  lea     rcx, [rsp+2A0h+TokenHandle]
0x18001e3e2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e3e7  lea     rcx, [rbp+1A0h+var_218]
0x18001e3eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001e3f0  mov     [rsp+2A0h+var_260], r15
0x18001e3f5  mov     [rsp+2A0h+hMem], r15
0x18001e3fa  mov     rdx, [r13+90h]
0x18001e401  movzx   ecx, byte ptr [rdx]
0x18001e404  sub     ecx, 1
0x18001e407  jz      loc_18001E4AC
0x18001e40d  cmp     ecx, 1
0x18001e410  jz      short loc_18001E432
0x18001e412  mov     ebx, 57h ; 'W'
0x18001e417  mov     [rsp+2A0h+hMem], r15
0x18001e41c  mov     [rsp+2A0h+var_260], r15
0x18001e421  lea     rcx, [rbp+1A0h+var_D0]
0x18001e428  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e42d  jmp     loc_18001E23B
0x18001e432  lea     rax, [rsp+2A0h+hMem]
0x18001e437  mov     [rbp+1A0h+var_210], rax
0x18001e43b  mov     [rbp+1A0h+var_208], r15
0x18001e43f  mov     [rbp+1A0h+var_200], 1
0x18001e443  inc     rdx
0x18001e446  mov     ecx, [r13+88h]
0x18001e44d  dec     ecx
0x18001e44f  mov     qword ptr [rsp+2A0h+ReturnLength], r15
0x18001e454  xor     r9d, r9d
0x18001e457  lea     r8, [rbp+1A0h+var_208]
0x18001e45b  call    CtapCborDecodeGetAssertionRequest
0x18001e460  mov     ebx, eax
0x18001e462  lea     rcx, [rbp+1A0h+var_210]
0x18001e466  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001e46b  test    ebx, ebx
0x18001e46d  jz      short loc_18001E4A1
0x18001e46f  mov     ebx, 57h ; 'W'
0x18001e474  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18001e479  test    rcx, rcx
0x18001e47c  mov     [rsp+2A0h+hMem], r15
0x18001e481  jz      short loc_18001E48A
0x18001e483  call    cs:__imp_LocalFree
0x18001e489  nop
0x18001e48a  mov     rcx, [rsp+2A0h+var_260]; hMem
0x18001e48f  mov     [rsp+2A0h+var_260], r15
0x18001e494  test    rcx, rcx
0x18001e497  jz      short loc_18001E421
0x18001e499  call    cs:__imp_LocalFree
0x18001e49f  jmp     short loc_18001E421
  ... truncated ...
```
