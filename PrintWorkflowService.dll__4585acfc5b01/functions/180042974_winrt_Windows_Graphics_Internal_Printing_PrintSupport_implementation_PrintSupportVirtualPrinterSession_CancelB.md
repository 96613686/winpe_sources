# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CancelBackgroundTaskAsync(void)

- ea: `0x180042974`
- end: `0x180042a85`
- name: `?CancelBackgroundTaskAsync@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AUIAsyncAction@Foundation@78@XZ`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180042a8c`

## callees

- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x1800097ec`
- `0x180012940`
- `0x1800427c0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180042a23`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180042a23`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CancelBackgroundTaskAsync(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  char *v5; // r14
  _QWORD *v6; // rsi
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF

  v4 = operator new(0xF0u);
  v5 = (char *)(v4 + 14);
  v4[29] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CancelBackgroundTaskAsync__ResumeCoro_1;
  *((_DWORD *)v4 + 30) = 65538;
  v6 = v4;
  memset_0(v4, 0, 0x68u);
  v6[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  v6[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[4] = 0;
  v6[5] = 0;
  *((_BYTE *)v6 + 48) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v6[7] = 0;
  v6[8] = 0;
  __ExceptionPtrCreate(v6 + 7);
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 0;
  *((_BYTE *)v6 + 100) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  *a2 = v6 + 2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a2);
  v8 = 0;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v8);
  v5[112] = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CancelBackgroundTaskAsync__ResumeCoro_1(v5);
  return a2;
}

```

## disassembly

```asm
0x180042974  mov     [rsp+arg_18], rbx
0x180042979  mov     [rsp+arg_8], rdx
0x18004297e  push    rbp
0x18004297f  push    rsi
0x180042980  push    rdi
0x180042981  push    r14
0x180042983  push    r15
0x180042985  sub     rsp, 30h
0x180042989  mov     r15, rdx
0x18004298c  mov     rbx, rcx
0x18004298f  mov     ebp, 70h ; 'p'
0x180042994  lea     rcx, [rbp+80h]; Size
0x18004299b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800429a0  mov     [rsp+58h+arg_0], rax
0x1800429a5  lea     r14, [rax+rbp]
0x1800429a9  mov     [rsp+58h+arg_0], r14
0x1800429ae  mov     [r14+rbp+8], rbx
0x1800429b3  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__CancelBackgroundTaskAsync$_ResumeCoro$1
0x1800429ba  mov     [r14], rax
0x1800429bd  mov     dword ptr [r14+8], 10002h
0x1800429c5  lea     rsi, [r14-70h]
0x1800429c9  xor     edx, edx; Val
0x1800429cb  lea     r8d, [rbp-8]; Size
0x1800429cf  mov     rcx, rsi; void *
0x1800429d2  call    memset_0
0x1800429d7  lea     rdi, [rsi+10h]
0x1800429db  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x1800429e2  mov     [rdi], rax
0x1800429e5  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x1800429ec  mov     [rdi+8], rax
0x1800429f0  lea     rcx, [rsi+8]
0x1800429f4  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800429f9  mov     qword ptr [rsi+8], 1
0x180042a01  xor     ebx, ebx
0x180042a03  mov     [rsi+20h], rbx
0x180042a07  mov     [rsi+28h], rbx
0x180042a0b  mov     [rsi+30h], bl
0x180042a0e  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180042a15  mov     [rsi], rax
0x180042a18  lea     rcx, [rsi+38h]
0x180042a1c  mov     [rcx], rbx
0x180042a1f  mov     [rcx+8], rbx
0x180042a23  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180042a29  mov     [rsi+48h], rbx
0x180042a2d  mov     [rsi+50h], rbx
0x180042a31  mov     [rsi+58h], rbx
0x180042a35  xor     eax, eax
0x180042a37  mov     [rsi+60h], eax
0x180042a3a  mov     [rsi+64h], bl
0x180042a3d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180042a44  mov     [rsi], rax
0x180042a47  mov     [r15], rdi
0x180042a4a  mov     rcx, r15
0x180042a4d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042a52  mov     [rsp+58h+arg_10], rbx
0x180042a57  lea     rcx, [rsp+58h+arg_10]; this
0x180042a5c  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180042a61  nop
0x180042a62  xor     eax, eax
0x180042a64  mov     [r14+rbp], al
0x180042a68  mov     rcx, r14
0x180042a6b  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__CancelBackgroundTaskAsync$_ResumeCoro$1
0x180042a70  nop
0x180042a71  mov     rax, r15
0x180042a74  mov     rbx, [rsp+58h+arg_18]
0x180042a79  add     rsp, 30h
0x180042a7d  pop     r15
0x180042a7f  pop     r14
0x180042a81  pop     rdi
0x180042a82  pop     rsi
0x180042a83  pop     rbp
0x180042a84  retn
```
