# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)

- ea: `0x18001d3d8`
- end: `0x18001d424`
- name: `?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001d184`
- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001d3d8`
- `0x180021010`

## string_xrefs

- `0x18001d3df`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
0x18001d3d8  sub     rsp, 48h
0x18001d3dc  mov     rcx, [rcx]
0x18001d3df  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d3e6  mov     r8, [r8]
0x18001d3e9  mov     rdx, [rdx]
0x18001d3ec  mov     [rsp+48h+var_20], rax
0x18001d3f1  mov     rax, [rcx]
0x18001d3f4  mov     [rsp+48h+var_28], 0BDh
0x18001d3fc  mov     [rsp+48h+var_18], 0
0x18001d405  mov     rax, [rax+38h]
0x18001d409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40e  test    eax, eax
0x18001d410  js      short loc_18001D417
0x18001d412  add     rsp, 48h
0x18001d416  retn
0x18001d417  lea     rdx, [rsp+48h+var_28]
0x18001d41c  mov     ecx, eax
0x18001d41e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
