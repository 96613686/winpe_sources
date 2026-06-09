# ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z

- ea: `0x180015198`
- end: `0x1800152f1`
- name: `??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x1800051fd`
- `0x18000ea80`
- `0x1800145d8`
- `0x180014974`
- `0x180015198`
- `0x1800166ec`
- `0x180032010`

## string_xrefs

- `0x1800151c0`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v3; // rbx
  char v4; // di
  int v6; // [rsp+20h] [rbp-40h] BYREF
  const char *v7; // [rsp+28h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-30h]
  _DWORD *v9; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+50h] [rbp-10h]
  __int64 *v12; // [rsp+70h] [rbp+10h] BYREF
  __int64 *v13; // [rsp+80h] [rbp+20h] BYREF

  v12 = a1;
  v10[0] = 1;
  v10[1] = 28;
  v11 = L"Windows.Data.Json.JsonObject";
  v9 = v10;
  v13 = 0;
  v6 = 6172;
  v7 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    (__int64)winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>,
    (__int64)&v13);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v6);
  v3 = v13;
  v12 = v13;
  if ( v13
    && (v13 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v3)(
          v3,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v13),
        v13) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    v13 = &qword_18005FAA8;
    _InterlockedIncrement64(&qword_18005FAA8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            (signed __int64)v3,
            0) )
    {
      v3 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18005FAB0);
    }
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_18005FAA8);
  }
  else
  {
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(a2, &v12);
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return v4;
}

```

## disassembly

```asm
0x180015198  mov     [rsp-8+arg_8], rbx
0x18001519d  mov     [rsp-8+arg_18], rdi
0x1800151a2  mov     [rsp-8+arg_0], rcx
0x1800151a7  push    rbp
0x1800151a8  mov     rbp, rsp
0x1800151ab  sub     rsp, 60h
0x1800151af  mov     rdi, rdx
0x1800151b2  mov     [rbp+var_20], 1
0x1800151b9  mov     [rbp+var_1C], 1Ch
0x1800151c0  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x1800151c7  mov     [rbp+var_10], rax
0x1800151cb  lea     rax, [rbp+var_20]
0x1800151cf  mov     [rbp+var_28], rax
0x1800151d3  mov     [rbp+arg_10], 0
0x1800151db  mov     [rbp+var_40], 181Ch
0x1800151e2  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800151e9  mov     [rbp+var_38], rax
0x1800151ed  mov     [rbp+var_30], 0
0x1800151f5  lea     r9, [rbp+arg_10]
0x1800151f9  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x180015200  lea     rdx, [rbp+var_28]
0x180015204  lea     rcx, [rbp+arg_0]
0x180015208  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001520d  mov     ecx, dword ptr [rbp+arg_0]
0x180015210  test    ecx, ecx
0x180015212  js      loc_1800152E7
0x180015218  mov     rbx, [rbp+arg_10]
0x18001521c  mov     [rbp+arg_0], rbx
0x180015220  test    rbx, rbx
0x180015223  jz      loc_1800152B5
0x180015229  mov     [rbp+arg_10], 0
0x180015231  mov     rax, [rbx]
0x180015234  lea     r8, [rbp+arg_10]
0x180015238  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001523f  mov     rcx, rbx
0x180015242  mov     rax, [rax]
0x180015245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001524a  mov     rax, [rbp+arg_10]
0x18001524e  mov     [rbp+arg_10], rax
0x180015252  test    rax, rax
0x180015255  jz      short loc_1800152B5
0x180015257  lea     rcx, [rbp+arg_10]
0x18001525b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015260  lea     rax, qword_18005FAA8
0x180015267  mov     [rbp+arg_10], rax
0x18001526b  lock inc cs:qword_18005FAA8
0x180015273  xor     eax, eax
0x180015275  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001527e  jnz     short loc_180015299
0x180015280  xor     ebx, ebx
0x180015282  mov     [rbp+arg_0], rbx
0x180015286  lea     rdx, stru_18005FAB0; ListEntry
0x18001528d  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180015294  call    WINRT_IMPL_InterlockedPushEntrySList
0x180015299  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x1800152a0  mov     rcx, rdi
0x1800152a3  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x1800152a8  mov     dil, al
0x1800152ab  lock dec cs:qword_18005FAA8
0x1800152b3  jmp     short loc_1800152C4
0x1800152b5  lea     rdx, [rbp+arg_0]
0x1800152b9  mov     rcx, rdi
0x1800152bc  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x1800152c1  mov     dil, al
0x1800152c4  test    rbx, rbx
0x1800152c7  jz      short loc_1800152D2
0x1800152c9  lea     rcx, [rbp+arg_0]
0x1800152cd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800152d2  mov     al, dil
0x1800152d5  lea     r11, [rsp+60h+var_s0]
0x1800152da  mov     rbx, [r11+18h]
0x1800152de  mov     rdi, [r11+28h]
0x1800152e2  mov     rsp, r11
0x1800152e5  pop     rbp
0x1800152e6  retn
0x1800152e7  lea     rdx, [rbp+var_40]
0x1800152eb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
