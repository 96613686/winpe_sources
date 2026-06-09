# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(void)

- ea: `0x180016ca0`
- end: `0x180016d69`
- name: `?First@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800176ec`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x180016ca0`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+28h] [rbp-18h] BYREF
  const char *v10; // [rsp+30h] [rbp-10h]
  __int64 v11; // [rsp+38h] [rbp-8h]
  __int64 v12; // [rsp+50h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF

  v13 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v12 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>>,
           &v12);
    v4 = v12;
  }
  else
  {
    v5 = 0;
    v12 = 0;
  }
  v9 = 21;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v11 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v9, a3);
  v9 = 23;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, &v13);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v9, v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  *a2 = v13;
  return a2;
}

```

## disassembly

```asm
0x180016ca0  mov     [rsp-8+arg_8], rbx
0x180016ca5  push    rbp
0x180016ca6  mov     rbp, rsp
0x180016ca9  sub     rsp, 40h
0x180016cad  mov     rbx, rdx
0x180016cb0  mov     [rbp+arg_10], 0
0x180016cb8  mov     rcx, [rcx]
0x180016cbb  test    rcx, rcx
0x180016cbe  jnz     short loc_180016CC8
0x180016cc0  xor     eax, eax
0x180016cc2  mov     [rbp+arg_0], rax
0x180016cc6  jmp     short loc_180016CEE
0x180016cc8  mov     [rbp+arg_0], 0
0x180016cd0  mov     rax, [rcx]
0x180016cd3  lea     r8, [rbp+arg_0]
0x180016cd7  lea     rdx, ??$guid_v@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>>
0x180016cde  mov     rax, [rax]
0x180016ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce6  mov     rcx, [rbp+arg_0]
0x180016cea  mov     [rbp+arg_0], rcx
0x180016cee  mov     [rbp+var_18], 15h
0x180016cf5  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016cfc  mov     [rbp+var_10], rdx
0x180016d00  mov     [rbp+var_8], 0
0x180016d08  test    eax, eax
0x180016d0a  js      short loc_180016D5D
0x180016d0c  mov     [rbp+var_18], 17h
0x180016d13  mov     [rbp+var_10], rdx
0x180016d17  mov     [rbp+var_8], 0
0x180016d1f  mov     rax, [rcx]
0x180016d22  lea     rdx, [rbp+arg_10]
0x180016d26  mov     rax, [rax+30h]
0x180016d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d2f  test    eax, eax
0x180016d31  js      short loc_180016D51
0x180016d33  lea     rcx, [rbp+arg_0]
0x180016d37  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016d3c  mov     rax, [rbp+arg_10]
0x180016d40  mov     [rbx], rax
0x180016d43  mov     rax, rbx
0x180016d46  mov     rbx, [rsp+40h+arg_8]
0x180016d4b  add     rsp, 40h
0x180016d4f  pop     rbp
0x180016d50  retn
0x180016d51  lea     rdx, [rbp+var_18]
0x180016d55  mov     ecx, eax
0x180016d57  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016d5d  lea     rdx, [rbp+var_18]
0x180016d61  mov     ecx, eax
0x180016d63  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
