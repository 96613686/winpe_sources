# ??$call@AEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@?$factory_cache_entry@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@impl@winrt@@QEAA?A_PAEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@Z

- ea: `0x180026c1c`
- end: `0x180026d12`
- name: `??$call@AEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@?$factory_cache_entry@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@impl@winrt@@QEAA?A_PAEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180027a40`

## callees

- `0x180005236`
- `0x1800072d8`
- `0x18000dfc0`
- `0x180020388`
- `0x18002636c`
- `0x180026854`
- `0x180026c1c`
- `0x180026ea0`
- `0x180035010`

## string_xrefs

- `0x180026c42`: `Windows.ApplicationModel.LimitedAccessFeatures`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>::call<_lambda_c098c4d09b8d941208075d7422bf37c2_ &>(
        __int64 a1,
        winrt::Windows::Foundation::IUnknown *a2,
        void (__fastcall ***a3)(_QWORD, __int64 *, __int64 *))
{
  signed __int64 v4; // rdi
  void (__fastcall **v5)(_QWORD, __int64 *, __int64 *); // rax
  __int64 v6; // rcx
  _QWORD v8[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v9[40]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v11)(_QWORD, __int64 *, __int64 *); // [rsp+80h] [rbp+20h] BYREF

  v11 = a3;
  v10 = a1;
  v8[1] = 46;
  v8[0] = L"Windows.ApplicationModel.LimitedAccessFeatures";
  winrt::param::hstring::hstring(v9, v8);
  winrt::get_activation_factory<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>(&v11, v9);
  v4 = (signed __int64)v11;
  if ( v11 && (v5 = *v11, v10 = 0, (*v5)(v11, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    _InterlockedIncrement64(&qword_180046D68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>,
            v4,
            0) )
    {
      v11 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180046D70);
    }
    _lambda_c098c4d09b8d941208075d7422bf37c2_::operator()<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal const &>(
      v6,
      a2);
    _InterlockedDecrement64(&qword_180046D68);
  }
  else
  {
    *(_QWORD *)a2 = v4;
    winrt::Windows::Foundation::IUnknown::add_ref(a2);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
  return a2;
}

```

## disassembly

```asm
0x180026c1c  mov     rax, rsp
0x180026c1f  mov     [rax+10h], rbx
0x180026c23  mov     [rax+20h], rdi
0x180026c27  mov     [rax+18h], r8
0x180026c2b  mov     [rax+8], rcx
0x180026c2f  push    rbp
0x180026c30  mov     rbp, rsp
0x180026c33  sub     rsp, 60h
0x180026c37  mov     rbx, rdx
0x180026c3a  mov     [rbp+var_30], 2Eh ; '.'
0x180026c42  lea     rax, aWindowsApplica; "Windows.ApplicationModel.LimitedAccessF"...
0x180026c49  lea     rdx, [rbp+var_38]
0x180026c4d  mov     [rbp+var_38], rax
0x180026c51  lea     rcx, [rbp+var_28]
0x180026c55  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180026c5a  lea     rdx, [rbp+var_28]
0x180026c5e  lea     rcx, [rbp+arg_10]
0x180026c62  call    ??$get_activation_factory@UILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@winrt@@@winrt@@YA?AUILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>(winrt::param::hstring const &)
0x180026c67  mov     rdi, [rbp+arg_10]
0x180026c6b  test    rdi, rdi
0x180026c6e  jz      short loc_180026CE9
0x180026c70  mov     rax, [rdi]
0x180026c73  lea     r8, [rbp+arg_0]
0x180026c77  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180026c7e  mov     [rbp+arg_0], 0
0x180026c86  mov     rcx, rdi
0x180026c89  mov     rax, [rax]
0x180026c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c91  mov     rax, [rbp+arg_0]
0x180026c95  mov     [rbp+arg_0], rax
0x180026c99  test    rax, rax
0x180026c9c  jz      short loc_180026CE9
0x180026c9e  lea     rcx, [rbp+arg_0]
0x180026ca2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026ca7  lock inc cs:qword_180046D68
0x180026caf  xor     eax, eax
0x180026cb1  lock cmpxchg cs:??$factory_cache_entry_v@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@impl@winrt@@3U?$factory_cache_entry@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@12@A, rdi; factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>
0x180026cba  jnz     short loc_180026CD7
0x180026cbc  lea     rdx, stru_180046D70; ListEntry
0x180026cc3  mov     [rbp+arg_10], 0
0x180026ccb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180026cd2  call    WINRT_IMPL_InterlockedPushEntrySList
0x180026cd7  mov     rdx, rbx
0x180026cda  call    ??$?RAEBUILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@winrt@@@_lambda_c098c4d09b8d941208075d7422bf37c2_@@QEBA?A_PAEBUILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@winrt@@@Z
0x180026cdf  lock dec cs:qword_180046D68
0x180026ce7  jmp     short loc_180026CF4
0x180026ce9  mov     rcx, rbx; this
0x180026cec  mov     [rbx], rdi
0x180026cef  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180026cf4  lea     rcx, [rbp+arg_10]
0x180026cf8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180026cfd  lea     r11, [rsp+60h+var_s0]
0x180026d02  mov     rax, rbx
0x180026d05  mov     rbx, [r11+18h]
0x180026d09  mov     rdi, [r11+28h]
0x180026d0d  mov     rsp, r11
0x180026d10  pop     rbp
0x180026d11  retn
```
