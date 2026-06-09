# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x180022330`
- end: `0x180022402`
- name: `?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800228d0`
- `0x180023ac0`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x180022330`
- `0x180041010`

## string_xrefs

- `0x18002238a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
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
  v12 = 343;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v12);
  v12 = 345;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, *a3, *a4, &v11);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v12);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x180022330  push    rbp
0x180022332  push    rbx
0x180022333  push    rsi
0x180022334  push    rdi
0x180022335  mov     rbp, rsp
0x180022338  sub     rsp, 68h
0x18002233c  mov     rdi, r9
0x18002233f  mov     rsi, r8
0x180022342  mov     rbx, rdx
0x180022345  mov     [rbp+var_30], 0
0x18002234d  mov     rcx, [rcx]
0x180022350  test    rcx, rcx
0x180022353  jnz     short loc_18002235D
0x180022355  xor     eax, eax
0x180022357  mov     [rbp+arg_0], rax
0x18002235b  jmp     short loc_180022383
0x18002235d  mov     [rbp+arg_0], 0
0x180022365  mov     rax, [rcx]
0x180022368  lea     r8, [rbp+arg_0]
0x18002236c  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x180022373  mov     rax, [rax]
0x180022376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002237b  mov     rcx, [rbp+arg_0]
0x18002237f  mov     [rbp+arg_0], rcx
0x180022383  mov     [rbp+var_28], 157h
0x18002238a  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022391  mov     [rbp+var_20], rdx
0x180022395  mov     [rbp+var_18], 0
0x18002239d  test    eax, eax
0x18002239f  js      short loc_1800223F6
0x1800223a1  mov     [rbp+var_28], 159h
0x1800223a8  mov     [rbp+var_20], rdx
0x1800223ac  mov     [rbp+var_18], 0
0x1800223b4  mov     rax, [rcx]
0x1800223b7  lea     r9, [rbp+var_30]
0x1800223bb  mov     r8, [rdi]
0x1800223be  mov     rdx, [rsi]
0x1800223c1  mov     rax, [rax+38h]
0x1800223c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ca  test    eax, eax
0x1800223cc  js      short loc_1800223EA
0x1800223ce  lea     rcx, [rbp+arg_0]
0x1800223d2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800223d7  mov     rax, [rbp+var_30]
0x1800223db  mov     [rbx], rax
0x1800223de  mov     rax, rbx
0x1800223e1  add     rsp, 68h
0x1800223e5  pop     rdi
0x1800223e6  pop     rsi
0x1800223e7  pop     rbx
0x1800223e8  pop     rbp
0x1800223e9  retn
0x1800223ea  lea     rdx, [rbp+var_28]
0x1800223ee  mov     ecx, eax
0x1800223f0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800223f6  lea     rdx, [rbp+var_28]
0x1800223fa  mov     ecx, eax
0x1800223fc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
