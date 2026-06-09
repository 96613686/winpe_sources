# IndexHashDelete

- ea: `0x14003b0e0`
- end: `0x14003b193`
- name: `IndexHashDelete`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009520`
- `0x140009c50`
- `0x140009e00`
- `0x14003b0e0`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003b11d`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003b11d`
- `NDIS!NdisReleaseRWLock` at `0x14003b145`
- `NDIS!NdisReleaseRWLock` at `0x14003b145`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003b107`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003b107`

## string_xrefs

- `0x14003b16b`: `RtlRemoveEntryHashTable`
- `0x14003b182`: `IndexHashDelete`

## pseudocode

```c
__int64 __fastcall IndexHashDelete(__int64 a1, __int64 a2)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v2; // rbx
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(struct _RTL_DYNAMIC_HASH_TABLE_ENTRY **)(a2 + 32);
  *(_WORD *)&LockState.OldIrql = 0;
  v4 = *(struct _NDIS_RW_LOCK_EX **)a1;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v4, &LockState, 1u);
  if ( RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), v2, 0) )
  {
    v6 = 0;
    WfpRestructureHashtable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16));
    *(_QWORD *)(a1 + 24) -= 32LL;
  }
  else
  {
    v6 = WfpReportSysErrorAsNtStatus(v5, "RtlRemoveEntryHashTable", 3221225473LL, 1);
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, &LockState);
  if ( v6 )
    WfpReportError(v6, "IndexHashDelete");
  return v6;
}

```

## disassembly

```asm
0x14003b0e0  mov     [rsp+arg_8], rbx
0x14003b0e5  push    rdi
0x14003b0e6  sub     rsp, 20h
0x14003b0ea  mov     rbx, [rdx+20h]
0x14003b0ee  xor     eax, eax
0x14003b0f0  mov     rdi, rcx
0x14003b0f3  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14003b0f8  mov     rcx, [rcx]; Lock
0x14003b0fb  lea     rdx, [rsp+28h+LockState]; LockState
0x14003b100  mov     r8b, 1; Flags
0x14003b103  mov     [rsp+28h+LockState.Flags], al
0x14003b107  call    cs:__imp_NdisAcquireRWLockWrite
0x14003b10e  nop     dword ptr [rax+rax+00h]
0x14003b113  mov     rcx, [rdi+10h]; HashTable
0x14003b117  xor     r8d, r8d; Context
0x14003b11a  mov     rdx, rbx; Entry
0x14003b11d  call    cs:__imp_RtlRemoveEntryHashTable
0x14003b124  nop     dword ptr [rax+rax+00h]
0x14003b129  test    al, al
0x14003b12b  jz      short loc_14003B165
0x14003b12d  mov     rcx, [rdi+10h]; HashTable
0x14003b131  xor     ebx, ebx
0x14003b133  call    WfpRestructureHashtable
0x14003b138  add     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFE0h
0x14003b13d  mov     rcx, [rdi]; Lock
0x14003b140  lea     rdx, [rsp+28h+LockState]; LockState
0x14003b145  call    cs:__imp_NdisReleaseRWLock
0x14003b14c  nop     dword ptr [rax+rax+00h]
0x14003b151  test    rbx, rbx
0x14003b154  jnz     short loc_14003B182
0x14003b156  mov     rax, rbx
0x14003b159  mov     rbx, [rsp+28h+arg_8]
0x14003b15e  add     rsp, 20h
0x14003b162  pop     rdi
0x14003b163  retn
0x14003b165  mov     r9d, 1
0x14003b16b  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x14003b172  mov     r8d, 0C0000001h
0x14003b178  call    WfpReportSysErrorAsNtStatus
0x14003b17d  mov     rbx, rax
0x14003b180  jmp     short loc_14003B13D
0x14003b182  lea     rdx, aIndexhashdelet; "IndexHashDelete"
0x14003b189  mov     rcx, rbx
0x14003b18c  call    WfpReportError
0x14003b191  jmp     short loc_14003B156
```
