# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18004b4b0`
- end: `0x18004b72f`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `639`
- prototype: `__int64(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004bc48`

## callees

- `0x180005d6c`
- `0x180009084`
- `0x18004b2c4`
- `0x18004b4b0`
- `0x18004bd54`
- `0x18004f710`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b642`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b642`

## string_xrefs

- `0x18004b574`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b59d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b5f5`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18004b655`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18004b4b0  mov     rax, rsp
0x18004b4b3  mov     [rax+8], rbx
0x18004b4b7  mov     [rax+20h], r9
0x18004b4bb  mov     [rax+18h], r8d
0x18004b4bf  mov     [rax+10h], edx
0x18004b4c2  push    rbp
0x18004b4c3  push    rsi
0x18004b4c4  push    rdi
0x18004b4c5  mov     rbp, rsp
0x18004b4c8  sub     rsp, 40h
0x18004b4cc  mov     rsi, rcx
0x18004b4cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b4d6  mov     ecx, 40h ; '@'; unsigned __int64
0x18004b4db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b4e0  mov     rdi, rax
0x18004b4e3  test    rax, rax
0x18004b4e6  jnz     short loc_18004B4F2
0x18004b4e8  mov     ebx, 8007000Eh
0x18004b4ed  jmp     loc_18004B596
0x18004b4f2  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x18004b4f9  mov     [rdi], rax
0x18004b4fc  lea     rbx, [rdi+8]
0x18004b500  mov     rcx, rbx
0x18004b503  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18004b508  mov     dword ptr [rdi+2Ch], 1
0x18004b50f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x18004b516  mov     [rdi], rax
0x18004b519  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004b520  mov     [rbx], rax
0x18004b523  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004b52a  test    rcx, rcx
0x18004b52d  jz      short loc_18004B53C
0x18004b52f  mov     rax, [rcx]
0x18004b532  mov     rax, [rax+8]
0x18004b536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b53b  nop
0x18004b53c  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x18004b543  mov     [rdi], rax
0x18004b546  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004b54d  mov     [rbx], rax
0x18004b550  mov     dword ptr [rdi+30h], 0
0x18004b557  lea     rcx, [rdi+38h]
0x18004b55b  mov     qword ptr [rcx], 0
0x18004b562  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004b567  mov     ebx, eax
0x18004b569  test    eax, eax
0x18004b56b  jns     short loc_18004B5B6
0x18004b56d  mov     rcx, [rbp+18h]; this
0x18004b571  mov     r9d, eax; char *
0x18004b574  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b57b  mov     edx, 62Bh; void *
0x18004b580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b585  nop
0x18004b586  mov     rax, [rdi]
0x18004b589  mov     rcx, rdi
0x18004b58c  mov     rax, [rax+10h]
0x18004b590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b595  nop
0x18004b596  mov     rcx, [rbp+18h]; this
0x18004b59a  mov     r9d, ebx; char *
0x18004b59d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b5a4  mov     edx, 648h; void *
0x18004b5a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b5ae  nop
0x18004b5af  mov     eax, ebx
0x18004b5b1  jmp     loc_18004B722
0x18004b5b6  mov     rax, [rdi]
0x18004b5b9  mov     rcx, rdi
0x18004b5bc  mov     rax, [rax+8]
0x18004b5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5c5  nop
0x18004b5c6  mov     rax, [rdi]
0x18004b5c9  mov     rcx, rdi
0x18004b5cc  mov     rax, [rax+10h]
0x18004b5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5d5  nop
0x18004b5d6  mov     rax, [rsi]
0x18004b5d9  mov     rdx, rdi
0x18004b5dc  mov     rcx, rsi
0x18004b5df  mov     rax, [rax+30h]
0x18004b5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5e8  mov     ebx, eax
0x18004b5ea  test    eax, eax
0x18004b5ec  jns     short loc_18004B619
0x18004b5ee  mov     rcx, [rbp+18h]; this
0x18004b5f2  mov     r9d, eax; char *
0x18004b5f5  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b5fc  mov     edx, 649h; void *
0x18004b601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b606  nop
0x18004b607  mov     rcx, [rdi]
0x18004b60a  mov     rax, [rcx+10h]
0x18004b60e  mov     rcx, rdi
0x18004b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b616  nop
0x18004b617  jmp     short loc_18004B5AF
0x18004b619  mov     rax, [rdi+38h]
0x18004b61d  mov     [rbp+pHandles], rax
0x18004b621  mov     [rbp+dwindex], 0
0x18004b628  lea     rax, [rbp+dwindex]
0x18004b62c  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18004b631  lea     r9, [rbp+pHandles]; pHandles
0x18004b635  mov     r8d, 1; cHandles
0x18004b63b  or      edx, 0FFFFFFFFh; dwTimeout
0x18004b63e  lea     ecx, [r8+7]; dwFlags
0x18004b642  call    cs:__imp_CoWaitForMultipleHandles
0x18004b648  mov     ebx, eax
0x18004b64a  test    eax, eax
0x18004b64c  jns     short loc_18004B67C
0x18004b64e  mov     rcx, [rbp+18h]; this
0x18004b652  mov     r9d, eax; char *
0x18004b655  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b65c  mov     edx, 655h; void *
0x18004b661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b666  nop
0x18004b667  mov     rcx, [rdi]
0x18004b66a  mov     rax, [rcx+10h]
0x18004b66e  mov     rcx, rdi
0x18004b671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b676  nop
0x18004b677  jmp     loc_18004B5AF
0x18004b67c  mov     eax, [rdi+30h]
0x18004b67f  cmp     eax, 1
0x18004b682  jz      loc_18004B710
0x18004b688  mov     [rbp+arg_18], 0
0x18004b690  mov     rax, [rsi]
0x18004b693  mov     rbx, [rax]
0x18004b696  lea     rcx, [rbp+arg_18]
0x18004b69a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18004b69f  mov     r8, rax
0x18004b6a2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18004b6a9  mov     rcx, rsi
0x18004b6ac  mov     rax, rbx
0x18004b6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6b4  mov     ebx, eax
0x18004b6b6  test    eax, eax
0x18004b6b8  js      short loc_18004B6DD
0x18004b6ba  mov     [rbp+arg_10], 8000FFFFh
0x18004b6c1  mov     rcx, [rbp+arg_18]
0x18004b6c5  mov     rax, [rcx]
0x18004b6c8  lea     rdx, [rbp+arg_10]
0x18004b6cc  mov     rax, [rax+40h]
0x18004b6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6d5  mov     ebx, eax
0x18004b6d7  test    eax, eax
0x18004b6d9  cmovns  ebx, [rbp+arg_10]
0x18004b6dd  mov     rcx, [rbp+arg_18]
0x18004b6e1  test    rcx, rcx
0x18004b6e4  jz      short loc_18004B6FB
0x18004b6e6  mov     [rbp+arg_18], 0
0x18004b6ee  mov     rax, [rcx]
0x18004b6f1  mov     rax, [rax+10h]
0x18004b6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6fa  nop
0x18004b6fb  mov     rax, [rdi]
0x18004b6fe  mov     rcx, rdi
0x18004b701  mov     rax, [rax+10h]
0x18004b705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b70a  nop
0x18004b70b  jmp     loc_18004B5AF
0x18004b710  mov     rax, [rdi]
0x18004b713  mov     rcx, rdi
0x18004b716  mov     rax, [rax+10h]
0x18004b71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b71f  nop
0x18004b720  xor     eax, eax
0x18004b722  mov     rbx, [rsp+40h+arg_0]
0x18004b727  add     rsp, 40h
0x18004b72b  pop     rdi
0x18004b72c  pop     rsi
0x18004b72d  pop     rbp
0x18004b72e  retn
```
