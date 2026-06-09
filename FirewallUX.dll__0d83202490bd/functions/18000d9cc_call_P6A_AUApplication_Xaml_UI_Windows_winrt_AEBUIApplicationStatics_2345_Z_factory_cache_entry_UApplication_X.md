# ??$call@P6A?AUApplication@Xaml@UI@Windows@winrt@@AEBUIApplicationStatics@2345@@Z@?$factory_cache_entry@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUApplication@Xaml@UI@Windows@2@AEBUIApplicationStatics@4562@@Z@Z

- ea: `0x18000d9cc`
- end: `0x18000db24`
- name: `??$call@P6A?AUApplication@Xaml@UI@Windows@winrt@@AEBUIApplicationStatics@2345@@Z@?$factory_cache_entry@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUApplication@Xaml@UI@Windows@2@AEBUIApplicationStatics@4562@@Z@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800101bc`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d9cc`
- `0x18000e70c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>::call<winrt::Windows::UI::Xaml::Application (*)(winrt::Windows::UI::Xaml::IApplicationStatics const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+38h] [rbp-38h]
  _DWORD *v9; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+60h] [rbp-10h]
  __int64 *v12; // [rsp+80h] [rbp+10h] BYREF
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp+28h] BYREF

  v12 = a1;
  v10[0] = 1;
  v10[1] = 27;
  v11 = L"Windows.UI.Xaml.Application";
  v9 = v10;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IApplicationStatics>,
    &v6);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v7);
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v12 = 0, (**v6)(v6, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), v12) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
    v12 = &qword_18003C0D8;
    _InterlockedIncrement64(&qword_18003C0D8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>,
            (signed __int64)v13,
            0) )
    {
      v13 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C0E0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>);
    _InterlockedDecrement64(&qword_18003C0D8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v13);
  }
  if ( v13 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v13);
  return a2;
}

```

## disassembly

```asm
0x18000d9cc  mov     [rsp-8+arg_8], rbx
0x18000d9d1  mov     [rsp-8+arg_10], rdi
0x18000d9d6  mov     [rsp-8+arg_0], rcx
0x18000d9db  push    rbp
0x18000d9dc  mov     rbp, rsp
0x18000d9df  sub     rsp, 70h
0x18000d9e3  mov     rdi, r8
0x18000d9e6  mov     rbx, rdx
0x18000d9e9  mov     [rbp+var_20], 1
0x18000d9f0  mov     [rbp+var_1C], 1Bh
0x18000d9f7  lea     rax, aWindowsUiXamlA_0; "Windows.UI.Xaml.Application"
0x18000d9fe  mov     [rbp+var_10], rax
0x18000da02  lea     rax, [rbp+var_20]
0x18000da06  mov     [rbp+var_28], rax
0x18000da0a  mov     [rbp+var_48], 0
0x18000da12  mov     [rbp+var_40], 0
0x18000da19  xorps   xmm0, xmm0
0x18000da1c  movdqu  [rbp+var_38], xmm0
0x18000da21  lea     r9, [rbp+var_48]
0x18000da25  lea     r8, ??$guid_v@UIApplicationStatics@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IApplicationStatics>
0x18000da2c  lea     rdx, [rbp+var_28]
0x18000da30  lea     rcx, [rbp+arg_0]
0x18000da34  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000da39  mov     ecx, dword ptr [rbp+arg_0]
0x18000da3c  test    ecx, ecx
0x18000da3e  js      loc_18000DB1A
0x18000da44  mov     rcx, [rbp+var_48]
0x18000da48  mov     [rbp+arg_18], rcx
0x18000da4c  test    rcx, rcx
0x18000da4f  jz      loc_18000DAE5
0x18000da55  mov     [rbp+arg_0], 0
0x18000da5d  mov     rax, [rcx]
0x18000da60  lea     r8, [rbp+arg_0]
0x18000da64  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000da6b  mov     rax, [rax]
0x18000da6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da73  mov     rax, [rbp+arg_0]
0x18000da77  mov     [rbp+arg_0], rax
0x18000da7b  test    rax, rax
0x18000da7e  jz      short loc_18000DAE5
0x18000da80  lea     rcx, [rbp+arg_0]
0x18000da84  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000da89  lea     rax, qword_18003C0D8
0x18000da90  mov     [rbp+arg_0], rax
0x18000da94  lock inc cs:qword_18003C0D8
0x18000da9c  mov     rcx, [rbp+arg_18]
0x18000daa0  xor     eax, eax
0x18000daa2  lock cmpxchg cs:??$factory_cache_entry_v@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>
0x18000daab  jnz     short loc_18000DAC8
0x18000daad  mov     [rbp+arg_18], 0
0x18000dab5  lea     rdx, stru_18003C0E0; ListEntry
0x18000dabc  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000dac3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000dac8  lea     rdx, ??$factory_cache_entry_v@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@Xaml@UI@Windows@winrt@@UIApplicationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Application,winrt::Windows::UI::Xaml::IApplicationStatics>
0x18000dacf  mov     rcx, rbx
0x18000dad2  mov     rax, [rdi]
0x18000dad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dada  nop
0x18000dadb  lock dec cs:qword_18003C0D8
0x18000dae3  jmp     short loc_18000DAF5
0x18000dae5  lea     rdx, [rbp+arg_18]
0x18000dae9  mov     rcx, rbx
0x18000daec  mov     rax, [rdi]
0x18000daef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf4  nop
0x18000daf5  cmp     [rbp+arg_18], 0
0x18000dafa  jz      short loc_18000DB05
0x18000dafc  lea     rcx, [rbp+arg_18]
0x18000db00  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000db05  mov     rax, rbx
0x18000db08  lea     r11, [rsp+70h+var_s0]
0x18000db0d  mov     rbx, [r11+18h]
0x18000db11  mov     rdi, [r11+20h]
0x18000db15  mov     rsp, r11
0x18000db18  pop     rbp
0x18000db19  retn
0x18000db1a  lea     rdx, [rbp+var_40]
0x18000db1e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
