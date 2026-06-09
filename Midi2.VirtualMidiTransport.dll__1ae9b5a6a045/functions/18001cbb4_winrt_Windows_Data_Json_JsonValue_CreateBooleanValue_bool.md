# winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)

- ea: `0x18001cbb4`
- end: `0x18001cc67`
- name: `?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z`
- size: `179`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001bb50`
- `0x18001cbb4`
- `0x180021010`

## string_xrefs

- `0x18001cbfe`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
  v10 = &qword_18002DAA8;
  _InterlockedIncrement64(&qword_18002DAA8);
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
    _InterlockedDecrement64(&qword_18002DAA8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002DAA8);
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
0x18001cbb4  mov     [rsp-8+arg_0], rbx
0x18001cbb9  mov     [rsp-8+arg_8], dl
0x18001cbbd  push    rbp
0x18001cbbe  mov     rbp, rsp
0x18001cbc1  sub     rsp, 40h
0x18001cbc5  mov     rbx, rcx
0x18001cbc8  lea     rax, [rbp+arg_8]
0x18001cbcc  mov     [rbp+arg_10], rax
0x18001cbd0  lea     rax, qword_18002DAA8
0x18001cbd7  mov     [rbp+arg_18], rax
0x18001cbdb  lock inc cs:qword_18002DAA8
0x18001cbe3  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18001cbea  test    rcx, rcx
0x18001cbed  jz      short loc_18001CC39
0x18001cbef  mov     [rbp+arg_10], 0
0x18001cbf7  mov     [rbp+var_18], 25Ah
0x18001cbfe  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001cc05  mov     [rbp+var_10], rax
0x18001cc09  mov     [rbp+var_8], 0
0x18001cc11  mov     rax, [rcx]
0x18001cc14  lea     r8, [rbp+arg_10]
0x18001cc18  mov     dl, [rbp+arg_8]
0x18001cc1b  mov     rax, [rax+40h]
0x18001cc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc24  test    eax, eax
0x18001cc26  js      short loc_18001CC5B
0x18001cc28  mov     rax, [rbp+arg_10]
0x18001cc2c  mov     [rbx], rax
0x18001cc2f  lock dec cs:qword_18002DAA8
0x18001cc37  jmp     short loc_18001CC4D
0x18001cc39  lock dec cs:qword_18002DAA8
0x18001cc41  lea     r8, [rbp+arg_10]
0x18001cc45  mov     rdx, rbx
0x18001cc48  call    ??$call@AEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateBooleanValue@JsonValue@Json@Data@Windows@2@SA@_N@Z@@Z
0x18001cc4d  mov     rax, rbx
0x18001cc50  mov     rbx, [rsp+40h+arg_0]
0x18001cc55  add     rsp, 40h
0x18001cc59  pop     rbp
0x18001cc5a  retn
0x18001cc5b  lea     rdx, [rbp+var_18]
0x18001cc5f  mov     ecx, eax
0x18001cc61  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
