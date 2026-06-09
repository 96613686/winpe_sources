# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)

- ea: `0x18001d5b0`
- end: `0x18001d679`
- name: `?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d33c`
- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001d5b0`
- `0x180021010`

## string_xrefs

- `0x18001d605`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
0x18001d5b0  mov     [rsp-8+arg_8], rbx
0x18001d5b5  push    rbp
0x18001d5b6  mov     rbp, rsp
0x18001d5b9  sub     rsp, 40h
0x18001d5bd  mov     rbx, rdx
0x18001d5c0  mov     [rbp+arg_10], 0
0x18001d5c8  mov     rcx, [rcx]
0x18001d5cb  test    rcx, rcx
0x18001d5ce  jnz     short loc_18001D5D8
0x18001d5d0  xor     eax, eax
0x18001d5d2  mov     [rbp+arg_0], rax
0x18001d5d6  jmp     short loc_18001D5FE
0x18001d5d8  mov     [rbp+arg_0], 0
0x18001d5e0  mov     rax, [rcx]
0x18001d5e3  lea     r8, [rbp+arg_0]
0x18001d5e7  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x18001d5ee  mov     rax, [rax]
0x18001d5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5f6  mov     rcx, [rbp+arg_0]
0x18001d5fa  mov     [rbp+arg_0], rcx
0x18001d5fe  mov     [rbp+var_18], 1C3h
0x18001d605  lea     rdx, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d60c  mov     [rbp+var_10], rdx
0x18001d610  mov     [rbp+var_8], 0
0x18001d618  test    eax, eax
0x18001d61a  js      short loc_18001D66D
0x18001d61c  mov     [rbp+var_18], 1C5h
0x18001d623  mov     [rbp+var_10], rdx
0x18001d627  mov     [rbp+var_8], 0
0x18001d62f  mov     rax, [rcx]
0x18001d632  lea     rdx, [rbp+arg_10]
0x18001d636  mov     rax, [rax+38h]
0x18001d63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d63f  test    eax, eax
0x18001d641  js      short loc_18001D661
0x18001d643  lea     rcx, [rbp+arg_0]
0x18001d647  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d64c  mov     rax, [rbp+arg_10]
0x18001d650  mov     [rbx], rax
0x18001d653  mov     rax, rbx
0x18001d656  mov     rbx, [rsp+40h+arg_8]
0x18001d65b  add     rsp, 40h
0x18001d65f  pop     rbp
0x18001d660  retn
0x18001d661  lea     rdx, [rbp+var_18]
0x18001d665  mov     ecx, eax
0x18001d667  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d66d  lea     rdx, [rbp+var_18]
0x18001d671  mov     ecx, eax
0x18001d673  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
