# Windows::UO::LegacyUOProvider::LegacyUOProvider(std::shared_ptr<DecisionEngine<SystemInterface::Providers::ConditionContext>> &,UpdateDatabase &)

- ea: `0x140317d5c`
- end: `0x140317f95`
- name: `??0LegacyUOProvider@UO@Windows@@QEAA@AEAV?$shared_ptr@V?$DecisionEngine@VConditionContext@Providers@SystemInterface@@@@@std@@AEAVUpdateDatabase@@@Z`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14029b100`
- `0x1402a1220`

## callees

- `0x14003c578`
- `0x140040364`
- `0x14004045c`
- `0x1400413a8`
- `0x14004519c`
- `0x140317d5c`
- `0x140325bf4`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140317ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140317ec5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140317e6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140317e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140317eb3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140317eb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140317ee1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140317ee1`

## string_xrefs

- `0x140317f5b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140317f71`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140317ea8`: `Global\LegacyUOProviderWorkCompleted`
- `0x140317f83`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::UO::LegacyUOProvider::LegacyUOProvider(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  const char *v6; // r9
  HANDLE v7; // rbx
  const char *v8; // r9
  const char *v9; // r9
  void *v10; // rdx
  int take_hevent_ownership; // eax
  _BYTE v13[8]; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v14[13]; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v15; // [rsp+A0h] [rbp+7h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+A8h] [rbp+Fh] BYREF
  void *v17; // [rsp+C0h] [rbp+27h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *(_QWORD *)a1 = &Windows::UO::LegacyUOProvider::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = a2[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  *(_QWORD *)(a1 + 16) = *a2;
  *(_QWORD *)(a1 + 24) = a2[1];
  *(_QWORD *)(a1 + 32) = a3;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(80);
  *(_QWORD *)v5 = v5;
  *(_QWORD *)(v5 + 8) = v5;
  *(_QWORD *)(v5 + 16) = v5;
  *(_WORD *)(v5 + 24) = 257;
  *(_QWORD *)(a1 + 40) = v5;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 2;
  *(_OWORD *)(a1 + 152) = 0;
  *(_OWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 200) = -1;
  *(_DWORD *)(a1 + 204) = 0;
  *(_BYTE *)(a1 + 208) = 0;
  *(&EventAttributes.nLength + 1) = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
      v6);
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  EventAttributes.bInheritHandle = 0;
  v17 = 0;
  v7 = CreateEventExW(&EventAttributes, L"Global\\LegacyUOProviderWorkCompleted", 0, 0x1F0003u);
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CA0,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      v8);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    v7);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  v14[0] = off_1403D95D8;
  v14[1] = a1;
  v15 = v14;
  v10 = v17;
  v17 = 0;
  take_hevent_ownership = wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
                            (wil::details::event_watcher_state **)(a1 + 8),
                            v10,
                            (__int64)v13,
                            v9);
  if ( take_hevent_ownership < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)take_hevent_ownership,
      1);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 24LL))(v15);
  return a1;
}

```

## disassembly

```asm
0x140317d5c  mov     [rsp-8+arg_10], rbx
0x140317d61  mov     [rsp-8+arg_18], rsi
0x140317d66  push    rbp
0x140317d67  push    rdi
0x140317d68  push    r14
0x140317d6a  lea     rbp, [rsp-47h]
0x140317d6f  sub     rsp, 0E0h
0x140317d76  mov     rax, cs:__security_cookie
0x140317d7d  xor     rax, rsp
0x140317d80  mov     [rbp+57h+var_20], rax
0x140317d84  mov     rdi, rcx
0x140317d87  mov     [rbp+57h+var_C8], rcx
0x140317d8b  xor     r14d, r14d
0x140317d8e  mov     [rbp+57h+var_D0], r14d
0x140317d92  lea     rax, ??_7LegacyUOProvider@UO@Windows@@6B@; const Windows::UO::LegacyUOProvider::`vftable'
0x140317d99  mov     [rcx], rax
0x140317d9c  mov     [rcx+8], r14
0x140317da0  mov     [rcx+10h], r14
0x140317da4  mov     [rcx+18h], r14
0x140317da8  mov     rax, [rdx+8]
0x140317dac  test    rax, rax
0x140317daf  jz      short loc_140317DB5
0x140317db1  lock inc dword ptr [rax+8]
0x140317db5  mov     rax, [rdx]
0x140317db8  mov     [rcx+10h], rax
0x140317dbc  mov     rax, [rdx+8]
0x140317dc0  mov     [rcx+18h], rax
0x140317dc4  mov     [rcx+20h], r8
0x140317dc8  mov     [rcx+28h], r14
0x140317dcc  mov     [rcx+30h], r14
0x140317dd0  mov     ecx, 50h ; 'P'
0x140317dd5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140317dda  mov     [rax], rax
0x140317ddd  mov     [rax+8], rax
0x140317de1  mov     [rax+10h], rax
0x140317de5  mov     word ptr [rax+18h], 101h
0x140317deb  mov     [rdi+28h], rax
0x140317def  mov     [rdi+38h], r14
0x140317df3  mov     [rdi+40h], r14
0x140317df7  xorps   xmm0, xmm0
0x140317dfa  xor     eax, eax
0x140317dfc  movups  xmmword ptr [rdi+48h], xmm0
0x140317e00  movups  xmmword ptr [rdi+58h], xmm0
0x140317e04  movups  xmmword ptr [rdi+68h], xmm0
0x140317e08  mov     [rdi+78h], rax
0x140317e0c  mov     qword ptr [rdi+80h], 2
0x140317e17  movups  xmmword ptr [rdi+98h], xmm0
0x140317e1e  movups  xmmword ptr [rdi+0A8h], xmm0
0x140317e25  movups  xmmword ptr [rdi+0B8h], xmm0
0x140317e2c  mov     [rdi+88h], r14
0x140317e33  mov     [rdi+90h], r14
0x140317e3a  mov     dword ptr [rdi+0C8h], 0FFFFFFFFh
0x140317e44  mov     [rdi+0CCh], r14d
0x140317e4b  mov     [rdi+0D0h], r14b
0x140317e52  mov     dword ptr [rbp+57h+EventAttributes+4], r14d
0x140317e56  mov     dword ptr [rbp+57h+EventAttributes+14h], r14d
0x140317e5a  mov     [rbp+57h+SecurityDescriptor], r14
0x140317e5e  xor     r9d, r9d; SecurityDescriptorSize
0x140317e61  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140317e65  lea     edx, [rax+1]; StringSDRevision
0x140317e68  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x140317e6f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140317e75  mov     rcx, [rbp+5Fh]; this
0x140317e79  test    eax, eax
0x140317e7b  jz      loc_140317F83
0x140317e81  mov     [rbp+57h+EventAttributes.nLength], 18h
0x140317e88  mov     rax, [rbp+57h+SecurityDescriptor]
0x140317e8c  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x140317e90  mov     [rbp+57h+EventAttributes.bInheritHandle], r14d
0x140317e94  mov     [rbp+57h+var_30], r14
0x140317e98  mov     [rbp+57h+var_D0], 1
0x140317e9f  mov     r9d, 1F0003h; dwDesiredAccess
0x140317ea5  xor     r8d, r8d; dwFlags
0x140317ea8  lea     rdx, aGlobalLegacyuo; "Global\\LegacyUOProviderWorkCompleted"
0x140317eaf  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x140317eb3  call    cs:__imp_CreateEventExW
0x140317eb9  mov     rbx, rax
0x140317ebc  test    rax, rax
0x140317ebf  jz      loc_140317F6D
0x140317ec5  call    cs:__imp_GetLastError
0x140317ecb  mov     rdx, rbx
0x140317ece  lea     rcx, [rbp+57h+var_30]
0x140317ed2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140317ed7  nop
0x140317ed8  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x140317edc  test    rcx, rcx
0x140317edf  jz      short loc_140317EE7
0x140317ee1  call    cs:__imp_LocalFree
0x140317ee7  lea     rax, off_1403D95D8
0x140317eee  mov     [rbp+57h+var_B8], rax
0x140317ef2  mov     [rbp+57h+var_B0], rdi
0x140317ef6  lea     rax, [rbp+57h+var_B8]
0x140317efa  mov     [rbp+57h+var_50], rax
0x140317efe  mov     rdx, [rbp+57h+var_30]
0x140317f02  mov     [rbp+57h+var_30], r14
0x140317f06  lea     r8, [rbp+57h+var_C0]
0x140317f0a  lea     rcx, [rdi+8]
0x140317f0e  call    ?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wistd::function<void (void)> &&)
0x140317f13  mov     rcx, [rbp+5Fh]; this
0x140317f17  test    eax, eax
0x140317f19  js      short loc_140317F58
0x140317f1b  mov     rcx, [rbp+57h+var_50]
0x140317f1f  test    rcx, rcx
0x140317f22  jz      short loc_140317F31
0x140317f24  mov     rdx, [rcx]
0x140317f27  mov     rax, [rdx+18h]
0x140317f2b  call    _guard_dispatch_icall
0x140317f30  nop
0x140317f31  mov     rax, rdi
0x140317f34  mov     rcx, [rbp+57h+var_20]
0x140317f38  xor     rcx, rsp; StackCookie
0x140317f3b  call    __security_check_cookie
0x140317f40  lea     r11, [rsp+0F0h+var_10]
0x140317f48  mov     rbx, [r11+30h]
0x140317f4c  mov     rsi, [r11+38h]
0x140317f50  mov     rsp, r11
0x140317f53  pop     r14
0x140317f55  pop     rdi
0x140317f56  pop     rbp
0x140317f57  retn
0x140317f58  mov     r9d, eax; char *
0x140317f5b  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140317f62  mov     edx, 1C96h; void *
0x140317f67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140317f6d  mov     rcx, [rbp+5Fh]; this
0x140317f71  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140317f78  mov     edx, 1CA0h; void *
0x140317f7d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140317f83  lea     r8, aCW1SSrcOrchest_90; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140317f8a  mov     edx, 52h ; 'R'; void *
0x140317f8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
