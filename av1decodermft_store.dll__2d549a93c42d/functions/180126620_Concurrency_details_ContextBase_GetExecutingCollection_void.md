# Concurrency::details::ContextBase::GetExecutingCollection(void)

- ea: `0x180126620`
- end: `0x180126625`
- name: `?GetExecutingCollection@ContextBase@details@Concurrency@@QEAAPEAV_TaskCollectionBase@23@XZ`
- size: `5`
- prototype: `struct Concurrency::details::_TaskCollectionBase *__fastcall(Concurrency::details::ContextBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
struct Concurrency::details::_TaskCollectionBase *__fastcall Concurrency::details::ContextBase::GetExecutingCollection(
        Concurrency::details::ContextBase *this)
{
  return (struct Concurrency::details::_TaskCollectionBase *)*((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x180126620  mov     rax, [rcx+60h]
0x180126624  retn
```
