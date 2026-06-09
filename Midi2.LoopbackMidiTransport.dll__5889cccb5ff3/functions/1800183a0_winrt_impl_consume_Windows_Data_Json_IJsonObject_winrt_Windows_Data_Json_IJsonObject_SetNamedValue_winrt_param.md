# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)

- ea: `0x1800183a0`
- end: `0x1800183ec`
- name: `?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800167c4`
- `0x180017c54`
- `0x180018090`
- `0x180018264`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x1800183a0`
- `0x180032010`

## string_xrefs

- `0x1800183a7`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
0x1800183a0  sub     rsp, 48h
0x1800183a4  mov     rcx, [rcx]
0x1800183a7  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800183ae  mov     r8, [r8]
0x1800183b1  mov     rdx, [rdx]
0x1800183b4  mov     [rsp+48h+var_20], rax
0x1800183b9  mov     rax, [rcx]
0x1800183bc  mov     [rsp+48h+var_28], 0BDh
0x1800183c4  mov     [rsp+48h+var_18], 0
0x1800183cd  mov     rax, [rax+38h]
0x1800183d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d6  test    eax, eax
0x1800183d8  js      short loc_1800183DF
0x1800183da  add     rsp, 48h
0x1800183de  retn
0x1800183df  lea     rdx, [rsp+48h+var_28]
0x1800183e4  mov     ecx, eax
0x1800183e6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
