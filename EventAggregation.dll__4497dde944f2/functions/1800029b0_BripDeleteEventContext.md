# BripDeleteEventContext

- ea: `0x1800029b0`
- end: `0x180002a35`
- name: `BripDeleteEventContext`
- size: `133`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002130`

## callees

- `0x1800029b0`
- `0x180002a40`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002a20`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002a20`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800029c0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800029c0`
- `ntdll!RtlFreeHeap` at `0x180002a07`
- `ntdll!RtlFreeHeap` at `0x180002a07`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800029ef`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800029ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029c6`

## pseudocode

```c
__int64 __fastcall BripDeleteEventContext(void *Source1)
{
  __int64 EventContextByEventId; // rax
  void *v3; // rbx
  unsigned int v4; // ebx

  RtlAcquireSRWLockExclusive(&BrokeredEventTableLock);
  dword_1800121A8 = GetCurrentThreadId();
  EventContextByEventId = BripFindEventContextByEventId(Source1);
  v3 = (void *)EventContextByEventId;
  if ( EventContextByEventId )
  {
    RtlRemoveEntryHashTable(BrokeredEventTable, EventContextByEventId, 0);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v4 = 0;
  }
  else
  {
    v4 = -1073741275;
  }
  dword_1800121A8 = 0;
  RtlReleaseSRWLockExclusive(&BrokeredEventTableLock);
  return v4;
}

```

## disassembly

```asm
0x1800029b0  push    rbx
0x1800029b2  sub     rsp, 20h
0x1800029b6  mov     rbx, rcx
0x1800029b9  lea     rcx, BrokeredEventTableLock
0x1800029c0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800029c6  call    cs:__imp_GetCurrentThreadId
0x1800029cc  mov     rcx, rbx; Source1
0x1800029cf  mov     cs:dword_1800121A8, eax
0x1800029d5  call    BripFindEventContextByEventId
0x1800029da  mov     rbx, rax
0x1800029dd  test    rax, rax
0x1800029e0  jz      short loc_180002A2E
0x1800029e2  mov     rcx, cs:BrokeredEventTable
0x1800029e9  xor     r8d, r8d
0x1800029ec  mov     rdx, rax
0x1800029ef  call    cs:__imp_RtlRemoveEntryHashTable
0x1800029f5  mov     rcx, gs:60h
0x1800029fe  mov     r8, rbx; P
0x180002a01  xor     edx, edx; Flags
0x180002a03  mov     rcx, [rcx+30h]; HeapHandle
0x180002a07  call    cs:__imp_RtlFreeHeap
0x180002a0d  xor     ebx, ebx
0x180002a0f  lea     rcx, BrokeredEventTableLock
0x180002a16  mov     cs:dword_1800121A8, 0
0x180002a20  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002a26  mov     eax, ebx
0x180002a28  add     rsp, 20h
0x180002a2c  pop     rbx
0x180002a2d  retn
0x180002a2e  mov     ebx, 0C0000225h
0x180002a33  jmp     short loc_180002A0F
```
