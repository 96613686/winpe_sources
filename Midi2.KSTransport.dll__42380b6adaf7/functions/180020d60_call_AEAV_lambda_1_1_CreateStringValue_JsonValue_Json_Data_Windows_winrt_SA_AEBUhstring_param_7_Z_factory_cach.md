# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x180020d60`
- end: `0x180020f05`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002213c`

## callees

- `0x1800054a9`
- `0x18000d1c0`
- `0x180015348`
- `0x180020d60`
- `0x180021960`
- `0x180041010`

## string_xrefs

- `0x180020d88`: `Windows.Data.Json.JsonValue`
- `0x180020e44`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x180020e9a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
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
  _InterlockedIncrement64(&qword_180071CE8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180071CF0);
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
  _InterlockedDecrement64(&qword_180071CE8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x180020d60  mov     [rsp-18h+arg_8], rbx
0x180020d65  mov     [rsp-18h+arg_0], rcx
0x180020d6a  push    rbp
0x180020d6b  push    rsi
0x180020d6c  push    rdi
0x180020d6d  mov     rbp, rsp
0x180020d70  sub     rsp, 70h
0x180020d74  mov     rsi, r8
0x180020d77  mov     rbx, rdx
0x180020d7a  mov     [rbp+var_20], 1
0x180020d81  mov     [rbp+var_1C], 1Bh
0x180020d88  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180020d8f  mov     [rbp+var_10], rax
0x180020d93  lea     rax, [rbp+var_20]
0x180020d97  mov     [rbp+var_28], rax
0x180020d9b  lea     rdx, [rbp+var_28]
0x180020d9f  lea     rcx, [rbp+arg_0]
0x180020da3  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180020da8  nop
0x180020da9  mov     rdi, [rbp+arg_0]
0x180020dad  test    rdi, rdi
0x180020db0  jz      loc_180020E8B
0x180020db6  mov     [rbp+arg_18], 0
0x180020dbe  mov     rax, [rdi]
0x180020dc1  lea     r8, [rbp+arg_18]
0x180020dc5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180020dcc  mov     rcx, rdi
0x180020dcf  mov     rax, [rax]
0x180020dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd7  mov     rax, [rbp+arg_18]
0x180020ddb  mov     [rbp+arg_18], rax
0x180020ddf  test    rax, rax
0x180020de2  jz      loc_180020E8B
0x180020de8  lea     rcx, [rbp+arg_18]
0x180020dec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020df1  lea     rax, qword_180071CE8
0x180020df8  mov     [rbp+var_48], rax
0x180020dfc  lock inc cs:qword_180071CE8
0x180020e04  xor     eax, eax
0x180020e06  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180020e0f  jnz     short loc_180020E2E
0x180020e11  mov     [rbp+arg_0], 0
0x180020e19  lea     rdx, stru_180071CF0; ListEntry
0x180020e20  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180020e27  call    WINRT_IMPL_InterlockedPushEntrySList
0x180020e2c  xor     edi, edi
0x180020e2e  mov     [rbp+arg_18], 0
0x180020e36  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180020e3d  mov     [rbp+var_40], 27Eh
0x180020e44  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180020e4b  mov     [rbp+var_38], rax
0x180020e4f  mov     [rbp+var_30], 0
0x180020e57  mov     rax, [rcx]
0x180020e5a  mov     rdx, [rsi]
0x180020e5d  lea     r8, [rbp+arg_18]
0x180020e61  mov     rdx, [rdx]
0x180020e64  mov     rax, [rax+50h]
0x180020e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e6d  test    eax, eax
0x180020e6f  js      loc_180020EF9
0x180020e75  mov     rax, [rbp+arg_18]
0x180020e79  mov     [rbx], rax
0x180020e7c  lock dec cs:qword_180071CE8
0x180020e84  test    rdi, rdi
0x180020e87  jz      short loc_180020EDA
0x180020e89  jmp     short loc_180020ED1
0x180020e8b  mov     [rbp+arg_18], 0
0x180020e93  mov     [rbp+var_40], 27Eh
0x180020e9a  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180020ea1  mov     [rbp+var_38], rax
0x180020ea5  mov     [rbp+var_30], 0
0x180020ead  mov     rax, [rdi]
0x180020eb0  mov     rdx, [rsi]
0x180020eb3  lea     r8, [rbp+arg_18]
0x180020eb7  mov     rdx, [rdx]
0x180020eba  mov     rcx, rdi
0x180020ebd  mov     rax, [rax+50h]
0x180020ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec6  test    eax, eax
0x180020ec8  js      short loc_180020EED
0x180020eca  mov     rax, [rbp+arg_18]
0x180020ece  mov     [rbx], rax
0x180020ed1  lea     rcx, [rbp+arg_0]
0x180020ed5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020eda  mov     rax, rbx
0x180020edd  mov     rbx, [rsp+70h+arg_8]
0x180020ee5  add     rsp, 70h
0x180020ee9  pop     rdi
0x180020eea  pop     rsi
0x180020eeb  pop     rbp
0x180020eec  retn
0x180020eed  lea     rdx, [rbp+var_40]
0x180020ef1  mov     ecx, eax
0x180020ef3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180020ef9  lea     rdx, [rbp+var_40]
0x180020efd  mov     ecx, eax
0x180020eff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
