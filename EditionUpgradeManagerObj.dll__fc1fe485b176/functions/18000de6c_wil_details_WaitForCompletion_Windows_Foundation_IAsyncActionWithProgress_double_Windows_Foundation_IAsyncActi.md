# wil::details::WaitForCompletion<Windows::Foundation::IAsyncActionWithProgress<double> *>(Windows::Foundation::IAsyncActionWithProgress<double> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000de6c`
- end: `0x18000e0ad`
- name: `??$WaitForCompletion@PEAU?$IAsyncActionWithProgress@N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncActionWithProgress@N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
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
- `0x18000de6c`
- `0x18000ed8c`
- `0x180017b1c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dff6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dff6`

## string_xrefs

- `0x18000df2c`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000df53`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18000dfad`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncActionWithProgress<double> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncActionWithProgress<double> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), char *))(*a1)[8])(a1, v4);
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
0x18000de6c  mov     rax, rsp
0x18000de6f  mov     [rax+8], rbx
0x18000de73  mov     [rax+20h], r9
0x18000de77  mov     [rax+18h], r8d
0x18000de7b  mov     [rax+10h], edx
0x18000de7e  push    rbp
0x18000de7f  push    rsi
0x18000de80  push    rdi
0x18000de81  mov     rbp, rsp
0x18000de84  sub     rsp, 40h
0x18000de88  mov     rsi, rcx
0x18000de8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000de92  mov     ecx, 40h ; '@'; unsigned __int64
0x18000de97  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000de9c  mov     rdi, rax
0x18000de9f  test    rax, rax
0x18000dea2  jnz     short loc_18000DEAE
0x18000dea4  mov     ebx, 8007000Eh
0x18000dea9  jmp     loc_18000DF4F
0x18000deae  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000deb5  lea     rbx, [rdi+8]
0x18000deb9  mov     [rdi], rax
0x18000debc  mov     rcx, rbx; this
0x18000debf  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000dec4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000decb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>'}
0x18000ded2  mov     [rdi], rax
0x18000ded5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000dedc  mov     [rbx], rax
0x18000dedf  mov     dword ptr [rdi+2Ch], 1
0x18000dee6  test    rcx, rcx
0x18000dee9  jz      short loc_18000DEF7
0x18000deeb  mov     rax, [rcx]
0x18000deee  mov     rax, [rax+8]
0x18000def2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def7  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncActionWithProgress@N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncActionWithProgress@N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncActionWithProgressCompletedHandler@N@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncActionWithProgress<double> *>(Windows::Foundation::IAsyncActionWithProgress<double> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>'}
0x18000defe  mov     [rdi], rax
0x18000df01  lea     rcx, [rdi+38h]
0x18000df05  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000df0c  mov     qword ptr [rcx], 0
0x18000df13  mov     [rbx], rax
0x18000df16  mov     dword ptr [rdi+30h], 0
0x18000df1d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000df22  mov     ebx, eax
0x18000df24  test    eax, eax
0x18000df26  jns     short loc_18000DF6E
0x18000df28  mov     rcx, [rbp+18h]; this
0x18000df2c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000df33  mov     r9d, eax; char *
0x18000df36  mov     edx, 62Bh; void *
0x18000df3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df40  mov     rcx, [rdi]
0x18000df43  mov     rax, [rcx+10h]
0x18000df47  mov     rcx, rdi
0x18000df4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4f  mov     rcx, [rbp+18h]; this
0x18000df53  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000df5a  mov     r9d, ebx; char *
0x18000df5d  mov     edx, 648h; void *
0x18000df62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df67  mov     eax, ebx
0x18000df69  jmp     loc_18000E0A0
0x18000df6e  mov     rax, [rdi]
0x18000df71  mov     rcx, rdi
0x18000df74  mov     rax, [rax+8]
0x18000df78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df7d  mov     rax, [rdi]
0x18000df80  mov     rcx, rdi
0x18000df83  mov     rax, [rax+10h]
0x18000df87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df8c  mov     rax, [rsi]
0x18000df8f  mov     rdx, rdi
0x18000df92  mov     rcx, rsi
0x18000df95  mov     rax, [rax+40h]
0x18000df99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df9e  mov     ebx, eax
0x18000dfa0  test    eax, eax
0x18000dfa2  jns     short loc_18000DFCD
0x18000dfa4  mov     edx, 649h; void *
0x18000dfa9  mov     rcx, [rbp+18h]; this
0x18000dfad  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dfb4  mov     r9d, ebx; char *
0x18000dfb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfbc  mov     rcx, [rdi]
0x18000dfbf  mov     rax, [rcx+10h]
0x18000dfc3  mov     rcx, rdi
0x18000dfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfcb  jmp     short loc_18000DF67
0x18000dfcd  mov     rax, [rdi+38h]
0x18000dfd1  lea     r9, [rbp+pHandles]; pHandles
0x18000dfd5  mov     r8d, 1; cHandles
0x18000dfdb  mov     [rbp+pHandles], rax
0x18000dfdf  lea     rax, [rbp+dwindex]
0x18000dfe3  mov     [rbp+dwindex], 0
0x18000dfea  or      edx, 0FFFFFFFFh; dwTimeout
0x18000dfed  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000dff2  lea     ecx, [r8+7]; dwFlags
0x18000dff6  call    cs:__imp_CoWaitForMultipleHandles
0x18000dffc  mov     ebx, eax
0x18000dffe  test    eax, eax
0x18000e000  jns     short loc_18000E009
0x18000e002  mov     edx, 655h
0x18000e007  jmp     short loc_18000DFA9
0x18000e009  mov     eax, [rdi+30h]
0x18000e00c  cmp     eax, 1
0x18000e00f  jz      short loc_18000E08F
0x18000e011  mov     rax, [rsi]
0x18000e014  lea     rcx, [rbp+arg_18]
0x18000e018  mov     [rbp+arg_18], 0
0x18000e020  mov     rbx, [rax]
0x18000e023  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e028  mov     r8, rax
0x18000e02b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e032  mov     rax, rbx
0x18000e035  mov     rcx, rsi
0x18000e038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e03d  mov     ebx, eax
0x18000e03f  test    eax, eax
0x18000e041  js      short loc_18000E066
0x18000e043  mov     rcx, [rbp+arg_18]
0x18000e047  lea     rdx, [rbp+arg_10]
0x18000e04b  mov     [rbp+arg_10], 8000FFFFh
0x18000e052  mov     rax, [rcx]
0x18000e055  mov     rax, [rax+40h]
0x18000e059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e05e  test    eax, eax
0x18000e060  mov     ebx, eax
0x18000e062  cmovns  ebx, [rbp+arg_10]
0x18000e066  mov     rcx, [rbp+arg_18]
0x18000e06a  test    rcx, rcx
0x18000e06d  jz      short loc_18000E083
0x18000e06f  mov     [rbp+arg_18], 0
0x18000e077  mov     rax, [rcx]
0x18000e07a  mov     rax, [rax+10h]
0x18000e07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e083  mov     rax, [rdi]
0x18000e086  mov     rax, [rax+10h]
0x18000e08a  jmp     loc_18000DFC3
0x18000e08f  mov     rax, [rdi]
0x18000e092  mov     rcx, rdi
0x18000e095  mov     rax, [rax+10h]
0x18000e099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e09e  xor     eax, eax
0x18000e0a0  mov     rbx, [rsp+40h+arg_0]
0x18000e0a5  add     rsp, 40h
0x18000e0a9  pop     rdi
0x18000e0aa  pop     rsi
0x18000e0ab  pop     rbp
0x18000e0ac  retn
```
