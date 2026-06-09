# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::RemoveAt(uint)

- ea: `0x180027e70`
- end: `0x180027fc7`
- name: `?RemoveAt@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x180010200`
- `0x180027e70`
- `0x180034ef0`
- `0x180036f4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r14
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 *v8; // r14
  __int64 *i; // rdi
  __int64 v10; // rax
  __int64 *v11; // rcx
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  char v15; // [rsp+48h] [rbp-30h]

  v2 = a1 - 16;
  if ( !a1 )
    v2 = 0;
  v15 = 0;
  v3 = 0;
  if ( v2 != -40 )
    v3 = v2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)(v3 + 56) - *(_QWORD *)(v3 + 48)) >> 3) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 40));
  v4 = 0;
  if ( v2 != -40 )
    v4 = v2;
  v5 = (__int64 *)(*(_QWORD *)(v4 + 48) + 8LL * a2);
  v6 = *v5;
  *v5 = 0;
  v14 = v6;
  v15 = 1;
  v7 = 0;
  if ( v2 != -40 )
    v7 = v2;
  v8 = *(__int64 **)(v7 + 56);
  for ( i = v5 + 1; i != v8; ++i )
  {
    if ( v5 != i )
    {
      if ( *v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
      v10 = *i;
      *i = 0;
      *v5 = v10;
    }
    ++v5;
  }
  v11 = (__int64 *)(*(_QWORD *)(v7 + 56) - 8LL);
  if ( *v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v11);
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v15 && v14 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return 0;
}

```

## disassembly

```asm
0x180027e70  mov     [rsp+arg_8], rbx
0x180027e75  mov     [rsp+arg_10], rsi
0x180027e7a  push    rdi
0x180027e7b  push    r14
0x180027e7d  push    r15
0x180027e7f  sub     rsp, 60h
0x180027e83  mov     rax, cs:__security_cookie
0x180027e8a  xor     rax, rsp
0x180027e8d  mov     [rsp+78h+var_28], rax
0x180027e92  lea     r14, [rcx-10h]
0x180027e96  xor     r15d, r15d
0x180027e99  test    rcx, rcx
0x180027e9c  cmovz   r14, r15
0x180027ea0  lea     rdi, [r14+28h]
0x180027ea4  mov     [rsp+78h+var_30], r15b
0x180027ea9  mov     ecx, r15d
0x180027eac  test    rdi, rdi
0x180027eaf  cmovnz  rcx, r14
0x180027eb3  mov     r8d, edx
0x180027eb6  mov     rax, [rcx+38h]
0x180027eba  sub     rax, [rcx+30h]
0x180027ebe  sar     rax, 3
0x180027ec2  cmp     r8, rax
0x180027ec5  jnb     loc_180027FAA
0x180027ecb  lock inc dword ptr [rdi]
0x180027ece  mov     rax, r15
0x180027ed1  test    rdi, rdi
0x180027ed4  cmovnz  rax, r14
0x180027ed8  mov     rax, [rax+30h]
0x180027edc  lea     rbx, [rax+r8*8]
0x180027ee0  cmp     [rsp+78h+var_30], 0
0x180027ee5  jz      short loc_180027EFE
0x180027ee7  cmp     [rsp+78h+var_38], 0
0x180027eed  jz      short loc_180027EF9
0x180027eef  lea     rcx, [rsp+78h+var_38]
0x180027ef4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027ef9  mov     [rsp+78h+var_30], 0
0x180027efe  mov     rax, [rbx]
0x180027f01  mov     [rbx], r15
0x180027f04  mov     [rsp+78h+var_38], rax
0x180027f09  mov     [rsp+78h+var_30], 1
0x180027f0e  mov     rsi, r15
0x180027f11  test    rdi, rdi
0x180027f14  cmovnz  rsi, r14
0x180027f18  mov     r14, [rsi+38h]
0x180027f1c  lea     rdi, [rbx+8]
0x180027f20  cmp     rdi, r14
0x180027f23  jz      short loc_180027F4E
0x180027f25  cmp     rbx, rdi
0x180027f28  jz      short loc_180027F41
0x180027f2a  cmp     qword ptr [rbx], 0
0x180027f2e  jz      short loc_180027F38
0x180027f30  mov     rcx, rbx
0x180027f33  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027f38  mov     rax, [rdi]
0x180027f3b  mov     [rdi], r15
0x180027f3e  mov     [rbx], rax
0x180027f41  add     rbx, 8
0x180027f45  add     rdi, 8
0x180027f49  cmp     rdi, r14
0x180027f4c  jnz     short loc_180027F25
0x180027f4e  mov     rcx, [rsi+38h]
0x180027f52  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180027f56  cmp     qword ptr [rcx], 0
0x180027f5a  jz      short loc_180027F61
0x180027f5c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027f61  add     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFF8h
0x180027f66  cmp     [rsp+78h+var_30], 0
0x180027f6b  jz      short loc_180027F7F
0x180027f6d  cmp     [rsp+78h+var_38], 0
0x180027f73  jz      short loc_180027F7F
0x180027f75  lea     rcx, [rsp+78h+var_38]
0x180027f7a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027f7f  xor     eax, eax
0x180027f81  jmp     short loc_180027F87
0x180027f83  mov     eax, [rsp+78h+var_58]
0x180027f87  mov     rcx, [rsp+78h+var_28]
0x180027f8c  xor     rcx, rsp; StackCookie
0x180027f8f  call    __security_check_cookie
0x180027f94  lea     r11, [rsp+78h+var_18]
0x180027f99  mov     rbx, [r11+28h]
0x180027f9d  mov     rsi, [r11+30h]
0x180027fa1  mov     rsp, r11
0x180027fa4  pop     r15
0x180027fa6  pop     r14
0x180027fa8  pop     rdi
0x180027fa9  retn
0x180027faa  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180027faf  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x180027fb4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180027fbb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180027fc0  call    _CxxThrowException
```
