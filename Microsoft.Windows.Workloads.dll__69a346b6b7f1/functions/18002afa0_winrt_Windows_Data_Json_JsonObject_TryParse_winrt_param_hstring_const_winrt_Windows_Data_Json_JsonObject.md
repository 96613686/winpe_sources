# winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x18002afa0`
- end: `0x18002b002`
- name: `?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z`
- size: `98`
- prototype: `__int64 __fastcall(const struct winrt::param::hstring *, struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x18002ad40`
- `0x18002ade0`
- `0x18002afa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Data::Json::JsonObject::TryParse(
        const struct winrt::param::hstring *a1,
        struct winrt::Windows::Data::Json::JsonObject *a2)
{
  __int64 result; // rax
  _QWORD v3[3]; // [rsp+20h] [rbp-18h] BYREF

  v3[0] = a1;
  v3[1] = a2;
  _InterlockedIncrement64(&qword_180059F98);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    result = _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(
               v3,
               &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180059F98);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059F98);
    return winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_216e461b0f2bafa6414b8faed9d5cbb6_ &>(
             (__int64)a1,
             v3);
  }
  return result;
}

```

## disassembly

```asm
0x18002afa0  sub     rsp, 38h
0x18002afa4  mov     [rsp+38h+var_18], rcx
0x18002afa9  mov     [rsp+38h+var_10], rdx
0x18002afae  lea     rax, qword_180059F98
0x18002afb5  mov     [rsp+38h+arg_0], rax
0x18002afba  lock inc cs:qword_180059F98
0x18002afc2  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18002afca  jz      short loc_18002AFEB
0x18002afcc  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18002afd3  lea     rcx, [rsp+38h+var_18]
0x18002afd8  call    ??R_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18002afdd  nop
0x18002afde  lock dec cs:qword_180059F98
0x18002afe6  add     rsp, 38h
0x18002afea  retn
0x18002afeb  lock dec cs:qword_180059F98
0x18002aff3  lea     rdx, [rsp+38h+var_18]
0x18002aff8  call    ??$call@AEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@Z
0x18002affd  add     rsp, 38h
0x18002b001  retn
```
