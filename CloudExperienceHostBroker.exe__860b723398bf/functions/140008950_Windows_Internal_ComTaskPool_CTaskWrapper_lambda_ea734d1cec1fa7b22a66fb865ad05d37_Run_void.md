# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::Run(void)

- ea: `0x140008950`
- end: `0x140008959`
- name: `?Run@?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@UEAAXXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000759c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::Run(
        __int64 a1)
{
  return _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::operator()((__int64 *)(a1 + 16));
}

```

## disassembly

```asm
0x140008950  add     rcx, 10h
0x140008954  jmp     ??R_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEBAJXZ; _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::operator()(void)
```
