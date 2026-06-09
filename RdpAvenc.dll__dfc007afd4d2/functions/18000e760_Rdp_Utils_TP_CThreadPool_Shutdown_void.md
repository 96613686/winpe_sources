# Rdp::Utils::TP::CThreadPool::Shutdown(void)

- ea: `0x18000e760`
- end: `0x18000e826`
- name: `?Shutdown@CThreadPool@TP@Utils@Rdp@@QEAAXXZ`
- size: `198`
- prototype: `void __fastcall(Rdp::Utils::TP::CThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000da54`
- `0x18003c360`

## callees

- `0x180007018`
- `0x18000ba24`
- `0x18000e760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e810`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000e7dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000e7dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000e79b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000e79b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e7a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e7a4`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::CThreadPool::Shutdown(Rdp::Utils::TP::CThreadPool *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_POOL *v4; // rsi
  DWORD v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+28h] [rbp-10h]

  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    &v8,
    (char *)this + 104);
  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    LastError = GetLastError();
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(v2);
    SetLastError(LastError);
    *((_QWORD *)this + 3) = 0;
    memset_0((char *)this + 32, 0, 0x48u);
    v4 = (struct _TP_POOL *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      v5 = GetLastError();
      CloseThreadpool(v4);
      SetLastError(v5);
    }
    *((_QWORD *)this + 2) = 0;
  }
  if ( v9 )
  {
    v6 = v8;
    if ( (*(_DWORD *)(v8 + 76))-- == 1 )
    {
      *(_DWORD *)(v6 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 16));
    }
  }
}

```

## disassembly

```asm
0x18000e760  mov     [rsp+arg_8], rbx
0x18000e765  mov     [rsp+arg_10], rsi
0x18000e76a  push    rdi
0x18000e76b  sub     rsp, 30h
0x18000e76f  mov     rdi, rcx
0x18000e772  lea     rdx, [rcx+68h]
0x18000e776  lea     rcx, [rsp+38h+var_18]
0x18000e77b  call    ??0?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &)
0x18000e780  mov     rsi, [rdi+18h]
0x18000e784  test    rsi, rsi
0x18000e787  jz      short loc_18000E7F3
0x18000e789  call    cs:__imp_GetLastError
0x18000e78f  xor     r8d, r8d; pvCleanupContext
0x18000e792  mov     rcx, rsi; ptpcg
0x18000e795  mov     ebx, eax
0x18000e797  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000e79b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000e7a1  mov     rcx, rsi; ptpcg
0x18000e7a4  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000e7aa  mov     ecx, ebx; dwErrCode
0x18000e7ac  call    cs:__imp_SetLastError
0x18000e7b2  xor     edx, edx; Val
0x18000e7b4  mov     qword ptr [rdi+18h], 0
0x18000e7bc  lea     rcx, [rdi+20h]; void *
0x18000e7c0  lea     r8d, [rdx+48h]; Size
0x18000e7c4  call    memset_0
0x18000e7c9  mov     rsi, [rdi+10h]
0x18000e7cd  test    rsi, rsi
0x18000e7d0  jz      short loc_18000E7EB
0x18000e7d2  call    cs:__imp_GetLastError
0x18000e7d8  mov     rcx, rsi; ptpp
0x18000e7db  mov     ebx, eax
0x18000e7dd  call    cs:__imp_CloseThreadpool
0x18000e7e3  mov     ecx, ebx; dwErrCode
0x18000e7e5  call    cs:__imp_SetLastError
0x18000e7eb  mov     qword ptr [rdi+10h], 0
0x18000e7f3  cmp     [rsp+38h+var_10], 0
0x18000e7f8  jz      short loc_18000E816
0x18000e7fa  mov     rcx, [rsp+38h+var_18]
0x18000e7ff  sub     dword ptr [rcx+4Ch], 1
0x18000e803  jnz     short loc_18000E816
0x18000e805  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x18000e80c  add     rcx, 10h; SRWLock
0x18000e810  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e816  mov     rbx, [rsp+38h+arg_8]
0x18000e81b  mov     rsi, [rsp+38h+arg_10]
0x18000e820  add     rsp, 30h
0x18000e824  pop     rdi
0x18000e825  retn
```
