# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>(Windows::Foundation::IAsyncOperation<int> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000e0b4`
- end: `0x18000e2f5`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@H@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@H@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
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
- `0x18000e0b4`
- `0x18000ed8c`
- `0x180017b1c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e23e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e23e`

## string_xrefs

- `0x18000e174`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e19b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000e1f5`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<int>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000e0b4  mov     rax, rsp
0x18000e0b7  mov     [rax+8], rbx
0x18000e0bb  mov     [rax+20h], r9
0x18000e0bf  mov     [rax+18h], r8d
0x18000e0c3  mov     [rax+10h], edx
0x18000e0c6  push    rbp
0x18000e0c7  push    rsi
0x18000e0c8  push    rdi
0x18000e0c9  mov     rbp, rsp
0x18000e0cc  sub     rsp, 40h
0x18000e0d0  mov     rsi, rcx
0x18000e0d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e0da  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e0df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e0e4  mov     rdi, rax
0x18000e0e7  test    rax, rax
0x18000e0ea  jnz     short loc_18000E0F6
0x18000e0ec  mov     ebx, 8007000Eh
0x18000e0f1  jmp     loc_18000E197
0x18000e0f6  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000e0fd  lea     rbx, [rdi+8]
0x18000e101  mov     [rdi], rax
0x18000e104  mov     rcx, rbx; this
0x18000e107  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e10c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e113  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<int>'}
0x18000e11a  mov     [rdi], rax
0x18000e11d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e124  mov     [rbx], rax
0x18000e127  mov     dword ptr [rdi+2Ch], 1
0x18000e12e  test    rcx, rcx
0x18000e131  jz      short loc_18000E13F
0x18000e133  mov     rax, [rcx]
0x18000e136  mov     rax, [rax+8]
0x18000e13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e13f  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@H@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@H@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@H@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>(Windows::Foundation::IAsyncOperation<int> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<int>'}
0x18000e146  mov     [rdi], rax
0x18000e149  lea     rcx, [rdi+38h]
0x18000e14d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e154  mov     qword ptr [rcx], 0
0x18000e15b  mov     [rbx], rax
0x18000e15e  mov     dword ptr [rdi+30h], 0
0x18000e165  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e16a  mov     ebx, eax
0x18000e16c  test    eax, eax
0x18000e16e  jns     short loc_18000E1B6
0x18000e170  mov     rcx, [rbp+18h]; this
0x18000e174  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e17b  mov     r9d, eax; char *
0x18000e17e  mov     edx, 62Bh; void *
0x18000e183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e188  mov     rcx, [rdi]
0x18000e18b  mov     rax, [rcx+10h]
0x18000e18f  mov     rcx, rdi
0x18000e192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e197  mov     rcx, [rbp+18h]; this
0x18000e19b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1a2  mov     r9d, ebx; char *
0x18000e1a5  mov     edx, 648h; void *
0x18000e1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1af  mov     eax, ebx
0x18000e1b1  jmp     loc_18000E2E8
0x18000e1b6  mov     rax, [rdi]
0x18000e1b9  mov     rcx, rdi
0x18000e1bc  mov     rax, [rax+8]
0x18000e1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c5  mov     rax, [rdi]
0x18000e1c8  mov     rcx, rdi
0x18000e1cb  mov     rax, [rax+10h]
0x18000e1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d4  mov     rax, [rsi]
0x18000e1d7  mov     rdx, rdi
0x18000e1da  mov     rcx, rsi
0x18000e1dd  mov     rax, [rax+30h]
0x18000e1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1e6  mov     ebx, eax
0x18000e1e8  test    eax, eax
0x18000e1ea  jns     short loc_18000E215
0x18000e1ec  mov     edx, 649h; void *
0x18000e1f1  mov     rcx, [rbp+18h]; this
0x18000e1f5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1fc  mov     r9d, ebx; char *
0x18000e1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e204  mov     rcx, [rdi]
0x18000e207  mov     rax, [rcx+10h]
0x18000e20b  mov     rcx, rdi
0x18000e20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e213  jmp     short loc_18000E1AF
0x18000e215  mov     rax, [rdi+38h]
0x18000e219  lea     r9, [rbp+pHandles]; pHandles
0x18000e21d  mov     r8d, 1; cHandles
0x18000e223  mov     [rbp+pHandles], rax
0x18000e227  lea     rax, [rbp+dwindex]
0x18000e22b  mov     [rbp+dwindex], 0
0x18000e232  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e235  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000e23a  lea     ecx, [r8+7]; dwFlags
0x18000e23e  call    cs:__imp_CoWaitForMultipleHandles
0x18000e244  mov     ebx, eax
0x18000e246  test    eax, eax
0x18000e248  jns     short loc_18000E251
0x18000e24a  mov     edx, 655h
0x18000e24f  jmp     short loc_18000E1F1
0x18000e251  mov     eax, [rdi+30h]
0x18000e254  cmp     eax, 1
0x18000e257  jz      short loc_18000E2D7
0x18000e259  mov     rax, [rsi]
0x18000e25c  lea     rcx, [rbp+arg_18]
0x18000e260  mov     [rbp+arg_18], 0
0x18000e268  mov     rbx, [rax]
0x18000e26b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e270  mov     r8, rax
0x18000e273  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e27a  mov     rax, rbx
0x18000e27d  mov     rcx, rsi
0x18000e280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e285  mov     ebx, eax
0x18000e287  test    eax, eax
0x18000e289  js      short loc_18000E2AE
0x18000e28b  mov     rcx, [rbp+arg_18]
0x18000e28f  lea     rdx, [rbp+arg_10]
0x18000e293  mov     [rbp+arg_10], 8000FFFFh
0x18000e29a  mov     rax, [rcx]
0x18000e29d  mov     rax, [rax+40h]
0x18000e2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a6  test    eax, eax
0x18000e2a8  mov     ebx, eax
0x18000e2aa  cmovns  ebx, [rbp+arg_10]
0x18000e2ae  mov     rcx, [rbp+arg_18]
0x18000e2b2  test    rcx, rcx
0x18000e2b5  jz      short loc_18000E2CB
0x18000e2b7  mov     [rbp+arg_18], 0
0x18000e2bf  mov     rax, [rcx]
0x18000e2c2  mov     rax, [rax+10h]
0x18000e2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2cb  mov     rax, [rdi]
0x18000e2ce  mov     rax, [rax+10h]
0x18000e2d2  jmp     loc_18000E20B
0x18000e2d7  mov     rax, [rdi]
0x18000e2da  mov     rcx, rdi
0x18000e2dd  mov     rax, [rax+10h]
0x18000e2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2e6  xor     eax, eax
0x18000e2e8  mov     rbx, [rsp+40h+arg_0]
0x18000e2ed  add     rsp, 40h
0x18000e2f1  pop     rdi
0x18000e2f2  pop     rsi
0x18000e2f3  pop     rbp
0x18000e2f4  retn
```
