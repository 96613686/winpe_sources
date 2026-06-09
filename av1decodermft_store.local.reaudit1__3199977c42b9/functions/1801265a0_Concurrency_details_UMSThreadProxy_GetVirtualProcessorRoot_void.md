# Concurrency::details::UMSThreadProxy::GetVirtualProcessorRoot(void)

- ea: `0x1801265a0`
- end: `0x1801265a5`
- name: `?GetVirtualProcessorRoot@UMSThreadProxy@details@Concurrency@@QEAAPEAVUMSFreeVirtualProcessorRoot@23@XZ`
- size: `5`
- prototype: `struct Concurrency::details::UMSFreeVirtualProcessorRoot *__fastcall(Concurrency::details::UMSThreadProxy *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct Concurrency::details::UMSFreeVirtualProcessorRoot *__fastcall Concurrency::details::UMSThreadProxy::GetVirtualProcessorRoot(
        Concurrency::details::UMSThreadProxy *this)
{
  return (struct Concurrency::details::UMSFreeVirtualProcessorRoot *)*((_QWORD *)this + 8);
}

```

## disassembly

```asm
0x1801265a0  mov     rax, [rcx+40h]
0x1801265a4  retn
```
