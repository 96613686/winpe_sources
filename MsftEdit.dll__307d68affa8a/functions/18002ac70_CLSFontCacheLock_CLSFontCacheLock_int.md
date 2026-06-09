# CLSFontCacheLock::CLSFontCacheLock(int)

- ea: `0x18002ac70`
- end: `0x18002ad28`
- name: `??0CLSFontCacheLock@@QEAA@H@Z`
- size: `184`
- prototype: `CLSFontCacheLock *__fastcall(CLSFontCacheLock *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d9f8c`
- `0x1800f4438`

## callees

- `0x18002ac70`
- `0x18002af88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002aced`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002aced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002acf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002acf3`

## pseudocode

```c
CLSFontCacheLock *__fastcall CLSFontCacheLock::CLSFontCacheLock(CLSFontCacheLock *this, int a2)
{
  int v2; // edi
  struct LOCK_TELEMETRY near **v5; // rax
  int v6; // eax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  bool v10; // cc
  __int64 v11; // rcx
  __int64 v12; // rcx

  v2 = (int)CLockSharedData::LockOwner;
  *(_DWORD *)this = 0;
  if ( v2 && v2 == GetCurrentThreadId() )
  {
    if ( *(_DWORD *)this > 3u )
      v5 = 0;
    else
      v5 = &CLockSharedData::LockTelemetry + 2 * *(int *)this;
    ++*(_DWORD *)v5;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(*(unsigned int *)this);
    AcquireSRWLockExclusive(Lock);
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_DWORD *)this <= 3u;
    v11 = *(int *)this;
    *((_DWORD *)&CLockSharedData::LockOwner + v11) = CurrentThreadId;
    if ( v10 )
      v12 = (__int64)&dword_1802DF74C[4 * v11];
    else
      v12 = 4;
    ++*(_DWORD *)v12;
  }
  ++CLSLock::_cOLSBusy;
  *((_BYTE *)this + 4) = 1;
  v6 = a2 != 0;
  g_cFCLock += v6;
  *((_DWORD *)this + 2) = v6;
  return this;
}

```

## disassembly

```asm
0x18002ac70  mov     [rsp+arg_0], rbx
0x18002ac75  mov     [rsp+arg_8], rsi
0x18002ac7a  push    rdi
0x18002ac7b  sub     rsp, 20h
0x18002ac7f  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002ac85  mov     esi, edx
0x18002ac87  mov     dword ptr [rcx], 0
0x18002ac8d  mov     rbx, rcx
0x18002ac90  test    edi, edi
0x18002ac92  jz      short loc_18002ACE3
0x18002ac94  call    cs:__imp_GetCurrentThreadId
0x18002ac9a  cmp     edi, eax
0x18002ac9c  jnz     short loc_18002ACE3
0x18002ac9e  cmp     dword ptr [rbx], 3
0x18002aca1  ja      short loc_18002AD1D
0x18002aca3  movsxd  rax, dword ptr [rbx]
0x18002aca6  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002acad  shl     rax, 4
0x18002acb1  add     rax, rcx
0x18002acb4  inc     dword ptr [rax]
0x18002acb6  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x18002acbc  xor     eax, eax
0x18002acbe  test    esi, esi
0x18002acc0  mov     byte ptr [rbx+4], 1
0x18002acc4  mov     rsi, [rsp+28h+arg_8]
0x18002acc9  setnz   al
0x18002accc  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x18002acd2  mov     [rbx+8], eax
0x18002acd5  mov     rax, rbx
0x18002acd8  mov     rbx, [rsp+28h+arg_0]
0x18002acdd  add     rsp, 20h
0x18002ace1  pop     rdi
0x18002ace2  retn
0x18002ace3  mov     ecx, [rbx]
0x18002ace5  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002acea  mov     rcx, rax; SRWLock
0x18002aced  call    cs:__imp_AcquireSRWLockExclusive
0x18002acf3  call    cs:__imp_GetCurrentThreadId
0x18002acf9  cmp     dword ptr [rbx], 3
0x18002acfc  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002ad03  movsxd  rcx, dword ptr [rbx]
0x18002ad06  mov     [rdx+rcx*4], eax
0x18002ad09  ja      short loc_18002AD21
0x18002ad0b  shl     rcx, 4
0x18002ad0f  lea     rax, dword_1802DF74C
0x18002ad16  add     rcx, rax
0x18002ad19  inc     dword ptr [rcx]
0x18002ad1b  jmp     short loc_18002ACB6
0x18002ad1d  xor     eax, eax
0x18002ad1f  jmp     short loc_18002ACB4
0x18002ad21  mov     ecx, 4
0x18002ad26  jmp     short loc_18002AD19
```
