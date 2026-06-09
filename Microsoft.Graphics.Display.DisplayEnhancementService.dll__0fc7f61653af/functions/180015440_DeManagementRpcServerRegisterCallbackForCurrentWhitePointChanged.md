# DeManagementRpcServerRegisterCallbackForCurrentWhitePointChanged

- ea: `0x180015440`
- end: `0x18001559f`
- name: `DeManagementRpcServerRegisterCallbackForCurrentWhitePointChanged`
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
- `0x180015440`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800154c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800154c5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015509`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015509`

## string_xrefs

- `0x180015464`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015513`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForCurrentWhitePointChanged(__int64 a1, void *a2)
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
    v4 = 768;
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
    v4 = 769;
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
        (void *)0x310,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 136))(v12, &v18);
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
                           (void *)0x312,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015440  mov     [rsp+arg_8], rbx
0x180015445  mov     [rsp+arg_18], rsi
0x18001544a  push    rdi
0x18001544b  sub     rsp, 60h
0x18001544f  mov     rdi, rdx
0x180015452  mov     rbx, rcx
0x180015455  test    rcx, rcx
0x180015458  jnz     short loc_18001547F
0x18001545a  mov     edx, 300h; void *
0x18001545f  mov     ebx, 80070057h
0x180015464  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001546b  mov     r9d, ebx; char *
0x18001546e  mov     rcx, [rsp+68h]; this
0x180015473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015478  mov     eax, ebx
0x18001547a  jmp     loc_18001558D
0x18001547f  test    rdi, rdi
0x180015482  jnz     short loc_18001548B
0x180015484  mov     edx, 301h
0x180015489  jmp     short loc_18001545F
0x18001548b  lea     rcx, [rsp+68h+var_18]
0x180015490  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015495  nop
0x180015496  mov     rcx, [rsp+68h+var_18]
0x18001549b  mov     rax, [rcx]
0x18001549e  mov     r8, rbx
0x1800154a1  lea     rdx, [rsp+68h+var_28]
0x1800154a6  mov     rax, [rax+18h]
0x1800154aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154af  nop
0x1800154b0  mov     [rsp+68h+TargetHandle], 0
0x1800154b9  xor     edx, edx
0x1800154bb  lea     rcx, [rsp+68h+TargetHandle]
0x1800154c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800154c5  call    cs:__imp_GetCurrentProcess
0x1800154cb  mov     rsi, rax
0x1800154ce  mov     rcx, [rsp+68h+var_28]
0x1800154d3  mov     rdx, [rcx]
0x1800154d6  mov     rax, [rdx]
0x1800154d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154de  mov     rbx, [rsp+68h]
0x1800154e3  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800154eb  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1800154f3  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x1800154fb  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015500  mov     r8, rsi; hTargetProcessHandle
0x180015503  mov     rdx, rdi; hSourceHandle
0x180015506  mov     rcx, rax; hSourceProcessHandle
0x180015509  call    cs:__imp_DuplicateHandle
0x18001550f  test    eax, eax
0x180015511  jnz     short loc_180015527
0x180015513  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001551a  mov     edx, 310h; void *
0x18001551f  mov     rcx, rbx; this
0x180015522  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015527  mov     rcx, [rsp+68h+var_28]
0x18001552c  mov     rax, [rcx]
0x18001552f  mov     rdx, [rsp+68h+TargetHandle]
0x180015534  mov     [rsp+68h+arg_10], rdx
0x18001553c  mov     [rsp+68h+TargetHandle], 0
0x180015545  lea     rdx, [rsp+68h+arg_10]
0x18001554d  mov     rax, [rax+88h]
0x180015554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015559  nop
0x18001555a  lea     rcx, [rsp+68h+TargetHandle]
0x18001555f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015564  nop
0x180015565  mov     rcx, [rsp+68h+var_20]; this
0x18001556a  test    rcx, rcx
0x18001556d  jz      short loc_180015575
0x18001556f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015574  nop
0x180015575  mov     rcx, [rsp+68h+var_10]; this
0x18001557a  test    rcx, rcx
0x18001557d  jz      short loc_180015585
0x18001557f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015584  nop
0x180015585  xor     eax, eax
0x180015587  jmp     short loc_18001558D
0x180015589  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x18001558d  lea     r11, [rsp+68h+var_8]
0x180015592  mov     rbx, [r11+18h]
0x180015596  mov     rsi, [r11+28h]
0x18001559a  mov     rsp, r11
0x18001559d  pop     rdi
0x18001559e  retn
```
