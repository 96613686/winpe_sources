# winrt::hresult_error::to_abi(void)

- ea: `0x1800017b0`
- end: `0x180001846`
- name: `?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ`
- size: `150`
- prototype: `_DWORD *__fastcall(__int64, _DWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c4c0`
- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## callees

- `0x1800017b0`
- `0x180005cb0`
- `0x180007280`
- `0x18000b807`
- `0x18000b930`

## pseudocode

```c
_DWORD *__fastcall winrt::hresult_error::to_abi(__int64 a1, _DWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, IErrorInfo **); // rcx
  void (__fastcall **v5)(_QWORD, __int64 *, IErrorInfo **); // rax
  IErrorInfo *v6; // rbx
  _DWORD *result; // rax
  IErrorInfo *perrinfo; // [rsp+20h] [rbp-18h] BYREF

  v4 = *(void (__fastcall ****)(_QWORD, __int64 *, IErrorInfo **))(a1 + 16);
  if ( v4 )
  {
    v5 = *v4;
    perrinfo = 0;
    (*v5)(v4, winrt::impl::guid_v<winrt::impl::IErrorInfo>, &perrinfo);
    v6 = perrinfo;
    SetErrorInfo_0(0, perrinfo);
    if ( v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&perrinfo);
  }
  result = a2;
  *a2 = *(_DWORD *)(a1 + 12);
  return result;
}

```

## disassembly

```asm
0x1800017b0  mov     [rsp+arg_18], rsi
0x1800017b5  push    rdi
0x1800017b6  sub     rsp, 30h
0x1800017ba  mov     rax, cs:__security_cookie
0x1800017c1  xor     rax, rsp
0x1800017c4  mov     [rsp+38h+var_10], rax
0x1800017c9  mov     rsi, rcx
0x1800017cc  mov     rdi, rdx
0x1800017cf  mov     rcx, [rcx+10h]
0x1800017d3  test    rcx, rcx
0x1800017d6  jz      short loc_180001826
0x1800017d8  mov     rax, [rcx]
0x1800017db  lea     r8, [rsp+38h+perrinfo]
0x1800017e0  lea     rdx, ??$guid_v@UIErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IErrorInfo>
0x1800017e7  mov     [rsp+38h+arg_10], rbx
0x1800017ec  mov     [rsp+38h+perrinfo], 0
0x1800017f5  mov     rax, [rax]
0x1800017f8  call    cs:__guard_dispatch_icall_fptr
0x1800017fe  mov     rbx, [rsp+38h+perrinfo]
0x180001803  xor     ecx, ecx; dwReserved
0x180001805  mov     rdx, rbx; perrinfo
0x180001808  mov     [rsp+38h+perrinfo], rbx
0x18000180d  call    SetErrorInfo_0
0x180001812  test    rbx, rbx
0x180001815  mov     rbx, [rsp+38h+arg_10]
0x18000181a  jz      short loc_180001826
0x18000181c  lea     rcx, [rsp+38h+perrinfo]
0x180001821  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180001826  mov     ecx, [rsi+0Ch]
0x180001829  mov     rax, rdi
0x18000182c  mov     [rdi], ecx
0x18000182e  mov     rcx, [rsp+38h+var_10]
0x180001833  xor     rcx, rsp; StackCookie
0x180001836  call    __security_check_cookie
0x18000183b  mov     rsi, [rsp+38h+arg_18]
0x180001840  add     rsp, 30h
0x180001844  pop     rdi
0x180001845  retn
```
