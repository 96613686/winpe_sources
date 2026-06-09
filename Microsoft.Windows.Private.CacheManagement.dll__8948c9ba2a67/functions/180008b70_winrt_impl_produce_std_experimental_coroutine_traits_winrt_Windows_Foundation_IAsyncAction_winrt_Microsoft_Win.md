# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::GetResults(void)

- ea: `0x180008b70`
- end: `0x180008be1`
- name: `?GetResults@?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@UEAAHXZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008b70`
- `0x180009bf0`
- `0x18000f0d0`
- `0x1800162aa`
- `0x1800162b0`
- `0x180019c0c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::GetResults(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v1 + 72));
  if ( *(_DWORD *)(v1 + 96) != 1 )
  {
    try
    {
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed();
      winrt::hresult_illegal_method_call::hresult_illegal_method_call((winrt::hresult_illegal_method_call *)pExceptionObject);
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v3 + 80) = *(_DWORD *)winrt::to_hresult(&v5);
      return (unsigned int)v5;
    }
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)(v1 + 72));
  return 0;
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_8], rbx
0x180008b75  push    rdi
0x180008b76  sub     rsp, 40h
0x180008b7a  lea     rdi, [rcx-10h]
0x180008b7e  xor     eax, eax
0x180008b80  test    rcx, rcx
0x180008b83  cmovz   rdi, rax
0x180008b87  lea     rbx, [rdi+48h]
0x180008b8b  mov     [rsp+48h+arg_0], rbx
0x180008b90  mov     rcx, rbx; SRWLock
0x180008b93  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180008b98  nop
0x180008b99  mov     edx, [rdi+60h]
0x180008b9c  cmp     edx, 1
0x180008b9f  jnz     short loc_180008BBC
0x180008ba1  mov     rcx, rbx; SRWLock
0x180008ba4  call    ReleaseSRWLockExclusive_0
0x180008ba9  xor     eax, eax
0x180008bab  jmp     short loc_180008BB1
0x180008bad  mov     eax, dword ptr [rsp+48h+arg_0]
0x180008bb1  mov     rbx, [rsp+48h+arg_8]
0x180008bb6  add     rsp, 40h
0x180008bba  pop     rdi
0x180008bbb  retn
0x180008bbc  mov     rcx, rdi
0x180008bbf  call    ?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)
0x180008bc4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008bc9  call    ??0hresult_illegal_method_call@winrt@@QEAA@XZ; winrt::hresult_illegal_method_call::hresult_illegal_method_call(void)
0x180008bce  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180008bd5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008bda  call    _CxxThrowException
```
