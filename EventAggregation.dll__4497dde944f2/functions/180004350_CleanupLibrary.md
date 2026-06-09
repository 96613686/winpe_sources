# CleanupLibrary

- ea: `0x180004350`
- end: `0x180004470`
- name: `CleanupLibrary`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004060`

## callees

- `0x180001460`
- `0x1800016c0`
- `0x180004350`
- `0x180008ca8`
- `0x180008d98`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000439d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000439d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004374`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004374`
- `ntdll!RtlDeleteHashTable` at `0x1800043eb`
- `ntdll!RtlDeleteHashTable` at `0x1800043eb`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800043b0`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800043b0`
- `ntdll!RtlRemoveEntryHashTable` at `0x180004415`
- `ntdll!RtlRemoveEntryHashTable` at `0x180004415`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800043dd`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800043dd`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800043c7`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180004423`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800043c7`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180004423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000437a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000437a`

## pseudocode

```c
__int64 CleanupLibrary()
{
  __int64 v0; // rbx
  __int64 result; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rcx
  _OWORD v10[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-18h]

  memset(v10, 0, sizeof(v10));
  v11 = 0;
  RtlAcquireSRWLockExclusive(AggregateEventListLock);
  GetCurrentThreadId();
  v0 = qword_180012148;
  qword_180012148 = 0;
  dword_1800121B8 = 0;
  result = RtlReleaseSRWLockExclusive(AggregateEventListLock);
  if ( v0 )
  {
    if ( (unsigned __int8)RtlInitEnumerationHashTable(v0, v10) )
    {
      v6 = RtlEnumerateEntryHashTable(v0, v10);
      while ( v6 )
      {
        v7 = v6;
        RtlRemoveEntryHashTable(v0, v6, 0);
        v8 = RtlEnumerateEntryHashTable(v0, v10);
        v9 = v6;
        v6 = v8;
        EaiDisableAggregateEvent(v9);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 136), 0xFFFFFFFF) == 1 )
          EaiFreeAggregateEvent(v7);
      }
      RtlEndEnumerationHashTable(v0, v10);
    }
    result = RtlDeleteHashTable(v0);
  }
  if ( BrokerInternalClientInitialized )
  {
    BripCleanupEventTable(v3, v2, v4, v5, *(_QWORD *)&v10[0]);
    result = BripCleanupBindingTable();
    BrokerInternalClientInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004350  sub     rsp, 58h
0x180004354  xorps   xmm0, xmm0
0x180004357  mov     [rsp+58h+arg_0], rbx
0x18000435c  xor     eax, eax
0x18000435e  lea     rcx, AggregateEventListLock
0x180004365  movups  [rsp+58h+var_38], xmm0
0x18000436a  mov     [rsp+58h+var_18], rax
0x18000436f  movups  [rsp+58h+var_28], xmm0
0x180004374  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000437a  call    cs:__imp_GetCurrentThreadId
0x180004380  mov     rbx, cs:qword_180012148
0x180004387  lea     rcx, AggregateEventListLock
0x18000438e  xor     eax, eax
0x180004390  mov     cs:qword_180012148, rax
0x180004397  mov     cs:dword_1800121B8, eax
0x18000439d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800043a3  test    rbx, rbx
0x1800043a6  jz      short loc_1800043F1
0x1800043a8  lea     rdx, [rsp+58h+var_38]
0x1800043ad  mov     rcx, rbx
0x1800043b0  call    cs:__imp_RtlInitEnumerationHashTable
0x1800043b6  test    al, al
0x1800043b8  jz      short loc_1800043E8
0x1800043ba  lea     rdx, [rsp+58h+var_38]
0x1800043bf  mov     [rsp+58h+var_8], rdi
0x1800043c4  mov     rcx, rbx
0x1800043c7  call    cs:__imp_RtlEnumerateEntryHashTable
0x1800043cd  mov     rdi, rax
0x1800043d0  test    rax, rax
0x1800043d3  jnz     short loc_180004404
0x1800043d5  lea     rdx, [rsp+58h+var_38]
0x1800043da  mov     rcx, rbx
0x1800043dd  call    cs:__imp_RtlEndEnumerationHashTable
0x1800043e3  mov     rdi, [rsp+58h+var_8]
0x1800043e8  mov     rcx, rbx
0x1800043eb  call    cs:__imp_RtlDeleteHashTable
0x1800043f1  cmp     cs:BrokerInternalClientInitialized, 0
0x1800043f8  mov     rbx, [rsp+58h+arg_0]
0x1800043fd  jnz     short loc_18000445D
0x1800043ff  add     rsp, 58h
0x180004403  retn
0x180004404  mov     [rsp+58h+arg_8], rsi
0x180004409  xor     r8d, r8d
0x18000440c  mov     rdx, rdi
0x18000440f  mov     rcx, rbx
0x180004412  mov     rsi, rdi
0x180004415  call    cs:__imp_RtlRemoveEntryHashTable
0x18000441b  lea     rdx, [rsp+58h+var_38]
0x180004420  mov     rcx, rbx
0x180004423  call    cs:__imp_RtlEnumerateEntryHashTable
0x180004429  mov     rcx, rsi
0x18000442c  mov     rdi, rax
0x18000442f  call    EaiDisableAggregateEvent
0x180004434  mov     eax, 0FFFFFFFFh
0x180004439  lock xadd [rsi+88h], eax
0x180004441  cmp     eax, 1
0x180004444  jnz     short loc_18000444E
0x180004446  mov     rcx, rsi
0x180004449  call    EaiFreeAggregateEvent
0x18000444e  test    rdi, rdi
0x180004451  jnz     short loc_180004409
0x180004453  mov     rsi, [rsp+58h+arg_8]
0x180004458  jmp     loc_1800043D5
0x18000445d  call    BripCleanupEventTable
0x180004462  call    BripCleanupBindingTable
0x180004467  mov     cs:BrokerInternalClientInitialized, 0
0x18000446e  jmp     short loc_1800043FF
```
