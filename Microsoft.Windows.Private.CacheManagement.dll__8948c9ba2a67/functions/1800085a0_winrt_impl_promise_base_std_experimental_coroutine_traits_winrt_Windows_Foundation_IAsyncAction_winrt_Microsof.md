# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)

- ea: `0x1800085a0`
- end: `0x180008662`
- name: `?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z`
- size: `194`
- prototype: `bool __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c7a0`
- `0x18001ca20`

## callees

- `0x180003840`
- `0x1800085a0`
- `0x180009b70`
- `0x18000a420`
- `0x1800162aa`
- `0x1800162b0`

## pseudocode

```c
bool __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(
        __int64 *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 *v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v9; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v10[4]; // [rsp+28h] [rbp-20h] BYREF

  v1 = *a1;
  v3 = 0;
  v10[0] = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v1 + 72));
  v9 = *(_DWORD *)(v1 + 96);
  if ( !v9 )
  {
    v9 = 1;
    *(_DWORD *)(v1 + 96) = 1;
  }
  v4 = (__int64 *)(v1 + 80);
  v5 = 0;
  if ( v10 != (_QWORD *)(v1 + 80) )
  {
    v5 = *v4;
    *v4 = 0;
    v3 = v5;
    v10[0] = v5;
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)(v1 + 72));
  if ( v5 )
  {
    winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
      v10,
      v1,
      &v9);
    v3 = v10[0];
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
  v6 = *a1;
  v7 = winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(*a1);
  if ( !v7 )
    *(_QWORD *)(v6 + 8) = 1;
  return v7 != 0;
}

```

## disassembly

```asm
0x1800085a0  mov     [rsp+arg_8], rbx
0x1800085a5  mov     [rsp+arg_10], rbp
0x1800085aa  push    rsi
0x1800085ab  push    rdi
0x1800085ac  push    r14
0x1800085ae  sub     rsp, 30h
0x1800085b2  mov     rsi, [rcx]
0x1800085b5  mov     r14, rcx
0x1800085b8  xor     ebx, ebx
0x1800085ba  mov     [rsp+48h+var_20], rbx
0x1800085bf  lea     rcx, [rsi+48h]; SRWLock
0x1800085c3  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800085c8  mov     eax, [rsi+60h]
0x1800085cb  mov     [rsp+48h+var_28], eax
0x1800085cf  test    eax, eax
0x1800085d1  jnz     short loc_1800085E2
0x1800085d3  mov     [rsp+48h+var_28], 1
0x1800085db  mov     dword ptr [rsi+60h], 1
0x1800085e2  lea     rax, [rsi+50h]
0x1800085e6  mov     rbp, rbx
0x1800085e9  lea     rcx, [rsp+48h+var_20]
0x1800085ee  cmp     rcx, rax
0x1800085f1  jz      short loc_180008601
0x1800085f3  mov     rbp, [rax]
0x1800085f6  mov     [rax], rbx
0x1800085f9  mov     rbx, rbp
0x1800085fc  mov     [rsp+48h+var_20], rbx
0x180008601  lea     rcx, [rsi+48h]; SRWLock
0x180008605  call    ReleaseSRWLockExclusive_0
0x18000860a  test    rbp, rbp
0x18000860d  jz      short loc_180008626
0x18000860f  lea     r8, [rsp+48h+var_28]
0x180008614  mov     rdx, rsi
0x180008617  lea     rcx, [rsp+48h+var_20]
0x18000861c  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180008621  mov     rbx, [rsp+48h+var_20]
0x180008626  test    rbx, rbx
0x180008629  jz      short loc_180008635
0x18000862b  lea     rcx, [rsp+48h+var_20]
0x180008630  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008635  mov     rbx, [r14]
0x180008638  mov     rcx, rbx
0x18000863b  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180008640  test    eax, eax
0x180008642  jnz     short loc_18000864C
0x180008644  mov     qword ptr [rbx+8], 1
0x18000864c  mov     rbx, [rsp+48h+arg_8]
0x180008651  setnz   al
0x180008654  mov     rbp, [rsp+48h+arg_10]
0x180008659  add     rsp, 30h
0x18000865d  pop     r14
0x18000865f  pop     rdi
0x180008660  pop     rsi
0x180008661  retn
```
