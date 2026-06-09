# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x180028064`
- end: `0x1800280a3`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800264b8`
- `0x180026a7c`
- `0x18003b9ac`
- `0x18003ba24`

## callees

- `0x180028064`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028082`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180028082`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028097`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180028097`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed(
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
0x180028064  sub     rsp, 38h
0x180028068  lea     eax, [rdx-2]
0x18002806b  cmp     eax, 1
0x18002806e  ja      short loc_18002809E
0x180028070  xorps   xmm0, xmm0
0x180028073  movdqu  [rsp+38h+var_18], xmm0
0x180028079  lea     rdx, [rcx+38h]
0x18002807d  lea     rcx, [rsp+38h+var_18]
0x180028082  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180028088  lea     rax, [rsp+38h+var_18]
0x18002808d  mov     [rsp+38h+arg_10], rax
0x180028092  lea     rcx, [rsp+38h+var_18]
0x180028097  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002809d  nop
0x18002809e  add     rsp, 38h
0x1800280a2  retn
```
