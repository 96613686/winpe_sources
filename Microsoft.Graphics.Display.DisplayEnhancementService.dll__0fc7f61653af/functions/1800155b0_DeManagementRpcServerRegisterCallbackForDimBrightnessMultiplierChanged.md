# DeManagementRpcServerRegisterCallbackForDimBrightnessMultiplierChanged

- ea: `0x1800155b0`
- end: `0x18001570f`
- name: `DeManagementRpcServerRegisterCallbackForDimBrightnessMultiplierChanged`
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
- `0x1800155b0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015635`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015679`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015679`

## string_xrefs

- `0x1800155d4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180015683`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeManagementRpcServerRegisterCallbackForDimBrightnessMultiplierChanged(__int64 a1, void *a2)
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
    v4 = 1383;
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
    v4 = 1384;
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
        (void *)0x577,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        v8);
    v9 = *v12;
    v18 = TargetHandle;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD *, HANDLE *))(v9 + 488))(v12, &v18);
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
                           (void *)0x579,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\serve"
                                         "r\\lib\\demanagementrpcserver.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800155b0  mov     [rsp+arg_8], rbx
0x1800155b5  mov     [rsp+arg_18], rsi
0x1800155ba  push    rdi
0x1800155bb  sub     rsp, 60h
0x1800155bf  mov     rdi, rdx
0x1800155c2  mov     rbx, rcx
0x1800155c5  test    rcx, rcx
0x1800155c8  jnz     short loc_1800155EF
0x1800155ca  mov     edx, 567h; void *
0x1800155cf  mov     ebx, 80070057h
0x1800155d4  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800155db  mov     r9d, ebx; char *
0x1800155de  mov     rcx, [rsp+68h]; this
0x1800155e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155e8  mov     eax, ebx
0x1800155ea  jmp     loc_1800156FD
0x1800155ef  test    rdi, rdi
0x1800155f2  jnz     short loc_1800155FB
0x1800155f4  mov     edx, 568h
0x1800155f9  jmp     short loc_1800155CF
0x1800155fb  lea     rcx, [rsp+68h+var_18]
0x180015600  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180015605  nop
0x180015606  mov     rcx, [rsp+68h+var_18]
0x18001560b  mov     rax, [rcx]
0x18001560e  mov     r8, rbx
0x180015611  lea     rdx, [rsp+68h+var_28]
0x180015616  mov     rax, [rax+18h]
0x18001561a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001561f  nop
0x180015620  mov     [rsp+68h+TargetHandle], 0
0x180015629  xor     edx, edx
0x18001562b  lea     rcx, [rsp+68h+TargetHandle]
0x180015630  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015635  call    cs:__imp_GetCurrentProcess
0x18001563b  mov     rsi, rax
0x18001563e  mov     rcx, [rsp+68h+var_28]
0x180015643  mov     rdx, [rcx]
0x180015646  mov     rax, [rdx]
0x180015649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001564e  mov     rbx, [rsp+68h]
0x180015653  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001565b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180015663  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18001566b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180015670  mov     r8, rsi; hTargetProcessHandle
0x180015673  mov     rdx, rdi; hSourceHandle
0x180015676  mov     rcx, rax; hSourceProcessHandle
0x180015679  call    cs:__imp_DuplicateHandle
0x18001567f  test    eax, eax
0x180015681  jnz     short loc_180015697
0x180015683  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18001568a  mov     edx, 577h; void *
0x18001568f  mov     rcx, rbx; this
0x180015692  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015697  mov     rcx, [rsp+68h+var_28]
0x18001569c  mov     rax, [rcx]
0x18001569f  mov     rdx, [rsp+68h+TargetHandle]
0x1800156a4  mov     [rsp+68h+arg_10], rdx
0x1800156ac  mov     [rsp+68h+TargetHandle], 0
0x1800156b5  lea     rdx, [rsp+68h+arg_10]
0x1800156bd  mov     rax, [rax+1E8h]
0x1800156c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c9  nop
0x1800156ca  lea     rcx, [rsp+68h+TargetHandle]
0x1800156cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800156d4  nop
0x1800156d5  mov     rcx, [rsp+68h+var_20]; this
0x1800156da  test    rcx, rcx
0x1800156dd  jz      short loc_1800156E5
0x1800156df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800156e4  nop
0x1800156e5  mov     rcx, [rsp+68h+var_10]; this
0x1800156ea  test    rcx, rcx
0x1800156ed  jz      short loc_1800156F5
0x1800156ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800156f4  nop
0x1800156f5  xor     eax, eax
0x1800156f7  jmp     short loc_1800156FD
0x1800156f9  mov     eax, dword ptr [rsp+68h+TargetHandle]
0x1800156fd  lea     r11, [rsp+68h+var_8]
0x180015702  mov     rbx, [r11+18h]
0x180015706  mov     rsi, [r11+28h]
0x18001570a  mov     rsp, r11
0x18001570d  pop     rdi
0x18001570e  retn
```
