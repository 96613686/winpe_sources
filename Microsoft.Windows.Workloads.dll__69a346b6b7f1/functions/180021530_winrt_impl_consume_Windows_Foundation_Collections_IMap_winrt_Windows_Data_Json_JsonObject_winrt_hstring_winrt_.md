# winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)

- ea: `0x180021530`
- end: `0x1800215d8`
- name: `?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `168`
- prototype: `__int64 __fastcall(void (__fastcall ****)(_QWORD, __int64 *, __int64 *), _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180021530`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  void (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // r9
  __int64 v4; // rcx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-20h] BYREF

  v9[0] = 0;
  v3 = *a1;
  v4 = 0;
  v8 = 0;
  if ( v3 )
  {
    (**v3)(
      v3,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
      &v8);
    v4 = v8;
  }
  v5 = v4;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v4 + 64LL))(v4, *a2, v9);
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
0x180021530  mov     [rsp+arg_8], rbx
0x180021535  push    rdi
0x180021536  sub     rsp, 40h
0x18002153a  mov     rax, cs:__security_cookie
0x180021541  xor     rax, rsp
0x180021544  mov     [rsp+48h+var_18], rax
0x180021549  mov     rdi, rdx
0x18002154c  mov     [rsp+48h+var_20], 0
0x180021551  mov     r9, [rcx]
0x180021554  xor     ecx, ecx
0x180021556  mov     [rsp+48h+var_28], rcx
0x18002155b  test    r9, r9
0x18002155e  jz      short loc_180021585
0x180021560  mov     rax, [r9]
0x180021563  lea     r8, [rsp+48h+var_28]
0x180021568  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>
0x18002156f  mov     rcx, r9
0x180021572  mov     rax, [rax]
0x180021575  call    cs:__guard_dispatch_icall_fptr
0x18002157b  mov     rcx, [rsp+48h+var_28]
0x180021580  mov     [rsp+48h+var_28], rcx
0x180021585  mov     rbx, rcx
0x180021588  mov     rax, [rcx]
0x18002158b  lea     r8, [rsp+48h+var_20]
0x180021590  mov     rdx, [rdi]
0x180021593  mov     rax, [rax+40h]
0x180021597  call    cs:__guard_dispatch_icall_fptr
0x18002159d  test    eax, eax
0x18002159f  js      short loc_1800215CD
0x1800215a1  test    rbx, rbx
0x1800215a4  jz      short loc_1800215B0
0x1800215a6  lea     rcx, [rsp+48h+var_28]
0x1800215ab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800215b0  movzx   eax, [rsp+48h+var_20]
0x1800215b5  mov     rcx, [rsp+48h+var_18]
0x1800215ba  xor     rcx, rsp; StackCookie
0x1800215bd  call    __security_check_cookie
0x1800215c2  mov     rbx, [rsp+48h+arg_8]
0x1800215c7  add     rsp, 40h
0x1800215cb  pop     rdi
0x1800215cc  retn
0x1800215cd  lfence
0x1800215d0  mov     ecx, eax
0x1800215d2  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
