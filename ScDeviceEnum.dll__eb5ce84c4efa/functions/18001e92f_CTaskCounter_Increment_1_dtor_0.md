# _CTaskCounter::Increment_::_1_::dtor$0

- ea: `0x18001e92f`
- end: `0x18001e93b`
- name: `_CTaskCounter::Increment_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800076f0`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Increment_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____::_WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____(a2 + 64);
}

```

## disassembly

```asm
0x18001e92f  lea     rcx, [rdx+40h]
0x18001e936  jmp     WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16_______WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____
```
