# Concurrency::details::_TaskCollection::_OriginalCollection(void)

- ea: `0x180051ed0`
- end: `0x180051ed8`
- name: `?_OriginalCollection@_TaskCollection@details@Concurrency@@AEBAPEAV123@XZ`
- size: `8`
- prototype: `struct Concurrency::details::_TaskCollection *__fastcall(Concurrency::details::_TaskCollection *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
struct Concurrency::details::_TaskCollection *__fastcall Concurrency::details::_TaskCollection::_OriginalCollection(
        Concurrency::details::_TaskCollection *this)
{
  return (struct Concurrency::details::_TaskCollection *)*((_QWORD *)this + 18);
}

```

## disassembly

```asm
0x180051ed0  mov     rax, [rcx+90h]
0x180051ed7  retn
```
