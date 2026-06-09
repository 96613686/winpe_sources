# std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>::promise_type::unhandled_exception(void)

- ea: `0x180008ea0`
- end: `0x180008eaa`
- name: `?unhandled_exception@promise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@2@@experimental@std@@QEBAXXZ`
- size: `10`
- prototype: `void __fastcall __noreturn(winrt *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001fb75`

## callees

- `0x18000f080`

## pseudocode

```c
void __fastcall __noreturn std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>::promise_type::unhandled_exception(
        winrt *a1)
{
  winrt::terminate(a1);
}

```

## disassembly

```asm
0x180008ea0  sub     rsp, 28h
0x180008ea4  call    ?terminate@winrt@@YAXXZ; winrt::terminate(void)
```
