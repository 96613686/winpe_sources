# _dynamic_atexit_destructor_for__g_semStaticLock__

- ea: `0x1800144a0`
- end: `0x1800144c5`
- name: `_dynamic_atexit_destructor_for__g_semStaticLock__`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144b9`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_semStaticLock__()
{
  qword_18001F950 = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_18001F958);
}

```

## disassembly

```asm
0x1800144a0  sub     rsp, 28h
0x1800144a4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800144ab  mov     cs:qword_18001F950, rax
0x1800144b2  lea     rcx, stru_18001F958; lpCriticalSection
0x1800144b9  call    cs:__imp_DeleteCriticalSection
0x1800144bf  nop
0x1800144c0  add     rsp, 28h
0x1800144c4  retn
```
