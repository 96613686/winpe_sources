# winrt::vector_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload>::InsertAt(uint,winrt::Microsoft::Windows::Workloads::Workload const &)

- ea: `0x180029820`
- end: `0x1800299a6`
- name: `?InsertAt@?$vector_base@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWorkload@Workloads@Windows@Microsoft@3@@winrt@@QEAAXIAEBUWorkload@Workloads@Windows@Microsoft@2@@Z`
- size: `390`
- prototype: `_QWORD *__fastcall(volatile signed __int32 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180027fd0`

## callees

- `0x1800040a0`
- `0x180010200`
- `0x180029820`
- `0x18002a740`
- `0x180034ef0`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::vector_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload>::InsertAt(
        volatile signed __int32 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // r14
  _QWORD *result; // rax
  __int64 *v5; // rbx
  __int64 *v6; // rsi
  _QWORD *v7; // rcx
  __int64 *v8; // rdi
  __int64 v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h]
  _QWORD *v12; // [rsp+40h] [rbp-28h] BYREF

  v3 = (__int64)(a1 + 2);
  if ( !a1 )
    v3 = 48;
  if ( (unsigned int)a2 > (unsigned __int64)((__int64)(*(_QWORD *)(v3 + 8) - *(_QWORD *)v3) >> 3) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement(a1);
  result = *(_QWORD **)v3;
  v5 = *(__int64 **)(v3 + 8);
  v6 = (__int64 *)(*(_QWORD *)v3 + 8LL * (unsigned int)a2);
  if ( v5 == *(__int64 **)(v3 + 16) )
  {
    _mm_lfence();
    return (_QWORD *)std::vector<winrt::Microsoft::Windows::Workloads::Workload>::_Emplace_reallocate<winrt::Microsoft::Windows::Workloads::Workload const &>(
                       v3,
                       *(_QWORD *)v3 + 8LL * (unsigned int)a2,
                       a3);
  }
  else
  {
    v7 = (_QWORD *)*a3;
    if ( v6 == v5 )
    {
      *v5 = (__int64)v7;
      if ( v7 )
        result = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *, _QWORD))(*v7 + 8LL))(
                             v7,
                             a2,
                             a3,
                             (unsigned int)a2);
      *(_QWORD *)(v3 + 8) += 8LL;
    }
    else
    {
      v11 = v3;
      v12 = v7;
      if ( v7 )
        (*(void (__fastcall **)(_QWORD *, __int64, _QWORD *, _QWORD))(*v7 + 8LL))(v7, a2, a3, (unsigned int)a2);
      v8 = v5 - 1;
      *v5 = *(v5 - 1);
      *(v5 - 1) = 0;
      *(_QWORD *)(v3 + 8) += 8LL;
      if ( v5 - 1 != v6 )
      {
        do
        {
          if ( --v5 != --v8 )
          {
            if ( *v5 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
            v9 = *v8;
            *v8 = 0;
            *v5 = v9;
          }
        }
        while ( v8 != v6 );
      }
      result = &v12;
      if ( v6 == (__int64 *)&v12 )
      {
        if ( v12 )
          return (_QWORD *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
      }
      else
      {
        if ( *v6 )
        {
          _mm_lfence();
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
        }
        result = v12;
        *v6 = (__int64)v12;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029820  push    r14
0x180029822  sub     rsp, 60h
0x180029826  mov     rax, cs:__security_cookie
0x18002982d  xor     rax, rsp
0x180029830  mov     [rsp+68h+var_20], rax
0x180029835  test    rcx, rcx
0x180029838  mov     r9d, edx
0x18002983b  mov     eax, 30h ; '0'
0x180029840  lea     r14, [rcx+8]
0x180029844  cmovz   r14, rax
0x180029848  mov     rax, [r14+8]
0x18002984c  sub     rax, [r14]
0x18002984f  sar     rax, 3
0x180029853  cmp     r9, rax
0x180029856  ja      loc_18002998A
0x18002985c  mov     [rsp+68h+arg_8], rbx
0x180029861  mov     [rsp+68h+var_10], rsi
0x180029866  lock inc dword ptr [rcx]
0x180029869  mov     rax, [r14]
0x18002986c  mov     rbx, [r14+8]
0x180029870  lea     rsi, [rax+r9*8]
0x180029874  cmp     rbx, [r14+10h]
0x180029878  jz      loc_18002995E
0x18002987e  mov     rcx, [r8]
0x180029881  cmp     rsi, rbx
0x180029884  jnz     short loc_1800298A5
0x180029886  mov     [rbx], rcx
0x180029889  test    rcx, rcx
0x18002988c  jz      short loc_18002989B
0x18002988e  mov     rax, [rcx]
0x180029891  mov     rax, [rax+8]
0x180029895  call    cs:__guard_dispatch_icall_fptr
0x18002989b  add     qword ptr [r14+8], 8
0x1800298a0  jmp     loc_18002996C
0x1800298a5  mov     [rsp+68h+arg_18], rbp
0x1800298ad  mov     [rsp+68h+var_18], rdi
0x1800298b2  mov     [rsp+68h+var_30], r14
0x1800298b7  mov     [rsp+68h+var_28], rcx
0x1800298bc  test    rcx, rcx
0x1800298bf  jz      short loc_1800298CE
0x1800298c1  mov     rax, [rcx]
0x1800298c4  mov     rax, [rax+8]
0x1800298c8  call    cs:__guard_dispatch_icall_fptr
0x1800298ce  mov     rax, [rbx-8]
0x1800298d2  lea     rdi, [rbx-8]
0x1800298d6  xor     ebp, ebp
0x1800298d8  mov     [rbx], rax
0x1800298db  mov     [rdi], rbp
0x1800298de  add     qword ptr [r14+8], 8
0x1800298e3  cmp     rdi, rsi
0x1800298e6  jz      short loc_180029918
0x1800298e8  nop     dword ptr [rax+rax+00000000h]
0x1800298f0  sub     rdi, 8
0x1800298f4  sub     rbx, 8
0x1800298f8  cmp     rbx, rdi
0x1800298fb  jz      short loc_180029913
0x1800298fd  cmp     [rbx], rbp
0x180029900  jz      short loc_18002990A
0x180029902  mov     rcx, rbx
0x180029905  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002990a  mov     rax, [rdi]
0x18002990d  mov     [rdi], rbp
0x180029910  mov     [rbx], rax
0x180029913  cmp     rdi, rsi
0x180029916  jnz     short loc_1800298F0
0x180029918  mov     rdi, [rsp+68h+var_18]
0x18002991d  lea     rax, [rsp+68h+var_28]
0x180029922  mov     rbp, [rsp+68h+arg_18]
0x18002992a  cmp     rsi, rax
0x18002992d  jz      short loc_18002994A
0x18002992f  cmp     qword ptr [rsi], 0
0x180029933  jz      short loc_180029940
0x180029935  lfence
0x180029938  mov     rcx, rsi
0x18002993b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029940  mov     rax, [rsp+68h+var_28]
0x180029945  mov     [rsi], rax
0x180029948  jmp     short loc_18002996C
0x18002994a  cmp     [rsp+68h+var_28], 0
0x180029950  jz      short loc_18002996C
0x180029952  lea     rcx, [rsp+68h+var_28]
0x180029957  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002995c  jmp     short loc_18002996C
0x18002995e  lfence
0x180029961  mov     rdx, rsi
0x180029964  mov     rcx, r14
0x180029967  call    ??$_Emplace_reallocate@AEBUWorkload@Workloads@Windows@Microsoft@winrt@@@?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@AEAAPEAUWorkload@Workloads@Windows@Microsoft@winrt@@QEAU23456@AEBU23456@@Z; std::vector<winrt::Microsoft::Windows::Workloads::Workload>::_Emplace_reallocate<winrt::Microsoft::Windows::Workloads::Workload const &>(winrt::Microsoft::Windows::Workloads::Workload * const,winrt::Microsoft::Windows::Workloads::Workload const &)
0x18002996c  mov     rbx, [rsp+68h+arg_8]
0x180029971  mov     rsi, [rsp+68h+var_10]
0x180029976  mov     rcx, [rsp+68h+var_20]
0x18002997b  xor     rcx, rsp; StackCookie
0x18002997e  call    __security_check_cookie
0x180029983  add     rsp, 60h
0x180029987  pop     r14
0x180029989  retn
0x18002998a  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002998f  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x180029994  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18002999b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800299a0  call    _CxxThrowException
```
