# DeManagementRpcServerRegisterCallbackForBrightnessHotkeysChanged

- ea: `0x180015160`
- end: `0x1800152bf`
- name: `DeManagementRpcServerRegisterCallbackForBrightnessHotkeysChanged`
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
- `0x180015160`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800151e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800151e5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015229`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015229`

## string_xrefs

- `0x180015184`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015233`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForBrightnessHotkeysChanged(__int64 a1, void *a2)
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
    v4 = 1539;
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
    v4 = 1540;
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
        (void *)0x613,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 600))(v12, &v18);
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
                           (void *)0x615,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015160  mov     [rsp+arg_8], rbx
0x180015165  mov     [rsp+arg_18], rsi
0x18001516a  push    rdi
0x18001516b  sub     rsp, 60h
0x18001516f  mov     rdi, rdx
0x180015172  mov     rbx, rcx
0x180015175  test    rcx, rcx
0x180015178  jnz     short loc_18001519F
0x18001517a  mov     edx, 603h; void *
0x18001517f  mov     ebx, 80070057h
0x180015184  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001518b  mov     r9d, ebx; char *
0x18001518e  mov     rcx, [rsp+68h]; this
0x180015193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015198  mov     eax, ebx
0x18001519a  jmp     loc_1800152AD
0x18001519f  test    rdi, rdi
0x1800151a2  jnz     short loc_1800151AB
0x1800151a4  mov     edx, 604h
0x1800151a9  jmp     short loc_18001517F
0x1800151ab  lea     rcx, [rsp+68h+var_18]
0x1800151b0  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x1800151b5  nop
0x1800151b6  mov     rcx, [rsp+68h+var_18]
0x1800151bb  mov     rax, [rcx]
0x1800151be  mov     r8, rbx
0x1800151c1  lea     rdx, [rsp+68h+var_28]
0x1800151c6  mov     rax, [rax+18h]
0x1800151ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151cf  nop
0x1800151d0  mov     [rsp+68h+TargetHandle], 0
0x1800151d9  xor     edx, edx
0x1800151db  lea     rcx, [rsp+68h+TargetHandle]
0x1800151e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800151e5  call    cs:__imp_GetCurrentProcess
0x1800151eb  mov     rsi, rax
0x1800151ee  mov     rcx, [rsp+68h+var_28]
0x1800151f3  mov     rdx, [rcx]
0x1800151f6  mov     rax, [rdx]
0x1800151f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151fe  mov     rbx, [rsp+68h]
0x180015203  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001520b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015213  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18001521b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015220  mov     r8, rsi; hTargetProcessHandle
0x180015223  mov     rdx, rdi; hSourceHandle
0x180015226  mov     rcx, rax; hSourceProcessHandle
0x180015229  call    cs:__imp_DuplicateHandle
0x18001522f  test    eax, eax
0x180015231  jnz     short loc_180015247
0x180015233  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001523a  mov     edx, 613h; void *
0x18001523f  mov     rcx, rbx; this
0x180015242  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015247  mov     rcx, [rsp+68h+var_28]
0x18001524c  mov     rax, [rcx]
0x18001524f  mov     rdx, [rsp+68h+TargetHandle]
0x180015254  mov     [rsp+68h+arg_10], rdx
0x18001525c  mov     [rsp+68h+TargetHandle], 0
0x180015265  lea     rdx, [rsp+68h+arg_10]
0x18001526d  mov     rax, [rax+258h]
0x180015274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015279  nop
0x18001527a  lea     rcx, [rsp+68h+TargetHandle]
0x18001527f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015284  nop
0x180015285  mov     rcx, [rsp+68h+var_20]; this
0x18001528a  test    rcx, rcx
0x18001528d  jz      short loc_180015295
0x18001528f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015294  nop
0x180015295  mov     rcx, [rsp+68h+var_10]; this
0x18001529a  test    rcx, rcx
0x18001529d  jz      short loc_1800152A5
0x18001529f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800152a4  nop
0x1800152a5  xor     eax, eax
0x1800152a7  jmp     short loc_1800152AD
0x1800152a9  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x1800152ad  lea     r11, [rsp+68h+var_8]
0x1800152b2  mov     rbx, [r11+18h]
0x1800152b6  mov     rsi, [r11+28h]
0x1800152ba  mov     rsp, r11
0x1800152bd  pop     rdi
0x1800152be  retn
```
