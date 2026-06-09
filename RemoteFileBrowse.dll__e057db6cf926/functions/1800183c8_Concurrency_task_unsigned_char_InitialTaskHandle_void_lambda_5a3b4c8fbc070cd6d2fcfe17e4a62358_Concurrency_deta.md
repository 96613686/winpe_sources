# _Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$8

- ea: `0x1800183c8`
- end: `0x1800183d4`
- name: `_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f8d4`

## pseudocode

```c
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor_8(
        __int64 a1,
        __int64 a2)
{
  return std::_Func_class<void,>::~_Func_class<void,>(*(_QWORD *)(a2 + 40), a2);
}

```

## disassembly

```asm
0x1800183c8  mov     rcx, [rdx+28h]
0x1800183cf  jmp     ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
```
