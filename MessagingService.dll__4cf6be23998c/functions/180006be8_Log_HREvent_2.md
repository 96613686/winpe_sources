# Log_HREvent_2

- ea: `0x180006be8`
- end: `0x180006bff`
- name: `Log_HREvent_2`
- size: `23`
- prototype: `void __fastcall(__int64, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004c48`
- `0x180006d00`
- `0x180006df0`

## callees

- `0x180006858`
- `0x1800068a8`

## pseudocode

```c
void __fastcall Log_HREvent_2(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  if ( a2 )
    EventWriteCommsErrorPropagateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\textmessagetransport.cpp",
      (unsigned int)a4,
      a4);
  else
    EventWriteCommsErrorOriginateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\textmessagetransport.cpp",
      (unsigned int)a4,
      a4);
}

```

## disassembly

```asm
0x180006be8  test    edx, edx
0x180006bea  mov     r8d, r9d; unsigned int
0x180006bed  lea     rdx, aOnecoreuapNetM; "onecoreuap\\net\\messaging\\desktoptran"...
0x180006bf4  jnz     ?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)
0x180006bfa  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
