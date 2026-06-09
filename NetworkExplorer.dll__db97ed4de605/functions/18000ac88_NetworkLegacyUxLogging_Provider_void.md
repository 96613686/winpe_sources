# NetworkLegacyUxLogging::Provider(void)

- ea: `0x18000ac88`
- end: `0x18000aca1`
- name: `?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b90`
- `0x18000a820`
- `0x18000b8c4`
- `0x18000baa4`
- `0x18000bb90`

## callees

- `0x18000d3c4`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall NetworkLegacyUxLogging::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<NetworkLegacyUxLogging>::get(
                                             a1,
                                             _lambda_0f38c6fafb7aeb3e11e6a93cf8931294_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x18000ac88  sub     rsp, 28h
0x18000ac8c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0f38c6fafb7aeb3e11e6a93cf8931294_@@CA@XZ; _lambda_0f38c6fafb7aeb3e11e6a93cf8931294_::_lambda_invoker_cdecl_(void)
0x18000ac93  call    ?get@?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@QEAAPEAVNetworkLegacyUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkLegacyUxLogging>::get(void (*)(void))
0x18000ac98  mov     rax, [rax+8]
0x18000ac9c  add     rsp, 28h
0x18000aca0  retn
```
