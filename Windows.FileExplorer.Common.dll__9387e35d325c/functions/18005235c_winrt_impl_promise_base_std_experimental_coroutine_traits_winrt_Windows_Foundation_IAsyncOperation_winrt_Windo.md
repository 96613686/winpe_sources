# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::Windows::Internal::implementation::MicrosoftGraphRecentItemsManagerExtension *,winrt::Windows::Foundation::Uri,winrt::hstring,uint,uint>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::unhandled_exception(void)

- ea: `0x18005235c`
- end: `0x1800523df`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUMicrosoftGraphRecentItemsManagerExtension@implementation@Internal@34@UUri@234@Uhstring@4@II@experimental@std@@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086173`
- `0x1800864c4`
- `0x1800866c2`
- `0x180086986`

## callees

- `0x180038a8e`
- `0x180038a9a`
- `0x180051638`
- `0x18005235c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800523c7`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800523c7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800523b2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800523b2`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18005238e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18005238e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180052399`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180052399`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::Windows::Internal::implementation::MicrosoftGraphRecentItemsManagerExtension *,winrt::Windows::Foundation::Uri,winrt::hstring,unsigned int,unsigned int>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::unhandled_exception(
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
0x18005235c  mov     [rsp+arg_0], rcx
0x180052361  push    rbx
0x180052362  sub     rsp, 30h
0x180052366  mov     rbx, rcx
0x180052369  add     rcx, 48h ; 'H'; SRWLock
0x18005236d  mov     [rsp+38h+SRWLock], rcx
0x180052372  mov     [rsp+38h+arg_10], rcx
0x180052377  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18005237c  nop
0x18005237d  lea     rcx, [rsp+38h+var_18]
0x180052382  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180052387  mov     rdx, rax
0x18005238a  lea     rcx, [rbx+38h]
0x18005238e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180052394  lea     rcx, [rsp+38h+var_18]
0x180052399  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18005239f  nop
0x1800523a0  xorps   xmm0, xmm0
0x1800523a3  movdqu  [rsp+38h+var_18], xmm0
0x1800523a9  lea     rdx, [rbx+38h]
0x1800523ad  lea     rcx, [rsp+38h+var_18]
0x1800523b2  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800523b8  lea     rax, [rsp+38h+var_18]
0x1800523bd  mov     [rsp+38h+arg_18], rax
0x1800523c2  lea     rcx, [rsp+38h+var_18]
0x1800523c7  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800523cd  nop
0x1800523ce  jmp     short $+2
0x1800523d0  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800523d5  add     rsp, 30h
0x1800523d9  pop     rbx
0x1800523da  jmp     ReleaseSRWLockExclusive_0
```
