# _CTaskCounter::Decrement_::_1_::dtor$0

- ea: `0x18001e8e0`
- end: `0x18001e8ec`
- name: `_CTaskCounter::Decrement_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800076d4`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Decrement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____::_WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____(a2 + 64);
}

```

## disassembly

```asm
0x18001e8e0  lea     rcx, [rdx+40h]
0x18001e8e7  jmp     WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab_______WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____
```
