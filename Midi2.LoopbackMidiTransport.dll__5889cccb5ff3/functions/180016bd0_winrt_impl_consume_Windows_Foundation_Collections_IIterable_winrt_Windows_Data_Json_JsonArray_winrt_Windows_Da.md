# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::First(void)

- ea: `0x180016bd0`
- end: `0x180016c99`
- name: `?First@?$consume_Windows_Foundation_Collections_IIterable@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x180016bd0`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::First(
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
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Data::Json::IJsonValue>>,
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
0x180016bd0  mov     [rsp-8+arg_8], rbx
0x180016bd5  push    rbp
0x180016bd6  mov     rbp, rsp
0x180016bd9  sub     rsp, 40h
0x180016bdd  mov     rbx, rdx
0x180016be0  mov     [rbp+arg_10], 0
0x180016be8  mov     rcx, [rcx]
0x180016beb  test    rcx, rcx
0x180016bee  jnz     short loc_180016BF8
0x180016bf0  xor     eax, eax
0x180016bf2  mov     [rbp+arg_0], rax
0x180016bf6  jmp     short loc_180016C1E
0x180016bf8  mov     [rbp+arg_0], 0
0x180016c00  mov     rax, [rcx]
0x180016c03  lea     r8, [rbp+arg_0]
0x180016c07  lea     rdx, ??$guid_v@U?$IIterable@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Data::Json::IJsonValue>>
0x180016c0e  mov     rax, [rax]
0x180016c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c16  mov     rcx, [rbp+arg_0]
0x180016c1a  mov     [rbp+arg_0], rcx
0x180016c1e  mov     [rbp+var_18], 15h
0x180016c25  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016c2c  mov     [rbp+var_10], rdx
0x180016c30  mov     [rbp+var_8], 0
0x180016c38  test    eax, eax
0x180016c3a  js      short loc_180016C8D
0x180016c3c  mov     [rbp+var_18], 17h
0x180016c43  mov     [rbp+var_10], rdx
0x180016c47  mov     [rbp+var_8], 0
0x180016c4f  mov     rax, [rcx]
0x180016c52  lea     rdx, [rbp+arg_10]
0x180016c56  mov     rax, [rax+30h]
0x180016c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c5f  test    eax, eax
0x180016c61  js      short loc_180016C81
0x180016c63  lea     rcx, [rbp+arg_0]
0x180016c67  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016c6c  mov     rax, [rbp+arg_10]
0x180016c70  mov     [rbx], rax
0x180016c73  mov     rax, rbx
0x180016c76  mov     rbx, [rsp+40h+arg_8]
0x180016c7b  add     rsp, 40h
0x180016c7f  pop     rbp
0x180016c80  retn
0x180016c81  lea     rdx, [rbp+var_18]
0x180016c85  mov     ecx, eax
0x180016c87  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016c8d  lea     rdx, [rbp+var_18]
0x180016c91  mov     ecx, eax
0x180016c93  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
