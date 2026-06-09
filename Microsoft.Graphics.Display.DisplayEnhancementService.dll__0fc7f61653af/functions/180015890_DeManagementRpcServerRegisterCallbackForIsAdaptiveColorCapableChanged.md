# DeManagementRpcServerRegisterCallbackForIsAdaptiveColorCapableChanged

- ea: `0x180015890`
- end: `0x1800159ef`
- name: `DeManagementRpcServerRegisterCallbackForIsAdaptiveColorCapableChanged`
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
- `0x180015890`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015915`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015959`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015959`

## string_xrefs

- `0x1800158b4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015963`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForIsAdaptiveColorCapableChanged(__int64 a1, void *a2)
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
    v4 = 534;
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
    v4 = 535;
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
        (void *)0x226,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 168))(v12, &v18);
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
                           (void *)0x228,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015890  mov     [rsp+arg_8], rbx
0x180015895  mov     [rsp+arg_18], rsi
0x18001589a  push    rdi
0x18001589b  sub     rsp, 60h
0x18001589f  mov     rdi, rdx
0x1800158a2  mov     rbx, rcx
0x1800158a5  test    rcx, rcx
0x1800158a8  jnz     short loc_1800158CF
0x1800158aa  mov     edx, 216h; void *
0x1800158af  mov     ebx, 80070057h
0x1800158b4  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800158bb  mov     r9d, ebx; char *
0x1800158be  mov     rcx, [rsp+68h]; this
0x1800158c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800158c8  mov     eax, ebx
0x1800158ca  jmp     loc_1800159DD
0x1800158cf  test    rdi, rdi
0x1800158d2  jnz     short loc_1800158DB
0x1800158d4  mov     edx, 217h
0x1800158d9  jmp     short loc_1800158AF
0x1800158db  lea     rcx, [rsp+68h+var_18]
0x1800158e0  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x1800158e5  nop
0x1800158e6  mov     rcx, [rsp+68h+var_18]
0x1800158eb  mov     rax, [rcx]
0x1800158ee  mov     r8, rbx
0x1800158f1  lea     rdx, [rsp+68h+var_28]
0x1800158f6  mov     rax, [rax+18h]
0x1800158fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ff  nop
0x180015900  mov     [rsp+68h+TargetHandle], 0
0x180015909  xor     edx, edx
0x18001590b  lea     rcx, [rsp+68h+TargetHandle]
0x180015910  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015915  call    cs:__imp_GetCurrentProcess
0x18001591b  mov     rsi, rax
0x18001591e  mov     rcx, [rsp+68h+var_28]
0x180015923  mov     rdx, [rcx]
0x180015926  mov     rax, [rdx]
0x180015929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001592e  mov     rbx, [rsp+68h]
0x180015933  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001593b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015943  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18001594b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015950  mov     r8, rsi; hTargetProcessHandle
0x180015953  mov     rdx, rdi; hSourceHandle
0x180015956  mov     rcx, rax; hSourceProcessHandle
0x180015959  call    cs:__imp_DuplicateHandle
0x18001595f  test    eax, eax
0x180015961  jnz     short loc_180015977
0x180015963  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001596a  mov     edx, 226h; void *
0x18001596f  mov     rcx, rbx; this
0x180015972  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015977  mov     rcx, [rsp+68h+var_28]
0x18001597c  mov     rax, [rcx]
0x18001597f  mov     rdx, [rsp+68h+TargetHandle]
0x180015984  mov     [rsp+68h+arg_10], rdx
0x18001598c  mov     [rsp+68h+TargetHandle], 0
0x180015995  lea     rdx, [rsp+68h+arg_10]
0x18001599d  mov     rax, [rax+0A8h]
0x1800159a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a9  nop
0x1800159aa  lea     rcx, [rsp+68h+TargetHandle]
0x1800159af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800159b4  nop
0x1800159b5  mov     rcx, [rsp+68h+var_20]; this
0x1800159ba  test    rcx, rcx
0x1800159bd  jz      short loc_1800159C5
0x1800159bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800159c4  nop
0x1800159c5  mov     rcx, [rsp+68h+var_10]; this
0x1800159ca  test    rcx, rcx
0x1800159cd  jz      short loc_1800159D5
0x1800159cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800159d4  nop
0x1800159d5  xor     eax, eax
0x1800159d7  jmp     short loc_1800159DD
0x1800159d9  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x1800159dd  lea     r11, [rsp+68h+var_8]
0x1800159e2  mov     rbx, [r11+18h]
0x1800159e6  mov     rsi, [r11+28h]
0x1800159ea  mov     rsp, r11
0x1800159ed  pop     rdi
0x1800159ee  retn
```
