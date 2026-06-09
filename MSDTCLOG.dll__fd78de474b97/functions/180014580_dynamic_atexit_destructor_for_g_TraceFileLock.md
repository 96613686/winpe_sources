# _dynamic_atexit_destructor_for__g_TraceFileLock__

- ea: `0x180014580`
- end: `0x1800145a5`
- name: `_dynamic_atexit_destructor_for__g_TraceFileLock__`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014599`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014599`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_TraceFileLock__()
{
  g_TraceFileLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_18001F9D8);
}

```

## disassembly

```asm
0x180014580  sub     rsp, 28h
0x180014584  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18001458b  mov     cs:?g_TraceFileLock@@3VCSemExclusive@@A, rax; CSemExclusive g_TraceFileLock
0x180014592  lea     rcx, stru_18001F9D8; lpCriticalSection
0x180014599  call    cs:__imp_DeleteCriticalSection
0x18001459f  nop
0x1800145a0  add     rsp, 28h
0x1800145a4  retn
```
