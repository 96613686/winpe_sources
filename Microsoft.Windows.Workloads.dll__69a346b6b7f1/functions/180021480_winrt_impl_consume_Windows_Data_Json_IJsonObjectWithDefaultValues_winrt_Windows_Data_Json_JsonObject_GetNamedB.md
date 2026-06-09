# winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)

- ea: `0x180021480`
- end: `0x18002152b`
- name: `?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z`
- size: `171`
- prototype: `__int64 __fastcall(void (__fastcall ****)(_QWORD, __int64 *, __int64 *), _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180021480`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  void (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // r9
  __int64 v4; // rcx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v9[8]; // [rsp+38h] [rbp-20h] BYREF

  v9[0] = 0;
  v3 = *a1;
  v4 = 0;
  v8 = 0;
  if ( v3 )
  {
    (**v3)(v3, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>, &v8);
    v4 = v8;
  }
  v5 = v4;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v4 + 88LL))(v4, *a2, 0, v9);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  if ( v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
  return v9[0];
}

```

## disassembly

```asm
0x180021480  mov     [rsp+arg_10], rbx
0x180021485  push    rdi
0x180021486  sub     rsp, 50h
0x18002148a  mov     rax, cs:__security_cookie
0x180021491  xor     rax, rsp
0x180021494  mov     [rsp+58h+var_18], rax
0x180021499  mov     rdi, rdx
0x18002149c  mov     [rsp+58h+var_20], 0
0x1800214a1  mov     r9, [rcx]
0x1800214a4  xor     ecx, ecx
0x1800214a6  mov     [rsp+58h+var_28], rcx
0x1800214ab  test    r9, r9
0x1800214ae  jz      short loc_1800214D5
0x1800214b0  mov     rax, [r9]
0x1800214b3  lea     r8, [rsp+58h+var_28]
0x1800214b8  lea     rdx, ??$guid_v@UIJsonObjectWithDefaultValues@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectWithDefaultValues>
0x1800214bf  mov     rcx, r9
0x1800214c2  mov     rax, [rax]
0x1800214c5  call    cs:__guard_dispatch_icall_fptr
0x1800214cb  mov     rcx, [rsp+58h+var_28]
0x1800214d0  mov     [rsp+58h+var_28], rcx
0x1800214d5  mov     rbx, rcx
0x1800214d8  mov     rax, [rcx]
0x1800214db  lea     r9, [rsp+58h+var_20]
0x1800214e0  xor     r8d, r8d
0x1800214e3  mov     rdx, [rdi]
0x1800214e6  mov     rax, [rax+58h]
0x1800214ea  call    cs:__guard_dispatch_icall_fptr
0x1800214f0  test    eax, eax
0x1800214f2  js      short loc_180021520
0x1800214f4  test    rbx, rbx
0x1800214f7  jz      short loc_180021503
0x1800214f9  lea     rcx, [rsp+58h+var_28]
0x1800214fe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021503  movzx   eax, [rsp+58h+var_20]
0x180021508  mov     rcx, [rsp+58h+var_18]
0x18002150d  xor     rcx, rsp; StackCookie
0x180021510  call    __security_check_cookie
0x180021515  mov     rbx, [rsp+58h+arg_10]
0x18002151a  add     rsp, 50h
0x18002151e  pop     rdi
0x18002151f  retn
0x180021520  lfence
0x180021523  mov     ecx, eax
0x180021525  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
