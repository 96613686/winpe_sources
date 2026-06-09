# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::Windows::Internal::implementation::MicrosoftGraphRecentItemsManagerExtension *,winrt::Windows::Foundation::Uri,winrt::hstring,uint,uint>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x180030a50`
- end: `0x180030a8f`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUMicrosoftGraphRecentItemsManagerExtension@implementation@Internal@34@UUri@234@Uhstring@4@II@experimental@std@@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `63`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026c9c`
- `0x1800312dc`
- `0x18004c850`

## callees

- `0x180030a50`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180030a83`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180030a83`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030a6e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030a6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::Windows::Internal::implementation::MicrosoftGraphRecentItemsManagerExtension *,winrt::Windows::Foundation::Uri,winrt::hstring,unsigned int,unsigned int>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::rethrow_if_failed(
        __int64 a1,
        int a2)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( (unsigned int)(a2 - 2) <= 1 )
  {
    v2 = 0;
    __ExceptionPtrCopy(&v2, (const void *)(a1 + 56));
    __ExceptionPtrRethrow(&v2);
  }
}

```

## disassembly

```asm
0x180030a50  sub     rsp, 38h
0x180030a54  lea     eax, [rdx-2]
0x180030a57  cmp     eax, 1
0x180030a5a  ja      short loc_180030A8A
0x180030a5c  xorps   xmm0, xmm0
0x180030a5f  movdqu  [rsp+38h+var_18], xmm0
0x180030a65  lea     rdx, [rcx+38h]
0x180030a69  lea     rcx, [rsp+38h+var_18]
0x180030a6e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180030a74  lea     rax, [rsp+38h+var_18]
0x180030a79  mov     [rsp+38h+arg_10], rax
0x180030a7e  lea     rcx, [rsp+38h+var_18]
0x180030a83  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180030a89  nop
0x180030a8a  add     rsp, 38h
0x180030a8e  retn
```
