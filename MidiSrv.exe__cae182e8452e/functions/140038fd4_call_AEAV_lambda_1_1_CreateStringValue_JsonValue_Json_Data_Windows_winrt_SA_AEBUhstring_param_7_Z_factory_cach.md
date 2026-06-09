# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x140038fd4`
- end: `0x140039181`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `429`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a534`

## callees

- `0x140006310`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140038fd4`
- `0x1400392b0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140039001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140039001`

## string_xrefs

- `0x1400390c7`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x140039115`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x140039016`: `Windows.Data.Json.JsonValue`

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
  if ( aWindowsDataJso_0[27] )
    abort();
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
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_140096AB8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096AC0);
    v5 = 0;
  }
  v16 = 0;
  v9 = 638;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_140096AB8);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x140038fd4  mov     [rsp-18h+arg_8], rbx
0x140038fd9  mov     [rsp-18h+arg_10], rsi
0x140038fde  mov     [rsp-18h+arg_0], rcx
0x140038fe3  push    rbp
0x140038fe4  push    rdi
0x140038fe5  push    r14
0x140038fe7  mov     rbp, rsp
0x140038fea  sub     rsp, 70h
0x140038fee  mov     rsi, r8
0x140038ff1  mov     rbx, rdx
0x140038ff4  xor     r14d, r14d
0x140038ff7  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x140038fff  jz      short loc_140039008
0x140039001  call    cs:__imp_abort
0x140039008  mov     [rbp+var_20], 1
0x14003900f  mov     [rbp+var_1C], 1Bh
0x140039016  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x14003901d  mov     [rbp+var_10], rax
0x140039021  lea     rax, [rbp+var_20]
0x140039025  mov     [rbp+var_28], rax
0x140039029  lea     rdx, [rbp+var_28]
0x14003902d  lea     rcx, [rbp+arg_0]
0x140039031  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x140039036  nop
0x140039037  mov     rdi, [rbp+arg_0]
0x14003903b  test    rdi, rdi
0x14003903e  jz      loc_14003910A
0x140039044  mov     [rbp+arg_18], r14
0x140039048  mov     rax, [rdi]
0x14003904b  lea     r8, [rbp+arg_18]
0x14003904f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140039056  mov     rcx, rdi
0x140039059  mov     rax, [rax]
0x14003905c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039061  mov     rax, [rbp+arg_18]
0x140039065  mov     [rbp+arg_18], rax
0x140039069  test    rax, rax
0x14003906c  jz      loc_14003910A
0x140039072  lea     rcx, [rbp+arg_18]
0x140039076  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003907b  lea     rax, qword_140096AB8
0x140039082  mov     [rbp+var_48], rax
0x140039086  lock inc cs:qword_140096AB8
0x14003908e  xor     eax, eax
0x140039090  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x140039099  jnz     short loc_1400390B5
0x14003909b  mov     [rbp+arg_0], r14
0x14003909f  lea     rdx, stru_140096AC0; ListEntry
0x1400390a6  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1400390ad  call    WINRT_IMPL_InterlockedPushEntrySList
0x1400390b2  mov     rdi, r14
0x1400390b5  mov     [rbp+arg_18], r14
0x1400390b9  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1400390c0  mov     [rbp+var_40], 27Eh
0x1400390c7  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1400390ce  mov     [rbp+var_38], rax
0x1400390d2  mov     [rbp+var_30], r14
0x1400390d6  mov     rax, [rcx]
0x1400390d9  mov     rdx, [rsi]
0x1400390dc  lea     r8, [rbp+arg_18]
0x1400390e0  mov     rdx, [rdx]
0x1400390e3  mov     rax, [rax+50h]
0x1400390e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400390ec  test    eax, eax
0x1400390ee  js      loc_140039175
0x1400390f4  mov     rax, [rbp+arg_18]
0x1400390f8  mov     [rbx], rax
0x1400390fb  lock dec cs:qword_140096AB8
0x140039103  test    rdi, rdi
0x140039106  jz      short loc_140039151
0x140039108  jmp     short loc_140039148
0x14003910a  mov     [rbp+arg_18], r14
0x14003910e  mov     [rbp+var_40], 27Eh
0x140039115  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003911c  mov     [rbp+var_38], rax
0x140039120  mov     [rbp+var_30], r14
0x140039124  mov     rax, [rdi]
0x140039127  mov     rdx, [rsi]
0x14003912a  lea     r8, [rbp+arg_18]
0x14003912e  mov     rdx, [rdx]
0x140039131  mov     rcx, rdi
0x140039134  mov     rax, [rax+50h]
0x140039138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003913d  test    eax, eax
0x14003913f  js      short loc_140039169
0x140039141  mov     rax, [rbp+arg_18]
0x140039145  mov     [rbx], rax
0x140039148  lea     rcx, [rbp+arg_0]
0x14003914c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140039151  mov     rax, rbx
0x140039154  lea     r11, [rsp+70h+var_s0]
0x140039159  mov     rbx, [r11+28h]
0x14003915d  mov     rsi, [r11+30h]
0x140039161  mov     rsp, r11
0x140039164  pop     r14
0x140039166  pop     rdi
0x140039167  pop     rbp
0x140039168  retn
0x140039169  lea     rdx, [rbp+var_40]
0x14003916d  mov     ecx, eax
0x14003916f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140039175  lea     rdx, [rbp+var_40]
0x140039179  mov     ecx, eax
0x14003917b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
