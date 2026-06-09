# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)

- ea: `0x18001863c`
- end: `0x180018705`
- name: `?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017584`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x18001863c`
- `0x180032010`

## string_xrefs

- `0x180018691`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
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
0x18001863c  mov     [rsp-8+arg_8], rbx
0x180018641  push    rbp
0x180018642  mov     rbp, rsp
0x180018645  sub     rsp, 40h
0x180018649  mov     rbx, rdx
0x18001864c  mov     [rbp+arg_10], 0
0x180018654  mov     rcx, [rcx]
0x180018657  test    rcx, rcx
0x18001865a  jnz     short loc_180018664
0x18001865c  xor     eax, eax
0x18001865e  mov     [rbp+arg_0], rax
0x180018662  jmp     short loc_18001868A
0x180018664  mov     [rbp+arg_0], 0
0x18001866c  mov     rax, [rcx]
0x18001866f  lea     r8, [rbp+arg_0]
0x180018673  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x18001867a  mov     rax, [rax]
0x18001867d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018682  mov     rcx, [rbp+arg_0]
0x180018686  mov     [rbp+arg_0], rcx
0x18001868a  mov     [rbp+var_18], 1C3h
0x180018691  lea     rdx, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180018698  mov     [rbp+var_10], rdx
0x18001869c  mov     [rbp+var_8], 0
0x1800186a4  test    eax, eax
0x1800186a6  js      short loc_1800186F9
0x1800186a8  mov     [rbp+var_18], 1C5h
0x1800186af  mov     [rbp+var_10], rdx
0x1800186b3  mov     [rbp+var_8], 0
0x1800186bb  mov     rax, [rcx]
0x1800186be  lea     rdx, [rbp+arg_10]
0x1800186c2  mov     rax, [rax+38h]
0x1800186c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186cb  test    eax, eax
0x1800186cd  js      short loc_1800186ED
0x1800186cf  lea     rcx, [rbp+arg_0]
0x1800186d3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800186d8  mov     rax, [rbp+arg_10]
0x1800186dc  mov     [rbx], rax
0x1800186df  mov     rax, rbx
0x1800186e2  mov     rbx, [rsp+40h+arg_8]
0x1800186e7  add     rsp, 40h
0x1800186eb  pop     rbp
0x1800186ec  retn
0x1800186ed  lea     rdx, [rbp+var_18]
0x1800186f1  mov     ecx, eax
0x1800186f3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800186f9  lea     rdx, [rbp+var_18]
0x1800186fd  mov     ecx, eax
0x1800186ff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
