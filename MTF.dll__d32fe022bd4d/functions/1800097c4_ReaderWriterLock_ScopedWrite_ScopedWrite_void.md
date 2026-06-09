# ReaderWriterLock::ScopedWrite::~ScopedWrite(void)

- ea: `0x1800097c4`
- end: `0x1800097ce`
- name: `??1ScopedWrite@ReaderWriterLock@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ReaderWriterLock::ScopedWrite *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002c75b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800097c7`

## pseudocode

```c
void __fastcall ReaderWriterLock::ScopedWrite::~ScopedWrite(PSRWLOCK *this)
{
  ReleaseSRWLockExclusive(*this);
}

```

## disassembly

```asm
0x1800097c4  mov     rcx, [rcx]
0x1800097c7  jmp     cs:__imp_ReleaseSRWLockExclusive
```
