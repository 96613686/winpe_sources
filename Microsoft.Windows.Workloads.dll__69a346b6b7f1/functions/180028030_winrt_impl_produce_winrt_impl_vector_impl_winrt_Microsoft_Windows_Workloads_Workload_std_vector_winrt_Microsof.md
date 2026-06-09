# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::SetAt(uint,void *)

- ea: `0x180028030`
- end: `0x180028150`
- name: `?SetAt@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x180010200`
- `0x180028030`
- `0x180034ef0`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::SetAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h] BYREF
  char v12; // [rsp+48h] [rbp-30h]
  char v13; // [rsp+90h] [rbp+18h] BYREF

  v4 = a1 - 16;
  if ( !a1 )
    v4 = 0;
  v12 = 0;
  v5 = 0;
  if ( v4 != -40 )
    v5 = v4;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)(v5 + 56) - *(_QWORD *)(v5 + 48)) >> 3) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 40));
  v6 = 0;
  if ( v4 != -40 )
    v6 = v4;
  v7 = (__int64 *)(*(_QWORD *)(v6 + 48) + 8LL * a2);
  v8 = *v7;
  *v7 = 0;
  v11 = v8;
  v12 = 1;
  if ( v7 != (__int64 *)&v13 )
  {
    if ( *v7 )
    {
      _mm_lfence();
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    }
    *v7 = a3;
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  if ( v12 && v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return 0;
}

```

## disassembly

```asm
0x180028030  push    rbx
0x180028032  push    rsi
0x180028033  push    rdi
0x180028034  sub     rsp, 60h
0x180028038  mov     rax, cs:__security_cookie
0x18002803f  xor     rax, rsp
0x180028042  mov     [rsp+78h+var_28], rax
0x180028047  mov     rdi, r8
0x18002804a  mov     eax, edx
0x18002804c  lea     r8, [rcx-10h]
0x180028050  xor     esi, esi
0x180028052  test    rcx, rcx
0x180028055  cmovz   r8, rsi
0x180028059  lea     rdx, [r8+28h]
0x18002805d  mov     [rsp+78h+var_30], sil
0x180028062  mov     ecx, esi
0x180028064  test    rdx, rdx
0x180028067  cmovnz  rcx, r8
0x18002806b  mov     r9d, eax
0x18002806e  mov     rax, [rcx+38h]
0x180028072  sub     rax, [rcx+30h]
0x180028076  sar     rax, 3
0x18002807a  cmp     r9, rax
0x18002807d  jnb     loc_180028133
0x180028083  lock inc dword ptr [rdx]
0x180028086  mov     rax, rsi
0x180028089  test    rdx, rdx
0x18002808c  cmovnz  rax, r8
0x180028090  mov     rax, [rax+30h]
0x180028094  lea     rbx, [rax+r9*8]
0x180028098  cmp     [rsp+78h+var_30], 0
0x18002809d  jz      short loc_1800280B6
0x18002809f  cmp     [rsp+78h+var_38], 0
0x1800280a5  jz      short loc_1800280B1
0x1800280a7  lea     rcx, [rsp+78h+var_38]
0x1800280ac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800280b1  mov     [rsp+78h+var_30], 0
0x1800280b6  mov     rax, [rbx]
0x1800280b9  mov     [rbx], rsi
0x1800280bc  mov     [rsp+78h+var_38], rax
0x1800280c1  mov     [rsp+78h+var_30], 1
0x1800280c6  lea     rax, [rsp+78h+arg_10]
0x1800280ce  cmp     rbx, rax
0x1800280d1  jz      short loc_1800280FD
0x1800280d3  cmp     qword ptr [rbx], 0
0x1800280d7  jz      short loc_1800280E4
0x1800280d9  lfence
0x1800280dc  mov     rcx, rbx
0x1800280df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800280e4  mov     [rbx], rdi
0x1800280e7  test    rdi, rdi
0x1800280ea  jz      short loc_1800280FD
0x1800280ec  mov     rax, [rdi]
0x1800280ef  mov     rcx, rdi
0x1800280f2  mov     rax, [rax+8]
0x1800280f6  call    cs:__guard_dispatch_icall_fptr
0x1800280fc  nop
0x1800280fd  cmp     [rsp+78h+var_30], 0
0x180028102  jz      short loc_180028116
0x180028104  cmp     [rsp+78h+var_38], 0
0x18002810a  jz      short loc_180028116
0x18002810c  lea     rcx, [rsp+78h+var_38]
0x180028111  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028116  xor     eax, eax
0x180028118  jmp     short loc_18002811E
0x18002811a  mov     eax, [rsp+78h+var_58]
0x18002811e  mov     rcx, [rsp+78h+var_28]
0x180028123  xor     rcx, rsp; StackCookie
0x180028126  call    __security_check_cookie
0x18002812b  add     rsp, 60h
0x18002812f  pop     rdi
0x180028130  pop     rsi
0x180028131  pop     rbx
0x180028132  retn
0x180028133  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180028138  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x18002813d  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180028144  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180028149  call    _CxxThrowException
```
