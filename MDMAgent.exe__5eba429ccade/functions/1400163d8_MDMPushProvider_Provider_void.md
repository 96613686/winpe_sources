# MDMPushProvider::Provider(void)

- ea: `0x1400163d8`
- end: `0x1400163f1`
- name: `?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140016010`
- `0x1400163cc`
- `0x1400163f8`
- `0x140016980`
- `0x140016a18`
- `0x140016ab0`
- `0x140016bbc`
- `0x140016c90`
- `0x140016ed0`
- `0x140017110`

## callees

- `0x1400173f4`

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
0x1400163d8  sub     rsp, 28h
0x1400163dc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8e2e3e542c2dc97e9f262390b1f584c8_@@CA@XZ; _lambda_8e2e3e542c2dc97e9f262390b1f584c8_::_lambda_invoker_cdecl_(void)
0x1400163e3  call    ?get@?$static_lazy@VMDMPushProvider@@@details@wil@@QEAAPEAVMDMPushProvider@@P6AXXZ@Z; wil::details::static_lazy<MDMPushProvider>::get(void (*)(void))
0x1400163e8  mov     rax, [rax+8]
0x1400163ec  add     rsp, 28h
0x1400163f0  retn
```
