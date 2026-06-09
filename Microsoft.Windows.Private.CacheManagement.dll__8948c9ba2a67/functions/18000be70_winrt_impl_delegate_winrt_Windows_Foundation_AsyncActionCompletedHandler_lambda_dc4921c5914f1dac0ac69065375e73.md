# winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::Invoke(void *,int)

- ea: `0x18000be70`
- end: `0x18000bf0f`
- name: `?Invoke@?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@UEAAHPEAXH@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x18000be70`
- `0x1800181b0`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::Invoke(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  int v5; // eax
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 16) + 24LL))(
    *(_QWORD *)(a1 + 16),
    a1 + 24,
    &v7);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, a2, a3);
  if ( v5 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v5);
  }
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v7);
  return 0;
}

```

## disassembly

```asm
0x18000be70  mov     [rsp+arg_18], rbx
0x18000be75  push    rdi
0x18000be76  sub     rsp, 30h
0x18000be7a  mov     rax, cs:__security_cookie
0x18000be81  xor     rax, rsp
0x18000be84  mov     [rsp+38h+var_10], rax
0x18000be89  mov     edi, r8d
0x18000be8c  mov     rbx, rdx
0x18000be8f  mov     rdx, rcx
0x18000be92  mov     [rsp+38h+var_18], 0
0x18000be9b  mov     rcx, [rcx+10h]
0x18000be9f  add     rdx, 18h
0x18000bea3  mov     rax, [rcx]
0x18000bea6  lea     r8, [rsp+38h+var_18]
0x18000beab  mov     rax, [rax+18h]
0x18000beaf  call    cs:__guard_dispatch_icall_fptr
0x18000beb5  mov     rcx, [rsp+38h+var_18]
0x18000beba  mov     rax, [rcx]
0x18000bebd  mov     r8d, edi
0x18000bec0  mov     rdx, rbx
0x18000bec3  mov     rax, [rax+18h]
0x18000bec7  call    cs:__guard_dispatch_icall_fptr
0x18000becd  test    eax, eax
0x18000becf  js      short loc_18000BF03
0x18000bed1  cmp     [rsp+38h+var_18], 0
0x18000bed7  jz      short loc_18000BEE3
0x18000bed9  lea     rcx, [rsp+38h+var_18]
0x18000bede  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bee3  xor     eax, eax
0x18000bee5  jmp     short loc_18000BEEB
0x18000bee7  mov     eax, dword ptr [rsp+38h+var_18]
0x18000beeb  mov     rcx, [rsp+38h+var_10]
0x18000bef0  xor     rcx, rsp; StackCookie
0x18000bef3  call    __security_check_cookie
0x18000bef8  mov     rbx, [rsp+38h+arg_18]
0x18000befd  add     rsp, 30h
0x18000bf01  pop     rdi
0x18000bf02  retn
0x18000bf03  lfence
0x18000bf06  mov     ecx, eax
0x18000bf08  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
