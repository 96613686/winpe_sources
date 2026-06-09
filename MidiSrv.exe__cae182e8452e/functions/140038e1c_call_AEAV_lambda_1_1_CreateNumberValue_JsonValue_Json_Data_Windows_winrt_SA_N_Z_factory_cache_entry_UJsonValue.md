# ??$call@AEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@2@SA@N@Z@@Z

- ea: `0x140038e1c`
- end: `0x140038fce`
- name: `??$call@AEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@2@SA@N@Z@@Z`
- size: `434`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a474`

## callees

- `0x140006310`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140038e1c`
- `0x1400392b0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140038e49`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140038e49`

## string_xrefs

- `0x140038f0f`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x140038f61`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x140038e5e`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
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
    v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, *a3, &v16);
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
  v9 = 620;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 72LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
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
0x140038e1c  mov     [rsp-18h+arg_8], rbx
0x140038e21  mov     [rsp-18h+arg_10], rsi
0x140038e26  mov     [rsp-18h+arg_0], rcx
0x140038e2b  push    rbp
0x140038e2c  push    rdi
0x140038e2d  push    r14
0x140038e2f  mov     rbp, rsp
0x140038e32  sub     rsp, 70h
0x140038e36  mov     rsi, r8
0x140038e39  mov     rbx, rdx
0x140038e3c  xor     r14d, r14d
0x140038e3f  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x140038e47  jz      short loc_140038E50
0x140038e49  call    cs:__imp_abort
0x140038e50  mov     [rbp+var_20], 1
0x140038e57  mov     [rbp+var_1C], 1Bh
0x140038e5e  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x140038e65  mov     [rbp+var_10], rax
0x140038e69  lea     rax, [rbp+var_20]
0x140038e6d  mov     [rbp+var_28], rax
0x140038e71  lea     rdx, [rbp+var_28]
0x140038e75  lea     rcx, [rbp+arg_0]
0x140038e79  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x140038e7e  nop
0x140038e7f  mov     rdi, [rbp+arg_0]
0x140038e83  test    rdi, rdi
0x140038e86  jz      loc_140038F56
0x140038e8c  mov     [rbp+arg_18], r14
0x140038e90  mov     rax, [rdi]
0x140038e93  lea     r8, [rbp+arg_18]
0x140038e97  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140038e9e  mov     rcx, rdi
0x140038ea1  mov     rax, [rax]
0x140038ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ea9  mov     rax, [rbp+arg_18]
0x140038ead  mov     [rbp+arg_18], rax
0x140038eb1  test    rax, rax
0x140038eb4  jz      loc_140038F56
0x140038eba  lea     rcx, [rbp+arg_18]
0x140038ebe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140038ec3  lea     rax, qword_140096AB8
0x140038eca  mov     [rbp+var_48], rax
0x140038ece  lock inc cs:qword_140096AB8
0x140038ed6  xor     eax, eax
0x140038ed8  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x140038ee1  jnz     short loc_140038EFD
0x140038ee3  mov     [rbp+arg_0], r14
0x140038ee7  lea     rdx, stru_140096AC0; ListEntry
0x140038eee  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140038ef5  call    WINRT_IMPL_InterlockedPushEntrySList
0x140038efa  mov     rdi, r14
0x140038efd  mov     [rbp+arg_18], r14
0x140038f01  mov     rdx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x140038f08  mov     [rbp+var_40], 26Ch
0x140038f0f  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140038f16  mov     [rbp+var_38], rax
0x140038f1a  mov     [rbp+var_30], r14
0x140038f1e  mov     rax, [rdx]
0x140038f21  mov     rcx, [rsi]
0x140038f24  lea     r8, [rbp+arg_18]
0x140038f28  movsd   xmm1, qword ptr [rcx]
0x140038f2c  mov     rcx, rdx
0x140038f2f  mov     rax, [rax+48h]
0x140038f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f38  test    eax, eax
0x140038f3a  js      loc_140038FC2
0x140038f40  mov     rax, [rbp+arg_18]
0x140038f44  mov     [rbx], rax
0x140038f47  lock dec cs:qword_140096AB8
0x140038f4f  test    rdi, rdi
0x140038f52  jz      short loc_140038F9E
0x140038f54  jmp     short loc_140038F95
0x140038f56  mov     [rbp+arg_18], r14
0x140038f5a  mov     [rbp+var_40], 26Ch
0x140038f61  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140038f68  mov     [rbp+var_38], rax
0x140038f6c  mov     [rbp+var_30], r14
0x140038f70  mov     rax, [rdi]
0x140038f73  mov     rdx, [rsi]
0x140038f76  lea     r8, [rbp+arg_18]
0x140038f7a  movsd   xmm1, qword ptr [rdx]
0x140038f7e  mov     rcx, rdi
0x140038f81  mov     rax, [rax+48h]
0x140038f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f8a  test    eax, eax
0x140038f8c  js      short loc_140038FB6
0x140038f8e  mov     rax, [rbp+arg_18]
0x140038f92  mov     [rbx], rax
0x140038f95  lea     rcx, [rbp+arg_0]
0x140038f99  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140038f9e  mov     rax, rbx
0x140038fa1  lea     r11, [rsp+70h+var_s0]
0x140038fa6  mov     rbx, [r11+28h]
0x140038faa  mov     rsi, [r11+30h]
0x140038fae  mov     rsp, r11
0x140038fb1  pop     r14
0x140038fb3  pop     rdi
0x140038fb4  pop     rbp
0x140038fb5  retn
0x140038fb6  lea     rdx, [rbp+var_40]
0x140038fba  mov     ecx, eax
0x140038fbc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140038fc2  lea     rdx, [rbp+var_40]
0x140038fc6  mov     ecx, eax
0x140038fc8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
