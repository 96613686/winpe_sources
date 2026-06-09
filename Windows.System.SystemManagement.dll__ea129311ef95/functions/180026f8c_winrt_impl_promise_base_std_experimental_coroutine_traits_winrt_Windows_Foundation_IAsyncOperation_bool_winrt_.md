# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x180026f8c`
- end: `0x180026fcb`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180020b58`
- `0x180022034`

## callees

- `0x180026f8c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180026faa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180026faa`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180026fbf`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180026fbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::rethrow_if_failed(
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
0x180026f8c  sub     rsp, 38h
0x180026f90  lea     eax, [rdx-2]
0x180026f93  cmp     eax, 1
0x180026f96  ja      short loc_180026FC6
0x180026f98  xorps   xmm0, xmm0
0x180026f9b  movdqu  [rsp+38h+var_18], xmm0
0x180026fa1  lea     rdx, [rcx+38h]
0x180026fa5  lea     rcx, [rsp+38h+var_18]
0x180026faa  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180026fb0  lea     rax, [rsp+38h+var_18]
0x180026fb5  mov     [rsp+38h+arg_10], rax
0x180026fba  lea     rcx, [rsp+38h+var_18]
0x180026fbf  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180026fc5  nop
0x180026fc6  add     rsp, 38h
0x180026fca  retn
```
