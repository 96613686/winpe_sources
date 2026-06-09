# Container::Manager::Service::CmsService::Initialize(void)

- ea: `0x180023d24`
- end: `0x1800242b4`
- name: `?Initialize@CmsService@Service@Manager@Container@@QEAAJXZ`
- size: `1424`
- prototype: `__int64 __fastcall(Container::Manager::Service::CmsService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026440`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016658`
- `0x180023b68`
- `0x180023d24`
- `0x1800242bc`
- `0x1800262e4`
- `0x1801b7010`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x180023da9`
- `ntdll!RtlLengthRequiredSid` at `0x180023da9`
- `ntdll!RtlCreateServiceSid` at `0x180023e0e`
- `ntdll!RtlCreateServiceSid` at `0x180023e0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023f39`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023f39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023fab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024058`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800241f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023fab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024058`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800241f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024177`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800241c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024207`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024177`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800241c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024207`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024041`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002423d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024041`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002423d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023dbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023dbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ee6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002406d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024093`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002426b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ee6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002406d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024093`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002426b`
- `RPCRT4!RpcServerUseProtseqW` at `0x180023f02`
- `RPCRT4!RpcServerUseProtseqW` at `0x180023f02`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002402d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800240e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180024228`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002402d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800240e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180024228`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023e59`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023eb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023e59`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023eb6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180023d76`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180023d76`

## string_xrefs

- `0x180023d8e`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023ddf`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023e25`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023e6d`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023ecb`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023f19`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023f7a`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x18002400c`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180023d6c`: `cmservice`

## pseudocode

```c
__int64 __fastcall Container::Manager::Service::CmsService::Initialize(Container::Manager::Service::CmsService *this)
{
  Container::Manager::Service::CmsService *v1; // rcx
  SERVICE_STATUS_HANDLE v2; // rdi
  const char *v3; // r9
  HLOCAL v5; // rax
  void *v6; // r15
  unsigned int LastError; // ebx
  NTSTATUS v8; // eax
  const char *v9; // r9
  const char *v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rsi
  int v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v18; // rbx
  unsigned int v19; // eax
  int v20; // edi
  unsigned int v21; // r8d
  const char *v22; // r9
  HANDLE v23; // r14
  HANDLE v24; // rdi
  DWORD v25; // ebx
  HLOCAL v26; // rdi
  DWORD v27; // ebx
  PSECURITY_DESCRIPTOR v28; // r14
  HLOCAL v29; // rdi
  DWORD v30; // ebx
  PSECURITY_DESCRIPTOR v31; // r14
  HLOCAL v32; // rdi
  DWORD v33; // ebx
  struct _TP_TIMER *v34; // rdi
  DWORD v35; // ebx
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // [rsp+20h] [rbp-48h]
  HANDLE hObject; // [rsp+40h] [rbp-28h] BYREF
  _UNICODE_STRING ServiceName; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  Container::Manager::Service::CmsService *ServiceSidLength; // [rsp+A0h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+B0h] [rbp+48h] BYREF
  HANDLE WaitHandle; // [rsp+B8h] [rbp+50h] BYREF

  ServiceSidLength = this;
  AcquireSRWLockExclusive(&pv);
  Container::Manager::Service::CmsService::Reset(v1);
  ReleaseSRWLockExclusive(&pv);
  v2 = RegisterServiceCtrlHandlerExW(L"cmservice", anonymous_namespace_::ServiceHandlerCallback, 0);
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x83,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
             v3);
  LODWORD(ServiceSidLength) = RtlLengthRequiredSid(6u);
  v5 = LocalAlloc(0x40u, (unsigned int)ServiceSidLength);
  v6 = v5;
  if ( !v5 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
      (const char *)0x8007000ELL,
      v38);
    return LastError;
  }
  *(_QWORD *)&ServiceName.Length = 1310738;
  ServiceName.Buffer = (PWSTR)L"cmservice";
  v8 = RtlCreateServiceSid(&ServiceName, v5, (PULONG)&ServiceSidLength);
  if ( v8 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x8D,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                  (const char *)(unsigned int)v8,
                  v38);
LABEL_36:
    LocalFree(v6);
    return LastError;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;WD)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x95,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                  v9);
LABEL_10:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_36;
  }
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;BA)", 1u, &hMem, 0) )
  {
    v11 = 157;
LABEL_14:
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
            v10);
LABEL_15:
    LastError = v12;
LABEL_16:
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_10;
  }
  v13 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  if ( v13 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xA2,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
            (const char *)v13,
            v38);
    goto LABEL_15;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(Container::Manager::Service::CmsService::ServiceStopTimeoutCallback, &pv, 0);
  if ( !ThreadpoolTimer )
  {
    v11 = 169;
    goto LABEL_14;
  }
  hObject = 0;
  v15 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &hObject,
          1);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
      (const char *)(unsigned int)v15,
      v38);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    CloseThreadpoolTimer(ThreadpoolTimer);
    goto LABEL_16;
  }
  WaitHandle = 0;
  v18 = hObject;
  v19 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)()))(qword_18021E488 + 192))(
          &WaitHandle,
          L"cmservice",
          hObject,
          anonymous_namespace_::ServiceStopCallback);
  if ( v19 )
  {
    v20 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xBB,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
            (const char *)v19,
            0);
    if ( (char *)WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      UnregisterWait(WaitHandle);
    if ( v18 && !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
    CloseThreadpoolTimer(ThreadpoolTimer);
    if ( hMem )
      LocalFree(hMem);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    LastError = v20;
    goto LABEL_36;
  }
  hServiceStatus = v2;
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    &hEvent,
    &hObject);
  v23 = WaitHandle;
  v24 = ::WaitHandle;
  if ( (char *)::WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v25 = GetLastError();
    UnregisterWait(v24);
    SetLastError(v25);
  }
  ::WaitHandle = v23;
  WaitHandle = 0;
  v26 = pSid;
  if ( pSid )
  {
    v27 = GetLastError();
    LocalFree(v26);
    SetLastError(v27);
  }
  pSid = v6;
  v28 = SecurityDescriptor;
  v29 = qword_18021E4C8;
  if ( qword_18021E4C8 )
  {
    v30 = GetLastError();
    LocalFree(v29);
    SetLastError(v30);
  }
  qword_18021E4C8 = v28;
  SecurityDescriptor = 0;
  v31 = hMem;
  v32 = qword_18021E4D0;
  if ( qword_18021E4D0 )
  {
    v33 = GetLastError();
    LocalFree(v32);
    SetLastError(v33);
  }
  qword_18021E4D0 = v31;
  hMem = 0;
  v34 = pti;
  if ( pti )
  {
    v35 = GetLastError();
    CloseThreadpoolTimer(v34);
    SetLastError(v35);
  }
  pti = ThreadpoolTimer;
  if ( (char *)WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    UnregisterWait(WaitHandle);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  if ( hMem )
    LocalFree(hMem);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x180023d24  mov     [rsp-30h+ServiceSidLength], rcx
0x180023d29  push    rbp
0x180023d2a  push    rbx
0x180023d2b  push    rsi
0x180023d2c  push    rdi
0x180023d2d  push    r14
0x180023d2f  push    r15
0x180023d31  mov     rbp, rsp
0x180023d34  sub     rsp, 68h
0x180023d38  lea     rsi, pv
0x180023d3f  mov     rcx, rsi; SRWLock
0x180023d42  call    cs:__imp_AcquireSRWLockExclusive
0x180023d49  nop     dword ptr [rax+rax+00h]
0x180023d4e  call    ?Reset@CmsService@Service@Manager@Container@@AEAAXXZ; Container::Manager::Service::CmsService::Reset(void)
0x180023d53  mov     rcx, rsi; SRWLock
0x180023d56  call    cs:__imp_ReleaseSRWLockExclusive
0x180023d5d  nop     dword ptr [rax+rax+00h]
0x180023d62  xor     r8d, r8d; lpContext
0x180023d65  lea     rdx, _anonymous_namespace___ServiceHandlerCallback; lpHandlerProc
0x180023d6c  lea     r14, ServiceName; "cmservice"
0x180023d73  mov     rcx, r14; lpServiceName
0x180023d76  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180023d7d  nop     dword ptr [rax+rax+00h]
0x180023d82  mov     rdi, rax
0x180023d85  test    rax, rax
0x180023d88  jnz     short loc_180023DA4
0x180023d8a  mov     rcx, [rbp+30h]; this
0x180023d8e  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023d95  mov     edx, 83h; void *
0x180023d9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023d9f  jmp     loc_180024279
0x180023da4  mov     ecx, 6; SubAuthorityCount
0x180023da9  call    cs:__imp_RtlLengthRequiredSid
0x180023db0  nop     dword ptr [rax+rax+00h]
0x180023db5  mov     edx, eax; uBytes
0x180023db7  mov     dword ptr [rbp+ServiceSidLength], edx
0x180023dba  mov     ecx, 40h ; '@'; uFlags
0x180023dbf  call    cs:__imp_LocalAlloc
0x180023dc6  nop     dword ptr [rax+rax+00h]
0x180023dcb  mov     r15, rax
0x180023dce  test    rax, rax
0x180023dd1  jnz     short loc_180023DF7
0x180023dd3  mov     rcx, [rbp+30h]; this
0x180023dd7  mov     ebx, 8007000Eh
0x180023ddc  mov     r9d, ebx; char *
0x180023ddf  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023de6  mov     edx, 88h; void *
0x180023deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023df0  mov     eax, ebx
0x180023df2  jmp     loc_180024279
0x180023df7  mov     qword ptr [rbp+ServiceName.Length], 140012h
0x180023dff  mov     [rbp+ServiceName.Buffer], r14
0x180023e03  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180023e07  mov     rdx, r15; ServiceSid
0x180023e0a  lea     rcx, [rbp+ServiceName]; ServiceName
0x180023e0e  call    cs:__imp_RtlCreateServiceSid
0x180023e15  nop     dword ptr [rax+rax+00h]
0x180023e1a  test    eax, eax
0x180023e1c  jns     short loc_180023E3D
0x180023e1e  mov     rcx, [rbp+30h]; this
0x180023e22  mov     r9d, eax; char *
0x180023e25  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023e2c  mov     edx, 8Dh; void *
0x180023e31  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180023e36  mov     ebx, eax
0x180023e38  jmp     loc_180024090
0x180023e3d  mov     [rbp+SecurityDescriptor], 0
0x180023e45  xor     r9d, r9d; SecurityDescriptorSize
0x180023e48  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180023e4c  lea     ebx, [r9+1]
0x180023e50  mov     edx, ebx; StringSDRevision
0x180023e52  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;WD)"
0x180023e59  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023e60  nop     dword ptr [rax+rax+00h]
0x180023e65  test    eax, eax
0x180023e67  jnz     short loc_180023E9E
0x180023e69  mov     rcx, [rbp+30h]; this
0x180023e6d  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023e74  mov     edx, 95h; void *
0x180023e79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e7e  mov     ebx, eax
0x180023e80  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180023e84  test    rcx, rcx
0x180023e87  jz      loc_180024090
0x180023e8d  call    cs:__imp_LocalFree
0x180023e94  nop     dword ptr [rax+rax+00h]
0x180023e99  jmp     loc_180024090
0x180023e9e  mov     [rbp+hMem], 0
0x180023ea6  xor     r9d, r9d; SecurityDescriptorSize
0x180023ea9  lea     r8, [rbp+hMem]; SecurityDescriptor
0x180023ead  mov     edx, ebx; StringSDRevision
0x180023eaf  lea     rcx, aOBagBadAGaSyAG; "O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;BA)"
0x180023eb6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023ebd  nop     dword ptr [rax+rax+00h]
0x180023ec2  test    eax, eax
0x180023ec4  jnz     short loc_180023EF4
0x180023ec6  mov     edx, 9Dh; void *
0x180023ecb  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023ed2  mov     rcx, [rbp+30h]; this
0x180023ed6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023edb  mov     ebx, eax
0x180023edd  mov     rcx, [rbp+hMem]; hMem
0x180023ee1  test    rcx, rcx
0x180023ee4  jz      short loc_180023E80
0x180023ee6  call    cs:__imp_LocalFree
0x180023eed  nop     dword ptr [rax+rax+00h]
0x180023ef2  jmp     short loc_180023E80
0x180023ef4  xor     r8d, r8d; SecurityDescriptor
0x180023ef7  lea     edx, [r8+0Ah]; MaxCalls
0x180023efb  lea     rcx, Protseq; "ncalrpc"
0x180023f02  call    cs:__imp_RpcServerUseProtseqW
0x180023f09  nop     dword ptr [rax+rax+00h]
0x180023f0e  test    eax, eax
0x180023f10  jz      short loc_180023F2C
0x180023f12  mov     rcx, [rbp+30h]; this
0x180023f16  mov     r9d, eax; char *
0x180023f19  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023f20  mov     edx, 0A2h; void *
0x180023f25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023f2a  jmp     short loc_180023EDB
0x180023f2c  xor     r8d, r8d; pcbe
0x180023f2f  mov     rdx, rsi; pv
0x180023f32  lea     rcx, ?ServiceStopTimeoutCallback@CmsService@Service@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180023f39  call    cs:__imp_CreateThreadpoolTimer
0x180023f40  nop     dword ptr [rax+rax+00h]
0x180023f45  mov     rsi, rax
0x180023f48  test    rax, rax
0x180023f4b  jnz     short loc_180023F57
0x180023f4d  mov     edx, 0A9h
0x180023f52  jmp     loc_180023ECB
0x180023f57  mov     [rbp+hObject], 0
0x180023f5f  xor     r9d, r9d
0x180023f62  mov     edx, ebx
0x180023f64  lea     rcx, [rbp+hObject]
0x180023f68  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180023f6d  mov     ebx, eax
0x180023f6f  test    eax, eax
0x180023f71  jns     short loc_180023FBC
0x180023f73  mov     rcx, [rbp+30h]; this
0x180023f77  mov     r9d, eax; char *
0x180023f7a  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180023f81  mov     edx, 0B0h; void *
0x180023f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f8b  mov     rcx, [rbp+hObject]; hObject
0x180023f8f  test    rcx, rcx
0x180023f92  jz      short loc_180023FA8
0x180023f94  call    cs:__imp_CloseHandle
0x180023f9b  nop     dword ptr [rax+rax+00h]
0x180023fa0  test    eax, eax
0x180023fa2  jz      loc_180024296
0x180023fa8  mov     rcx, rsi; pti
0x180023fab  call    cs:__imp_CloseThreadpoolTimer
0x180023fb2  nop     dword ptr [rax+rax+00h]
0x180023fb7  jmp     loc_180023EDD
0x180023fbc  mov     [rbp+WaitHandle], 0
0x180023fc4  mov     rbx, [rbp+hObject]
0x180023fc8  mov     rax, cs:qword_18021E488
0x180023fcf  mov     [rsp+68h+var_40], 18h
0x180023fd7  mov     qword ptr [rsp+68h+var_48], 0; unsigned int
0x180023fe0  lea     r9, _anonymous_namespace___ServiceStopCallback
0x180023fe7  mov     r8, rbx
0x180023fea  mov     rdx, r14
0x180023fed  lea     rcx, [rbp+WaitHandle]
0x180023ff1  mov     rax, [rax+0C0h]
0x180023ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ffd  test    eax, eax
0x180023fff  jz      loc_1800240A4
0x180024005  mov     rcx, [rbp+30h]; this
0x180024009  mov     r9d, eax; char *
0x18002400c  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180024013  mov     edx, 0BBh; void *
0x180024018  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002401d  mov     edi, eax
0x18002401f  mov     rcx, [rbp+WaitHandle]; WaitHandle
0x180024023  lea     rdx, [rcx-1]
0x180024027  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002402b  ja      short loc_180024039
0x18002402d  call    cs:__imp_UnregisterWait
0x180024034  nop     dword ptr [rax+rax+00h]
0x180024039  test    rbx, rbx
0x18002403c  jz      short loc_180024055
0x18002403e  mov     rcx, rbx; hObject
0x180024041  call    cs:__imp_CloseHandle
0x180024048  nop     dword ptr [rax+rax+00h]
0x18002404d  test    eax, eax
0x18002404f  jz      loc_1800242A5
0x180024055  mov     rcx, rsi; pti
0x180024058  call    cs:__imp_CloseThreadpoolTimer
0x18002405f  nop     dword ptr [rax+rax+00h]
0x180024064  mov     rcx, [rbp+hMem]; hMem
0x180024068  test    rcx, rcx
0x18002406b  jz      short loc_180024079
0x18002406d  call    cs:__imp_LocalFree
0x180024074  nop     dword ptr [rax+rax+00h]
0x180024079  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002407d  test    rcx, rcx
0x180024080  jz      short loc_18002408E
0x180024082  call    cs:__imp_LocalFree
0x180024089  nop     dword ptr [rax+rax+00h]
0x18002408e  mov     ebx, edi
0x180024090  mov     rcx, r15; hMem
0x180024093  call    cs:__imp_LocalFree
0x18002409a  nop     dword ptr [rax+rax+00h]
0x18002409f  jmp     loc_180023DF0
0x1800240a4  mov     cs:hServiceStatus, rdi
0x1800240ab  lea     rdx, [rbp+hObject]
0x1800240af  lea     rcx, hEvent
0x1800240b6  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800240bb  mov     r14, [rbp+WaitHandle]
0x1800240bf  mov     rdi, cs:WaitHandle
0x1800240c6  lea     rax, [rdi-1]
0x1800240ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800240ce  ja      short loc_1800240FB
0x1800240d0  call    cs:__imp_GetLastError
0x1800240d7  nop     dword ptr [rax+rax+00h]
0x1800240dc  mov     ebx, eax
0x1800240de  mov     rcx, rdi; WaitHandle
0x1800240e1  call    cs:__imp_UnregisterWait
0x1800240e8  nop     dword ptr [rax+rax+00h]
0x1800240ed  mov     ecx, ebx; dwErrCode
0x1800240ef  call    cs:__imp_SetLastError
0x1800240f6  nop     dword ptr [rax+rax+00h]
0x1800240fb  mov     cs:WaitHandle, r14
0x180024102  mov     [rbp+WaitHandle], 0
0x18002410a  mov     rdi, cs:pSid
0x180024111  test    rdi, rdi
0x180024114  jz      short loc_180024141
0x180024116  call    cs:__imp_GetLastError
0x18002411d  nop     dword ptr [rax+rax+00h]
0x180024122  mov     ebx, eax
0x180024124  mov     rcx, rdi; hMem
0x180024127  call    cs:__imp_LocalFree
0x18002412e  nop     dword ptr [rax+rax+00h]
0x180024133  mov     ecx, ebx; dwErrCode
0x180024135  call    cs:__imp_SetLastError
0x18002413c  nop     dword ptr [rax+rax+00h]
0x180024141  mov     cs:pSid, r15
0x180024148  mov     r14, [rbp+SecurityDescriptor]
0x18002414c  mov     rdi, cs:qword_18021E4C8
0x180024153  test    rdi, rdi
0x180024156  jz      short loc_180024183
0x180024158  call    cs:__imp_GetLastError
0x18002415f  nop     dword ptr [rax+rax+00h]
0x180024164  mov     ebx, eax
0x180024166  mov     rcx, rdi; hMem
0x180024169  call    cs:__imp_LocalFree
0x180024170  nop     dword ptr [rax+rax+00h]
0x180024175  mov     ecx, ebx; dwErrCode
0x180024177  call    cs:__imp_SetLastError
0x18002417e  nop     dword ptr [rax+rax+00h]
0x180024183  mov     cs:qword_18021E4C8, r14
0x18002418a  mov     [rbp+SecurityDescriptor], 0
0x180024192  mov     r14, [rbp+hMem]
0x180024196  mov     rdi, cs:qword_18021E4D0
0x18002419d  test    rdi, rdi
0x1800241a0  jz      short loc_1800241CD
0x1800241a2  call    cs:__imp_GetLastError
0x1800241a9  nop     dword ptr [rax+rax+00h]
0x1800241ae  mov     ebx, eax
0x1800241b0  mov     rcx, rdi; hMem
0x1800241b3  call    cs:__imp_LocalFree
0x1800241ba  nop     dword ptr [rax+rax+00h]
0x1800241bf  mov     ecx, ebx; dwErrCode
0x1800241c1  call    cs:__imp_SetLastError
0x1800241c8  nop     dword ptr [rax+rax+00h]
0x1800241cd  mov     cs:qword_18021E4D0, r14
0x1800241d4  mov     [rbp+hMem], 0
0x1800241dc  mov     rdi, cs:pti
0x1800241e3  test    rdi, rdi
0x1800241e6  jz      short loc_180024213
0x1800241e8  call    cs:__imp_GetLastError
0x1800241ef  nop     dword ptr [rax+rax+00h]
0x1800241f4  mov     ebx, eax
0x1800241f6  mov     rcx, rdi; pti
0x1800241f9  call    cs:__imp_CloseThreadpoolTimer
0x180024200  nop     dword ptr [rax+rax+00h]
0x180024205  mov     ecx, ebx; dwErrCode
0x180024207  call    cs:__imp_SetLastError
0x18002420e  nop     dword ptr [rax+rax+00h]
0x180024213  mov     cs:pti, rsi
0x18002421a  mov     rcx, [rbp+WaitHandle]; WaitHandle
0x18002421e  lea     rax, [rcx-1]
0x180024222  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024226  ja      short loc_180024234
0x180024228  call    cs:__imp_UnregisterWait
0x18002422f  nop     dword ptr [rax+rax+00h]
0x180024234  mov     rcx, [rbp+hObject]; hObject
0x180024238  test    rcx, rcx
0x18002423b  jz      short loc_18002424D
0x18002423d  call    cs:__imp_CloseHandle
0x180024244  nop     dword ptr [rax+rax+00h]
0x180024249  test    eax, eax
0x18002424b  jz      short loc_180024287
0x18002424d  mov     rcx, [rbp+hMem]; hMem
0x180024251  test    rcx, rcx
0x180024254  jz      short loc_180024262
0x180024256  call    cs:__imp_LocalFree
0x18002425d  nop     dword ptr [rax+rax+00h]
0x180024262  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180024266  test    rcx, rcx
  ... truncated ...
```
