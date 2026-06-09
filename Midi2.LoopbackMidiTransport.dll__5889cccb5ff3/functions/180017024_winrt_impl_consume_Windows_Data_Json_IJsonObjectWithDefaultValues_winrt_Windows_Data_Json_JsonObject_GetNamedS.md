# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)

- ea: `0x180017024`
- end: `0x1800170f6`
- name: `?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z`
- size: `210`
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
- `0x180017024`
- `0x180032010`

## string_xrefs

- `0x18001707e`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

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
0x180017024  push    rbp
0x180017026  push    rbx
0x180017027  push    rsi
0x180017028  push    rdi
0x180017029  mov     rbp, rsp
0x18001702c  sub     rsp, 68h
0x180017030  mov     rdi, r9
0x180017033  mov     rsi, r8
0x180017036  mov     rbx, rdx
0x180017039  mov     [rbp+var_30], 0
0x180017041  mov     rcx, [rcx]
0x180017044  test    rcx, rcx
0x180017047  jnz     short loc_180017051
0x180017049  xor     eax, eax
0x18001704b  mov     [rbp+arg_0], rax
0x18001704f  jmp     short loc_180017077
0x180017051  mov     [rbp+arg_0], 0
0x180017059  mov     rax, [rcx]
0x18001705c  lea     r8, [rbp+arg_0]
0x180017060  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x180017067  mov     rax, [rax]
0x18001706a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001706f  mov     rcx, [rbp+arg_0]
0x180017073  mov     [rbp+arg_0], rcx
0x180017077  mov     [rbp+var_28], 169h
0x18001707e  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180017085  mov     [rbp+var_20], rdx
0x180017089  mov     [rbp+var_18], 0
0x180017091  test    eax, eax
0x180017093  js      short loc_1800170EA
0x180017095  mov     [rbp+var_28], 16Bh
0x18001709c  mov     [rbp+var_20], rdx
0x1800170a0  mov     [rbp+var_18], 0
0x1800170a8  mov     rax, [rcx]
0x1800170ab  lea     r9, [rbp+var_30]
0x1800170af  mov     r8, [rdi]
0x1800170b2  mov     rdx, [rsi]
0x1800170b5  mov     rax, [rax+40h]
0x1800170b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170be  test    eax, eax
0x1800170c0  js      short loc_1800170DE
0x1800170c2  lea     rcx, [rbp+arg_0]
0x1800170c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800170cb  mov     rax, [rbp+var_30]
0x1800170cf  mov     [rbx], rax
0x1800170d2  mov     rax, rbx
0x1800170d5  add     rsp, 68h
0x1800170d9  pop     rdi
0x1800170da  pop     rsi
0x1800170db  pop     rbx
0x1800170dc  pop     rbp
0x1800170dd  retn
0x1800170de  lea     rdx, [rbp+var_28]
0x1800170e2  mov     ecx, eax
0x1800170e4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800170ea  lea     rdx, [rbp+var_28]
0x1800170ee  mov     ecx, eax
0x1800170f0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
