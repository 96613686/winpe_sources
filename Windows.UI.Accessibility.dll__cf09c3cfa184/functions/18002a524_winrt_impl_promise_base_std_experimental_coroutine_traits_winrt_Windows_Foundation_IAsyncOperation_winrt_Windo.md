# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x18002a524`
- end: `0x18002a563`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180029480`
- `0x180029594`

## callees

- `0x18002a524`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002a557`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002a557`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a542`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a542`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::rethrow_if_failed(
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
0x18002a524  sub     rsp, 38h
0x18002a528  lea     eax, [rdx-2]
0x18002a52b  cmp     eax, 1
0x18002a52e  ja      short loc_18002A55E
0x18002a530  xorps   xmm0, xmm0
0x18002a533  movdqu  [rsp+38h+var_18], xmm0
0x18002a539  lea     rdx, [rcx+38h]
0x18002a53d  lea     rcx, [rsp+38h+var_18]
0x18002a542  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002a548  lea     rax, [rsp+38h+var_18]
0x18002a54d  mov     [rsp+38h+arg_10], rax
0x18002a552  lea     rcx, [rsp+38h+var_18]
0x18002a557  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002a55d  nop
0x18002a55e  add     rsp, 38h
0x18002a562  retn
```
