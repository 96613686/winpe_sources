# CSmStoreTransaction::IsOwned(ISmStore *)

- ea: `0x1800179ac`
- end: `0x1800179d9`
- name: `?IsOwned@CSmStoreTransaction@@SA_NPEAUISmStore@@@Z`
- size: `45`
- prototype: `bool __fastcall(struct ISmStore *)`
- caller_count: `23`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180012210`
- `0x1800142a4`
- `0x180014448`
- `0x180019e94`
- `0x18001eb30`
- `0x18001f8f4`
- `0x18001fab4`
- `0x180021fd0`
- `0x1800224c4`
- `0x1800237fc`
- `0x180032f9c`
- `0x180033c88`
- `0x180035170`
- `0x180035448`
- `0x1800355e8`
- `0x180037640`
- `0x1800383d0`
- `0x180038a90`
- `0x18003b044`
- `0x18003cb00`
- `0x18003dc50`
- `0x180041cc0`
- `0x180044ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179c8`

## pseudocode

```c
bool __fastcall CSmStoreTransaction::IsOwned(struct ISmStore *a1)
{
  signed __int32 v1; // ebx

  v1 = _InterlockedCompareExchange(
         (volatile signed __int32 *)&CSmStoreTransaction::m_storeLockOwningThread,
         CSmStoreTransaction::m_storeLockOwningThread,
         GetCurrentThreadId());
  return v1 == GetCurrentThreadId();
}

```

## disassembly

```asm
0x1800179ac  push    rbx
0x1800179ae  sub     rsp, 20h
0x1800179b2  call    cs:__imp_GetCurrentThreadId
0x1800179b8  mov     ecx, cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x1800179be  lock cmpxchg cs:?m_storeLockOwningThread@CSmStoreTransaction@@1KC, ecx; ulong volatile CSmStoreTransaction::m_storeLockOwningThread
0x1800179c6  mov     ebx, eax
0x1800179c8  call    cs:__imp_GetCurrentThreadId
0x1800179ce  cmp     ebx, eax
0x1800179d0  setz    al
0x1800179d3  add     rsp, 20h
0x1800179d7  pop     rbx
0x1800179d8  retn
```
