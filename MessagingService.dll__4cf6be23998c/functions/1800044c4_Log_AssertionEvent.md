# Log_AssertionEvent

- ea: `0x1800044c4`
- end: `0x1800044d5`
- name: `Log_AssertionEvent`
- size: `17`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004ba0`
- `0x180004ea0`

## callees

- `0x180006858`

## string_xrefs

- `0x1800044c4`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
void __fastcall Log_AssertionEvent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  EventWriteCommsErrorOriginateEvent(
    2147549183LL,
    "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp",
    a3,
    a4);
}

```

## disassembly

```asm
0x1800044c4  lea     rdx, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800044cb  mov     ecx, 8000FFFFh; int
0x1800044d0  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
