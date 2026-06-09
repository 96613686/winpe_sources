# DeManagementRpcServerRegisterCallbackForIsAdaptiveColorAdaptationStrengthChanged

- ea: `0x180015720`
- end: `0x18001587f`
- name: `DeManagementRpcServerRegisterCallbackForIsAdaptiveColorAdaptationStrengthChanged`
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
- `0x180015720`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800157a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800157a5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800157e9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800157e9`

## string_xrefs

- `0x180015744`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x1800157f3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForIsAdaptiveColorAdaptationStrengthChanged(
        __int64 a1,
        void *a2)
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
    v4 = 612;
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
    v4 = 613;
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
        (void *)0x274,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 264))(v12, &v18);
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
                           (void *)0x276,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180015720  mov     [rsp+arg_8], rbx
0x180015725  mov     [rsp+arg_18], rsi
0x18001572a  push    rdi
0x18001572b  sub     rsp, 60h
0x18001572f  mov     rdi, rdx
0x180015732  mov     rbx, rcx
0x180015735  test    rcx, rcx
0x180015738  jnz     short loc_18001575F
0x18001573a  mov     edx, 264h; void *
0x18001573f  mov     ebx, 80070057h
0x180015744  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001574b  mov     r9d, ebx; char *
0x18001574e  mov     rcx, [rsp+68h]; this
0x180015753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015758  mov     eax, ebx
0x18001575a  jmp     loc_18001586D
0x18001575f  test    rdi, rdi
0x180015762  jnz     short loc_18001576B
0x180015764  mov     edx, 265h
0x180015769  jmp     short loc_18001573F
0x18001576b  lea     rcx, [rsp+68h+var_18]
0x180015770  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015775  nop
0x180015776  mov     rcx, [rsp+68h+var_18]
0x18001577b  mov     rax, [rcx]
0x18001577e  mov     r8, rbx
0x180015781  lea     rdx, [rsp+68h+var_28]
0x180015786  mov     rax, [rax+18h]
0x18001578a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001578f  nop
0x180015790  mov     [rsp+68h+TargetHandle], 0
0x180015799  xor     edx, edx
0x18001579b  lea     rcx, [rsp+68h+TargetHandle]
0x1800157a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800157a5  call    cs:__imp_GetCurrentProcess
0x1800157ab  mov     rsi, rax
0x1800157ae  mov     rcx, [rsp+68h+var_28]
0x1800157b3  mov     rdx, [rcx]
0x1800157b6  mov     rax, [rdx]
0x1800157b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157be  mov     rbx, [rsp+68h]
0x1800157c3  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800157cb  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1800157d3  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x1800157db  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x1800157e0  mov     r8, rsi; hTargetProcessHandle
0x1800157e3  mov     rdx, rdi; hSourceHandle
0x1800157e6  mov     rcx, rax; hSourceProcessHandle
0x1800157e9  call    cs:__imp_DuplicateHandle
0x1800157ef  test    eax, eax
0x1800157f1  jnz     short loc_180015807
0x1800157f3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800157fa  mov     edx, 274h; void *
0x1800157ff  mov     rcx, rbx; this
0x180015802  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015807  mov     rcx, [rsp+68h+var_28]
0x18001580c  mov     rax, [rcx]
0x18001580f  mov     rdx, [rsp+68h+TargetHandle]
0x180015814  mov     [rsp+68h+arg_10], rdx
0x18001581c  mov     [rsp+68h+TargetHandle], 0
0x180015825  lea     rdx, [rsp+68h+arg_10]
0x18001582d  mov     rax, [rax+108h]
0x180015834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015839  nop
0x18001583a  lea     rcx, [rsp+68h+TargetHandle]
0x18001583f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015844  nop
0x180015845  mov     rcx, [rsp+68h+var_20]; this
0x18001584a  test    rcx, rcx
0x18001584d  jz      short loc_180015855
0x18001584f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015854  nop
0x180015855  mov     rcx, [rsp+68h+var_10]; this
0x18001585a  test    rcx, rcx
0x18001585d  jz      short loc_180015865
0x18001585f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015864  nop
0x180015865  xor     eax, eax
0x180015867  jmp     short loc_18001586D
0x180015869  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x18001586d  lea     r11, [rsp+68h+var_8]
0x180015872  mov     rbx, [r11+18h]
0x180015876  mov     rsi, [r11+28h]
0x18001587a  mov     rsp, r11
0x18001587d  pop     rdi
0x18001587e  retn
```
