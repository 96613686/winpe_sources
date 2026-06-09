# ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z

- ea: `0x18001b75c`
- end: `0x18001b8ff`
- name: `??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cd34`

## callees

- `0x180006031`
- `0x180010b94`
- `0x18001a4a8`
- `0x18001b75c`
- `0x18001c508`
- `0x18005e010`

## string_xrefs

- `0x18001b784`: `Windows.Data.Json.JsonValue`
- `0x18001b840`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`
- `0x18001b895`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
  _InterlockedIncrement64(&qword_180096B68);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v17 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180096B70);
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
  _InterlockedDecrement64(&qword_180096B68);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  return a2;
}

```

## disassembly

```asm
0x18001b75c  mov     [rsp-18h+arg_8], rbx
0x18001b761  mov     [rsp-18h+arg_0], rcx
0x18001b766  push    rbp
0x18001b767  push    rsi
0x18001b768  push    rdi
0x18001b769  mov     rbp, rsp
0x18001b76c  sub     rsp, 70h
0x18001b770  mov     rsi, r8
0x18001b773  mov     rbx, rdx
0x18001b776  mov     [rbp+var_20], 1
0x18001b77d  mov     [rbp+var_1C], 1Bh
0x18001b784  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x18001b78b  mov     [rbp+var_10], rax
0x18001b78f  lea     rax, [rbp+var_20]
0x18001b793  mov     [rbp+var_28], rax
0x18001b797  lea     rdx, [rbp+var_28]
0x18001b79b  lea     rcx, [rbp+arg_0]
0x18001b79f  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x18001b7a4  nop
0x18001b7a5  mov     rdi, [rbp+arg_0]
0x18001b7a9  test    rdi, rdi
0x18001b7ac  jz      loc_18001B886
0x18001b7b2  mov     [rbp+arg_18], 0
0x18001b7ba  mov     rax, [rdi]
0x18001b7bd  lea     r8, [rbp+arg_18]
0x18001b7c1  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001b7c8  mov     rcx, rdi
0x18001b7cb  mov     rax, [rax]
0x18001b7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d3  mov     rax, [rbp+arg_18]
0x18001b7d7  mov     [rbp+arg_18], rax
0x18001b7db  test    rax, rax
0x18001b7de  jz      loc_18001B886
0x18001b7e4  lea     rcx, [rbp+arg_18]
0x18001b7e8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b7ed  lea     rax, qword_180096B68
0x18001b7f4  mov     [rbp+var_48], rax
0x18001b7f8  lock inc cs:qword_180096B68
0x18001b800  xor     eax, eax
0x18001b802  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001b80b  jnz     short loc_18001B82A
0x18001b80d  mov     [rbp+arg_0], 0
0x18001b815  lea     rdx, stru_180096B70; ListEntry
0x18001b81c  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001b823  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001b828  xor     edi, edi
0x18001b82a  mov     [rbp+arg_18], 0
0x18001b832  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001b839  mov     [rbp+var_40], 25Ah
0x18001b840  lea     rax, aOnecoreuapInte_8; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001b847  mov     [rbp+var_38], rax
0x18001b84b  mov     [rbp+var_30], 0
0x18001b853  mov     rax, [rcx]
0x18001b856  mov     rdx, [rsi]
0x18001b859  lea     r8, [rbp+arg_18]
0x18001b85d  mov     dl, [rdx]
0x18001b85f  mov     rax, [rax+40h]
0x18001b863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b868  test    eax, eax
0x18001b86a  js      loc_18001B8F3
0x18001b870  mov     rax, [rbp+arg_18]
0x18001b874  mov     [rbx], rax
0x18001b877  lock dec cs:qword_180096B68
0x18001b87f  test    rdi, rdi
0x18001b882  jz      short loc_18001B8D4
0x18001b884  jmp     short loc_18001B8CB
0x18001b886  mov     [rbp+arg_18], 0
0x18001b88e  mov     [rbp+var_40], 25Ah
0x18001b895  lea     rax, aOnecoreuapInte_8; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001b89c  mov     [rbp+var_38], rax
0x18001b8a0  mov     [rbp+var_30], 0
0x18001b8a8  mov     rax, [rdi]
0x18001b8ab  mov     rdx, [rsi]
0x18001b8ae  lea     r8, [rbp+arg_18]
0x18001b8b2  mov     dl, [rdx]
0x18001b8b4  mov     rcx, rdi
0x18001b8b7  mov     rax, [rax+40h]
0x18001b8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c0  test    eax, eax
0x18001b8c2  js      short loc_18001B8E7
0x18001b8c4  mov     rax, [rbp+arg_18]
0x18001b8c8  mov     [rbx], rax
0x18001b8cb  lea     rcx, [rbp+arg_0]
0x18001b8cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b8d4  mov     rax, rbx
0x18001b8d7  mov     rbx, [rsp+70h+arg_8]
0x18001b8df  add     rsp, 70h
0x18001b8e3  pop     rdi
0x18001b8e4  pop     rsi
0x18001b8e5  pop     rbp
0x18001b8e6  retn
0x18001b8e7  lea     rdx, [rbp+var_40]
0x18001b8eb  mov     ecx, eax
0x18001b8ed  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001b8f3  lea     rdx, [rbp+var_40]
0x18001b8f7  mov     ecx, eax
0x18001b8f9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
