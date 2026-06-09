# _CTaskCounter::Initialize_::_1_::dtor$0

- ea: `0x18001e941`
- end: `0x18001e94d`
- name: `_CTaskCounter::Initialize_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800076b8`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Initialize_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____::_WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____(a2 + 48);
}

```

## disassembly

```asm
0x18001e941  lea     rcx, [rdx+30h]
0x18001e948  jmp     WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47_______WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____
```
