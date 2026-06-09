# winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)

- ea: `0x1800071ac`
- end: `0x180007247`
- name: `?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z`
- size: `155`
- prototype: `const struct winrt::param::hstring *__fastcall(const struct winrt::param::hstring *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006920`

## callees

- `0x1800033c0`
- `0x1800071ac`
- `0x18000bde4`
- `0x18000d010`

## pseudocode

```c
const struct winrt::param::hstring *__fastcall winrt::Windows::Data::Json::JsonValue::CreateStringValue(
        const struct winrt::param::hstring *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // [rsp+28h] [rbp-20h] BYREF
  __int128 v6; // [rsp+30h] [rbp-18h]
  _QWORD *v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 *v8; // [rsp+60h] [rbp+18h]

  v7 = a2;
  v8 = &qword_180014788;
  _InterlockedIncrement64(&qword_180014788);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v7 = 0;
    v5 = 0;
    v6 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                               + 80LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           *a2,
           &v7);
    if ( v3 < 0 )
      winrt::throw_hresult((unsigned int)v3, &v5);
    *(_QWORD *)a1 = v7;
    _InterlockedDecrement64(&qword_180014788);
  }
  else
  {
    _InterlockedDecrement64(&qword_180014788);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_ca425077811c26dd994b3d0531fe1de0_ &>(
      0,
      a1,
      &v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800071ac  mov     r11, rsp
0x1800071af  push    rbx
0x1800071b0  sub     rsp, 40h
0x1800071b4  mov     rbx, rcx
0x1800071b7  mov     [r11+10h], rdx
0x1800071bb  lea     rax, qword_180014788
0x1800071c2  mov     [r11+18h], rax
0x1800071c6  lock inc cs:qword_180014788
0x1800071ce  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800071d5  test    rcx, rcx
0x1800071d8  jz      short loc_18000721C
0x1800071da  mov     qword ptr [r11+10h], 0
0x1800071e2  mov     [rsp+48h+var_20], 0
0x1800071ea  xorps   xmm0, xmm0
0x1800071ed  movdqu  [rsp+48h+var_18], xmm0
0x1800071f3  mov     rax, [rcx]
0x1800071f6  lea     r8, [r11+10h]
0x1800071fa  mov     rdx, [rdx]
0x1800071fd  mov     rax, [rax+50h]
0x180007201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007206  test    eax, eax
0x180007208  js      short loc_18000723A
0x18000720a  mov     rax, [rsp+48h+arg_8]
0x18000720f  mov     [rbx], rax
0x180007212  lock dec cs:qword_180014788
0x18000721a  jmp     short loc_180007231
0x18000721c  lock dec cs:qword_180014788
0x180007224  lea     r8, [rsp+48h+arg_8]
0x180007229  mov     rdx, rbx
0x18000722c  call    ??$call@AEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@Z
0x180007231  mov     rax, rbx
0x180007234  add     rsp, 40h
0x180007238  pop     rbx
0x180007239  retn
0x18000723a  lea     rdx, [rsp+48h+var_20]
0x18000723f  mov     ecx, eax
0x180007241  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
