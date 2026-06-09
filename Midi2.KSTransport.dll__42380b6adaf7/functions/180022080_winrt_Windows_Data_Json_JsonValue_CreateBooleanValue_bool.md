# winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)

- ea: `0x180022080`
- end: `0x180022133`
- name: `?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z`
- size: `179`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180021ff4`
- `0x180022e38`
- `0x180023534`
- `0x1800236b8`
- `0x180023ac0`

## callees

- `0x180015348`
- `0x180020bb4`
- `0x180022080`
- `0x180041010`

## string_xrefs

- `0x1800220ca`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char **__fastcall winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(char **a1, __int64 a2)
{
  int v3; // eax
  int v5; // [rsp+28h] [rbp-18h] BYREF
  const char *v6; // [rsp+30h] [rbp-10h]
  __int64 v7; // [rsp+38h] [rbp-8h]
  char v8; // [rsp+58h] [rbp+18h] BYREF
  char *v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+68h] [rbp+28h]

  v8 = a2;
  v9 = &v8;
  v10 = &qword_180071CE8;
  _InterlockedIncrement64(&qword_180071CE8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v9 = 0;
    v5 = 602;
    v6 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
    v7 = 0;
    LOBYTE(a2) = v8;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, char **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 64LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           a2,
           &v9);
    if ( v3 < 0 )
      winrt::throw_hresult((unsigned int)v3, &v5);
    *a1 = v9;
    _InterlockedDecrement64(&qword_180071CE8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180071CE8);
    ___call_AEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_winrt__SA__N_Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_2_SA__N_Z__Z(
      0,
      a1,
      &v9);
  }
  return a1;
}

```

## disassembly

```asm
0x180022080  mov     [rsp-8+arg_0], rbx
0x180022085  mov     [rsp-8+arg_8], dl
0x180022089  push    rbp
0x18002208a  mov     rbp, rsp
0x18002208d  sub     rsp, 40h
0x180022091  mov     rbx, rcx
0x180022094  lea     rax, [rbp+arg_8]
0x180022098  mov     [rbp+arg_10], rax
0x18002209c  lea     rax, qword_180071CE8
0x1800220a3  mov     [rbp+arg_18], rax
0x1800220a7  lock inc cs:qword_180071CE8
0x1800220af  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800220b6  test    rcx, rcx
0x1800220b9  jz      short loc_180022105
0x1800220bb  mov     [rbp+arg_10], 0
0x1800220c3  mov     [rbp+var_18], 25Ah
0x1800220ca  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800220d1  mov     [rbp+var_10], rax
0x1800220d5  mov     [rbp+var_8], 0
0x1800220dd  mov     rax, [rcx]
0x1800220e0  lea     r8, [rbp+arg_10]
0x1800220e4  mov     dl, [rbp+arg_8]
0x1800220e7  mov     rax, [rax+40h]
0x1800220eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220f0  test    eax, eax
0x1800220f2  js      short loc_180022127
0x1800220f4  mov     rax, [rbp+arg_10]
0x1800220f8  mov     [rbx], rax
0x1800220fb  lock dec cs:qword_180071CE8
0x180022103  jmp     short loc_180022119
0x180022105  lock dec cs:qword_180071CE8
0x18002210d  lea     r8, [rbp+arg_10]
0x180022111  mov     rdx, rbx
0x180022114  call    ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z
0x180022119  mov     rax, rbx
0x18002211c  mov     rbx, [rsp+40h+arg_0]
0x180022121  add     rsp, 40h
0x180022125  pop     rbp
0x180022126  retn
0x180022127  lea     rdx, [rbp+var_18]
0x18002212b  mov     ecx, eax
0x18002212d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
