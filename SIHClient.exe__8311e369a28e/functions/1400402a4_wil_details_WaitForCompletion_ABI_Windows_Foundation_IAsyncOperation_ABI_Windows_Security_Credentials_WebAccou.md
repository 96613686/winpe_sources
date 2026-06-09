# wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1400402a4`
- end: `0x140040532`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `654`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003f96c`

## callees

- `0x140008de4`
- `0x1400402a4`
- `0x140040b4c`
- `0x140040e14`
- `0x140045dc0`
- `0x140045df0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14004043f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14004043f`

## string_xrefs

- `0x140040371`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x14004039a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x1400403f2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x140040452`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(
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
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>'};
  *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>'::`2'::CompletionDelegate::`vftable';
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
0x1400402a4  mov     [rsp-8+arg_8], rbx
0x1400402a9  mov     [rsp-8+arg_10], rsi
0x1400402ae  mov     [rsp-8+arg_18], rdi
0x1400402b3  push    rbp
0x1400402b4  mov     rbp, rsp
0x1400402b7  sub     rsp, 60h
0x1400402bb  mov     rax, cs:__security_cookie
0x1400402c2  xor     rax, rsp
0x1400402c5  mov     [rbp+var_10], rax
0x1400402c9  mov     rsi, rcx
0x1400402cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400402d3  mov     ecx, 40h ; '@'; unsigned __int64
0x1400402d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400402dd  mov     rbx, rax
0x1400402e0  test    rax, rax
0x1400402e3  jnz     short loc_1400402EF
0x1400402e5  mov     edi, 8007000Eh
0x1400402ea  jmp     loc_140040393
0x1400402ef  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@6B@; const ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>::`vftable'
0x1400402f6  mov     [rbx], rax
0x1400402f9  lea     rdi, [rbx+8]
0x1400402fd  mov     rcx, rdi
0x140040300  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x140040305  mov     dword ptr [rbx+2Ch], 1
0x14004030c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>'}
0x140040313  mov     [rbx], rax
0x140040316  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14004031d  mov     [rdi], rax
0x140040320  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140040327  test    rcx, rcx
0x14004032a  jz      short loc_140040339
0x14004032c  mov     rax, [rcx]
0x14004032f  mov     rax, [rax+8]
0x140040333  call    _guard_dispatch_icall
0x140040338  nop
0x140040339  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@456@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Security::Credentials::WebAccountProvider *>'}
0x140040340  mov     [rbx], rax
0x140040343  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14004034a  mov     [rdi], rax
0x14004034d  mov     dword ptr [rbx+30h], 0
0x140040354  lea     rcx, [rbx+38h]
0x140040358  mov     qword ptr [rcx], 0
0x14004035f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140040364  mov     edi, eax
0x140040366  test    eax, eax
0x140040368  jns     short loc_1400403B3
0x14004036a  mov     rcx, [rbp+8]; this
0x14004036e  mov     r9d, eax; char *
0x140040371  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140040378  mov     edx, 629h; void *
0x14004037d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040382  nop
0x140040383  mov     rax, [rbx]
0x140040386  mov     rcx, rbx
0x140040389  mov     rax, [rax+10h]
0x14004038d  call    _guard_dispatch_icall
0x140040392  nop
0x140040393  mov     rcx, [rbp+8]; this
0x140040397  mov     r9d, edi; char *
0x14004039a  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400403a1  mov     edx, 646h; void *
0x1400403a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400403ab  nop
0x1400403ac  mov     eax, edi
0x1400403ae  jmp     loc_140040510
0x1400403b3  mov     rax, [rbx]
0x1400403b6  mov     rcx, rbx
0x1400403b9  mov     rax, [rax+8]
0x1400403bd  call    _guard_dispatch_icall
0x1400403c2  nop
0x1400403c3  mov     rax, [rbx]
0x1400403c6  mov     rcx, rbx
0x1400403c9  mov     rax, [rax+10h]
0x1400403cd  call    _guard_dispatch_icall
0x1400403d2  nop
0x1400403d3  mov     rax, [rsi]
0x1400403d6  mov     rdx, rbx
0x1400403d9  mov     rcx, rsi
0x1400403dc  mov     rax, [rax+30h]
0x1400403e0  call    _guard_dispatch_icall
0x1400403e5  mov     edi, eax
0x1400403e7  test    eax, eax
0x1400403e9  jns     short loc_140040416
0x1400403eb  mov     rcx, [rbp+8]; this
0x1400403ef  mov     r9d, eax; char *
0x1400403f2  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400403f9  mov     edx, 647h; void *
0x1400403fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040403  nop
0x140040404  mov     rcx, [rbx]
0x140040407  mov     rax, [rcx+10h]
0x14004040b  mov     rcx, rbx
0x14004040e  call    _guard_dispatch_icall
0x140040413  nop
0x140040414  jmp     short loc_1400403AC
0x140040416  mov     rax, [rbx+38h]
0x14004041a  mov     [rbp+pHandles], rax
0x14004041e  mov     [rbp+dwindex], 0
0x140040425  lea     rax, [rbp+dwindex]
0x140040429  mov     qword ptr [rsp+60h+lpdwindex], rax; int
0x14004042e  lea     r9, [rbp+pHandles]; pHandles
0x140040432  mov     r8d, 1; cHandles
0x140040438  or      edx, 0FFFFFFFFh; dwTimeout
0x14004043b  lea     ecx, [r8+7]; dwFlags
0x14004043f  call    cs:__imp_CoWaitForMultipleHandles
0x140040445  mov     edi, eax
0x140040447  test    eax, eax
0x140040449  jns     short loc_140040479
0x14004044b  mov     rcx, [rbp+8]; this
0x14004044f  mov     r9d, eax; char *
0x140040452  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140040459  mov     edx, 653h; void *
0x14004045e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040463  nop
0x140040464  mov     rcx, [rbx]
0x140040467  mov     rax, [rcx+10h]
0x14004046b  mov     rcx, rbx
0x14004046e  call    _guard_dispatch_icall
0x140040473  nop
0x140040474  jmp     loc_1400403AC
0x140040479  mov     eax, [rbx+30h]
0x14004047c  cmp     eax, 1
0x14004047f  jz      short loc_1400404FE
0x140040481  mov     [rbp+var_28], 0
0x140040489  mov     rax, [rsi]
0x14004048c  lea     r8, [rbp+var_28]
0x140040490  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140040497  mov     rcx, rsi
0x14004049a  mov     rax, [rax]
0x14004049d  call    _guard_dispatch_icall
0x1400404a2  mov     edi, eax
0x1400404a4  test    eax, eax
0x1400404a6  js      short loc_1400404CB
0x1400404a8  mov     [rbp+var_30], 8000FFFFh
0x1400404af  mov     rcx, [rbp+var_28]
0x1400404b3  mov     rax, [rcx]
0x1400404b6  lea     rdx, [rbp+var_30]
0x1400404ba  mov     rax, [rax+40h]
0x1400404be  call    _guard_dispatch_icall
0x1400404c3  mov     edi, eax
0x1400404c5  test    eax, eax
0x1400404c7  cmovns  edi, [rbp+var_30]
0x1400404cb  mov     rcx, [rbp+var_28]
0x1400404cf  test    rcx, rcx
0x1400404d2  jz      short loc_1400404E9
0x1400404d4  mov     [rbp+var_28], 0
0x1400404dc  mov     rax, [rcx]
0x1400404df  mov     rax, [rax+10h]
0x1400404e3  call    _guard_dispatch_icall
0x1400404e8  nop
0x1400404e9  mov     rax, [rbx]
0x1400404ec  mov     rcx, rbx
0x1400404ef  mov     rax, [rax+10h]
0x1400404f3  call    _guard_dispatch_icall
0x1400404f8  nop
0x1400404f9  jmp     loc_1400403AC
0x1400404fe  mov     rax, [rbx]
0x140040501  mov     rcx, rbx
0x140040504  mov     rax, [rax+10h]
0x140040508  call    _guard_dispatch_icall
0x14004050d  nop
0x14004050e  xor     eax, eax
0x140040510  mov     rcx, [rbp+var_10]
0x140040514  xor     rcx, rsp; StackCookie
0x140040517  call    __security_check_cookie
0x14004051c  lea     r11, [rsp+60h+var_s0]
0x140040521  mov     rbx, [r11+18h]
0x140040525  mov     rsi, [r11+20h]
0x140040529  mov     rdi, [r11+28h]
0x14004052d  mov     rsp, r11
0x140040530  pop     rbp
0x140040531  retn
```
