# ??$call@AEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@2@SA@N@Z@@Z

- ea: `0x1800e233c`
- end: `0x1800e24ee`
- name: `??$call@AEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@2@SA@N@Z@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e33bc`

## callees

- `0x1800051c9`
- `0x18000c844`
- `0x18001112c`
- `0x1800e233c`
- `0x1800e2960`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e2369`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e2369`

## string_xrefs

- `0x1800e242f`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x1800e2481`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x1800e237e`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateNumberValue_JsonValue_Json_Data_Windows_winrt__SA_N_Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateNumberValue_JsonValue_Json_Data_Windows_2_SA_N_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD *a3)
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
    v9 = 620;
    v10 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, *a3, &v16);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v16;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v16);
  _InterlockedIncrement64(&qword_180159C38);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v15 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180159C40);
    v5 = 0;
  }
  v16 = 0;
  v9 = 620;
  v10 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 72LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         &v16);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v16;
  _InterlockedDecrement64(&qword_180159C38);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
  return a2;
}

```

## disassembly

```asm
0x1800e233c  mov     [rsp-18h+arg_8], rbx
0x1800e2341  mov     [rsp-18h+arg_10], rsi
0x1800e2346  mov     [rsp-18h+arg_0], rcx
0x1800e234b  push    rbp
0x1800e234c  push    rdi
0x1800e234d  push    r14
0x1800e234f  mov     rbp, rsp
0x1800e2352  sub     rsp, 70h
0x1800e2356  mov     rsi, r8
0x1800e2359  mov     rbx, rdx
0x1800e235c  xor     r14d, r14d
0x1800e235f  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x1800e2367  jz      short loc_1800E2370
0x1800e2369  call    cs:__imp_abort
0x1800e2370  mov     [rbp+var_20], 1
0x1800e2377  mov     [rbp+var_1C], 1Bh
0x1800e237e  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x1800e2385  mov     [rbp+var_10], rax
0x1800e2389  lea     rax, [rbp+var_20]
0x1800e238d  mov     [rbp+var_28], rax
0x1800e2391  lea     rdx, [rbp+var_28]
0x1800e2395  lea     rcx, [rbp+arg_0]
0x1800e2399  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x1800e239e  nop
0x1800e239f  mov     rdi, [rbp+arg_0]
0x1800e23a3  test    rdi, rdi
0x1800e23a6  jz      loc_1800E2476
0x1800e23ac  mov     [rbp+arg_18], r14
0x1800e23b0  mov     rax, [rdi]
0x1800e23b3  lea     r8, [rbp+arg_18]
0x1800e23b7  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800e23be  mov     rcx, rdi
0x1800e23c1  mov     rax, [rax]
0x1800e23c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e23c9  mov     rax, [rbp+arg_18]
0x1800e23cd  mov     [rbp+arg_18], rax
0x1800e23d1  test    rax, rax
0x1800e23d4  jz      loc_1800E2476
0x1800e23da  lea     rcx, [rbp+arg_18]
0x1800e23de  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e23e3  lea     rax, qword_180159C38
0x1800e23ea  mov     [rbp+var_48], rax
0x1800e23ee  lock inc cs:qword_180159C38
0x1800e23f6  xor     eax, eax
0x1800e23f8  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800e2401  jnz     short loc_1800E241D
0x1800e2403  mov     [rbp+arg_0], r14
0x1800e2407  lea     rdx, stru_180159C40; ListEntry
0x1800e240e  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800e2415  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800e241a  mov     rdi, r14
0x1800e241d  mov     [rbp+arg_18], r14
0x1800e2421  mov     rdx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800e2428  mov     [rbp+var_40], 26Ch
0x1800e242f  lea     rax, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800e2436  mov     [rbp+var_38], rax
0x1800e243a  mov     [rbp+var_30], r14
0x1800e243e  mov     rax, [rdx]
0x1800e2441  mov     rcx, [rsi]
0x1800e2444  lea     r8, [rbp+arg_18]
0x1800e2448  movsd   xmm1, qword ptr [rcx]
0x1800e244c  mov     rcx, rdx
0x1800e244f  mov     rax, [rax+48h]
0x1800e2453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2458  test    eax, eax
0x1800e245a  js      loc_1800E24E2
0x1800e2460  mov     rax, [rbp+arg_18]
0x1800e2464  mov     [rbx], rax
0x1800e2467  lock dec cs:qword_180159C38
0x1800e246f  test    rdi, rdi
0x1800e2472  jz      short loc_1800E24BE
0x1800e2474  jmp     short loc_1800E24B5
0x1800e2476  mov     [rbp+arg_18], r14
0x1800e247a  mov     [rbp+var_40], 26Ch
0x1800e2481  lea     rax, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800e2488  mov     [rbp+var_38], rax
0x1800e248c  mov     [rbp+var_30], r14
0x1800e2490  mov     rax, [rdi]
0x1800e2493  mov     rdx, [rsi]
0x1800e2496  lea     r8, [rbp+arg_18]
0x1800e249a  movsd   xmm1, qword ptr [rdx]
0x1800e249e  mov     rcx, rdi
0x1800e24a1  mov     rax, [rax+48h]
0x1800e24a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e24aa  test    eax, eax
0x1800e24ac  js      short loc_1800E24D6
0x1800e24ae  mov     rax, [rbp+arg_18]
0x1800e24b2  mov     [rbx], rax
0x1800e24b5  lea     rcx, [rbp+arg_0]
0x1800e24b9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e24be  mov     rax, rbx
0x1800e24c1  lea     r11, [rsp+70h+var_s0]
0x1800e24c6  mov     rbx, [r11+28h]
0x1800e24ca  mov     rsi, [r11+30h]
0x1800e24ce  mov     rsp, r11
0x1800e24d1  pop     r14
0x1800e24d3  pop     rdi
0x1800e24d4  pop     rbp
0x1800e24d5  retn
0x1800e24d6  lea     rdx, [rbp+var_40]
0x1800e24da  mov     ecx, eax
0x1800e24dc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800e24e2  lea     rdx, [rbp+var_40]
0x1800e24e6  mov     ecx, eax
0x1800e24e8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
