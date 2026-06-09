# Concurrency::details::ContextBase::GetRootCollection(void)

- ea: `0x180056a40`
- end: `0x180056a45`
- name: `?GetRootCollection@ContextBase@details@Concurrency@@QEAAPEAV_TaskCollectionBase@23@XZ`
- size: `5`
- prototype: `struct Concurrency::details::_TaskCollectionBase *__fastcall(Concurrency::details::ContextBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
struct Concurrency::details::_TaskCollectionBase *__fastcall Concurrency::details::ContextBase::GetRootCollection(
        Concurrency::details::ContextBase *this)
{
  return (struct Concurrency::details::_TaskCollectionBase *)*((_QWORD *)this + 11);
}

```

## disassembly

```asm
0x180056a40  mov     rax, [rcx+58h]
0x180056a44  retn
```
