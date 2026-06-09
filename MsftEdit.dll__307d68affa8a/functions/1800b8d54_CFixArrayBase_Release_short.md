# CFixArrayBase::Release(short)

- ea: `0x1800b8d54`
- end: `0x1800b8e8c`
- name: `?Release@CFixArrayBase@@QEAAJF@Z`
- size: `312`
- prototype: `__int64 __fastcall(CFixArrayBase *__hidden this, __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b8c30`
- `0x1800b8cc0`

## callees

- `0x18002ab44`
- `0x1800b8d54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8e33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8e33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8e39`

## pseudocode

```c
__int64 __fastcall CFixArrayBase::Release(CFixArrayBase *this, __int16 a2)
{
  unsigned int v2; // esi
  signed int v3; // edi
  int v5; // ebp
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  bool v9; // zf
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+58h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 3) )
  {
    v5 = (int)CLockSharedData::LockOwner;
    v12 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v5 == GetCurrentThreadId() )
    {
      LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
    }
    else
    {
      AcquireSRWLockExclusive(&SRW_RELock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802DF74C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( (unsigned int)v3 >= *((_DWORD *)this + 3)
      || *(int *)(*(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16)) + *((_DWORD *)this + 5) * (v3 % 16 + 1) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = v3 / 16;
      v7 = *((_DWORD *)this + 5) * (v3 % 16 + 1);
      v8 = *(_QWORD *)(*(_QWORD *)this + 8 * v6);
      v9 = (*(_DWORD *)(v7 + v8 - 4))-- == 1;
      v2 = *(_DWORD *)(v7 + v8 - 4);
      if ( v9 && (unsigned int)v3 < *((_DWORD *)this + 3) )
      {
        *(_DWORD *)(*((_DWORD *)this + 5) * (v3 % 16 + 1) + *(_QWORD *)(*(_QWORD *)this + 8 * v6) - 4LL) = *((_DWORD *)this + 4);
        *((_DWORD *)this + 4) = v3 | 0x80000000;
      }
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        ReleaseSRWLockExclusive(&SRW_RELock);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800b8d54  push    rbx
0x1800b8d56  push    rbp
0x1800b8d57  push    rsi
0x1800b8d58  push    rdi
0x1800b8d59  sub     rsp, 28h
0x1800b8d5d  or      esi, 0FFFFFFFFh
0x1800b8d60  movsx   edi, dx
0x1800b8d63  mov     rbx, rcx
0x1800b8d66  cmp     edi, [rcx+0Ch]
0x1800b8d69  jnb     loc_1800B8E21
0x1800b8d6f  mov     ebp, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800b8d75  mov     [rsp+48h+arg_8], 0
0x1800b8d7d  test    ebp, ebp
0x1800b8d7f  jz      loc_1800B8E2C
0x1800b8d85  call    cs:__imp_GetCurrentThreadId
0x1800b8d8b  cmp     ebp, eax
0x1800b8d8d  jnz     loc_1800B8E2C
0x1800b8d93  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b8d99  cmp     edi, [rbx+0Ch]
0x1800b8d9c  jnb     loc_1800B8E80
0x1800b8da2  mov     r8, [rbx]
0x1800b8da5  mov     eax, edi
0x1800b8da7  cdq
0x1800b8da8  mov     r10d, 10h
0x1800b8dae  idiv    r10d
0x1800b8db1  movsxd  r9, eax
0x1800b8db4  mov     eax, edi
0x1800b8db6  cdq
0x1800b8db7  idiv    r10d
0x1800b8dba  mov     rax, [r8+r9*8]
0x1800b8dbe  inc     edx
0x1800b8dc0  imul    edx, [rbx+14h]
0x1800b8dc4  movsxd  rcx, edx
0x1800b8dc7  cmp     dword ptr [rax+rcx-4], 0
0x1800b8dcc  jle     loc_1800B8E80
0x1800b8dd2  mov     eax, edi
0x1800b8dd4  cdq
0x1800b8dd5  idiv    r10d
0x1800b8dd8  mov     eax, edi
0x1800b8dda  lea     r8d, [rdx+1]
0x1800b8dde  cdq
0x1800b8ddf  idiv    r10d
0x1800b8de2  movsxd  r9, eax
0x1800b8de5  mov     eax, r8d
0x1800b8de8  imul    eax, [rbx+14h]
0x1800b8dec  movsxd  rdx, eax
0x1800b8def  mov     rax, [rbx]
0x1800b8df2  mov     rcx, [rax+r9*8]
0x1800b8df6  add     [rdx+rcx-4], esi
0x1800b8dfa  mov     esi, [rdx+rcx-4]
0x1800b8dfe  jz      short loc_1800B8E5A
0x1800b8e00  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b8e06  test    eax, eax
0x1800b8e08  jg      short loc_1800B8E50
0x1800b8e0a  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800b8e11  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x1800b8e1b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8e21  mov     eax, esi
0x1800b8e23  add     rsp, 28h
0x1800b8e27  pop     rdi
0x1800b8e28  pop     rsi
0x1800b8e29  pop     rbp
0x1800b8e2a  pop     rbx
0x1800b8e2b  retn
0x1800b8e2c  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800b8e33  call    cs:__imp_AcquireSRWLockExclusive
0x1800b8e39  call    cs:__imp_GetCurrentThreadId
0x1800b8e3f  inc     cs:dword_1802DF74C
0x1800b8e45  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800b8e4b  jmp     loc_1800B8D99
0x1800b8e50  dec     eax
0x1800b8e52  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b8e58  jmp     short loc_1800B8E21
0x1800b8e5a  cmp     edi, [rbx+0Ch]
0x1800b8e5d  jnb     short loc_1800B8E00
0x1800b8e5f  imul    r8d, [rbx+14h]
0x1800b8e64  mov     rax, [rbx]
0x1800b8e67  or      edi, 80000000h
0x1800b8e6d  mov     rcx, [rax+r9*8]
0x1800b8e71  mov     eax, [rbx+10h]
0x1800b8e74  movsxd  rdx, r8d
0x1800b8e77  mov     [rdx+rcx-4], eax
0x1800b8e7b  mov     [rbx+10h], edi
0x1800b8e7e  jmp     short loc_1800B8E00
0x1800b8e80  lea     rcx, [rsp+48h+arg_8]; this
0x1800b8e85  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800b8e8a  jmp     short loc_1800B8E21
```
