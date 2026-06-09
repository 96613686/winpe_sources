# HostNameVerifierProvider::Provider(void)

- ea: `0x14000da38`
- end: `0x14000da51`
- name: `?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d610`
- `0x14000da2c`
- `0x14000dfdc`
- `0x14000e0ec`
- `0x14000e1e0`
- `0x14000e348`
- `0x14000e430`
- `0x14000e660`
- `0x14000e890`

## callees

- `0x14000fe34`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall HostNameVerifierProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<HostNameVerifierProvider>::get(
                                             a1,
                                             _lambda_a64840057034bcf27d3d166bd51c0bfc_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x14000da38  sub     rsp, 28h
0x14000da3c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a64840057034bcf27d3d166bd51c0bfc_@@CA@XZ; _lambda_a64840057034bcf27d3d166bd51c0bfc_::_lambda_invoker_cdecl_(void)
0x14000da43  call    ?get@?$static_lazy@VHostNameVerifierProvider@@@details@wil@@QEAAPEAVHostNameVerifierProvider@@P6AXXZ@Z; wil::details::static_lazy<HostNameVerifierProvider>::get(void (*)(void))
0x14000da48  mov     rax, [rax+8]
0x14000da4c  add     rsp, 28h
0x14000da50  retn
```
