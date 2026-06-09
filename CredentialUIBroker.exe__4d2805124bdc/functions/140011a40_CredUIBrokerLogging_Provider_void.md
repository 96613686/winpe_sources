# CredUIBrokerLogging::Provider(void)

- ea: `0x140011a40`
- end: `0x140011a59`
- name: `?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004e50`
- `0x14000f750`
- `0x140011a1c`
- `0x140014684`
- `0x140014730`
- `0x140014bb0`
- `0x140014eb0`
- `0x1400158e0`
- `0x140015b10`

## callees

- `0x140019b60`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CredUIBrokerLogging::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<CredUIBrokerLogging>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_93ae2df0382b960c1667db6321119e38_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x140011a40  sub     rsp, 28h
0x140011a44  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_93ae2df0382b960c1667db6321119e38_@@CA@XZ; _lambda_93ae2df0382b960c1667db6321119e38_::_lambda_invoker_cdecl_(void)
0x140011a4b  call    ?get@?$static_lazy@VCredUIBrokerLogging@@@details@wil@@QEAAPEAVCredUIBrokerLogging@@P6AXXZ@Z; wil::details::static_lazy<CredUIBrokerLogging>::get(void (*)(void))
0x140011a50  mov     rax, [rax+8]
0x140011a54  add     rsp, 28h
0x140011a58  retn
```
