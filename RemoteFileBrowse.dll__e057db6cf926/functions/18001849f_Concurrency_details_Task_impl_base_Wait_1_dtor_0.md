# _Concurrency::details::_Task_impl_base::_Wait_::_1_::dtor$0

- ea: `0x18001849f`
- end: `0x1800184ab`
- name: `_Concurrency::details::_Task_impl_base::_Wait_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010128`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_Wait_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::exception_ptr::~exception_ptr((std::exception_ptr *)(a2 + 32));
}

```

## disassembly

```asm
0x18001849f  lea     rcx, [rdx+20h]; this
0x1800184a6  jmp     ??1exception_ptr@std@@QEAA@XZ; std::exception_ptr::~exception_ptr(void)
```
