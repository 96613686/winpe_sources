# CCharFormatArray::Release(short)

- ea: `0x1800c3d40`
- end: `0x1800c3e7f`
- name: `?Release@CCharFormatArray@@UEAAJF@Z`
- size: `319`
- prototype: `__int64 __fastcall(CCharFormatArray *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002ab44`
- `0x1800c3d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3e22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3e22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3e0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3e0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3e28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3e28`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::Release(CCharFormatArray *this, __int16 a2)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  int v5; // ebp
  int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  bool v10; // zf
  DWORD CurrentThreadId; // eax
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 5) )
  {
    v5 = (int)CLockSharedData::LockOwner;
    v13 = 0;
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
    if ( v3 >= *((_DWORD *)this + 5)
      || *(int *)(*((_DWORD *)this + 7) * ((int)v3 % 16 + 1)
                + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * ((int)v3 / 16))
                - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v13);
    }
    else
    {
      v6 = (int)v3 % 16 + 1;
      v7 = (int)v3 / 16;
      v8 = *((_DWORD *)this + 7) * v6;
      v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7);
      v10 = (*(_DWORD *)(v8 + v9 - 4))-- == 1;
      v2 = *(_DWORD *)(v8 + v9 - 4);
      if ( v10 && v3 < *((_DWORD *)this + 5) )
      {
        *(_DWORD *)(*((_DWORD *)this + 7) * v6 + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7) - 4LL) = *((_DWORD *)this + 6);
        *((_DWORD *)this + 6) = v3 | 0x80000000;
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
0x1800c3d40  push    rbx
0x1800c3d42  push    rbp
0x1800c3d43  push    rsi
0x1800c3d44  push    rdi
0x1800c3d45  sub     rsp, 28h
0x1800c3d49  or      esi, 0FFFFFFFFh
0x1800c3d4c  movsx   edi, dx
0x1800c3d4f  mov     rbx, rcx
0x1800c3d52  cmp     edi, [rcx+14h]
0x1800c3d55  jnb     loc_1800C3E10
0x1800c3d5b  mov     ebp, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800c3d61  mov     [rsp+48h+arg_8], 0
0x1800c3d69  test    ebp, ebp
0x1800c3d6b  jz      loc_1800C3E1B
0x1800c3d71  call    cs:__imp_GetCurrentThreadId
0x1800c3d77  cmp     ebp, eax
0x1800c3d79  jnz     loc_1800C3E1B
0x1800c3d7f  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800c3d85  cmp     edi, [rbx+14h]
0x1800c3d88  jnb     loc_1800C3E73
0x1800c3d8e  mov     eax, edi
0x1800c3d90  mov     r9d, 10h
0x1800c3d96  cdq
0x1800c3d97  idiv    r9d
0x1800c3d9a  mov     eax, edi
0x1800c3d9c  inc     edx
0x1800c3d9e  imul    edx, [rbx+1Ch]
0x1800c3da2  movsxd  r8, edx
0x1800c3da5  cdq
0x1800c3da6  idiv    r9d
0x1800c3da9  movsxd  rcx, eax
0x1800c3dac  mov     rax, [rbx+8]
0x1800c3db0  mov     rcx, [rax+rcx*8]
0x1800c3db4  cmp     dword ptr [r8+rcx-4], 0
0x1800c3dba  jle     loc_1800C3E73
0x1800c3dc0  mov     eax, edi
0x1800c3dc2  cdq
0x1800c3dc3  idiv    r9d
0x1800c3dc6  mov     eax, edi
0x1800c3dc8  lea     r8d, [rdx+1]
0x1800c3dcc  cdq
0x1800c3dcd  idiv    r9d
0x1800c3dd0  movsxd  r9, eax
0x1800c3dd3  mov     eax, r8d
0x1800c3dd6  imul    eax, [rbx+1Ch]
0x1800c3dda  movsxd  rdx, eax
0x1800c3ddd  mov     rax, [rbx+8]
0x1800c3de1  mov     rcx, [rax+r9*8]
0x1800c3de5  add     [rdx+rcx-4], esi
0x1800c3de9  mov     esi, [rdx+rcx-4]
0x1800c3ded  jz      short loc_1800C3E49
0x1800c3def  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800c3df5  test    eax, eax
0x1800c3df7  jg      short loc_1800C3E3F
0x1800c3df9  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800c3e00  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x1800c3e0a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c3e10  mov     eax, esi
0x1800c3e12  add     rsp, 28h
0x1800c3e16  pop     rdi
0x1800c3e17  pop     rsi
0x1800c3e18  pop     rbp
0x1800c3e19  pop     rbx
0x1800c3e1a  retn
0x1800c3e1b  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800c3e22  call    cs:__imp_AcquireSRWLockExclusive
0x1800c3e28  call    cs:__imp_GetCurrentThreadId
0x1800c3e2e  inc     cs:dword_1802DF74C
0x1800c3e34  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800c3e3a  jmp     loc_1800C3D85
0x1800c3e3f  dec     eax
0x1800c3e41  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800c3e47  jmp     short loc_1800C3E10
0x1800c3e49  cmp     edi, [rbx+14h]
0x1800c3e4c  jnb     short loc_1800C3DEF
0x1800c3e4e  imul    r8d, [rbx+1Ch]
0x1800c3e53  mov     rax, [rbx+8]
0x1800c3e57  or      edi, 80000000h
0x1800c3e5d  mov     rcx, [rax+r9*8]
0x1800c3e61  mov     eax, [rbx+18h]
0x1800c3e64  movsxd  rdx, r8d
0x1800c3e67  mov     [rdx+rcx-4], eax
0x1800c3e6b  mov     [rbx+18h], edi
0x1800c3e6e  jmp     loc_1800C3DEF
0x1800c3e73  lea     rcx, [rsp+48h+arg_8]; this
0x1800c3e78  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800c3e7d  jmp     short loc_1800C3E10
```
