# winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::Invoke(void *,int)

- ea: `0x18001acb0`
- end: `0x18001ad4f`
- name: `?Invoke@?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@UEAAHPEAXH@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x18001acb0`
- `0x180034ef0`
- `0x18003bed0`

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
0x18001acb0  mov     [rsp+arg_18], rbx
0x18001acb5  push    rdi
0x18001acb6  sub     rsp, 30h
0x18001acba  mov     rax, cs:__security_cookie
0x18001acc1  xor     rax, rsp
0x18001acc4  mov     [rsp+38h+var_10], rax
0x18001acc9  mov     edi, r8d
0x18001accc  mov     rbx, rdx
0x18001accf  mov     rdx, rcx
0x18001acd2  mov     [rsp+38h+var_18], 0
0x18001acdb  mov     rcx, [rcx+10h]
0x18001acdf  add     rdx, 18h
0x18001ace3  mov     rax, [rcx]
0x18001ace6  lea     r8, [rsp+38h+var_18]
0x18001aceb  mov     rax, [rax+18h]
0x18001acef  call    cs:__guard_dispatch_icall_fptr
0x18001acf5  mov     rcx, [rsp+38h+var_18]
0x18001acfa  mov     rax, [rcx]
0x18001acfd  mov     r8d, edi
0x18001ad00  mov     rdx, rbx
0x18001ad03  mov     rax, [rax+18h]
0x18001ad07  call    cs:__guard_dispatch_icall_fptr
0x18001ad0d  test    eax, eax
0x18001ad0f  js      short loc_18001AD43
0x18001ad11  cmp     [rsp+38h+var_18], 0
0x18001ad17  jz      short loc_18001AD23
0x18001ad19  lea     rcx, [rsp+38h+var_18]
0x18001ad1e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ad23  xor     eax, eax
0x18001ad25  jmp     short loc_18001AD2B
0x18001ad27  mov     eax, dword ptr [rsp+38h+var_18]
0x18001ad2b  mov     rcx, [rsp+38h+var_10]
0x18001ad30  xor     rcx, rsp; StackCookie
0x18001ad33  call    __security_check_cookie
0x18001ad38  mov     rbx, [rsp+38h+arg_18]
0x18001ad3d  add     rsp, 30h
0x18001ad41  pop     rdi
0x18001ad42  retn
0x18001ad43  lfence
0x18001ad46  mov     ecx, eax
0x18001ad48  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
