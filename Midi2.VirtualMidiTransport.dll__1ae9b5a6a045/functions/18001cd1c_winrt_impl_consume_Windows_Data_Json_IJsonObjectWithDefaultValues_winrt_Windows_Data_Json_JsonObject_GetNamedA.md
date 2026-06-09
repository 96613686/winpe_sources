# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)

- ea: `0x18001cd1c`
- end: `0x18001cdee`
- name: `?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z`
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
- `0x18001cd1c`
- `0x180021010`

## string_xrefs

- `0x18001cd76`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

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
0x18001cd1c  push    rbp
0x18001cd1e  push    rbx
0x18001cd1f  push    rsi
0x18001cd20  push    rdi
0x18001cd21  mov     rbp, rsp
0x18001cd24  sub     rsp, 68h
0x18001cd28  mov     rdi, r9
0x18001cd2b  mov     rsi, r8
0x18001cd2e  mov     rbx, rdx
0x18001cd31  mov     [rbp+var_30], 0
0x18001cd39  mov     rcx, [rcx]
0x18001cd3c  test    rcx, rcx
0x18001cd3f  jnz     short loc_18001CD49
0x18001cd41  xor     eax, eax
0x18001cd43  mov     [rbp+arg_0], rax
0x18001cd47  jmp     short loc_18001CD6F
0x18001cd49  mov     [rbp+arg_0], 0
0x18001cd51  mov     rax, [rcx]
0x18001cd54  lea     r8, [rbp+arg_0]
0x18001cd58  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18001cd5f  mov     rax, [rax]
0x18001cd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd67  mov     rcx, [rbp+arg_0]
0x18001cd6b  mov     [rbp+arg_0], rcx
0x18001cd6f  mov     [rbp+var_28], 17Bh
0x18001cd76  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001cd7d  mov     [rbp+var_20], rdx
0x18001cd81  mov     [rbp+var_18], 0
0x18001cd89  test    eax, eax
0x18001cd8b  js      short loc_18001CDE2
0x18001cd8d  mov     [rbp+var_28], 17Dh
0x18001cd94  mov     [rbp+var_20], rdx
0x18001cd98  mov     [rbp+var_18], 0
0x18001cda0  mov     rax, [rcx]
0x18001cda3  lea     r9, [rbp+var_30]
0x18001cda7  mov     r8, [rdi]
0x18001cdaa  mov     rdx, [rsi]
0x18001cdad  mov     rax, [rax+48h]
0x18001cdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdb6  test    eax, eax
0x18001cdb8  js      short loc_18001CDD6
0x18001cdba  lea     rcx, [rbp+arg_0]
0x18001cdbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cdc3  mov     rax, [rbp+var_30]
0x18001cdc7  mov     [rbx], rax
0x18001cdca  mov     rax, rbx
0x18001cdcd  add     rsp, 68h
0x18001cdd1  pop     rdi
0x18001cdd2  pop     rsi
0x18001cdd3  pop     rbx
0x18001cdd4  pop     rbp
0x18001cdd5  retn
0x18001cdd6  lea     rdx, [rbp+var_28]
0x18001cdda  mov     ecx, eax
0x18001cddc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001cde2  lea     rdx, [rbp+var_28]
0x18001cde6  mov     ecx, eax
0x18001cde8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
