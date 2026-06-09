# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)

- ea: `0x180016e7c`
- end: `0x180016f45`
- name: `?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z`
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
- `0x180016e7c`
- `0x180032010`

## string_xrefs

- `0x180016ed2`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+30h] [rbp-20h] BYREF
  const char *v8; // [rsp+38h] [rbp-18h]
  __int64 v9; // [rsp+40h] [rbp-10h]
  __int64 v10; // [rsp+60h] [rbp+10h] BYREF
  char v11; // [rsp+70h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 415;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 417;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v3 + 88LL))(v3, *a2, 0, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  return v11;
}

```

## disassembly

```asm
0x180016e7c  mov     [rsp-8+arg_8], rbx
0x180016e81  mov     [rsp-8+arg_10], r8b
0x180016e86  push    rbp
0x180016e87  mov     rbp, rsp
0x180016e8a  sub     rsp, 50h
0x180016e8e  mov     rbx, rdx
0x180016e91  mov     [rbp+arg_10], 0
0x180016e95  mov     rcx, [rcx]
0x180016e98  test    rcx, rcx
0x180016e9b  jnz     short loc_180016EA5
0x180016e9d  xor     eax, eax
0x180016e9f  mov     [rbp+arg_0], rax
0x180016ea3  jmp     short loc_180016ECB
0x180016ea5  mov     [rbp+arg_0], 0
0x180016ead  mov     rax, [rcx]
0x180016eb0  lea     r8, [rbp+arg_0]
0x180016eb4  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x180016ebb  mov     rax, [rax]
0x180016ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ec3  mov     rcx, [rbp+arg_0]
0x180016ec7  mov     [rbp+arg_0], rcx
0x180016ecb  mov     [rbp+var_20], 19Fh
0x180016ed2  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016ed9  mov     [rbp+var_18], rdx
0x180016edd  mov     [rbp+var_10], 0
0x180016ee5  test    eax, eax
0x180016ee7  js      short loc_180016F39
0x180016ee9  mov     [rbp+var_20], 1A1h
0x180016ef0  mov     [rbp+var_18], rdx
0x180016ef4  mov     [rbp+var_10], 0
0x180016efc  mov     rax, [rcx]
0x180016eff  lea     r9, [rbp+arg_10]
0x180016f03  xor     r8d, r8d
0x180016f06  mov     rdx, [rbx]
0x180016f09  mov     rax, [rax+58h]
0x180016f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f12  test    eax, eax
0x180016f14  js      short loc_180016F2D
0x180016f16  lea     rcx, [rbp+arg_0]
0x180016f1a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016f1f  mov     al, [rbp+arg_10]
0x180016f22  mov     rbx, [rsp+50h+arg_8]
0x180016f27  add     rsp, 50h
0x180016f2b  pop     rbp
0x180016f2c  retn
0x180016f2d  lea     rdx, [rbp+var_20]
0x180016f31  mov     ecx, eax
0x180016f33  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016f39  lea     rdx, [rbp+var_20]
0x180016f3d  mov     ecx, eax
0x180016f3f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
