# CtapUtilsGetCallerProcessInfo(void *,void * const,wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)> &)

- ea: `0x18001e848`
- end: `0x18001ed32`
- name: `?CtapUtilsGetCallerProcessInfo@@YAJPEAXQEAXAEAV?$unique_struct@UWEBAUTHN_CALLER_INFO@@P6AXPEAU1@@Z$1?FreeCallerInfo@@YAX0@ZP6AX0@Z$1?InitCallerInfo@@YAX0@Z@wil@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001dfb8`
- `0x1800da85c`
- `0x1800dab70`

## callees

- `0x18000c050`
- `0x180017a88`
- `0x18001df88`
- `0x18001e848`
- `0x180036da4`
- `0x180036dc8`
- `0x18003737c`
- `0x180037f6c`
- `0x18003ac98`
- `0x18003acb8`
- `0x180043a18`
- `0x180043ab4`
- `0x180048b70`
- `0x18007d7c4`
- `0x1800d8a34`
- `0x1800d8ab0`
- `0x1800d8b24`
- `0x1800d8b58`
- `0x18011d09c`
- `0x18011d394`
- `0x18011d56c`
- `0x18011dfa0`
- `0x18011e740`
- `0x180120854`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8cc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e922`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e922`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001e969`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001e969`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ea46`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ea46`
- `api-ms-win-shell-associations-l1-1-3!SHAssocEnumHandlersForProtocolByApplication` at `0x18001e9af`
- `api-ms-win-shell-associations-l1-1-3!SHAssocEnumHandlersForProtocolByApplication` at `0x18001e9af`
- `RPCRT4!RpcImpersonateClient` at `0x18001e8fb`
- `RPCRT4!RpcImpersonateClient` at `0x18001e8fb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001e8dd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001e8dd`
- `WINTRUST!WTGetSignatureInfo` at `0x18001ea92`
- `WINTRUST!WTGetSignatureInfo` at `0x18001ea92`

## string_xrefs

- `0x18001e97a`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18001eaa8`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18001eb75`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18001ec8d`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18001ecb2`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18001ecd4`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CtapUtilsGetCallerProcessInfo(void *a1, __int64 a2, struct WEBAUTHN_CALLER_INFO *a3)
{
  DWORD CurrentProcessId; // eax
  __int64 v6; // rdx
  HANDLE v7; // rdi
  const char *v8; // r9
  const WCHAR *v9; // rbx
  const char *v10; // r9
  unsigned int LastError; // ebx
  void *v12; // rdi
  unsigned int (__fastcall *v13)(void *, __int64, __int64 *, int *); // rsi
  __int64 v14; // rcx
  __int64 v15; // rsi
  int (__fastcall *v16)(__int64, LPCWSTR *); // rdi
  int v17; // eax
  char v18; // cl
  unsigned int CallerPackageDetails; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  unsigned int Pid; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR lpString1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwSize; // [rsp+5Ch] [rbp-A4h] BYREF
  LPWSTR lpExeName; // [rsp+60h] [rbp-A0h] BYREF
  void *enumHandlers; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v30; // [rsp+70h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  char v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v36[32]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v37[5]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v38[4]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v39; // [rsp+124h] [rbp+24h]
  _BYTE v40[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v41[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v42[32]; // [rsp+188h] [rbp+88h] BYREF
  int v43; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v44[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v45; // [rsp+1B4h] [rbp+B4h]
  _BYTE v46[240]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  Binding = a1;
  v26 = 0;
  Pid = 0;
  v30 = 0;
  dwSize = 1023;
  wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>((struct WEBAUTHN_CALLER_INFO *)v38);
  v32[0] = &v26;
  v32[1] = &Binding;
  v33 = 1;
  if ( Binding == (RPC_BINDING_HANDLE)1 )
  {
    CurrentProcessId = GetCurrentProcessId();
    Pid = CurrentProcessId;
    goto LABEL_8;
  }
  if ( I_RpcBindingInqLocalClientPID(Binding, &Pid) || !Pid )
  {
    v6 = 509;
    goto LABEL_33;
  }
  if ( RpcImpersonateClient(Binding) )
  {
    v6 = 512;
LABEL_33:
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)0x8000FFFFLL,
      v21);
    goto LABEL_34;
  }
  v26 = 1;
  CurrentProcessId = Pid;
LABEL_8:
  v7 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v30 = v7;
  if ( !v7 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x209,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
                  v8);
    goto LABEL_34;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpExeName,
    0,
    dwSize + 1);
  v9 = lpExeName;
  if ( !lpExeName )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)0x8007000ELL,
      v21);
    goto LABEL_30;
  }
  if ( !QueryFullProcessImageNameW(v7, 0, lpExeName, &dwSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x213,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
                  v10);
LABEL_30:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpExeName);
LABEL_34:
    wil::details::lambda_call__CtapUtilsGetCallerProcessInfo_::_2_::_lambda_1___::reset(v32);
    wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::~unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>((WEBAUTHN_CALLER_INFO *)v38);
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
    return LastError;
  }
  v25 = 0;
  enumHandlers = 0;
  if ( SHAssocEnumHandlersForProtocolByApplication(L"https", &GUID_973810ae_9599_4b88_9e4d_6ee98c9552da, &enumHandlers) >= 0 )
  {
    v23 = 0;
    while ( 1 )
    {
      v12 = enumHandlers;
      v13 = *(unsigned int (__fastcall **)(void *, __int64, __int64 *, int *))(*(_QWORD *)enumHandlers + 24LL);
      v14 = v25;
      v25 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v13(v12, 1, &v25, &v23) || v23 != 1 )
        break;
      lpString1 = 0;
      v15 = v25;
      v16 = *(int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v25 + 24LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString1,
        0);
      if ( v16(v15, &lpString1) >= 0 && !lstrcmpiW(lpString1, v9) )
      {
        v38[1] = 1;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
        break;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
    }
  }
  v17 = WTGetSignatureInfo(v9, -1, 4099, v44);
  LastError = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)v17,
      (int)&v43);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&enumHandlers);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v25);
    goto LABEL_30;
  }
  v18 = v38[0];
  if ( (unsigned int)(v45 - 5) <= 1 )
    v18 = 1;
  v38[0] = v18;
  v39 = Pid;
  wil::details::lambda_call__CtapUtilsGetCallerProcessInfo_::_2_::_lambda_1___::reset(v32);
  LODWORD(lpString1) = 0;
  std::wstring::wstring(v37);
  std::wstring::wstring(v36);
  std::wstring::wstring(v35);
  std::wstring::wstring(v34);
  v23 = 0;
  CallerPackageDetails = GetCallerPackageDetails(a2, &v23, &lpString1, v37, (__int64)v36, (__int64)v35, (__int64)v34);
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0x245,
    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
    (const char *)CallerPackageDetails,
    1,
    0x80070490);
  if ( v23 )
  {
    v38[2] = 1;
    std::wstring::operator=(v40, v36);
    std::wstring::operator=(v41, v35);
    std::wstring::operator=(v42, v34);
  }
  WEBAUTHN_CALLER_INFO::WEBAUTHN_CALLER_INFO((WEBAUTHN_CALLER_INFO *)v46, (const struct WEBAUTHN_CALLER_INFO *)v38);
  InitCallerInfo((struct WEBAUTHN_CALLER_INFO *)v38);
  wil::last_error_context::last_error_context((wil::last_error_context *)&lpString1);
  FreeCallerInfo(a3);
  wil::last_error_context::~last_error_context((wil::last_error_context *)&lpString1);
  WEBAUTHN_CALLER_INFO::operator=(a3, v46);
  WEBAUTHN_CALLER_INFO::~WEBAUTHN_CALLER_INFO((WEBAUTHN_CALLER_INFO *)v46);
  std::wstring::_Tidy_deallocate(v34);
  std::wstring::_Tidy_deallocate(v35);
  std::wstring::_Tidy_deallocate(v36);
  std::wstring::_Tidy_deallocate(v37);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&enumHandlers);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v25);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpExeName);
  wil::details::lambda_call__CtapUtilsGetCallerProcessInfo_::_2_::_lambda_1___::reset(v32);
  wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::~unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&void FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&void InitCallerInfo(WEBAUTHN_CALLER_INFO *)>((WEBAUTHN_CALLER_INFO *)v38);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
  return 0;
}

```

## disassembly

```asm
0x18001e848  mov     [rsp-8+arg_18], rbx
0x18001e84d  push    rbp
0x18001e84e  push    rsi
0x18001e84f  push    rdi
0x18001e850  push    r12
0x18001e852  push    r13
0x18001e854  push    r14
0x18001e856  push    r15
0x18001e858  lea     rbp, [rsp-210h]
0x18001e860  sub     rsp, 310h
0x18001e867  mov     rax, cs:__security_cookie
0x18001e86e  xor     rax, rsp
0x18001e871  mov     [rbp+240h+var_40], rax
0x18001e878  mov     r14, r8
0x18001e87b  mov     r15, rdx
0x18001e87e  mov     [rsp+340h+Binding], rcx
0x18001e883  xor     r12d, r12d
0x18001e886  mov     [rsp+340h+var_2E8], r12d
0x18001e88b  mov     [rsp+340h+Pid], r12d
0x18001e890  mov     [rsp+340h+var_2D0], r12
0x18001e895  mov     [rsp+340h+dwSize], 3FFh
0x18001e89d  lea     rcx, [rbp+240h+var_220]; struct WEBAUTHN_CALLER_INFO *
0x18001e8a1  call    ??0?$unique_struct@UWEBAUTHN_CALLER_INFO@@P6AXPEAU1@@Z$1?FreeCallerInfo@@YAX0@ZP6AX0@Z$1?InitCallerInfo@@YAX0@Z@wil@@QEAA@XZ; wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>(void)
0x18001e8a6  nop
0x18001e8a7  lea     rax, [rsp+340h+var_2E8]
0x18001e8ac  mov     [rbp+240h+var_2C0], rax
0x18001e8b0  lea     rax, [rsp+340h+Binding]
0x18001e8b5  mov     [rbp+240h+var_2B8], rax
0x18001e8b9  lea     r13d, [r12+1]
0x18001e8be  mov     [rbp+240h+var_2B0], r13b
0x18001e8c2  mov     rcx, [rsp+340h+Binding]; Binding
0x18001e8c7  cmp     rcx, r13
0x18001e8ca  jnz     short loc_18001E8D8
0x18001e8cc  call    cs:__imp_GetCurrentProcessId
0x18001e8d2  mov     [rsp+340h+Pid], eax
0x18001e8d6  jmp     short loc_18001E918
0x18001e8d8  lea     rdx, [rsp+340h+Pid]; Pid
0x18001e8dd  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001e8e3  test    eax, eax
0x18001e8e5  jnz     loc_18001ECC7
0x18001e8eb  cmp     [rsp+340h+Pid], r12d
0x18001e8f0  jz      loc_18001ECC7
0x18001e8f6  mov     rcx, [rsp+340h+Binding]; BindingHandle
0x18001e8fb  call    cs:__imp_RpcImpersonateClient
0x18001e901  test    eax, eax
0x18001e903  jz      short loc_18001E90F
0x18001e905  mov     edx, 200h
0x18001e90a  jmp     loc_18001ECCC
0x18001e90f  mov     [rsp+340h+var_2E8], r13d
0x18001e914  mov     eax, [rsp+340h+Pid]
0x18001e918  mov     r8d, eax; dwProcessId
0x18001e91b  xor     edx, edx; bInheritHandle
0x18001e91d  mov     ecx, 1000h; dwDesiredAccess
0x18001e922  call    cs:__imp_OpenProcess
0x18001e928  mov     rdi, rax
0x18001e92b  mov     [rsp+340h+var_2D0], rax
0x18001e930  test    rax, rax
0x18001e933  jz      loc_18001ECAB
0x18001e939  mov     r8d, [rsp+340h+dwSize]
0x18001e93e  inc     r8d
0x18001e941  xor     edx, edx
0x18001e943  lea     rcx, [rsp+340h+lpExeName]
0x18001e948  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001e94d  nop
0x18001e94e  mov     rbx, [rsp+340h+lpExeName]
0x18001e953  test    rbx, rbx
0x18001e956  jz      loc_18001EC7E
0x18001e95c  lea     r9, [rsp+340h+dwSize]; lpdwSize
0x18001e961  mov     r8, rbx; lpExeName
0x18001e964  xor     edx, edx; dwFlags
0x18001e966  mov     rcx, rdi; hProcess
0x18001e969  call    cs:__imp_QueryFullProcessImageNameW
0x18001e96f  test    eax, eax
0x18001e971  jnz     short loc_18001E992
0x18001e973  mov     rcx, [rbp+248h]; this
0x18001e97a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001e981  mov     edx, 213h; void *
0x18001e986  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e98b  mov     ebx, eax
0x18001e98d  jmp     loc_18001EC9F
0x18001e992  mov     [rsp+340h+var_2F0], r12
0x18001e997  mov     [rsp+340h+enumHandlers], r12
0x18001e99c  lea     r8, [rsp+340h+enumHandlers]; enumHandlers
0x18001e9a1  lea     rdx, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da; riid
0x18001e9a8  lea     rcx, protocol; "https"
0x18001e9af  call    cs:__imp_SHAssocEnumHandlersForProtocolByApplication
0x18001e9b5  test    eax, eax
0x18001e9b7  js      loc_18001EA6D
0x18001e9bd  mov     [rsp+340h+var_2FC], r12d
0x18001e9c2  mov     rdi, [rsp+340h+enumHandlers]
0x18001e9c7  mov     rax, [rdi]
0x18001e9ca  mov     rsi, [rax+18h]
0x18001e9ce  mov     rcx, [rsp+340h+var_2F0]
0x18001e9d3  mov     [rsp+340h+var_2F0], r12
0x18001e9d8  test    rcx, rcx
0x18001e9db  jz      short loc_18001E9EA
0x18001e9dd  mov     rdx, [rcx]
0x18001e9e0  mov     rax, [rdx+10h]
0x18001e9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e9  nop
0x18001e9ea  lea     r9, [rsp+340h+var_2FC]
0x18001e9ef  lea     r8, [rsp+340h+var_2F0]
0x18001e9f4  mov     edx, r13d
0x18001e9f7  mov     rcx, rdi
0x18001e9fa  mov     rax, rsi
0x18001e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea02  test    eax, eax
0x18001ea04  jnz     short loc_18001EA6D
0x18001ea06  cmp     [rsp+340h+var_2FC], r13d
0x18001ea0b  jnz     short loc_18001EA6D
0x18001ea0d  mov     [rsp+340h+lpString1], r12
0x18001ea12  mov     rsi, [rsp+340h+var_2F0]
0x18001ea17  mov     rax, [rsi]
0x18001ea1a  mov     rdi, [rax+18h]
0x18001ea1e  xor     edx, edx
0x18001ea20  lea     rcx, [rsp+340h+lpString1]
0x18001ea25  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ea2a  lea     rdx, [rsp+340h+lpString1]
0x18001ea2f  mov     rcx, rsi
0x18001ea32  mov     rax, rdi
0x18001ea35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea3a  test    eax, eax
0x18001ea3c  js      short loc_18001EA50
0x18001ea3e  mov     rdx, rbx; lpString2
0x18001ea41  mov     rcx, [rsp+340h+lpString1]; lpString1
0x18001ea46  call    cs:__imp_lstrcmpiW
0x18001ea4c  test    eax, eax
0x18001ea4e  jz      short loc_18001EA5F
0x18001ea50  lea     rcx, [rsp+340h+lpString1]
0x18001ea55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ea5a  jmp     loc_18001E9C2
0x18001ea5f  mov     [rbp+240h+var_21F], r13b
0x18001ea63  lea     rcx, [rsp+340h+lpString1]
0x18001ea68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ea6d  mov     qword ptr [rsp+340h+var_318], r12
0x18001ea72  lea     rax, [rbp+240h+var_198]
0x18001ea79  mov     qword ptr [rsp+340h+var_320], rax; int
0x18001ea7e  lea     r9, [rbp+240h+var_190]
0x18001ea85  mov     r8d, 1003h
0x18001ea8b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ea8f  mov     rcx, rbx
0x18001ea92  call    cs:__imp_WTGetSignatureInfo
0x18001ea98  mov     ebx, eax
0x18001ea9a  test    eax, eax
0x18001ea9c  jns     short loc_18001EAD4
0x18001ea9e  mov     rcx, [rbp+248h]; this
0x18001eaa5  mov     r9d, eax; char *
0x18001eaa8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001eaaf  mov     edx, 231h; void *
0x18001eab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eab9  nop
0x18001eaba  lea     rcx, [rsp+340h+enumHandlers]
0x18001eabf  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001eac4  nop
0x18001eac5  lea     rcx, [rsp+340h+var_2F0]
0x18001eaca  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001eacf  jmp     loc_18001EC9F
0x18001ead4  mov     eax, [rbp+240h+var_18C]
0x18001eada  add     eax, 0FFFFFFFBh
0x18001eadd  movzx   ecx, [rbp+240h+var_220]
0x18001eae1  cmp     eax, r13d
0x18001eae4  cmovbe  ecx, r13d
0x18001eae8  mov     [rbp+240h+var_220], cl
0x18001eaeb  mov     eax, [rsp+340h+Pid]
0x18001eaef  mov     [rbp+240h+var_21C], eax
0x18001eaf2  lea     rcx, [rbp+240h+var_2C0]
0x18001eaf6  call    wil__details__lambda_call__CtapUtilsGetCallerProcessInfo____2____lambda_1_____reset
0x18001eafb  mov     dword ptr [rsp+340h+lpString1], r12d
0x18001eb00  lea     rcx, [rbp+240h+var_248]
0x18001eb04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001eb09  nop
0x18001eb0a  lea     rcx, [rbp+240h+var_268]
0x18001eb0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001eb13  nop
0x18001eb14  lea     rcx, [rbp+240h+var_288]
0x18001eb18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001eb1d  nop
0x18001eb1e  lea     rcx, [rbp+240h+var_2A8]
0x18001eb22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001eb27  nop
0x18001eb28  mov     [rsp+340h+var_2FC], r12d
0x18001eb2d  lea     rax, [rbp+240h+var_2A8]
0x18001eb31  mov     [rsp+340h+var_310], rax
0x18001eb36  lea     rax, [rbp+240h+var_288]
0x18001eb3a  mov     qword ptr [rsp+340h+var_318], rax
0x18001eb3f  lea     rax, [rbp+240h+var_268]
0x18001eb43  mov     qword ptr [rsp+340h+var_320], rax
0x18001eb48  lea     r9, [rbp+240h+var_248]
0x18001eb4c  lea     r8, [rsp+340h+lpString1]
0x18001eb51  lea     rdx, [rsp+340h+var_2FC]
0x18001eb56  mov     rcx, r15
0x18001eb59  call    ?GetCallerPackageDetails@@YAJQEAXAEAH1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@222@Z; GetCallerPackageDetails(void * const,int &,int &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x18001eb5e  mov     rcx, [rbp+248h]; this
0x18001eb65  mov     [rsp+340h+var_318], 80070490h; unsigned int
0x18001eb6d  mov     [rsp+340h+var_320], r13d; int
0x18001eb72  mov     r9d, eax; char *
0x18001eb75  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001eb7c  mov     edx, 245h; void *
0x18001eb81  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18001eb86  cmp     [rsp+340h+var_2FC], r12d
0x18001eb8b  jz      short loc_18001EBBC
0x18001eb8d  mov     [rbp+240h+var_21E], r13b
0x18001eb91  lea     rdx, [rbp+240h+var_268]
0x18001eb95  lea     rcx, [rbp+240h+var_1F8]
0x18001eb99  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001eb9e  lea     rdx, [rbp+240h+var_288]
0x18001eba2  lea     rcx, [rbp+240h+var_1D8]
0x18001eba6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001ebab  lea     rdx, [rbp+240h+var_2A8]
0x18001ebaf  lea     rcx, [rbp+240h+var_1B8]
0x18001ebb6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001ebbb  nop
0x18001ebbc  lea     rdx, [rbp+240h+var_220]; struct WEBAUTHN_CALLER_INFO *
0x18001ebc0  lea     rcx, [rbp+240h+var_130]; this
0x18001ebc7  call    ??0WEBAUTHN_CALLER_INFO@@QEAA@AEBU0@@Z; WEBAUTHN_CALLER_INFO::WEBAUTHN_CALLER_INFO(WEBAUTHN_CALLER_INFO const &)
0x18001ebcc  lea     rcx, [rbp+240h+var_220]; struct WEBAUTHN_CALLER_INFO *
0x18001ebd0  call    ?InitCallerInfo@@YAXPEAUWEBAUTHN_CALLER_INFO@@@Z; InitCallerInfo(WEBAUTHN_CALLER_INFO *)
0x18001ebd5  nop
0x18001ebd6  lea     rcx, [rsp+340h+lpString1]; this
0x18001ebdb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ebe0  mov     rcx, r14; struct WEBAUTHN_CALLER_INFO *
0x18001ebe3  call    ?FreeCallerInfo@@YAXPEAUWEBAUTHN_CALLER_INFO@@@Z; FreeCallerInfo(WEBAUTHN_CALLER_INFO *)
0x18001ebe8  lea     rcx, [rsp+340h+lpString1]; this
0x18001ebed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ebf2  nop
0x18001ebf3  lea     rdx, [rbp+240h+var_130]
0x18001ebfa  mov     rcx, r14
0x18001ebfd  call    ??4WEBAUTHN_CALLER_INFO@@QEAAAEAU0@AEBU0@@Z; WEBAUTHN_CALLER_INFO::operator=(WEBAUTHN_CALLER_INFO const &)
0x18001ec02  nop
0x18001ec03  lea     rcx, [rbp+240h+var_130]; this
0x18001ec0a  call    ??1WEBAUTHN_CALLER_INFO@@QEAA@XZ; WEBAUTHN_CALLER_INFO::~WEBAUTHN_CALLER_INFO(void)
0x18001ec0f  nop
0x18001ec10  lea     rcx, [rbp+240h+var_2A8]
0x18001ec14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec19  nop
0x18001ec1a  lea     rcx, [rbp+240h+var_288]
0x18001ec1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec23  nop
0x18001ec24  lea     rcx, [rbp+240h+var_268]
0x18001ec28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec2d  nop
0x18001ec2e  lea     rcx, [rbp+240h+var_248]
0x18001ec32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec37  nop
0x18001ec38  lea     rcx, [rsp+340h+enumHandlers]
0x18001ec3d  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001ec42  nop
0x18001ec43  lea     rcx, [rsp+340h+var_2F0]
0x18001ec48  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001ec4d  nop
0x18001ec4e  lea     rcx, [rsp+340h+lpExeName]
0x18001ec53  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001ec58  nop
0x18001ec59  lea     rcx, [rbp+240h+var_2C0]
0x18001ec5d  call    wil__details__lambda_call__CtapUtilsGetCallerProcessInfo____2____lambda_1_____reset
0x18001ec62  nop
0x18001ec63  lea     rcx, [rbp+240h+var_220]; this
0x18001ec67  call    ??1?$unique_struct@UWEBAUTHN_CALLER_INFO@@P6AXPEAU1@@Z$1?FreeCallerInfo@@YAX0@ZP6AX0@Z$1?InitCallerInfo@@YAX0@Z@wil@@QEAA@XZ; wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::~unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>(void)
0x18001ec6c  nop
0x18001ec6d  lea     rcx, [rsp+340h+var_2D0]
0x18001ec72  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ec77  xor     eax, eax
0x18001ec79  jmp     loc_18001ED08
0x18001ec7e  mov     rcx, [rbp+248h]; this
0x18001ec85  mov     ebx, 8007000Eh
0x18001ec8a  mov     r9d, ebx; char *
0x18001ec8d  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001ec94  mov     edx, 20Dh; void *
0x18001ec99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec9e  nop
0x18001ec9f  lea     rcx, [rsp+340h+lpExeName]
0x18001eca4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001eca9  jmp     short loc_18001ECE8
0x18001ecab  mov     rcx, [rbp+248h]; this
0x18001ecb2  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001ecb9  mov     edx, 209h; void *
0x18001ecbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ecc3  mov     ebx, eax
0x18001ecc5  jmp     short loc_18001ECE8
0x18001ecc7  mov     edx, 1FDh; void *
0x18001eccc  mov     ebx, 8000FFFFh
0x18001ecd1  mov     r9d, ebx; char *
0x18001ecd4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18001ecdb  mov     rcx, [rbp+248h]; this
0x18001ece2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ece7  nop
0x18001ece8  lea     rcx, [rbp+240h+var_2C0]
0x18001ecec  call    wil__details__lambda_call__CtapUtilsGetCallerProcessInfo____2____lambda_1_____reset
0x18001ecf1  nop
0x18001ecf2  lea     rcx, [rbp+240h+var_220]; this
0x18001ecf6  call    ??1?$unique_struct@UWEBAUTHN_CALLER_INFO@@P6AXPEAU1@@Z$1?FreeCallerInfo@@YAX0@ZP6AX0@Z$1?InitCallerInfo@@YAX0@Z@wil@@QEAA@XZ; wil::unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>::~unique_struct<WEBAUTHN_CALLER_INFO,void (*)(WEBAUTHN_CALLER_INFO *),&FreeCallerInfo(WEBAUTHN_CALLER_INFO *),void (*)(WEBAUTHN_CALLER_INFO *),&InitCallerInfo(WEBAUTHN_CALLER_INFO *)>(void)
0x18001ecfb  nop
0x18001ecfc  lea     rcx, [rsp+340h+var_2D0]
0x18001ed01  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ed06  mov     eax, ebx
0x18001ed08  mov     rcx, [rbp+240h+var_40]
0x18001ed0f  xor     rcx, rsp; StackCookie
0x18001ed12  call    __security_check_cookie
0x18001ed17  mov     rbx, [rsp+340h+arg_18]
0x18001ed1f  add     rsp, 310h
  ... truncated ...
```
