# CCharFormatArray::AddRef(short)

- ea: `0x18002ae60`
- end: `0x18002af81`
- name: `?AddRef@CCharFormatArray@@UEAAJF@Z`
- size: `289`
- prototype: `__int64 __fastcall(CCharFormatArray *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002ab44`
- `0x18002ae60`
- `0x18002af88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002af52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002af52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002af58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002af58`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::AddRef(CCharFormatArray *this, __int16 a2)
{
  unsigned int v2; // edi
  signed int v3; // ebp
  int v5; // r14d
  __int64 v6; // rax
  int v7; // edx
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 5) )
  {
    v5 = (int)CLockSharedData::LockOwner;
    v12 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v5 == GetCurrentThreadId() )
    {
      LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
    }
    else
    {
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802DF74C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( (unsigned int)v3 >= *((_DWORD *)this + 5)
      || *(int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (v3 / 16)) + *((_DWORD *)this + 7) * (v3 % 16 + 1) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (v3 / 16));
      v7 = *((_DWORD *)this + 7) * (v3 % 16 + 1);
      v2 = ++*(_DWORD *)(v6 + v7 - 4);
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        v8 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        ReleaseSRWLockExclusive(v8);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002ae60  mov     [rsp+arg_0], rbx
0x18002ae65  mov     [rsp+arg_10], rbp
0x18002ae6a  push    rsi
0x18002ae6b  push    rdi
0x18002ae6c  push    r14
0x18002ae6e  sub     rsp, 20h
0x18002ae72  or      edi, 0FFFFFFFFh
0x18002ae75  movsx   ebp, dx
0x18002ae78  mov     rsi, rcx
0x18002ae7b  cmp     ebp, [rcx+14h]
0x18002ae7e  jnb     loc_18002AF33
0x18002ae84  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002ae8b  xor     ebx, ebx
0x18002ae8d  mov     [rsp+38h+arg_8], ebx
0x18002ae91  test    r14d, r14d
0x18002ae94  jz      loc_18002AF48
0x18002ae9a  call    cs:__imp_GetCurrentThreadId
0x18002aea0  cmp     r14d, eax
0x18002aea3  jnz     loc_18002AF48
0x18002aea9  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002aeaf  cmp     ebp, [rsi+14h]
0x18002aeb2  jnb     loc_18002AF75
0x18002aeb8  mov     rcx, [rsi+8]
0x18002aebc  mov     r10d, 10h
0x18002aec2  mov     eax, ebp
0x18002aec4  cdq
0x18002aec5  idiv    r10d
0x18002aec8  movsxd  r8, eax
0x18002aecb  mov     eax, ebp
0x18002aecd  cdq
0x18002aece  idiv    r10d
0x18002aed1  mov     rcx, [rcx+r8*8]
0x18002aed5  inc     edx
0x18002aed7  imul    edx, [rsi+1Ch]
0x18002aedb  movsxd  rdx, edx
0x18002aede  cmp     [rcx+rdx-4], ebx
0x18002aee2  jle     loc_18002AF75
0x18002aee8  mov     r8, [rsi+8]
0x18002aeec  mov     eax, ebp
0x18002aeee  cdq
0x18002aeef  idiv    r10d
0x18002aef2  movsxd  r9, eax
0x18002aef5  mov     eax, ebp
0x18002aef7  cdq
0x18002aef8  idiv    r10d
0x18002aefb  mov     rax, [r8+r9*8]
0x18002aeff  inc     edx
0x18002af01  imul    edx, [rsi+1Ch]
0x18002af05  movsxd  rcx, edx
0x18002af08  inc     dword ptr [rax+rcx-4]
0x18002af0c  mov     edi, [rax+rcx-4]
0x18002af10  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002af17  mov     eax, [rcx]
0x18002af19  test    eax, eax
0x18002af1b  jg      short loc_18002AF6F
0x18002af1d  xor     ecx, ecx
0x18002af1f  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, ebx; uint near * CLockSharedData::LockOwner
0x18002af25  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002af2a  mov     rcx, rax; SRWLock
0x18002af2d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002af33  mov     rbx, [rsp+38h+arg_0]
0x18002af38  mov     eax, edi
0x18002af3a  mov     rbp, [rsp+38h+arg_10]
0x18002af3f  add     rsp, 20h
0x18002af43  pop     r14
0x18002af45  pop     rdi
0x18002af46  pop     rsi
0x18002af47  retn
0x18002af48  xor     ecx, ecx
0x18002af4a  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002af4f  mov     rcx, rax; SRWLock
0x18002af52  call    cs:__imp_AcquireSRWLockExclusive
0x18002af58  call    cs:__imp_GetCurrentThreadId
0x18002af5e  inc     cs:dword_1802DF74C
0x18002af64  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002af6a  jmp     loc_18002AEAF
0x18002af6f  dec     eax
0x18002af71  mov     [rcx], eax
0x18002af73  jmp     short loc_18002AF33
0x18002af75  lea     rcx, [rsp+38h+arg_8]; this
0x18002af7a  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18002af7f  jmp     short loc_18002AF33
```
