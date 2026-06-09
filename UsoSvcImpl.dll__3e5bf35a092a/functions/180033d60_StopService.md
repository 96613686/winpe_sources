# StopService

- ea: `0x180033d60`
- end: `0x180034366`
- name: `StopService`
- size: `1542`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008ea8`
- `0x180008ec4`
- `0x180011680`
- `0x18001b064`
- `0x18002e0d0`
- `0x1800308e8`
- `0x180030bd0`
- `0x180033ad8`
- `0x180033d60`
- `0x1800353e0`
- `0x180037d9c`
- `0x180037e28`
- `0x180042e00`
- `0x180042e48`
- `0x1800648fc`
- `0x180064a3c`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18003409c`
- `ntdll!RtlPublishWnfStateData` at `0x18003409c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034042`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034042`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034068`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034068`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ecf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ecf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034297`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180033f12`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180033f12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034034`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800340c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800340c7`

## string_xrefs

- `0x180033d8e`: `UsoSvc setting service state to: SERVICE_STOP_PENDING`
- `0x180034191`: `UsoSvc setting service state to: SERVICE_STOPPED`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int StopService()
{
  int v0; // eax
  HANDLE v1; // rdi
  HANDLE v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  char v11; // si
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  DWORD v18; // eax
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r13d
  HANDLE v22; // r14
  DWORD LastError; // esi
  HANDLE v24; // rsi
  DWORD v25; // r14d
  unsigned int v26; // r8d
  const char *v27; // r9
  __int64 *System; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rax
  volatile signed __int32 *v31; // rsi
  _QWORD *v32; // r12
  _QWORD *v33; // rsi
  volatile signed __int32 *v34; // r14
  __int64 **v35; // rcx
  __int64 v36; // rax
  _QWORD *v37; // rcx
  __int64 *i; // rcx
  int result; // eax
  const char *v40; // r9
  unsigned int v41; // r8d
  unsigned int v42; // r8d
  HANDLE v43; // [rsp+30h] [rbp-88h] BYREF
  HANDLE hEvent; // [rsp+38h] [rbp-80h] BYREF
  HANDLE hHandle; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v46[40]; // [rsp+48h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-48h] BYREF
  __int64 v48; // [rsp+78h] [rbp-40h]
  __int64 v49; // [rsp+80h] [rbp-38h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    hObject = L"UsoSvc setting service state to: SERVICE_STOP_PENDING";
    v48 = 53;
    SystemInterface::Log<>(&hObject);
    ServiceHelpers::UpdateServiceStatus(3u, 0, 0x7530u);
    *(_BYTE *)(qword_180150768 + 48) = 1;
    *(_BYTE *)(qword_180150780 + 48) = 1;
    *(_BYTE *)(qword_180150770 + 48) = 1;
    *(_BYTE *)(qword_180150788 + 48) = 1;
    *(_BYTE *)(qword_180150790 + 48) = 1;
    *(_BYTE *)(qword_180150798 + 48) = 1;
    if ( (unsigned int)mtx_do_lock(&g_coreWorkerLaunchMutex) )
      std::_Throw_Cpp_error(5);
    v0 = dword_18014D7EC;
    if ( dword_18014D7EC == 0x7FFFFFFF )
    {
      dword_18014D7EC = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    g_ShuttingDown = 1;
    --dword_18014D7EC;
    if ( v0 == 1 )
    {
      dword_18014D7E8 = -1;
      ReleaseSRWLockExclusive(&stru_18014D7B0);
    }
    v1 = 0;
    hHandle = 0;
    v2 = 0;
    hEvent = 0;
    if ( DoesCoreWorkerSupportsPrivateNamespaces() )
    {
      v3 = Windows::PrivateNamespaceHelpers::CreatePrivateNamespaceEvent(&hObject, L"\\UsoCoreWorkerExiting", 1);
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        &hHandle,
        v3);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v4, v5);
      v6 = Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceEvent(&hObject);
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        &hEvent,
        v6);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v7, v8);
      v1 = hHandle;
      v2 = hEvent;
    }
    else
    {
      SecurityDescriptor = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
      {
        hObject = (HANDLE)24;
        v49 = 0;
        v48 = (__int64)SecurityDescriptor;
        v9 = (_QWORD *)GlobalObjectName(v46, L"\\UsoCoreWorkerExiting");
        if ( v9[3] > 7u )
          v9 = (_QWORD *)*v9;
        _try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &hHandle,
          1,
          v9,
          &hObject);
        std::wstring::~wstring(v46);
        v1 = hHandle;
      }
      v43 = 0;
      v10 = (_QWORD *)GlobalObjectName(v46, L"\\UsoCoreWorkerRequestShutdown");
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      v11 = _try_open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEB_WK_N_Z(
              &v43,
              v10);
      std::wstring::~wstring(v46);
      if ( v11 )
      {
        hObject = 0;
        hEvent = 0;
        __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
          &hEvent,
          &v43);
        __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
          &v43,
          &hObject);
        if ( hObject && !CloseHandle(hObject) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v12, v13);
        v2 = hEvent;
      }
      if ( v43 && !CloseHandle(v43) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v14, v15);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
    }
    if ( v2 )
    {
      if ( !SetEvent(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9C7, v16, v17);
      if ( v1 )
      {
        v18 = WaitForSingleObjectEx(v1, 0x2710u, 0);
        if ( v18 != 258 )
        {
          if ( v18 )
            wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xAD8, v19, v20);
        }
      }
    }
    *(_BYTE *)(qword_180150778 + 48) = 1;
    RtlPublishWnfStateData(WNF_USO_SERVICE_STOPPING, 0, 0, 0);
    v21 = UninitializeService();
    v22 = WaitHandle;
    if ( WaitHandle != (HANDLE)-1LL && WaitHandle )
    {
      LastError = GetLastError();
      UnregisterWait(v22);
      SetLastError(LastError);
    }
    WaitHandle = (HANDLE)-1LL;
    qword_180150118 = 0;
    v24 = ::hObject;
    if ( ::hObject )
    {
      v25 = GetLastError();
      if ( !CloseHandle(v24) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v26, v27);
      SetLastError(v25);
    }
    ::hObject = 0;
    System = SystemInterface::Service::GetSystem((__int64 *)&hObject);
    v29 = (_QWORD *)*System;
    v30 = *(_QWORD *)*System;
    LODWORD(v43) = 3;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v30 + 152))(v29, &v43);
    v31 = (volatile signed __int32 *)v48;
    if ( v48 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v48 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    hObject = L"UsoSvc setting service state to: SERVICE_STOPPED";
    v48 = 48;
    SystemInterface::Log<>(&hObject);
    v32 = g_loggerMap;
    v33 = *(_QWORD **)g_loggerMap;
    while ( v33 != v32 )
    {
      v33[8] = 0;
      v34 = (volatile signed __int32 *)v33[9];
      v33[9] = 0;
      if ( v34 )
      {
        if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      v35 = (__int64 **)v33[2];
      if ( *((_BYTE *)v35 + 25) )
      {
        v36 = v33[1];
        while ( !*(_BYTE *)(v36 + 25) )
        {
          v37 = (_QWORD *)v36;
          if ( v33 != *(_QWORD **)(v36 + 16) )
            break;
          v36 = *(_QWORD *)(v36 + 8);
          v33 = v37;
        }
        v33 = (_QWORD *)v36;
      }
      else
      {
        v33 = (_QWORD *)v33[2];
        for ( i = *v35; !*((_BYTE *)i + 25); i = (__int64 *)*i )
          v33 = i;
      }
    }
    result = ServiceHelpers::UpdateServiceStatus(1u, v21, 0);
    if ( v2 )
    {
      result = CloseHandle(v2);
      if ( !result )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v41, v40);
    }
    if ( v1 )
    {
      result = CloseHandle(v1);
      if ( !result )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v42, v40);
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x31B,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
             v40);
  }
  return result;
}

```

## disassembly

```asm
0x180033d60  mov     r11, rsp
0x180033d63  mov     [r11+8], rbx
0x180033d67  mov     [r11+10h], rsi
0x180033d6b  mov     [r11+18h], rdi
0x180033d6f  push    r12
0x180033d71  push    r13
0x180033d73  push    r14
0x180033d75  sub     rsp, 0A0h
0x180033d7c  mov     rax, cs:__security_cookie
0x180033d83  xor     rax, rsp
0x180033d86  mov     [rsp+0B8h+var_20], rax
0x180033d8e  lea     rax, aUsosvcSettingS_1; "UsoSvc setting service state to: SERVIC"...
0x180033d95  mov     [r11-48h], rax
0x180033d99  mov     qword ptr [r11-40h], 35h ; '5'
0x180033da1  lea     rcx, [r11-48h]
0x180033da5  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x180033daa  xor     edx, edx; unsigned int
0x180033dac  lea     ecx, [rdx+3]; unsigned int
0x180033daf  mov     r8d, 7530h; unsigned int
0x180033db5  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x180033dba  mov     rax, cs:qword_180150768
0x180033dc1  mov     byte ptr [rax+30h], 1
0x180033dc5  mov     rax, cs:qword_180150780
0x180033dcc  mov     byte ptr [rax+30h], 1
0x180033dd0  mov     rax, cs:qword_180150770
0x180033dd7  mov     byte ptr [rax+30h], 1
0x180033ddb  mov     rax, cs:qword_180150788
0x180033de2  mov     byte ptr [rax+30h], 1
0x180033de6  mov     rax, cs:qword_180150790
0x180033ded  mov     byte ptr [rax+30h], 1
0x180033df1  mov     rax, cs:qword_180150798
0x180033df8  mov     byte ptr [rax+30h], 1
0x180033dfc  lea     rcx, ?g_coreWorkerLaunchMutex@@3Vrecursive_mutex@std@@A; std::recursive_mutex g_coreWorkerLaunchMutex
0x180033e03  call    mtx_do_lock
0x180033e08  xor     r12d, r12d
0x180033e0b  test    eax, eax
0x180033e0d  jnz     loc_1800342DB
0x180033e13  mov     eax, cs:dword_18014D7EC
0x180033e19  cmp     eax, 7FFFFFFFh
0x180033e1e  jz      loc_1800342E5
0x180033e24  mov     cs:?g_ShuttingDown@@3_NA, 1; bool g_ShuttingDown
0x180033e2b  sub     eax, 1
0x180033e2e  mov     cs:dword_18014D7EC, eax
0x180033e34  jnz     short loc_180033E4D
0x180033e36  mov     cs:dword_18014D7E8, 0FFFFFFFFh
0x180033e40  lea     rcx, stru_18014D7B0; SRWLock
0x180033e47  call    cs:__imp_ReleaseSRWLockExclusive
0x180033e4d  mov     rdi, r12
0x180033e50  mov     [rsp+0B8h+hHandle], r12
0x180033e55  mov     rbx, r12
0x180033e58  mov     [rsp+0B8h+hEvent], rbx
0x180033e5d  call    ?DoesCoreWorkerSupportsPrivateNamespaces@@YA_NXZ; DoesCoreWorkerSupportsPrivateNamespaces(void)
0x180033e62  test    al, al
0x180033e64  jz      loc_180033EF4
0x180033e6a  mov     r8d, 1
0x180033e70  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x180033e77  lea     rcx, [rsp+0B8h+hObject]
0x180033e7c  call    ?CreatePrivateNamespaceEvent@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WW4EventOptions@4@PEA_N@Z
0x180033e81  mov     rdx, rax
0x180033e84  lea     rcx, [rsp+0B8h+hHandle]
0x180033e89  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180033e8e  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180033e93  test    rcx, rcx
0x180033e96  jz      short loc_180033EAE
0x180033e98  call    cs:__imp_CloseHandle
0x180033e9e  mov     rcx, [rsp+0B8h]; this
0x180033ea6  test    eax, eax
0x180033ea8  jz      loc_1800342FA
0x180033eae  lea     rcx, [rsp+0B8h+hObject]
0x180033eb3  call    ?TryOpenPrivateNamespaceEvent@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WK_N@Z
0x180033eb8  mov     rdx, rax
0x180033ebb  lea     rcx, [rsp+0B8h+hEvent]
0x180033ec0  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180033ec5  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180033eca  test    rcx, rcx
0x180033ecd  jz      short loc_180033EE5
0x180033ecf  call    cs:__imp_CloseHandle
0x180033ed5  mov     rcx, [rsp+0B8h]; this
0x180033edd  test    eax, eax
0x180033edf  jz      loc_180034305
0x180033ee5  mov     rdi, [rsp+0B8h+hHandle]
0x180033eea  mov     rbx, [rsp+0B8h+hEvent]
0x180033eef  jmp     loc_18003403A
0x180033ef4  mov     [rsp+0B8h+SecurityDescriptor], r12
0x180033efc  xor     r9d, r9d; SecurityDescriptorSize
0x180033eff  lea     r8, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x180033f07  lea     edx, [r9+1]; StringSDRevision
0x180033f0b  lea     rcx, aDAGaSy; "D:(A;;GA;;;SY)"
0x180033f12  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180033f18  test    eax, eax
0x180033f1a  jz      short loc_180033F7B
0x180033f1c  mov     [rsp+0B8h+hObject], 18h
0x180033f25  mov     [rsp+0B8h+var_38], r12
0x180033f2d  mov     rax, [rsp+0B8h+SecurityDescriptor]
0x180033f35  mov     [rsp+0B8h+var_40], rax
0x180033f3a  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x180033f41  lea     rcx, [rsp+0B8h+var_70]
0x180033f46  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x180033f4b  cmp     qword ptr [rax+18h], 7
0x180033f50  jbe     short loc_180033F55
0x180033f52  mov     rax, [rax]
0x180033f55  lea     r9, [rsp+0B8h+hObject]
0x180033f5a  mov     r8, rax
0x180033f5d  mov     edx, 1
0x180033f62  lea     rcx, [rsp+0B8h+hHandle]
0x180033f67  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180033f6c  lea     rcx, [rsp+0B8h+var_70]; void *
0x180033f71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033f76  mov     rdi, [rsp+0B8h+hHandle]
0x180033f7b  mov     [rsp+0B8h+var_88], r12
0x180033f80  lea     rdx, aUsocoreworkerr; "\\UsoCoreWorkerRequestShutdown"
0x180033f87  lea     rcx, [rsp+0B8h+var_70]
0x180033f8c  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x180033f91  cmp     qword ptr [rax+18h], 7
0x180033f96  jbe     short loc_180033F9B
0x180033f98  mov     rax, [rax]
0x180033f9b  mov     rdx, rax
0x180033f9e  lea     rcx, [rsp+0B8h+var_88]
0x180033fa3  call    ?try_open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEB_WK_N@Z
0x180033fa8  mov     sil, al
0x180033fab  lea     rcx, [rsp+0B8h+var_70]; void *
0x180033fb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033fb5  test    sil, sil
0x180033fb8  jz      short loc_180034007
0x180033fba  mov     [rsp+0B8h+hObject], r12
0x180033fbf  mov     [rsp+0B8h+hEvent], r12
0x180033fc4  lea     rdx, [rsp+0B8h+var_88]
0x180033fc9  lea     rcx, [rsp+0B8h+hEvent]
0x180033fce  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180033fd3  lea     rdx, [rsp+0B8h+hObject]
0x180033fd8  lea     rcx, [rsp+0B8h+var_88]
0x180033fdd  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180033fe2  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180033fe7  test    rcx, rcx
0x180033fea  jz      short loc_180034002
0x180033fec  call    cs:__imp_CloseHandle
0x180033ff2  mov     rcx, [rsp+0B8h]; this
0x180033ffa  test    eax, eax
0x180033ffc  jz      loc_180034310
0x180034002  mov     rbx, [rsp+0B8h+hEvent]
0x180034007  mov     rcx, [rsp+0B8h+var_88]; hObject
0x18003400c  test    rcx, rcx
0x18003400f  jz      short loc_180034027
0x180034011  call    cs:__imp_CloseHandle
0x180034017  mov     rcx, [rsp+0B8h]; this
0x18003401f  test    eax, eax
0x180034021  jz      loc_18003431B
0x180034027  mov     rcx, [rsp+0B8h+SecurityDescriptor]; hMem
0x18003402f  test    rcx, rcx
0x180034032  jz      short loc_18003403A
0x180034034  call    cs:__imp_LocalFree
0x18003403a  test    rbx, rbx
0x18003403d  jz      short loc_18003407D
0x18003403f  mov     rcx, rbx; hEvent
0x180034042  call    cs:__imp_SetEvent
0x180034048  mov     rcx, [rsp+0B8h]; this
0x180034050  test    eax, eax
0x180034052  jz      loc_180034326
0x180034058  test    rdi, rdi
0x18003405b  jz      short loc_18003407D
0x18003405d  xor     r8d, r8d; bAlertable
0x180034060  mov     edx, 2710h; dwMilliseconds
0x180034065  mov     rcx, rdi; hHandle
0x180034068  call    cs:__imp_WaitForSingleObjectEx
0x18003406e  cmp     eax, 102h
0x180034073  jz      short loc_18003407D
0x180034075  test    eax, eax
0x180034077  jnz     loc_180034331
0x18003407d  mov     rax, cs:qword_180150778
0x180034084  mov     byte ptr [rax+30h], 1
0x180034088  mov     [rsp+0B8h+var_98], r12
0x18003408d  xor     r9d, r9d
0x180034090  xor     r8d, r8d
0x180034093  xor     edx, edx
0x180034095  mov     rcx, cs:WNF_USO_SERVICE_STOPPING
0x18003409c  call    cs:__imp_RtlPublishWnfStateData
0x1800340a2  call    ?UninitializeService@@YAJXZ; UninitializeService(void)
0x1800340a7  mov     r13d, eax
0x1800340aa  mov     r14, cs:WaitHandle
0x1800340b1  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800340b5  jz      short loc_1800340D5
0x1800340b7  test    r14, r14
0x1800340ba  jz      short loc_1800340D5
0x1800340bc  call    cs:__imp_GetLastError
0x1800340c2  mov     esi, eax
0x1800340c4  mov     rcx, r14; WaitHandle
0x1800340c7  call    cs:__imp_UnregisterWait
0x1800340cd  mov     ecx, esi; dwErrCode
0x1800340cf  call    cs:__imp_SetLastError
0x1800340d5  mov     cs:WaitHandle, 0FFFFFFFFFFFFFFFFh
0x1800340e0  mov     cs:qword_180150118, r12
0x1800340e7  mov     rsi, cs:hObject
0x1800340ee  test    rsi, rsi
0x1800340f1  jz      short loc_18003411E
0x1800340f3  call    cs:__imp_GetLastError
0x1800340f9  mov     r14d, eax
0x1800340fc  mov     rcx, rsi; hObject
0x1800340ff  call    cs:__imp_CloseHandle
0x180034105  mov     rcx, [rsp+0B8h]; this
0x18003410d  test    eax, eax
0x18003410f  jz      loc_180034344
0x180034115  mov     ecx, r14d; dwErrCode
0x180034118  call    cs:__imp_SetLastError
0x18003411e  mov     cs:hObject, r12
0x180034125  lea     rcx, [rsp+0B8h+hObject]
0x18003412a  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003412f  nop
0x180034130  mov     rcx, [rax]
0x180034133  mov     rax, [rcx]
0x180034136  mov     dword ptr [rsp+0B8h+var_88], 3
0x18003413e  lea     rdx, [rsp+0B8h+var_88]
0x180034143  mov     rax, [rax+98h]
0x18003414a  call    _guard_dispatch_icall
0x18003414f  nop
0x180034150  mov     rsi, [rsp+0B8h+var_40]
0x180034155  test    rsi, rsi
0x180034158  jz      short loc_180034191
0x18003415a  or      eax, 0FFFFFFFFh
0x18003415d  lock xadd [rsi+8], eax
0x180034162  cmp     eax, 1
0x180034165  jnz     short loc_180034191
0x180034167  mov     rax, [rsi]
0x18003416a  mov     rcx, rsi
0x18003416d  mov     rax, [rax]
0x180034170  call    _guard_dispatch_icall
0x180034175  or      eax, 0FFFFFFFFh
0x180034178  lock xadd [rsi+0Ch], eax
0x18003417d  cmp     eax, 1
0x180034180  jnz     short loc_180034191
0x180034182  mov     rax, [rsi]
0x180034185  mov     rcx, rsi
0x180034188  mov     rax, [rax+8]
0x18003418c  call    _guard_dispatch_icall
0x180034191  lea     rax, aUsosvcSettingS_0; "UsoSvc setting service state to: SERVIC"...
0x180034198  mov     [rsp+0B8h+hObject], rax
0x18003419d  mov     [rsp+0B8h+var_40], 30h ; '0'
0x1800341a6  lea     rcx, [rsp+0B8h+hObject]
0x1800341ab  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800341b0  mov     r12, cs:?g_loggerMap@@3V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Logger>> g_loggerMap
0x1800341b7  mov     rsi, [r12]
0x1800341bb  jmp     loc_180034258
0x1800341c0  mov     qword ptr [rsi+40h], 0
0x1800341c8  mov     r14, [rsi+48h]
0x1800341cc  mov     qword ptr [rsi+48h], 0
0x1800341d4  test    r14, r14
0x1800341d7  jz      short loc_180034212
0x1800341d9  or      eax, 0FFFFFFFFh
0x1800341dc  lock xadd [r14+8], eax
0x1800341e2  cmp     eax, 1
0x1800341e5  jnz     short loc_180034212
0x1800341e7  mov     rax, [r14]
0x1800341ea  mov     rcx, r14
0x1800341ed  mov     rax, [rax]
0x1800341f0  call    _guard_dispatch_icall
0x1800341f5  or      eax, 0FFFFFFFFh
0x1800341f8  lock xadd [r14+0Ch], eax
0x1800341fe  cmp     eax, 1
0x180034201  jnz     short loc_180034212
0x180034203  mov     rax, [r14]
0x180034206  mov     rcx, r14
0x180034209  mov     rax, [rax+8]
0x18003420d  call    _guard_dispatch_icall
0x180034212  mov     rcx, [rsi+10h]
0x180034216  cmp     byte ptr [rcx+19h], 0
0x18003421a  jz      short loc_18003423D
0x18003421c  mov     rax, [rsi+8]
0x180034220  jmp     short loc_180034232
0x180034222  mov     rcx, rax
0x180034225  cmp     rsi, [rax+10h]
0x180034229  jnz     short loc_180034238
0x18003422b  mov     rax, [rax+8]
0x18003422f  mov     rsi, rcx
0x180034232  cmp     byte ptr [rax+19h], 0
0x180034236  jz      short loc_180034222
0x180034238  mov     rsi, rax
0x18003423b  jmp     short loc_180034258
0x18003423d  mov     rsi, rcx
0x180034240  mov     rcx, [rcx]
0x180034243  cmp     byte ptr [rcx+19h], 0
0x180034247  jnz     short loc_180034258
0x180034249  mov     rsi, rcx
0x18003424c  mov     rax, [rcx]
0x18003424f  mov     rcx, rax
0x180034252  cmp     byte ptr [rax+19h], 0
0x180034256  jz      short loc_180034249
0x180034258  cmp     rsi, r12
0x18003425b  jnz     loc_1800341C0
0x180034261  xor     r8d, r8d; unsigned int
0x180034264  mov     edx, r13d; unsigned int
0x180034267  lea     ecx, [r8+1]; unsigned int
0x18003426b  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x180034270  nop
0x180034271  test    rbx, rbx
0x180034274  jz      short loc_18003428F
0x180034276  mov     rcx, rbx; hObject
0x180034279  call    cs:__imp_CloseHandle
0x18003427f  mov     rcx, [rsp+0B8h]; this
0x180034287  test    eax, eax
0x180034289  jz      loc_18003434F
0x18003428f  test    rdi, rdi
  ... truncated ...
```
