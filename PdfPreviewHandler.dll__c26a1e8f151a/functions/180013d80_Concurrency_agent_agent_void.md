# Concurrency::agent::~agent(void)

- ea: `0x180013d80`
- end: `0x180013d85`
- name: `j_??1agent@Concurrency@@UEAA@XZ`
- size: `5`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180013a10`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  ??1agent@Concurrency@@UEAA@XZ(this);
}

```

## disassembly

```asm
0x180013d80  jmp     ??1agent@Concurrency@@UEAA@XZ
```
