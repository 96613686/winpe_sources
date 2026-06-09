# ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z

- ea: `0x1800f1040`
- end: `0x1800f11eb`
- name: `??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z`
- size: `427`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _BYTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2958`

## callees

- `0x1800051c9`
- `0x18000c844`
- `0x18001112c`
- `0x1800e2960`
- `0x1800f1040`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f106d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f106d`

## string_xrefs

- `0x1800f1133`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x1800f1180`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x1800f1082`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    v12 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v13 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, v8, &v18);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v18;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v18);
  _InterlockedIncrement64(&qword_180159C38);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v17 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180159C40);
    v5 = 0;
  }
  v18 = 0;
  v11 = 602;
  v12 = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
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
  _InterlockedDecrement64(&qword_180159C38);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
  return a2;
}

```

## disassembly

```asm
0x1800f1040  mov     [rsp-18h+arg_8], rbx
0x1800f1045  mov     [rsp-18h+arg_10], rsi
0x1800f104a  mov     [rsp-18h+arg_0], rcx
0x1800f104f  push    rbp
0x1800f1050  push    rdi
0x1800f1051  push    r14
0x1800f1053  mov     rbp, rsp
0x1800f1056  sub     rsp, 70h
0x1800f105a  mov     rsi, r8
0x1800f105d  mov     rbx, rdx
0x1800f1060  xor     r14d, r14d
0x1800f1063  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x1800f106b  jz      short loc_1800F1074
0x1800f106d  call    cs:__imp_abort
0x1800f1074  mov     [rbp+var_20], 1
0x1800f107b  mov     [rbp+var_1C], 1Bh
0x1800f1082  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x1800f1089  mov     [rbp+var_10], rax
0x1800f108d  lea     rax, [rbp+var_20]
0x1800f1091  mov     [rbp+var_28], rax
0x1800f1095  lea     rdx, [rbp+var_28]
0x1800f1099  lea     rcx, [rbp+arg_0]
0x1800f109d  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x1800f10a2  nop
0x1800f10a3  mov     rdi, [rbp+arg_0]
0x1800f10a7  test    rdi, rdi
0x1800f10aa  jz      loc_1800F1175
0x1800f10b0  mov     [rbp+arg_18], r14
0x1800f10b4  mov     rax, [rdi]
0x1800f10b7  lea     r8, [rbp+arg_18]
0x1800f10bb  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800f10c2  mov     rcx, rdi
0x1800f10c5  mov     rax, [rax]
0x1800f10c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f10cd  mov     rax, [rbp+arg_18]
0x1800f10d1  mov     [rbp+arg_18], rax
0x1800f10d5  test    rax, rax
0x1800f10d8  jz      loc_1800F1175
0x1800f10de  lea     rcx, [rbp+arg_18]
0x1800f10e2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f10e7  lea     rax, qword_180159C38
0x1800f10ee  mov     [rbp+var_48], rax
0x1800f10f2  lock inc cs:qword_180159C38
0x1800f10fa  xor     eax, eax
0x1800f10fc  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800f1105  jnz     short loc_1800F1121
0x1800f1107  mov     [rbp+arg_0], r14
0x1800f110b  lea     rdx, stru_180159C40; ListEntry
0x1800f1112  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800f1119  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800f111e  mov     rdi, r14
0x1800f1121  mov     [rbp+arg_18], r14
0x1800f1125  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800f112c  mov     [rbp+var_40], 25Ah
0x1800f1133  lea     rax, aOnecoreuapInte_13; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800f113a  mov     [rbp+var_38], rax
0x1800f113e  mov     [rbp+var_30], r14
0x1800f1142  mov     rax, [rcx]
0x1800f1145  mov     rdx, [rsi]
0x1800f1148  lea     r8, [rbp+arg_18]
0x1800f114c  mov     dl, [rdx]
0x1800f114e  mov     rax, [rax+40h]
0x1800f1152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1157  test    eax, eax
0x1800f1159  js      loc_1800F11DF
0x1800f115f  mov     rax, [rbp+arg_18]
0x1800f1163  mov     [rbx], rax
0x1800f1166  lock dec cs:qword_180159C38
0x1800f116e  test    rdi, rdi
0x1800f1171  jz      short loc_1800F11BB
0x1800f1173  jmp     short loc_1800F11B2
0x1800f1175  mov     [rbp+arg_18], r14
0x1800f1179  mov     [rbp+var_40], 25Ah
0x1800f1180  lea     rax, aOnecoreuapInte_13; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800f1187  mov     [rbp+var_38], rax
0x1800f118b  mov     [rbp+var_30], r14
0x1800f118f  mov     rax, [rdi]
0x1800f1192  mov     rdx, [rsi]
0x1800f1195  lea     r8, [rbp+arg_18]
0x1800f1199  mov     dl, [rdx]
0x1800f119b  mov     rcx, rdi
0x1800f119e  mov     rax, [rax+40h]
0x1800f11a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f11a7  test    eax, eax
0x1800f11a9  js      short loc_1800F11D3
0x1800f11ab  mov     rax, [rbp+arg_18]
0x1800f11af  mov     [rbx], rax
0x1800f11b2  lea     rcx, [rbp+arg_0]
0x1800f11b6  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f11bb  mov     rax, rbx
0x1800f11be  lea     r11, [rsp+70h+var_s0]
0x1800f11c3  mov     rbx, [r11+28h]
0x1800f11c7  mov     rsi, [r11+30h]
0x1800f11cb  mov     rsp, r11
0x1800f11ce  pop     r14
0x1800f11d0  pop     rdi
0x1800f11d1  pop     rbp
0x1800f11d2  retn
0x1800f11d3  lea     rdx, [rbp+var_40]
0x1800f11d7  mov     ecx, eax
0x1800f11d9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800f11df  lea     rdx, [rbp+var_40]
0x1800f11e3  mov     ecx, eax
0x1800f11e5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
