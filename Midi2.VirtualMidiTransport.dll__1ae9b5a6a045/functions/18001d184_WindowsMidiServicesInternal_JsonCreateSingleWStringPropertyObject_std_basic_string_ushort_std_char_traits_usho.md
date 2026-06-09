# WindowsMidiServicesInternal::JsonCreateSingleWStringPropertyObject(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001d184`
- end: `0x18001d333`
- name: `?JsonCreateSingleWStringPropertyObject@WindowsMidiServicesInternal@@YA?AUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001bcfc`
- `0x18001c12c`
- `0x18001c9a8`
- `0x18001d184`
- `0x18001d3d8`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d320`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d320`

## string_xrefs

- `0x18001d25a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::JsonCreateSingleWStringPropertyObject(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  __int64 (__fastcall *v8)(); // rbx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-60h] BYREF
  const char *v12; // [rsp+28h] [rbp-58h]
  __int64 v13; // [rsp+30h] [rbp-50h]
  _DWORD *v14; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v15[4]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-30h]
  _DWORD *v17; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v18[4]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD *v19; // [rsp+70h] [rbp-10h]
  __int64 (__fastcall *v20)(); // [rsp+A0h] [rbp+20h] BYREF
  _QWORD *v21; // [rsp+B0h] [rbp+30h] BYREF

  _InterlockedIncrement64(&qword_18002DA68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
      a1,
      a1,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18002DA68);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002DA68);
    v20 = `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      a1,
      &v20);
  }
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)a3 + v6) );
  if ( (_DWORD)v6 )
  {
    if ( *((_WORD *)a3 + (unsigned int)v6) )
      goto LABEL_25;
    v15[0] = 1;
    v15[1] = v6;
    v16 = a3;
    v14 = v15;
  }
  else
  {
    v14 = 0;
  }
  v21 = &v14;
  _InterlockedIncrement64(&qword_18002DAA8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v20 = 0;
    v11 = 638;
    v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v13 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64 (__fastcall **)()))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                                                 + 80LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           v14,
           &v20);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v11);
    v8 = v20;
    _InterlockedDecrement64(&qword_18002DAA8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002DAA8);
    ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
      0,
      &v20,
      &v21);
    v8 = v20;
  }
  v9 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( !(_DWORD)v9 )
  {
    v17 = 0;
    goto LABEL_22;
  }
  if ( *((_WORD *)a2 + (unsigned int)v9) )
LABEL_25:
    abort();
  v18[0] = 1;
  v18[1] = v9;
  v19 = a2;
  v17 = v18;
LABEL_22:
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a1,
    &v17,
    &v20);
  if ( v8 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  return a1;
}

```

## disassembly

```asm
0x18001d184  mov     [rsp-18h+arg_8], rbx
0x18001d189  mov     [rsp-18h+arg_18], rsi
0x18001d18e  push    rbp
0x18001d18f  push    rdi
0x18001d190  push    r14
0x18001d192  mov     rbp, rsp
0x18001d195  sub     rsp, 80h
0x18001d19c  mov     rbx, r8
0x18001d19f  mov     rdi, rdx
0x18001d1a2  mov     rsi, rcx
0x18001d1a5  lock inc cs:qword_18002DA68
0x18001d1ad  xor     r14d, r14d
0x18001d1b0  mov     rdx, rcx
0x18001d1b3  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r14; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d1ba  jz      short loc_18001D1D2
0x18001d1bc  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d1c3  call    ??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d1c8  lock dec cs:qword_18002DA68
0x18001d1d0  jmp     short loc_18001D1EE
0x18001d1d2  lock dec cs:qword_18002DA68
0x18001d1da  lea     rax, ?_lambda_invoker_cdecl_@_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d1e1  mov     [rbp+arg_0], rax
0x18001d1e5  lea     r8, [rbp+arg_0]
0x18001d1e9  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18001d1ee  cmp     qword ptr [rbx+18h], 7
0x18001d1f3  jbe     short loc_18001D1F8
0x18001d1f5  mov     rbx, [rbx]
0x18001d1f8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001d1fc  inc     rcx
0x18001d1ff  cmp     [rbx+rcx*2], r14w
0x18001d204  jnz     short loc_18001D1FC
0x18001d206  test    ecx, ecx
0x18001d208  jnz     short loc_18001D210
0x18001d20a  mov     [rbp+var_48], r14
0x18001d20e  jmp     short loc_18001D233
0x18001d210  mov     eax, ecx
0x18001d212  cmp     [rbx+rax*2], r14w
0x18001d217  jnz     loc_18001D320
0x18001d21d  mov     [rbp+var_40], 1
0x18001d224  mov     [rbp+var_3C], ecx
0x18001d227  mov     [rbp+var_30], rbx
0x18001d22b  lea     rax, [rbp+var_40]
0x18001d22f  mov     [rbp+var_48], rax
0x18001d233  lea     rax, [rbp+var_48]
0x18001d237  mov     [rbp+arg_10], rax
0x18001d23b  lock inc cs:qword_18002DAA8
0x18001d243  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001d24a  test    rcx, rcx
0x18001d24d  jz      short loc_18001D297
0x18001d24f  mov     [rbp+arg_0], r14
0x18001d253  mov     [rbp+var_60], 27Eh
0x18001d25a  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d261  mov     [rbp+var_58], rax
0x18001d265  mov     [rbp+var_50], r14
0x18001d269  mov     rax, [rcx]
0x18001d26c  lea     r8, [rbp+arg_0]
0x18001d270  mov     rdx, [rbp+var_48]
0x18001d274  mov     rax, [rax+50h]
0x18001d278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d27d  test    eax, eax
0x18001d27f  js      loc_18001D327
0x18001d285  mov     rbx, [rbp+arg_0]
0x18001d289  mov     [rbp+arg_0], rbx
0x18001d28d  lock dec cs:qword_18002DAA8
0x18001d295  jmp     short loc_18001D2B0
0x18001d297  lock dec cs:qword_18002DAA8
0x18001d29f  lea     r8, [rbp+arg_10]
0x18001d2a3  lea     rdx, [rbp+arg_0]
0x18001d2a7  call    ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x18001d2ac  mov     rbx, [rbp+arg_0]
0x18001d2b0  mov     rcx, [rdi+10h]
0x18001d2b4  cmp     qword ptr [rdi+18h], 7
0x18001d2b9  jbe     short loc_18001D2BE
0x18001d2bb  mov     rdi, [rdi]
0x18001d2be  test    ecx, ecx
0x18001d2c0  jnz     short loc_18001D2C8
0x18001d2c2  mov     [rbp+var_28], r14
0x18001d2c6  jmp     short loc_18001D2E7
0x18001d2c8  mov     eax, ecx
0x18001d2ca  cmp     [rdi+rax*2], r14w
0x18001d2cf  jnz     short loc_18001D320
0x18001d2d1  mov     [rbp+var_20], 1
0x18001d2d8  mov     [rbp+var_1C], ecx
0x18001d2db  mov     [rbp+var_10], rdi
0x18001d2df  lea     rax, [rbp+var_20]
0x18001d2e3  mov     [rbp+var_28], rax
0x18001d2e7  lea     r8, [rbp+arg_0]
0x18001d2eb  lea     rdx, [rbp+var_28]
0x18001d2ef  mov     rcx, rsi
0x18001d2f2  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001d2f7  test    rbx, rbx
0x18001d2fa  jz      short loc_18001D305
0x18001d2fc  lea     rcx, [rbp+arg_0]
0x18001d300  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d305  mov     rax, rsi
0x18001d308  lea     r11, [rsp+80h+var_s0]
0x18001d310  mov     rbx, [r11+28h]
0x18001d314  mov     rsi, [r11+38h]
0x18001d318  mov     rsp, r11
0x18001d31b  pop     r14
0x18001d31d  pop     rdi
0x18001d31e  pop     rbp
0x18001d31f  retn
0x18001d320  call    cs:__imp_abort
0x18001d327  lea     rdx, [rbp+var_60]
0x18001d32b  mov     ecx, eax
0x18001d32d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
