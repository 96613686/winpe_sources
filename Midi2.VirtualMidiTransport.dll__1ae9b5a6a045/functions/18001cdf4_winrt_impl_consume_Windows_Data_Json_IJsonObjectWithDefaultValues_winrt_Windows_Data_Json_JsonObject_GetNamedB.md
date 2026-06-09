# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)

- ea: `0x18001cdf4`
- end: `0x18001cebd`
- name: `?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001cdf4`
- `0x180021010`

## string_xrefs

- `0x18001ce4a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

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
0x18001cdf4  mov     [rsp-8+arg_8], rbx
0x18001cdf9  mov     [rsp-8+arg_10], r8b
0x18001cdfe  push    rbp
0x18001cdff  mov     rbp, rsp
0x18001ce02  sub     rsp, 50h
0x18001ce06  mov     rbx, rdx
0x18001ce09  mov     [rbp+arg_10], 0
0x18001ce0d  mov     rcx, [rcx]
0x18001ce10  test    rcx, rcx
0x18001ce13  jnz     short loc_18001CE1D
0x18001ce15  xor     eax, eax
0x18001ce17  mov     [rbp+arg_0], rax
0x18001ce1b  jmp     short loc_18001CE43
0x18001ce1d  mov     [rbp+arg_0], 0
0x18001ce25  mov     rax, [rcx]
0x18001ce28  lea     r8, [rbp+arg_0]
0x18001ce2c  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x18001ce33  mov     rax, [rax]
0x18001ce36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce3b  mov     rcx, [rbp+arg_0]
0x18001ce3f  mov     [rbp+arg_0], rcx
0x18001ce43  mov     [rbp+var_20], 19Fh
0x18001ce4a  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001ce51  mov     [rbp+var_18], rdx
0x18001ce55  mov     [rbp+var_10], 0
0x18001ce5d  test    eax, eax
0x18001ce5f  js      short loc_18001CEB1
0x18001ce61  mov     [rbp+var_20], 1A1h
0x18001ce68  mov     [rbp+var_18], rdx
0x18001ce6c  mov     [rbp+var_10], 0
0x18001ce74  mov     rax, [rcx]
0x18001ce77  lea     r9, [rbp+arg_10]
0x18001ce7b  xor     r8d, r8d
0x18001ce7e  mov     rdx, [rbx]
0x18001ce81  mov     rax, [rax+58h]
0x18001ce85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce8a  test    eax, eax
0x18001ce8c  js      short loc_18001CEA5
0x18001ce8e  lea     rcx, [rbp+arg_0]
0x18001ce92  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ce97  mov     al, [rbp+arg_10]
0x18001ce9a  mov     rbx, [rsp+50h+arg_8]
0x18001ce9f  add     rsp, 50h
0x18001cea3  pop     rbp
0x18001cea4  retn
0x18001cea5  lea     rdx, [rbp+var_20]
0x18001cea9  mov     ecx, eax
0x18001ceab  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ceb1  lea     rdx, [rbp+var_20]
0x18001ceb5  mov     ecx, eax
0x18001ceb7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
