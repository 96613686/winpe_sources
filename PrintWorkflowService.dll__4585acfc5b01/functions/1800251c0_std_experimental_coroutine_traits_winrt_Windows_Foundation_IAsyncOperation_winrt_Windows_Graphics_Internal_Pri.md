# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type::promise_type(void)

- ea: `0x1800251c0`
- end: `0x18002524c`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@34@Uhstring@4@I@experimental@std@@QEAA@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800263d8`

## callees

- `0x180008670`
- `0x18000874c`
- `0x1800245e0`
- `0x1800250a8`
- `0x1800250e4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180025212`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180025212`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>>(a1 + 16);
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<enum winrt::Windows::Foundation::AsyncStatus>::atomic<enum winrt::Windows::Foundation::AsyncStatus>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,unsigned int>::promise_type::`vftable';
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x1800251c0  mov     [rsp+arg_0], rbx
0x1800251c5  push    rdi
0x1800251c6  sub     rsp, 20h
0x1800251ca  mov     rdi, rcx
0x1800251cd  add     rcx, 10h
0x1800251d1  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@34@Uhstring@4@I@experimental@std@@V?$tuple@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x1800251d6  lea     rcx, [rdi+8]
0x1800251da  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800251df  lea     rcx, [rdi+8]
0x1800251e3  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1800251e8  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@34@Uhstring@4@I@experimental@std@@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x1800251ef  mov     [rdi], rcx
0x1800251f2  lea     rcx, [rdi+20h]; this
0x1800251f6  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x1800251fb  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@34@Uhstring@4@I@experimental@std@@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,void>::`vftable'
0x180025202  xor     ebx, ebx
0x180025204  mov     [rdi], rcx
0x180025207  lea     rcx, [rdi+38h]
0x18002520b  mov     [rcx], rbx
0x18002520e  mov     [rcx+8], rbx
0x180025212  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180025218  mov     [rdi+48h], rbx
0x18002521c  lea     rcx, [rdi+60h]
0x180025220  mov     [rdi+50h], rbx
0x180025224  mov     [rdi+58h], rbx
0x180025228  call    ??$?0W4AsyncStatus@Foundation@Windows@winrt@@$0A@@?$atomic@W4AsyncStatus@Foundation@Windows@winrt@@@std@@QEAA@XZ; std::atomic<winrt::Windows::Foundation::AsyncStatus>::atomic<winrt::Windows::Foundation::AsyncStatus>(void)
0x18002522d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSourceSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@34@Uhstring@4@I@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSourceSession>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *,winrt::hstring,uint>::promise_type::`vftable'
0x180025234  mov     [rdi+64h], bl
0x180025237  mov     [rdi], rax
0x18002523a  mov     rax, rdi
0x18002523d  mov     [rdi+68h], rbx
0x180025241  mov     rbx, [rsp+28h+arg_0]
0x180025246  add     rsp, 20h
0x18002524a  pop     rdi
0x18002524b  retn
```
