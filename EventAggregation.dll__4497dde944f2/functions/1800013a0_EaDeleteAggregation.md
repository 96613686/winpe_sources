# EaDeleteAggregation

- ea: `0x1800013a0`
- end: `0x180001456`
- name: `EaDeleteAggregation`
- size: `182`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001170`
- `0x180004b30`

## callees

- `0x1800013a0`
- `0x180001460`
- `0x180001730`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000140b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001449`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000140b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001449`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800013b5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800013b5`
- `ntdll!RtlLookupEntryHashTable` at `0x1800013d9`
- `ntdll!RtlLookupEntryHashTable` at `0x1800013d9`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800013f4`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800013f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800013bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800013bb`

## pseudocode

```c
__int64 __fastcall EaDeleteAggregation(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 result; // rax

  if ( !a1 )
    return 3221225485LL;
  RtlAcquireSRWLockExclusive(AggregateEventListLock);
  dword_1800121B8 = GetCurrentThreadId();
  if ( qword_180012148 && (v2 = RtlLookupEntryHashTable(qword_180012148, a1, 0), (v3 = v2) != 0) )
  {
    RtlRemoveEntryHashTable(qword_180012148, v2, 0);
    dword_1800121B8 = 0;
    RtlReleaseSRWLockExclusive(AggregateEventListLock);
    result = EaiDisableAggregateEvent(v3);
    if ( (int)result >= 0 )
    {
      EaiReleaseAggregateEvent(v3);
      return 0;
    }
  }
  else
  {
    dword_1800121B8 = 0;
    RtlReleaseSRWLockExclusive(AggregateEventListLock);
    return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800013a0  push    rbx
0x1800013a2  sub     rsp, 20h
0x1800013a6  mov     rbx, rcx
0x1800013a9  test    rcx, rcx
0x1800013ac  jz      short loc_18000142D
0x1800013ae  lea     rcx, AggregateEventListLock
0x1800013b5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800013bb  call    cs:__imp_GetCurrentThreadId
0x1800013c1  mov     rcx, cs:qword_180012148
0x1800013c8  mov     cs:dword_1800121B8, eax
0x1800013ce  test    rcx, rcx
0x1800013d1  jz      short loc_180001438
0x1800013d3  xor     r8d, r8d
0x1800013d6  mov     rdx, rbx
0x1800013d9  call    cs:__imp_RtlLookupEntryHashTable
0x1800013df  mov     rbx, rax
0x1800013e2  test    rax, rax
0x1800013e5  jz      short loc_180001438
0x1800013e7  mov     rcx, cs:qword_180012148
0x1800013ee  xor     r8d, r8d
0x1800013f1  mov     rdx, rax
0x1800013f4  call    cs:__imp_RtlRemoveEntryHashTable
0x1800013fa  lea     rcx, AggregateEventListLock
0x180001401  mov     cs:dword_1800121B8, 0
0x18000140b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001411  mov     rcx, rbx
0x180001414  call    EaiDisableAggregateEvent
0x180001419  test    eax, eax
0x18000141b  js      short loc_180001427
0x18000141d  mov     rcx, rbx
0x180001420  call    EaiReleaseAggregateEvent
0x180001425  xor     eax, eax
0x180001427  add     rsp, 20h
0x18000142b  pop     rbx
0x18000142c  retn
0x18000142d  mov     eax, 0C000000Dh
0x180001432  add     rsp, 20h
0x180001436  pop     rbx
0x180001437  retn
0x180001438  lea     rcx, AggregateEventListLock
0x18000143f  mov     cs:dword_1800121B8, 0
0x180001449  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000144f  mov     eax, 0C0000225h
0x180001454  jmp     short loc_180001427
```
