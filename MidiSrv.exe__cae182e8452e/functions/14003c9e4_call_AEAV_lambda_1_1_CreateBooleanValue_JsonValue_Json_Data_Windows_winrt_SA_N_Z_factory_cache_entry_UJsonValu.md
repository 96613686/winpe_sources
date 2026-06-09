# ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z

- ea: `0x14003c9e4`
- end: `0x14003cb8f`
- name: `??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z`
- size: `427`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _BYTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ce84`

## callees

- `0x140006310`
- `0x14000ca00`
- `0x14000cc2c`
- `0x1400392b0`
- `0x14003c9e4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003ca11`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003ca11`

## string_xrefs

- `0x14003cad7`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x14003cb24`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x14003ca26`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_winrt__SA__N_Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_2_SA__N_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _BYTE **a3)
{
  signed __int64 v5; // rdi
  _BYTE *v6; // rdx
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  const char *v12; // [rsp+38h] [rbp-38h]
  __int64 v13; // [rsp+40h] [rbp-30h]
  _DWORD *v14; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v15[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v17)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+38h] BYREF

  v17 = a1;
  if ( aWindowsDataJso_0[27] )
    abort();
  v15[0] = 1;
  v15[1] = 27;
  v16 = L"Windows.Data.Json.JsonValue";
  v14 = v15;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v17, &v14);
  v5 = (signed __int64)v17;
  if ( !v17 || (v18 = 0, (**v17)(v17, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v18), !v18) )
  {
    v18 = 0;
    v11 = 602;
    v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v13 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, v8, &v18);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v18;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  _InterlockedIncrement64(&qword_140096AB8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v17 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096AC0);
    v5 = 0;
  }
  v18 = 0;
  v11 = 602;
  v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v13 = 0;
  v6 = *a3;
  LOBYTE(v6) = **a3;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         v6,
         &v18);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v11);
  *a2 = v18;
  _InterlockedDecrement64(&qword_140096AB8);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  return a2;
}

```

## disassembly

```asm
0x14003c9e4  mov     [rsp-18h+arg_8], rbx
0x14003c9e9  mov     [rsp-18h+arg_10], rsi
0x14003c9ee  mov     [rsp-18h+arg_0], rcx
0x14003c9f3  push    rbp
0x14003c9f4  push    rdi
0x14003c9f5  push    r14
0x14003c9f7  mov     rbp, rsp
0x14003c9fa  sub     rsp, 70h
0x14003c9fe  mov     rsi, r8
0x14003ca01  mov     rbx, rdx
0x14003ca04  xor     r14d, r14d
0x14003ca07  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x14003ca0f  jz      short loc_14003CA18
0x14003ca11  call    cs:__imp_abort
0x14003ca18  mov     [rbp+var_20], 1
0x14003ca1f  mov     [rbp+var_1C], 1Bh
0x14003ca26  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x14003ca2d  mov     [rbp+var_10], rax
0x14003ca31  lea     rax, [rbp+var_20]
0x14003ca35  mov     [rbp+var_28], rax
0x14003ca39  lea     rdx, [rbp+var_28]
0x14003ca3d  lea     rcx, [rbp+arg_0]
0x14003ca41  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x14003ca46  nop
0x14003ca47  mov     rdi, [rbp+arg_0]
0x14003ca4b  test    rdi, rdi
0x14003ca4e  jz      loc_14003CB19
0x14003ca54  mov     [rbp+arg_18], r14
0x14003ca58  mov     rax, [rdi]
0x14003ca5b  lea     r8, [rbp+arg_18]
0x14003ca5f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14003ca66  mov     rcx, rdi
0x14003ca69  mov     rax, [rax]
0x14003ca6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ca71  mov     rax, [rbp+arg_18]
0x14003ca75  mov     [rbp+arg_18], rax
0x14003ca79  test    rax, rax
0x14003ca7c  jz      loc_14003CB19
0x14003ca82  lea     rcx, [rbp+arg_18]
0x14003ca86  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003ca8b  lea     rax, qword_140096AB8
0x14003ca92  mov     [rbp+var_48], rax
0x14003ca96  lock inc cs:qword_140096AB8
0x14003ca9e  xor     eax, eax
0x14003caa0  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x14003caa9  jnz     short loc_14003CAC5
0x14003caab  mov     [rbp+arg_0], r14
0x14003caaf  lea     rdx, stru_140096AC0; ListEntry
0x14003cab6  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14003cabd  call    WINRT_IMPL_InterlockedPushEntrySList
0x14003cac2  mov     rdi, r14
0x14003cac5  mov     [rbp+arg_18], r14
0x14003cac9  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x14003cad0  mov     [rbp+var_40], 25Ah
0x14003cad7  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003cade  mov     [rbp+var_38], rax
0x14003cae2  mov     [rbp+var_30], r14
0x14003cae6  mov     rax, [rcx]
0x14003cae9  mov     rdx, [rsi]
0x14003caec  lea     r8, [rbp+arg_18]
0x14003caf0  mov     dl, [rdx]
0x14003caf2  mov     rax, [rax+40h]
0x14003caf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cafb  test    eax, eax
0x14003cafd  js      loc_14003CB83
0x14003cb03  mov     rax, [rbp+arg_18]
0x14003cb07  mov     [rbx], rax
0x14003cb0a  lock dec cs:qword_140096AB8
0x14003cb12  test    rdi, rdi
0x14003cb15  jz      short loc_14003CB5F
0x14003cb17  jmp     short loc_14003CB56
0x14003cb19  mov     [rbp+arg_18], r14
0x14003cb1d  mov     [rbp+var_40], 25Ah
0x14003cb24  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003cb2b  mov     [rbp+var_38], rax
0x14003cb2f  mov     [rbp+var_30], r14
0x14003cb33  mov     rax, [rdi]
0x14003cb36  mov     rdx, [rsi]
0x14003cb39  lea     r8, [rbp+arg_18]
0x14003cb3d  mov     dl, [rdx]
0x14003cb3f  mov     rcx, rdi
0x14003cb42  mov     rax, [rax+40h]
0x14003cb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cb4b  test    eax, eax
0x14003cb4d  js      short loc_14003CB77
0x14003cb4f  mov     rax, [rbp+arg_18]
0x14003cb53  mov     [rbx], rax
0x14003cb56  lea     rcx, [rbp+arg_0]
0x14003cb5a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003cb5f  mov     rax, rbx
0x14003cb62  lea     r11, [rsp+70h+var_s0]
0x14003cb67  mov     rbx, [r11+28h]
0x14003cb6b  mov     rsi, [r11+30h]
0x14003cb6f  mov     rsp, r11
0x14003cb72  pop     r14
0x14003cb74  pop     rdi
0x14003cb75  pop     rbp
0x14003cb76  retn
0x14003cb77  lea     rdx, [rbp+var_40]
0x14003cb7b  mov     ecx, eax
0x14003cb7d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14003cb83  lea     rdx, [rbp+var_40]
0x14003cb87  mov     ecx, eax
0x14003cb89  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
