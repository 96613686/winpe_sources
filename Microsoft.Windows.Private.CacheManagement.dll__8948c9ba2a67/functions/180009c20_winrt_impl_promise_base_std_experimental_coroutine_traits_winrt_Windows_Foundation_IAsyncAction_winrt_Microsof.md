# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::ErrorCode(void)

- ea: `0x180009c20`
- end: `0x180009c87`
- name: `?ErrorCode@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAA?AUhresult@3@XZ`
- size: `103`
- prototype: `_DWORD *__fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800089b0`

## callees

- `0x180009c20`
- `0x180012ae0`
- `0x180012b00`
- `0x1800162aa`
- `0x1800162b0`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::ErrorCode(
        __int64 a1,
        _DWORD *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 *v6; // rdx
  __int64 v7; // [rsp+0h] [rbp-48h] BYREF
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+58h] [rbp+10h]

  v4 = (RTL_SRWLOCK *)(a1 + 72);
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( (unsigned int)(*(_DWORD *)(a1 + 96) - 2) <= 1 )
  {
    std::exception_ptr::exception_ptr((std::exception_ptr *)v8, (const struct std::exception_ptr *)(a1 + 56));
    try
    {
      std::rethrow_exception();
    }
    catch ( ... )
    {
      v6 = &v7;
      winrt::to_hresult(v6[11]);
      return (_DWORD *)v9;
    }
  }
  *a2 = 0;
  ReleaseSRWLockExclusive_0(v4);
  return a2;
}

```

## disassembly

```asm
0x180009c20  mov     [rsp+arg_8], rdx
0x180009c25  push    rbx
0x180009c26  push    rsi
0x180009c27  push    rdi
0x180009c28  sub     rsp, 30h
0x180009c2c  mov     rdi, rdx
0x180009c2f  mov     rsi, rcx
0x180009c32  lea     rbx, [rcx+48h]
0x180009c36  mov     [rsp+48h+arg_0], rbx
0x180009c3b  mov     rcx, rbx; SRWLock
0x180009c3e  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180009c43  nop
0x180009c44  mov     eax, [rsi+60h]
0x180009c47  add     eax, 0FFFFFFFEh
0x180009c4a  cmp     eax, 1
0x180009c4d  jbe     short loc_180009C6F
0x180009c4f  mov     dword ptr [rdi], 0
0x180009c55  mov     rcx, rbx; SRWLock
0x180009c58  call    ReleaseSRWLockExclusive_0
0x180009c5d  mov     rax, rdi
0x180009c60  jmp     short loc_180009C67
0x180009c62  mov     rax, [rsp+48h+arg_8]
0x180009c67  add     rsp, 30h
0x180009c6b  pop     rdi
0x180009c6c  pop     rsi
0x180009c6d  pop     rbx
0x180009c6e  retn
0x180009c6f  lea     rdx, [rsi+38h]; struct std::exception_ptr *
0x180009c73  lea     rcx, [rsp+48h+var_28]; this
0x180009c78  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180009c7d  mov     rcx, rax
0x180009c80  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
