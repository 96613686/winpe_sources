# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(void)

- ea: `0x1800212e0`
- end: `0x180021399`
- name: `?end@?$consume_Windows_Foundation_Collections_IIterable@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `185`
- prototype: `__int64 __fastcall(void (__fastcall ****)(_QWORD, __int64 *, __int64 *), __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x1800212e0`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        __int64 a2)
{
  __int64 v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64 *, __int64 *); // r9
  __int64 v6; // rdi
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  int v10; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  v10 = 0;
  v5 = *a1;
  v9 = 0;
  if ( v5 )
  {
    (**v5)(
      v5,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
      &v9);
    v4 = v9;
  }
  v6 = v4;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 56LL))(v4, &v10);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7);
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  *(_QWORD *)a2 = a1;
  *(_DWORD *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x1800212e0  mov     [rsp+arg_10], rbx
0x1800212e5  mov     [rsp+arg_18], rsi
0x1800212ea  push    rdi
0x1800212eb  sub     rsp, 40h
0x1800212ef  mov     rax, cs:__security_cookie
0x1800212f6  xor     rax, rsp
0x1800212f9  mov     [rsp+48h+var_18], rax
0x1800212fe  mov     rbx, rdx
0x180021301  mov     rsi, rcx
0x180021304  xor     ecx, ecx
0x180021306  mov     [rsp+48h+var_20], ecx
0x18002130a  mov     r9, [rsi]
0x18002130d  mov     [rsp+48h+var_28], rcx
0x180021312  test    r9, r9
0x180021315  jz      short loc_18002133C
0x180021317  mov     rax, [r9]
0x18002131a  lea     r8, [rsp+48h+var_28]
0x18002131f  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x180021326  mov     rcx, r9
0x180021329  mov     rax, [rax]
0x18002132c  call    cs:__guard_dispatch_icall_fptr
0x180021332  mov     rcx, [rsp+48h+var_28]
0x180021337  mov     [rsp+48h+var_28], rcx
0x18002133c  mov     rdi, rcx
0x18002133f  mov     rax, [rcx]
0x180021342  lea     rdx, [rsp+48h+var_20]
0x180021347  mov     rax, [rax+38h]
0x18002134b  call    cs:__guard_dispatch_icall_fptr
0x180021351  test    eax, eax
0x180021353  js      short loc_18002138E
0x180021355  test    rdi, rdi
0x180021358  jz      short loc_180021364
0x18002135a  lea     rcx, [rsp+48h+var_28]
0x18002135f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021364  mov     [rbx], rsi
0x180021367  mov     ecx, [rsp+48h+var_20]
0x18002136b  mov     [rbx+8], ecx
0x18002136e  mov     rax, rbx
0x180021371  mov     rcx, [rsp+48h+var_18]
0x180021376  xor     rcx, rsp; StackCookie
0x180021379  call    __security_check_cookie
0x18002137e  mov     rbx, [rsp+48h+arg_10]
0x180021383  mov     rsi, [rsp+48h+arg_18]
0x180021388  add     rsp, 40h
0x18002138c  pop     rdi
0x18002138d  retn
0x18002138e  lfence
0x180021391  mov     ecx, eax
0x180021393  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
