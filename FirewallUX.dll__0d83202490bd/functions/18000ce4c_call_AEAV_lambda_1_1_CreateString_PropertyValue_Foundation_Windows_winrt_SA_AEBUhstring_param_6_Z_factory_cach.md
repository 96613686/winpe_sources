# ??$call@AEAV_lambda_1_@?1??CreateString@PropertyValue@Foundation@Windows@winrt@@SA@AEBUhstring@param@6@@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateString@PropertyValue@Foundation@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18000ce4c`
- end: `0x18000cfdd`
- name: `??$call@AEAV_lambda_1_@?1??CreateString@PropertyValue@Foundation@Windows@winrt@@SA@AEBUhstring@param@6@@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateString@PropertyValue@Foundation@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `401`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014980`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000ce4c`
- `0x18000e2c4`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateString_PropertyValue_Foundation_Windows_winrt__SA_AEBUhstring_param_6__Z____factory_cache_entry_UPropertyValue_Foundation_Windows_winrt__UIPropertyValueStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateString_PropertyValue_Foundation_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 32;
  v13 = L"Windows.Foundation.PropertyValue";
  v11 = v12;
  winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(&v14, &v11);
  v5 = (signed __int64)v14;
  if ( !v14 || (v15 = 0, (**v14)(v14, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 144LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_18003C1D8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
          v5,
          0) )
  {
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C1E0);
    v5 = 0;
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
                                                             + 144LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_18003C1D8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18000ce4c  mov     [rsp-18h+arg_8], rbx
0x18000ce51  mov     [rsp-18h+arg_0], rcx
0x18000ce56  push    rbp
0x18000ce57  push    rsi
0x18000ce58  push    rdi
0x18000ce59  mov     rbp, rsp
0x18000ce5c  sub     rsp, 70h
0x18000ce60  mov     rsi, r8
0x18000ce63  mov     rbx, rdx
0x18000ce66  mov     [rbp+var_20], 1
0x18000ce6d  mov     [rbp+var_1C], 20h ; ' '
0x18000ce74  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x18000ce7b  mov     [rbp+var_10], rax
0x18000ce7f  lea     rax, [rbp+var_20]
0x18000ce83  mov     [rbp+var_28], rax
0x18000ce87  lea     rdx, [rbp+var_28]
0x18000ce8b  lea     rcx, [rbp+arg_0]
0x18000ce8f  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x18000ce94  nop
0x18000ce95  mov     rdi, [rbp+arg_0]
0x18000ce99  test    rdi, rdi
0x18000ce9c  jz      loc_18000CF6B
0x18000cea2  mov     [rbp+arg_18], 0
0x18000ceaa  mov     rax, [rdi]
0x18000cead  lea     r8, [rbp+arg_18]
0x18000ceb1  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000ceb8  mov     rcx, rdi
0x18000cebb  mov     rax, [rax]
0x18000cebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec3  mov     rax, [rbp+arg_18]
0x18000cec7  mov     [rbp+arg_18], rax
0x18000cecb  test    rax, rax
0x18000cece  jz      loc_18000CF6B
0x18000ced4  lea     rcx, [rbp+arg_18]
0x18000ced8  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000cedd  lea     rax, qword_18003C1D8
0x18000cee4  mov     [rbp+var_48], rax
0x18000cee8  lock inc cs:qword_18003C1D8
0x18000cef0  xor     eax, eax
0x18000cef2  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18000cefb  jnz     short loc_18000CF1A
0x18000cefd  mov     [rbp+arg_0], 0
0x18000cf05  lea     rdx, stru_18003C1E0; ListEntry
0x18000cf0c  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000cf13  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000cf18  xor     edi, edi
0x18000cf1a  mov     [rbp+arg_18], 0
0x18000cf22  mov     rcx, cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18000cf29  mov     [rbp+var_40], 0
0x18000cf30  xorps   xmm0, xmm0
0x18000cf33  movdqu  [rbp+var_38], xmm0
0x18000cf38  mov     rax, [rcx]
0x18000cf3b  mov     rdx, [rsi]
0x18000cf3e  lea     r8, [rbp+arg_18]
0x18000cf42  mov     rdx, [rdx]
0x18000cf45  mov     rax, [rax+90h]
0x18000cf4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf51  test    eax, eax
0x18000cf53  js      short loc_18000CFD1
0x18000cf55  mov     rax, [rbp+arg_18]
0x18000cf59  mov     [rbx], rax
0x18000cf5c  lock dec cs:qword_18003C1D8
0x18000cf64  test    rdi, rdi
0x18000cf67  jz      short loc_18000CFB2
0x18000cf69  jmp     short loc_18000CFA9
0x18000cf6b  mov     [rbp+arg_18], 0
0x18000cf73  mov     [rbp+var_40], 0
0x18000cf7a  xorps   xmm0, xmm0
0x18000cf7d  movdqu  [rbp+var_38], xmm0
0x18000cf82  mov     rax, [rdi]
0x18000cf85  mov     rdx, [rsi]
0x18000cf88  lea     r8, [rbp+arg_18]
0x18000cf8c  mov     rdx, [rdx]
0x18000cf8f  mov     rcx, rdi
0x18000cf92  mov     rax, [rax+90h]
0x18000cf99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf9e  test    eax, eax
0x18000cfa0  js      short loc_18000CFC5
0x18000cfa2  mov     rax, [rbp+arg_18]
0x18000cfa6  mov     [rbx], rax
0x18000cfa9  lea     rcx, [rbp+arg_0]
0x18000cfad  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000cfb2  mov     rax, rbx
0x18000cfb5  mov     rbx, [rsp+70h+arg_8]
0x18000cfbd  add     rsp, 70h
0x18000cfc1  pop     rdi
0x18000cfc2  pop     rsi
0x18000cfc3  pop     rbp
0x18000cfc4  retn
0x18000cfc5  lea     rdx, [rbp+var_40]
0x18000cfc9  mov     ecx, eax
0x18000cfcb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000cfd1  lea     rdx, [rbp+var_40]
0x18000cfd5  mov     ecx, eax
0x18000cfd7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
