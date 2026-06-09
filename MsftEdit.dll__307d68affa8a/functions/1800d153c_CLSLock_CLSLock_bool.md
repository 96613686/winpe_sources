# CLSLock::CLSLock(bool)

- ea: `0x1800d153c`
- end: `0x1800d160d`
- name: `??0CLSLock@@QEAA@_N@Z`
- size: `209`
- prototype: `CLSLock *__fastcall(CLSLock *__hidden this, bool)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002dee0`
- `0x1800c23c8`
- `0x18018ee00`

## callees

- `0x1800d153c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d15b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d15b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d1561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d15bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d1561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d15bc`

## pseudocode

```c
CLSLock *__fastcall CLSLock::CLSLock(CLSLock *this, char a2)
{
  int v2; // edi
  struct LOCK_TELEMETRY near **v5; // rax
  RTL_SRWLOCK *v7; // rcx
  DWORD CurrentThreadId; // eax
  bool v9; // cc
  __int64 v10; // rcx
  __int64 v11; // rcx

  v2 = (int)CLockSharedData::LockOwner;
  *(_DWORD *)this = 0;
  if ( !v2 || v2 != GetCurrentThreadId() )
  {
    switch ( *(_DWORD *)this )
    {
      case 0:
        goto LABEL_10;
      case 1:
        v7 = &SRW_PTSLock;
        break;
      case 2:
        v7 = &SRW_IdealHDCLock;
        break;
      default:
LABEL_10:
        v7 = &SRW_RELock;
        break;
    }
    AcquireSRWLockExclusive(v7);
    CurrentThreadId = GetCurrentThreadId();
    v9 = *(_DWORD *)this <= 3u;
    v10 = *(int *)this;
    *((_DWORD *)&CLockSharedData::LockOwner + v10) = CurrentThreadId;
    if ( v9 )
      v11 = (__int64)&dword_1802DF74C[4 * v10];
    else
      v11 = 4;
    ++*(_DWORD *)v11;
    goto LABEL_6;
  }
  if ( *(_DWORD *)this > 3u )
    v5 = 0;
  else
    v5 = &CLockSharedData::LockTelemetry + 2 * *(int *)this;
  ++*(_DWORD *)v5;
LABEL_6:
  *((_BYTE *)this + 4) = a2;
  if ( a2 )
    ++CLSLock::_cOLSBusy;
  return this;
}

```

## disassembly

```asm
0x1800d153c  mov     [rsp+arg_0], rbx
0x1800d1541  mov     [rsp+arg_8], rsi
0x1800d1546  push    rdi
0x1800d1547  sub     rsp, 20h
0x1800d154b  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800d1551  mov     sil, dl
0x1800d1554  mov     dword ptr [rcx], 0
0x1800d155a  mov     rbx, rcx
0x1800d155d  test    edi, edi
0x1800d155f  jz      short loc_1800D15A9
0x1800d1561  call    cs:__imp_GetCurrentThreadId
0x1800d1567  cmp     edi, eax
0x1800d1569  jnz     short loc_1800D15A9
0x1800d156b  cmp     dword ptr [rbx], 3
0x1800d156e  ja      loc_1800D15F9
0x1800d1574  movsxd  rax, dword ptr [rbx]
0x1800d1577  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800d157e  shl     rax, 4
0x1800d1582  add     rax, rcx
0x1800d1585  inc     dword ptr [rax]
0x1800d1587  mov     [rbx+4], sil
0x1800d158b  test    sil, sil
0x1800d158e  jz      short loc_1800D1596
0x1800d1590  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x1800d1596  mov     rsi, [rsp+28h+arg_8]
0x1800d159b  mov     rax, rbx
0x1800d159e  mov     rbx, [rsp+28h+arg_0]
0x1800d15a3  add     rsp, 20h
0x1800d15a7  pop     rdi
0x1800d15a8  retn
0x1800d15a9  mov     ecx, [rbx]
0x1800d15ab  test    ecx, ecx
0x1800d15ad  jnz     short loc_1800D15E6
0x1800d15af  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800d15b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800d15bc  call    cs:__imp_GetCurrentThreadId
0x1800d15c2  cmp     dword ptr [rbx], 3
0x1800d15c5  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800d15cc  movsxd  rcx, dword ptr [rbx]
0x1800d15cf  mov     [rdx+rcx*4], eax
0x1800d15d2  ja      short loc_1800D15FD
0x1800d15d4  shl     rcx, 4
0x1800d15d8  lea     rax, dword_1802DF74C
0x1800d15df  add     rcx, rax
0x1800d15e2  inc     dword ptr [rcx]
0x1800d15e4  jmp     short loc_1800D1587
0x1800d15e6  sub     ecx, 1
0x1800d15e9  jz      short loc_1800D1604
0x1800d15eb  cmp     ecx, 1
0x1800d15ee  jnz     short loc_1800D15AF
0x1800d15f0  lea     rcx, ?SRW_IdealHDCLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_IdealHDCLock
0x1800d15f7  jmp     short loc_1800D15B6
0x1800d15f9  xor     eax, eax
0x1800d15fb  jmp     short loc_1800D1585
0x1800d15fd  mov     ecx, 4
0x1800d1602  jmp     short loc_1800D15E2
0x1800d1604  lea     rcx, ?SRW_PTSLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_PTSLock
0x1800d160b  jmp     short loc_1800D15B6
```
