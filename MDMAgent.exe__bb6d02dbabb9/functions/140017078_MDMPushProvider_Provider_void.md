# MDMPushProvider::Provider(void)

- ea: `0x140017078`
- end: `0x140017092`
- name: `?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `26`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140016cb0`
- `0x14001706c`
- `0x140017098`
- `0x140017628`
- `0x1400176c4`
- `0x140017760`
- `0x140017878`
- `0x140017950`
- `0x140017b90`
- `0x140017dd0`

## callees

- `0x1400180b8`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall MDMPushProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<MDMPushProvider>::get(
                                             a1,
                                             _lambda_8e2e3e542c2dc97e9f262390b1f584c8_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x140017078  sub     rsp, 28h
0x14001707c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8e2e3e542c2dc97e9f262390b1f584c8_@@CA@XZ; _lambda_8e2e3e542c2dc97e9f262390b1f584c8_::_lambda_invoker_cdecl_(void)
0x140017083  call    ?get@?$static_lazy@VMDMPushProvider@@@details@wil@@QEAAPEAVMDMPushProvider@@P6AXXZ@Z; wil::details::static_lazy<MDMPushProvider>::get(void (*)(void))
0x140017088  mov     rax, [rax+8]
0x14001708c  add     rsp, 28h
0x140017090  retn
```
