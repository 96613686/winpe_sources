# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::promise_type(void)

- ea: `0x180031194`
- end: `0x180031220`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@QEAA@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180033984`
- `0x180043e2c`

## callees

- `0x18000874c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800311ea`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800311ea`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::`vftable';
  result = a1;
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180031194  mov     [rsp+arg_0], rbx
0x180031199  push    rdi
0x18003119a  sub     rsp, 20h
0x18003119e  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAVPrintSupportSessionCommon@@@experimental@std@@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>>::`vftable'
0x1800311a5  mov     rdi, rcx
0x1800311a8  mov     [rcx+10h], rax
0x1800311ac  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAVPrintSupportSessionCommon@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x1800311b3  mov     [rcx+18h], rax
0x1800311b7  add     rcx, 8
0x1800311bb  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800311c0  xor     ebx, ebx
0x1800311c2  mov     qword ptr [rdi+8], 1
0x1800311ca  lea     rcx, [rdi+38h]
0x1800311ce  mov     [rdi+20h], rbx
0x1800311d2  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAVPrintSupportSessionCommon@@@experimental@std@@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,void>::`vftable'
0x1800311d9  mov     [rdi+28h], rbx
0x1800311dd  mov     [rdi+30h], bl
0x1800311e0  mov     [rdi], rax
0x1800311e3  mov     [rcx], rbx
0x1800311e6  mov     [rcx+8], rbx
0x1800311ea  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800311f0  mov     [rdi+48h], rbx
0x1800311f4  xor     eax, eax
0x1800311f6  mov     [rdi+50h], rbx
0x1800311fa  mov     [rdi+58h], rbx
0x1800311fe  mov     [rdi+60h], eax
0x180031201  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::`vftable'
0x180031208  mov     [rdi], rax
0x18003120b  mov     rax, rdi
0x18003120e  mov     [rdi+64h], bl
0x180031211  mov     [rdi+68h], rbx
0x180031215  mov     rbx, [rsp+28h+arg_0]
0x18003121a  add     rsp, 20h
0x18003121e  pop     rdi
0x18003121f  retn
```
