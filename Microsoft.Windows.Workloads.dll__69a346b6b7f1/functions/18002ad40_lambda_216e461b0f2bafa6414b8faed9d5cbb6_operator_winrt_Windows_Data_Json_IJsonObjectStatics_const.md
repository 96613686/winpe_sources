# _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)

- ea: `0x18002ad40`
- end: `0x18002add8`
- name: `??R_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ade0`
- `0x18002afa0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x18002ad40`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rdi
  char *v3; // rbx
  _QWORD *v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, char *, _BYTE *); // rbp
  int v6; // eax
  char v8; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v9[8]; // [rsp+38h] [rbp-30h] BYREF

  v2 = *a2;
  v3 = (char *)a1[1];
  v4 = (_QWORD *)*a1;
  v9[0] = 0;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, _BYTE *))(*(_QWORD *)v2 + 56LL);
  if ( v3 != &v8 )
  {
    if ( *(_QWORD *)v3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3);
    *(_QWORD *)v3 = 0;
  }
  v6 = v5(v2, *v4, v3, v9);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  return v9[0];
}

```

## disassembly

```asm
0x18002ad40  mov     [rsp+arg_10], rbx
0x18002ad45  push    rbp
0x18002ad46  push    rsi
0x18002ad47  push    rdi
0x18002ad48  sub     rsp, 50h
0x18002ad4c  mov     rax, cs:__security_cookie
0x18002ad53  xor     rax, rsp
0x18002ad56  mov     [rsp+68h+var_28], rax
0x18002ad5b  mov     rdi, [rdx]
0x18002ad5e  mov     rbx, [rcx+8]
0x18002ad62  mov     rsi, [rcx]
0x18002ad65  mov     [rsp+68h+var_30], 0
0x18002ad6a  mov     rax, [rdi]
0x18002ad6d  mov     rbp, [rax+38h]
0x18002ad71  lea     rax, [rsp+68h+var_38]
0x18002ad76  cmp     rbx, rax
0x18002ad79  jz      short loc_18002AD90
0x18002ad7b  cmp     qword ptr [rbx], 0
0x18002ad7f  jz      short loc_18002AD89
0x18002ad81  mov     rcx, rbx
0x18002ad84  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ad89  mov     qword ptr [rbx], 0
0x18002ad90  mov     rdx, [rsi]
0x18002ad93  lea     r9, [rsp+68h+var_30]
0x18002ad98  mov     r8, rbx
0x18002ad9b  mov     rcx, rdi
0x18002ad9e  mov     rax, rbp
0x18002ada1  call    cs:__guard_dispatch_icall_fptr
0x18002ada7  test    eax, eax
0x18002ada9  js      short loc_18002ADCD
0x18002adab  movzx   eax, [rsp+68h+var_30]
0x18002adb0  mov     rcx, [rsp+68h+var_28]
0x18002adb5  xor     rcx, rsp; StackCookie
0x18002adb8  call    __security_check_cookie
0x18002adbd  mov     rbx, [rsp+68h+arg_10]
0x18002adc5  add     rsp, 50h
0x18002adc9  pop     rdi
0x18002adca  pop     rsi
0x18002adcb  pop     rbp
0x18002adcc  retn
0x18002adcd  lfence
0x18002add0  mov     ecx, eax
0x18002add2  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
