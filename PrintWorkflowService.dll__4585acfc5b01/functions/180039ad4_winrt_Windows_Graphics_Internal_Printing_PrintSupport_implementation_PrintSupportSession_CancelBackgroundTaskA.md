# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::CancelBackgroundTaskAsync(void)

- ea: `0x180039ad4`
- end: `0x180039bd7`
- name: `?CancelBackgroundTaskAsync@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@78@XZ`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180039be0`

## callees

- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x1800398f0`
- `0x18004106c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180039b82`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180039b82`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::CancelBackgroundTaskAsync(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  char *v5; // rsi
  _QWORD *v6; // rdi

  v4 = operator new(0xF0u);
  v5 = (char *)(v4 + 14);
  v4[29] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::CancelBackgroundTaskAsync__ResumeCoro_1;
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
  v5[112] = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::CancelBackgroundTaskAsync__ResumeCoro_1(v5);
  return a2;
}

```

## disassembly

```asm
0x180039ad4  mov     [rsp+arg_10], rbx
0x180039ad9  mov     [rsp+arg_18], rbp
0x180039ade  mov     [rsp+arg_8], rdx
0x180039ae3  push    rsi
0x180039ae4  push    rdi
0x180039ae5  push    r14
0x180039ae7  sub     rsp, 30h
0x180039aeb  mov     rbp, rdx
0x180039aee  mov     rbx, rcx
0x180039af1  mov     r14d, 70h ; 'p'
0x180039af7  lea     rcx, [r14+80h]; Size
0x180039afe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039b03  mov     [rsp+48h+arg_0], rax
0x180039b08  lea     rsi, [r14+rax]
0x180039b0c  mov     [rsp+48h+arg_0], rsi
0x180039b11  mov     [rsi+r14+8], rbx
0x180039b16  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__CancelBackgroundTaskAsync$_ResumeCoro$1
0x180039b1d  mov     [rsi], rax
0x180039b20  mov     dword ptr [rsi+8], 10002h
0x180039b27  lea     rdi, [rsi-70h]
0x180039b2b  xor     edx, edx; Val
0x180039b2d  lea     r8d, [r14-8]; Size
0x180039b31  mov     rcx, rdi; void *
0x180039b34  call    memset_0
0x180039b39  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x180039b40  mov     [rdi+10h], rax
0x180039b44  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180039b4b  mov     [rdi+18h], rax
0x180039b4f  lea     rcx, [rdi+8]
0x180039b53  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180039b58  mov     qword ptr [rdi+8], 1
0x180039b60  xor     ebx, ebx
0x180039b62  mov     [rdi+20h], rbx
0x180039b66  mov     [rdi+28h], rbx
0x180039b6a  mov     [rdi+30h], bl
0x180039b6d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180039b74  mov     [rdi], rax
0x180039b77  lea     rcx, [rdi+38h]
0x180039b7b  mov     [rcx], rbx
0x180039b7e  mov     [rcx+8], rbx
0x180039b82  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180039b88  mov     [rdi+48h], rbx
0x180039b8c  mov     [rdi+50h], rbx
0x180039b90  mov     [rdi+58h], rbx
0x180039b94  xor     eax, eax
0x180039b96  mov     [rdi+60h], eax
0x180039b99  mov     [rdi+64h], bl
0x180039b9c  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180039ba3  mov     [rdi], rax
0x180039ba6  mov     rdx, rbp
0x180039ba9  mov     rcx, rdi
0x180039bac  call    ?get_return_object@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA?AUIAsyncAction@Foundation@Windows@3@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::get_return_object(void)
0x180039bb1  nop
0x180039bb2  xor     eax, eax
0x180039bb4  mov     [rsi+r14], al
0x180039bb8  mov     rcx, rsi
0x180039bbb  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__CancelBackgroundTaskAsync$_ResumeCoro$1
0x180039bc0  nop
0x180039bc1  mov     rax, rbp
0x180039bc4  mov     rbx, [rsp+48h+arg_10]
0x180039bc9  mov     rbp, [rsp+48h+arg_18]
0x180039bce  add     rsp, 30h
0x180039bd2  pop     r14
0x180039bd4  pop     rdi
0x180039bd5  pop     rsi
0x180039bd6  retn
```
