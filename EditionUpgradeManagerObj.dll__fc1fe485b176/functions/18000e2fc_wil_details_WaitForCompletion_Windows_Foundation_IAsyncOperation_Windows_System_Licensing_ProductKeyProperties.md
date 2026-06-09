# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000e2fc`
- end: `0x18000e53d`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
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
- `0x18000e2fc`
- `0x18000ed8c`
- `0x180017b1c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e486`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e486`

## string_xrefs

- `0x18000e3bc`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e3e3`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e43d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>'};
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>'::`2'::CompletionDelegate::`vftable';
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>'::`2'::CompletionDelegate::`vftable';
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
0x18000e2fc  mov     rax, rsp
0x18000e2ff  mov     [rax+8], rbx
0x18000e303  mov     [rax+20h], r9
0x18000e307  mov     [rax+18h], r8d
0x18000e30b  mov     [rax+10h], edx
0x18000e30e  push    rbp
0x18000e30f  push    rsi
0x18000e310  push    rdi
0x18000e311  mov     rbp, rsp
0x18000e314  sub     rsp, 40h
0x18000e318  mov     rsi, rcx
0x18000e31b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e322  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e327  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e32c  mov     rdi, rax
0x18000e32f  test    rax, rax
0x18000e332  jnz     short loc_18000E33E
0x18000e334  mov     ebx, 8007000Eh
0x18000e339  jmp     loc_18000E3DF
0x18000e33e  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000e345  lea     rbx, [rdi+8]
0x18000e349  mov     [rdi], rax
0x18000e34c  mov     rcx, rbx; this
0x18000e34f  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e354  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e35b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>'}
0x18000e362  mov     [rdi], rax
0x18000e365  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e36c  mov     [rbx], rax
0x18000e36f  mov     dword ptr [rdi+2Ch], 1
0x18000e376  test    rcx, rcx
0x18000e379  jz      short loc_18000E387
0x18000e37b  mov     rax, [rcx]
0x18000e37e  mov     rax, [rax+8]
0x18000e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e387  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVProductKeyProperties@Licensing@System@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>'}
0x18000e38e  mov     [rdi], rax
0x18000e391  lea     rcx, [rdi+38h]
0x18000e395  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e39c  mov     qword ptr [rcx], 0
0x18000e3a3  mov     [rbx], rax
0x18000e3a6  mov     dword ptr [rdi+30h], 0
0x18000e3ad  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e3b2  mov     ebx, eax
0x18000e3b4  test    eax, eax
0x18000e3b6  jns     short loc_18000E3FE
0x18000e3b8  mov     rcx, [rbp+18h]; this
0x18000e3bc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e3c3  mov     r9d, eax; char *
0x18000e3c6  mov     edx, 62Bh; void *
0x18000e3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3d0  mov     rcx, [rdi]
0x18000e3d3  mov     rax, [rcx+10h]
0x18000e3d7  mov     rcx, rdi
0x18000e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3df  mov     rcx, [rbp+18h]; this
0x18000e3e3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e3ea  mov     r9d, ebx; char *
0x18000e3ed  mov     edx, 648h; void *
0x18000e3f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3f7  mov     eax, ebx
0x18000e3f9  jmp     loc_18000E530
0x18000e3fe  mov     rax, [rdi]
0x18000e401  mov     rcx, rdi
0x18000e404  mov     rax, [rax+8]
0x18000e408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40d  mov     rax, [rdi]
0x18000e410  mov     rcx, rdi
0x18000e413  mov     rax, [rax+10h]
0x18000e417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e41c  mov     rax, [rsi]
0x18000e41f  mov     rdx, rdi
0x18000e422  mov     rcx, rsi
0x18000e425  mov     rax, [rax+30h]
0x18000e429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42e  mov     ebx, eax
0x18000e430  test    eax, eax
0x18000e432  jns     short loc_18000E45D
0x18000e434  mov     edx, 649h; void *
0x18000e439  mov     rcx, [rbp+18h]; this
0x18000e43d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e444  mov     r9d, ebx; char *
0x18000e447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e44c  mov     rcx, [rdi]
0x18000e44f  mov     rax, [rcx+10h]
0x18000e453  mov     rcx, rdi
0x18000e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45b  jmp     short loc_18000E3F7
0x18000e45d  mov     rax, [rdi+38h]
0x18000e461  lea     r9, [rbp+pHandles]; pHandles
0x18000e465  mov     r8d, 1; cHandles
0x18000e46b  mov     [rbp+pHandles], rax
0x18000e46f  lea     rax, [rbp+dwindex]
0x18000e473  mov     [rbp+dwindex], 0
0x18000e47a  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e47d  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000e482  lea     ecx, [r8+7]; dwFlags
0x18000e486  call    cs:__imp_CoWaitForMultipleHandles
0x18000e48c  mov     ebx, eax
0x18000e48e  test    eax, eax
0x18000e490  jns     short loc_18000E499
0x18000e492  mov     edx, 655h
0x18000e497  jmp     short loc_18000E439
0x18000e499  mov     eax, [rdi+30h]
0x18000e49c  cmp     eax, 1
0x18000e49f  jz      short loc_18000E51F
0x18000e4a1  mov     rax, [rsi]
0x18000e4a4  lea     rcx, [rbp+arg_18]
0x18000e4a8  mov     [rbp+arg_18], 0
0x18000e4b0  mov     rbx, [rax]
0x18000e4b3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e4b8  mov     r8, rax
0x18000e4bb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e4c2  mov     rax, rbx
0x18000e4c5  mov     rcx, rsi
0x18000e4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4cd  mov     ebx, eax
0x18000e4cf  test    eax, eax
0x18000e4d1  js      short loc_18000E4F6
0x18000e4d3  mov     rcx, [rbp+arg_18]
0x18000e4d7  lea     rdx, [rbp+arg_10]
0x18000e4db  mov     [rbp+arg_10], 8000FFFFh
0x18000e4e2  mov     rax, [rcx]
0x18000e4e5  mov     rax, [rax+40h]
0x18000e4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ee  test    eax, eax
0x18000e4f0  mov     ebx, eax
0x18000e4f2  cmovns  ebx, [rbp+arg_10]
0x18000e4f6  mov     rcx, [rbp+arg_18]
0x18000e4fa  test    rcx, rcx
0x18000e4fd  jz      short loc_18000E513
0x18000e4ff  mov     [rbp+arg_18], 0
0x18000e507  mov     rax, [rcx]
0x18000e50a  mov     rax, [rax+10h]
0x18000e50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e513  mov     rax, [rdi]
0x18000e516  mov     rax, [rax+10h]
0x18000e51a  jmp     loc_18000E453
0x18000e51f  mov     rax, [rdi]
0x18000e522  mov     rcx, rdi
0x18000e525  mov     rax, [rax+10h]
0x18000e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e52e  xor     eax, eax
0x18000e530  mov     rbx, [rsp+40h+arg_0]
0x18000e535  add     rsp, 40h
0x18000e539  pop     rdi
0x18000e53a  pop     rsi
0x18000e53b  pop     rbp
0x18000e53c  retn
```
