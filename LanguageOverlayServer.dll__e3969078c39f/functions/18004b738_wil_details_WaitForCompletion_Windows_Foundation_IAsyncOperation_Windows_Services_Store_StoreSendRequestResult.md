# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18004b738`
- end: `0x18004b9b7`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `639`
- prototype: `__int64(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bcc4`

## callees

- `0x180005d6c`
- `0x180009084`
- `0x18004b2c4`
- `0x18004b738`
- `0x18004bd54`
- `0x18004f710`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b8ca`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b8ca`

## string_xrefs

- `0x18004b7fc`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b825`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b87d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b8dd`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'};
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
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
0x18004b738  mov     rax, rsp
0x18004b73b  mov     [rax+8], rbx
0x18004b73f  mov     [rax+20h], r9
0x18004b743  mov     [rax+18h], r8d
0x18004b747  mov     [rax+10h], edx
0x18004b74a  push    rbp
0x18004b74b  push    rsi
0x18004b74c  push    rdi
0x18004b74d  mov     rbp, rsp
0x18004b750  sub     rsp, 40h
0x18004b754  mov     rsi, rcx
0x18004b757  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b75e  mov     ecx, 40h ; '@'; unsigned __int64
0x18004b763  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b768  mov     rdi, rax
0x18004b76b  test    rax, rax
0x18004b76e  jnz     short loc_18004B77A
0x18004b770  mov     ebx, 8007000Eh
0x18004b775  jmp     loc_18004B81E
0x18004b77a  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x18004b781  mov     [rdi], rax
0x18004b784  lea     rbx, [rdi+8]
0x18004b788  mov     rcx, rbx
0x18004b78b  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18004b790  mov     dword ptr [rdi+2Ch], 1
0x18004b797  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'}
0x18004b79e  mov     [rdi], rax
0x18004b7a1  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004b7a8  mov     [rbx], rax
0x18004b7ab  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004b7b2  test    rcx, rcx
0x18004b7b5  jz      short loc_18004B7C4
0x18004b7b7  mov     rax, [rcx]
0x18004b7ba  mov     rax, [rax+8]
0x18004b7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7c3  nop
0x18004b7c4  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'}
0x18004b7cb  mov     [rdi], rax
0x18004b7ce  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004b7d5  mov     [rbx], rax
0x18004b7d8  mov     dword ptr [rdi+30h], 0
0x18004b7df  lea     rcx, [rdi+38h]
0x18004b7e3  mov     qword ptr [rcx], 0
0x18004b7ea  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004b7ef  mov     ebx, eax
0x18004b7f1  test    eax, eax
0x18004b7f3  jns     short loc_18004B83E
0x18004b7f5  mov     rcx, [rbp+18h]; this
0x18004b7f9  mov     r9d, eax; char *
0x18004b7fc  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b803  mov     edx, 62Bh; void *
0x18004b808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b80d  nop
0x18004b80e  mov     rax, [rdi]
0x18004b811  mov     rcx, rdi
0x18004b814  mov     rax, [rax+10h]
0x18004b818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b81d  nop
0x18004b81e  mov     rcx, [rbp+18h]; this
0x18004b822  mov     r9d, ebx; char *
0x18004b825  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b82c  mov     edx, 648h; void *
0x18004b831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b836  nop
0x18004b837  mov     eax, ebx
0x18004b839  jmp     loc_18004B9AA
0x18004b83e  mov     rax, [rdi]
0x18004b841  mov     rcx, rdi
0x18004b844  mov     rax, [rax+8]
0x18004b848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b84d  nop
0x18004b84e  mov     rax, [rdi]
0x18004b851  mov     rcx, rdi
0x18004b854  mov     rax, [rax+10h]
0x18004b858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b85d  nop
0x18004b85e  mov     rax, [rsi]
0x18004b861  mov     rdx, rdi
0x18004b864  mov     rcx, rsi
0x18004b867  mov     rax, [rax+30h]
0x18004b86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b870  mov     ebx, eax
0x18004b872  test    eax, eax
0x18004b874  jns     short loc_18004B8A1
0x18004b876  mov     rcx, [rbp+18h]; this
0x18004b87a  mov     r9d, eax; char *
0x18004b87d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b884  mov     edx, 649h; void *
0x18004b889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b88e  nop
0x18004b88f  mov     rcx, [rdi]
0x18004b892  mov     rax, [rcx+10h]
0x18004b896  mov     rcx, rdi
0x18004b899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b89e  nop
0x18004b89f  jmp     short loc_18004B837
0x18004b8a1  mov     rax, [rdi+38h]
0x18004b8a5  mov     [rbp+pHandles], rax
0x18004b8a9  mov     [rbp+dwindex], 0
0x18004b8b0  lea     rax, [rbp+dwindex]
0x18004b8b4  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18004b8b9  lea     r9, [rbp+pHandles]; pHandles
0x18004b8bd  mov     r8d, 1; cHandles
0x18004b8c3  or      edx, 0FFFFFFFFh; dwTimeout
0x18004b8c6  lea     ecx, [r8+7]; dwFlags
0x18004b8ca  call    cs:__imp_CoWaitForMultipleHandles
0x18004b8d0  mov     ebx, eax
0x18004b8d2  test    eax, eax
0x18004b8d4  jns     short loc_18004B904
0x18004b8d6  mov     rcx, [rbp+18h]; this
0x18004b8da  mov     r9d, eax; char *
0x18004b8dd  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b8e4  mov     edx, 655h; void *
0x18004b8e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b8ee  nop
0x18004b8ef  mov     rcx, [rdi]
0x18004b8f2  mov     rax, [rcx+10h]
0x18004b8f6  mov     rcx, rdi
0x18004b8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8fe  nop
0x18004b8ff  jmp     loc_18004B837
0x18004b904  mov     eax, [rdi+30h]
0x18004b907  cmp     eax, 1
0x18004b90a  jz      loc_18004B998
0x18004b910  mov     [rbp+arg_18], 0
0x18004b918  mov     rax, [rsi]
0x18004b91b  mov     rbx, [rax]
0x18004b91e  lea     rcx, [rbp+arg_18]
0x18004b922  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18004b927  mov     r8, rax
0x18004b92a  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18004b931  mov     rcx, rsi
0x18004b934  mov     rax, rbx
0x18004b937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b93c  mov     ebx, eax
0x18004b93e  test    eax, eax
0x18004b940  js      short loc_18004B965
0x18004b942  mov     [rbp+arg_10], 8000FFFFh
0x18004b949  mov     rcx, [rbp+arg_18]
0x18004b94d  mov     rax, [rcx]
0x18004b950  lea     rdx, [rbp+arg_10]
0x18004b954  mov     rax, [rax+40h]
0x18004b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b95d  mov     ebx, eax
0x18004b95f  test    eax, eax
0x18004b961  cmovns  ebx, [rbp+arg_10]
0x18004b965  mov     rcx, [rbp+arg_18]
0x18004b969  test    rcx, rcx
0x18004b96c  jz      short loc_18004B983
0x18004b96e  mov     [rbp+arg_18], 0
0x18004b976  mov     rax, [rcx]
0x18004b979  mov     rax, [rax+10h]
0x18004b97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b982  nop
0x18004b983  mov     rax, [rdi]
0x18004b986  mov     rcx, rdi
0x18004b989  mov     rax, [rax+10h]
0x18004b98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b992  nop
0x18004b993  jmp     loc_18004B837
0x18004b998  mov     rax, [rdi]
0x18004b99b  mov     rcx, rdi
0x18004b99e  mov     rax, [rax+10h]
0x18004b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9a7  nop
0x18004b9a8  xor     eax, eax
0x18004b9aa  mov     rbx, [rsp+40h+arg_0]
0x18004b9af  add     rsp, 40h
0x18004b9b3  pop     rdi
0x18004b9b4  pop     rsi
0x18004b9b5  pop     rbp
0x18004b9b6  retn
```
