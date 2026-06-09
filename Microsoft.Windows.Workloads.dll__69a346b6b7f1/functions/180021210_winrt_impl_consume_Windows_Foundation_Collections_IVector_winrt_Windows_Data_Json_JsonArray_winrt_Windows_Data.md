# winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(uint)

- ea: `0x180021210`
- end: `0x1800212db`
- name: `?GetAt@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@I@Z`
- size: `203`
- prototype: `_QWORD *__fastcall(void (__fastcall ****)(_QWORD, __int64 *, __int64 *), _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180021210`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v5; // rbx
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD *); // rbp
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF

  v5 = 0;
  *a2 = 0;
  v6 = *a1;
  v10 = 0;
  if ( v6 )
  {
    (**v6)(
      v6,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
      &v10);
    v5 = v10;
  }
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v5 + 48LL);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  v8 = v7(v5, a3, a2);
  if ( v8 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v8);
  }
  _mm_lfence();
  if ( v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  return a2;
}

```

## disassembly

```asm
0x180021210  push    rbx
0x180021212  push    rbp
0x180021213  push    rsi
0x180021214  push    rdi
0x180021215  push    r14
0x180021217  sub     rsp, 40h
0x18002121b  mov     rax, cs:__security_cookie
0x180021222  xor     rax, rsp
0x180021225  mov     [rsp+68h+var_30], rax
0x18002122a  mov     r14d, r8d
0x18002122d  mov     rdi, rdx
0x180021230  mov     [rsp+68h+var_40], rdx
0x180021235  xor     ebx, ebx
0x180021237  mov     [rsp+68h+var_48], ebx
0x18002123b  mov     [rdx], rbx
0x18002123e  mov     [rsp+68h+var_48], 1
0x180021246  mov     rcx, [rcx]
0x180021249  mov     [rsp+68h+var_38], rbx
0x18002124e  test    rcx, rcx
0x180021251  jz      short loc_180021275
0x180021253  mov     rax, [rcx]
0x180021256  lea     r8, [rsp+68h+var_38]
0x18002125b  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x180021262  mov     rax, [rax]
0x180021265  call    cs:__guard_dispatch_icall_fptr
0x18002126b  mov     rbx, [rsp+68h+var_38]
0x180021270  mov     [rsp+68h+var_38], rbx
0x180021275  mov     rsi, rbx
0x180021278  mov     rax, [rbx]
0x18002127b  mov     rbp, [rax+30h]
0x18002127f  cmp     qword ptr [rdi], 0
0x180021283  jz      short loc_18002128D
0x180021285  mov     rcx, rdi
0x180021288  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002128d  mov     r8, rdi
0x180021290  mov     edx, r14d
0x180021293  mov     rcx, rbx
0x180021296  mov     rax, rbp
0x180021299  call    cs:__guard_dispatch_icall_fptr
0x18002129f  test    eax, eax
0x1800212a1  js      short loc_1800212D0
0x1800212a3  lfence
0x1800212a6  test    rsi, rsi
0x1800212a9  jz      short loc_1800212B5
0x1800212ab  lea     rcx, [rsp+68h+var_38]
0x1800212b0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800212b5  mov     rax, rdi
0x1800212b8  mov     rcx, [rsp+68h+var_30]
0x1800212bd  xor     rcx, rsp; StackCookie
0x1800212c0  call    __security_check_cookie
0x1800212c5  add     rsp, 40h
0x1800212c9  pop     r14
0x1800212cb  pop     rdi
0x1800212cc  pop     rsi
0x1800212cd  pop     rbp
0x1800212ce  pop     rbx
0x1800212cf  retn
0x1800212d0  lfence
0x1800212d3  mov     ecx, eax
0x1800212d5  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
