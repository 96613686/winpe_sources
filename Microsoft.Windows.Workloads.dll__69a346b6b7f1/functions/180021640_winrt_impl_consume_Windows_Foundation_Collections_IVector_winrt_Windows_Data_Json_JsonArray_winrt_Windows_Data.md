# winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)

- ea: `0x180021640`
- end: `0x1800216d7`
- name: `?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180021640`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *))
{
  void (__fastcall ***v1)(_QWORD, __int64 *, __int64 *); // r9
  __int64 v2; // rcx
  __int64 v3; // rbx
  signed int v4; // eax
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v7; // [rsp+28h] [rbp-20h] BYREF

  v1 = *a1;
  v2 = 0;
  v7 = 0;
  v6 = 0;
  if ( v1 )
  {
    (**v1)(
      v1,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
      &v6);
    v2 = v6;
  }
  v3 = v2;
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v2 + 56LL))(v2, &v7);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v4);
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v6);
  return v7;
}

```

## disassembly

```asm
0x180021640  push    rbx
0x180021642  sub     rsp, 40h
0x180021646  mov     rax, cs:__security_cookie
0x18002164d  xor     rax, rsp
0x180021650  mov     [rsp+48h+var_18], rax
0x180021655  mov     r9, [rcx]
0x180021658  xor     ecx, ecx
0x18002165a  mov     [rsp+48h+var_20], ecx
0x18002165e  mov     [rsp+48h+var_28], rcx
0x180021663  test    r9, r9
0x180021666  jz      short loc_18002168D
0x180021668  mov     rax, [r9]
0x18002166b  lea     r8, [rsp+48h+var_28]
0x180021670  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x180021677  mov     rcx, r9
0x18002167a  mov     rax, [rax]
0x18002167d  call    cs:__guard_dispatch_icall_fptr
0x180021683  mov     rcx, [rsp+48h+var_28]
0x180021688  mov     [rsp+48h+var_28], rcx
0x18002168d  mov     rbx, rcx
0x180021690  mov     rax, [rcx]
0x180021693  lea     rdx, [rsp+48h+var_20]
0x180021698  mov     rax, [rax+38h]
0x18002169c  call    cs:__guard_dispatch_icall_fptr
0x1800216a2  test    eax, eax
0x1800216a4  js      short loc_1800216CC
0x1800216a6  test    rbx, rbx
0x1800216a9  jz      short loc_1800216B5
0x1800216ab  lea     rcx, [rsp+48h+var_28]
0x1800216b0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800216b5  mov     eax, [rsp+48h+var_20]
0x1800216b9  mov     rcx, [rsp+48h+var_18]
0x1800216be  xor     rcx, rsp; StackCookie
0x1800216c1  call    __security_check_cookie
0x1800216c6  add     rsp, 40h
0x1800216ca  pop     rbx
0x1800216cb  retn
0x1800216cc  lfence
0x1800216cf  mov     ecx, eax
0x1800216d1  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
