# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type::promise_type(void)

- ea: `0x180050b64`
- end: `0x180050bf0`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUIppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@34@_NUhstring@4@@experimental@std@@QEAA@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180051868`

## callees

- `0x18000874c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050bba`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050bba`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type::`vftable';
  result = a1;
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180050b64  mov     [rsp+arg_0], rbx
0x180050b69  push    rdi
0x180050b6a  sub     rsp, 20h
0x180050b6e  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUIppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@34@_NUhstring@4@@experimental@std@@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>>::`vftable'
0x180050b75  mov     rdi, rcx
0x180050b78  mov     [rcx+10h], rax
0x180050b7c  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUIppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@34@_NUhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180050b83  mov     [rcx+18h], rax
0x180050b87  add     rcx, 8
0x180050b8b  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180050b90  xor     ebx, ebx
0x180050b92  mov     qword ptr [rdi+8], 1
0x180050b9a  lea     rcx, [rdi+38h]
0x180050b9e  mov     [rdi+20h], rbx
0x180050ba2  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUIppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@34@_NUhstring@4@@experimental@std@@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,void>::`vftable'
0x180050ba9  mov     [rdi+28h], rbx
0x180050bad  mov     [rdi+30h], bl
0x180050bb0  mov     [rdi], rax
0x180050bb3  mov     [rcx], rbx
0x180050bb6  mov     [rcx+8], rbx
0x180050bba  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180050bc0  mov     [rdi+48h], rbx
0x180050bc4  xor     eax, eax
0x180050bc6  mov     [rdi+50h], rbx
0x180050bca  mov     [rdi+58h], rbx
0x180050bce  mov     [rdi+60h], eax
0x180050bd1  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UIppPrinterCredentials@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUIppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@34@_NUhstring@4@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials>,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *,bool,winrt::hstring>::promise_type::`vftable'
0x180050bd8  mov     [rdi], rax
0x180050bdb  mov     rax, rdi
0x180050bde  mov     [rdi+64h], bl
0x180050be1  mov     [rdi+68h], rbx
0x180050be5  mov     rbx, [rsp+28h+arg_0]
0x180050bea  add     rsp, 20h
0x180050bee  pop     rdi
0x180050bef  retn
```
