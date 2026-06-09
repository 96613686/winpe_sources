# WfpPoolInit

- ea: `0x180117cdc`
- end: `0x180117da6`
- name: `WfpPoolInit`
- size: `202`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180085d50`

## callees

- `0x1800061ec`
- `0x180010db0`
- `0x180088a80`
- `0x180117cdc`
- `0x180117e3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117d5e`
- `ntdll!RtlInitializeSListHead` at `0x180117d00`
- `ntdll!RtlInitializeSListHead` at `0x180117d00`
- `ntdll!RtlInterlockedPushEntrySList` at `0x180117d2a`
- `ntdll!RtlInterlockedPushEntrySList` at `0x180117d2a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180117d4f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180117d4f`

## string_xrefs

- `0x180117d6a`: `CreateSemaphoreExW`

## pseudocode

```c
__int64 __fastcall WfpPoolInit(PSLIST_HEADER ListHead)
{
  __int64 v1; // rdi
  LONG Alignment; // r8d
  HANDLE Semaphore; // rax
  DWORD LastError; // eax
  __int64 v6; // rcx
  PSLIST_ENTRY ListEntry; // [rsp+58h] [rbp+20h] BYREF

  v1 = 0;
  ListEntry = 0;
  ListHead[2].Alignment = (ULONGLONG)WfpFreeAuditStorageEntry;
  RtlInitializeSListHead(ListHead);
  while ( 1 )
  {
    Alignment = ListHead[1].Alignment;
    if ( Alignment >= 25 )
      break;
    v1 = WfpAllocAuditStorageEntry(&ListEntry);
    if ( v1 )
      goto LABEL_7;
    RtlInterlockedPushEntrySList(ListHead, ListEntry);
    ++LODWORD(ListHead[1].Alignment);
    ++*((_DWORD *)&ListHead[1].HeaderX64 + 1);
  }
  Semaphore = CreateSemaphoreExW(0, 0, Alignment, 0, 0, 0x1F0003u);
  ListHead[1].Region = (ULONGLONG)Semaphore;
  if ( !Semaphore )
  {
    LastError = GetLastError();
    v1 = WfpReportSysErrorAsWinError(v6, "CreateSemaphoreExW", LastError, 1);
    if ( v1 )
    {
LABEL_7:
      WfpPoolShutdown(ListHead);
      WfpReportError(v1, "WfpPoolInit");
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180117cdc  mov     [rsp+arg_0], rbx
0x180117ce1  mov     [rsp+ListEntry], r9
0x180117ce6  push    rdi
0x180117ce7  sub     rsp, 30h
0x180117ceb  xor     edi, edi
0x180117ced  lea     rax, WfpFreeAuditStorageEntry
0x180117cf4  mov     [rsp+38h+ListEntry], rdi
0x180117cf9  mov     rbx, rcx
0x180117cfc  mov     [rcx+20h], rax
0x180117d00  call    cs:__imp_RtlInitializeSListHead
0x180117d06  mov     r8d, [rbx+10h]; lMaximumCount
0x180117d0a  cmp     r8d, 19h
0x180117d0e  jge     short loc_180117D38
0x180117d10  lea     rcx, [rsp+38h+ListEntry]
0x180117d15  call    WfpAllocAuditStorageEntry
0x180117d1a  mov     rdi, rax
0x180117d1d  test    rax, rax
0x180117d20  jnz     short loc_180117D81
0x180117d22  mov     rdx, [rsp+38h+ListEntry]; ListEntry
0x180117d27  mov     rcx, rbx; ListHead
0x180117d2a  call    cs:__imp_RtlInterlockedPushEntrySList
0x180117d30  inc     dword ptr [rbx+10h]
0x180117d33  inc     dword ptr [rbx+14h]
0x180117d36  jmp     short loc_180117D06
0x180117d38  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180117d40  xor     r9d, r9d; lpName
0x180117d43  xor     edx, edx; lInitialCount
0x180117d45  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180117d4d  xor     ecx, ecx; lpSemaphoreAttributes
0x180117d4f  call    cs:__imp_CreateSemaphoreExW
0x180117d55  mov     [rbx+18h], rax
0x180117d59  test    rax, rax
0x180117d5c  jnz     short loc_180117D98
0x180117d5e  call    cs:__imp_GetLastError
0x180117d64  mov     r9d, 1
0x180117d6a  lea     rdx, aCreatesemaphor; "CreateSemaphoreExW"
0x180117d71  mov     r8d, eax
0x180117d74  call    WfpReportSysErrorAsWinError
0x180117d79  mov     rdi, rax
0x180117d7c  test    rax, rax
0x180117d7f  jz      short loc_180117D98
0x180117d81  mov     rcx, rbx; ListHead
0x180117d84  call    WfpPoolShutdown
0x180117d89  lea     rdx, aWfppoolinit; "WfpPoolInit"
0x180117d90  mov     rcx, rdi
0x180117d93  call    WfpReportError
0x180117d98  mov     rbx, [rsp+38h+arg_0]
0x180117d9d  mov     rax, rdi
0x180117da0  add     rsp, 30h
0x180117da4  pop     rdi
0x180117da5  retn
```
