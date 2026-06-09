# winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Size(void)

- ea: `0x1800184c4`
- end: `0x180018579`
- name: `?Size@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
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
- `0x1800184c4`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Size(
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
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
           &v12);
    v3 = v12;
  }
  else
  {
    v4 = 0;
    v12 = 0;
  }
  v8 = 271;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v10 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v8, a3);
  v8 = 273;
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
0x1800184c4  push    rbp
0x1800184c6  mov     rbp, rsp
0x1800184c9  sub     rsp, 40h
0x1800184cd  mov     [rbp+arg_0], 0
0x1800184d4  mov     rcx, [rcx]
0x1800184d7  test    rcx, rcx
0x1800184da  jnz     short loc_1800184E4
0x1800184dc  xor     eax, eax
0x1800184de  mov     [rbp+arg_8], rax
0x1800184e2  jmp     short loc_18001850A
0x1800184e4  mov     [rbp+arg_8], 0
0x1800184ec  mov     rax, [rcx]
0x1800184ef  lea     r8, [rbp+arg_8]
0x1800184f3  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>
0x1800184fa  mov     rax, [rax]
0x1800184fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018502  mov     rcx, [rbp+arg_8]
0x180018506  mov     [rbp+arg_8], rcx
0x18001850a  mov     [rbp+var_20], 10Fh
0x180018511  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180018518  mov     [rbp+var_18], rdx
0x18001851c  mov     [rbp+var_10], 0
0x180018524  test    eax, eax
0x180018526  js      short loc_18001856D
0x180018528  mov     [rbp+var_20], 111h
0x18001852f  mov     [rbp+var_18], rdx
0x180018533  mov     [rbp+var_10], 0
0x18001853b  mov     rax, [rcx]
0x18001853e  lea     rdx, [rbp+arg_0]
0x180018542  mov     rax, [rax+38h]
0x180018546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001854b  test    eax, eax
0x18001854d  js      short loc_180018561
0x18001854f  lea     rcx, [rbp+arg_8]
0x180018553  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018558  mov     eax, [rbp+arg_0]
0x18001855b  add     rsp, 40h
0x18001855f  pop     rbp
0x180018560  retn
0x180018561  lea     rdx, [rbp+var_20]
0x180018565  mov     ecx, eax
0x180018567  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001856d  lea     rdx, [rbp+var_20]
0x180018571  mov     ecx, eax
0x180018573  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
