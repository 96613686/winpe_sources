# _Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$1

- ea: `0x180017f0f`
- end: `0x180017f1b`
- name: `_Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ffdc`

## pseudocode

```c
void __fastcall Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack((char **)(a2 + 40));
}

```

## disassembly

```asm
0x180017f0f  lea     rcx, [rdx+28h]; this
0x180017f16  jmp     ??1_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(void)
```
