# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::MonitorIdleBackgroundTask(void)

- ea: `0x18003dc10`
- end: `0x18003dd13`
- name: `?MonitorIdleBackgroundTask@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@78@XZ`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18003dd1c`

## callees

- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x18003d990`
- `0x18004106c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003dcbe`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003dcbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::MonitorIdleBackgroundTask(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  char *v5; // rsi
  _QWORD *v6; // rdi

  v4 = operator new(0x120u);
  v5 = (char *)(v4 + 14);
  v4[35] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::MonitorIdleBackgroundTask__ResumeCoro_1;
  *((_DWORD *)v4 + 30) = 65538;
  v6 = v4;
  memset_0(v4, 0, 0x68u);
  v6[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  v6[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[4] = 0;
  v6[5] = 0;
  *((_BYTE *)v6 + 48) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v6[7] = 0;
  v6[8] = 0;
  __ExceptionPtrCreate(v6 + 7);
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 0;
  *((_BYTE *)v6 + 100) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::get_return_object(
    v5 - 112,
    a2);
  v5[160] = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::MonitorIdleBackgroundTask__ResumeCoro_1(v5);
  return a2;
}

```

## disassembly

```asm
0x18003dc10  mov     [rsp+arg_10], rbx
0x18003dc15  mov     [rsp+arg_18], rbp
0x18003dc1a  mov     [rsp+arg_8], rdx
0x18003dc1f  push    rsi
0x18003dc20  push    rdi
0x18003dc21  push    r14
0x18003dc23  sub     rsp, 30h
0x18003dc27  mov     rbp, rdx
0x18003dc2a  mov     rbx, rcx
0x18003dc2d  mov     r14d, 0A0h
0x18003dc33  lea     rcx, [r14+80h]; Size
0x18003dc3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dc3f  mov     [rsp+48h+arg_0], rax
0x18003dc44  lea     rsi, [rax+70h]
0x18003dc48  mov     [rsp+48h+arg_0], rsi
0x18003dc4d  mov     [rsi+r14+8], rbx
0x18003dc52  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__MonitorIdleBackgroundTask$_ResumeCoro$1
0x18003dc59  mov     [rsi], rax
0x18003dc5c  mov     dword ptr [rsi+8], 10002h
0x18003dc63  lea     rdi, [rsi-70h]
0x18003dc67  xor     edx, edx; Val
0x18003dc69  lea     r8d, [r14-38h]; Size
0x18003dc6d  mov     rcx, rdi; void *
0x18003dc70  call    memset_0
0x18003dc75  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x18003dc7c  mov     [rdi+10h], rax
0x18003dc80  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18003dc87  mov     [rdi+18h], rax
0x18003dc8b  lea     rcx, [rdi+8]
0x18003dc8f  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18003dc94  mov     qword ptr [rdi+8], 1
0x18003dc9c  xor     ebx, ebx
0x18003dc9e  mov     [rdi+20h], rbx
0x18003dca2  mov     [rdi+28h], rbx
0x18003dca6  mov     [rdi+30h], bl
0x18003dca9  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x18003dcb0  mov     [rdi], rax
0x18003dcb3  lea     rcx, [rdi+38h]
0x18003dcb7  mov     [rcx], rbx
0x18003dcba  mov     [rcx+8], rbx
0x18003dcbe  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003dcc4  mov     [rdi+48h], rbx
0x18003dcc8  mov     [rdi+50h], rbx
0x18003dccc  mov     [rdi+58h], rbx
0x18003dcd0  xor     eax, eax
0x18003dcd2  mov     [rdi+60h], eax
0x18003dcd5  mov     [rdi+64h], bl
0x18003dcd8  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x18003dcdf  mov     [rdi], rax
0x18003dce2  mov     rdx, rbp
0x18003dce5  mov     rcx, rdi
0x18003dce8  call    ?get_return_object@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA?AUIAsyncAction@Foundation@Windows@3@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::get_return_object(void)
0x18003dced  nop
0x18003dcee  xor     eax, eax
0x18003dcf0  mov     [rsi+r14], al
0x18003dcf4  mov     rcx, rsi
0x18003dcf7  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__MonitorIdleBackgroundTask$_ResumeCoro$1
0x18003dcfc  nop
0x18003dcfd  mov     rax, rbp
0x18003dd00  mov     rbx, [rsp+48h+arg_10]
0x18003dd05  mov     rbp, [rsp+48h+arg_18]
0x18003dd0a  add     rsp, 30h
0x18003dd0e  pop     r14
0x18003dd10  pop     rdi
0x18003dd11  pop     rsi
0x18003dd12  retn
```
