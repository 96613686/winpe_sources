# _dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__

- ea: `0x1800144d0`
- end: `0x1800144f5`
- name: `_dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144e9`

## pseudocode

```c
void dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__()
{
  CTraceMemoryBuffer::MemoryBufferLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_18001FA10);
}

```

## disassembly

```asm
0x1800144d0  sub     rsp, 28h
0x1800144d4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800144db  mov     cs:?MemoryBufferLock@CTraceMemoryBuffer@@0VCSemExclusive@@A, rax; CSemExclusive CTraceMemoryBuffer::MemoryBufferLock
0x1800144e2  lea     rcx, stru_18001FA10; lpCriticalSection
0x1800144e9  call    cs:__imp_DeleteCriticalSection
0x1800144ef  nop
0x1800144f0  add     rsp, 28h
0x1800144f4  retn
```
