# GetAndVerifyAuthBrokerClientContext(uint,_AUTH_BROKER_CLIENT_CONTEXT * *)

- ea: `0x180002b20`
- end: `0x1800030b7`
- name: `?GetAndVerifyAuthBrokerClientContext@@YAJIPEAPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z`
- size: `1431`
- prototype: `__int64 __fastcall(unsigned int brokerFlags, _AUTH_BROKER_CLIENT_CONTEXT **clientContext)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002420`
- `0x180017770`

## callees

- `0x180002b20`
- `0x1800030c0`
- `0x180003330`
- `0x1800047d0`
- `0x180004940`
- `0x180006060`
- `0x1800060f8`
- `0x180006d0c`
- `0x18000737c`
- `0x18000f34c`
- `0x180011b30`
- `0x180011df4`
- `0x180012018`
- `0x180012128`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002b48`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002b48`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180002ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180002ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002ca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003030`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002bd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002bd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003039`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003039`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180002cfe`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180002cfe`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180002cde`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180002cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003021`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002c66`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002c66`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180002d5c`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180002d5c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180002ef0`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180002ef0`

## pseudocode

```c
__int64 __fastcall GetAndVerifyAuthBrokerClientContext(
        unsigned int brokerFlags,
        _AUTH_BROKER_CLIENT_CONTEXT **clientContext)
{
  unsigned int v2; // r15d
  _AUTH_BROKER_CLIENT_CONTEXT *Value; // rax
  _AUTH_BROKER_CLIENT_CONTEXT *v5; // rbx
  unsigned __int16 v6; // dx
  const _GUID *v7; // r8
  HRESULT AuthBrokerClientInfoFromRpcThread; // edi
  int v9; // r12d
  const wchar_t *v10; // r15
  int v11; // eax
  HRESULT IsApplicationServiceSupported; // ebx
  WaitForCompletion::__l2::FTMEventDelegate *ptr; // rcx
  __int64 ProcessId; // rdi
  WaitForCompletion::__l2::FTMEventDelegate *v15; // rcx
  WaitForCompletion::__l2::FTMEventDelegate *v16; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *); // rbx
  __int64 v19; // rcx
  HKEY v20; // rcx
  HWND__ *v21; // rdi
  _AUTH_BROKER_CLIENT_CONTEXT *v22; // rax
  void *tokenHandle; // r12
  int v24; // eax
  unsigned int i; // r15d
  WPP_PROJECT_CONTROL_BLOCK *v26; // rcx
  WPP_PROJECT_CONTROL_BLOCK *v27; // rcx
  unsigned __int16 v28; // dx
  wchar_t *dialogTitle; // rcx
  void *v30; // rcx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  HWND__ *hwndParent; // [rsp+38h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+40h]
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> Data; // [rsp+98h] [rbp+50h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> Type; // [rsp+A0h] [rbp+58h] BYREF
  __int64 cbData; // [rsp+A8h] [rbp+60h] BYREF

  v2 = brokerFlags;
  if ( clientContextTlsIndex != -1 )
  {
    Value = (_AUTH_BROKER_CLIENT_CONTEXT *)TlsGetValue(clientContextTlsIndex);
    v5 = Value;
    if ( Value )
    {
      AddRefAuthBrokerClientContext(Value);
      AuthBrokerClientInfoFromRpcThread = 0;
      goto LABEL_51;
    }
  }
  LODWORD(cbData) = 4;
  hwndParent = 0;
  LODWORD(Data.ptr_) = 0;
  LODWORD(Type.ptr_) = 0;
  hKey = 0;
  v9 = 0;
  v10 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\authhost.exe",
          0,
          0x20019u,
          &hKey)
    && (RegQueryValueExW(hKey, L"EnableTestSystemUI", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData)
     || LODWORD(Type.ptr_) != 4
     || (_DWORD)cbData != 4) )
  {
    LODWORD(Data.ptr_) = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( LODWORD(Data.ptr_) )
  {
    v9 = 8;
    v10 = L"Test System UI Title";
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x61u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
    }
  }
  hwndParent = 0;
  hKey = 0;
  cbData = 0;
  Type.ptr_ = 0;
  Data.ptr_ = 0;
  v11 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, (void **)&Data.ptr_);
  IsApplicationServiceSupported = v11;
  if ( v11 >= 0 )
  {
    IsApplicationServiceSupported = Data.ptr_->Invoke(
                                      Data.ptr_,
                                      (Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *)4096,
                                      (ABI::Windows::Foundation::AsyncStatus)&Type);
    if ( IsApplicationServiceSupported < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Data);
      goto LABEL_27;
    }
    goto LABEL_21;
  }
  if ( v11 == -2147417833 )
  {
    Type.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)GetCurrentProcess();
LABEL_21:
    ptr = Data.ptr_;
    if ( Data.ptr_ )
    {
      Data.ptr_ = 0;
      ptr->Release(ptr);
    }
    ProcessId = GetProcessId(Type.ptr_);
    IsApplicationServiceSupported = CoreIsApplicationServiceSupported(
                                      ProcessId,
                                      &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1);
    if ( IsApplicationServiceSupported >= 0 )
      IsApplicationServiceSupported = CoreQueryApplicationService(
                                        (unsigned int)ProcessId,
                                        &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
                                        &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
                                        &cbData);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x58u, "onecore\\shell\\lib\\calleridentity\\calleridentity.cpp", v11);
  v15 = Data.ptr_;
  if ( Data.ptr_ )
  {
    Data.ptr_ = 0;
    v15->Release(v15);
  }
LABEL_27:
  v16 = Type.ptr_;
  Type.ptr_ = 0;
  if ( (unsigned __int64)&v16[-1]._hEventCompleted + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16);
  if ( IsApplicationServiceSupported >= 0 )
  {
    LODWORD(Data.ptr_) = 0;
    IsApplicationServiceSupported = CoGetCallerTID((LPDWORD)&Data);
    if ( IsApplicationServiceSupported >= 0 )
    {
      if ( (unsigned int)(LODWORD(Data.ptr_) - 1) > 0xFFFFFFFD )
      {
        IsApplicationServiceSupported = -2147023728;
      }
      else
      {
        v17 = cbData;
        Type.ptr_ = 0;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *))(*(_QWORD *)cbData + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Type);
        IsApplicationServiceSupported = v18(v17, LODWORD(Data.ptr_), &Type);
        if ( IsApplicationServiceSupported >= 0 )
          IsApplicationServiceSupported = Type.ptr_->QueryInterface(
                                            Type.ptr_,
                                            &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f,
                                            (void **)&hKey);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Type);
      }
    }
  }
  v19 = cbData;
  if ( cbData )
  {
    cbData = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( IsApplicationServiceSupported >= 0 )
    IsApplicationServiceSupported = (*(__int64 (__fastcall **)(HKEY, HWND__ **))(*(_QWORD *)hKey + 24LL))(
                                      hKey,
                                      &hwndParent);
  v20 = hKey;
  if ( hKey )
  {
    hKey = 0;
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( IsApplicationServiceSupported < 0
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Control.Logger,
      0x62u,
      WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
      IsApplicationServiceSupported);
  }
  v21 = hwndParent;
  v22 = (_AUTH_BROKER_CLIENT_CONTEXT *)LocalAlloc(0x40u, 0x28u);
  v5 = v22;
  if ( !v22 )
  {
    AuthBrokerClientInfoFromRpcThread = -2147024882;
LABEL_49:
    FreeAuthBrokerClientContext(v5);
    goto LABEL_95;
  }
  v22->refCount = 1;
  v22->flags = v9;
  v22->parentWindow = v21;
  if ( v10 )
  {
    AuthBrokerClientInfoFromRpcThread = SHStrDupW(v10, &v22->dialogTitle);
    if ( AuthBrokerClientInfoFromRpcThread < 0 )
      goto LABEL_49;
  }
  AuthBrokerClientInfoFromRpcThread = GetAuthBrokerClientInfoFromRpcThread(
                                        &v5->processId,
                                        &v5->threadId,
                                        &v5->tokenHandle);
  if ( AuthBrokerClientInfoFromRpcThread < 0 )
    goto LABEL_49;
  AuthBrokerClientInfoFromRpcThread = 0;
  v2 = brokerFlags;
LABEL_51:
  if ( (v5->flags & 2) != 0 )
    goto LABEL_90;
  tokenHandle = v5->tokenHandle;
  v24 = HasAppContainerNetworkCapability(tokenHandle);
  if ( (v2 & 0x100000) != 0 )
  {
    if ( v24 )
    {
      for ( i = 0; i < 3; ++i )
      {
        if ( !HasAppContainerCapability(tokenHandle, AuthClientCorporateNetworkExtraCapabilities[i]) )
        {
          v2 = brokerFlags;
          goto LABEL_63;
        }
      }
      v2 = brokerFlags;
      goto LABEL_90;
    }
LABEL_63:
    if ( GetAuthHostRegDWORDValue(L"EnableTestEnterprise") )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_101;
      if ( (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0 || WPP_GLOBAL_Control[1].Control.Level < 5u )
        goto $Exit_0;
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x63u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
LABEL_90:
      v26 = WPP_GLOBAL_Control;
$Exit_0:
      if ( v26 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (v26[1].ReserveSpace[28] & 0x10) != 0
        && v26[1].Control.Level >= 5u )
      {
        WPP_SF_qD(v26[1].Control.Logger, v6, v7, v5, v2);
      }
      goto LABEL_101;
    }
    AuthBrokerClientInfoFromRpcThread = -2147024891;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      v28 = 100;
LABEL_77:
      WPP_SF_(v27[1].Control.Logger, v28, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( v24 )
      goto LABEL_90;
    AuthBrokerClientInfoFromRpcThread = -2147024891;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      v28 = 101;
      goto LABEL_77;
    }
  }
  if ( v5 )
  {
    if ( v27 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v27[1].ReserveSpace[28] & 0x10) != 0
      && v27[1].Control.Level >= 5u )
    {
      WPP_SF_qd(v27[1].Control.Logger, 0x5Fu, v7, v5, v5->refCount);
    }
    if ( _InterlockedExchangeAdd(&v5->refCount, 0xFFFFFFFF) == 1 )
    {
      dialogTitle = v5->dialogTitle;
      if ( dialogTitle )
        CoTaskMemFree(dialogTitle);
      v30 = v5->tokenHandle;
      if ( v30 )
        CloseHandle(v30);
      LocalFree(v5);
      goto LABEL_96;
    }
LABEL_95:
    v2 = brokerFlags;
LABEL_96:
    v27 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( v27 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (v27[1].ReserveSpace[28] & 0x10) != 0
    && v27[1].Control.Level >= 2u )
  {
    WPP_SF_dD(v27[1].Control.Logger, v6, v7, AuthBrokerClientInfoFromRpcThread, v2);
  }
LABEL_101:
  *clientContext = v5;
  return (unsigned int)AuthBrokerClientInfoFromRpcThread;
}

```

## disassembly

```asm
0x180002b20  mov     [rsp-40h+arg_0], brokerFlags
0x180002b24  push    rbp
0x180002b25  push    rbx
0x180002b26  push    rsi
0x180002b27  push    rdi
0x180002b28  push    r12
0x180002b2a  push    r13
0x180002b2c  push    r14
0x180002b2e  push    r15
0x180002b30  mov     rbp, rsp
0x180002b33  sub     rsp, 48h
0x180002b37  mov     r15d, brokerFlags
0x180002b3a  mov     r13, clientContext
0x180002b3d  mov     brokerFlags, cs:_clientContextTlsIndex; dwTlsIndex
0x180002b43  cmp     brokerFlags, 0FFFFFFFFh
0x180002b46  jz      short loc_180002B6E
0x180002b48  call    cs:__imp_TlsGetValue
0x180002b4e  mov     rbx, rax
0x180002b51  test    rax, rax
0x180002b54  jz      short loc_180002B6E
0x180002b56  mov     rcx, rax; clientContext
0x180002b59  call    ?AddRefAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; AddRefAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x180002b5e  xor     esi, esi
0x180002b60  lea     r14, WPP_GLOBAL_Control
0x180002b67  mov     edi, esi
0x180002b69  jmp     loc_180002E86
0x180002b6e  xor     esi, esi
0x180002b70  mov     dword ptr [rbp+cbData], 4
0x180002b77  lea     rax, [rbp+hKey]
0x180002b7b  mov     [rbp+hwndParent], rsi
0x180002b7f  mov     r9d, 20019h; samDesired
0x180002b85  mov     dword ptr [rbp+Data], esi
0x180002b88  xor     r8d, r8d; ulOptions
0x180002b8b  mov     dword ptr [rbp+Type], esi
0x180002b8e  lea     clientContext, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180002b95  mov     [rbp+hKey], rsi
0x180002b99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002ba0  mov     [rsp+48h+phkResult], rax; phkResult
0x180002ba5  mov     r12d, esi
0x180002ba8  mov     r15d, esi
0x180002bab  call    cs:__imp_RegOpenKeyExW
0x180002bb1  test    eax, eax
0x180002bb3  jnz     short loc_180002BF2
0x180002bb5  mov     rcx, [rbp+hKey]; hKey
0x180002bb9  lea     rax, [rbp+cbData]
0x180002bbd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180002bc2  lea     r9, [rbp+Type]; lpType
0x180002bc6  lea     rax, [rbp+Data]
0x180002bca  xor     r8d, r8d; lpReserved
0x180002bcd  lea     clientContext, aEnabletestsyst; "EnableTestSystemUI"
0x180002bd4  mov     [rsp+48h+phkResult], rax; lpData
0x180002bd9  call    cs:__imp_RegQueryValueExW
0x180002bdf  test    eax, eax
0x180002be1  jnz     short loc_180002BEF
0x180002be3  cmp     dword ptr [rbp+Type], 4
0x180002be7  jnz     short loc_180002BEF
0x180002be9  cmp     dword ptr [rbp+cbData], 4
0x180002bed  jz      short loc_180002BF2
0x180002bef  mov     dword ptr [rbp+Data], esi
0x180002bf2  mov     rcx, [rbp+hKey]; hKey
0x180002bf6  test    rcx, rcx
0x180002bf9  jz      short loc_180002C01
0x180002bfb  call    cs:__imp_RegCloseKey
0x180002c01  lea     r14, WPP_GLOBAL_Control
0x180002c08  cmp     dword ptr [rbp+Data], esi
0x180002c0b  jz      short loc_180002C47
0x180002c0d  mov     r12d, 8
0x180002c13  lea     r15, aTestSystemUiTi; "Test System UI Title"
0x180002c1a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002c21  cmp     rcx, r14
0x180002c24  jz      short loc_180002C47
0x180002c26  test    byte ptr [rcx+44h], 10h
0x180002c2a  jz      short loc_180002C47
0x180002c2c  cmp     byte ptr [rcx+41h], 5
0x180002c30  jb      short loc_180002C47
0x180002c32  mov     rcx, [rcx+38h]; Logger
0x180002c36  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180002c3d  mov     edx, 61h ; 'a'; id
0x180002c42  call    WPP_SF_
0x180002c47  lea     clientContext, [rbp+Data]; ppInterface
0x180002c4b  mov     [rbp+hwndParent], rsi
0x180002c4f  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180002c56  mov     [rbp+hKey], rsi
0x180002c5a  mov     [rbp+cbData], rsi
0x180002c5e  mov     [rbp+Type], rsi
0x180002c62  mov     [rbp+Data], rsi
0x180002c66  call    cs:__imp_CoGetCallContext
0x180002c6c  mov     ebx, eax
0x180002c6e  test    eax, eax
0x180002c70  js      short loc_180002C9F
0x180002c72  mov     rcx, [rbp+Data]
0x180002c76  lea     r8, [rbp+Type]
0x180002c7a  mov     edx, 1000h
0x180002c7f  mov     rax, [rcx]
0x180002c82  mov     rax, [rax+18h]
0x180002c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8b  mov     ebx, eax
0x180002c8d  test    eax, eax
0x180002c8f  jns     short loc_180002CB0
0x180002c91  lea     rcx, [rbp+Data]; this
0x180002c95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180002c9a  jmp     loc_180002D39
0x180002c9f  cmp     eax, 80010117h
0x180002ca4  jnz     short loc_180002D08
0x180002ca6  call    cs:__imp_GetCurrentProcess
0x180002cac  mov     [rbp+Type], rax
0x180002cb0  mov     rcx, [rbp+Data]
0x180002cb4  test    rcx, rcx
0x180002cb7  jz      short loc_180002CC9
0x180002cb9  mov     [rbp+Data], rsi
0x180002cbd  mov     rax, [rcx]
0x180002cc0  mov     rax, [rax+10h]
0x180002cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc9  mov     rcx, [rbp+Type]; Process
0x180002ccd  call    cs:__imp_GetProcessId
0x180002cd3  mov     brokerFlags, eax
0x180002cd5  lea     clientContext, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180002cdc  mov     edi, eax
0x180002cde  call    cs:__imp_CoreIsApplicationServiceSupported
0x180002ce4  mov     ebx, eax
0x180002ce6  test    eax, eax
0x180002ce8  js      short loc_180002D39
0x180002cea  lea     r9, [rbp+cbData]
0x180002cee  mov     brokerFlags, edi
0x180002cf0  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180002cf7  lea     clientContext, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180002cfe  call    cs:__imp_CoreQueryApplicationService
0x180002d04  mov     ebx, eax
0x180002d06  jmp     short loc_180002D39
0x180002d08  mov     rcx, [rbp+40h]; callerReturnAddress
0x180002d0c  lea     r8, fileName; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180002d13  mov     r9d, eax; hr
0x180002d16  mov     edx, 58h ; 'X'; lineNumber
0x180002d1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d20  mov     rcx, [rbp+Data]
0x180002d24  test    rcx, rcx
0x180002d27  jz      short loc_180002D39
0x180002d29  mov     [rbp+Data], rsi
0x180002d2d  mov     rax, [rcx]
0x180002d30  mov     rax, [rax+10h]
0x180002d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d39  mov     rcx, [rbp+Type]; hObject
0x180002d3d  mov     [rbp+Type], rsi
0x180002d41  lea     rax, [rcx-1]
0x180002d45  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002d49  ja      short loc_180002D51
0x180002d4b  call    cs:__imp_CloseHandle
0x180002d51  test    ebx, ebx
0x180002d53  js      short loc_180002DCE
0x180002d55  lea     rcx, [rbp+Data]; lpdwTID
0x180002d59  mov     dword ptr [rbp+Data], esi
0x180002d5c  call    cs:__imp_CoGetCallerTID
0x180002d62  mov     ebx, eax
0x180002d64  test    eax, eax
0x180002d66  js      short loc_180002DCE
0x180002d68  mov     eax, dword ptr [rbp+Data]
0x180002d6b  dec     eax
0x180002d6d  cmp     eax, 0FFFFFFFDh
0x180002d70  ja      short loc_180002DC9
0x180002d72  mov     rdi, [rbp+cbData]
0x180002d76  lea     rcx, [rbp+Type]; this
0x180002d7a  mov     [rbp+Type], rsi
0x180002d7e  mov     rax, [rdi]
0x180002d81  mov     rbx, [rax+40h]
0x180002d85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180002d8a  mov     edx, dword ptr [rbp+Data]
0x180002d8d  lea     r8, [rbp+Type]
0x180002d91  mov     rcx, rdi
0x180002d94  mov     rax, rbx
0x180002d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9c  mov     ebx, eax
0x180002d9e  test    eax, eax
0x180002da0  js      short loc_180002DBE
0x180002da2  mov     rcx, [rbp+Type]
0x180002da6  lea     r8, [rbp+hKey]
0x180002daa  lea     clientContext, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x180002db1  mov     rax, [rcx]
0x180002db4  mov     rax, [rax]
0x180002db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbc  mov     ebx, eax
0x180002dbe  lea     rcx, [rbp+Type]; this
0x180002dc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180002dc7  jmp     short loc_180002DCE
0x180002dc9  mov     ebx, 80070490h
0x180002dce  mov     rcx, [rbp+cbData]
0x180002dd2  test    rcx, rcx
0x180002dd5  jz      short loc_180002DE7
0x180002dd7  mov     [rbp+cbData], rsi
0x180002ddb  mov     rax, [rcx]
0x180002dde  mov     rax, [rax+10h]
0x180002de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de7  test    ebx, ebx
0x180002de9  js      short loc_180002E01
0x180002deb  mov     rcx, [rbp+hKey]
0x180002def  lea     clientContext, [rbp+hwndParent]
0x180002df3  mov     rax, [rcx]
0x180002df6  mov     rax, [rax+18h]
0x180002dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dff  mov     ebx, eax
0x180002e01  mov     rcx, [rbp+hKey]
0x180002e05  test    rcx, rcx
0x180002e08  jz      short loc_180002E1A
0x180002e0a  mov     [rbp+hKey], rsi
0x180002e0e  mov     rax, [rcx]
0x180002e11  mov     rax, [rax+10h]
0x180002e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1a  test    ebx, ebx
0x180002e1c  jns     short loc_180002E4E
0x180002e1e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002e25  cmp     rcx, r14
0x180002e28  jz      short loc_180002E4E
0x180002e2a  test    byte ptr [rcx+44h], 10h
0x180002e2e  jz      short loc_180002E4E
0x180002e30  cmp     byte ptr [rcx+41h], 5
0x180002e34  jb      short loc_180002E4E
0x180002e36  mov     rcx, [rcx+38h]; Logger
0x180002e3a  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180002e41  mov     edx, 62h ; 'b'; id
0x180002e46  mov     r9d, ebx; _a1
0x180002e49  call    WPP_SF_d
0x180002e4e  mov     rdi, [rbp+hwndParent]
0x180002e52  mov     edx, 28h ; '('; uBytes
0x180002e57  mov     brokerFlags, 40h ; '@'; uFlags
0x180002e5c  call    cs:__imp_LocalAlloc
0x180002e62  mov     rbx, rax
0x180002e65  test    rax, rax
0x180002e68  jnz     short loc_180002ED6
0x180002e6a  mov     edi, 8007000Eh
0x180002e6f  mov     rcx, rbx; clientContext
0x180002e72  call    ?FreeAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; FreeAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x180002e77  mov     rbx, rsi
0x180002e7a  test    edi, edi
0x180002e7c  js      loc_180003070
0x180002e82  mov     r15d, [rbp+arg_0]
0x180002e86  test    byte ptr [rbx+4], 2
0x180002e8a  jnz     loc_180003045
0x180002e90  mov     r12, [rbx+20h]
0x180002e94  mov     rcx, r12; tokenHandle
0x180002e97  call    _HasAppContainerNetworkCapability
0x180002e9c  bt      r15d, 14h
0x180002ea1  jnb     loc_180002F98
0x180002ea7  test    eax, eax
0x180002ea9  jz      short loc_180002F26
0x180002eab  mov     r15d, esi
0x180002eae  lea     rax, _AuthClientCorporateNetworkExtraCapabilities
0x180002eb5  cmp     r15d, 3
0x180002eb9  jnb     loc_180003041
0x180002ebf  mov     edx, r15d
0x180002ec2  mov     rcx, r12; tokenHandle
0x180002ec5  mov     edx, [rax+clientContext*4]; capabilityToCheck
0x180002ec8  call    _HasAppContainerCapability
0x180002ecd  test    eax, eax
0x180002ecf  jz      short loc_180002F22
0x180002ed1  inc     r15d
0x180002ed4  jmp     short loc_180002EAE
0x180002ed6  mov     dword ptr [rax], 1
0x180002edc  mov     [rax+4], r12d
0x180002ee0  mov     [rax+8], rdi
0x180002ee4  test    r15, r15
0x180002ee7  jz      short loc_180002F00
0x180002ee9  lea     clientContext, [rax+10h]; ppwsz
0x180002eed  mov     rcx, r15; psz
0x180002ef0  call    cs:__imp_SHStrDupW
0x180002ef6  mov     edi, eax
0x180002ef8  test    eax, eax
0x180002efa  js      loc_180002E6F
0x180002f00  lea     r8, [rbx+20h]; clientTokenHandle
0x180002f04  lea     clientContext, [rbx+1Ch]; clientThreadId
0x180002f08  lea     rcx, [rbx+18h]; clientProcessId
0x180002f0c  call    _GetAuthBrokerClientInfoFromRpcThread
0x180002f11  mov     edi, eax
0x180002f13  test    eax, eax
0x180002f15  js      loc_180002E6F
0x180002f1b  mov     edi, esi
0x180002f1d  jmp     loc_180002E82
0x180002f22  mov     r15d, [rbp+arg_0]
0x180002f26  lea     rcx, aEnabletestente; "EnableTestEnterprise"
0x180002f2d  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180002f32  test    eax, eax
0x180002f34  jz      short loc_180002F74
0x180002f36  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002f3d  cmp     rcx, r14
0x180002f40  jz      loc_1800030A0
0x180002f46  test    byte ptr [rcx+44h], 10h
0x180002f4a  jz      $Exit_0
0x180002f50  cmp     byte ptr [rcx+41h], 5
0x180002f54  jb      $Exit_0
0x180002f5a  mov     rcx, [rcx+38h]; Logger
0x180002f5e  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180002f65  mov     edx, 63h ; 'c'; id
0x180002f6a  call    WPP_SF_
0x180002f6f  jmp     loc_180003045
0x180002f74  mov     edi, 80070005h
0x180002f79  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002f80  cmp     rcx, r14
0x180002f83  jz      short loc_180002FD9
0x180002f85  test    byte ptr [rcx+44h], 10h
0x180002f89  jz      short loc_180002FD9
0x180002f8b  cmp     byte ptr [rcx+41h], 2
0x180002f8f  jb      short loc_180002FD9
  ... truncated ...
```
