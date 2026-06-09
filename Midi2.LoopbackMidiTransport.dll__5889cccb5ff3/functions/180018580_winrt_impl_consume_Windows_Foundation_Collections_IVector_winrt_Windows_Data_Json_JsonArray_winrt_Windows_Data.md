# winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)

- ea: `0x180018580`
- end: `0x180018635`
- name: `?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x180018580`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rcx
  signed int v4; // eax
  signed int v5; // eax
  __int64 v6; // r8
  unsigned int v8; // [rsp+20h] [rbp-20h] BYREF
  const char *v9; // [rsp+28h] [rbp-18h]
  __int64 v10; // [rsp+30h] [rbp-10h]
  unsigned int v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+58h] [rbp+18h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v12 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
           &v12);
    v3 = v12;
  }
  else
  {
    v4 = 0;
    v12 = 0;
  }
  v8 = 577;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v10 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v8, a3);
  v8 = 579;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v10 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 56LL))(v3, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v8, v6);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return v11;
}

```

## disassembly

```asm
0x180018580  push    rbp
0x180018582  mov     rbp, rsp
0x180018585  sub     rsp, 40h
0x180018589  mov     [rbp+arg_0], 0
0x180018590  mov     rcx, [rcx]
0x180018593  test    rcx, rcx
0x180018596  jnz     short loc_1800185A0
0x180018598  xor     eax, eax
0x18001859a  mov     [rbp+arg_8], rax
0x18001859e  jmp     short loc_1800185C6
0x1800185a0  mov     [rbp+arg_8], 0
0x1800185a8  mov     rax, [rcx]
0x1800185ab  lea     r8, [rbp+arg_8]
0x1800185af  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x1800185b6  mov     rax, [rax]
0x1800185b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185be  mov     rcx, [rbp+arg_8]
0x1800185c2  mov     [rbp+arg_8], rcx
0x1800185c6  mov     [rbp+var_20], 241h
0x1800185cd  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800185d4  mov     [rbp+var_18], rdx
0x1800185d8  mov     [rbp+var_10], 0
0x1800185e0  test    eax, eax
0x1800185e2  js      short loc_180018629
0x1800185e4  mov     [rbp+var_20], 243h
0x1800185eb  mov     [rbp+var_18], rdx
0x1800185ef  mov     [rbp+var_10], 0
0x1800185f7  mov     rax, [rcx]
0x1800185fa  lea     rdx, [rbp+arg_0]
0x1800185fe  mov     rax, [rax+38h]
0x180018602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018607  test    eax, eax
0x180018609  js      short loc_18001861D
0x18001860b  lea     rcx, [rbp+arg_8]
0x18001860f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018614  mov     eax, [rbp+arg_0]
0x180018617  add     rsp, 40h
0x18001861b  pop     rbp
0x18001861c  retn
0x18001861d  lea     rdx, [rbp+var_20]
0x180018621  mov     ecx, eax
0x180018623  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018629  lea     rdx, [rbp+var_20]
0x18001862d  mov     ecx, eax
0x18001862f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
