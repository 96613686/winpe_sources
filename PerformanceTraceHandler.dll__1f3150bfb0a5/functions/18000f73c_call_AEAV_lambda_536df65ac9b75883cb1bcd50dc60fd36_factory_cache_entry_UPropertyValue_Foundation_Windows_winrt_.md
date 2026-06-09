# ??$call@AEAV_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@@Z

- ea: `0x18000f73c`
- end: `0x18000f881`
- name: `??$call@AEAV_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010278`

## callees

- `0x1800038e9`
- `0x180009c74`
- `0x18000f73c`
- `0x18000fe58`
- `0x1800109e8`
- `0x180010a38`
- `0x180010ce0`
- `0x180012e00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_536df65ac9b75883cb1bcd50dc60fd36_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _BYTE v9[32]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"Windows.Foundation.PropertyValue";
  *(_QWORD *)&v8 = 32;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValueStatics>,
    &v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v11);
    v11 = &qword_1800279F8;
    _InterlockedIncrement64(&qword_1800279F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_536df65ac9b75883cb1bcd50dc60fd36_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_1800279F8);
  }
  else
  {
    _lambda_536df65ac9b75883cb1bcd50dc60fd36_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18000f73c  mov     [rsp-18h+arg_8], rbx
0x18000f741  mov     [rsp-18h+arg_0], rcx
0x18000f746  push    rbp
0x18000f747  push    rsi
0x18000f748  push    rdi
0x18000f749  mov     rbp, rsp
0x18000f74c  sub     rsp, 60h
0x18000f750  mov     rsi, r8
0x18000f753  mov     rbx, rdx
0x18000f756  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x18000f75d  mov     [rbp+var_38], rax
0x18000f761  mov     qword ptr [rbp+var_30], 20h ; ' '
0x18000f769  lea     rdx, [rbp+var_38]
0x18000f76d  lea     rcx, [rbp+var_20]
0x18000f771  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f776  mov     [rbp+arg_18], 0
0x18000f77e  mov     dword ptr [rbp+var_38], 0
0x18000f785  xorps   xmm0, xmm0
0x18000f788  movdqu  [rbp+var_30], xmm0
0x18000f78d  lea     r9, [rbp+arg_18]
0x18000f791  lea     r8, ??$guid_v@UIPropertyValueStatics@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValueStatics>
0x18000f798  lea     rdx, [rbp+var_20]
0x18000f79c  lea     rcx, [rbp+arg_0]
0x18000f7a0  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000f7a5  lea     r8, [rbp+var_38]
0x18000f7a9  mov     edx, dword ptr [rbp+arg_0]
0x18000f7ac  lea     rcx, [rbp+arg_0]
0x18000f7b0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f7b5  mov     rdi, [rbp+arg_18]
0x18000f7b9  mov     [rbp+arg_0], rdi
0x18000f7bd  test    rdi, rdi
0x18000f7c0  jz      loc_18000F855
0x18000f7c6  mov     [rbp+arg_18], 0
0x18000f7ce  mov     rax, [rdi]
0x18000f7d1  lea     r8, [rbp+arg_18]
0x18000f7d5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f7dc  mov     rcx, rdi
0x18000f7df  mov     rax, [rax]
0x18000f7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7e7  mov     rax, [rbp+arg_18]
0x18000f7eb  mov     [rbp+arg_18], rax
0x18000f7ef  test    rax, rax
0x18000f7f2  jz      short loc_18000F855
0x18000f7f4  lea     rcx, [rbp+arg_18]
0x18000f7f8  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000f7fd  lea     rax, qword_1800279F8
0x18000f804  mov     [rbp+arg_18], rax
0x18000f808  lock inc cs:qword_1800279F8
0x18000f810  xor     eax, eax
0x18000f812  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18000f81b  jnz     short loc_18000F838
0x18000f81d  mov     [rbp+arg_0], 0
0x18000f825  lea     rdx, ListEntry; ListEntry
0x18000f82c  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f833  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f838  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x18000f83f  mov     rdx, rbx
0x18000f842  mov     rcx, rsi
0x18000f845  call    ??R_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_536df65ac9b75883cb1bcd50dc60fd36_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x18000f84a  nop
0x18000f84b  lock dec cs:qword_1800279F8
0x18000f853  jmp     short loc_18000F865
0x18000f855  lea     r8, [rbp+arg_0]
0x18000f859  mov     rdx, rbx
0x18000f85c  mov     rcx, rsi
0x18000f85f  call    ??R_lambda_536df65ac9b75883cb1bcd50dc60fd36_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_536df65ac9b75883cb1bcd50dc60fd36_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x18000f864  nop
0x18000f865  lea     rcx, [rbp+arg_0]
0x18000f869  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x18000f86e  mov     rax, rbx
0x18000f871  mov     rbx, [rsp+60h+arg_8]
0x18000f879  add     rsp, 60h
0x18000f87d  pop     rdi
0x18000f87e  pop     rsi
0x18000f87f  pop     rbp
0x18000f880  retn
```
