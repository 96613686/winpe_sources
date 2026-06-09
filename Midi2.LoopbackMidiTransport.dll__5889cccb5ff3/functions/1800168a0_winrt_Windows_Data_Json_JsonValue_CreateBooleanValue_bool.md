# winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)

- ea: `0x1800168a0`
- end: `0x180016953`
- name: `?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z`
- size: `179`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800167c4`
- `0x180017c54`
- `0x180018090`
- `0x180018264`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014e40`
- `0x1800168a0`
- `0x180032010`

## string_xrefs

- `0x1800168ea`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
  v10 = &qword_18005FAC8;
  _InterlockedIncrement64(&qword_18005FAC8);
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
    _InterlockedDecrement64(&qword_18005FAC8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18005FAC8);
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
0x1800168a0  mov     [rsp-8+arg_0], rbx
0x1800168a5  mov     [rsp-8+arg_8], dl
0x1800168a9  push    rbp
0x1800168aa  mov     rbp, rsp
0x1800168ad  sub     rsp, 40h
0x1800168b1  mov     rbx, rcx
0x1800168b4  lea     rax, [rbp+arg_8]
0x1800168b8  mov     [rbp+arg_10], rax
0x1800168bc  lea     rax, qword_18005FAC8
0x1800168c3  mov     [rbp+arg_18], rax
0x1800168c7  lock inc cs:qword_18005FAC8
0x1800168cf  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800168d6  test    rcx, rcx
0x1800168d9  jz      short loc_180016925
0x1800168db  mov     [rbp+arg_10], 0
0x1800168e3  mov     [rbp+var_18], 25Ah
0x1800168ea  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800168f1  mov     [rbp+var_10], rax
0x1800168f5  mov     [rbp+var_8], 0
0x1800168fd  mov     rax, [rcx]
0x180016900  lea     r8, [rbp+arg_10]
0x180016904  mov     dl, [rbp+arg_8]
0x180016907  mov     rax, [rax+40h]
0x18001690b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016910  test    eax, eax
0x180016912  js      short loc_180016947
0x180016914  mov     rax, [rbp+arg_10]
0x180016918  mov     [rbx], rax
0x18001691b  lock dec cs:qword_18005FAC8
0x180016923  jmp     short loc_180016939
0x180016925  lock dec cs:qword_18005FAC8
0x18001692d  lea     r8, [rbp+arg_10]
0x180016931  mov     rdx, rbx
0x180016934  call    ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z
0x180016939  mov     rax, rbx
0x18001693c  mov     rbx, [rsp+40h+arg_0]
0x180016941  add     rsp, 40h
0x180016945  pop     rbp
0x180016946  retn
0x180016947  lea     rdx, [rbp+var_18]
0x18001694b  mov     ecx, eax
0x18001694d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
