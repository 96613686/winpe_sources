# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::unhandled_exception(void)

- ea: `0x1800271d8`
- end: `0x18002725b`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029639`
- `0x180029eca`

## callees

- `0x180003aac`
- `0x180003ab8`
- `0x180025b2c`
- `0x1800271d8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002720a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002720a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002722e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002722e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027215`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027215`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180027243`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180027243`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::unhandled_exception(
        RTL_SRWLOCK *a1)
{
  const void *v2; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  RTL_SRWLOCK *SRWLock; // [rsp+48h] [rbp+10h]

  SRWLock = a1 + 9;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 9);
  v2 = (const void *)std::current_exception(&v3);
  __ExceptionPtrAssign(&a1[7], v2);
  __ExceptionPtrDestroy(&v3);
  v3 = 0;
  __ExceptionPtrCopy(&v3, &a1[7]);
  try
  {
    __ExceptionPtrRethrow(&v3);
  }
  catch ( winrt::hresult_canceled )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 2);
  }
  catch ( ... )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 3);
  }
  ReleaseSRWLockExclusive_0(SRWLock);
}

```

## disassembly

```asm
0x1800271d8  mov     [rsp+arg_0], rcx
0x1800271dd  push    rbx
0x1800271de  sub     rsp, 30h
0x1800271e2  mov     rbx, rcx
0x1800271e5  add     rcx, 48h ; 'H'; SRWLock
0x1800271e9  mov     [rsp+38h+SRWLock], rcx
0x1800271ee  mov     [rsp+38h+arg_10], rcx
0x1800271f3  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800271f8  nop
0x1800271f9  lea     rcx, [rsp+38h+var_18]
0x1800271fe  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180027203  mov     rdx, rax
0x180027206  lea     rcx, [rbx+38h]
0x18002720a  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180027210  lea     rcx, [rsp+38h+var_18]
0x180027215  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002721b  nop
0x18002721c  xorps   xmm0, xmm0
0x18002721f  movdqu  [rsp+38h+var_18], xmm0
0x180027225  lea     rdx, [rbx+38h]
0x180027229  lea     rcx, [rsp+38h+var_18]
0x18002722e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180027234  lea     rax, [rsp+38h+var_18]
0x180027239  mov     [rsp+38h+arg_18], rax
0x18002723e  lea     rcx, [rsp+38h+var_18]
0x180027243  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180027249  nop
0x18002724a  jmp     short $+2
0x18002724c  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180027251  add     rsp, 30h
0x180027255  pop     rbx
0x180027256  jmp     ReleaseSRWLockExclusive_0
```
