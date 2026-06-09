# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::LaunchUIForPdlDataAsync(void)

- ea: `0x180044974`
- end: `0x180044a88`
- name: `?LaunchUIForPdlDataAsync@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AU?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@78@XZ`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004b750`

## callees

- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x1800097ec`
- `0x180012940`
- `0x180044810`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044a23`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044a23`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::LaunchUIForPdlDataAsync(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  char *v5; // r14
  _QWORD *v6; // rsi
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF

  v4 = operator new(0xC0u);
  v5 = (char *)(v4 + 14);
  v4[23] = a1;
  v4[14] = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::LaunchUIForPdlDataAsync__ResumeCoro_1;
  *((_DWORD *)v4 + 30) = 65538;
  v6 = v4;
  memset_0(v4, 0, 0x70u);
  v6[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>>::`vftable';
  v6[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[4] = 0;
  v6[5] = 0;
  *((_BYTE *)v6 + 48) = 0;
  *v6 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::`vftable';
  v6[7] = 0;
  v6[8] = 0;
  __ExceptionPtrCreate(v6 + 7);
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 0;
  *((_BYTE *)v6 + 100) = 0;
  *v6 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable';
  *((_DWORD *)v6 + 26) = 0;
  *a2 = v6 + 2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a2);
  v8 = 0;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v8);
  v5[64] = 0;
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::LaunchUIForPdlDataAsync__ResumeCoro_1(v5);
  return a2;
}

```

## disassembly

```asm
0x180044974  mov     [rsp+arg_18], rbx
0x180044979  mov     [rsp+arg_8], rdx
0x18004497e  push    rbp
0x18004497f  push    rsi
0x180044980  push    rdi
0x180044981  push    r14
0x180044983  push    r15
0x180044985  sub     rsp, 30h
0x180044989  mov     r15, rdx
0x18004498c  mov     rbx, rcx
0x18004498f  mov     ebp, 40h ; '@'
0x180044994  lea     rcx, [rbp+80h]; Size
0x18004499b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800449a0  mov     [rsp+58h+arg_0], rax
0x1800449a5  lea     r8d, [rbp+30h]; Size
0x1800449a9  lea     r14, [r8+rax]
0x1800449ad  mov     [rsp+58h+arg_0], r14
0x1800449b2  mov     [r14+rbp+8], rbx
0x1800449b7  lea     rax, winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__LaunchUIForPdlDataAsync$_ResumeCoro$1
0x1800449be  mov     [r14], rax
0x1800449c1  mov     dword ptr [r14+8], 10002h
0x1800449c9  lea     rsi, [r14-70h]
0x1800449cd  xor     edx, edx; Val
0x1800449cf  mov     rcx, rsi; void *
0x1800449d2  call    memset_0
0x1800449d7  lea     rdi, [rsi+10h]
0x1800449db  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>>::`vftable'
0x1800449e2  mov     [rdi], rax
0x1800449e5  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x1800449ec  mov     [rdi+8], rax
0x1800449f0  lea     rcx, [rsi+8]
0x1800449f4  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800449f9  mov     qword ptr [rsi+8], 1
0x180044a01  xor     ebx, ebx
0x180044a03  mov     [rsi+20h], rbx
0x180044a07  mov     [rsi+28h], rbx
0x180044a0b  mov     [rsi+30h], bl
0x180044a0e  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::`vftable'
0x180044a15  mov     [rsi], rax
0x180044a18  lea     rcx, [rsi+38h]
0x180044a1c  mov     [rcx], rbx
0x180044a1f  mov     [rcx+8], rbx
0x180044a23  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180044a29  mov     [rsi+48h], rbx
0x180044a2d  mov     [rsi+50h], rbx
0x180044a31  mov     [rsi+58h], rbx
0x180044a35  xor     eax, eax
0x180044a37  mov     [rsi+60h], eax
0x180044a3a  mov     [rsi+64h], bl
0x180044a3d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable'
0x180044a44  mov     [rsi], rax
0x180044a47  mov     [rsi+68h], ebx
0x180044a4a  mov     [r15], rdi
0x180044a4d  mov     rcx, r15
0x180044a50  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180044a55  mov     [rsp+58h+arg_10], rbx
0x180044a5a  lea     rcx, [rsp+58h+arg_10]; this
0x180044a5f  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180044a64  nop
0x180044a65  xor     eax, eax
0x180044a67  mov     [r14+rbp], al
0x180044a6b  mov     rcx, r14
0x180044a6e  call    winrt__Windows__Graphics__Internal__Printing__PrintSupport__implementation__PrintSupportVirtualPrinterSession__LaunchUIForPdlDataAsync$_ResumeCoro$1
0x180044a73  nop
0x180044a74  mov     rax, r15
0x180044a77  mov     rbx, [rsp+58h+arg_18]
0x180044a7c  add     rsp, 30h
0x180044a80  pop     r15
0x180044a82  pop     r14
0x180044a84  pop     rdi
0x180044a85  pop     rsi
0x180044a86  pop     rbp
0x180044a87  retn
```
