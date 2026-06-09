# _TraceAllowedByRateLimiter_::_2_::_dynamic_atexit_destructor_for__s_comtraceRateLimiter__

- ea: `0x14000f4a0`
- end: `0x14000f4ae`
- name: `_TraceAllowedByRateLimiter_::_2_::_dynamic_atexit_destructor_for__s_comtraceRateLimiter__`
- size: `14`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f4a7`

## pseudocode

```c
void __fastcall TraceAllowedByRateLimiter_::_2_::_dynamic_atexit_destructor_for__s_comtraceRateLimiter__()
{
  DeleteCriticalSection(&stru_140018320);
}

```

## disassembly

```asm
0x14000f4a0  lea     rcx, stru_140018320
0x14000f4a7  jmp     cs:__imp_DeleteCriticalSection
```
