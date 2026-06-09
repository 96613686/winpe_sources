# winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)

- ea: `0x18002213c`
- end: `0x1800221e1`
- name: `?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z`
- size: `165`
- prototype: `__int64 __fastcall(const struct winrt::param::hstring *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800236b8`

## callees

- `0x180015348`
- `0x180020d60`
- `0x18002213c`
- `0x180041010`

## string_xrefs

- `0x18002217a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
  v9 = &qword_180071CE8;
  _InterlockedIncrement64(&qword_180071CE8);
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
    _InterlockedDecrement64(&qword_180071CE8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180071CE8);
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
0x18002213c  mov     r11, rsp
0x18002213f  push    rbx
0x180022140  sub     rsp, 40h
0x180022144  mov     rbx, rcx
0x180022147  mov     [r11+10h], rdx
0x18002214b  lea     rax, qword_180071CE8
0x180022152  mov     [r11+18h], rax
0x180022156  lock inc cs:qword_180071CE8
0x18002215e  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180022165  test    rcx, rcx
0x180022168  jz      short loc_1800221B6
0x18002216a  mov     qword ptr [r11+10h], 0
0x180022172  mov     [rsp+48h+var_20], 27Eh
0x18002217a  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022181  mov     [r11-18h], rax
0x180022185  mov     qword ptr [r11-10h], 0
0x18002218d  mov     rax, [rcx]
0x180022190  lea     r8, [r11+10h]
0x180022194  mov     rdx, [rdx]
0x180022197  mov     rax, [rax+50h]
0x18002219b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221a0  test    eax, eax
0x1800221a2  js      short loc_1800221D4
0x1800221a4  mov     rax, [rsp+48h+arg_8]
0x1800221a9  mov     [rbx], rax
0x1800221ac  lock dec cs:qword_180071CE8
0x1800221b4  jmp     short loc_1800221CB
0x1800221b6  lock dec cs:qword_180071CE8
0x1800221be  lea     r8, [rsp+48h+arg_8]
0x1800221c3  mov     rdx, rbx
0x1800221c6  call    ??$call@AEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateStringValue@JsonValue@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x1800221cb  mov     rax, rbx
0x1800221ce  add     rsp, 40h
0x1800221d2  pop     rbx
0x1800221d3  retn
0x1800221d4  lea     rdx, [rsp+48h+var_20]
0x1800221d9  mov     ecx, eax
0x1800221db  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
