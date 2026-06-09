# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18004b9c0`
- end: `0x18004bc3f`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `639`
- prototype: `__int64(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f2c8`
- `0x1800621d8`

## callees

- `0x180005d6c`
- `0x180009084`
- `0x18004b2c4`
- `0x18004b9c0`
- `0x18004bd54`
- `0x18004f710`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004bb52`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004bb52`

## string_xrefs

- `0x18004ba84`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004baad`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004bb05`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004bb65`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rdi
  unsigned int v5; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v8; // eax
  HRESULT v9; // eax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v11; // rax
  __int64 v12; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
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
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 7) = 0;
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
  v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v4);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v8,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v9 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v9,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v19 = 0;
    v10 = **a1;
    v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((__int64 *)va);
    v5 = v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11);
    if ( (v5 & 0x80000000) == 0 )
    {
      v18 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v18);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v18;
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18004b9c0  mov     rax, rsp
0x18004b9c3  mov     [rax+8], rbx
0x18004b9c7  mov     [rax+20h], r9
0x18004b9cb  mov     [rax+18h], r8d
0x18004b9cf  mov     [rax+10h], edx
0x18004b9d2  push    rbp
0x18004b9d3  push    rsi
0x18004b9d4  push    rdi
0x18004b9d5  mov     rbp, rsp
0x18004b9d8  sub     rsp, 40h
0x18004b9dc  mov     rsi, rcx
0x18004b9df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b9e6  mov     ecx, 40h ; '@'; unsigned __int64
0x18004b9eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b9f0  mov     rdi, rax
0x18004b9f3  test    rax, rax
0x18004b9f6  jnz     short loc_18004BA02
0x18004b9f8  mov     ebx, 8007000Eh
0x18004b9fd  jmp     loc_18004BAA6
0x18004ba02  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x18004ba09  mov     [rdi], rax
0x18004ba0c  lea     rbx, [rdi+8]
0x18004ba10  mov     rcx, rbx
0x18004ba13  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18004ba18  mov     dword ptr [rdi+2Ch], 1
0x18004ba1f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18004ba26  mov     [rdi], rax
0x18004ba29  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004ba30  mov     [rbx], rax
0x18004ba33  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004ba3a  test    rcx, rcx
0x18004ba3d  jz      short loc_18004BA4C
0x18004ba3f  mov     rax, [rcx]
0x18004ba42  mov     rax, [rax+8]
0x18004ba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba4b  nop
0x18004ba4c  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@_N@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18004ba53  mov     [rdi], rax
0x18004ba56  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004ba5d  mov     [rbx], rax
0x18004ba60  mov     dword ptr [rdi+30h], 0
0x18004ba67  lea     rcx, [rdi+38h]
0x18004ba6b  mov     qword ptr [rcx], 0
0x18004ba72  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004ba77  mov     ebx, eax
0x18004ba79  test    eax, eax
0x18004ba7b  jns     short loc_18004BAC6
0x18004ba7d  mov     rcx, [rbp+18h]; this
0x18004ba81  mov     r9d, eax; char *
0x18004ba84  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004ba8b  mov     edx, 62Bh; void *
0x18004ba90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ba95  nop
0x18004ba96  mov     rax, [rdi]
0x18004ba99  mov     rcx, rdi
0x18004ba9c  mov     rax, [rax+10h]
0x18004baa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004baa5  nop
0x18004baa6  mov     rcx, [rbp+18h]; this
0x18004baaa  mov     r9d, ebx; char *
0x18004baad  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004bab4  mov     edx, 648h; void *
0x18004bab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004babe  nop
0x18004babf  mov     eax, ebx
0x18004bac1  jmp     loc_18004BC32
0x18004bac6  mov     rax, [rdi]
0x18004bac9  mov     rcx, rdi
0x18004bacc  mov     rax, [rax+8]
0x18004bad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bad5  nop
0x18004bad6  mov     rax, [rdi]
0x18004bad9  mov     rcx, rdi
0x18004badc  mov     rax, [rax+10h]
0x18004bae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bae5  nop
0x18004bae6  mov     rax, [rsi]
0x18004bae9  mov     rdx, rdi
0x18004baec  mov     rcx, rsi
0x18004baef  mov     rax, [rax+30h]
0x18004baf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004baf8  mov     ebx, eax
0x18004bafa  test    eax, eax
0x18004bafc  jns     short loc_18004BB29
0x18004bafe  mov     rcx, [rbp+18h]; this
0x18004bb02  mov     r9d, eax; char *
0x18004bb05  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004bb0c  mov     edx, 649h; void *
0x18004bb11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb16  nop
0x18004bb17  mov     rcx, [rdi]
0x18004bb1a  mov     rax, [rcx+10h]
0x18004bb1e  mov     rcx, rdi
0x18004bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb26  nop
0x18004bb27  jmp     short loc_18004BABF
0x18004bb29  mov     rax, [rdi+38h]
0x18004bb2d  mov     [rbp+pHandles], rax
0x18004bb31  mov     [rbp+dwindex], 0
0x18004bb38  lea     rax, [rbp+dwindex]
0x18004bb3c  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18004bb41  lea     r9, [rbp+pHandles]; pHandles
0x18004bb45  mov     r8d, 1; cHandles
0x18004bb4b  or      edx, 0FFFFFFFFh; dwTimeout
0x18004bb4e  lea     ecx, [r8+7]; dwFlags
0x18004bb52  call    cs:__imp_CoWaitForMultipleHandles
0x18004bb58  mov     ebx, eax
0x18004bb5a  test    eax, eax
0x18004bb5c  jns     short loc_18004BB8C
0x18004bb5e  mov     rcx, [rbp+18h]; this
0x18004bb62  mov     r9d, eax; char *
0x18004bb65  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004bb6c  mov     edx, 655h; void *
0x18004bb71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb76  nop
0x18004bb77  mov     rcx, [rdi]
0x18004bb7a  mov     rax, [rcx+10h]
0x18004bb7e  mov     rcx, rdi
0x18004bb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb86  nop
0x18004bb87  jmp     loc_18004BABF
0x18004bb8c  mov     eax, [rdi+30h]
0x18004bb8f  cmp     eax, 1
0x18004bb92  jz      loc_18004BC20
0x18004bb98  mov     [rbp+arg_18], 0
0x18004bba0  mov     rax, [rsi]
0x18004bba3  mov     rbx, [rax]
0x18004bba6  lea     rcx, [rbp+arg_18]
0x18004bbaa  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18004bbaf  mov     r8, rax
0x18004bbb2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18004bbb9  mov     rcx, rsi
0x18004bbbc  mov     rax, rbx
0x18004bbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbc4  mov     ebx, eax
0x18004bbc6  test    eax, eax
0x18004bbc8  js      short loc_18004BBED
0x18004bbca  mov     [rbp+arg_10], 8000FFFFh
0x18004bbd1  mov     rcx, [rbp+arg_18]
0x18004bbd5  mov     rax, [rcx]
0x18004bbd8  lea     rdx, [rbp+arg_10]
0x18004bbdc  mov     rax, [rax+40h]
0x18004bbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbe5  mov     ebx, eax
0x18004bbe7  test    eax, eax
0x18004bbe9  cmovns  ebx, [rbp+arg_10]
0x18004bbed  mov     rcx, [rbp+arg_18]
0x18004bbf1  test    rcx, rcx
0x18004bbf4  jz      short loc_18004BC0B
0x18004bbf6  mov     [rbp+arg_18], 0
0x18004bbfe  mov     rax, [rcx]
0x18004bc01  mov     rax, [rax+10h]
0x18004bc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc0a  nop
0x18004bc0b  mov     rax, [rdi]
0x18004bc0e  mov     rcx, rdi
0x18004bc11  mov     rax, [rax+10h]
0x18004bc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc1a  nop
0x18004bc1b  jmp     loc_18004BABF
0x18004bc20  mov     rax, [rdi]
0x18004bc23  mov     rcx, rdi
0x18004bc26  mov     rax, [rax+10h]
0x18004bc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc2f  nop
0x18004bc30  xor     eax, eax
0x18004bc32  mov     rbx, [rsp+40h+arg_0]
0x18004bc37  add     rsp, 40h
0x18004bc3b  pop     rdi
0x18004bc3c  pop     rsi
0x18004bc3d  pop     rbp
0x18004bc3e  retn
```
