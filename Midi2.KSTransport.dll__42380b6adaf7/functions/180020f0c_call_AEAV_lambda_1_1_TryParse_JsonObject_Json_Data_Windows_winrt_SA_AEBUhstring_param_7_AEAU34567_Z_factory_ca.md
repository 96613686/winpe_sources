# ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z

- ea: `0x180020f0c`
- end: `0x180021065`
- name: `??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023ac0`

## callees

- `0x1800054a9`
- `0x18000d1c0`
- `0x18000fb5c`
- `0x180015348`
- `0x180020f0c`
- `0x180021f58`
- `0x180041010`

## string_xrefs

- `0x180020f34`: `Windows.Data.Json.JsonObject`

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
    v13 = &qword_180071CC8;
    _InterlockedIncrement64(&qword_180071CC8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            (signed __int64)v3,
            0) )
    {
      v3 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180071CD0);
    }
    v4 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180071CC8);
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
0x180020f0c  mov     [rsp-8+arg_8], rbx
0x180020f11  mov     [rsp-8+arg_18], rdi
0x180020f16  mov     [rsp-8+arg_0], rcx
0x180020f1b  push    rbp
0x180020f1c  mov     rbp, rsp
0x180020f1f  sub     rsp, 60h
0x180020f23  mov     rdi, rdx
0x180020f26  mov     [rbp+var_20], 1
0x180020f2d  mov     [rbp+var_1C], 1Ch
0x180020f34  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x180020f3b  mov     [rbp+var_10], rax
0x180020f3f  lea     rax, [rbp+var_20]
0x180020f43  mov     [rbp+var_28], rax
0x180020f47  mov     [rbp+arg_10], 0
0x180020f4f  mov     [rbp+var_40], 181Ch
0x180020f56  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180020f5d  mov     [rbp+var_38], rax
0x180020f61  mov     [rbp+var_30], 0
0x180020f69  lea     r9, [rbp+arg_10]
0x180020f6d  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x180020f74  lea     rdx, [rbp+var_28]
0x180020f78  lea     rcx, [rbp+arg_0]
0x180020f7c  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180020f81  mov     ecx, dword ptr [rbp+arg_0]
0x180020f84  test    ecx, ecx
0x180020f86  js      loc_18002105B
0x180020f8c  mov     rbx, [rbp+arg_10]
0x180020f90  mov     [rbp+arg_0], rbx
0x180020f94  test    rbx, rbx
0x180020f97  jz      loc_180021029
0x180020f9d  mov     [rbp+arg_10], 0
0x180020fa5  mov     rax, [rbx]
0x180020fa8  lea     r8, [rbp+arg_10]
0x180020fac  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180020fb3  mov     rcx, rbx
0x180020fb6  mov     rax, [rax]
0x180020fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fbe  mov     rax, [rbp+arg_10]
0x180020fc2  mov     [rbp+arg_10], rax
0x180020fc6  test    rax, rax
0x180020fc9  jz      short loc_180021029
0x180020fcb  lea     rcx, [rbp+arg_10]
0x180020fcf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020fd4  lea     rax, qword_180071CC8
0x180020fdb  mov     [rbp+arg_10], rax
0x180020fdf  lock inc cs:qword_180071CC8
0x180020fe7  xor     eax, eax
0x180020fe9  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180020ff2  jnz     short loc_18002100D
0x180020ff4  xor     ebx, ebx
0x180020ff6  mov     [rbp+arg_0], rbx
0x180020ffa  lea     rdx, stru_180071CD0; ListEntry
0x180021001  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180021008  call    WINRT_IMPL_InterlockedPushEntrySList
0x18002100d  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180021014  mov     rcx, rdi
0x180021017  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18002101c  mov     dil, al
0x18002101f  lock dec cs:qword_180071CC8
0x180021027  jmp     short loc_180021038
0x180021029  lea     rdx, [rbp+arg_0]
0x18002102d  mov     rcx, rdi
0x180021030  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x180021035  mov     dil, al
0x180021038  test    rbx, rbx
0x18002103b  jz      short loc_180021046
0x18002103d  lea     rcx, [rbp+arg_0]
0x180021041  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021046  mov     al, dil
0x180021049  lea     r11, [rsp+60h+var_s0]
0x18002104e  mov     rbx, [r11+18h]
0x180021052  mov     rdi, [r11+28h]
0x180021056  mov     rsp, r11
0x180021059  pop     rbp
0x18002105a  retn
0x18002105b  lea     rdx, [rbp+var_40]
0x18002105f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
