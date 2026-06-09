# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type::promise_type(void)

- ea: `0x18001f39c`
- end: `0x18001f430`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@QEAA@XZ`
- size: `148`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800204c8`
- `0x1800252a8`

## callees

- `0x18001c8ec`
- `0x18001e5cc`
- `0x18001ee40`
- `0x18001f1d8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001f3ee`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001f3ee`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>>();
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<unsigned int>::atomic<unsigned int>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type::`vftable';
  result = a1;
  *(_BYTE *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x18001f39c  push    rbx
0x18001f39e  sub     rsp, 20h
0x18001f3a2  mov     rbx, rcx
0x18001f3a5  add     rcx, 10h
0x18001f3a9  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@V?$tuple@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x18001f3ae  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f3b5  lea     rcx, [rbx+8]
0x18001f3b9  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001f3be  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18001f3c5  mov     [rbx], rcx
0x18001f3c8  lea     rcx, [rbx+20h]; this
0x18001f3cc  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x18001f3d1  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::`vftable'
0x18001f3d8  mov     [rbx], rcx
0x18001f3db  lea     rcx, [rbx+38h]
0x18001f3df  mov     qword ptr [rcx], 0
0x18001f3e6  mov     qword ptr [rcx+8], 0
0x18001f3ee  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001f3f4  mov     qword ptr [rbx+48h], 0
0x18001f3fc  lea     rcx, [rbx+60h]
0x18001f400  mov     qword ptr [rbx+50h], 0
0x18001f408  mov     qword ptr [rbx+58h], 0
0x18001f410  call    ??$?0I$0A@@?$atomic@I@std@@QEAA@XZ; std::atomic<uint>::atomic<uint>(void)
0x18001f415  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type::`vftable'
0x18001f41c  mov     byte ptr [rbx+64h], 0
0x18001f420  mov     [rbx], rax
0x18001f423  mov     rax, rbx
0x18001f426  mov     byte ptr [rbx+68h], 0
0x18001f42a  add     rsp, 20h
0x18001f42e  pop     rbx
0x18001f42f  retn
```
