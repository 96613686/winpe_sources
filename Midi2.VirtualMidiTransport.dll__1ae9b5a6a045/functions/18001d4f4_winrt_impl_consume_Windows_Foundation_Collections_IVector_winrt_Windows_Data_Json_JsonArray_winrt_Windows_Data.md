# winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)

- ea: `0x18001d4f4`
- end: `0x18001d5a9`
- name: `?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001d4f4`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001d4f4  push    rbp
0x18001d4f6  mov     rbp, rsp
0x18001d4f9  sub     rsp, 40h
0x18001d4fd  mov     [rbp+arg_0], 0
0x18001d504  mov     rcx, [rcx]
0x18001d507  test    rcx, rcx
0x18001d50a  jnz     short loc_18001D514
0x18001d50c  xor     eax, eax
0x18001d50e  mov     [rbp+arg_8], rax
0x18001d512  jmp     short loc_18001D53A
0x18001d514  mov     [rbp+arg_8], 0
0x18001d51c  mov     rax, [rcx]
0x18001d51f  lea     r8, [rbp+arg_8]
0x18001d523  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x18001d52a  mov     rax, [rax]
0x18001d52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d532  mov     rcx, [rbp+arg_8]
0x18001d536  mov     [rbp+arg_8], rcx
0x18001d53a  mov     [rbp+var_20], 241h
0x18001d541  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d548  mov     [rbp+var_18], rdx
0x18001d54c  mov     [rbp+var_10], 0
0x18001d554  test    eax, eax
0x18001d556  js      short loc_18001D59D
0x18001d558  mov     [rbp+var_20], 243h
0x18001d55f  mov     [rbp+var_18], rdx
0x18001d563  mov     [rbp+var_10], 0
0x18001d56b  mov     rax, [rcx]
0x18001d56e  lea     rdx, [rbp+arg_0]
0x18001d572  mov     rax, [rax+38h]
0x18001d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d57b  test    eax, eax
0x18001d57d  js      short loc_18001D591
0x18001d57f  lea     rcx, [rbp+arg_8]
0x18001d583  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d588  mov     eax, [rbp+arg_0]
0x18001d58b  add     rsp, 40h
0x18001d58f  pop     rbp
0x18001d590  retn
0x18001d591  lea     rdx, [rbp+var_20]
0x18001d595  mov     ecx, eax
0x18001d597  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d59d  lea     rdx, [rbp+var_20]
0x18001d5a1  mov     ecx, eax
0x18001d5a3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
