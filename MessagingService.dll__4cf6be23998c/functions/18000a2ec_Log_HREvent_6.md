# Log_HREvent_6

- ea: `0x18000a2ec`
- end: `0x18000a303`
- name: `Log_HREvent_6`
- size: `23`
- prototype: `void __fastcall(__int64, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1c0`
- `0x18000a328`
- `0x18000a78c`

## callees

- `0x180006858`
- `0x1800068a8`

## pseudocode

```c
void __fastcall Log_HREvent_6(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  if ( a2 )
    EventWriteCommsErrorPropagateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\textmessage.cpp",
      (unsigned int)a4,
      a4);
  else
    EventWriteCommsErrorOriginateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\textmessage.cpp",
      (unsigned int)a4,
      a4);
}

```

## disassembly

```asm
0x18000a2ec  test    edx, edx
0x18000a2ee  mov     r8d, r9d; unsigned int
0x18000a2f1  lea     rdx, aOnecoreuapNetM_2; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000a2f8  jnz     ?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)
0x18000a2fe  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
