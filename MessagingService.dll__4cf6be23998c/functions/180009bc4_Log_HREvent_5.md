# Log_HREvent_5

- ea: `0x180009bc4`
- end: `0x180009bdb`
- name: `Log_HREvent_5`
- size: `23`
- prototype: `void __fastcall(__int64, int, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007930`
- `0x180009aec`
- `0x180009b70`
- `0x180009be4`
- `0x180009e58`

## callees

- `0x180006858`
- `0x1800068a8`

## string_xrefs

- `0x180009bc9`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\incomingmessageregistrationevent.cpp`

## pseudocode

```c
void __fastcall Log_HREvent_5(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  if ( a2 )
    EventWriteCommsErrorPropagateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\incomingmessageregistrationevent.cpp",
      (unsigned int)a4,
      a4);
  else
    EventWriteCommsErrorOriginateEvent(
      a1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\incomingmessageregistrationevent.cpp",
      (unsigned int)a4,
      a4);
}

```

## disassembly

```asm
0x180009bc4  test    edx, edx
0x180009bc6  mov     r8d, r9d; unsigned int
0x180009bc9  lea     rdx, aOnecoreuapNetM_5; "onecoreuap\\net\\messaging\\desktoptran"...
0x180009bd0  jnz     ?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)
0x180009bd6  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
