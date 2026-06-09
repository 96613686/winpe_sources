# ComTrace::Provider(void)

- ea: `0x14000e06c`
- end: `0x14000e085`
- name: `?Provider@ComTrace@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000dc6c`
- `0x14000df40`
- `0x14000e884`
- `0x14000e8e4`

## callees

- `0x14000e98c`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall ComTrace::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<ComTrace>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x14000e06c  sub     rsp, 28h
0x14000e070  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_(void)
0x14000e077  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x14000e07c  mov     rax, [rax+8]
0x14000e080  add     rsp, 28h
0x14000e084  retn
```
