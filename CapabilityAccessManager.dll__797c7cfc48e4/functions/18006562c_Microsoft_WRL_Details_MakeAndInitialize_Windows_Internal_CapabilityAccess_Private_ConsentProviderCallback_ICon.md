# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback,IConsentResponseCallback,>(IConsentResponseCallback * *)

- ea: `0x18006562c`
- end: `0x18006576e`
- name: `??$MakeAndInitialize@VConsentProviderCallback@Private@CapabilityAccess@Internal@Windows@@UIConsentResponseCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIConsentResponseCallback@@@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065774`

## callees

- `0x180009528`
- `0x180016968`
- `0x18001c770`
- `0x180039e9c`
- `0x18006562c`
- `0x180066d64`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800656fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800656fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065709`

## string_xrefs

- `0x18006575c`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback,IConsentResponseCallback,>(
        _QWORD *a1)
{
  char *v2; // rax
  char *v3; // rdi
  _QWORD *v5; // rbx
  HANDLE Event; // rbp
  const char *v7; // r9
  unsigned int v8; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v10; // [rsp+40h] [rbp+8h] BYREF
  char *v11; // [rsp+48h] [rbp+10h]

  *a1 = 0;
  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    v5 = v2 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `IConsentResponseCallback'};
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback::`vftable'{for `IConsentResponseCallback'};
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v3 + 6) = 0;
    *((_DWORD *)v3 + 14) = 0;
    v11 = v3;
    v10 = 0;
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CC8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        v7);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v3 + 48,
      Event);
    v8 = (**(__int64 (__fastcall ***)(char *, GUID *, _QWORD *))v3)(v3, &GUID_dbd3f191_9873_4dca_9b73_c6ff107d8ee1, a1);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v10);
    return v8;
  }
  else
  {
    Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v10);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18006562c  mov     [rsp+arg_10], rbx
0x180065631  push    rbp
0x180065632  push    rsi
0x180065633  push    rdi
0x180065634  sub     rsp, 20h
0x180065638  mov     rsi, rcx
0x18006563b  mov     qword ptr [rcx], 0
0x180065642  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180065649  mov     ecx, 40h ; '@'; unsigned __int64
0x18006564e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180065653  mov     rdi, rax
0x180065656  mov     [rsp+38h+arg_0], rax
0x18006565b  test    rax, rax
0x18006565e  jnz     short loc_18006567C
0x180065660  lea     rcx, [rsp+38h+arg_0]
0x180065665  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18006566a  mov     eax, 8007000Eh
0x18006566f  mov     rbx, [rsp+38h+arg_10]
0x180065674  add     rsp, 20h
0x180065678  pop     rdi
0x180065679  pop     rsi
0x18006567a  pop     rbp
0x18006567b  retn
0x18006567c  lea     rbx, [rax+8]
0x180065680  mov     rcx, rbx; this
0x180065683  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180065688  mov     ebp, 1
0x18006568d  mov     [rdi+2Ch], ebp
0x180065690  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIConsentResponseCallback@@VFtmBase@23@@WRL@Microsoft@@6BIConsentResponseCallback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `IConsentResponseCallback'}
0x180065697  mov     [rdi], rax
0x18006569a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIConsentResponseCallback@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800656a1  mov     [rbx], rax
0x1800656a4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800656ab  test    rcx, rcx
0x1800656ae  jz      short loc_1800656BD
0x1800656b0  mov     rax, [rcx]
0x1800656b3  mov     rax, [rax+8]
0x1800656b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656bc  nop
0x1800656bd  lea     rax, ??_7ConsentProviderCallback@Private@CapabilityAccess@Internal@Windows@@6BIConsentResponseCallback@@@; const Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback::`vftable'{for `IConsentResponseCallback'}
0x1800656c4  mov     [rdi], rax
0x1800656c7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIConsentResponseCallback@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConsentResponseCallback,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800656ce  mov     [rbx], rax
0x1800656d1  mov     qword ptr [rdi+30h], 0
0x1800656d9  mov     dword ptr [rdi+38h], 0
0x1800656e0  mov     [rsp+38h+arg_8], rdi
0x1800656e5  mov     [rsp+38h+arg_0], 0
0x1800656ee  mov     r9d, 1F0003h; dwDesiredAccess
0x1800656f4  mov     r8d, ebp; dwFlags
0x1800656f7  xor     edx, edx; lpName
0x1800656f9  xor     ecx, ecx; lpEventAttributes
0x1800656fb  call    cs:__imp_CreateEventExW
0x180065701  mov     rbp, rax
0x180065704  test    rax, rax
0x180065707  jz      short loc_180065757
0x180065709  call    cs:__imp_GetLastError
0x18006570f  mov     rdx, rbp
0x180065712  lea     rcx, [rdi+30h]
0x180065716  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006571b  nop
0x18006571c  mov     rax, [rdi]
0x18006571f  mov     r8, rsi
0x180065722  lea     rdx, _GUID_dbd3f191_9873_4dca_9b73_c6ff107d8ee1
0x180065729  mov     rcx, rdi
0x18006572c  mov     rax, [rax]
0x18006572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065734  mov     ebx, eax
0x180065736  mov     rcx, [rdi]
0x180065739  mov     rax, [rcx+10h]
0x18006573d  mov     rcx, rdi
0x180065740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065745  nop
0x180065746  lea     rcx, [rsp+38h+arg_0]
0x18006574b  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180065750  mov     eax, ebx
0x180065752  jmp     loc_18006566F
0x180065757  mov     rcx, [rsp+38h]; this
0x18006575c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180065763  mov     edx, 1CC8h; void *
0x180065768  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
