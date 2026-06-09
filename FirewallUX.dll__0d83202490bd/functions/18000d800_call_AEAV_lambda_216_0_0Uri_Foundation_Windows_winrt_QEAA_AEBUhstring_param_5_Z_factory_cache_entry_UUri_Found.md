# ??$call@AEAV_lambda_216__@?0???0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_216__@?0???0Uri@Foundation@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18000d800`
- end: `0x18000d9c5`
- name: `??$call@AEAV_lambda_216__@?0???0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_216__@?0???0Uri@Foundation@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z`
- size: `453`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f46c`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d800`
- `0x18000e70c`
- `0x18002d010`

## string_xrefs

- `0x18000d828`: `Windows.Foundation.Uri`

## pseudocode

```c
signed __int64 *__fastcall ___call_AEAV_lambda_216____0___0Uri_Foundation_Windows_winrt__QEAA_AEBUhstring_param_5__Z____factory_cache_entry_UUri_Foundation_Windows_winrt__UIUriRuntimeClassFactory_234__impl_winrt__QEAA_A_PAEAV_lambda_216____0___0Uri_Foundation_Windows_2_QEAA_AEBUhstring_param_2__Z__Z(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 22;
  v13 = L"Windows.Foundation.Uri";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    &winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_18003C238);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C240);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                                    + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_18003C238);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18000d800  mov     [rsp-18h+arg_8], rbx
0x18000d805  mov     [rsp-18h+arg_0], rcx
0x18000d80a  push    rbp
0x18000d80b  push    rsi
0x18000d80c  push    rdi
0x18000d80d  mov     rbp, rsp
0x18000d810  sub     rsp, 70h
0x18000d814  mov     rsi, r8
0x18000d817  mov     rdi, rdx
0x18000d81a  mov     [rbp+var_20], 1
0x18000d821  mov     [rbp+var_1C], 16h
0x18000d828  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Uri"
0x18000d82f  mov     [rbp+var_10], rax
0x18000d833  lea     rax, [rbp+var_20]
0x18000d837  mov     [rbp+var_28], rax
0x18000d83b  mov     [rbp+arg_18], 0
0x18000d843  mov     [rbp+var_40], 0
0x18000d84a  xorps   xmm0, xmm0
0x18000d84d  movdqu  [rbp+var_38], xmm0
0x18000d852  lea     r9, [rbp+arg_18]
0x18000d856  lea     r8, ??$guid_v@UIUriRuntimeClassFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000d85d  lea     rdx, [rbp+var_28]
0x18000d861  lea     rcx, [rbp+arg_0]
0x18000d865  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000d86a  mov     ecx, dword ptr [rbp+arg_0]
0x18000d86d  test    ecx, ecx
0x18000d86f  js      loc_18000D9AF
0x18000d875  mov     rbx, [rbp+arg_18]
0x18000d879  mov     [rbp+arg_0], rbx
0x18000d87d  test    rbx, rbx
0x18000d880  jz      loc_18000D94C
0x18000d886  mov     [rbp+arg_18], 0
0x18000d88e  mov     rax, [rbx]
0x18000d891  lea     r8, [rbp+arg_18]
0x18000d895  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d89c  mov     rcx, rbx
0x18000d89f  mov     rax, [rax]
0x18000d8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a7  mov     rax, [rbp+arg_18]
0x18000d8ab  mov     [rbp+arg_18], rax
0x18000d8af  test    rax, rax
0x18000d8b2  jz      loc_18000D94C
0x18000d8b8  lea     rcx, [rbp+arg_18]
0x18000d8bc  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d8c1  lea     rax, qword_18003C238
0x18000d8c8  mov     [rbp+var_48], rax
0x18000d8cc  lock inc cs:qword_18003C238
0x18000d8d4  xor     eax, eax
0x18000d8d6  lock cmpxchg cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rbx; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000d8df  jnz     short loc_18000D8FA
0x18000d8e1  xor     ebx, ebx
0x18000d8e3  mov     [rbp+arg_0], rbx
0x18000d8e7  lea     rdx, stru_18003C240; ListEntry
0x18000d8ee  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d8f5  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d8fa  mov     [rbp+arg_18], 0
0x18000d902  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000d909  mov     [rbp+var_40], 0
0x18000d910  xorps   xmm0, xmm0
0x18000d913  movdqu  [rbp+var_38], xmm0
0x18000d918  mov     rax, [rcx]
0x18000d91b  mov     rdx, [rsi]
0x18000d91e  lea     r8, [rbp+arg_18]
0x18000d922  mov     rdx, [rdx]
0x18000d925  mov     rax, [rax+30h]
0x18000d929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92e  test    eax, eax
0x18000d930  js      loc_18000D9B9
0x18000d936  mov     rax, [rbp+arg_18]
0x18000d93a  mov     [rdi], rax
0x18000d93d  lock dec cs:qword_18003C238
0x18000d945  test    rbx, rbx
0x18000d948  jz      short loc_18000D990
0x18000d94a  jmp     short loc_18000D987
0x18000d94c  mov     [rbp+arg_18], 0
0x18000d954  mov     [rbp+var_40], 0
0x18000d95b  xorps   xmm0, xmm0
0x18000d95e  movdqu  [rbp+var_38], xmm0
0x18000d963  mov     rax, [rbx]
0x18000d966  mov     rdx, [rsi]
0x18000d969  lea     r8, [rbp+arg_18]
0x18000d96d  mov     rdx, [rdx]
0x18000d970  mov     rcx, rbx
0x18000d973  mov     rax, [rax+30h]
0x18000d977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d97c  test    eax, eax
0x18000d97e  js      short loc_18000D9A3
0x18000d980  mov     rax, [rbp+arg_18]
0x18000d984  mov     [rdi], rax
0x18000d987  lea     rcx, [rbp+arg_0]
0x18000d98b  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d990  mov     rax, rdi
0x18000d993  mov     rbx, [rsp+70h+arg_8]
0x18000d99b  add     rsp, 70h
0x18000d99f  pop     rdi
0x18000d9a0  pop     rsi
0x18000d9a1  pop     rbp
0x18000d9a2  retn
0x18000d9a3  lea     rdx, [rbp+var_40]
0x18000d9a7  mov     ecx, eax
0x18000d9a9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d9af  lea     rdx, [rbp+var_40]
0x18000d9b3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d9b9  lea     rdx, [rbp+var_40]
0x18000d9bd  mov     ecx, eax
0x18000d9bf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
