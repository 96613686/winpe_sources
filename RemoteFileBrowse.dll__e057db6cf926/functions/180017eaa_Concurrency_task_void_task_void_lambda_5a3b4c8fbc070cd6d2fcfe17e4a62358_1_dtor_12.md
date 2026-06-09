# _Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$12

- ea: `0x180017eaa`
- end: `0x180017eb6`
- name: `_Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$12`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005988`

## pseudocode

```c
__int64 __fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_12(
        __int64 a1,
        __int64 a2)
{
  return std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(*(_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x180017eaa  mov     rcx, [rdx+20h]
0x180017eb1  jmp     ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
```
