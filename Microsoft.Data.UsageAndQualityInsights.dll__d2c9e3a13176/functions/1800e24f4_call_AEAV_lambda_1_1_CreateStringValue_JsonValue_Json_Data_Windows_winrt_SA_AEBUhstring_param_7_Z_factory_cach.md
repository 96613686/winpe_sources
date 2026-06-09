# ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x1800e24f4`
- end: `0x1800e26a1`
- name: `??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `429`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e347c`

## callees

- `0x1800051c9`
- `0x18000c844`
- `0x18001112c`
- `0x1800e24f4`
- `0x1800e2960`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e2521`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e2521`

## string_xrefs

- `0x1800e25e7`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x1800e2635`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x1800e2536`: `Windows.Data.Json.JsonValue`

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
    v10 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v16);
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
  v9 = 638;
  v10 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
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
0x1800e24f4  mov     [rsp-18h+arg_8], rbx
0x1800e24f9  mov     [rsp-18h+arg_10], rsi
0x1800e24fe  mov     [rsp-18h+arg_0], rcx
0x1800e2503  push    rbp
0x1800e2504  push    rdi
0x1800e2505  push    r14
0x1800e2507  mov     rbp, rsp
0x1800e250a  sub     rsp, 70h
0x1800e250e  mov     rsi, r8
0x1800e2511  mov     rbx, rdx
0x1800e2514  xor     r14d, r14d
0x1800e2517  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x1800e251f  jz      short loc_1800E2528
0x1800e2521  call    cs:__imp_abort
0x1800e2528  mov     [rbp+var_20], 1
0x1800e252f  mov     [rbp+var_1C], 1Bh
0x1800e2536  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x1800e253d  mov     [rbp+var_10], rax
0x1800e2541  lea     rax, [rbp+var_20]
0x1800e2545  mov     [rbp+var_28], rax
0x1800e2549  lea     rdx, [rbp+var_28]
0x1800e254d  lea     rcx, [rbp+arg_0]
0x1800e2551  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x1800e2556  nop
0x1800e2557  mov     rdi, [rbp+arg_0]
0x1800e255b  test    rdi, rdi
0x1800e255e  jz      loc_1800E262A
0x1800e2564  mov     [rbp+arg_18], r14
0x1800e2568  mov     rax, [rdi]
0x1800e256b  lea     r8, [rbp+arg_18]
0x1800e256f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800e2576  mov     rcx, rdi
0x1800e2579  mov     rax, [rax]
0x1800e257c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2581  mov     rax, [rbp+arg_18]
0x1800e2585  mov     [rbp+arg_18], rax
0x1800e2589  test    rax, rax
0x1800e258c  jz      loc_1800E262A
0x1800e2592  lea     rcx, [rbp+arg_18]
0x1800e2596  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e259b  lea     rax, qword_180159C38
0x1800e25a2  mov     [rbp+var_48], rax
0x1800e25a6  lock inc cs:qword_180159C38
0x1800e25ae  xor     eax, eax
0x1800e25b0  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800e25b9  jnz     short loc_1800E25D5
0x1800e25bb  mov     [rbp+arg_0], r14
0x1800e25bf  lea     rdx, stru_180159C40; ListEntry
0x1800e25c6  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800e25cd  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800e25d2  mov     rdi, r14
0x1800e25d5  mov     [rbp+arg_18], r14
0x1800e25d9  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800e25e0  mov     [rbp+var_40], 27Eh
0x1800e25e7  lea     rax, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800e25ee  mov     [rbp+var_38], rax
0x1800e25f2  mov     [rbp+var_30], r14
0x1800e25f6  mov     rax, [rcx]
0x1800e25f9  mov     rdx, [rsi]
0x1800e25fc  lea     r8, [rbp+arg_18]
0x1800e2600  mov     rdx, [rdx]
0x1800e2603  mov     rax, [rax+50h]
0x1800e2607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e260c  test    eax, eax
0x1800e260e  js      loc_1800E2695
0x1800e2614  mov     rax, [rbp+arg_18]
0x1800e2618  mov     [rbx], rax
0x1800e261b  lock dec cs:qword_180159C38
0x1800e2623  test    rdi, rdi
0x1800e2626  jz      short loc_1800E2671
0x1800e2628  jmp     short loc_1800E2668
0x1800e262a  mov     [rbp+arg_18], r14
0x1800e262e  mov     [rbp+var_40], 27Eh
0x1800e2635  lea     rax, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800e263c  mov     [rbp+var_38], rax
0x1800e2640  mov     [rbp+var_30], r14
0x1800e2644  mov     rax, [rdi]
0x1800e2647  mov     rdx, [rsi]
0x1800e264a  lea     r8, [rbp+arg_18]
0x1800e264e  mov     rdx, [rdx]
0x1800e2651  mov     rcx, rdi
0x1800e2654  mov     rax, [rax+50h]
0x1800e2658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e265d  test    eax, eax
0x1800e265f  js      short loc_1800E2689
0x1800e2661  mov     rax, [rbp+arg_18]
0x1800e2665  mov     [rbx], rax
0x1800e2668  lea     rcx, [rbp+arg_0]
0x1800e266c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e2671  mov     rax, rbx
0x1800e2674  lea     r11, [rsp+70h+var_s0]
0x1800e2679  mov     rbx, [r11+28h]
0x1800e267d  mov     rsi, [r11+30h]
0x1800e2681  mov     rsp, r11
0x1800e2684  pop     r14
0x1800e2686  pop     rdi
0x1800e2687  pop     rbp
0x1800e2688  retn
0x1800e2689  lea     rdx, [rbp+var_40]
0x1800e268d  mov     ecx, eax
0x1800e268f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800e2695  lea     rdx, [rbp+var_40]
0x1800e2699  mov     ecx, eax
0x1800e269b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
