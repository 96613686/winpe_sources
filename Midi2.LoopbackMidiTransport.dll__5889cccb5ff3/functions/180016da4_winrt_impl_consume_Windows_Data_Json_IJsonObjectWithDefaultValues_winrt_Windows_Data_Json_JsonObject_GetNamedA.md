# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)

- ea: `0x180016da4`
- end: `0x180016e76`
- name: `?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x180016da4`
- `0x180032010`

## string_xrefs

- `0x180016dfe`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v11; // [rsp+38h] [rbp-30h] BYREF
  int v12; // [rsp+40h] [rbp-28h] BYREF
  const char *v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+90h] [rbp+28h] BYREF

  v11 = 0;
  v7 = *a1;
  if ( v7 )
  {
    v15 = 0;
    v8 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v7)(
           v7,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>,
           &v15);
    v7 = v15;
  }
  else
  {
    v8 = 0;
    v15 = 0;
  }
  v12 = 379;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v12);
  v12 = 381;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, *a3, *a4, &v11);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v12);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x180016da4  push    rbp
0x180016da6  push    rbx
0x180016da7  push    rsi
0x180016da8  push    rdi
0x180016da9  mov     rbp, rsp
0x180016dac  sub     rsp, 68h
0x180016db0  mov     rdi, r9
0x180016db3  mov     rsi, r8
0x180016db6  mov     rbx, rdx
0x180016db9  mov     [rbp+var_30], 0
0x180016dc1  mov     rcx, [rcx]
0x180016dc4  test    rcx, rcx
0x180016dc7  jnz     short loc_180016DD1
0x180016dc9  xor     eax, eax
0x180016dcb  mov     [rbp+arg_0], rax
0x180016dcf  jmp     short loc_180016DF7
0x180016dd1  mov     [rbp+arg_0], 0
0x180016dd9  mov     rax, [rcx]
0x180016ddc  lea     r8, [rbp+arg_0]
0x180016de0  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x180016de7  mov     rax, [rax]
0x180016dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016def  mov     rcx, [rbp+arg_0]
0x180016df3  mov     [rbp+arg_0], rcx
0x180016df7  mov     [rbp+var_28], 17Bh
0x180016dfe  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016e05  mov     [rbp+var_20], rdx
0x180016e09  mov     [rbp+var_18], 0
0x180016e11  test    eax, eax
0x180016e13  js      short loc_180016E6A
0x180016e15  mov     [rbp+var_28], 17Dh
0x180016e1c  mov     [rbp+var_20], rdx
0x180016e20  mov     [rbp+var_18], 0
0x180016e28  mov     rax, [rcx]
0x180016e2b  lea     r9, [rbp+var_30]
0x180016e2f  mov     r8, [rdi]
0x180016e32  mov     rdx, [rsi]
0x180016e35  mov     rax, [rax+48h]
0x180016e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e3e  test    eax, eax
0x180016e40  js      short loc_180016E5E
0x180016e42  lea     rcx, [rbp+arg_0]
0x180016e46  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016e4b  mov     rax, [rbp+var_30]
0x180016e4f  mov     [rbx], rax
0x180016e52  mov     rax, rbx
0x180016e55  add     rsp, 68h
0x180016e59  pop     rdi
0x180016e5a  pop     rsi
0x180016e5b  pop     rbx
0x180016e5c  pop     rbp
0x180016e5d  retn
0x180016e5e  lea     rdx, [rbp+var_28]
0x180016e62  mov     ecx, eax
0x180016e64  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016e6a  lea     rdx, [rbp+var_28]
0x180016e6e  mov     ecx, eax
0x180016e70  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
