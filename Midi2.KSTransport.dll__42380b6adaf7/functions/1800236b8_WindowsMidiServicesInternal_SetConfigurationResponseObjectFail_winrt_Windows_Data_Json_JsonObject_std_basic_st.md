# WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(winrt::Windows::Data::Json::JsonObject &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800236b8`
- end: `0x1800237ee`
- name: `?SetConfigurationResponseObjectFail@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e38`

## callees

- `0x180004410`
- `0x18000c250`
- `0x18000d1c0`
- `0x180022080`
- `0x18002213c`
- `0x1800236b8`
- `0x1800237f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002370d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002370d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(__int64 **a1, _QWORD *a2)
{
  void *v2; // rbx
  __int64 v4; // rcx
  bool v5[8]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v6; // [rsp+28h] [rbp-58h] BYREF
  int *v7; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+38h] [rbp-48h] BYREF
  int v9; // [rsp+3Ch] [rbp-44h]
  const wchar_t *v10; // [rsp+48h] [rbp-38h]
  _DWORD *v11; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v12[4]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-18h]
  _QWORD *v14; // [rsp+70h] [rbp-10h]

  v2 = a2;
  v14 = a2;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)a2 + v4) );
  if ( (_DWORD)v4 )
  {
    if ( *((_WORD *)a2 + (unsigned int)v4) )
      abort();
    v12[0] = 1;
    v12[1] = v4;
    v13 = a2;
    v11 = v12;
  }
  else
  {
    v11 = 0;
  }
  winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v6, &v11);
  v8 = 1;
  v9 = 7;
  v10 = L"message";
  v7 = &v8;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a1,
    (__int64 *)&v7,
    &v6);
  winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((char **)v5, 0);
  v8 = 1;
  v9 = 7;
  v10 = L"success";
  v7 = &v8;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a1,
    (__int64 *)&v7,
    (__int64 *)v5);
  if ( *(_QWORD *)v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v5);
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v6);
  std::wstring::~wstring(v2);
}

```

## disassembly

```asm
0x1800236b8  mov     [rsp-18h+arg_10], rbx
0x1800236bd  push    rbp
0x1800236be  push    rsi
0x1800236bf  push    rdi
0x1800236c0  mov     rbp, rsp
0x1800236c3  sub     rsp, 80h
0x1800236ca  mov     rax, cs:__security_cookie
0x1800236d1  xor     rax, rsp
0x1800236d4  mov     [rbp+var_8], rax
0x1800236d8  mov     rbx, rdx
0x1800236db  mov     rdi, rcx
0x1800236de  mov     [rbp+var_10], rdx
0x1800236e2  cmp     qword ptr [rdx+18h], 7
0x1800236e7  jbe     short loc_1800236EC
0x1800236e9  mov     rdx, [rdx]
0x1800236ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800236f0  xor     esi, esi
0x1800236f2  inc     rcx
0x1800236f5  cmp     [rdx+rcx*2], si
0x1800236f9  jnz     short loc_1800236F2
0x1800236fb  test    ecx, ecx
0x1800236fd  jnz     short loc_180023705
0x1800236ff  mov     [rbp+var_30], rsi
0x180023703  jmp     short loc_18002372A
0x180023705  mov     eax, ecx
0x180023707  cmp     [rdx+rax*2], si
0x18002370b  jz      short loc_180023714
0x18002370d  call    cs:__imp_abort
0x180023714  mov     [rbp+var_28], 1
0x18002371b  mov     [rbp+var_24], ecx
0x18002371e  mov     [rbp+var_18], rdx
0x180023722  lea     rax, [rbp+var_28]
0x180023726  mov     [rbp+var_30], rax
0x18002372a  lea     rdx, [rbp+var_30]
0x18002372e  lea     rcx, [rbp+var_58]; struct winrt::param::hstring *
0x180023732  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180023737  nop
0x180023738  mov     [rbp+var_48], 1
0x18002373f  mov     [rbp+var_44], 7
0x180023746  lea     rax, aMessage; "message"
0x18002374d  mov     [rbp+var_38], rax
0x180023751  lea     rax, [rbp+var_48]
0x180023755  mov     [rbp+var_50], rax
0x180023759  lea     r8, [rbp+var_58]
0x18002375d  lea     rdx, [rbp+var_50]
0x180023761  mov     rcx, rdi
0x180023764  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180023769  xor     edx, edx
0x18002376b  lea     rcx, [rbp+var_60]; bool
0x18002376f  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180023774  nop
0x180023775  mov     [rbp+var_48], 1
0x18002377c  mov     [rbp+var_44], 7
0x180023783  lea     rax, aSuccess; "success"
0x18002378a  mov     [rbp+var_38], rax
0x18002378e  lea     rax, [rbp+var_48]
0x180023792  mov     [rbp+var_50], rax
0x180023796  lea     r8, [rbp+var_60]
0x18002379a  lea     rdx, [rbp+var_50]
0x18002379e  mov     rcx, rdi
0x1800237a1  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800237a6  nop
0x1800237a7  cmp     qword ptr [rbp+var_60], rsi
0x1800237ab  jz      short loc_1800237B7
0x1800237ad  lea     rcx, [rbp+var_60]
0x1800237b1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800237b6  nop
0x1800237b7  cmp     [rbp+var_58], rsi
0x1800237bb  jz      short loc_1800237C7
0x1800237bd  lea     rcx, [rbp+var_58]
0x1800237c1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800237c6  nop
0x1800237c7  mov     rcx, rbx; void *
0x1800237ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800237cf  mov     rcx, [rbp+var_8]
0x1800237d3  xor     rcx, rsp; StackCookie
0x1800237d6  call    __security_check_cookie
0x1800237db  mov     rbx, [rsp+80h+arg_10]
0x1800237e3  add     rsp, 80h
0x1800237ea  pop     rdi
0x1800237eb  pop     rsi
0x1800237ec  pop     rbp
0x1800237ed  retn
```
