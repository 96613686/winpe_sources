# wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140040574`
- end: `0x140040802`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `654`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003f96c`

## callees

- `0x140008de4`
- `0x140040574`
- `0x140040b4c`
- `0x140040e14`
- `0x140045dc0`
- `0x140045df0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14004070f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14004070f`

## string_xrefs

- `0x140040641`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x14004066a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x1400406c2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x140040722`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
        __int64 a1)
{
  char *v2; // rbx
  unsigned int v3; // edi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v6; // eax
  HRESULT v7; // eax
  __int64 v8; // rcx
  int lpdwindex; // [rsp+20h] [rbp-40h]
  int lpdwindexa; // [rsp+20h] [rbp-40h]
  int v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+40h] [rbp-20h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
  {
    v3 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v3,
      lpdwindex);
    return v3;
  }
  *(_QWORD *)v2 = &ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v2 + 8);
  *((_DWORD *)v2 + 11) = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 7) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z();
  v3 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x629,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v2);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x647,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
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
      (void *)0x653,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v7,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  if ( *((_DWORD *)v2 + 12) != 1 )
  {
    v12 = 0;
    v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           &v12);
    if ( (v3 & 0x80000000) == 0 )
    {
      v11 = -2147418113;
      v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v11);
      if ( (v3 & 0x80000000) == 0 )
        v3 = v11;
    }
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
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
0x140040574  mov     [rsp-8+arg_8], rbx
0x140040579  mov     [rsp-8+arg_10], rsi
0x14004057e  mov     [rsp-8+arg_18], rdi
0x140040583  push    rbp
0x140040584  mov     rbp, rsp
0x140040587  sub     rsp, 60h
0x14004058b  mov     rax, cs:__security_cookie
0x140040592  xor     rax, rsp
0x140040595  mov     [rbp+var_10], rax
0x140040599  mov     rsi, rcx
0x14004059c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400405a3  mov     ecx, 40h ; '@'; unsigned __int64
0x1400405a8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400405ad  mov     rbx, rax
0x1400405b0  test    rax, rax
0x1400405b3  jnz     short loc_1400405BF
0x1400405b5  mov     edi, 8007000Eh
0x1400405ba  jmp     loc_140040663
0x1400405bf  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@6B@; const ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>::`vftable'
0x1400405c6  mov     [rbx], rax
0x1400405c9  lea     rdi, [rbx+8]
0x1400405cd  mov     rcx, rdi
0x1400405d0  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1400405d5  mov     dword ptr [rbx+2Ch], 1
0x1400405dc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x1400405e3  mov     [rbx], rax
0x1400405e6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400405ed  mov     [rdi], rax
0x1400405f0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400405f7  test    rcx, rcx
0x1400405fa  jz      short loc_140040609
0x1400405fc  mov     rax, [rcx]
0x1400405ff  mov     rax, [rax+8]
0x140040603  call    _guard_dispatch_icall
0x140040608  nop
0x140040609  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@456@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x140040610  mov     [rbx], rax
0x140040613  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14004061a  mov     [rdi], rax
0x14004061d  mov     dword ptr [rbx+30h], 0
0x140040624  lea     rcx, [rbx+38h]
0x140040628  mov     qword ptr [rcx], 0
0x14004062f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140040634  mov     edi, eax
0x140040636  test    eax, eax
0x140040638  jns     short loc_140040683
0x14004063a  mov     rcx, [rbp+8]; this
0x14004063e  mov     r9d, eax; char *
0x140040641  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140040648  mov     edx, 629h; void *
0x14004064d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040652  nop
0x140040653  mov     rax, [rbx]
0x140040656  mov     rcx, rbx
0x140040659  mov     rax, [rax+10h]
0x14004065d  call    _guard_dispatch_icall
0x140040662  nop
0x140040663  mov     rcx, [rbp+8]; this
0x140040667  mov     r9d, edi; char *
0x14004066a  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140040671  mov     edx, 646h; void *
0x140040676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004067b  nop
0x14004067c  mov     eax, edi
0x14004067e  jmp     loc_1400407E0
0x140040683  mov     rax, [rbx]
0x140040686  mov     rcx, rbx
0x140040689  mov     rax, [rax+8]
0x14004068d  call    _guard_dispatch_icall
0x140040692  nop
0x140040693  mov     rax, [rbx]
0x140040696  mov     rcx, rbx
0x140040699  mov     rax, [rax+10h]
0x14004069d  call    _guard_dispatch_icall
0x1400406a2  nop
0x1400406a3  mov     rax, [rsi]
0x1400406a6  mov     rdx, rbx
0x1400406a9  mov     rcx, rsi
0x1400406ac  mov     rax, [rax+30h]
0x1400406b0  call    _guard_dispatch_icall
0x1400406b5  mov     edi, eax
0x1400406b7  test    eax, eax
0x1400406b9  jns     short loc_1400406E6
0x1400406bb  mov     rcx, [rbp+8]; this
0x1400406bf  mov     r9d, eax; char *
0x1400406c2  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400406c9  mov     edx, 647h; void *
0x1400406ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400406d3  nop
0x1400406d4  mov     rcx, [rbx]
0x1400406d7  mov     rax, [rcx+10h]
0x1400406db  mov     rcx, rbx
0x1400406de  call    _guard_dispatch_icall
0x1400406e3  nop
0x1400406e4  jmp     short loc_14004067C
0x1400406e6  mov     rax, [rbx+38h]
0x1400406ea  mov     [rbp+pHandles], rax
0x1400406ee  mov     [rbp+dwindex], 0
0x1400406f5  lea     rax, [rbp+dwindex]
0x1400406f9  mov     qword ptr [rsp+60h+lpdwindex], rax; int
0x1400406fe  lea     r9, [rbp+pHandles]; pHandles
0x140040702  mov     r8d, 1; cHandles
0x140040708  or      edx, 0FFFFFFFFh; dwTimeout
0x14004070b  lea     ecx, [r8+7]; dwFlags
0x14004070f  call    cs:__imp_CoWaitForMultipleHandles
0x140040715  mov     edi, eax
0x140040717  test    eax, eax
0x140040719  jns     short loc_140040749
0x14004071b  mov     rcx, [rbp+8]; this
0x14004071f  mov     r9d, eax; char *
0x140040722  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140040729  mov     edx, 653h; void *
0x14004072e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040733  nop
0x140040734  mov     rcx, [rbx]
0x140040737  mov     rax, [rcx+10h]
0x14004073b  mov     rcx, rbx
0x14004073e  call    _guard_dispatch_icall
0x140040743  nop
0x140040744  jmp     loc_14004067C
0x140040749  mov     eax, [rbx+30h]
0x14004074c  cmp     eax, 1
0x14004074f  jz      short loc_1400407CE
0x140040751  mov     [rbp+var_28], 0
0x140040759  mov     rax, [rsi]
0x14004075c  lea     r8, [rbp+var_28]
0x140040760  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140040767  mov     rcx, rsi
0x14004076a  mov     rax, [rax]
0x14004076d  call    _guard_dispatch_icall
0x140040772  mov     edi, eax
0x140040774  test    eax, eax
0x140040776  js      short loc_14004079B
0x140040778  mov     [rbp+var_30], 8000FFFFh
0x14004077f  mov     rcx, [rbp+var_28]
0x140040783  mov     rax, [rcx]
0x140040786  lea     rdx, [rbp+var_30]
0x14004078a  mov     rax, [rax+40h]
0x14004078e  call    _guard_dispatch_icall
0x140040793  mov     edi, eax
0x140040795  test    eax, eax
0x140040797  cmovns  edi, [rbp+var_30]
0x14004079b  mov     rcx, [rbp+var_28]
0x14004079f  test    rcx, rcx
0x1400407a2  jz      short loc_1400407B9
0x1400407a4  mov     [rbp+var_28], 0
0x1400407ac  mov     rax, [rcx]
0x1400407af  mov     rax, [rax+10h]
0x1400407b3  call    _guard_dispatch_icall
0x1400407b8  nop
0x1400407b9  mov     rax, [rbx]
0x1400407bc  mov     rcx, rbx
0x1400407bf  mov     rax, [rax+10h]
0x1400407c3  call    _guard_dispatch_icall
0x1400407c8  nop
0x1400407c9  jmp     loc_14004067C
0x1400407ce  mov     rax, [rbx]
0x1400407d1  mov     rcx, rbx
0x1400407d4  mov     rax, [rax+10h]
0x1400407d8  call    _guard_dispatch_icall
0x1400407dd  nop
0x1400407de  xor     eax, eax
0x1400407e0  mov     rcx, [rbp+var_10]
0x1400407e4  xor     rcx, rsp; StackCookie
0x1400407e7  call    __security_check_cookie
0x1400407ec  lea     r11, [rsp+60h+var_s0]
0x1400407f1  mov     rbx, [r11+18h]
0x1400407f5  mov     rsi, [r11+20h]
0x1400407f9  mov     rdi, [r11+28h]
0x1400407fd  mov     rsp, r11
0x140040800  pop     rbp
0x140040801  retn
```
