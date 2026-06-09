# _Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$0

- ea: `0x180017efd`
- end: `0x180017f09`
- name: `_Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010138`

## pseudocode

```c
void __fastcall Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  Concurrency::task_options::~task_options(*(char ***)(a2 + 112));
}

```

## disassembly

```asm
0x180017efd  mov     rcx, [rdx+70h]; this
0x180017f04  jmp     ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
```
