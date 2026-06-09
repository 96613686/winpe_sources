# ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z

- ea: `0x1400223c0`
- end: `0x1400224db`
- name: `??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z`
- size: `283`
- prototype: `char __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002455c`
- `0x140025978`

## callees

- `0x140006310`
- `0x14000cc2c`
- `0x1400223c0`
- `0x140022678`
- `0x140023108`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400223e2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400223e2`

## string_xrefs

- `0x1400223f7`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
char __fastcall ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2)
{
  signed __int64 v3; // rbx
  char v4; // di
  _DWORD *v6; // [rsp+20h] [rbp-20h] BYREF
  _DWORD v7[4]; // [rsp+28h] [rbp-18h] BYREF
  const wchar_t *v8; // [rsp+38h] [rbp-8h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+70h] [rbp+30h] BYREF

  v9 = a1;
  if ( aWindowsDataJso[28] )
    abort();
  v7[0] = 1;
  v7[1] = 28;
  v8 = L"Windows.Data.Json.JsonObject";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(&v9, &v6);
  v3 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_140096A98;
    _InterlockedIncrement64(&qword_140096A98);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            v3,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096AA0);
      v3 = 0;
    }
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_140096A98);
  }
  else
  {
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(a2, &v9);
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return v4;
}

```

## disassembly

```asm
0x1400223c0  mov     [rsp-18h+arg_8], rbx
0x1400223c5  mov     [rsp-18h+arg_0], rcx
0x1400223ca  push    rbp
0x1400223cb  push    rsi
0x1400223cc  push    rdi
0x1400223cd  mov     rbp, rsp
0x1400223d0  sub     rsp, 40h
0x1400223d4  mov     rdi, rdx
0x1400223d7  xor     esi, esi
0x1400223d9  cmp     word ptr cs:aWindowsDataJso+38h, si; ""
0x1400223e0  jz      short loc_1400223E9
0x1400223e2  call    cs:__imp_abort
0x1400223e9  mov     [rbp+var_18], 1
0x1400223f0  mov     [rbp+var_14], 1Ch
0x1400223f7  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x1400223fe  mov     [rbp+var_8], rax
0x140022402  lea     rax, [rbp+var_18]
0x140022406  mov     [rbp+var_20], rax
0x14002240a  lea     rdx, [rbp+var_20]
0x14002240e  lea     rcx, [rbp+arg_0]
0x140022412  call    ??$get_activation_factory@UIJsonObjectStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonObjectStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(winrt::param::hstring const &)
0x140022417  nop
0x140022418  mov     rbx, [rbp+arg_0]
0x14002241c  test    rbx, rbx
0x14002241f  jz      loc_1400224AE
0x140022425  mov     [rbp+arg_10], rsi
0x140022429  mov     rax, [rbx]
0x14002242c  lea     r8, [rbp+arg_10]
0x140022430  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140022437  mov     rcx, rbx
0x14002243a  mov     rax, [rax]
0x14002243d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022442  mov     rax, [rbp+arg_10]
0x140022446  mov     [rbp+arg_10], rax
0x14002244a  test    rax, rax
0x14002244d  jz      short loc_1400224AE
0x14002244f  lea     rcx, [rbp+arg_10]
0x140022453  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140022458  lea     rax, qword_140096A98
0x14002245f  mov     [rbp+arg_10], rax
0x140022463  lock inc cs:qword_140096A98
0x14002246b  xor     eax, eax
0x14002246d  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x140022476  jnz     short loc_140022492
0x140022478  mov     [rbp+arg_0], rsi
0x14002247c  lea     rdx, stru_140096AA0; ListEntry
0x140022483  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14002248a  call    WINRT_IMPL_InterlockedPushEntrySList
0x14002248f  mov     rbx, rsi
0x140022492  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x140022499  mov     rcx, rdi
0x14002249c  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x1400224a1  mov     dil, al
0x1400224a4  lock dec cs:qword_140096A98
0x1400224ac  jmp     short loc_1400224BD
0x1400224ae  lea     rdx, [rbp+arg_0]
0x1400224b2  mov     rcx, rdi
0x1400224b5  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x1400224ba  mov     dil, al
0x1400224bd  test    rbx, rbx
0x1400224c0  jz      short loc_1400224CB
0x1400224c2  lea     rcx, [rbp+arg_0]
0x1400224c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400224cb  mov     al, dil
0x1400224ce  mov     rbx, [rsp+40h+arg_8]
0x1400224d3  add     rsp, 40h
0x1400224d7  pop     rdi
0x1400224d8  pop     rsi
0x1400224d9  pop     rbp
0x1400224da  retn
```
