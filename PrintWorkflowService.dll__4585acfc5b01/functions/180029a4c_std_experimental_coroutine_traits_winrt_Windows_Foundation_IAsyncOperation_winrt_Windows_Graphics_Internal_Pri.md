# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type::promise_type(void)

- ea: `0x180029a4c`
- end: `0x180029ad8`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@QEAA@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002c044`

## callees

- `0x180008670`
- `0x18000874c`
- `0x1800245e0`
- `0x1800250e4`
- `0x180029790`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029a9e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029a9e`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>>();
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<enum winrt::Windows::Foundation::AsyncStatus>::atomic<enum winrt::Windows::Foundation::AsyncStatus>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type::`vftable';
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180029a4c  mov     [rsp+arg_0], rbx
0x180029a51  push    rdi
0x180029a52  sub     rsp, 20h
0x180029a56  mov     rdi, rcx
0x180029a59  add     rcx, 10h
0x180029a5d  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@V?$tuple@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x180029a62  lea     rcx, [rdi+8]
0x180029a66  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180029a6b  lea     rcx, [rdi+8]
0x180029a6f  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180029a74  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180029a7b  mov     [rdi], rcx
0x180029a7e  lea     rcx, [rdi+20h]; this
0x180029a82  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x180029a87  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::`vftable'
0x180029a8e  xor     ebx, ebx
0x180029a90  mov     [rdi], rcx
0x180029a93  lea     rcx, [rdi+38h]
0x180029a97  mov     [rcx], rbx
0x180029a9a  mov     [rcx+8], rbx
0x180029a9e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180029aa4  mov     [rdi+48h], rbx
0x180029aa8  lea     rcx, [rdi+60h]
0x180029aac  mov     [rdi+50h], rbx
0x180029ab0  mov     [rdi+58h], rbx
0x180029ab4  call    ??$?0W4AsyncStatus@Foundation@Windows@winrt@@$0A@@?$atomic@W4AsyncStatus@Foundation@Windows@winrt@@@std@@QEAA@XZ; std::atomic<winrt::Windows::Foundation::AsyncStatus>::atomic<winrt::Windows::Foundation::AsyncStatus>(void)
0x180029ab9  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type::`vftable'
0x180029ac0  mov     [rdi+64h], bl
0x180029ac3  mov     [rdi], rax
0x180029ac6  mov     rax, rdi
0x180029ac9  mov     [rdi+68h], rbx
0x180029acd  mov     rbx, [rsp+28h+arg_0]
0x180029ad2  add     rsp, 20h
0x180029ad6  pop     rdi
0x180029ad7  retn
```
