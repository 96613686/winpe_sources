# CFixArrayBase::AddRef(short)

- ea: `0x18002ad30`
- end: `0x18002ae52`
- name: `?AddRef@CFixArrayBase@@QEAAJF@Z`
- size: `290`
- prototype: `__int64 __fastcall(CFixArrayBase *__hidden this, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18010ebc0`

## callees

- `0x18002ab44`
- `0x18002ad30`
- `0x18002af88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002adfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002adfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ad6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ad6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae29`

## pseudocode

```c
__int64 __fastcall CFixArrayBase::AddRef(CFixArrayBase *this, __int16 a2)
{
  unsigned int v2; // ebp
  signed int v3; // esi
  int v5; // r14d
  __int64 v6; // r8
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+48h] [rbp+10h] BYREF

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
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802DF74C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( (unsigned int)v3 >= *((_DWORD *)this + 3)
      || *(int *)(*((_DWORD *)this + 5) * (v3 % 16 + 1) + *(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16)) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = *((_DWORD *)this + 5) * (v3 % 16 + 1);
      v7 = *(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16));
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
0x18002ad30  mov     [rsp+arg_0], rbx
0x18002ad35  mov     [rsp+arg_10], rbp
0x18002ad3a  push    rsi
0x18002ad3b  push    rdi
0x18002ad3c  push    r14
0x18002ad3e  sub     rsp, 20h
0x18002ad42  or      ebp, 0FFFFFFFFh
0x18002ad45  movsx   esi, dx
0x18002ad48  mov     rdi, rcx
0x18002ad4b  cmp     esi, [rcx+0Ch]
0x18002ad4e  jnb     loc_18002AE04
0x18002ad54  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002ad5b  xor     ebx, ebx
0x18002ad5d  mov     [rsp+38h+arg_8], ebx
0x18002ad61  test    r14d, r14d
0x18002ad64  jz      loc_18002AE19
0x18002ad6a  call    cs:__imp_GetCurrentThreadId
0x18002ad70  cmp     r14d, eax
0x18002ad73  jnz     loc_18002AE19
0x18002ad79  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002ad7f  cmp     esi, [rdi+0Ch]
0x18002ad82  jnb     loc_18002AE46
0x18002ad88  mov     eax, esi
0x18002ad8a  mov     r9d, 10h
0x18002ad90  cdq
0x18002ad91  idiv    r9d
0x18002ad94  mov     eax, esi
0x18002ad96  inc     edx
0x18002ad98  imul    edx, [rdi+14h]
0x18002ad9c  movsxd  r8, edx
0x18002ad9f  cdq
0x18002ada0  idiv    r9d
0x18002ada3  movsxd  rcx, eax
0x18002ada6  mov     rax, [rdi]
0x18002ada9  mov     rcx, [rax+rcx*8]
0x18002adad  cmp     [r8+rcx-4], ebx
0x18002adb2  jle     loc_18002AE46
0x18002adb8  mov     eax, esi
0x18002adba  cdq
0x18002adbb  idiv    r9d
0x18002adbe  mov     eax, esi
0x18002adc0  inc     edx
0x18002adc2  imul    edx, [rdi+14h]
0x18002adc6  movsxd  r8, edx
0x18002adc9  cdq
0x18002adca  idiv    r9d
0x18002adcd  movsxd  rcx, eax
0x18002add0  mov     rax, [rdi]
0x18002add3  mov     rdx, [rax+rcx*8]
0x18002add7  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002adde  inc     dword ptr [r8+rdx-4]
0x18002ade3  mov     eax, [rcx]
0x18002ade5  mov     ebp, [r8+rdx-4]
0x18002adea  test    eax, eax
0x18002adec  jg      short loc_18002AE40
0x18002adee  xor     ecx, ecx
0x18002adf0  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, ebx; uint near * CLockSharedData::LockOwner
0x18002adf6  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002adfb  mov     rcx, rax; SRWLock
0x18002adfe  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ae04  mov     rbx, [rsp+38h+arg_0]
0x18002ae09  mov     eax, ebp
0x18002ae0b  mov     rbp, [rsp+38h+arg_10]
0x18002ae10  add     rsp, 20h
0x18002ae14  pop     r14
0x18002ae16  pop     rdi
0x18002ae17  pop     rsi
0x18002ae18  retn
0x18002ae19  xor     ecx, ecx
0x18002ae1b  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002ae20  mov     rcx, rax; SRWLock
0x18002ae23  call    cs:__imp_AcquireSRWLockExclusive
0x18002ae29  call    cs:__imp_GetCurrentThreadId
0x18002ae2f  inc     cs:dword_1802DF74C
0x18002ae35  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002ae3b  jmp     loc_18002AD7F
0x18002ae40  dec     eax
0x18002ae42  mov     [rcx], eax
0x18002ae44  jmp     short loc_18002AE04
0x18002ae46  lea     rcx, [rsp+38h+arg_8]; this
0x18002ae4b  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18002ae50  jmp     short loc_18002AE04
```
