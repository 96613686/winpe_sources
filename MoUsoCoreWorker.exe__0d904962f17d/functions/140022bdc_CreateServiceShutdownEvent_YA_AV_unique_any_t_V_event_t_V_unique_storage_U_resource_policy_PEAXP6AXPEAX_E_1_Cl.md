# ?CreateServiceShutdownEvent@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@XZ

- ea: `0x140022bdc`
- end: `0x140022d6e`
- name: `?CreateServiceShutdownEvent@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@XZ`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400230ec`

## callees

- `0x140022afc`
- `0x140022bdc`
- `0x140040308`
- `0x140040364`
- `0x14004045c`
- `0x140045404`
- `0x140072f48`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022c4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022c4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140022c7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140022c7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140022cd9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140022cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022d14`

## string_xrefs

- `0x140022d4b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall CreateServiceShutdownEvent(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  const char *v4; // r9
  const char *v5; // r9
  __int64 v6; // rax
  wil::details *v7; // rcx
  HANDLE v8; // rdi
  const char *v9; // r9
  _BYTE v12[32]; // [rsp+30h] [rbp-58h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+50h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = a1;
  *a1 = 0;
  if ( g_usoSvcSupportsPrivateNamespaces )
  {
    v2 = (_QWORD *)Windows::PrivateNamespaceHelpers::CreatePrivateNamespaceEvent(&hObject);
    v3 = v2;
    if ( v1 != v2 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v1,
        *v2);
      *v3 = 0;
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
  else
  {
    hObject = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &hObject, 0) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x3B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v5);
    try
    {
      *(_QWORD *)&EventAttributes.nLength = 24;
      *(_QWORD *)&EventAttributes.bInheritHandle = 0;
      EventAttributes.lpSecurityDescriptor = hObject;
      v6 = GlobalObjectName(v12, L"\\UsoCoreWorkerRequestShutdown");
      if ( *(_QWORD *)(v6 + 24) > 7u )
        v6 = *(_QWORD *)v6;
      v8 = CreateEventExW(&EventAttributes, (LPCWSTR)v6, 1u, 0x1F0003u);
      if ( v8 )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          v1,
          v8);
      }
      else
      {
        wil::details::GetLastErrorFailHr(v7);
      }
      std::wstring::~wstring(v12);
      if ( hObject )
        LocalFree(hObject);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x42,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v9);
      return a1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140022bdc  mov     [rsp+arg_8], rbx
0x140022be1  push    rdi
0x140022be2  sub     rsp, 80h
0x140022be9  mov     rax, cs:__security_cookie
0x140022bf0  xor     rax, rsp
0x140022bf3  mov     [rsp+88h+var_18], rax
0x140022bf8  mov     rbx, rcx
0x140022bfb  mov     [rsp+88h+var_60], rcx
0x140022c00  mov     [rsp+88h+var_68], 0
0x140022c08  xor     eax, eax
0x140022c0a  mov     [rcx], rax
0x140022c0d  lea     edi, [rax+1]
0x140022c10  mov     [rsp+88h+var_68], edi
0x140022c14  cmp     cs:?g_usoSvcSupportsPrivateNamespaces@@3_NA, al; bool g_usoSvcSupportsPrivateNamespaces
0x140022c1a  jz      short loc_140022C61
0x140022c1c  lea     rcx, [rsp+88h+hObject]
0x140022c21  call    ?CreatePrivateNamespaceEvent@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WW4EventOptions@4@PEA_N@Z
0x140022c26  mov     rdi, rax
0x140022c29  cmp     rbx, rax
0x140022c2c  jz      short loc_140022C40
0x140022c2e  mov     rdx, [rax]
0x140022c31  mov     rcx, rbx
0x140022c34  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140022c39  mov     qword ptr [rdi], 0
0x140022c40  mov     rcx, [rsp+88h+hObject]; hObject
0x140022c45  test    rcx, rcx
0x140022c48  jz      loc_140022D22
0x140022c4e  call    cs:__imp_CloseHandle
0x140022c54  test    eax, eax
0x140022c56  jz      loc_140022D43
0x140022c5c  jmp     loc_140022D22
0x140022c61  mov     [rsp+88h+hObject], 0
0x140022c6a  xor     r9d, r9d; SecurityDescriptorSize
0x140022c6d  lea     r8, [rsp+88h+hObject]; SecurityDescriptor
0x140022c72  mov     edx, edi; StringSDRevision
0x140022c74  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x140022c7b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140022c81  mov     rcx, [rsp+88h]; this
0x140022c89  test    eax, eax
0x140022c8b  jz      loc_140022D5D
0x140022c91  mov     qword ptr [rsp+88h+EventAttributes.nLength], 18h
0x140022c9a  mov     qword ptr [rsp+88h+EventAttributes.bInheritHandle], 0
0x140022ca3  mov     rax, [rsp+88h+hObject]
0x140022ca8  mov     [rsp+88h+EventAttributes.lpSecurityDescriptor], rax
0x140022cad  lea     rdx, aUsocoreworkerr; "\\UsoCoreWorkerRequestShutdown"
0x140022cb4  lea     rcx, [rsp+88h+var_58]; void *
0x140022cb9  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x140022cbe  cmp     qword ptr [rax+18h], 7
0x140022cc3  jbe     short loc_140022CC8
0x140022cc5  mov     rax, [rax]
0x140022cc8  mov     r9d, 1F0003h; dwDesiredAccess
0x140022cce  mov     r8d, edi; dwFlags
0x140022cd1  mov     rdx, rax; lpName
0x140022cd4  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x140022cd9  call    cs:__imp_CreateEventExW
0x140022cdf  mov     rdi, rax
0x140022ce2  test    rax, rax
0x140022ce5  jz      short loc_140022CFA
0x140022ce7  call    cs:__imp_GetLastError
0x140022ced  mov     rdx, rdi
0x140022cf0  mov     rcx, rbx
0x140022cf3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140022cf8  jmp     short loc_140022CFF
0x140022cfa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140022cff  lea     rcx, [rsp+88h+var_58]
0x140022d04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140022d09  nop
0x140022d0a  mov     rcx, [rsp+88h+hObject]; hMem
0x140022d0f  test    rcx, rcx
0x140022d12  jz      short loc_140022D1B
0x140022d14  call    cs:__imp_LocalFree
0x140022d1a  nop
0x140022d1b  jmp     short loc_140022D22
0x140022d1d  mov     rbx, [rsp+88h+var_60]
0x140022d22  mov     rax, rbx
0x140022d25  mov     rcx, [rsp+88h+var_18]
0x140022d2a  xor     rcx, rsp; StackCookie
0x140022d2d  call    __security_check_cookie
0x140022d32  mov     rbx, [rsp+88h+arg_8]
0x140022d3a  add     rsp, 80h
0x140022d41  pop     rdi
0x140022d42  retn
0x140022d43  mov     rcx, [rsp+88h]; this
0x140022d4b  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140022d52  mov     edx, 9D1h; void *
0x140022d57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140022d5d  lea     r8, aCW1SSrcOrchest_62; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140022d64  lea     edx, [rax+3Bh]; void *
0x140022d67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
