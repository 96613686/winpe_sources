# _Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$5

- ea: `0x180018346`
- end: `0x180018356`
- name: `_Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$5`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010128`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  std::exception_ptr::~exception_ptr((std::exception_ptr *)(*(_QWORD *)(a2 + 144) + 8LL));
}

```

## disassembly

```asm
0x180018346  mov     rcx, [rdx+90h]
0x18001834d  add     rcx, 8; this
0x180018351  jmp     ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
```
