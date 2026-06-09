# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)

- ea: `0x180022478`
- end: `0x18002254a`
- name: `?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z`
- size: `210`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800228d0`
- `0x18002af94`
- `0x18002c4a4`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x180022478`
- `0x180041010`

## string_xrefs

- `0x1800224d2`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
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
  v12 = 361;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v12);
  v12 = 363;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v7 + 64LL))(v7, *a3, *a4, &v11);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v12);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x180022478  push    rbp
0x18002247a  push    rbx
0x18002247b  push    rsi
0x18002247c  push    rdi
0x18002247d  mov     rbp, rsp
0x180022480  sub     rsp, 68h
0x180022484  mov     rdi, r9
0x180022487  mov     rsi, r8
0x18002248a  mov     rbx, rdx
0x18002248d  mov     [rbp+var_30], 0
0x180022495  mov     rcx, [rcx]
0x180022498  test    rcx, rcx
0x18002249b  jnz     short loc_1800224A5
0x18002249d  xor     eax, eax
0x18002249f  mov     [rbp+arg_0], rax
0x1800224a3  jmp     short loc_1800224CB
0x1800224a5  mov     [rbp+arg_0], 0
0x1800224ad  mov     rax, [rcx]
0x1800224b0  lea     r8, [rbp+arg_0]
0x1800224b4  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x1800224bb  mov     rax, [rax]
0x1800224be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224c3  mov     rcx, [rbp+arg_0]
0x1800224c7  mov     [rbp+arg_0], rcx
0x1800224cb  mov     [rbp+var_28], 169h
0x1800224d2  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800224d9  mov     [rbp+var_20], rdx
0x1800224dd  mov     [rbp+var_18], 0
0x1800224e5  test    eax, eax
0x1800224e7  js      short loc_18002253E
0x1800224e9  mov     [rbp+var_28], 16Bh
0x1800224f0  mov     [rbp+var_20], rdx
0x1800224f4  mov     [rbp+var_18], 0
0x1800224fc  mov     rax, [rcx]
0x1800224ff  lea     r9, [rbp+var_30]
0x180022503  mov     r8, [rdi]
0x180022506  mov     rdx, [rsi]
0x180022509  mov     rax, [rax+40h]
0x18002250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022512  test    eax, eax
0x180022514  js      short loc_180022532
0x180022516  lea     rcx, [rbp+arg_0]
0x18002251a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002251f  mov     rax, [rbp+var_30]
0x180022523  mov     [rbx], rax
0x180022526  mov     rax, rbx
0x180022529  add     rsp, 68h
0x18002252d  pop     rdi
0x18002252e  pop     rsi
0x18002252f  pop     rbx
0x180022530  pop     rbp
0x180022531  retn
0x180022532  lea     rdx, [rbp+var_28]
0x180022536  mov     ecx, eax
0x180022538  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002253e  lea     rdx, [rbp+var_28]
0x180022542  mov     ecx, eax
0x180022544  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
