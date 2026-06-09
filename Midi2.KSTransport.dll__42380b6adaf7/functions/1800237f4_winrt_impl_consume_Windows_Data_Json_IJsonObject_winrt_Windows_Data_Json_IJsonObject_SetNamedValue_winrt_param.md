# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)

- ea: `0x1800237f4`
- end: `0x180023840`
- name: `?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z`
- size: `76`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180021ff4`
- `0x180022e38`
- `0x180023534`
- `0x1800236b8`
- `0x180023ac0`

## callees

- `0x180015348`
- `0x1800237f4`
- `0x180041010`

## string_xrefs

- `0x1800237fb`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-28h] BYREF
  const char *v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-18h]

  v3 = *a1;
  v4 = *a3;
  v5 = *a2;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v6 = *v3;
  v8 = 189;
  v10 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v6 + 56))(v3, v5, v4);
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v8);
  return result;
}

```

## disassembly

```asm
0x1800237f4  sub     rsp, 48h
0x1800237f8  mov     rcx, [rcx]
0x1800237fb  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180023802  mov     r8, [r8]
0x180023805  mov     rdx, [rdx]
0x180023808  mov     [rsp+48h+var_20], rax
0x18002380d  mov     rax, [rcx]
0x180023810  mov     [rsp+48h+var_28], 0BDh
0x180023818  mov     [rsp+48h+var_18], 0
0x180023821  mov     rax, [rax+38h]
0x180023825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002382a  test    eax, eax
0x18002382c  js      short loc_180023833
0x18002382e  add     rsp, 48h
0x180023832  retn
0x180023833  lea     rdx, [rsp+48h+var_28]
0x180023838  mov     ecx, eax
0x18002383a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
