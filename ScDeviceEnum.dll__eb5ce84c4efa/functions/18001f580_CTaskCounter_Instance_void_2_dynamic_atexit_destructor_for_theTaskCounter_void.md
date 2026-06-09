# `CTaskCounter::Instance(void)'::`2'::`dynamic atexit destructor for 'theTaskCounter''(void)

- ea: `0x18001f580`
- end: `0x18001f58c`
- name: `??__FtheTaskCounter@?1??Instance@CTaskCounter@@SAAEAV1@XZ@YAXXZ`
- size: `12`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000770c`

## pseudocode

```c
void __fastcall `CTaskCounter::Instance'::`2'::`dynamic atexit destructor for 'theTaskCounter''()
{
  CTaskCounter::~CTaskCounter((CTaskCounter *)&`CTaskCounter::Instance'::`2'::theTaskCounter);
}

```

## disassembly

```asm
0x18001f580  lea     rcx, ?theTaskCounter@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4V2@A; this
0x18001f587  jmp     ??1CTaskCounter@@QEAA@XZ; CTaskCounter::~CTaskCounter(void)
```
