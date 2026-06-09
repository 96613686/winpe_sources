# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18001bcfc`
- end: `0x18001bea1`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d184`

## callees

- `0x1800047ed`
- `0x18001a3fc`
- `0x18001a798`
- `0x18001bcfc`
- `0x18001c428`
- `0x180021010`

## string_xrefs

- `0x18001bd24`: `Windows.Data.Json.JsonValue`
- `0x18001bde0`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x18001be36`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
  _InterlockedIncrement64(&qword_18002DAA8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002DAB0);
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
  _InterlockedDecrement64(&qword_18002DAA8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x18001bcfc  mov     [rsp-18h+arg_8], rbx
0x18001bd01  mov     [rsp-18h+arg_0], rcx
0x18001bd06  push    rbp
0x18001bd07  push    rsi
0x18001bd08  push    rdi
0x18001bd09  mov     rbp, rsp
0x18001bd0c  sub     rsp, 70h
0x18001bd10  mov     rsi, r8
0x18001bd13  mov     rbx, rdx
0x18001bd16  mov     [rbp+var_20], 1
0x18001bd1d  mov     [rbp+var_1C], 1Bh
0x18001bd24  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x18001bd2b  mov     [rbp+var_10], rax
0x18001bd2f  lea     rax, [rbp+var_20]
0x18001bd33  mov     [rbp+var_28], rax
0x18001bd37  lea     rdx, [rbp+var_28]
0x18001bd3b  lea     rcx, [rbp+arg_0]
0x18001bd3f  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x18001bd44  nop
0x18001bd45  mov     rdi, [rbp+arg_0]
0x18001bd49  test    rdi, rdi
0x18001bd4c  jz      loc_18001BE27
0x18001bd52  mov     [rbp+arg_18], 0
0x18001bd5a  mov     rax, [rdi]
0x18001bd5d  lea     r8, [rbp+arg_18]
0x18001bd61  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001bd68  mov     rcx, rdi
0x18001bd6b  mov     rax, [rax]
0x18001bd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd73  mov     rax, [rbp+arg_18]
0x18001bd77  mov     [rbp+arg_18], rax
0x18001bd7b  test    rax, rax
0x18001bd7e  jz      loc_18001BE27
0x18001bd84  lea     rcx, [rbp+arg_18]
0x18001bd88  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bd8d  lea     rax, qword_18002DAA8
0x18001bd94  mov     [rbp+var_48], rax
0x18001bd98  lock inc cs:qword_18002DAA8
0x18001bda0  xor     eax, eax
0x18001bda2  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001bdab  jnz     short loc_18001BDCA
0x18001bdad  mov     [rbp+arg_0], 0
0x18001bdb5  lea     rdx, stru_18002DAB0; ListEntry
0x18001bdbc  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001bdc3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001bdc8  xor     edi, edi
0x18001bdca  mov     [rbp+arg_18], 0
0x18001bdd2  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001bdd9  mov     [rbp+var_40], 27Eh
0x18001bde0  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001bde7  mov     [rbp+var_38], rax
0x18001bdeb  mov     [rbp+var_30], 0
0x18001bdf3  mov     rax, [rcx]
0x18001bdf6  mov     rdx, [rsi]
0x18001bdf9  lea     r8, [rbp+arg_18]
0x18001bdfd  mov     rdx, [rdx]
0x18001be00  mov     rax, [rax+50h]
0x18001be04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be09  test    eax, eax
0x18001be0b  js      loc_18001BE95
0x18001be11  mov     rax, [rbp+arg_18]
0x18001be15  mov     [rbx], rax
0x18001be18  lock dec cs:qword_18002DAA8
0x18001be20  test    rdi, rdi
0x18001be23  jz      short loc_18001BE76
0x18001be25  jmp     short loc_18001BE6D
0x18001be27  mov     [rbp+arg_18], 0
0x18001be2f  mov     [rbp+var_40], 27Eh
0x18001be36  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001be3d  mov     [rbp+var_38], rax
0x18001be41  mov     [rbp+var_30], 0
0x18001be49  mov     rax, [rdi]
0x18001be4c  mov     rdx, [rsi]
0x18001be4f  lea     r8, [rbp+arg_18]
0x18001be53  mov     rdx, [rdx]
0x18001be56  mov     rcx, rdi
0x18001be59  mov     rax, [rax+50h]
0x18001be5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be62  test    eax, eax
0x18001be64  js      short loc_18001BE89
0x18001be66  mov     rax, [rbp+arg_18]
0x18001be6a  mov     [rbx], rax
0x18001be6d  lea     rcx, [rbp+arg_0]
0x18001be71  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001be76  mov     rax, rbx
0x18001be79  mov     rbx, [rsp+70h+arg_8]
0x18001be81  add     rsp, 70h
0x18001be85  pop     rdi
0x18001be86  pop     rsi
0x18001be87  pop     rbp
0x18001be88  retn
0x18001be89  lea     rdx, [rbp+var_40]
0x18001be8d  mov     ecx, eax
0x18001be8f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001be95  lea     rdx, [rbp+var_40]
0x18001be99  mov     ecx, eax
0x18001be9b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
