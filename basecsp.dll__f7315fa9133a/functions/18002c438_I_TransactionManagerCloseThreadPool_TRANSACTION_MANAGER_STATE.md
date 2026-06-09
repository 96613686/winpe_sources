# I_TransactionManagerCloseThreadPool(_TRANSACTION_MANAGER_STATE *)

- ea: `0x18002c438`
- end: `0x18002c478`
- name: `?I_TransactionManagerCloseThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z`
- size: `64`
- prototype: `unsigned int __fastcall(struct _TRANSACTION_MANAGER_STATE *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c40c`
- `0x18002c480`
- `0x18002c9e0`

## callees

- `0x18002c438`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002c451`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002c451`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002c45b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002c45b`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerCloseThreadPool(struct _TRANSACTION_MANAGER_STATE *a1)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx

  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)a1 + 11);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)a1 + 11));
    *((_QWORD *)a1 + 11) = 0;
  }
  *((_DWORD *)a1 + 24) = 0;
  return 0;
}

```

## disassembly

```asm
0x18002c438  push    rbx
0x18002c43a  sub     rsp, 20h
0x18002c43e  mov     rbx, rcx
0x18002c441  mov     rcx, [rcx+58h]; ptpcg
0x18002c445  test    rcx, rcx
0x18002c448  jz      short loc_18002C469
0x18002c44a  xor     r8d, r8d; pvCleanupContext
0x18002c44d  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002c451  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002c457  mov     rcx, [rbx+58h]; ptpcg
0x18002c45b  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002c461  mov     qword ptr [rbx+58h], 0
0x18002c469  mov     dword ptr [rbx+60h], 0
0x18002c470  xor     eax, eax
0x18002c472  add     rsp, 20h
0x18002c476  pop     rbx
0x18002c477  retn
```
