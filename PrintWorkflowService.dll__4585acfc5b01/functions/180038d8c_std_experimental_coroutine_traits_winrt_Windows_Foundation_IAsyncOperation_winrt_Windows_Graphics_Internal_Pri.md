# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::promise_type(void)

- ea: `0x180038d8c`
- end: `0x180038e17`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@QEAA@XZ`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003d5f0`
- `0x18003d7cc`

## callees

- `0x18000874c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180038de2`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180038de2`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable';
  result = a1;
  *(_BYTE *)(a1 + 100) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180038d8c  mov     [rsp+arg_0], rbx
0x180038d91  push    rdi
0x180038d92  sub     rsp, 20h
0x180038d96  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>>::`vftable'
0x180038d9d  mov     rdi, rcx
0x180038da0  mov     [rcx+10h], rax
0x180038da4  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180038dab  mov     [rcx+18h], rax
0x180038daf  add     rcx, 8
0x180038db3  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180038db8  xor     ebx, ebx
0x180038dba  mov     qword ptr [rdi+8], 1
0x180038dc2  lea     rcx, [rdi+38h]
0x180038dc6  mov     [rdi+20h], rbx
0x180038dca  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::`vftable'
0x180038dd1  mov     [rdi+28h], rbx
0x180038dd5  mov     [rdi+30h], bl
0x180038dd8  mov     [rdi], rax
0x180038ddb  mov     [rcx], rbx
0x180038dde  mov     [rcx+8], rbx
0x180038de2  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180038de8  mov     [rdi+48h], rbx
0x180038dec  xor     eax, eax
0x180038dee  mov     [rdi+50h], rbx
0x180038df2  mov     [rdi+58h], rbx
0x180038df6  mov     [rdi+60h], eax
0x180038df9  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type::`vftable'
0x180038e00  mov     [rdi], rax
0x180038e03  mov     rax, rdi
0x180038e06  mov     [rdi+64h], bl
0x180038e09  mov     [rdi+68h], ebx
0x180038e0c  mov     rbx, [rsp+28h+arg_0]
0x180038e11  add     rsp, 20h
0x180038e15  pop     rdi
0x180038e16  retn
```
