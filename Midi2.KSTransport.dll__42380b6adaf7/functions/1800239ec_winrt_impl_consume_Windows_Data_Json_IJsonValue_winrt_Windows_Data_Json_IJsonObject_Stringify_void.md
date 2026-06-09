# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)

- ea: `0x1800239ec`
- end: `0x180023ab5`
- name: `?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227c4`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x1800239ec`
- `0x180041010`

## string_xrefs

- `0x180023a41`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-18h] BYREF
  const char *v8; // [rsp+30h] [rbp-10h]
  __int64 v9; // [rsp+38h] [rbp-8h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 451;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 453;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL))(v3, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800239ec  mov     [rsp-8+arg_8], rbx
0x1800239f1  push    rbp
0x1800239f2  mov     rbp, rsp
0x1800239f5  sub     rsp, 40h
0x1800239f9  mov     rbx, rdx
0x1800239fc  mov     [rbp+arg_10], 0
0x180023a04  mov     rcx, [rcx]
0x180023a07  test    rcx, rcx
0x180023a0a  jnz     short loc_180023A14
0x180023a0c  xor     eax, eax
0x180023a0e  mov     [rbp+arg_0], rax
0x180023a12  jmp     short loc_180023A3A
0x180023a14  mov     [rbp+arg_0], 0
0x180023a1c  mov     rax, [rcx]
0x180023a1f  lea     r8, [rbp+arg_0]
0x180023a23  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180023a2a  mov     rax, [rax]
0x180023a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a32  mov     rcx, [rbp+arg_0]
0x180023a36  mov     [rbp+arg_0], rcx
0x180023a3a  mov     [rbp+var_18], 1C3h
0x180023a41  lea     rdx, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180023a48  mov     [rbp+var_10], rdx
0x180023a4c  mov     [rbp+var_8], 0
0x180023a54  test    eax, eax
0x180023a56  js      short loc_180023AA9
0x180023a58  mov     [rbp+var_18], 1C5h
0x180023a5f  mov     [rbp+var_10], rdx
0x180023a63  mov     [rbp+var_8], 0
0x180023a6b  mov     rax, [rcx]
0x180023a6e  lea     rdx, [rbp+arg_10]
0x180023a72  mov     rax, [rax+38h]
0x180023a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a7b  test    eax, eax
0x180023a7d  js      short loc_180023A9D
0x180023a7f  lea     rcx, [rbp+arg_0]
0x180023a83  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023a88  mov     rax, [rbp+arg_10]
0x180023a8c  mov     [rbx], rax
0x180023a8f  mov     rax, rbx
0x180023a92  mov     rbx, [rsp+40h+arg_8]
0x180023a97  add     rsp, 40h
0x180023a9b  pop     rbp
0x180023a9c  retn
0x180023a9d  lea     rdx, [rbp+var_18]
0x180023aa1  mov     ecx, eax
0x180023aa3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023aa9  lea     rdx, [rbp+var_18]
0x180023aad  mov     ecx, eax
0x180023aaf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
