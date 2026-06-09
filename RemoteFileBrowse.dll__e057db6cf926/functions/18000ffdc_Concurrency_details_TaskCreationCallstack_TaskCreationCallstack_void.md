# Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(void)

- ea: `0x18000ffdc`
- end: `0x18000ffe5`
- name: `??1_TaskCreationCallstack@details@Concurrency@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(char **this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180017e34`
- `0x180017e66`
- `0x180017f0f`
- `0x18001830e`

## callees

- `0x18000fd1c`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(char **this)
{
  std::vector<void *>::~vector<void *>(this + 1);
}

```

## disassembly

```asm
0x18000ffdc  add     rcx, 8
0x18000ffe0  jmp     ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
```
