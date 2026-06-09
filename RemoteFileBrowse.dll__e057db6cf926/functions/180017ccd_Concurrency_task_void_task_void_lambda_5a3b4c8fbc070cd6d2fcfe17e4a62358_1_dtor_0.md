# _Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$0

- ea: `0x180017ccd`
- end: `0x180017cd9`
- name: `_Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005988`

## pseudocode

```c
__int64 __fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(*(_QWORD *)(a2 + 192));
}

```

## disassembly

```asm
0x180017ccd  mov     rcx, [rdx+0C0h]
0x180017cd4  jmp     ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
```
