# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x180016f4c`
- end: `0x18001701e`
- name: `?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z`
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
- `0x180016f4c`
- `0x180032010`

## string_xrefs

- `0x180016fa6`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

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
0x180016f4c  push    rbp
0x180016f4e  push    rbx
0x180016f4f  push    rsi
0x180016f50  push    rdi
0x180016f51  mov     rbp, rsp
0x180016f54  sub     rsp, 68h
0x180016f58  mov     rdi, r9
0x180016f5b  mov     rsi, r8
0x180016f5e  mov     rbx, rdx
0x180016f61  mov     [rbp+var_30], 0
0x180016f69  mov     rcx, [rcx]
0x180016f6c  test    rcx, rcx
0x180016f6f  jnz     short loc_180016F79
0x180016f71  xor     eax, eax
0x180016f73  mov     [rbp+arg_0], rax
0x180016f77  jmp     short loc_180016F9F
0x180016f79  mov     [rbp+arg_0], 0
0x180016f81  mov     rax, [rcx]
0x180016f84  lea     r8, [rbp+arg_0]
0x180016f88  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x180016f8f  mov     rax, [rax]
0x180016f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f97  mov     rcx, [rbp+arg_0]
0x180016f9b  mov     [rbp+arg_0], rcx
0x180016f9f  mov     [rbp+var_28], 157h
0x180016fa6  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016fad  mov     [rbp+var_20], rdx
0x180016fb1  mov     [rbp+var_18], 0
0x180016fb9  test    eax, eax
0x180016fbb  js      short loc_180017012
0x180016fbd  mov     [rbp+var_28], 159h
0x180016fc4  mov     [rbp+var_20], rdx
0x180016fc8  mov     [rbp+var_18], 0
0x180016fd0  mov     rax, [rcx]
0x180016fd3  lea     r9, [rbp+var_30]
0x180016fd7  mov     r8, [rdi]
0x180016fda  mov     rdx, [rsi]
0x180016fdd  mov     rax, [rax+38h]
0x180016fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe6  test    eax, eax
0x180016fe8  js      short loc_180017006
0x180016fea  lea     rcx, [rbp+arg_0]
0x180016fee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016ff3  mov     rax, [rbp+var_30]
0x180016ff7  mov     [rbx], rax
0x180016ffa  mov     rax, rbx
0x180016ffd  add     rsp, 68h
0x180017001  pop     rdi
0x180017002  pop     rsi
0x180017003  pop     rbx
0x180017004  pop     rbp
0x180017005  retn
0x180017006  lea     rdx, [rbp+var_28]
0x18001700a  mov     ecx, eax
0x18001700c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180017012  lea     rdx, [rbp+var_28]
0x180017016  mov     ecx, eax
0x180017018  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
