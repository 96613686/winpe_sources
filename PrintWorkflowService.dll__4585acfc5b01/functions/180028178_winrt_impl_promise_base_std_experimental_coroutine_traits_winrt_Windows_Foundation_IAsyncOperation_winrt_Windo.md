# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::unhandled_exception(void)

- ea: `0x180028178`
- end: `0x1800281fb`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `131`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058cf6`
- `0x18005985b`
- `0x18005a861`
- `0x18005ac99`
- `0x18005ade7`
- `0x18005b50a`
- `0x18005c0eb`

## callees

- `0x180004a9c`
- `0x180004ac0`
- `0x1800277b8`
- `0x180028178`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800281aa`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800281aa`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800281b5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800281b5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800281ce`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800281ce`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800281e3`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800281e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::unhandled_exception(
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
0x180028178  mov     [rsp+arg_0], rcx
0x18002817d  push    rbx
0x18002817e  sub     rsp, 30h
0x180028182  mov     rbx, rcx
0x180028185  add     rcx, 48h ; 'H'; SRWLock
0x180028189  mov     [rsp+38h+SRWLock], rcx
0x18002818e  mov     [rsp+38h+arg_10], rcx
0x180028193  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180028198  nop
0x180028199  lea     rcx, [rsp+38h+var_18]
0x18002819e  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x1800281a3  mov     rdx, rax
0x1800281a6  lea     rcx, [rbx+38h]
0x1800281aa  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800281b0  lea     rcx, [rsp+38h+var_18]
0x1800281b5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800281bb  nop
0x1800281bc  xorps   xmm0, xmm0
0x1800281bf  movdqu  [rsp+38h+var_18], xmm0
0x1800281c5  lea     rdx, [rbx+38h]
0x1800281c9  lea     rcx, [rsp+38h+var_18]
0x1800281ce  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800281d4  lea     rax, [rsp+38h+var_18]
0x1800281d9  mov     [rsp+38h+arg_18], rax
0x1800281de  lea     rcx, [rsp+38h+var_18]
0x1800281e3  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800281e9  nop
0x1800281ea  jmp     short $+2
0x1800281ec  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800281f1  add     rsp, 30h
0x1800281f5  pop     rbx
0x1800281f6  jmp     ReleaseSRWLockExclusive_0
```
