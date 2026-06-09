# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000a614`
- end: `0x18000a8c5`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `689`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012b50`

## callees

- `0x180004618`
- `0x180009cac`
- `0x18000a614`
- `0x18000a8cc`
- `0x1800105f4`
- `0x180012184`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a7b0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a7b0`

## string_xrefs

- `0x18000a6e2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a70b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a763`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a7e7`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64),
        int a2,
        DWORD a3,
        _BYTE *a4)
{
  char *v7; // rdi
  unsigned int v8; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v11; // eax
  HRESULT v12; // eax
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v21; // [rsp+78h] [rbp+38h] BYREF
  DWORD dwindex; // [rsp+88h] [rbp+48h] BYREF

  v21 = a2;
  if ( a4 )
    *a4 = 0;
  v7 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    v8 = -2147024882;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v8,
      lpdwindex);
    return v8;
  }
  *(_QWORD *)v7 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 8));
  *((_DWORD *)v7 + 11) = 1;
  *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *((_QWORD *)v7 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v7 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v7 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 7) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((void **)v7 + 7);
  v8 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
    goto LABEL_9;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
  v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), char *))(*a1)[6])(a1, v7);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v11,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
    return v8;
  }
  pHandles = (HANDLE)*((_QWORD *)v7 + 7);
  dwindex = 0;
  v12 = CoWaitForMultipleHandles(8u, a3, 1u, &pHandles, &dwindex);
  v8 = v12;
  if ( a4 && v12 == -2147417835 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)v12,
        lpdwindexa);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
      return v8;
    }
    if ( *((_DWORD *)v7 + 12) != 1 )
    {
      v18 = 0;
      v13 = **a1;
      v14 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v18);
      v8 = v13(a1, &GUID_00000036_0000_0000_c000_000000000046, v14);
      if ( (v8 & 0x80000000) == 0 )
      {
        v21 = -2147418113;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 64LL))(v18, &v21);
        if ( (v8 & 0x80000000) == 0 )
          v8 = v21;
      }
      v15 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
      return v8;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a614  mov     [rsp-28h+arg_0], rbx
0x18000a619  mov     [rsp-28h+arg_8], edx
0x18000a61d  push    rbp
0x18000a61e  push    rsi
0x18000a61f  push    rdi
0x18000a620  push    r14
0x18000a622  push    r15
0x18000a624  mov     rbp, rsp
0x18000a627  sub     rsp, 40h
0x18000a62b  mov     rsi, r9
0x18000a62e  mov     r15d, r8d
0x18000a631  mov     r14, rcx
0x18000a634  test    r9, r9
0x18000a637  jz      short loc_18000A63D
0x18000a639  mov     byte ptr [r9], 0
0x18000a63d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a644  mov     ecx, 40h ; '@'; unsigned __int64
0x18000a649  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a64e  mov     rdi, rax
0x18000a651  test    rax, rax
0x18000a654  jnz     short loc_18000A660
0x18000a656  mov     ebx, 8007000Eh
0x18000a65b  jmp     loc_18000A704
0x18000a660  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x18000a667  mov     [rdi], rax
0x18000a66a  lea     rbx, [rdi+8]
0x18000a66e  mov     rcx, rbx; this
0x18000a671  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000a676  mov     dword ptr [rdi+2Ch], 1
0x18000a67d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18000a684  mov     [rdi], rax
0x18000a687  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000a68e  mov     [rbx], rax
0x18000a691  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a698  test    rcx, rcx
0x18000a69b  jz      short loc_18000A6AA
0x18000a69d  mov     rax, [rcx]
0x18000a6a0  mov     rax, [rax+8]
0x18000a6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a9  nop
0x18000a6aa  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@_N@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18000a6b1  mov     [rdi], rax
0x18000a6b4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000a6bb  mov     [rbx], rax
0x18000a6be  mov     dword ptr [rdi+30h], 0
0x18000a6c5  lea     rcx, [rdi+38h]
0x18000a6c9  mov     qword ptr [rcx], 0
0x18000a6d0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a6d5  mov     ebx, eax
0x18000a6d7  test    eax, eax
0x18000a6d9  jns     short loc_18000A724
0x18000a6db  mov     rcx, [rbp+28h]; this
0x18000a6df  mov     r9d, eax; char *
0x18000a6e2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a6e9  mov     edx, 62Bh; void *
0x18000a6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6f3  nop
0x18000a6f4  mov     rax, [rdi]
0x18000a6f7  mov     rcx, rdi
0x18000a6fa  mov     rax, [rax+10h]
0x18000a6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a703  nop
0x18000a704  mov     rcx, [rbp+28h]; this
0x18000a708  mov     r9d, ebx; char *
0x18000a70b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a712  mov     edx, 648h; void *
0x18000a717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a71c  nop
0x18000a71d  mov     eax, ebx
0x18000a71f  jmp     loc_18000A8B4
0x18000a724  mov     rax, [rdi]
0x18000a727  mov     rcx, rdi
0x18000a72a  mov     rax, [rax+8]
0x18000a72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a733  nop
0x18000a734  mov     rax, [rdi]
0x18000a737  mov     rcx, rdi
0x18000a73a  mov     rax, [rax+10h]
0x18000a73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a743  nop
0x18000a744  mov     rax, [r14]
0x18000a747  mov     rdx, rdi
0x18000a74a  mov     rcx, r14
0x18000a74d  mov     rax, [rax+30h]
0x18000a751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a756  mov     ebx, eax
0x18000a758  test    eax, eax
0x18000a75a  jns     short loc_18000A787
0x18000a75c  mov     rcx, [rbp+28h]; this
0x18000a760  mov     r9d, eax; char *
0x18000a763  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a76a  mov     edx, 649h; void *
0x18000a76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a774  nop
0x18000a775  mov     rcx, [rdi]
0x18000a778  mov     rax, [rcx+10h]
0x18000a77c  mov     rcx, rdi
0x18000a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a784  nop
0x18000a785  jmp     short loc_18000A71D
0x18000a787  mov     rax, [rdi+38h]
0x18000a78b  mov     [rbp+pHandles], rax
0x18000a78f  mov     [rbp+dwindex], 0
0x18000a796  lea     rax, [rbp+dwindex]
0x18000a79a  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18000a79f  lea     r9, [rbp+pHandles]; pHandles
0x18000a7a3  mov     r8d, 1; cHandles
0x18000a7a9  mov     edx, r15d; dwTimeout
0x18000a7ac  lea     ecx, [r8+7]; dwFlags
0x18000a7b0  call    cs:__imp_CoWaitForMultipleHandles
0x18000a7b6  mov     ebx, eax
0x18000a7b8  test    rsi, rsi
0x18000a7bb  jz      short loc_18000A7DC
0x18000a7bd  cmp     eax, 80010115h
0x18000a7c2  jnz     short loc_18000A7DC
0x18000a7c4  mov     byte ptr [rsi], 1
0x18000a7c7  mov     rax, [rdi]
0x18000a7ca  mov     rcx, rdi
0x18000a7cd  mov     rax, [rax+10h]
0x18000a7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d6  nop
0x18000a7d7  jmp     loc_18000A8B2
0x18000a7dc  test    ebx, ebx
0x18000a7de  jns     short loc_18000A80E
0x18000a7e0  mov     rcx, [rbp+28h]; this
0x18000a7e4  mov     r9d, ebx; char *
0x18000a7e7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a7ee  mov     edx, 655h; void *
0x18000a7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7f8  nop
0x18000a7f9  mov     rax, [rdi]
0x18000a7fc  mov     rcx, rdi
0x18000a7ff  mov     rax, [rax+10h]
0x18000a803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a808  nop
0x18000a809  jmp     loc_18000A71D
0x18000a80e  mov     eax, [rdi+30h]
0x18000a811  cmp     eax, 1
0x18000a814  jz      loc_18000A8A2
0x18000a81a  mov     [rbp+var_10], 0
0x18000a822  mov     rax, [r14]
0x18000a825  mov     rbx, [rax]
0x18000a828  lea     rcx, [rbp+var_10]
0x18000a82c  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000a831  mov     r8, rax
0x18000a834  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000a83b  mov     rcx, r14
0x18000a83e  mov     rax, rbx
0x18000a841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a846  mov     ebx, eax
0x18000a848  test    eax, eax
0x18000a84a  js      short loc_18000A86F
0x18000a84c  mov     [rbp+arg_8], 8000FFFFh
0x18000a853  mov     rcx, [rbp+var_10]
0x18000a857  mov     rax, [rcx]
0x18000a85a  lea     rdx, [rbp+arg_8]
0x18000a85e  mov     rax, [rax+40h]
0x18000a862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a867  mov     ebx, eax
0x18000a869  test    eax, eax
0x18000a86b  cmovns  ebx, [rbp+arg_8]
0x18000a86f  mov     rcx, [rbp+var_10]
0x18000a873  test    rcx, rcx
0x18000a876  jz      short loc_18000A88D
0x18000a878  mov     [rbp+var_10], 0
0x18000a880  mov     rax, [rcx]
0x18000a883  mov     rax, [rax+10h]
0x18000a887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a88c  nop
0x18000a88d  mov     rax, [rdi]
0x18000a890  mov     rcx, rdi
0x18000a893  mov     rax, [rax+10h]
0x18000a897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89c  nop
0x18000a89d  jmp     loc_18000A71D
0x18000a8a2  mov     rax, [rdi]
0x18000a8a5  mov     rcx, rdi
0x18000a8a8  mov     rax, [rax+10h]
0x18000a8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b1  nop
0x18000a8b2  xor     eax, eax
0x18000a8b4  mov     rbx, [rsp+40h+arg_0]
0x18000a8b9  add     rsp, 40h
0x18000a8bd  pop     r15
0x18000a8bf  pop     r14
0x18000a8c1  pop     rdi
0x18000a8c2  pop     rsi
0x18000a8c3  pop     rbp
0x18000a8c4  retn
```
