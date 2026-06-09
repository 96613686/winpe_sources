# DeManagementRpcServerRegisterCallbackForIsAutobrightnessCapableChanged

- ea: `0x180015ce0`
- end: `0x180015e3f`
- name: `DeManagementRpcServerRegisterCallbackForIsAutobrightnessCapableChanged`
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
- `0x180015ce0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015d65`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015da9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015da9`

## string_xrefs

- `0x180015d04`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015db3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForIsAutobrightnessCapableChanged(__int64 a1, void *a2)
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
    v4 = 1190;
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
    v4 = 1191;
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
        (void *)0x4B6,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 328))(v12, &v18);
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
                           (void *)0x4B8,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015ce0  mov     [rsp+arg_8], rbx
0x180015ce5  mov     [rsp+arg_18], rsi
0x180015cea  push    rdi
0x180015ceb  sub     rsp, 60h
0x180015cef  mov     rdi, rdx
0x180015cf2  mov     rbx, rcx
0x180015cf5  test    rcx, rcx
0x180015cf8  jnz     short loc_180015D1F
0x180015cfa  mov     edx, 4A6h; void *
0x180015cff  mov     ebx, 80070057h
0x180015d04  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180015d0b  mov     r9d, ebx; char *
0x180015d0e  mov     rcx, [rsp+68h]; this
0x180015d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d18  mov     eax, ebx
0x180015d1a  jmp     loc_180015E2D
0x180015d1f  test    rdi, rdi
0x180015d22  jnz     short loc_180015D2B
0x180015d24  mov     edx, 4A7h
0x180015d29  jmp     short loc_180015CFF
0x180015d2b  lea     rcx, [rsp+68h+var_18]
0x180015d30  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015d35  nop
0x180015d36  mov     rcx, [rsp+68h+var_18]
0x180015d3b  mov     rax, [rcx]
0x180015d3e  mov     r8, rbx
0x180015d41  lea     rdx, [rsp+68h+var_28]
0x180015d46  mov     rax, [rax+18h]
0x180015d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4f  nop
0x180015d50  mov     [rsp+68h+TargetHandle], 0
0x180015d59  xor     edx, edx
0x180015d5b  lea     rcx, [rsp+68h+TargetHandle]
0x180015d60  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015d65  call    cs:__imp_GetCurrentProcess
0x180015d6b  mov     rsi, rax
0x180015d6e  mov     rcx, [rsp+68h+var_28]
0x180015d73  mov     rdx, [rcx]
0x180015d76  mov     rax, [rdx]
0x180015d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d7e  mov     rbx, [rsp+68h]
0x180015d83  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180015d8b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015d93  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180015d9b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015da0  mov     r8, rsi; hTargetProcessHandle
0x180015da3  mov     rdx, rdi; hSourceHandle
0x180015da6  mov     rcx, rax; hSourceProcessHandle
0x180015da9  call    cs:__imp_DuplicateHandle
0x180015daf  test    eax, eax
0x180015db1  jnz     short loc_180015DC7
0x180015db3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180015dba  mov     edx, 4B6h; void *
0x180015dbf  mov     rcx, rbx; this
0x180015dc2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015dc7  mov     rcx, [rsp+68h+var_28]
0x180015dcc  mov     rax, [rcx]
0x180015dcf  mov     rdx, [rsp+68h+TargetHandle]
0x180015dd4  mov     [rsp+68h+arg_10], rdx
0x180015ddc  mov     [rsp+68h+TargetHandle], 0
0x180015de5  lea     rdx, [rsp+68h+arg_10]
0x180015ded  mov     rax, [rax+148h]
0x180015df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df9  nop
0x180015dfa  lea     rcx, [rsp+68h+TargetHandle]
0x180015dff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015e04  nop
0x180015e05  mov     rcx, [rsp+68h+var_20]; this
0x180015e0a  test    rcx, rcx
0x180015e0d  jz      short loc_180015E15
0x180015e0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015e14  nop
0x180015e15  mov     rcx, [rsp+68h+var_10]; this
0x180015e1a  test    rcx, rcx
0x180015e1d  jz      short loc_180015E25
0x180015e1f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015e24  nop
0x180015e25  xor     eax, eax
0x180015e27  jmp     short loc_180015E2D
0x180015e29  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x180015e2d  lea     r11, [rsp+68h+var_8]
0x180015e32  mov     rbx, [r11+18h]
0x180015e36  mov     rsi, [r11+28h]
0x180015e3a  mov     rsp, r11
0x180015e3d  pop     rdi
0x180015e3e  retn
```
