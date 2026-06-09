# Log_AssertionEvent_0

- ea: `0x180009ba4`
- end: `0x180009bbb`
- name: `Log_AssertionEvent_0`
- size: `23`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009be4`

## callees

- `0x180006858`

## string_xrefs

- `0x180009baa`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\incomingmessageregistrationevent.cpp`

## pseudocode

```c
void __fastcall Log_AssertionEvent_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  EventWriteCommsErrorOriginateEvent(
    2147549183LL,
    "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\incomingmessageregistrationevent.cpp",
    73,
    a4);
}

```

## disassembly

```asm
0x180009ba4  mov     r8d, 49h ; 'I'; unsigned int
0x180009baa  lea     rdx, aOnecoreuapNetM_5; "onecoreuap\\net\\messaging\\desktoptran"...
0x180009bb1  mov     ecx, 8000FFFFh; int
0x180009bb6  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
