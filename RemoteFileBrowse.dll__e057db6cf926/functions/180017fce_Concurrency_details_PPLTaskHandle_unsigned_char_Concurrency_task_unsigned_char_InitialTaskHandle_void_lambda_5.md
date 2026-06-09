# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::dtor$0

- ea: `0x180017fce`
- end: `0x180017fda`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010128`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::exception_ptr::~exception_ptr((std::exception_ptr *)(a2 + 48));
}

```

## disassembly

```asm
0x180017fce  lea     rcx, [rdx+30h]; this
0x180017fd5  jmp     ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
```
