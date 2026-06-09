# Concurrency::details::_Task_impl_base::_HasUserException(void)

- ea: `0x180012114`
- end: `0x18001211d`
- name: `?_HasUserException@_Task_impl_base@details@Concurrency@@QEAA_NXZ`
- size: `9`
- prototype: `bool __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18001854d`

## pseudocode

```c
bool __fastcall Concurrency::details::_Task_impl_base::_HasUserException(Concurrency::details::_Task_impl_base *this)
{
  return *((_QWORD *)this + 2) != 0;
}

```

## disassembly

```asm
0x180012114  cmp     qword ptr [rcx+10h], 0
0x180012119  setnz   al
0x18001211c  retn
```
