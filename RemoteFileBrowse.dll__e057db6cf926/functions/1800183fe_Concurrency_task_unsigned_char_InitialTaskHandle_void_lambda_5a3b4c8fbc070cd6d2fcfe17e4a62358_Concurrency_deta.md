# _Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$17

- ea: `0x1800183fe`
- end: `0x18001840a`
- name: `_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$17`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ffec`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor_17(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger((Concurrency::details::_TaskEventLogger **)(a2 + 32));
}

```

## disassembly

```asm
0x1800183fe  lea     rcx, [rdx+20h]; this
0x180018405  jmp     ??1_TaskWorkItemRAIILogger@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(void)
```
