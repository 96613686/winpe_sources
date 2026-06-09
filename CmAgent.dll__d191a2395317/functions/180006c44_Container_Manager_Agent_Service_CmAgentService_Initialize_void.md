# Container::Manager::Agent::Service::CmAgentService::Initialize(void)

- ea: `0x180006c44`
- end: `0x180006fac`
- name: `?Initialize@CmAgentService@Service@Agent@Manager@Container@@QEAAJXZ`
- size: `872`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Service::CmAgentService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009a60`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180006c44`
- `0x180007a4c`
- `0x180007b2c`
- `0x180007b4c`
- `0x180009518`
- `0x1800095f8`
- `0x18000970c`
- `0x18000a59c`
- `0x18003c010`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqEpW` at `0x180006d7a`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180006d7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f38`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180006e6f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180006f2a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180006e6f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180006f2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006edb`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006c94`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006c94`

## string_xrefs

- `0x180006c8d`: `cmagent`
- `0x180006e2c`: `cmagent`
- `0x180006cac`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180006cf3`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180006d4a`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180006d91`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180006dc7`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180006e4e`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Service::CmAgentService::Initialize(
        Container::Manager::Agent::Service::CmAgentService *this)
{
  Container::Manager::Agent::Service::CmAgentService *v1; // rcx
  SERVICE_STATUS_HANDLE v2; // rdi
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  RPC_WSTR v7; // rcx
  bool v8; // zf
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  HANDLE v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v18; // rdi
  DWORD LastError; // esi
  unsigned int v20; // r8d
  const char *v21; // r9
  HANDLE v22; // rsi
  HANDLE v23; // rdi
  DWORD v24; // ebx
  unsigned int v25; // [rsp+20h] [rbp-40h]
  RPC_WSTR Endpoint[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v27[8]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE WaitHandle; // [rsp+80h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+28h] BYREF

  WaitHandle = this;
  AcquireSRWLockExclusive(&SRWLock);
  Container::Manager::Agent::Service::CmAgentService::Reset(v1);
  ReleaseSRWLockExclusive(&SRWLock);
  v2 = RegisterServiceCtrlHandlerExW(L"cmagent", anonymous_namespace_::ServiceHandlerCallback, 0);
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
             v3);
  Endpoint[0] = v27;
  Endpoint[1] = v27;
  v27[0] = 0;
  v5 = Csl::GuidToString(qword_18003F890, Endpoint);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
      (const char *)(unsigned int)v5,
      v25);
LABEL_5:
    v7 = Endpoint[0];
    v8 = Endpoint[0] == v27;
LABEL_6:
    if ( !v8 )
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return v6;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           Endpoint,
                           L":parent",
                           7) )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
      (const char *)0x8007000ELL,
      v25);
    v7 = Endpoint[0];
    v8 = Endpoint[0] == v27;
    goto LABEL_6;
  }
  v9 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_hvsocket", 0xAu, Endpoint[0], 0);
  if ( v9 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x66,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
           (const char *)v9,
           v25);
    goto LABEL_5;
  }
  hObject = 0;
  v10 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&hObject);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
      (const char *)(unsigned int)v10,
      v25);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
    goto LABEL_5;
  }
  WaitHandle = 0;
  v13 = hObject;
  v14 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)()))(qword_18004B198 + 192))(
          &WaitHandle,
          L"cmagent",
          hObject,
          anonymous_namespace_::ServiceStopCallback);
  if ( v14 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
            (const char *)v14,
            0);
    if ( (char *)WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      UnregisterWait(WaitHandle);
    if ( v13 && !CloseHandle(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    if ( Endpoint[0] != v27 )
      operator delete(Endpoint[0], (const struct std::nothrow_t *)&std::nothrow);
    return v15;
  }
  else
  {
    hServiceStatus = v2;
    v18 = hEvent;
    if ( hEvent )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    hEvent = v13;
    v22 = WaitHandle;
    v23 = ::WaitHandle;
    if ( (char *)::WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v24 = GetLastError();
      UnregisterWait(v23);
      SetLastError(v24);
    }
    ::WaitHandle = v22;
    WaitHandle = 0;
    if ( Endpoint[0] != v27 )
      operator delete(Endpoint[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
}

```

## disassembly

```asm
0x180006c44  mov     [rsp-18h+arg_10], rbx
0x180006c49  mov     [rsp-18h+WaitHandle], rcx
0x180006c4e  push    rbp
0x180006c4f  push    rsi
0x180006c50  push    rdi
0x180006c51  mov     rbp, rsp
0x180006c54  sub     rsp, 60h
0x180006c58  lea     rcx, SRWLock; SRWLock
0x180006c5f  call    cs:__imp_AcquireSRWLockExclusive
0x180006c66  nop     dword ptr [rax+rax+00h]
0x180006c6b  call    ?Reset@CmAgentService@Service@Agent@Manager@Container@@AEAAXXZ; Container::Manager::Agent::Service::CmAgentService::Reset(void)
0x180006c70  lea     rcx, SRWLock; SRWLock
0x180006c77  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c7e  nop     dword ptr [rax+rax+00h]
0x180006c83  xor     r8d, r8d; lpContext
0x180006c86  lea     rdx, _anonymous_namespace___ServiceHandlerCallback; lpHandlerProc
0x180006c8d  lea     rcx, ServiceName; "cmagent"
0x180006c94  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180006c9b  nop     dword ptr [rax+rax+00h]
0x180006ca0  mov     rdi, rax
0x180006ca3  test    rax, rax
0x180006ca6  jnz     short loc_180006CC0
0x180006ca8  mov     rcx, [rbp+18h]; this
0x180006cac  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006cb3  lea     edx, [rax+5Ah]; void *
0x180006cb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006cbb  jmp     loc_180006F6E
0x180006cc0  lea     rax, [rbp+var_10]
0x180006cc4  mov     [rbp+Endpoint], rax
0x180006cc8  lea     rax, [rbp+var_10]
0x180006ccc  mov     [rbp+var_18], rax
0x180006cd0  xor     eax, eax
0x180006cd2  mov     [rbp+var_10], ax
0x180006cd6  lea     rdx, [rbp+Endpoint]
0x180006cda  lea     rcx, qword_18003F890
0x180006ce1  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180006ce6  mov     ebx, eax
0x180006ce8  test    eax, eax
0x180006cea  jns     short loc_180006D24
0x180006cec  mov     rcx, [rbp+18h]; this
0x180006cf0  mov     r9d, eax; char *
0x180006cf3  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006cfa  mov     edx, 5Fh ; '_'; void *
0x180006cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d04  lea     rax, [rbp+var_10]
0x180006d08  mov     rcx, [rbp+Endpoint]; void *
0x180006d0c  cmp     rcx, rax
0x180006d0f  jz      short loc_180006D1D
0x180006d11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d1d  mov     eax, ebx
0x180006d1f  jmp     loc_180006F6E
0x180006d24  mov     r8d, 7
0x180006d2a  lea     rdx, aParent; ":parent"
0x180006d31  lea     rcx, [rbp+Endpoint]
0x180006d35  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180006d3a  test    al, al
0x180006d3c  jnz     short loc_180006D68
0x180006d3e  mov     rcx, [rbp+18h]; this
0x180006d42  mov     ebx, 8007000Eh
0x180006d47  mov     r9d, ebx; char *
0x180006d4a  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006d51  mov     edx, 60h ; '`'; void *
0x180006d56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d5b  lea     rdx, [rbp+var_10]
0x180006d5f  mov     rcx, [rbp+Endpoint]
0x180006d63  cmp     rcx, rdx
0x180006d66  jmp     short loc_180006D0F
0x180006d68  xor     r9d, r9d; SecurityDescriptor
0x180006d6b  mov     r8, [rbp+Endpoint]; Endpoint
0x180006d6f  lea     edx, [r9+0Ah]; MaxCalls
0x180006d73  lea     rcx, Protseq; "ncacn_hvsocket"
0x180006d7a  call    cs:__imp_RpcServerUseProtseqEpW
0x180006d81  nop     dword ptr [rax+rax+00h]
0x180006d86  test    eax, eax
0x180006d88  jz      short loc_180006DA9
0x180006d8a  mov     rcx, [rbp+18h]; this
0x180006d8e  mov     r9d, eax; char *
0x180006d91  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006d98  mov     edx, 66h ; 'f'; void *
0x180006d9d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006da2  mov     ebx, eax
0x180006da4  jmp     loc_180006D04
0x180006da9  mov     [rbp+hObject], 0
0x180006db1  lea     rcx, [rbp+hObject]
0x180006db5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006dba  mov     ebx, eax
0x180006dbc  test    eax, eax
0x180006dbe  jns     short loc_180006DFE
0x180006dc0  mov     rcx, [rbp+18h]; this
0x180006dc4  mov     r9d, eax; char *
0x180006dc7  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006dce  mov     edx, 6Dh ; 'm'; void *
0x180006dd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dd8  mov     rcx, [rbp+hObject]; hObject
0x180006ddc  test    rcx, rcx
0x180006ddf  jz      loc_180006D04
0x180006de5  call    cs:__imp_CloseHandle
0x180006dec  nop     dword ptr [rax+rax+00h]
0x180006df1  test    eax, eax
0x180006df3  jz      loc_180006F8E
0x180006df9  jmp     loc_180006D04
0x180006dfe  mov     [rbp+WaitHandle], 0
0x180006e06  mov     rbx, [rbp+hObject]
0x180006e0a  mov     rax, cs:qword_18004B198
0x180006e11  mov     [rsp+60h+var_38], 18h
0x180006e19  mov     qword ptr [rsp+60h+var_40], 0; unsigned int
0x180006e22  lea     r9, _anonymous_namespace___ServiceStopCallback
0x180006e29  mov     r8, rbx
0x180006e2c  lea     rdx, ServiceName; "cmagent"
0x180006e33  lea     rcx, [rbp+WaitHandle]
0x180006e37  mov     rax, [rax+0C0h]
0x180006e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e43  test    eax, eax
0x180006e45  jz      short loc_180006EB7
0x180006e47  mov     rcx, [rbp+18h]; this
0x180006e4b  mov     r9d, eax; char *
0x180006e4e  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180006e55  mov     edx, 78h ; 'x'; void *
0x180006e5a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006e5f  mov     edi, eax
0x180006e61  mov     rcx, [rbp+WaitHandle]; WaitHandle
0x180006e65  lea     rdx, [rcx-1]
0x180006e69  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006e6d  ja      short loc_180006E7B
0x180006e6f  call    cs:__imp_UnregisterWait
0x180006e76  nop     dword ptr [rax+rax+00h]
0x180006e7b  test    rbx, rbx
0x180006e7e  jz      short loc_180006E97
0x180006e80  mov     rcx, rbx; hObject
0x180006e83  call    cs:__imp_CloseHandle
0x180006e8a  nop     dword ptr [rax+rax+00h]
0x180006e8f  test    eax, eax
0x180006e91  jz      loc_180006F9D
0x180006e97  lea     rax, [rbp+var_10]
0x180006e9b  mov     rcx, [rbp+Endpoint]; void *
0x180006e9f  cmp     rcx, rax
0x180006ea2  jz      short loc_180006EB0
0x180006ea4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006eab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006eb0  mov     eax, edi
0x180006eb2  jmp     loc_180006F6E
0x180006eb7  mov     cs:hServiceStatus, rdi
0x180006ebe  mov     rdi, cs:hEvent
0x180006ec5  test    rdi, rdi
0x180006ec8  jz      short loc_180006EFD
0x180006eca  call    cs:__imp_GetLastError
0x180006ed1  nop     dword ptr [rax+rax+00h]
0x180006ed6  mov     esi, eax
0x180006ed8  mov     rcx, rdi; hObject
0x180006edb  call    cs:__imp_CloseHandle
0x180006ee2  nop     dword ptr [rax+rax+00h]
0x180006ee7  test    eax, eax
0x180006ee9  jz      loc_180006F7F
0x180006eef  mov     ecx, esi; dwErrCode
0x180006ef1  call    cs:__imp_SetLastError
0x180006ef8  nop     dword ptr [rax+rax+00h]
0x180006efd  mov     cs:hEvent, rbx
0x180006f04  mov     rsi, [rbp+WaitHandle]
0x180006f08  mov     rdi, cs:WaitHandle
0x180006f0f  lea     rax, [rdi-1]
0x180006f13  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006f17  ja      short loc_180006F44
0x180006f19  call    cs:__imp_GetLastError
0x180006f20  nop     dword ptr [rax+rax+00h]
0x180006f25  mov     ebx, eax
0x180006f27  mov     rcx, rdi; WaitHandle
0x180006f2a  call    cs:__imp_UnregisterWait
0x180006f31  nop     dword ptr [rax+rax+00h]
0x180006f36  mov     ecx, ebx; dwErrCode
0x180006f38  call    cs:__imp_SetLastError
0x180006f3f  nop     dword ptr [rax+rax+00h]
0x180006f44  mov     cs:WaitHandle, rsi
0x180006f4b  mov     [rbp+WaitHandle], 0
0x180006f53  lea     rax, [rbp+var_10]
0x180006f57  mov     rcx, [rbp+Endpoint]; void *
0x180006f5b  cmp     rcx, rax
0x180006f5e  jz      short loc_180006F6C
0x180006f60  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006f6c  xor     eax, eax
0x180006f6e  mov     rbx, [rsp+60h+arg_10]
0x180006f76  add     rsp, 60h
0x180006f7a  pop     rdi
0x180006f7b  pop     rsi
0x180006f7c  pop     rbp
0x180006f7d  retn
0x180006f7f  mov     rcx, [rbp+18h]; this
0x180006f83  mov     edx, 0A0Bh; void *
0x180006f88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f8e  mov     rcx, [rbp+18h]; this
0x180006f92  mov     edx, 0A0Bh; void *
0x180006f97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f9d  mov     rcx, [rbp+18h]; this
0x180006fa1  mov     edx, 0A0Bh; void *
0x180006fa6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
