# Concurrency::details::ContextBase::SetIndirectAlias(Concurrency::details::_TaskCollection *)

- ea: `0x18002b7e0`
- end: `0x18002b7e8`
- name: `?SetIndirectAlias@ContextBase@details@Concurrency@@QEAAXPEAV_TaskCollection@23@@Z`
- size: `8`
- prototype: `void __fastcall(Concurrency::details::ContextBase *__hidden this, struct Concurrency::details::_TaskCollection *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18002dff0`

## pseudocode

```c
void __fastcall Concurrency::details::ContextBase::SetIndirectAlias(
        Concurrency::details::ContextBase *this,
        struct Concurrency::details::_TaskCollection *a2)
{
  *((_QWORD *)this + 22) = a2;
}

```

## disassembly

```asm
0x18002b7e0  mov     [rcx+0B0h], rdx
0x18002b7e7  retn
```
