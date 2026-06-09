# ProcessCacheMiss

- ea: `0x140046734`
- end: `0x1400468ed`
- name: `ProcessCacheMiss`
- size: `441`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PLOCK_STATE_EX LockState, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000418c`

## callees

- `0x140006240`
- `0x140007ee0`
- `0x140009520`
- `0x140009e00`
- `0x14003a440`
- `0x140046734`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14004681e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14004681e`
- `NDIS!NdisAcquireRWLockRead` at `0x1400468b5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400468b5`
- `NDIS!NdisReleaseRWLock` at `0x14004677c`
- `NDIS!NdisReleaseRWLock` at `0x14004687b`
- `NDIS!NdisReleaseRWLock` at `0x14004677c`
- `NDIS!NdisReleaseRWLock` at `0x14004687b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140046804`
- `NDIS!NdisAcquireRWLockWrite` at `0x140046804`

## string_xrefs

- `0x1400468c6`: `ProcessCacheMiss`

## pseudocode

```c
__int64 __fastcall ProcessCacheMiss(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PLOCK_STATE_EX LockState,
        _BYTE *a8,
        _BYTE *a9)
{
  _BYTE *v9; // r14
  PNPAGED_LOOKASIDE_LIST v11; // rcx
  struct _LOCK_STATE_EX *v13; // rdx
  __int64 v14; // rbx
  int v16; // r9d
  __int64 v17; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v18; // rdi
  __int64 v19; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+78h] [rbp+20h] BYREF

  v9 = a9;
  v11 = gWfpGlobal;
  v13 = LockState;
  v14 = 0;
  Entry = 0;
  *a9 = 0;
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v11[13].L.ListEntry.Flink, v13);
  if ( *(_DWORD *)(a1 + 4) <= *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL) )
  {
    v17 = ConstructNewCacheEntry(a1, a2, a3, v16, a5, a6, (__int64)&Entry);
    v18 = Entry;
    v14 = v17;
    if ( !v17 )
    {
      if ( !Entry )
      {
        *v9 = 1;
        goto LABEL_11;
      }
      NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, LockState, 1u);
      if ( RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), v18, v18->Signature, 0) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
        InsertCacheEntryLru(a1, v18);
        *a8 = 1;
      }
      else
      {
        v14 = WfpReportSysErrorAsNtStatus(v19, "RtlInsertEntryHashTable", 3221225473LL, 1);
      }
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, LockState);
      if ( !v14 )
        goto LABEL_11;
    }
    if ( v18 )
      FreeCacheEntry(a1, v18);
  }
LABEL_11:
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, LockState, 1u);
  if ( v14 )
    WfpReportError(v14, "ProcessCacheMiss");
  return v14;
}

```

## disassembly

```asm
0x140046734  mov     rax, rsp
0x140046737  mov     [rax+8], rbx
0x14004673b  mov     [rax+10h], rsi
0x14004673f  mov     [rax+20h], r9
0x140046743  push    rdi
0x140046744  push    r14
0x140046746  push    r15
0x140046748  sub     rsp, 40h
0x14004674c  mov     r14, [rsp+58h+arg_40]
0x140046754  mov     rsi, rcx
0x140046757  mov     rcx, cs:gWfpGlobal
0x14004675e  mov     r15, rdx
0x140046761  mov     rdx, [rsp+58h+LockState]; LockState
0x140046769  xor     ebx, ebx
0x14004676b  mov     rdi, r8
0x14004676e  mov     [rax+20h], rbx
0x140046772  mov     [r14], bl
0x140046775  mov     rcx, [rcx+6C0h]; Lock
0x14004677c  call    cs:__imp_NdisReleaseRWLock
0x140046783  nop     dword ptr [rax+rax+00h]
0x140046788  mov     r8d, [rsi+4]
0x14004678c  mov     rax, [rsi+10h]
0x140046790  cmp     r8d, [rax+4]
0x140046794  jg      loc_14004689C
0x14004679a  lea     rax, [rsp+58h+Entry]
0x14004679f  mov     r8, rdi
0x1400467a2  mov     [rsp+58h+var_28], rax
0x1400467a7  mov     rdx, r15
0x1400467aa  mov     rax, [rsp+58h+arg_28]
0x1400467b2  mov     rcx, rsi
0x1400467b5  mov     [rsp+58h+var_30], rax
0x1400467ba  mov     rax, [rsp+58h+arg_20]
0x1400467c2  mov     [rsp+58h+var_38], rax
0x1400467c7  call    ConstructNewCacheEntry
0x1400467cc  mov     rdi, [rsp+58h+Entry]
0x1400467d1  mov     rbx, rax
0x1400467d4  test    rax, rax
0x1400467d7  jnz     loc_14004688C
0x1400467dd  test    rdi, rdi
0x1400467e0  jnz     short loc_1400467EB
0x1400467e2  mov     byte ptr [r14], 1
0x1400467e6  jmp     loc_14004689C
0x1400467eb  mov     rcx, cs:gWfpGlobal
0x1400467f2  mov     r8b, 1; Flags
0x1400467f5  mov     rdx, [rsp+58h+LockState]; LockState
0x1400467fd  mov     rcx, [rcx+6C0h]; Lock
0x140046804  call    cs:__imp_NdisAcquireRWLockWrite
0x14004680b  nop     dword ptr [rax+rax+00h]
0x140046810  mov     r8, [rdi+10h]; Signature
0x140046814  xor     r9d, r9d; Context
0x140046817  mov     rcx, [rsi+8]; HashTable
0x14004681b  mov     rdx, rdi; Entry
0x14004681e  call    cs:__imp_RtlInsertEntryHashTable
0x140046825  nop     dword ptr [rax+rax+00h]
0x14004682a  test    al, al
0x14004682c  jnz     short loc_14004684B
0x14004682e  mov     r9d, 1
0x140046834  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x14004683b  mov     r8d, 0C0000001h
0x140046841  call    WfpReportSysErrorAsNtStatus
0x140046846  mov     rbx, rax
0x140046849  jmp     short loc_140046865
0x14004684b  lock inc dword ptr [rsi+4]
0x14004684f  mov     rdx, rdi
0x140046852  mov     rcx, rsi
0x140046855  call    InsertCacheEntryLru
0x14004685a  mov     rax, [rsp+58h+arg_38]
0x140046862  mov     byte ptr [rax], 1
0x140046865  mov     rcx, cs:gWfpGlobal
0x14004686c  mov     rdx, [rsp+58h+LockState]; LockState
0x140046874  mov     rcx, [rcx+6C0h]; Lock
0x14004687b  call    cs:__imp_NdisReleaseRWLock
0x140046882  nop     dword ptr [rax+rax+00h]
0x140046887  test    rbx, rbx
0x14004688a  jz      short loc_14004689C
0x14004688c  test    rdi, rdi
0x14004688f  jz      short loc_14004689C
0x140046891  mov     rdx, rdi
0x140046894  mov     rcx, rsi
0x140046897  call    FreeCacheEntry
0x14004689c  mov     rcx, cs:gWfpGlobal
0x1400468a3  mov     r8b, 1; Flags
0x1400468a6  mov     rdx, [rsp+58h+LockState]; LockState
0x1400468ae  mov     rcx, [rcx+6C0h]; Lock
0x1400468b5  call    cs:__imp_NdisAcquireRWLockRead
0x1400468bc  nop     dword ptr [rax+rax+00h]
0x1400468c1  test    rbx, rbx
0x1400468c4  jz      short loc_1400468D5
0x1400468c6  lea     rdx, aProcesscachemi; "ProcessCacheMiss"
0x1400468cd  mov     rcx, rbx
0x1400468d0  call    WfpReportError
0x1400468d5  mov     rsi, [rsp+58h+arg_8]
0x1400468da  mov     rax, rbx
0x1400468dd  mov     rbx, [rsp+58h+arg_0]
0x1400468e2  add     rsp, 40h
0x1400468e6  pop     r15
0x1400468e8  pop     r14
0x1400468ea  pop     rdi
0x1400468eb  retn
```
