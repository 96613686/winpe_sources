# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)

- ea: `0x140011aa0`
- end: `0x140011ab9`
- name: `?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005310`
- `0x14000fdf0`
- `0x140010140`
- `0x140011a34`
- `0x1400147dc`
- `0x14001492c`
- `0x1400151b0`
- `0x14001544c`
- `0x140015d40`
- `0x140015f70`

## callees

- `0x140019da0`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(
        __int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x140011aa0  sub     rsp, 28h
0x140011aa4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_bf0cab7e367b92d194d9a1ba31b40746_@@CA@XZ; _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_(void)
0x140011aab  call    ?get@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAAPEAVPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@P6AXXZ@Z; wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(void (*)(void))
0x140011ab0  mov     rax, [rax+8]
0x140011ab4  add     rsp, 28h
0x140011ab8  retn
```
