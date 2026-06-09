# WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(winrt::Windows::Data::Json::JsonObject &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180018264`
- end: `0x18001839a`
- name: `?SetConfigurationResponseObjectFail@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017c54`

## callees

- `0x180004180`
- `0x18000b740`
- `0x180014974`
- `0x1800168a0`
- `0x180016ab4`
- `0x180018264`
- `0x1800183a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800182b9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800182b9`

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
  const unsigned __int16 *v10; // [rsp+48h] [rbp-38h]
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
0x180018264  mov     [rsp-18h+arg_10], rbx
0x180018269  push    rbp
0x18001826a  push    rsi
0x18001826b  push    rdi
0x18001826c  mov     rbp, rsp
0x18001826f  sub     rsp, 80h
0x180018276  mov     rax, cs:__security_cookie
0x18001827d  xor     rax, rsp
0x180018280  mov     [rbp+var_8], rax
0x180018284  mov     rbx, rdx
0x180018287  mov     rdi, rcx
0x18001828a  mov     [rbp+var_10], rdx
0x18001828e  cmp     qword ptr [rdx+18h], 7
0x180018293  jbe     short loc_180018298
0x180018295  mov     rdx, [rdx]
0x180018298  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001829c  xor     esi, esi
0x18001829e  inc     rcx
0x1800182a1  cmp     [rdx+rcx*2], si
0x1800182a5  jnz     short loc_18001829E
0x1800182a7  test    ecx, ecx
0x1800182a9  jnz     short loc_1800182B1
0x1800182ab  mov     [rbp+var_30], rsi
0x1800182af  jmp     short loc_1800182D6
0x1800182b1  mov     eax, ecx
0x1800182b3  cmp     [rdx+rax*2], si
0x1800182b7  jz      short loc_1800182C0
0x1800182b9  call    cs:__imp_abort
0x1800182c0  mov     [rbp+var_28], 1
0x1800182c7  mov     [rbp+var_24], ecx
0x1800182ca  mov     [rbp+var_18], rdx
0x1800182ce  lea     rax, [rbp+var_28]
0x1800182d2  mov     [rbp+var_30], rax
0x1800182d6  lea     rdx, [rbp+var_30]
0x1800182da  lea     rcx, [rbp+var_58]; struct winrt::param::hstring *
0x1800182de  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800182e3  nop
0x1800182e4  mov     [rbp+var_48], 1
0x1800182eb  mov     [rbp+var_44], 7
0x1800182f2  lea     rax, aMessage; "message"
0x1800182f9  mov     [rbp+var_38], rax
0x1800182fd  lea     rax, [rbp+var_48]
0x180018301  mov     [rbp+var_50], rax
0x180018305  lea     r8, [rbp+var_58]
0x180018309  lea     rdx, [rbp+var_50]
0x18001830d  mov     rcx, rdi
0x180018310  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180018315  xor     edx, edx
0x180018317  lea     rcx, [rbp+var_60]; bool
0x18001831b  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180018320  nop
0x180018321  mov     [rbp+var_48], 1
0x180018328  mov     [rbp+var_44], 7
0x18001832f  lea     rax, aSuccess; "success"
0x180018336  mov     [rbp+var_38], rax
0x18001833a  lea     rax, [rbp+var_48]
0x18001833e  mov     [rbp+var_50], rax
0x180018342  lea     r8, [rbp+var_60]
0x180018346  lea     rdx, [rbp+var_50]
0x18001834a  mov     rcx, rdi
0x18001834d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180018352  nop
0x180018353  cmp     qword ptr [rbp+var_60], rsi
0x180018357  jz      short loc_180018363
0x180018359  lea     rcx, [rbp+var_60]
0x18001835d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018362  nop
0x180018363  cmp     [rbp+var_58], rsi
0x180018367  jz      short loc_180018373
0x180018369  lea     rcx, [rbp+var_58]
0x18001836d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018372  nop
0x180018373  mov     rcx, rbx; void *
0x180018376  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001837b  mov     rcx, [rbp+var_8]
0x18001837f  xor     rcx, rsp; StackCookie
0x180018382  call    __security_check_cookie
0x180018387  mov     rbx, [rsp+80h+arg_10]
0x18001838f  add     rsp, 80h
0x180018396  pop     rdi
0x180018397  pop     rsi
0x180018398  pop     rbp
0x180018399  retn
```
