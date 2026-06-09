# DeManagementRpcServerRegisterCallbackForColorLightSensorDeviceIdChanged

- ea: `0x1800152d0`
- end: `0x18001542f`
- name: `DeManagementRpcServerRegisterCallbackForColorLightSensorDeviceIdChanged`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009b3c`
- `0x18000decc`
- `0x18000f778`
- `0x18000f9f0`
- `0x18000ffe0`
- `0x180012ccc`
- `0x1800152d0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015355`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015399`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015399`

## string_xrefs

- `0x1800152f4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x1800153a3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForColorLightSensorDeviceIdChanged(__int64 a1, void *a2)
{
  __int64 v4; // rdx
  __int64 result; // rax
  HANDLE CurrentProcess; // rsi
  void *v7; // rax
  const char *v8; // r9
  __int64 v9; // rax
  const char *v10; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-48h]
  _QWORD *v12; // [rsp+40h] [rbp-28h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE v18; // [rsp+80h] [rbp+18h] BYREF

  if ( !a1 )
  {
    v4 = 729;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)0x80070057LL,
      dwDesiredAccess);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v4 = 730;
    goto LABEL_3;
  }
  try
  {
    Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(&v14);
    (*(void (__fastcall **)(__int64, _QWORD **, __int64))(*(_QWORD *)v14 + 24LL))(v14, &v12, a1);
    TargetHandle = 0;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &TargetHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    v7 = (void *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))*v12)(v12, *v12);
    if ( !DuplicateHandle(v7, a2, CurrentProcess, &TargetHandle, 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 760))(v12, &v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2EB,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800152d0  mov     [rsp+arg_8], rbx
0x1800152d5  mov     [rsp+arg_18], rsi
0x1800152da  push    rdi
0x1800152db  sub     rsp, 60h
0x1800152df  mov     rdi, rdx
0x1800152e2  mov     rbx, rcx
0x1800152e5  test    rcx, rcx
0x1800152e8  jnz     short loc_18001530F
0x1800152ea  mov     edx, 2D9h; void *
0x1800152ef  mov     ebx, 80070057h
0x1800152f4  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800152fb  mov     r9d, ebx; char *
0x1800152fe  mov     rcx, [rsp+68h]; this
0x180015303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015308  mov     eax, ebx
0x18001530a  jmp     loc_18001541D
0x18001530f  test    rdi, rdi
0x180015312  jnz     short loc_18001531B
0x180015314  mov     edx, 2DAh
0x180015319  jmp     short loc_1800152EF
0x18001531b  lea     rcx, [rsp+68h+var_18]
0x180015320  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015325  nop
0x180015326  mov     rcx, [rsp+68h+var_18]
0x18001532b  mov     rax, [rcx]
0x18001532e  mov     r8, rbx
0x180015331  lea     rdx, [rsp+68h+var_28]
0x180015336  mov     rax, [rax+18h]
0x18001533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001533f  nop
0x180015340  mov     [rsp+68h+TargetHandle], 0
0x180015349  xor     edx, edx
0x18001534b  lea     rcx, [rsp+68h+TargetHandle]
0x180015350  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015355  call    cs:__imp_GetCurrentProcess
0x18001535b  mov     rsi, rax
0x18001535e  mov     rcx, [rsp+68h+var_28]
0x180015363  mov     rdx, [rcx]
0x180015366  mov     rax, [rdx]
0x180015369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001536e  mov     rbx, [rsp+68h]
0x180015373  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001537b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015383  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18001538b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015390  mov     r8, rsi; hTargetProcessHandle
0x180015393  mov     rdx, rdi; hSourceHandle
0x180015396  mov     rcx, rax; hSourceProcessHandle
0x180015399  call    cs:__imp_DuplicateHandle
0x18001539f  test    eax, eax
0x1800153a1  jnz     short loc_1800153B7
0x1800153a3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800153aa  mov     edx, 2E9h; void *
0x1800153af  mov     rcx, rbx; this
0x1800153b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800153b7  mov     rcx, [rsp+68h+var_28]
0x1800153bc  mov     rax, [rcx]
0x1800153bf  mov     rdx, [rsp+68h+TargetHandle]
0x1800153c4  mov     [rsp+68h+arg_10], rdx
0x1800153cc  mov     [rsp+68h+TargetHandle], 0
0x1800153d5  lea     rdx, [rsp+68h+arg_10]
0x1800153dd  mov     rax, [rax+2F8h]
0x1800153e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e9  nop
0x1800153ea  lea     rcx, [rsp+68h+TargetHandle]
0x1800153ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800153f4  nop
0x1800153f5  mov     rcx, [rsp+68h+var_20]; this
0x1800153fa  test    rcx, rcx
0x1800153fd  jz      short loc_180015405
0x1800153ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015404  nop
0x180015405  mov     rcx, [rsp+68h+var_10]; this
0x18001540a  test    rcx, rcx
0x18001540d  jz      short loc_180015415
0x18001540f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015414  nop
0x180015415  xor     eax, eax
0x180015417  jmp     short loc_18001541D
0x180015419  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x18001541d  lea     r11, [rsp+68h+var_8]
0x180015422  mov     rbx, [r11+18h]
0x180015426  mov     rsi, [r11+28h]
0x18001542a  mov     rsp, r11
0x18001542d  pop     rdi
0x18001542e  retn
```
