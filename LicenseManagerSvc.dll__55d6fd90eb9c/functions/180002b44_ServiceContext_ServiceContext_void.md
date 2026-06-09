# ServiceContext::~ServiceContext(void)

- ea: `0x180002b44`
- end: `0x180002b49`
- name: `??1ServiceContext@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(ServiceContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800178f0`

## callees

- `0x180002b50`

## pseudocode

```c
// attributes: thunk
void __fastcall ServiceContext::~ServiceContext(ServiceContext *this)
{
  ProcessRefCount::~ProcessRefCount(this);
}

```

## disassembly

```asm
0x180002b44  jmp     ??1ProcessRefCount@@QEAA@XZ; ProcessRefCount::~ProcessRefCount(void)
```
