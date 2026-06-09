# Log_HREvent

- ea: `0x18000307c`
- end: `0x180003087`
- name: `Log_HREvent`
- size: `11`
- prototype: `void __fastcall(__int64, __int64, char *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003090`
- `0x1800034a0`
- `0x1800035d0`

## callees

- `0x1800068a8`

## pseudocode

```c
void __fastcall Log_HREvent(__int64 a1, __int64 a2, char *a3, __int64 a4)
{
  EventWriteCommsErrorPropagateEvent(a1, a3, (unsigned int)a4, a4);
}

```

## disassembly

```asm
0x18000307c  mov     rdx, r8; char *
0x18000307f  mov     r8d, r9d; unsigned int
0x180003082  jmp     ?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)
```
