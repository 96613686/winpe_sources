# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000e544`
- end: `0x18000e785`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `577`
- prototype: `__int64(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800170b0`

## callees

- `0x180001ea8`
- `0x180007434`
- `0x18000dcf8`
- `0x18000e544`
- `0x18000ed8c`
- `0x180017b1c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e6ce`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e6ce`

## string_xrefs

- `0x18000e604`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e62b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e685`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(
        __int64 (__fastcall ***a1)(__int64, GUID *, __int64 *),
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rdi
  HRESULT v5; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v6; // rcx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v9; // rdx
  __int64 (__fastcall **v10)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v11)(__int64, GUID *, __int64 *); // rbx
  __int64 *v12; // rax
  __int64 v13; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  va_list va1; // [rsp+80h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  v18 = a3;
  dwindex = a2;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v5,
      lpdwindex);
    return (unsigned int)v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 8));
  v6 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 12) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z();
  v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), char *))(*a1)[6])(a1, v4);
  if ( v5 < 0 )
  {
    v9 = 1609;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v5,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v5 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  if ( v5 < 0 )
  {
    v9 = 1621;
    goto LABEL_11;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v10 = *a1;
    v19 = 0;
    v11 = *v10;
    v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((__int64 *)va);
    v5 = v11((__int64)a1, &GUID_00000036_0000_0000_c000_000000000046, v12);
    if ( v5 >= 0 )
    {
      v18 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v18);
      if ( v5 >= 0 )
        v5 = v18;
    }
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18000e544  mov     rax, rsp
0x18000e547  mov     [rax+8], rbx
0x18000e54b  mov     [rax+20h], r9
0x18000e54f  mov     [rax+18h], r8d
0x18000e553  mov     [rax+10h], edx
0x18000e556  push    rbp
0x18000e557  push    rsi
0x18000e558  push    rdi
0x18000e559  mov     rbp, rsp
0x18000e55c  sub     rsp, 40h
0x18000e560  mov     rsi, rcx
0x18000e563  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e56a  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e56f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e574  mov     rdi, rax
0x18000e577  test    rax, rax
0x18000e57a  jnz     short loc_18000E586
0x18000e57c  mov     ebx, 8007000Eh
0x18000e581  jmp     loc_18000E627
0x18000e586  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000e58d  lea     rbx, [rdi+8]
0x18000e591  mov     [rdi], rax
0x18000e594  mov     rcx, rbx; this
0x18000e597  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e59c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e5a3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>'}
0x18000e5aa  mov     [rdi], rax
0x18000e5ad  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e5b4  mov     [rbx], rax
0x18000e5b7  mov     dword ptr [rdi+2Ch], 1
0x18000e5be  test    rcx, rcx
0x18000e5c1  jz      short loc_18000E5CF
0x18000e5c3  mov     rax, [rcx]
0x18000e5c6  mov     rax, [rax+8]
0x18000e5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5cf  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>'}
0x18000e5d6  mov     [rdi], rax
0x18000e5d9  lea     rcx, [rdi+38h]
0x18000e5dd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e5e4  mov     qword ptr [rcx], 0
0x18000e5eb  mov     [rbx], rax
0x18000e5ee  mov     dword ptr [rdi+30h], 0
0x18000e5f5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e5fa  mov     ebx, eax
0x18000e5fc  test    eax, eax
0x18000e5fe  jns     short loc_18000E646
0x18000e600  mov     rcx, [rbp+18h]; this
0x18000e604  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e60b  mov     r9d, eax; char *
0x18000e60e  mov     edx, 62Bh; void *
0x18000e613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e618  mov     rcx, [rdi]
0x18000e61b  mov     rax, [rcx+10h]
0x18000e61f  mov     rcx, rdi
0x18000e622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e627  mov     rcx, [rbp+18h]; this
0x18000e62b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e632  mov     r9d, ebx; char *
0x18000e635  mov     edx, 648h; void *
0x18000e63a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e63f  mov     eax, ebx
0x18000e641  jmp     loc_18000E778
0x18000e646  mov     rax, [rdi]
0x18000e649  mov     rcx, rdi
0x18000e64c  mov     rax, [rax+8]
0x18000e650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e655  mov     rax, [rdi]
0x18000e658  mov     rcx, rdi
0x18000e65b  mov     rax, [rax+10h]
0x18000e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e664  mov     rax, [rsi]
0x18000e667  mov     rdx, rdi
0x18000e66a  mov     rcx, rsi
0x18000e66d  mov     rax, [rax+30h]
0x18000e671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e676  mov     ebx, eax
0x18000e678  test    eax, eax
0x18000e67a  jns     short loc_18000E6A5
0x18000e67c  mov     edx, 649h; void *
0x18000e681  mov     rcx, [rbp+18h]; this
0x18000e685  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e68c  mov     r9d, ebx; char *
0x18000e68f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e694  mov     rcx, [rdi]
0x18000e697  mov     rax, [rcx+10h]
0x18000e69b  mov     rcx, rdi
0x18000e69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a3  jmp     short loc_18000E63F
0x18000e6a5  mov     rax, [rdi+38h]
0x18000e6a9  lea     r9, [rbp+pHandles]; pHandles
0x18000e6ad  mov     r8d, 1; cHandles
0x18000e6b3  mov     [rbp+pHandles], rax
0x18000e6b7  lea     rax, [rbp+dwindex]
0x18000e6bb  mov     [rbp+dwindex], 0
0x18000e6c2  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e6c5  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000e6ca  lea     ecx, [r8+7]; dwFlags
0x18000e6ce  call    cs:__imp_CoWaitForMultipleHandles
0x18000e6d4  mov     ebx, eax
0x18000e6d6  test    eax, eax
0x18000e6d8  jns     short loc_18000E6E1
0x18000e6da  mov     edx, 655h
0x18000e6df  jmp     short loc_18000E681
0x18000e6e1  mov     eax, [rdi+30h]
0x18000e6e4  cmp     eax, 1
0x18000e6e7  jz      short loc_18000E767
0x18000e6e9  mov     rax, [rsi]
0x18000e6ec  lea     rcx, [rbp+arg_18]
0x18000e6f0  mov     [rbp+arg_18], 0
0x18000e6f8  mov     rbx, [rax]
0x18000e6fb  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e700  mov     r8, rax
0x18000e703  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e70a  mov     rax, rbx
0x18000e70d  mov     rcx, rsi
0x18000e710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e715  mov     ebx, eax
0x18000e717  test    eax, eax
0x18000e719  js      short loc_18000E73E
0x18000e71b  mov     rcx, [rbp+arg_18]
0x18000e71f  lea     rdx, [rbp+arg_10]
0x18000e723  mov     [rbp+arg_10], 8000FFFFh
0x18000e72a  mov     rax, [rcx]
0x18000e72d  mov     rax, [rax+40h]
0x18000e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e736  test    eax, eax
0x18000e738  mov     ebx, eax
0x18000e73a  cmovns  ebx, [rbp+arg_10]
0x18000e73e  mov     rcx, [rbp+arg_18]
0x18000e742  test    rcx, rcx
0x18000e745  jz      short loc_18000E75B
0x18000e747  mov     [rbp+arg_18], 0
0x18000e74f  mov     rax, [rcx]
0x18000e752  mov     rax, [rax+10h]
0x18000e756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e75b  mov     rax, [rdi]
0x18000e75e  mov     rax, [rax+10h]
0x18000e762  jmp     loc_18000E69B
0x18000e767  mov     rax, [rdi]
0x18000e76a  mov     rcx, rdi
0x18000e76d  mov     rax, [rax+10h]
0x18000e771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e776  xor     eax, eax
0x18000e778  mov     rbx, [rsp+40h+arg_0]
0x18000e77d  add     rsp, 40h
0x18000e781  pop     rdi
0x18000e782  pop     rsi
0x18000e783  pop     rbp
0x18000e784  retn
```
