# winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)

- ea: `0x1800255b0`
- end: `0x18002568f`
- name: `??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ`
- size: `223`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x1800255b0`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  void (__fastcall ****v4)(_QWORD, __int64 *, __int64 *); // rax
  unsigned int v5; // r14d
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD *); // rbp
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF

  v3 = 0;
  v4 = *(void (__fastcall *****)(_QWORD, __int64 *, __int64 *))a1;
  v5 = *(_DWORD *)(a1 + 8);
  *a2 = 0;
  v6 = *v4;
  v10 = 0;
  if ( v6 )
  {
    (**v6)(
      v6,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
      &v10);
    v3 = v10;
  }
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v3 + 48LL);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  v8 = v7(v3, v5, a2);
  if ( v8 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v8);
  }
  _mm_lfence();
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  return a2;
}

```

## disassembly

```asm
0x1800255b0  mov     [rsp+arg_10], rbx
0x1800255b5  mov     [rsp+arg_18], rbp
0x1800255ba  push    rsi
0x1800255bb  push    rdi
0x1800255bc  push    r14
0x1800255be  sub     rsp, 40h
0x1800255c2  mov     rax, cs:__security_cookie
0x1800255c9  xor     rax, rsp
0x1800255cc  mov     [rsp+58h+var_20], rax
0x1800255d1  mov     rdi, rdx
0x1800255d4  mov     [rsp+58h+var_30], rdx
0x1800255d9  xor     ebx, ebx
0x1800255db  mov     [rsp+58h+var_38], ebx
0x1800255df  mov     rax, [rcx]
0x1800255e2  mov     r14d, [rcx+8]
0x1800255e6  mov     [rdx], rbx
0x1800255e9  mov     [rsp+58h+var_38], 2
0x1800255f1  mov     rcx, [rax]
0x1800255f4  mov     [rsp+58h+var_28], rbx
0x1800255f9  test    rcx, rcx
0x1800255fc  jz      short loc_180025620
0x1800255fe  mov     rax, [rcx]
0x180025601  lea     r8, [rsp+58h+var_28]
0x180025606  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x18002560d  mov     rax, [rax]
0x180025610  call    cs:__guard_dispatch_icall_fptr
0x180025616  mov     rbx, [rsp+58h+var_28]
0x18002561b  mov     [rsp+58h+var_28], rbx
0x180025620  mov     rsi, rbx
0x180025623  mov     rax, [rbx]
0x180025626  mov     rbp, [rax+30h]
0x18002562a  cmp     qword ptr [rdi], 0
0x18002562e  jz      short loc_180025638
0x180025630  mov     rcx, rdi
0x180025633  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025638  mov     r8, rdi
0x18002563b  mov     edx, r14d
0x18002563e  mov     rcx, rbx
0x180025641  mov     rax, rbp
0x180025644  call    cs:__guard_dispatch_icall_fptr
0x18002564a  test    eax, eax
0x18002564c  js      short loc_180025684
0x18002564e  lfence
0x180025651  test    rsi, rsi
0x180025654  jz      short loc_180025661
0x180025656  lea     rcx, [rsp+58h+var_28]
0x18002565b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025660  nop
0x180025661  mov     rax, rdi
0x180025664  mov     rcx, [rsp+58h+var_20]
0x180025669  xor     rcx, rsp; StackCookie
0x18002566c  call    __security_check_cookie
0x180025671  mov     rbx, [rsp+58h+arg_10]
0x180025676  mov     rbp, [rsp+58h+arg_18]
0x18002567b  add     rsp, 40h
0x18002567f  pop     r14
0x180025681  pop     rdi
0x180025682  pop     rsi
0x180025683  retn
0x180025684  lfence
0x180025687  mov     ecx, eax
0x180025689  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
