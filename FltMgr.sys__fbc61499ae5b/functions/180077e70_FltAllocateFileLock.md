# FltAllocateFileLock

- ea: `0x180077e70`
- end: `0x180077eee`
- name: `FltAllocateFileLock`
- size: `126`
- prototype: `PFILE_LOCK __stdcall(PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE CompleteLockCallbackDataRoutine, PUNLOCK_ROUTINE UnlockRoutine)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082710`

## callees

- `0x180077e70`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180077ea9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180077ea9`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x180077eca`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x180077eca`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x180077e85`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x180077e85`

## pseudocode

```c
PFILE_LOCK __stdcall FltAllocateFileLock(
        PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE CompleteLockCallbackDataRoutine,
        PUNLOCK_ROUTINE UnlockRoutine)
{
  FILE_LOCK *v5; // rax
  FILE_LOCK *v6; // rsi

  if ( !CompleteLockCallbackDataRoutine )
    return FsRtlAllocateFileLock(0, UnlockRoutine);
  v5 = (FILE_LOCK *)ExAllocateFromPagedLookasideList(&stru_18003F4C0);
  v6 = v5;
  if ( v5 )
  {
    FsRtlInitializeFileLock(v5, FltpCompleteLockIrpRoutine, UnlockRoutine);
    v6[1].CompleteLockIrpRoutine = (PCOMPLETE_LOCK_IRP_ROUTINE)CompleteLockCallbackDataRoutine;
  }
  return v6;
}

```

## disassembly

```asm
0x180077e70  mov     [rsp+arg_8], rbx
0x180077e75  push    rdi
0x180077e76  sub     rsp, 20h
0x180077e7a  mov     rdi, rdx
0x180077e7d  mov     rbx, rcx
0x180077e80  test    rcx, rcx
0x180077e83  jnz     short loc_180077E9D
0x180077e85  call    cs:__imp_FsRtlAllocateFileLock
0x180077e8c  nop     dword ptr [rax+rax+00h]
0x180077e91  mov     rbx, [rsp+28h+arg_8]
0x180077e96  add     rsp, 20h
0x180077e9a  pop     rdi
0x180077e9b  retn
0x180077e9d  lea     rcx, stru_18003F4C0; Lookaside
0x180077ea4  mov     [rsp+28h+arg_0], rsi
0x180077ea9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180077eb0  nop     dword ptr [rax+rax+00h]
0x180077eb5  mov     rsi, rax
0x180077eb8  test    rax, rax
0x180077ebb  jz      short loc_180077EDA
0x180077ebd  mov     r8, rdi; UnlockRoutine
0x180077ec0  lea     rdx, FltpCompleteLockIrpRoutine; CompleteLockIrpRoutine
0x180077ec7  mov     rcx, rax; FileLock
0x180077eca  call    cs:__imp_FsRtlInitializeFileLock
0x180077ed1  nop     dword ptr [rax+rax+00h]
0x180077ed6  mov     [rsi+60h], rbx
0x180077eda  mov     rbx, [rsp+28h+arg_8]
0x180077edf  mov     rax, rsi
0x180077ee2  mov     rsi, [rsp+28h+arg_0]
0x180077ee7  add     rsp, 20h
0x180077eeb  pop     rdi
0x180077eec  retn
```
