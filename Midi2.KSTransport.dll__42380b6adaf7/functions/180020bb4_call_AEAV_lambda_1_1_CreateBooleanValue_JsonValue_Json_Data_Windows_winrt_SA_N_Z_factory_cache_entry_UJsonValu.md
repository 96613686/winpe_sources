# ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z

- ea: `0x180020bb4`
- end: `0x180020d57`
- name: `??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022080`

## callees

- `0x1800054a9`
- `0x18000d1c0`
- `0x180015348`
- `0x180020bb4`
- `0x180021960`
- `0x180041010`

## string_xrefs

- `0x180020bdc`: `Windows.Data.Json.JsonValue`
- `0x180020c98`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x180020ced`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
    v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v13 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, v8, &v18);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v18;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  _InterlockedIncrement64(&qword_180071CE8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v17 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180071CF0);
    v5 = 0;
  }
  v18 = 0;
  v11 = 602;
  v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
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
  _InterlockedDecrement64(&qword_180071CE8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  return a2;
}

```

## disassembly

```asm
0x180020bb4  mov     [rsp-18h+arg_8], rbx
0x180020bb9  mov     [rsp-18h+arg_0], rcx
0x180020bbe  push    rbp
0x180020bbf  push    rsi
0x180020bc0  push    rdi
0x180020bc1  mov     rbp, rsp
0x180020bc4  sub     rsp, 70h
0x180020bc8  mov     rsi, r8
0x180020bcb  mov     rbx, rdx
0x180020bce  mov     [rbp+var_20], 1
0x180020bd5  mov     [rbp+var_1C], 1Bh
0x180020bdc  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180020be3  mov     [rbp+var_10], rax
0x180020be7  lea     rax, [rbp+var_20]
0x180020beb  mov     [rbp+var_28], rax
0x180020bef  lea     rdx, [rbp+var_28]
0x180020bf3  lea     rcx, [rbp+arg_0]
0x180020bf7  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180020bfc  nop
0x180020bfd  mov     rdi, [rbp+arg_0]
0x180020c01  test    rdi, rdi
0x180020c04  jz      loc_180020CDE
0x180020c0a  mov     [rbp+arg_18], 0
0x180020c12  mov     rax, [rdi]
0x180020c15  lea     r8, [rbp+arg_18]
0x180020c19  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180020c20  mov     rcx, rdi
0x180020c23  mov     rax, [rax]
0x180020c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c2b  mov     rax, [rbp+arg_18]
0x180020c2f  mov     [rbp+arg_18], rax
0x180020c33  test    rax, rax
0x180020c36  jz      loc_180020CDE
0x180020c3c  lea     rcx, [rbp+arg_18]
0x180020c40  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020c45  lea     rax, qword_180071CE8
0x180020c4c  mov     [rbp+var_48], rax
0x180020c50  lock inc cs:qword_180071CE8
0x180020c58  xor     eax, eax
0x180020c5a  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180020c63  jnz     short loc_180020C82
0x180020c65  mov     [rbp+arg_0], 0
0x180020c6d  lea     rdx, stru_180071CF0; ListEntry
0x180020c74  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180020c7b  call    WINRT_IMPL_InterlockedPushEntrySList
0x180020c80  xor     edi, edi
0x180020c82  mov     [rbp+arg_18], 0
0x180020c8a  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180020c91  mov     [rbp+var_40], 25Ah
0x180020c98  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180020c9f  mov     [rbp+var_38], rax
0x180020ca3  mov     [rbp+var_30], 0
0x180020cab  mov     rax, [rcx]
0x180020cae  mov     rdx, [rsi]
0x180020cb1  lea     r8, [rbp+arg_18]
0x180020cb5  mov     dl, [rdx]
0x180020cb7  mov     rax, [rax+40h]
0x180020cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cc0  test    eax, eax
0x180020cc2  js      loc_180020D4B
0x180020cc8  mov     rax, [rbp+arg_18]
0x180020ccc  mov     [rbx], rax
0x180020ccf  lock dec cs:qword_180071CE8
0x180020cd7  test    rdi, rdi
0x180020cda  jz      short loc_180020D2C
0x180020cdc  jmp     short loc_180020D23
0x180020cde  mov     [rbp+arg_18], 0
0x180020ce6  mov     [rbp+var_40], 25Ah
0x180020ced  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180020cf4  mov     [rbp+var_38], rax
0x180020cf8  mov     [rbp+var_30], 0
0x180020d00  mov     rax, [rdi]
0x180020d03  mov     rdx, [rsi]
0x180020d06  lea     r8, [rbp+arg_18]
0x180020d0a  mov     dl, [rdx]
0x180020d0c  mov     rcx, rdi
0x180020d0f  mov     rax, [rax+40h]
0x180020d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d18  test    eax, eax
0x180020d1a  js      short loc_180020D3F
0x180020d1c  mov     rax, [rbp+arg_18]
0x180020d20  mov     [rbx], rax
0x180020d23  lea     rcx, [rbp+arg_0]
0x180020d27  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020d2c  mov     rax, rbx
0x180020d2f  mov     rbx, [rsp+70h+arg_8]
0x180020d37  add     rsp, 70h
0x180020d3b  pop     rdi
0x180020d3c  pop     rsi
0x180020d3d  pop     rbp
0x180020d3e  retn
0x180020d3f  lea     rdx, [rbp+var_40]
0x180020d43  mov     ecx, eax
0x180020d45  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180020d4b  lea     rdx, [rbp+var_40]
0x180020d4f  mov     ecx, eax
0x180020d51  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
