# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)

- ea: `0x18002ba50`
- end: `0x18002bb19`
- name: `?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002af94`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x18002ba50`
- `0x180041010`

## string_xrefs

- `0x18002baa6`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+30h] [rbp-20h] BYREF
  const char *v8; // [rsp+38h] [rbp-18h]
  __int64 v9; // [rsp+40h] [rbp-10h]
  __int64 v10; // [rsp+60h] [rbp+10h] BYREF
  char v11; // [rsp+70h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 415;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 417;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v3 + 88LL))(v3, *a2, 0, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  return v11;
}

```

## disassembly

```asm
0x18002ba50  mov     [rsp-8+arg_8], rbx
0x18002ba55  mov     [rsp-8+arg_10], r8b
0x18002ba5a  push    rbp
0x18002ba5b  mov     rbp, rsp
0x18002ba5e  sub     rsp, 50h
0x18002ba62  mov     rbx, rdx
0x18002ba65  mov     [rbp+arg_10], 0
0x18002ba69  mov     rcx, [rcx]
0x18002ba6c  test    rcx, rcx
0x18002ba6f  jnz     short loc_18002BA79
0x18002ba71  xor     eax, eax
0x18002ba73  mov     [rbp+arg_0], rax
0x18002ba77  jmp     short loc_18002BA9F
0x18002ba79  mov     [rbp+arg_0], 0
0x18002ba81  mov     rax, [rcx]
0x18002ba84  lea     r8, [rbp+arg_0]
0x18002ba88  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18002ba8f  mov     rax, [rax]
0x18002ba92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba97  mov     rcx, [rbp+arg_0]
0x18002ba9b  mov     [rbp+arg_0], rcx
0x18002ba9f  mov     [rbp+var_20], 19Fh
0x18002baa6  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002baad  mov     [rbp+var_18], rdx
0x18002bab1  mov     [rbp+var_10], 0
0x18002bab9  test    eax, eax
0x18002babb  js      short loc_18002BB0D
0x18002babd  mov     [rbp+var_20], 1A1h
0x18002bac4  mov     [rbp+var_18], rdx
0x18002bac8  mov     [rbp+var_10], 0
0x18002bad0  mov     rax, [rcx]
0x18002bad3  lea     r9, [rbp+arg_10]
0x18002bad7  xor     r8d, r8d
0x18002bada  mov     rdx, [rbx]
0x18002badd  mov     rax, [rax+58h]
0x18002bae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae6  test    eax, eax
0x18002bae8  js      short loc_18002BB01
0x18002baea  lea     rcx, [rbp+arg_0]
0x18002baee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002baf3  mov     al, [rbp+arg_10]
0x18002baf6  mov     rbx, [rsp+50h+arg_8]
0x18002bafb  add     rsp, 50h
0x18002baff  pop     rbp
0x18002bb00  retn
0x18002bb01  lea     rdx, [rbp+var_20]
0x18002bb05  mov     ecx, eax
0x18002bb07  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bb0d  lea     rdx, [rbp+var_20]
0x18002bb11  mov     ecx, eax
0x18002bb13  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
