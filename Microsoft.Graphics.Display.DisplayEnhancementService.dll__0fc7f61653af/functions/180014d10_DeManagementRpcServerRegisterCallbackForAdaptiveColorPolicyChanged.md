# DeManagementRpcServerRegisterCallbackForAdaptiveColorPolicyChanged

- ea: `0x180014d10`
- end: `0x180014e6f`
- name: `DeManagementRpcServerRegisterCallbackForAdaptiveColorPolicyChanged`
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
- `0x180014d10`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d95`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014dd9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014dd9`

## string_xrefs

- `0x180014d34`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180014de3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForAdaptiveColorPolicyChanged(__int64 a1, void *a2)
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
    v4 = 651;
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
    v4 = 652;
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
        (void *)0x29B,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 784))(v12, &v18);
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
                           (void *)0x29D,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014d10  mov     [rsp+arg_8], rbx
0x180014d15  mov     [rsp+arg_18], rsi
0x180014d1a  push    rdi
0x180014d1b  sub     rsp, 60h
0x180014d1f  mov     rdi, rdx
0x180014d22  mov     rbx, rcx
0x180014d25  test    rcx, rcx
0x180014d28  jnz     short loc_180014D4F
0x180014d2a  mov     edx, 28Bh; void *
0x180014d2f  mov     ebx, 80070057h
0x180014d34  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180014d3b  mov     r9d, ebx; char *
0x180014d3e  mov     rcx, [rsp+68h]; this
0x180014d43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d48  mov     eax, ebx
0x180014d4a  jmp     loc_180014E5D
0x180014d4f  test    rdi, rdi
0x180014d52  jnz     short loc_180014D5B
0x180014d54  mov     edx, 28Ch
0x180014d59  jmp     short loc_180014D2F
0x180014d5b  lea     rcx, [rsp+68h+var_18]
0x180014d60  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180014d65  nop
0x180014d66  mov     rcx, [rsp+68h+var_18]
0x180014d6b  mov     rax, [rcx]
0x180014d6e  mov     r8, rbx
0x180014d71  lea     rdx, [rsp+68h+var_28]
0x180014d76  mov     rax, [rax+18h]
0x180014d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d7f  nop
0x180014d80  mov     [rsp+68h+TargetHandle], 0
0x180014d89  xor     edx, edx
0x180014d8b  lea     rcx, [rsp+68h+TargetHandle]
0x180014d90  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180014d95  call    cs:__imp_GetCurrentProcess
0x180014d9b  mov     rsi, rax
0x180014d9e  mov     rcx, [rsp+68h+var_28]
0x180014da3  mov     rdx, [rcx]
0x180014da6  mov     rax, [rdx]
0x180014da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dae  mov     rbx, [rsp+68h]
0x180014db3  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180014dbb  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180014dc3  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180014dcb  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180014dd0  mov     r8, rsi; hTargetProcessHandle
0x180014dd3  mov     rdx, rdi; hSourceHandle
0x180014dd6  mov     rcx, rax; hSourceProcessHandle
0x180014dd9  call    cs:__imp_DuplicateHandle
0x180014ddf  test    eax, eax
0x180014de1  jnz     short loc_180014DF7
0x180014de3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180014dea  mov     edx, 29Bh; void *
0x180014def  mov     rcx, rbx; this
0x180014df2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180014df7  mov     rcx, [rsp+68h+var_28]
0x180014dfc  mov     rax, [rcx]
0x180014dff  mov     rdx, [rsp+68h+TargetHandle]
0x180014e04  mov     [rsp+68h+arg_10], rdx
0x180014e0c  mov     [rsp+68h+TargetHandle], 0
0x180014e15  lea     rdx, [rsp+68h+arg_10]
0x180014e1d  mov     rax, [rax+310h]
0x180014e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e29  nop
0x180014e2a  lea     rcx, [rsp+68h+TargetHandle]
0x180014e2f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014e34  nop
0x180014e35  mov     rcx, [rsp+68h+var_20]; this
0x180014e3a  test    rcx, rcx
0x180014e3d  jz      short loc_180014E45
0x180014e3f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014e44  nop
0x180014e45  mov     rcx, [rsp+68h+var_10]; this
0x180014e4a  test    rcx, rcx
0x180014e4d  jz      short loc_180014E55
0x180014e4f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014e54  nop
0x180014e55  xor     eax, eax
0x180014e57  jmp     short loc_180014E5D
0x180014e59  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x180014e5d  lea     r11, [rsp+68h+var_8]
0x180014e62  mov     rbx, [r11+18h]
0x180014e66  mov     rsi, [r11+28h]
0x180014e6a  mov     rsp, r11
0x180014e6d  pop     rdi
0x180014e6e  retn
```
