# winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(winrt::Windows::Data::Json::IJsonValue const &)

- ea: `0x18001caf8`
- end: `0x18001cbae`
- name: `?Append@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUIJsonValue@Json@Data@Windows@3@@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001caf8`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+20h] [rbp-20h] BYREF
  const char *v10; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+30h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+10h] BYREF

  v4 = *a1;
  if ( v4 )
  {
    v12 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
           &v12);
    v4 = v12;
  }
  else
  {
    v5 = 0;
    v12 = 0;
  }
  v9 = 678;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v11 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v9, a3);
  v9 = 680;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 104LL))(v4, *a2);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v9, v7);
  return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
}

```

## disassembly

```asm
0x18001caf8  mov     [rsp-8+arg_8], rbx
0x18001cafd  push    rbp
0x18001cafe  mov     rbp, rsp
0x18001cb01  sub     rsp, 40h
0x18001cb05  mov     rbx, rdx
0x18001cb08  mov     rcx, [rcx]
0x18001cb0b  test    rcx, rcx
0x18001cb0e  jnz     short loc_18001CB18
0x18001cb10  xor     eax, eax
0x18001cb12  mov     [rbp+arg_0], rax
0x18001cb16  jmp     short loc_18001CB3E
0x18001cb18  mov     [rbp+arg_0], 0
0x18001cb20  mov     rax, [rcx]
0x18001cb23  lea     r8, [rbp+arg_0]
0x18001cb27  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x18001cb2e  mov     rax, [rax]
0x18001cb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb36  mov     rcx, [rbp+arg_0]
0x18001cb3a  mov     [rbp+arg_0], rcx
0x18001cb3e  mov     [rbp+var_20], 2A6h
0x18001cb45  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001cb4c  mov     [rbp+var_18], rdx
0x18001cb50  mov     [rbp+var_10], 0
0x18001cb58  test    eax, eax
0x18001cb5a  js      short loc_18001CBA2
0x18001cb5c  mov     [rbp+var_20], 2A8h
0x18001cb63  mov     [rbp+var_18], rdx
0x18001cb67  mov     [rbp+var_10], 0
0x18001cb6f  mov     rax, [rcx]
0x18001cb72  mov     rdx, [rbx]
0x18001cb75  mov     rax, [rax+68h]
0x18001cb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7e  test    eax, eax
0x18001cb80  js      short loc_18001CB96
0x18001cb82  lea     rcx, [rbp+arg_0]
0x18001cb86  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cb8b  mov     rbx, [rsp+40h+arg_8]
0x18001cb90  add     rsp, 40h
0x18001cb94  pop     rbp
0x18001cb95  retn
0x18001cb96  lea     rdx, [rbp+var_20]
0x18001cb9a  mov     ecx, eax
0x18001cb9c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001cba2  lea     rdx, [rbp+var_20]
0x18001cba6  mov     ecx, eax
0x18001cba8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
