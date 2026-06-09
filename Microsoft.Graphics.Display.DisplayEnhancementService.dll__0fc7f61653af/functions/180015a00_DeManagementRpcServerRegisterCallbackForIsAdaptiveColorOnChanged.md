# DeManagementRpcServerRegisterCallbackForIsAdaptiveColorOnChanged

- ea: `0x180015a00`
- end: `0x180015b5f`
- name: `DeManagementRpcServerRegisterCallbackForIsAdaptiveColorOnChanged`
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
- `0x180015a00`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015a85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015a85`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015ac9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015ac9`

## string_xrefs

- `0x180015a24`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015ad3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForIsAdaptiveColorOnChanged(__int64 a1, void *a2)
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
    v4 = 573;
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
    v4 = 574;
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
        (void *)0x24D,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 232))(v12, &v18);
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
                           (void *)0x24F,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015a00  mov     [rsp+arg_8], rbx
0x180015a05  mov     [rsp+arg_18], rsi
0x180015a0a  push    rdi
0x180015a0b  sub     rsp, 60h
0x180015a0f  mov     rdi, rdx
0x180015a12  mov     rbx, rcx
0x180015a15  test    rcx, rcx
0x180015a18  jnz     short loc_180015A3F
0x180015a1a  mov     edx, 23Dh; void *
0x180015a1f  mov     ebx, 80070057h
0x180015a24  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180015a2b  mov     r9d, ebx; char *
0x180015a2e  mov     rcx, [rsp+68h]; this
0x180015a33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a38  mov     eax, ebx
0x180015a3a  jmp     loc_180015B4D
0x180015a3f  test    rdi, rdi
0x180015a42  jnz     short loc_180015A4B
0x180015a44  mov     edx, 23Eh
0x180015a49  jmp     short loc_180015A1F
0x180015a4b  lea     rcx, [rsp+68h+var_18]
0x180015a50  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015a55  nop
0x180015a56  mov     rcx, [rsp+68h+var_18]
0x180015a5b  mov     rax, [rcx]
0x180015a5e  mov     r8, rbx
0x180015a61  lea     rdx, [rsp+68h+var_28]
0x180015a66  mov     rax, [rax+18h]
0x180015a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6f  nop
0x180015a70  mov     [rsp+68h+TargetHandle], 0
0x180015a79  xor     edx, edx
0x180015a7b  lea     rcx, [rsp+68h+TargetHandle]
0x180015a80  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015a85  call    cs:__imp_GetCurrentProcess
0x180015a8b  mov     rsi, rax
0x180015a8e  mov     rcx, [rsp+68h+var_28]
0x180015a93  mov     rdx, [rcx]
0x180015a96  mov     rax, [rdx]
0x180015a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a9e  mov     rbx, [rsp+68h]
0x180015aa3  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180015aab  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015ab3  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180015abb  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015ac0  mov     r8, rsi; hTargetProcessHandle
0x180015ac3  mov     rdx, rdi; hSourceHandle
0x180015ac6  mov     rcx, rax; hSourceProcessHandle
0x180015ac9  call    cs:__imp_DuplicateHandle
0x180015acf  test    eax, eax
0x180015ad1  jnz     short loc_180015AE7
0x180015ad3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180015ada  mov     edx, 24Dh; void *
0x180015adf  mov     rcx, rbx; this
0x180015ae2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015ae7  mov     rcx, [rsp+68h+var_28]
0x180015aec  mov     rax, [rcx]
0x180015aef  mov     rdx, [rsp+68h+TargetHandle]
0x180015af4  mov     [rsp+68h+arg_10], rdx
0x180015afc  mov     [rsp+68h+TargetHandle], 0
0x180015b05  lea     rdx, [rsp+68h+arg_10]
0x180015b0d  mov     rax, [rax+0E8h]
0x180015b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b19  nop
0x180015b1a  lea     rcx, [rsp+68h+TargetHandle]
0x180015b1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015b24  nop
0x180015b25  mov     rcx, [rsp+68h+var_20]; this
0x180015b2a  test    rcx, rcx
0x180015b2d  jz      short loc_180015B35
0x180015b2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015b34  nop
0x180015b35  mov     rcx, [rsp+68h+var_10]; this
0x180015b3a  test    rcx, rcx
0x180015b3d  jz      short loc_180015B45
0x180015b3f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015b44  nop
0x180015b45  xor     eax, eax
0x180015b47  jmp     short loc_180015B4D
0x180015b49  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x180015b4d  lea     r11, [rsp+68h+var_8]
0x180015b52  mov     rbx, [r11+18h]
0x180015b56  mov     rsi, [r11+28h]
0x180015b5a  mov     rsp, r11
0x180015b5d  pop     rdi
0x180015b5e  retn
```
