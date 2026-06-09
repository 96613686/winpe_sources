# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::unhandled_exception(void)

- ea: `0x18002a5a0`
- end: `0x18002a623`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033d2d`

## callees

- `0x180004601`
- `0x18000460d`
- `0x18002a1fc`
- `0x18002a5a0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002a60b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002a60b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a5f6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a5f6`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002a5d2`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18002a5d2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002a5dd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002a5dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::unhandled_exception(
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
0x18002a5a0  mov     [rsp+arg_0], rcx
0x18002a5a5  push    rbx
0x18002a5a6  sub     rsp, 30h
0x18002a5aa  mov     rbx, rcx
0x18002a5ad  add     rcx, 48h ; 'H'; SRWLock
0x18002a5b1  mov     [rsp+38h+SRWLock], rcx
0x18002a5b6  mov     [rsp+38h+arg_10], rcx
0x18002a5bb  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002a5c0  nop
0x18002a5c1  lea     rcx, [rsp+38h+var_18]
0x18002a5c6  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x18002a5cb  mov     rdx, rax
0x18002a5ce  lea     rcx, [rbx+38h]
0x18002a5d2  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002a5d8  lea     rcx, [rsp+38h+var_18]
0x18002a5dd  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002a5e3  nop
0x18002a5e4  xorps   xmm0, xmm0
0x18002a5e7  movdqu  [rsp+38h+var_18], xmm0
0x18002a5ed  lea     rdx, [rbx+38h]
0x18002a5f1  lea     rcx, [rsp+38h+var_18]
0x18002a5f6  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002a5fc  lea     rax, [rsp+38h+var_18]
0x18002a601  mov     [rsp+38h+arg_18], rax
0x18002a606  lea     rcx, [rsp+38h+var_18]
0x18002a60b  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002a611  nop
0x18002a612  jmp     short $+2
0x18002a614  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18002a619  add     rsp, 30h
0x18002a61d  pop     rbx
0x18002a61e  jmp     ReleaseSRWLockExclusive_0
```
