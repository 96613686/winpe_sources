# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)

- ea: `0x18001cec4`
- end: `0x18001cf96`
- name: `?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001cec4`
- `0x180021010`

## string_xrefs

- `0x18001cf1e`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

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
0x18001cec4  push    rbp
0x18001cec6  push    rbx
0x18001cec7  push    rsi
0x18001cec8  push    rdi
0x18001cec9  mov     rbp, rsp
0x18001cecc  sub     rsp, 68h
0x18001ced0  mov     rdi, r9
0x18001ced3  mov     rsi, r8
0x18001ced6  mov     rbx, rdx
0x18001ced9  mov     [rbp+var_30], 0
0x18001cee1  mov     rcx, [rcx]
0x18001cee4  test    rcx, rcx
0x18001cee7  jnz     short loc_18001CEF1
0x18001cee9  xor     eax, eax
0x18001ceeb  mov     [rbp+arg_0], rax
0x18001ceef  jmp     short loc_18001CF17
0x18001cef1  mov     [rbp+arg_0], 0
0x18001cef9  mov     rax, [rcx]
0x18001cefc  lea     r8, [rbp+arg_0]
0x18001cf00  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18001cf07  mov     rax, [rax]
0x18001cf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0f  mov     rcx, [rbp+arg_0]
0x18001cf13  mov     [rbp+arg_0], rcx
0x18001cf17  mov     [rbp+var_28], 169h
0x18001cf1e  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001cf25  mov     [rbp+var_20], rdx
0x18001cf29  mov     [rbp+var_18], 0
0x18001cf31  test    eax, eax
0x18001cf33  js      short loc_18001CF8A
0x18001cf35  mov     [rbp+var_28], 16Bh
0x18001cf3c  mov     [rbp+var_20], rdx
0x18001cf40  mov     [rbp+var_18], 0
0x18001cf48  mov     rax, [rcx]
0x18001cf4b  lea     r9, [rbp+var_30]
0x18001cf4f  mov     r8, [rdi]
0x18001cf52  mov     rdx, [rsi]
0x18001cf55  mov     rax, [rax+40h]
0x18001cf59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf5e  test    eax, eax
0x18001cf60  js      short loc_18001CF7E
0x18001cf62  lea     rcx, [rbp+arg_0]
0x18001cf66  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cf6b  mov     rax, [rbp+var_30]
0x18001cf6f  mov     [rbx], rax
0x18001cf72  mov     rax, rbx
0x18001cf75  add     rsp, 68h
0x18001cf79  pop     rdi
0x18001cf7a  pop     rsi
0x18001cf7b  pop     rbx
0x18001cf7c  pop     rbp
0x18001cf7d  retn
0x18001cf7e  lea     rdx, [rbp+var_28]
0x18001cf82  mov     ecx, eax
0x18001cf84  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001cf8a  lea     rdx, [rbp+var_28]
0x18001cf8e  mov     ecx, eax
0x18001cf90  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
