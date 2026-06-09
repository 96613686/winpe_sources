# DeManagementRpcServerRegisterCallbackForAmbientLightSensorDeviceIdChanged

- ea: `0x180014e80`
- end: `0x180014fdf`
- name: `DeManagementRpcServerRegisterCallbackForAmbientLightSensorDeviceIdChanged`
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
- `0x180014e80`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f05`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014f49`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014f49`

## string_xrefs

- `0x180014ea4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180014f53`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForAmbientLightSensorDeviceIdChanged(__int64 a1, void *a2)
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
    v4 = 1696;
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
    v4 = 1697;
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
        (void *)0x6B0,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 728))(v12, &v18);
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
                           (void *)0x6B2,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014e80  mov     [rsp+arg_8], rbx
0x180014e85  mov     [rsp+arg_18], rsi
0x180014e8a  push    rdi
0x180014e8b  sub     rsp, 60h
0x180014e8f  mov     rdi, rdx
0x180014e92  mov     rbx, rcx
0x180014e95  test    rcx, rcx
0x180014e98  jnz     short loc_180014EBF
0x180014e9a  mov     edx, 6A0h; void *
0x180014e9f  mov     ebx, 80070057h
0x180014ea4  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180014eab  mov     r9d, ebx; char *
0x180014eae  mov     rcx, [rsp+68h]; this
0x180014eb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014eb8  mov     eax, ebx
0x180014eba  jmp     loc_180014FCD
0x180014ebf  test    rdi, rdi
0x180014ec2  jnz     short loc_180014ECB
0x180014ec4  mov     edx, 6A1h
0x180014ec9  jmp     short loc_180014E9F
0x180014ecb  lea     rcx, [rsp+68h+var_18]
0x180014ed0  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180014ed5  nop
0x180014ed6  mov     rcx, [rsp+68h+var_18]
0x180014edb  mov     rax, [rcx]
0x180014ede  mov     r8, rbx
0x180014ee1  lea     rdx, [rsp+68h+var_28]
0x180014ee6  mov     rax, [rax+18h]
0x180014eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eef  nop
0x180014ef0  mov     [rsp+68h+TargetHandle], 0
0x180014ef9  xor     edx, edx
0x180014efb  lea     rcx, [rsp+68h+TargetHandle]
0x180014f00  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180014f05  call    cs:__imp_GetCurrentProcess
0x180014f0b  mov     rsi, rax
0x180014f0e  mov     rcx, [rsp+68h+var_28]
0x180014f13  mov     rdx, [rcx]
0x180014f16  mov     rax, [rdx]
0x180014f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f1e  mov     rbx, [rsp+68h]
0x180014f23  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180014f2b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180014f33  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180014f3b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180014f40  mov     r8, rsi; hTargetProcessHandle
0x180014f43  mov     rdx, rdi; hSourceHandle
0x180014f46  mov     rcx, rax; hSourceProcessHandle
0x180014f49  call    cs:__imp_DuplicateHandle
0x180014f4f  test    eax, eax
0x180014f51  jnz     short loc_180014F67
0x180014f53  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180014f5a  mov     edx, 6B0h; void *
0x180014f5f  mov     rcx, rbx; this
0x180014f62  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180014f67  mov     rcx, [rsp+68h+var_28]
0x180014f6c  mov     rax, [rcx]
0x180014f6f  mov     rdx, [rsp+68h+TargetHandle]
0x180014f74  mov     [rsp+68h+arg_10], rdx
0x180014f7c  mov     [rsp+68h+TargetHandle], 0
0x180014f85  lea     rdx, [rsp+68h+arg_10]
0x180014f8d  mov     rax, [rax+2D8h]
0x180014f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f99  nop
0x180014f9a  lea     rcx, [rsp+68h+TargetHandle]
0x180014f9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014fa4  nop
0x180014fa5  mov     rcx, [rsp+68h+var_20]; this
0x180014faa  test    rcx, rcx
0x180014fad  jz      short loc_180014FB5
0x180014faf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014fb4  nop
0x180014fb5  mov     rcx, [rsp+68h+var_10]; this
0x180014fba  test    rcx, rcx
0x180014fbd  jz      short loc_180014FC5
0x180014fbf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014fc4  nop
0x180014fc5  xor     eax, eax
0x180014fc7  jmp     short loc_180014FCD
0x180014fc9  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x180014fcd  lea     r11, [rsp+68h+var_8]
0x180014fd2  mov     rbx, [r11+18h]
0x180014fd6  mov     rsi, [r11+28h]
0x180014fda  mov     rsp, r11
0x180014fdd  pop     rdi
0x180014fde  retn
```
