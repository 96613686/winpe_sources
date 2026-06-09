# ??$call@AEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@Z

- ea: `0x180014b04`
- end: `0x180014c14`
- name: `??$call@AEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a190`

## callees

- `0x1800046b1`
- `0x1800078e4`
- `0x180007a58`
- `0x1800115a4`
- `0x180014b04`
- `0x18001787c`
- `0x1800187e0`
- `0x180048010`

## string_xrefs

- `0x180014b1e`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_24df58806cc5abd3d861a8c193996bf4_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.Data.Json.JsonValue";
  v7[1] = 27;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180060C88;
    _InterlockedIncrement64(&qword_180060C88);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180060C90);
    }
    _lambda_24df58806cc5abd3d861a8c193996bf4_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>);
    _InterlockedDecrement64(&qword_180060C88);
  }
  else
  {
    _lambda_24df58806cc5abd3d861a8c193996bf4_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v9);
  return a2;
}

```

## disassembly

```asm
0x180014b04  mov     [rsp-18h+arg_8], rbx
0x180014b09  mov     [rsp-18h+arg_0], rcx
0x180014b0e  push    rbp
0x180014b0f  push    rsi
0x180014b10  push    rdi
0x180014b11  mov     rbp, rsp
0x180014b14  sub     rsp, 60h
0x180014b18  mov     rsi, r8
0x180014b1b  mov     rbx, rdx
0x180014b1e  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180014b25  mov     [rbp+var_38], rax
0x180014b29  mov     [rbp+var_30], 1Bh
0x180014b31  lea     rdx, [rbp+var_38]
0x180014b35  lea     rcx, [rbp+var_28]
0x180014b39  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180014b3e  lea     rdx, [rbp+var_28]
0x180014b42  lea     rcx, [rbp+arg_0]
0x180014b46  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180014b4b  nop
0x180014b4c  mov     rdi, [rbp+arg_0]
0x180014b50  test    rdi, rdi
0x180014b53  jz      loc_180014BE8
0x180014b59  mov     [rbp+arg_18], 0
0x180014b61  mov     rax, [rdi]
0x180014b64  lea     r8, [rbp+arg_18]
0x180014b68  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180014b6f  mov     rcx, rdi
0x180014b72  mov     rax, [rax]
0x180014b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b7a  mov     rax, [rbp+arg_18]
0x180014b7e  mov     [rbp+arg_18], rax
0x180014b82  test    rax, rax
0x180014b85  jz      short loc_180014BE8
0x180014b87  lea     rcx, [rbp+arg_18]
0x180014b8b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014b90  lea     rax, qword_180060C88
0x180014b97  mov     [rbp+arg_18], rax
0x180014b9b  lock inc cs:qword_180060C88
0x180014ba3  xor     eax, eax
0x180014ba5  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180014bae  jnz     short loc_180014BCB
0x180014bb0  mov     [rbp+arg_0], 0
0x180014bb8  lea     rdx, stru_180060C90; ListEntry
0x180014bbf  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180014bc6  call    WINRT_IMPL_InterlockedPushEntrySList
0x180014bcb  lea     r8, ??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180014bd2  mov     rdx, rbx
0x180014bd5  mov     rcx, rsi
0x180014bd8  call    ??R_lambda_24df58806cc5abd3d861a8c193996bf4_@@QEBA@AEBUIJsonValueStatics@Json@Data@Windows@winrt@@@Z; _lambda_24df58806cc5abd3d861a8c193996bf4_::operator()(winrt::Windows::Data::Json::IJsonValueStatics const &)
0x180014bdd  nop
0x180014bde  lock dec cs:qword_180060C88
0x180014be6  jmp     short loc_180014BF8
0x180014be8  lea     r8, [rbp+arg_0]
0x180014bec  mov     rdx, rbx
0x180014bef  mov     rcx, rsi
0x180014bf2  call    ??R_lambda_24df58806cc5abd3d861a8c193996bf4_@@QEBA@AEBUIJsonValueStatics@Json@Data@Windows@winrt@@@Z; _lambda_24df58806cc5abd3d861a8c193996bf4_::operator()(winrt::Windows::Data::Json::IJsonValueStatics const &)
0x180014bf7  nop
0x180014bf8  lea     rcx, [rbp+arg_0]; this
0x180014bfc  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180014c01  mov     rax, rbx
0x180014c04  mov     rbx, [rsp+60h+arg_8]
0x180014c0c  add     rsp, 60h
0x180014c10  pop     rdi
0x180014c11  pop     rsi
0x180014c12  pop     rbp
0x180014c13  retn
```
