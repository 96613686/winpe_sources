# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::HandleJobIssueAsync(void)

- ea: `0x18003c504`
- end: `0x18003c618`
- name: `?HandleJobIssueAsync@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AU?$IAsyncOperation@_N@Foundation@78@XZ`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004a210`

## callees

- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x1800097ec`
- `0x180012940`
- `0x18003c2d0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003c5b3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003c5b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::HandleJobIssueAsync(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  char *v5; // r14
  _QWORD *v6; // rsi
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF

  v4 = operator new(0xE0u);
  v5 = (char *)(v4 + 14);
  v4[27] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::HandleJobIssueAsync__ResumeCoro_1;
  *((_DWORD *)v4 + 30) = 65538;
  v6 = v4;
  memset_0(v4, 0, 0x70u);
  v6[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>>::`vftable';
  v6[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[4] = 0;
  v6[5] = 0;
  *((_BYTE *)v6 + 48) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::`vftable';
  v6[7] = 0;
  v6[8] = 0;
  __ExceptionPtrCreate(v6 + 7);
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 0;
  *((_BYTE *)v6 + 100) = 0;
  *v6 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable';
  *((_BYTE *)v6 + 104) = 0;
  *a2 = v6 + 2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a2);
  v8 = 0;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v8);
  v5[96] = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::HandleJobIssueAsync__ResumeCoro_1(v5);
  return a2;
}

```

## disassembly

```asm
0x18003c504  mov     [rsp+arg_18], rbx
0x18003c509  mov     [rsp+arg_8], rdx
0x18003c50e  push    rbp
0x18003c50f  push    rsi
0x18003c510  push    rdi
0x18003c511  push    r14
0x18003c513  push    r15
0x18003c515  sub     rsp, 30h
0x18003c519  mov     r15, rdx
0x18003c51c  mov     rbx, rcx
0x18003c51f  mov     ebp, 60h ; '`'
0x18003c524  lea     rcx, [rbp+80h]; Size
0x18003c52b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c530  mov     [rsp+58h+arg_0], rax
0x18003c535  lea     r8d, [rbp+10h]; Size
0x18003c539  lea     r14, [r8+rax]
0x18003c53d  mov     [rsp+58h+arg_0], r14
0x18003c542  mov     [r14+rbp+8], rbx
0x18003c547  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__HandleJobIssueAsync$_ResumeCoro$1
0x18003c54e  mov     [r14], rax
0x18003c551  mov     dword ptr [r14+8], 10002h
0x18003c559  lea     rsi, [r14-70h]
0x18003c55d  xor     edx, edx; Val
0x18003c55f  mov     rcx, rsi; void *
0x18003c562  call    memset_0
0x18003c567  lea     rdi, [rsi+10h]
0x18003c56b  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>>::`vftable'
0x18003c572  mov     [rdi], rax
0x18003c575  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18003c57c  mov     [rdi+8], rax
0x18003c580  lea     rcx, [rsi+8]
0x18003c584  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18003c589  mov     qword ptr [rsi+8], 1
0x18003c591  xor     ebx, ebx
0x18003c593  mov     [rsi+20h], rbx
0x18003c597  mov     [rsi+28h], rbx
0x18003c59b  mov     [rsi+30h], bl
0x18003c59e  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::`vftable'
0x18003c5a5  mov     [rsi], rax
0x18003c5a8  lea     rcx, [rsi+38h]
0x18003c5ac  mov     [rcx], rbx
0x18003c5af  mov     [rcx+8], rbx
0x18003c5b3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003c5b9  mov     [rsi+48h], rbx
0x18003c5bd  mov     [rsi+50h], rbx
0x18003c5c1  mov     [rsi+58h], rbx
0x18003c5c5  xor     eax, eax
0x18003c5c7  mov     [rsi+60h], eax
0x18003c5ca  mov     [rsi+64h], bl
0x18003c5cd  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable'
0x18003c5d4  mov     [rsi], rax
0x18003c5d7  mov     [rsi+68h], bl
0x18003c5da  mov     [r15], rdi
0x18003c5dd  mov     rcx, r15
0x18003c5e0  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003c5e5  mov     [rsp+58h+arg_10], rbx
0x18003c5ea  lea     rcx, [rsp+58h+arg_10]; this
0x18003c5ef  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18003c5f4  nop
0x18003c5f5  xor     eax, eax
0x18003c5f7  mov     [r14+rbp], al
0x18003c5fb  mov     rcx, r14
0x18003c5fe  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportSession__HandleJobIssueAsync$_ResumeCoro$1
0x18003c603  nop
0x18003c604  mov     rax, r15
0x18003c607  mov     rbx, [rsp+58h+arg_18]
0x18003c60c  add     rsp, 30h
0x18003c610  pop     r15
0x18003c612  pop     r14
0x18003c614  pop     rdi
0x18003c615  pop     rsi
0x18003c616  pop     rbp
0x18003c617  retn
```
