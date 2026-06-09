# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180050594`
- end: `0x180050819`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052ad0`

## callees

- `0x180003a00`
- `0x180005d6c`
- `0x180009084`
- `0x18004b2c4`
- `0x18004bd54`
- `0x18004f710`
- `0x180050594`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050724`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050724`

## string_xrefs

- `0x180050656`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18005067f`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800506d7`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180050737`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *))
{
  char *v2; // rdi
  unsigned int v3; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v6; // eax
  HRESULT v7; // eax
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v9; // rax
  __int64 v10; // rcx
  int lpdwindex; // [rsp+20h] [rbp-48h]
  int lpdwindexa; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  DWORD dwindex; // [rsp+40h] [rbp-28h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v2 )
  {
    v3 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v3,
      lpdwindex);
    return v3;
  }
  *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v2 + 8);
  *((_DWORD *)v2 + 11) = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 7) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z();
  v3 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v2);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v6,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  pHandles = (HANDLE)*((_QWORD *)v2 + 7);
  dwindex = 0;
  v7 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v7,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  if ( *((_DWORD *)v2 + 12) != 1 )
  {
    v14 = 0;
    v8 = **a1;
    v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v14);
    v3 = v8(a1, &GUID_00000036_0000_0000_c000_000000000046, v9);
    if ( (v3 & 0x80000000) == 0 )
    {
      v13 = -2147418113;
      v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 64LL))(v14, &v13);
      if ( (v3 & 0x80000000) == 0 )
        v3 = v13;
    }
    v10 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180050594  push    rbp
0x180050596  push    rbx
0x180050597  push    rsi
0x180050598  push    rdi
0x180050599  mov     rbp, rsp
0x18005059c  sub     rsp, 68h
0x1800505a0  mov     rax, cs:__security_cookie
0x1800505a7  xor     rax, rsp
0x1800505aa  mov     [rbp+var_18], rax
0x1800505ae  mov     rsi, rcx
0x1800505b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800505b8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800505bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800505c2  mov     rdi, rax
0x1800505c5  test    rax, rax
0x1800505c8  jnz     short loc_1800505D4
0x1800505ca  mov     ebx, 8007000Eh
0x1800505cf  jmp     loc_180050678
0x1800505d4  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x1800505db  mov     [rdi], rax
0x1800505de  lea     rbx, [rdi+8]
0x1800505e2  mov     rcx, rbx
0x1800505e5  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800505ea  mov     dword ptr [rdi+2Ch], 1
0x1800505f1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>'}
0x1800505f8  mov     [rdi], rax
0x1800505fb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050602  mov     [rbx], rax
0x180050605  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18005060c  test    rcx, rcx
0x18005060f  jz      short loc_18005061E
0x180050611  mov     rax, [rcx]
0x180050614  mov     rax, [rax+8]
0x180050618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005061d  nop
0x18005061e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>'}
0x180050625  mov     [rdi], rax
0x180050628  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005062f  mov     [rbx], rax
0x180050632  mov     dword ptr [rdi+30h], 0
0x180050639  lea     rcx, [rdi+38h]
0x18005063d  mov     qword ptr [rcx], 0
0x180050644  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180050649  mov     ebx, eax
0x18005064b  test    eax, eax
0x18005064d  jns     short loc_180050698
0x18005064f  mov     rcx, [rbp+20h]; this
0x180050653  mov     r9d, eax; char *
0x180050656  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005065d  mov     edx, 62Bh; void *
0x180050662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050667  nop
0x180050668  mov     rax, [rdi]
0x18005066b  mov     rcx, rdi
0x18005066e  mov     rax, [rax+10h]
0x180050672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050677  nop
0x180050678  mov     rcx, [rbp+20h]; this
0x18005067c  mov     r9d, ebx; char *
0x18005067f  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180050686  mov     edx, 648h; void *
0x18005068b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050690  nop
0x180050691  mov     eax, ebx
0x180050693  jmp     loc_180050804
0x180050698  mov     rax, [rdi]
0x18005069b  mov     rcx, rdi
0x18005069e  mov     rax, [rax+8]
0x1800506a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506a7  nop
0x1800506a8  mov     rax, [rdi]
0x1800506ab  mov     rcx, rdi
0x1800506ae  mov     rax, [rax+10h]
0x1800506b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506b7  nop
0x1800506b8  mov     rax, [rsi]
0x1800506bb  mov     rdx, rdi
0x1800506be  mov     rcx, rsi
0x1800506c1  mov     rax, [rax+30h]
0x1800506c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506ca  mov     ebx, eax
0x1800506cc  test    eax, eax
0x1800506ce  jns     short loc_1800506FB
0x1800506d0  mov     rcx, [rbp+20h]; this
0x1800506d4  mov     r9d, eax; char *
0x1800506d7  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800506de  mov     edx, 649h; void *
0x1800506e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800506e8  nop
0x1800506e9  mov     rcx, [rdi]
0x1800506ec  mov     rax, [rcx+10h]
0x1800506f0  mov     rcx, rdi
0x1800506f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506f8  nop
0x1800506f9  jmp     short loc_180050691
0x1800506fb  mov     rax, [rdi+38h]
0x1800506ff  mov     [rbp+pHandles], rax
0x180050703  mov     [rbp+dwindex], 0
0x18005070a  lea     rax, [rbp+dwindex]
0x18005070e  mov     qword ptr [rsp+68h+lpdwindex], rax; int
0x180050713  lea     r9, [rbp+pHandles]; pHandles
0x180050717  mov     r8d, 1; cHandles
0x18005071d  or      edx, 0FFFFFFFFh; dwTimeout
0x180050720  lea     ecx, [r8+7]; dwFlags
0x180050724  call    cs:__imp_CoWaitForMultipleHandles
0x18005072a  mov     ebx, eax
0x18005072c  test    eax, eax
0x18005072e  jns     short loc_18005075E
0x180050730  mov     rcx, [rbp+20h]; this
0x180050734  mov     r9d, eax; char *
0x180050737  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005073e  mov     edx, 655h; void *
0x180050743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050748  nop
0x180050749  mov     rcx, [rdi]
0x18005074c  mov     rax, [rcx+10h]
0x180050750  mov     rcx, rdi
0x180050753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050758  nop
0x180050759  jmp     loc_180050691
0x18005075e  mov     eax, [rdi+30h]
0x180050761  cmp     eax, 1
0x180050764  jz      loc_1800507F2
0x18005076a  mov     [rbp+var_30], 0
0x180050772  mov     rax, [rsi]
0x180050775  mov     rbx, [rax]
0x180050778  lea     rcx, [rbp+var_30]
0x18005077c  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050781  mov     r8, rax
0x180050784  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18005078b  mov     rcx, rsi
0x18005078e  mov     rax, rbx
0x180050791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050796  mov     ebx, eax
0x180050798  test    eax, eax
0x18005079a  js      short loc_1800507BF
0x18005079c  mov     [rbp+var_38], 8000FFFFh
0x1800507a3  mov     rcx, [rbp+var_30]
0x1800507a7  mov     rax, [rcx]
0x1800507aa  lea     rdx, [rbp+var_38]
0x1800507ae  mov     rax, [rax+40h]
0x1800507b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507b7  mov     ebx, eax
0x1800507b9  test    eax, eax
0x1800507bb  cmovns  ebx, [rbp+var_38]
0x1800507bf  mov     rcx, [rbp+var_30]
0x1800507c3  test    rcx, rcx
0x1800507c6  jz      short loc_1800507DD
0x1800507c8  mov     [rbp+var_30], 0
0x1800507d0  mov     rax, [rcx]
0x1800507d3  mov     rax, [rax+10h]
0x1800507d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507dc  nop
0x1800507dd  mov     rax, [rdi]
0x1800507e0  mov     rcx, rdi
0x1800507e3  mov     rax, [rax+10h]
0x1800507e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507ec  nop
0x1800507ed  jmp     loc_180050691
0x1800507f2  mov     rax, [rdi]
0x1800507f5  mov     rcx, rdi
0x1800507f8  mov     rax, [rax+10h]
0x1800507fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050801  nop
0x180050802  xor     eax, eax
0x180050804  mov     rcx, [rbp+var_18]
0x180050808  xor     rcx, rsp; StackCookie
0x18005080b  call    __security_check_cookie
0x180050810  add     rsp, 68h
0x180050814  pop     rdi
0x180050815  pop     rsi
0x180050816  pop     rbx
0x180050817  pop     rbp
0x180050818  retn
```
