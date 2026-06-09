# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::unhandled_exception(void)

- ea: `0x180008e30`
- end: `0x180008e94`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `100`
- prototype: `void __fastcall __noreturn(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001fab6`
- `0x18001fb15`

## callees

- `0x18000f0b0`
- `0x18000f120`
- `0x180012ab0`
- `0x180012ae0`
- `0x180012af0`
- `0x180012b00`
- `0x1800162b0`

## pseudocode

```c
void __fastcall __noreturn winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::unhandled_exception(
        __int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx
  _QWORD v6[5]; // [rsp+0h] [rbp-48h] BYREF
  _BYTE v7[16]; // [rsp+28h] [rbp-20h] BYREF
  PSRWLOCK v8[2]; // [rsp+38h] [rbp-10h] BYREF

  v6[4] = a1;
  winrt::slim_lock_guard::slim_lock_guard((winrt::slim_lock_guard *)v8, (struct winrt::slim_mutex *)(a1 + 72));
  v2 = std::current_exception(v7);
  std::exception_ptr::operator=(a1 + 56, v2);
  std::exception_ptr::~exception_ptr((std::exception_ptr *)v7);
  v3 = std::exception_ptr::exception_ptr((std::exception_ptr *)v7, (const struct std::exception_ptr *)(a1 + 56));
  try
  {
    std::rethrow_exception(v3);
  }
  catch ( winrt::hresult_canceled )
  {
    v4 = v6;
    *(_DWORD *)(v4[4] + 96LL) = 2;
    goto LABEL_2;
  }
  catch ( ... )
  {
    v5 = v6;
    *(_DWORD *)(v5[4] + 96LL) = 3;
LABEL_2:
    ReleaseSRWLockExclusive_0(v8[0]);
  }
}

```

## disassembly

```asm
0x180008e30  push    rbx
0x180008e32  sub     rsp, 40h
0x180008e36  mov     rbx, rcx
0x180008e39  mov     [rsp+48h+var_28], rcx
0x180008e3e  lea     rdx, [rcx+48h]; struct winrt::slim_mutex *
0x180008e42  lea     rcx, [rsp+48h+var_10]; this
0x180008e47  call    ??0slim_lock_guard@winrt@@QEAA@AEAUslim_mutex@1@@Z; winrt::slim_lock_guard::slim_lock_guard(winrt::slim_mutex &)
0x180008e4c  nop
0x180008e4d  lea     rcx, [rsp+48h+var_20]
0x180008e52  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180008e57  mov     rdx, rax
0x180008e5a  lea     rcx, [rbx+38h]
0x180008e5e  call    ??4exception_ptr@std@@QEAAAEAV01@AEBV01@@Z; std::exception_ptr::operator=(std::exception_ptr const &)
0x180008e63  lea     rcx, [rsp+48h+var_20]; this
0x180008e68  call    ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
0x180008e6d  nop
0x180008e6e  lea     rdx, [rbx+38h]; struct std::exception_ptr *
0x180008e72  lea     rcx, [rsp+48h+var_20]; this
0x180008e77  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180008e7c  mov     rcx, rax
0x180008e7f  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180008e85  mov     rcx, [rsp+48h+var_10]
0x180008e8a  add     rsp, 40h
0x180008e8e  pop     rbx
0x180008e8f  jmp     ReleaseSRWLockExclusive_0
```
