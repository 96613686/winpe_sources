# ??$call@AEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x14003cb98`
- end: `0x14003cd45`
- name: `??$call@AEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `429`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ed10`

## callees

- `0x140006310`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140022678`
- `0x14003cb98`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003cbc5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003cbc5`

## string_xrefs

- `0x14003cbda`: `Windows.Data.Json.JsonObject`
- `0x14003cc8b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x14003ccd9`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__Parse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__Parse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
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
  if ( aWindowsDataJso[28] )
    abort();
  v13[0] = 1;
  v13[1] = 28;
  v14 = L"Windows.Data.Json.JsonObject";
  v12 = v13;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(&v15, &v12);
  v5 = (signed __int64)v15;
  if ( !v15 || (v16 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v16), !v16) )
  {
    v16 = 0;
    v9 = 296;
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_140096A98);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140096AA0);
    v5 = 0;
  }
  v16 = 0;
  v9 = 296;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
         **a3,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_140096A98);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x14003cb98  mov     [rsp-18h+arg_8], rbx
0x14003cb9d  mov     [rsp-18h+arg_10], rsi
0x14003cba2  mov     [rsp-18h+arg_0], rcx
0x14003cba7  push    rbp
0x14003cba8  push    rdi
0x14003cba9  push    r14
0x14003cbab  mov     rbp, rsp
0x14003cbae  sub     rsp, 70h
0x14003cbb2  mov     rsi, r8
0x14003cbb5  mov     rbx, rdx
0x14003cbb8  xor     r14d, r14d
0x14003cbbb  cmp     word ptr cs:aWindowsDataJso+38h, r14w; ""
0x14003cbc3  jz      short loc_14003CBCC
0x14003cbc5  call    cs:__imp_abort
0x14003cbcc  mov     [rbp+var_20], 1
0x14003cbd3  mov     [rbp+var_1C], 1Ch
0x14003cbda  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x14003cbe1  mov     [rbp+var_10], rax
0x14003cbe5  lea     rax, [rbp+var_20]
0x14003cbe9  mov     [rbp+var_28], rax
0x14003cbed  lea     rdx, [rbp+var_28]
0x14003cbf1  lea     rcx, [rbp+arg_0]
0x14003cbf5  call    ??$get_activation_factory@UIJsonObjectStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonObjectStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonObjectStatics>(winrt::param::hstring const &)
0x14003cbfa  nop
0x14003cbfb  mov     rdi, [rbp+arg_0]
0x14003cbff  test    rdi, rdi
0x14003cc02  jz      loc_14003CCCE
0x14003cc08  mov     [rbp+arg_18], r14
0x14003cc0c  mov     rax, [rdi]
0x14003cc0f  lea     r8, [rbp+arg_18]
0x14003cc13  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14003cc1a  mov     rcx, rdi
0x14003cc1d  mov     rax, [rax]
0x14003cc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cc25  mov     rax, [rbp+arg_18]
0x14003cc29  mov     [rbp+arg_18], rax
0x14003cc2d  test    rax, rax
0x14003cc30  jz      loc_14003CCCE
0x14003cc36  lea     rcx, [rbp+arg_18]
0x14003cc3a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003cc3f  lea     rax, qword_140096A98
0x14003cc46  mov     [rbp+var_48], rax
0x14003cc4a  lock inc cs:qword_140096A98
0x14003cc52  xor     eax, eax
0x14003cc54  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x14003cc5d  jnz     short loc_14003CC79
0x14003cc5f  mov     [rbp+arg_0], r14
0x14003cc63  lea     rdx, stru_140096AA0; ListEntry
0x14003cc6a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14003cc71  call    WINRT_IMPL_InterlockedPushEntrySList
0x14003cc76  mov     rdi, r14
0x14003cc79  mov     [rbp+arg_18], r14
0x14003cc7d  mov     rcx, cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x14003cc84  mov     [rbp+var_40], 128h
0x14003cc8b  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003cc92  mov     [rbp+var_38], rax
0x14003cc96  mov     [rbp+var_30], r14
0x14003cc9a  mov     rax, [rcx]
0x14003cc9d  mov     rdx, [rsi]
0x14003cca0  lea     r8, [rbp+arg_18]
0x14003cca4  mov     rdx, [rdx]
0x14003cca7  mov     rax, [rax+30h]
0x14003ccab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ccb0  test    eax, eax
0x14003ccb2  js      loc_14003CD39
0x14003ccb8  mov     rax, [rbp+arg_18]
0x14003ccbc  mov     [rbx], rax
0x14003ccbf  lock dec cs:qword_140096A98
0x14003ccc7  test    rdi, rdi
0x14003ccca  jz      short loc_14003CD15
0x14003cccc  jmp     short loc_14003CD0C
0x14003ccce  mov     [rbp+arg_18], r14
0x14003ccd2  mov     [rbp+var_40], 128h
0x14003ccd9  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003cce0  mov     [rbp+var_38], rax
0x14003cce4  mov     [rbp+var_30], r14
0x14003cce8  mov     rax, [rdi]
0x14003cceb  mov     rdx, [rsi]
0x14003ccee  lea     r8, [rbp+arg_18]
0x14003ccf2  mov     rdx, [rdx]
0x14003ccf5  mov     rcx, rdi
0x14003ccf8  mov     rax, [rax+30h]
0x14003ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cd01  test    eax, eax
0x14003cd03  js      short loc_14003CD2D
0x14003cd05  mov     rax, [rbp+arg_18]
0x14003cd09  mov     [rbx], rax
0x14003cd0c  lea     rcx, [rbp+arg_0]
0x14003cd10  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003cd15  mov     rax, rbx
0x14003cd18  lea     r11, [rsp+70h+var_s0]
0x14003cd1d  mov     rbx, [r11+28h]
0x14003cd21  mov     rsi, [r11+30h]
0x14003cd25  mov     rsp, r11
0x14003cd28  pop     r14
0x14003cd2a  pop     rdi
0x14003cd2b  pop     rbp
0x14003cd2c  retn
0x14003cd2d  lea     rdx, [rbp+var_40]
0x14003cd31  mov     ecx, eax
0x14003cd33  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14003cd39  lea     rdx, [rbp+var_40]
0x14003cd3d  mov     ecx, eax
0x14003cd3f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
