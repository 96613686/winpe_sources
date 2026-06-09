# winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)

- ea: `0x180016ab4`
- end: `0x180016b59`
- name: `?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z`
- size: `165`
- prototype: `__int64 __fastcall(const struct winrt::param::hstring *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018264`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014fec`
- `0x180016ab4`
- `0x180032010`

## string_xrefs

- `0x180016af2`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct winrt::param::hstring *__fastcall winrt::Windows::Data::Json::JsonValue::CreateStringValue(
        const struct winrt::param::hstring *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // [rsp+28h] [rbp-20h] BYREF
  const char *v6; // [rsp+30h] [rbp-18h]
  __int64 v7; // [rsp+38h] [rbp-10h]
  _QWORD *v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+18h]

  v8 = a2;
  v9 = &qword_18005FAC8;
  _InterlockedIncrement64(&qword_18005FAC8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v8 = 0;
    v5 = 638;
    v6 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v7 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                               + 80LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           *a2,
           &v8);
    if ( v3 < 0 )
      winrt::throw_hresult((unsigned int)v3, &v5);
    *(_QWORD *)a1 = v8;
    _InterlockedDecrement64(&qword_18005FAC8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18005FAC8);
    ___call_AEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateStringValue_JsonValue_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
      0,
      a1,
      &v8);
  }
  return a1;
}

```

## disassembly

```asm
0x180016ab4  mov     r11, rsp
0x180016ab7  push    rbx
0x180016ab8  sub     rsp, 40h
0x180016abc  mov     rbx, rcx
0x180016abf  mov     [r11+10h], rdx
0x180016ac3  lea     rax, qword_18005FAC8
0x180016aca  mov     [r11+18h], rax
0x180016ace  lock inc cs:qword_18005FAC8
0x180016ad6  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180016add  test    rcx, rcx
0x180016ae0  jz      short loc_180016B2E
0x180016ae2  mov     qword ptr [r11+10h], 0
0x180016aea  mov     [rsp+48h+var_20], 27Eh
0x180016af2  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016af9  mov     [r11-18h], rax
0x180016afd  mov     qword ptr [r11-10h], 0
0x180016b05  mov     rax, [rcx]
0x180016b08  lea     r8, [r11+10h]
0x180016b0c  mov     rdx, [rdx]
0x180016b0f  mov     rax, [rax+50h]
0x180016b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b18  test    eax, eax
0x180016b1a  js      short loc_180016B4C
0x180016b1c  mov     rax, [rsp+48h+arg_8]
0x180016b21  mov     [rbx], rax
0x180016b24  lock dec cs:qword_18005FAC8
0x180016b2c  jmp     short loc_180016B43
0x180016b2e  lock dec cs:qword_18005FAC8
0x180016b36  lea     r8, [rsp+48h+arg_8]
0x180016b3b  mov     rdx, rbx
0x180016b3e  call    ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x180016b43  mov     rax, rbx
0x180016b46  add     rsp, 40h
0x180016b4a  pop     rbx
0x180016b4b  retn
0x180016b4c  lea     rdx, [rsp+48h+var_20]
0x180016b51  mov     ecx, eax
0x180016b53  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
