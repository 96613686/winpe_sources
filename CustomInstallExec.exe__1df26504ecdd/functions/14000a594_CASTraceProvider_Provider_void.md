# CASTraceProvider::Provider(void)

- ea: `0x14000a594`
- end: `0x14000a5ad`
- name: `?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140007ebc`
- `0x140008964`
- `0x14000a070`
- `0x14000a588`
- `0x14000ab00`
- `0x14000abc0`
- `0x14000ad14`
- `0x14000afd4`
- `0x14000b2e0`
- `0x14000b510`

## callees

- `0x14000b934`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CASTraceProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<CASTraceProvider>::get(
                                             a1,
                                             _lambda_50b989813259e5c7866142d46bcd6eb5_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x14000a594  sub     rsp, 28h
0x14000a598  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_50b989813259e5c7866142d46bcd6eb5_@@CA@XZ; _lambda_50b989813259e5c7866142d46bcd6eb5_::_lambda_invoker_cdecl_(void)
0x14000a59f  call    ?get@?$static_lazy@VCASTraceProvider@@@details@wil@@QEAAPEAVCASTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<CASTraceProvider>::get(void (*)(void))
0x14000a5a4  mov     rax, [rax+8]
0x14000a5a8  add     rsp, 28h
0x14000a5ac  retn
```
