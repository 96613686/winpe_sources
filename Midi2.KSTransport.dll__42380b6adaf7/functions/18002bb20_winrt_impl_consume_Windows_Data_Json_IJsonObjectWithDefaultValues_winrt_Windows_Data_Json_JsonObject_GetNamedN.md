# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)

- ea: `0x18002bb20`
- end: `0x18002bbf7`
- name: `?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002af94`
- `0x18002c4a4`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x18002bb20`
- `0x180041010`

## string_xrefs

- `0x18002bb7d`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v8; // [rsp+30h] [rbp-30h] BYREF
  const char *v9; // [rsp+38h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-20h]
  __int64 v11; // [rsp+70h] [rbp+10h] BYREF
  double v12; // [rsp+88h] [rbp+28h] BYREF

  v12 = 0.0;
  v4 = *a1;
  if ( v4 )
  {
    v11 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>,
           &v11);
    v4 = v11;
  }
  else
  {
    v5 = 0;
    v11 = 0;
  }
  v8 = 397;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v10 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v8);
  v8 = 399;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, double *))(*(_QWORD *)v4 + 80LL))(v4, *a2, a3, &v12);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v8);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return v12;
}

```

## disassembly

```asm
0x18002bb20  mov     [rsp-8+arg_8], rbx
0x18002bb25  push    rbp
0x18002bb26  mov     rbp, rsp
0x18002bb29  sub     rsp, 60h
0x18002bb2d  movaps  [rsp+60h+var_10], xmm6
0x18002bb32  movaps  xmm6, xmm2
0x18002bb35  mov     rbx, rdx
0x18002bb38  xorps   xmm0, xmm0
0x18002bb3b  movsd   [rbp+arg_18], xmm0
0x18002bb40  mov     rcx, [rcx]
0x18002bb43  test    rcx, rcx
0x18002bb46  jnz     short loc_18002BB50
0x18002bb48  xor     eax, eax
0x18002bb4a  mov     [rbp+arg_0], rax
0x18002bb4e  jmp     short loc_18002BB76
0x18002bb50  mov     [rbp+arg_0], 0
0x18002bb58  mov     rax, [rcx]
0x18002bb5b  lea     r8, [rbp+arg_0]
0x18002bb5f  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18002bb66  mov     rax, [rax]
0x18002bb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb6e  mov     rcx, [rbp+arg_0]
0x18002bb72  mov     [rbp+arg_0], rcx
0x18002bb76  mov     [rbp+var_30], 18Dh
0x18002bb7d  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002bb84  mov     [rbp+var_28], rdx
0x18002bb88  mov     [rbp+var_20], 0
0x18002bb90  test    eax, eax
0x18002bb92  js      short loc_18002BBEB
0x18002bb94  mov     [rbp+var_30], 18Fh
0x18002bb9b  mov     [rbp+var_28], rdx
0x18002bb9f  mov     [rbp+var_20], 0
0x18002bba7  mov     rax, [rcx]
0x18002bbaa  lea     r9, [rbp+arg_18]
0x18002bbae  movaps  xmm2, xmm6
0x18002bbb1  mov     rdx, [rbx]
0x18002bbb4  mov     rax, [rax+50h]
0x18002bbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbbd  test    eax, eax
0x18002bbbf  js      short loc_18002BBDF
0x18002bbc1  lea     rcx, [rbp+arg_0]
0x18002bbc5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002bbca  movsd   xmm0, [rbp+arg_18]
0x18002bbcf  mov     rbx, [rsp+60h+arg_8]
0x18002bbd4  movaps  xmm6, [rsp+60h+var_10]
0x18002bbd9  add     rsp, 60h
0x18002bbdd  pop     rbp
0x18002bbde  retn
0x18002bbdf  lea     rdx, [rbp+var_30]
0x18002bbe3  mov     ecx, eax
0x18002bbe5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bbeb  lea     rdx, [rbp+var_30]
0x18002bbef  mov     ecx, eax
0x18002bbf1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
