# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)

- ea: `0x1800221e8`
- end: `0x1800222ba`
- name: `?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023ac0`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x1800221e8`
- `0x180041010`

## string_xrefs

- `0x180022242`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
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
  v12 = 379;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v12);
  v12 = 381;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, *a3, *a4, &v11);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v12);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800221e8  push    rbp
0x1800221ea  push    rbx
0x1800221eb  push    rsi
0x1800221ec  push    rdi
0x1800221ed  mov     rbp, rsp
0x1800221f0  sub     rsp, 68h
0x1800221f4  mov     rdi, r9
0x1800221f7  mov     rsi, r8
0x1800221fa  mov     rbx, rdx
0x1800221fd  mov     [rbp+var_30], 0
0x180022205  mov     rcx, [rcx]
0x180022208  test    rcx, rcx
0x18002220b  jnz     short loc_180022215
0x18002220d  xor     eax, eax
0x18002220f  mov     [rbp+arg_0], rax
0x180022213  jmp     short loc_18002223B
0x180022215  mov     [rbp+arg_0], 0
0x18002221d  mov     rax, [rcx]
0x180022220  lea     r8, [rbp+arg_0]
0x180022224  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18002222b  mov     rax, [rax]
0x18002222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022233  mov     rcx, [rbp+arg_0]
0x180022237  mov     [rbp+arg_0], rcx
0x18002223b  mov     [rbp+var_28], 17Bh
0x180022242  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022249  mov     [rbp+var_20], rdx
0x18002224d  mov     [rbp+var_18], 0
0x180022255  test    eax, eax
0x180022257  js      short loc_1800222AE
0x180022259  mov     [rbp+var_28], 17Dh
0x180022260  mov     [rbp+var_20], rdx
0x180022264  mov     [rbp+var_18], 0
0x18002226c  mov     rax, [rcx]
0x18002226f  lea     r9, [rbp+var_30]
0x180022273  mov     r8, [rdi]
0x180022276  mov     rdx, [rsi]
0x180022279  mov     rax, [rax+48h]
0x18002227d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022282  test    eax, eax
0x180022284  js      short loc_1800222A2
0x180022286  lea     rcx, [rbp+arg_0]
0x18002228a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002228f  mov     rax, [rbp+var_30]
0x180022293  mov     [rbx], rax
0x180022296  mov     rax, rbx
0x180022299  add     rsp, 68h
0x18002229d  pop     rdi
0x18002229e  pop     rsi
0x18002229f  pop     rbx
0x1800222a0  pop     rbp
0x1800222a1  retn
0x1800222a2  lea     rdx, [rbp+var_28]
0x1800222a6  mov     ecx, eax
0x1800222a8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800222ae  lea     rdx, [rbp+var_28]
0x1800222b2  mov     ecx, eax
0x1800222b4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
