# ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z

- ea: `0x18001bea8`
- end: `0x18001c001`
- name: `??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x1800047ed`
- `0x1800130d0`
- `0x18001a3fc`
- `0x18001a798`
- `0x18001bea8`
- `0x18001ca5c`
- `0x180021010`

## string_xrefs

- `0x18001bed0`: `Windows.Data.Json.JsonObject`

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
    v13 = &qword_18002DA88;
    _InterlockedIncrement64(&qword_18002DA88);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            (signed __int64)v3,
            0) )
    {
      v3 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002DA90);
    }
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_18002DA88);
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
0x18001bea8  mov     [rsp-8+arg_8], rbx
0x18001bead  mov     [rsp-8+arg_18], rdi
0x18001beb2  mov     [rsp-8+arg_0], rcx
0x18001beb7  push    rbp
0x18001beb8  mov     rbp, rsp
0x18001bebb  sub     rsp, 60h
0x18001bebf  mov     rdi, rdx
0x18001bec2  mov     [rbp+var_20], 1
0x18001bec9  mov     [rbp+var_1C], 1Ch
0x18001bed0  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18001bed7  mov     [rbp+var_10], rax
0x18001bedb  lea     rax, [rbp+var_20]
0x18001bedf  mov     [rbp+var_28], rax
0x18001bee3  mov     [rbp+arg_10], 0
0x18001beeb  mov     [rbp+var_40], 181Ch
0x18001bef2  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001bef9  mov     [rbp+var_38], rax
0x18001befd  mov     [rbp+var_30], 0
0x18001bf05  lea     r9, [rbp+arg_10]
0x18001bf09  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001bf10  lea     rdx, [rbp+var_28]
0x18001bf14  lea     rcx, [rbp+arg_0]
0x18001bf18  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001bf1d  mov     ecx, dword ptr [rbp+arg_0]
0x18001bf20  test    ecx, ecx
0x18001bf22  js      loc_18001BFF7
0x18001bf28  mov     rbx, [rbp+arg_10]
0x18001bf2c  mov     [rbp+arg_0], rbx
0x18001bf30  test    rbx, rbx
0x18001bf33  jz      loc_18001BFC5
0x18001bf39  mov     [rbp+arg_10], 0
0x18001bf41  mov     rax, [rbx]
0x18001bf44  lea     r8, [rbp+arg_10]
0x18001bf48  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001bf4f  mov     rcx, rbx
0x18001bf52  mov     rax, [rax]
0x18001bf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf5a  mov     rax, [rbp+arg_10]
0x18001bf5e  mov     [rbp+arg_10], rax
0x18001bf62  test    rax, rax
0x18001bf65  jz      short loc_18001BFC5
0x18001bf67  lea     rcx, [rbp+arg_10]
0x18001bf6b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bf70  lea     rax, qword_18002DA88
0x18001bf77  mov     [rbp+arg_10], rax
0x18001bf7b  lock inc cs:qword_18002DA88
0x18001bf83  xor     eax, eax
0x18001bf85  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001bf8e  jnz     short loc_18001BFA9
0x18001bf90  xor     ebx, ebx
0x18001bf92  mov     [rbp+arg_0], rbx
0x18001bf96  lea     rdx, stru_18002DA90; ListEntry
0x18001bf9d  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001bfa4  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001bfa9  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001bfb0  mov     rcx, rdi
0x18001bfb3  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001bfb8  mov     dil, al
0x18001bfbb  lock dec cs:qword_18002DA88
0x18001bfc3  jmp     short loc_18001BFD4
0x18001bfc5  lea     rdx, [rbp+arg_0]
0x18001bfc9  mov     rcx, rdi
0x18001bfcc  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001bfd1  mov     dil, al
0x18001bfd4  test    rbx, rbx
0x18001bfd7  jz      short loc_18001BFE2
0x18001bfd9  lea     rcx, [rbp+arg_0]
0x18001bfdd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bfe2  mov     al, dil
0x18001bfe5  lea     r11, [rsp+60h+var_s0]
0x18001bfea  mov     rbx, [r11+18h]
0x18001bfee  mov     rdi, [r11+28h]
0x18001bff2  mov     rsp, r11
0x18001bff5  pop     rbp
0x18001bff6  retn
0x18001bff7  lea     rdx, [rbp+var_40]
0x18001bffb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
