# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type::promise_type(void)

- ea: `0x180028eb0`
- end: `0x180028f48`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@QEAA@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029a30`

## callees

- `0x18000dd40`
- `0x1800287d8`
- `0x180028e18`
- `0x180028e3c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180028f02`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180028f02`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>>(a1 + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<enum winrt::Windows::Foundation::AsyncStatus>::atomic<enum winrt::Windows::Foundation::AsyncStatus>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type::`vftable';
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180028eb0  push    rbx
0x180028eb2  sub     rsp, 20h
0x180028eb6  mov     rbx, rcx
0x180028eb9  add     rcx, 10h
0x180028ebd  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@V?$tuple@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x180028ec2  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180028ec9  lea     rcx, [rbx+8]
0x180028ecd  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180028ed2  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180028ed9  mov     [rbx], rcx
0x180028edc  lea     rcx, [rbx+20h]; this
0x180028ee0  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x180028ee5  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,void>::`vftable'
0x180028eec  mov     [rbx], rcx
0x180028eef  lea     rcx, [rbx+38h]
0x180028ef3  mov     qword ptr [rcx], 0
0x180028efa  mov     qword ptr [rcx+8], 0
0x180028f02  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180028f08  mov     qword ptr [rbx+48h], 0
0x180028f10  lea     rcx, [rbx+60h]
0x180028f14  mov     qword ptr [rbx+50h], 0
0x180028f1c  mov     qword ptr [rbx+58h], 0
0x180028f24  call    ??$?0W4AsyncStatus@Foundation@Windows@winrt@@$0A@@?$atomic@W4AsyncStatus@Foundation@Windows@winrt@@@std@@QEAA@XZ; std::atomic<winrt::Windows::Foundation::AsyncStatus>::atomic<winrt::Windows::Foundation::AsyncStatus>(void)
0x180028f29  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@$$V@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>,>::promise_type::`vftable'
0x180028f30  mov     byte ptr [rbx+64h], 0
0x180028f34  mov     [rbx], rax
0x180028f37  mov     rax, rbx
0x180028f3a  mov     qword ptr [rbx+68h], 0
0x180028f42  add     rsp, 20h
0x180028f46  pop     rbx
0x180028f47  retn
```
