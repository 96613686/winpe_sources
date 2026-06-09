# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000a608`
- end: `0x18000a8c0`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `696`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int, DWORD, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012da0`

## callees

- `0x180004638`
- `0x180009c6c`
- `0x18000a608`
- `0x18000a944`
- `0x180010764`
- `0x180012284`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a7a4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a7a4`

## string_xrefs

- `0x18000a6d6`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a6ff`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a757`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000a7e1`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        DWORD a3,
        _BYTE *a4)
{
  char *v7; // rdi
  unsigned int v8; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v11; // eax
  HRESULT v12; // eax
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v14; // rax
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
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z();
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
  v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v7);
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
0x18000a608  mov     [rsp-28h+arg_0], rbx
0x18000a60d  mov     [rsp-28h+arg_8], edx
0x18000a611  push    rbp
0x18000a612  push    rsi
0x18000a613  push    rdi
0x18000a614  push    r14
0x18000a616  push    r15
0x18000a618  mov     rbp, rsp
0x18000a61b  sub     rsp, 40h
0x18000a61f  mov     rsi, r9
0x18000a622  mov     r15d, r8d
0x18000a625  mov     r14, rcx
0x18000a628  test    r9, r9
0x18000a62b  jz      short loc_18000A631
0x18000a62d  mov     byte ptr [r9], 0
0x18000a631  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a638  mov     ecx, 40h ; '@'; unsigned __int64
0x18000a63d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a642  mov     rdi, rax
0x18000a645  test    rax, rax
0x18000a648  jnz     short loc_18000A654
0x18000a64a  mov     ebx, 8007000Eh
0x18000a64f  jmp     loc_18000A6F8
0x18000a654  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x18000a65b  mov     [rdi], rax
0x18000a65e  lea     rbx, [rdi+8]
0x18000a662  mov     rcx, rbx; this
0x18000a665  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000a66a  mov     dword ptr [rdi+2Ch], 1
0x18000a671  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18000a678  mov     [rdi], rax
0x18000a67b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000a682  mov     [rbx], rax
0x18000a685  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a68c  test    rcx, rcx
0x18000a68f  jz      short loc_18000A69E
0x18000a691  mov     rax, [rcx]
0x18000a694  mov     rax, [rax+8]
0x18000a698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a69d  nop
0x18000a69e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@_N@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18000a6a5  mov     [rdi], rax
0x18000a6a8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000a6af  mov     [rbx], rax
0x18000a6b2  mov     dword ptr [rdi+30h], 0
0x18000a6b9  lea     rcx, [rdi+38h]
0x18000a6bd  mov     qword ptr [rcx], 0
0x18000a6c4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a6c9  mov     ebx, eax
0x18000a6cb  test    eax, eax
0x18000a6cd  jns     short loc_18000A718
0x18000a6cf  mov     rcx, [rbp+28h]; this
0x18000a6d3  mov     r9d, eax; char *
0x18000a6d6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a6dd  mov     edx, 62Bh; void *
0x18000a6e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6e7  nop
0x18000a6e8  mov     rax, [rdi]
0x18000a6eb  mov     rcx, rdi
0x18000a6ee  mov     rax, [rax+10h]
0x18000a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f7  nop
0x18000a6f8  mov     rcx, [rbp+28h]; this
0x18000a6fc  mov     r9d, ebx; char *
0x18000a6ff  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a706  mov     edx, 648h; void *
0x18000a70b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a710  nop
0x18000a711  mov     eax, ebx
0x18000a713  jmp     loc_18000A8AE
0x18000a718  mov     rax, [rdi]
0x18000a71b  mov     rcx, rdi
0x18000a71e  mov     rax, [rax+8]
0x18000a722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a727  nop
0x18000a728  mov     rax, [rdi]
0x18000a72b  mov     rcx, rdi
0x18000a72e  mov     rax, [rax+10h]
0x18000a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a737  nop
0x18000a738  mov     rax, [r14]
0x18000a73b  mov     rdx, rdi
0x18000a73e  mov     rcx, r14
0x18000a741  mov     rax, [rax+30h]
0x18000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74a  mov     ebx, eax
0x18000a74c  test    eax, eax
0x18000a74e  jns     short loc_18000A77B
0x18000a750  mov     rcx, [rbp+28h]; this
0x18000a754  mov     r9d, eax; char *
0x18000a757  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a75e  mov     edx, 649h; void *
0x18000a763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a768  nop
0x18000a769  mov     rcx, [rdi]
0x18000a76c  mov     rax, [rcx+10h]
0x18000a770  mov     rcx, rdi
0x18000a773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a778  nop
0x18000a779  jmp     short loc_18000A711
0x18000a77b  mov     rax, [rdi+38h]
0x18000a77f  mov     [rbp+pHandles], rax
0x18000a783  mov     [rbp+dwindex], 0
0x18000a78a  lea     rax, [rbp+dwindex]
0x18000a78e  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18000a793  lea     r9, [rbp+pHandles]; pHandles
0x18000a797  mov     r8d, 1; cHandles
0x18000a79d  mov     edx, r15d; dwTimeout
0x18000a7a0  lea     ecx, [r8+7]; dwFlags
0x18000a7a4  call    cs:__imp_CoWaitForMultipleHandles
0x18000a7ab  nop     dword ptr [rax+rax+00h]
0x18000a7b0  mov     ebx, eax
0x18000a7b2  test    rsi, rsi
0x18000a7b5  jz      short loc_18000A7D6
0x18000a7b7  cmp     eax, 80010115h
0x18000a7bc  jnz     short loc_18000A7D6
0x18000a7be  mov     byte ptr [rsi], 1
0x18000a7c1  mov     rax, [rdi]
0x18000a7c4  mov     rcx, rdi
0x18000a7c7  mov     rax, [rax+10h]
0x18000a7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d0  nop
0x18000a7d1  jmp     loc_18000A8AC
0x18000a7d6  test    ebx, ebx
0x18000a7d8  jns     short loc_18000A808
0x18000a7da  mov     rcx, [rbp+28h]; this
0x18000a7de  mov     r9d, ebx; char *
0x18000a7e1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a7e8  mov     edx, 655h; void *
0x18000a7ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7f2  nop
0x18000a7f3  mov     rax, [rdi]
0x18000a7f6  mov     rcx, rdi
0x18000a7f9  mov     rax, [rax+10h]
0x18000a7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a802  nop
0x18000a803  jmp     loc_18000A711
0x18000a808  mov     eax, [rdi+30h]
0x18000a80b  cmp     eax, 1
0x18000a80e  jz      loc_18000A89C
0x18000a814  mov     [rbp+var_10], 0
0x18000a81c  mov     rax, [r14]
0x18000a81f  mov     rbx, [rax]
0x18000a822  lea     rcx, [rbp+var_10]
0x18000a826  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000a82b  mov     r8, rax
0x18000a82e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000a835  mov     rcx, r14
0x18000a838  mov     rax, rbx
0x18000a83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a840  mov     ebx, eax
0x18000a842  test    eax, eax
0x18000a844  js      short loc_18000A869
0x18000a846  mov     [rbp+arg_8], 8000FFFFh
0x18000a84d  mov     rcx, [rbp+var_10]
0x18000a851  mov     rax, [rcx]
0x18000a854  lea     rdx, [rbp+arg_8]
0x18000a858  mov     rax, [rax+40h]
0x18000a85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a861  mov     ebx, eax
0x18000a863  test    eax, eax
0x18000a865  cmovns  ebx, [rbp+arg_8]
0x18000a869  mov     rcx, [rbp+var_10]
0x18000a86d  test    rcx, rcx
0x18000a870  jz      short loc_18000A887
0x18000a872  mov     [rbp+var_10], 0
0x18000a87a  mov     rax, [rcx]
0x18000a87d  mov     rax, [rax+10h]
0x18000a881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a886  nop
0x18000a887  mov     rax, [rdi]
0x18000a88a  mov     rcx, rdi
0x18000a88d  mov     rax, [rax+10h]
0x18000a891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a896  nop
0x18000a897  jmp     loc_18000A711
0x18000a89c  mov     rax, [rdi]
0x18000a89f  mov     rcx, rdi
0x18000a8a2  mov     rax, [rax+10h]
0x18000a8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ab  nop
0x18000a8ac  xor     eax, eax
0x18000a8ae  mov     rbx, [rsp+40h+arg_0]
0x18000a8b3  add     rsp, 40h
0x18000a8b7  pop     r15
0x18000a8b9  pop     r14
0x18000a8bb  pop     rdi
0x18000a8bc  pop     rsi
0x18000a8bd  pop     rbp
0x18000a8be  retn
```
