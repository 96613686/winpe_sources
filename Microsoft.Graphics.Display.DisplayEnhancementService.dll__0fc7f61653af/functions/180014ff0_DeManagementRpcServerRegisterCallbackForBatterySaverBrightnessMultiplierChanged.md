# DeManagementRpcServerRegisterCallbackForBatterySaverBrightnessMultiplierChanged

- ea: `0x180014ff0`
- end: `0x18001514f`
- name: `DeManagementRpcServerRegisterCallbackForBatterySaverBrightnessMultiplierChanged`
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
- `0x180014ff0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015075`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800150b9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800150b9`

## string_xrefs

- `0x180015014`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x1800150c3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForBatterySaverBrightnessMultiplierChanged(
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
    v4 = 1305;
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
    v4 = 1306;
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
        (void *)0x529,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 424))(v12, &v18);
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
                           (void *)0x52B,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014ff0  mov     [rsp+arg_8], rbx
0x180014ff5  mov     [rsp+arg_18], rsi
0x180014ffa  push    rdi
0x180014ffb  sub     rsp, 60h
0x180014fff  mov     rdi, rdx
0x180015002  mov     rbx, rcx
0x180015005  test    rcx, rcx
0x180015008  jnz     short loc_18001502F
0x18001500a  mov     edx, 519h; void *
0x18001500f  mov     ebx, 80070057h
0x180015014  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001501b  mov     r9d, ebx; char *
0x18001501e  mov     rcx, [rsp+68h]; this
0x180015023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015028  mov     eax, ebx
0x18001502a  jmp     loc_18001513D
0x18001502f  test    rdi, rdi
0x180015032  jnz     short loc_18001503B
0x180015034  mov     edx, 51Ah
0x180015039  jmp     short loc_18001500F
0x18001503b  lea     rcx, [rsp+68h+var_18]
0x180015040  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015045  nop
0x180015046  mov     rcx, [rsp+68h+var_18]
0x18001504b  mov     rax, [rcx]
0x18001504e  mov     r8, rbx
0x180015051  lea     rdx, [rsp+68h+var_28]
0x180015056  mov     rax, [rax+18h]
0x18001505a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001505f  nop
0x180015060  mov     [rsp+68h+TargetHandle], 0
0x180015069  xor     edx, edx
0x18001506b  lea     rcx, [rsp+68h+TargetHandle]
0x180015070  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015075  call    cs:__imp_GetCurrentProcess
0x18001507b  mov     rsi, rax
0x18001507e  mov     rcx, [rsp+68h+var_28]
0x180015083  mov     rdx, [rcx]
0x180015086  mov     rax, [rdx]
0x180015089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001508e  mov     rbx, [rsp+68h]
0x180015093  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001509b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1800150a3  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x1800150ab  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x1800150b0  mov     r8, rsi; hTargetProcessHandle
0x1800150b3  mov     rdx, rdi; hSourceHandle
0x1800150b6  mov     rcx, rax; hSourceProcessHandle
0x1800150b9  call    cs:__imp_DuplicateHandle
0x1800150bf  test    eax, eax
0x1800150c1  jnz     short loc_1800150D7
0x1800150c3  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800150ca  mov     edx, 529h; void *
0x1800150cf  mov     rcx, rbx; this
0x1800150d2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800150d7  mov     rcx, [rsp+68h+var_28]
0x1800150dc  mov     rax, [rcx]
0x1800150df  mov     rdx, [rsp+68h+TargetHandle]
0x1800150e4  mov     [rsp+68h+arg_10], rdx
0x1800150ec  mov     [rsp+68h+TargetHandle], 0
0x1800150f5  lea     rdx, [rsp+68h+arg_10]
0x1800150fd  mov     rax, [rax+1A8h]
0x180015104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015109  nop
0x18001510a  lea     rcx, [rsp+68h+TargetHandle]
0x18001510f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015114  nop
0x180015115  mov     rcx, [rsp+68h+var_20]; this
0x18001511a  test    rcx, rcx
0x18001511d  jz      short loc_180015125
0x18001511f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015124  nop
0x180015125  mov     rcx, [rsp+68h+var_10]; this
0x18001512a  test    rcx, rcx
0x18001512d  jz      short loc_180015135
0x18001512f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015134  nop
0x180015135  xor     eax, eax
0x180015137  jmp     short loc_18001513D
0x180015139  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x18001513d  lea     r11, [rsp+68h+var_8]
0x180015142  mov     rbx, [r11+18h]
0x180015146  mov     rsi, [r11+28h]
0x18001514a  mov     rsp, r11
0x18001514d  pop     rdi
0x18001514e  retn
```
