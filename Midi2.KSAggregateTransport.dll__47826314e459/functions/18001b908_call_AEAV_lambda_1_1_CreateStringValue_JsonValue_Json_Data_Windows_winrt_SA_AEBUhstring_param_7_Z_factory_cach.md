# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18001b908`
- end: `0x18001baad`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cdf0`

## callees

- `0x180006031`
- `0x180010b94`
- `0x18001a4a8`
- `0x18001b908`
- `0x18001c508`
- `0x18005e010`

## string_xrefs

- `0x18001b930`: `Windows.Data.Json.JsonValue`
- `0x18001b9ec`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x18001ba42`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  const char *v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-30h]
  _DWORD *v12; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v13[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v15)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v15 = a1;
  v13[0] = 1;
  v13[1] = 27;
  v14 = L"Windows.Data.Json.JsonValue";
  v12 = v13;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v15, &v12);
  v5 = (signed __int64)v15;
  if ( !v15 || (v16 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v16), !v16) )
  {
    v16 = 0;
    v9 = 638;
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_180096B68);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180096B70);
    v5 = 0;
  }
  v16 = 0;
  v9 = 638;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_180096B68);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x18001b908  mov     [rsp-18h+arg_8], rbx
0x18001b90d  mov     [rsp-18h+arg_0], rcx
0x18001b912  push    rbp
0x18001b913  push    rsi
0x18001b914  push    rdi
0x18001b915  mov     rbp, rsp
0x18001b918  sub     rsp, 70h
0x18001b91c  mov     rsi, r8
0x18001b91f  mov     rbx, rdx
0x18001b922  mov     [rbp+var_20], 1
0x18001b929  mov     [rbp+var_1C], 1Bh
0x18001b930  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x18001b937  mov     [rbp+var_10], rax
0x18001b93b  lea     rax, [rbp+var_20]
0x18001b93f  mov     [rbp+var_28], rax
0x18001b943  lea     rdx, [rbp+var_28]
0x18001b947  lea     rcx, [rbp+arg_0]
0x18001b94b  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x18001b950  nop
0x18001b951  mov     rdi, [rbp+arg_0]
0x18001b955  test    rdi, rdi
0x18001b958  jz      loc_18001BA33
0x18001b95e  mov     [rbp+arg_18], 0
0x18001b966  mov     rax, [rdi]
0x18001b969  lea     r8, [rbp+arg_18]
0x18001b96d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001b974  mov     rcx, rdi
0x18001b977  mov     rax, [rax]
0x18001b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b97f  mov     rax, [rbp+arg_18]
0x18001b983  mov     [rbp+arg_18], rax
0x18001b987  test    rax, rax
0x18001b98a  jz      loc_18001BA33
0x18001b990  lea     rcx, [rbp+arg_18]
0x18001b994  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b999  lea     rax, qword_180096B68
0x18001b9a0  mov     [rbp+var_48], rax
0x18001b9a4  lock inc cs:qword_180096B68
0x18001b9ac  xor     eax, eax
0x18001b9ae  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001b9b7  jnz     short loc_18001B9D6
0x18001b9b9  mov     [rbp+arg_0], 0
0x18001b9c1  lea     rdx, stru_180096B70; ListEntry
0x18001b9c8  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001b9cf  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001b9d4  xor     edi, edi
0x18001b9d6  mov     [rbp+arg_18], 0
0x18001b9de  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001b9e5  mov     [rbp+var_40], 27Eh
0x18001b9ec  lea     rax, aOnecoreuapInte_8; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001b9f3  mov     [rbp+var_38], rax
0x18001b9f7  mov     [rbp+var_30], 0
0x18001b9ff  mov     rax, [rcx]
0x18001ba02  mov     rdx, [rsi]
0x18001ba05  lea     r8, [rbp+arg_18]
0x18001ba09  mov     rdx, [rdx]
0x18001ba0c  mov     rax, [rax+50h]
0x18001ba10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba15  test    eax, eax
0x18001ba17  js      loc_18001BAA1
0x18001ba1d  mov     rax, [rbp+arg_18]
0x18001ba21  mov     [rbx], rax
0x18001ba24  lock dec cs:qword_180096B68
0x18001ba2c  test    rdi, rdi
0x18001ba2f  jz      short loc_18001BA82
0x18001ba31  jmp     short loc_18001BA79
0x18001ba33  mov     [rbp+arg_18], 0
0x18001ba3b  mov     [rbp+var_40], 27Eh
0x18001ba42  lea     rax, aOnecoreuapInte_8; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001ba49  mov     [rbp+var_38], rax
0x18001ba4d  mov     [rbp+var_30], 0
0x18001ba55  mov     rax, [rdi]
0x18001ba58  mov     rdx, [rsi]
0x18001ba5b  lea     r8, [rbp+arg_18]
0x18001ba5f  mov     rdx, [rdx]
0x18001ba62  mov     rcx, rdi
0x18001ba65  mov     rax, [rax+50h]
0x18001ba69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba6e  test    eax, eax
0x18001ba70  js      short loc_18001BA95
0x18001ba72  mov     rax, [rbp+arg_18]
0x18001ba76  mov     [rbx], rax
0x18001ba79  lea     rcx, [rbp+arg_0]
0x18001ba7d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ba82  mov     rax, rbx
0x18001ba85  mov     rbx, [rsp+70h+arg_8]
0x18001ba8d  add     rsp, 70h
0x18001ba91  pop     rdi
0x18001ba92  pop     rsi
0x18001ba93  pop     rbp
0x18001ba94  retn
0x18001ba95  lea     rdx, [rbp+var_40]
0x18001ba99  mov     ecx, eax
0x18001ba9b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001baa1  lea     rdx, [rbp+var_40]
0x18001baa5  mov     ecx, eax
0x18001baa7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
