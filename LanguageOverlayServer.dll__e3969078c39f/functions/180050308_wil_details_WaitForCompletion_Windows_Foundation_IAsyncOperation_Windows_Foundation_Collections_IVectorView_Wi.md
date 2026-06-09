# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180050308`
- end: `0x18005058d`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
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
- `0x180050308`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050498`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050498`

## string_xrefs

- `0x1800503ca`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800503f3`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18005044b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800504ab`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(
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
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180050308  push    rbp
0x18005030a  push    rbx
0x18005030b  push    rsi
0x18005030c  push    rdi
0x18005030d  mov     rbp, rsp
0x180050310  sub     rsp, 68h
0x180050314  mov     rax, cs:__security_cookie
0x18005031b  xor     rax, rsp
0x18005031e  mov     [rbp+var_18], rax
0x180050322  mov     rsi, rcx
0x180050325  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005032c  mov     ecx, 40h ; '@'; unsigned __int64
0x180050331  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180050336  mov     rdi, rax
0x180050339  test    rax, rax
0x18005033c  jnz     short loc_180050348
0x18005033e  mov     ebx, 8007000Eh
0x180050343  jmp     loc_1800503EC
0x180050348  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x18005034f  mov     [rdi], rax
0x180050352  lea     rbx, [rdi+8]
0x180050356  mov     rcx, rbx
0x180050359  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18005035e  mov     dword ptr [rdi+2Ch], 1
0x180050365  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>'}
0x18005036c  mov     [rdi], rax
0x18005036f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050376  mov     [rbx], rax
0x180050379  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180050380  test    rcx, rcx
0x180050383  jz      short loc_180050392
0x180050385  mov     rax, [rcx]
0x180050388  mov     rax, [rax+8]
0x18005038c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050391  nop
0x180050392  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>'}
0x180050399  mov     [rdi], rax
0x18005039c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800503a3  mov     [rbx], rax
0x1800503a6  mov     dword ptr [rdi+30h], 0
0x1800503ad  lea     rcx, [rdi+38h]
0x1800503b1  mov     qword ptr [rcx], 0
0x1800503b8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800503bd  mov     ebx, eax
0x1800503bf  test    eax, eax
0x1800503c1  jns     short loc_18005040C
0x1800503c3  mov     rcx, [rbp+20h]; this
0x1800503c7  mov     r9d, eax; char *
0x1800503ca  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800503d1  mov     edx, 62Bh; void *
0x1800503d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800503db  nop
0x1800503dc  mov     rax, [rdi]
0x1800503df  mov     rcx, rdi
0x1800503e2  mov     rax, [rax+10h]
0x1800503e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503eb  nop
0x1800503ec  mov     rcx, [rbp+20h]; this
0x1800503f0  mov     r9d, ebx; char *
0x1800503f3  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800503fa  mov     edx, 648h; void *
0x1800503ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050404  nop
0x180050405  mov     eax, ebx
0x180050407  jmp     loc_180050578
0x18005040c  mov     rax, [rdi]
0x18005040f  mov     rcx, rdi
0x180050412  mov     rax, [rax+8]
0x180050416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005041b  nop
0x18005041c  mov     rax, [rdi]
0x18005041f  mov     rcx, rdi
0x180050422  mov     rax, [rax+10h]
0x180050426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005042b  nop
0x18005042c  mov     rax, [rsi]
0x18005042f  mov     rdx, rdi
0x180050432  mov     rcx, rsi
0x180050435  mov     rax, [rax+30h]
0x180050439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005043e  mov     ebx, eax
0x180050440  test    eax, eax
0x180050442  jns     short loc_18005046F
0x180050444  mov     rcx, [rbp+20h]; this
0x180050448  mov     r9d, eax; char *
0x18005044b  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180050452  mov     edx, 649h; void *
0x180050457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005045c  nop
0x18005045d  mov     rcx, [rdi]
0x180050460  mov     rax, [rcx+10h]
0x180050464  mov     rcx, rdi
0x180050467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005046c  nop
0x18005046d  jmp     short loc_180050405
0x18005046f  mov     rax, [rdi+38h]
0x180050473  mov     [rbp+pHandles], rax
0x180050477  mov     [rbp+dwindex], 0
0x18005047e  lea     rax, [rbp+dwindex]
0x180050482  mov     qword ptr [rsp+68h+lpdwindex], rax; int
0x180050487  lea     r9, [rbp+pHandles]; pHandles
0x18005048b  mov     r8d, 1; cHandles
0x180050491  or      edx, 0FFFFFFFFh; dwTimeout
0x180050494  lea     ecx, [r8+7]; dwFlags
0x180050498  call    cs:__imp_CoWaitForMultipleHandles
0x18005049e  mov     ebx, eax
0x1800504a0  test    eax, eax
0x1800504a2  jns     short loc_1800504D2
0x1800504a4  mov     rcx, [rbp+20h]; this
0x1800504a8  mov     r9d, eax; char *
0x1800504ab  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800504b2  mov     edx, 655h; void *
0x1800504b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800504bc  nop
0x1800504bd  mov     rcx, [rdi]
0x1800504c0  mov     rax, [rcx+10h]
0x1800504c4  mov     rcx, rdi
0x1800504c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504cc  nop
0x1800504cd  jmp     loc_180050405
0x1800504d2  mov     eax, [rdi+30h]
0x1800504d5  cmp     eax, 1
0x1800504d8  jz      loc_180050566
0x1800504de  mov     [rbp+var_30], 0
0x1800504e6  mov     rax, [rsi]
0x1800504e9  mov     rbx, [rax]
0x1800504ec  lea     rcx, [rbp+var_30]
0x1800504f0  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800504f5  mov     r8, rax
0x1800504f8  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800504ff  mov     rcx, rsi
0x180050502  mov     rax, rbx
0x180050505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005050a  mov     ebx, eax
0x18005050c  test    eax, eax
0x18005050e  js      short loc_180050533
0x180050510  mov     [rbp+var_38], 8000FFFFh
0x180050517  mov     rcx, [rbp+var_30]
0x18005051b  mov     rax, [rcx]
0x18005051e  lea     rdx, [rbp+var_38]
0x180050522  mov     rax, [rax+40h]
0x180050526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005052b  mov     ebx, eax
0x18005052d  test    eax, eax
0x18005052f  cmovns  ebx, [rbp+var_38]
0x180050533  mov     rcx, [rbp+var_30]
0x180050537  test    rcx, rcx
0x18005053a  jz      short loc_180050551
0x18005053c  mov     [rbp+var_30], 0
0x180050544  mov     rax, [rcx]
0x180050547  mov     rax, [rax+10h]
0x18005054b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050550  nop
0x180050551  mov     rax, [rdi]
0x180050554  mov     rcx, rdi
0x180050557  mov     rax, [rax+10h]
0x18005055b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050560  nop
0x180050561  jmp     loc_180050405
0x180050566  mov     rax, [rdi]
0x180050569  mov     rcx, rdi
0x18005056c  mov     rax, [rax+10h]
0x180050570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050575  nop
0x180050576  xor     eax, eax
0x180050578  mov     rcx, [rbp+var_18]
0x18005057c  xor     rcx, rsp; StackCookie
0x18005057f  call    __security_check_cookie
0x180050584  add     rsp, 68h
0x180050588  pop     rdi
0x180050589  pop     rsi
0x18005058a  pop     rbx
0x18005058b  pop     rbp
0x18005058c  retn
```
