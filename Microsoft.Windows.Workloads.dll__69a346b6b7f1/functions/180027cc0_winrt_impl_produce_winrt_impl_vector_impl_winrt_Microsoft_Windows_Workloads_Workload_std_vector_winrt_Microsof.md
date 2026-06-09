# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::RemoveAtEnd(void)

- ea: `0x180027cc0`
- end: `0x180027ddb`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x180010200`
- `0x180027cc0`
- `0x180034ef0`
- `0x180036f4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::RemoveAtEnd(
        __int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // rdx
  char v7; // r8
  __int64 *v8; // rcx
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h] BYREF
  char v12; // [rsp+48h] [rbp-20h]

  v1 = a1 - 16;
  v2 = 0;
  if ( !a1 )
    v1 = 0;
  v12 = 0;
  v3 = 0;
  if ( v1 != -40 )
    v3 = v1;
  if ( *(_QWORD *)(v3 + 48) == *(_QWORD *)(v3 + 56) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 40));
  v4 = 0;
  if ( v1 != -40 )
    v4 = v1;
  v5 = *(_QWORD *)(v4 + 56);
  v6 = *(_QWORD *)(v5 - 8);
  *(_QWORD *)(v5 - 8) = 0;
  v11 = v6;
  v7 = 1;
  v12 = 1;
  if ( v1 != -40 )
    v2 = v1;
  v8 = (__int64 *)(*(_QWORD *)(v2 + 56) - 8LL);
  if ( *v8 )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
    v7 = v12;
    v6 = v11;
  }
  *(_QWORD *)(v2 + 56) -= 8LL;
  if ( v7 && v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return 0;
}

```

## disassembly

```asm
0x180027cc0  mov     [rsp+arg_8], rbx
0x180027cc5  mov     [rsp+arg_10], rsi
0x180027cca  mov     [rsp+arg_18], rdi
0x180027ccf  push    r14
0x180027cd1  sub     rsp, 60h
0x180027cd5  mov     rax, cs:__security_cookie
0x180027cdc  xor     rax, rsp
0x180027cdf  mov     [rsp+68h+var_18], rax
0x180027ce4  lea     rsi, [rcx-10h]
0x180027ce8  xor     ebx, ebx
0x180027cea  test    rcx, rcx
0x180027ced  cmovz   rsi, rbx
0x180027cf1  lea     rdi, [rsi+28h]
0x180027cf5  mov     [rsp+68h+var_20], bl
0x180027cf9  mov     ecx, ebx
0x180027cfb  test    rdi, rdi
0x180027cfe  cmovnz  rcx, rsi
0x180027d02  mov     rax, [rcx+38h]
0x180027d06  cmp     [rcx+30h], rax
0x180027d0a  jz      loc_180027DBE
0x180027d10  lock inc dword ptr [rdi]
0x180027d13  mov     rax, rbx
0x180027d16  test    rdi, rdi
0x180027d19  cmovnz  rax, rsi
0x180027d1d  mov     r14, [rax+38h]
0x180027d21  cmp     [rsp+68h+var_20], 0
0x180027d26  jz      short loc_180027D3F
0x180027d28  cmp     [rsp+68h+var_28], 0
0x180027d2e  jz      short loc_180027D3A
0x180027d30  lea     rcx, [rsp+68h+var_28]
0x180027d35  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027d3a  mov     [rsp+68h+var_20], 0
0x180027d3f  mov     rdx, [r14-8]
0x180027d43  mov     [r14-8], rbx
0x180027d47  mov     [rsp+68h+var_28], rdx
0x180027d4c  mov     r8b, 1
0x180027d4f  mov     [rsp+68h+var_20], r8b
0x180027d54  test    rdi, rdi
0x180027d57  cmovnz  rbx, rsi
0x180027d5b  mov     rcx, [rbx+38h]
0x180027d5f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180027d63  cmp     qword ptr [rcx], 0
0x180027d67  jz      short loc_180027D79
0x180027d69  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027d6e  movzx   r8d, [rsp+68h+var_20]
0x180027d74  mov     rdx, [rsp+68h+var_28]
0x180027d79  add     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFF8h
0x180027d7e  test    r8b, r8b
0x180027d81  jz      short loc_180027D92
0x180027d83  test    rdx, rdx
0x180027d86  jz      short loc_180027D92
0x180027d88  lea     rcx, [rsp+68h+var_28]
0x180027d8d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027d92  xor     eax, eax
0x180027d94  jmp     short loc_180027D9A
0x180027d96  mov     eax, [rsp+68h+var_48]
0x180027d9a  mov     rcx, [rsp+68h+var_18]
0x180027d9f  xor     rcx, rsp; StackCookie
0x180027da2  call    __security_check_cookie
0x180027da7  lea     r11, [rsp+68h+var_8]
0x180027dac  mov     rbx, [r11+18h]
0x180027db0  mov     rsi, [r11+20h]
0x180027db4  mov     rdi, [r11+28h]
0x180027db8  mov     rsp, r11
0x180027dbb  pop     r14
0x180027dbd  retn
0x180027dbe  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027dc3  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x180027dc8  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180027dcf  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027dd4  call    _CxxThrowException
```
