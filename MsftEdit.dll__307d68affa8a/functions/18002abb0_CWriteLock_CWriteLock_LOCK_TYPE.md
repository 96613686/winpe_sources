# CWriteLock::CWriteLock(LOCK_TYPE)

- ea: `0x18002abb0`
- end: `0x18002ac67`
- name: `??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z`
- size: `183`
- prototype: ``
- caller_count: `86`
- callee_count: `1`
- tags: ``

## callers

- `0x1800158d8`
- `0x18001bc08`
- `0x180021928`
- `0x180021b88`
- `0x180021c90`
- `0x180028c3c`
- `0x180029234`
- `0x18002a978`
- `0x18002b310`
- `0x180040d10`
- `0x180040d4c`
- `0x180040ef4`
- `0x180041040`
- `0x1800495d0`
- `0x180049ee0`
- `0x18004a158`
- `0x18004a758`
- `0x18004ae60`
- `0x18004af24`
- `0x18004b0e8`
- `0x18004bc78`
- `0x18004bd68`
- `0x18004deb8`
- `0x180050af0`
- `0x180051074`
- `0x180051740`
- `0x180051e9c`
- `0x18005dc0c`
- `0x18005eb58`
- `0x1800627c4`
- `0x180063454`
- `0x1800643d0`
- `0x1800700a4`
- `0x1800b1018`
- `0x1800b2a5c`
- `0x1800b5de0`
- `0x1800b8730`
- `0x1800b88e0`
- `0x1800b8960`
- `0x1800b8c30`
- `0x1800b8cc0`
- `0x1800c1154`
- `0x1800c2640`
- `0x1800d064c`
- `0x1800e0810`
- `0x1800e4b74`
- `0x1800eb748`
- `0x1800f0c70`
- `0x1800f4398`
- `0x1800f4438`

## callees

- `0x18002abb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002abd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002abd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac1d`

## pseudocode

```c
unsigned int *__fastcall CWriteLock::CWriteLock(unsigned int *a1, unsigned int a2)
{
  int v3; // edi
  struct LOCK_TELEMETRY near **v4; // rax
  RTL_SRWLOCK *v6; // rcx
  DWORD CurrentThreadId; // eax
  bool v8; // cc
  __int64 v9; // rcx
  __int64 v10; // rcx

  *a1 = a2;
  v3 = *((_DWORD *)&CLockSharedData::LockOwner + (int)a2);
  if ( v3 && v3 == GetCurrentThreadId() )
  {
    if ( *a1 > 3 )
      v4 = 0;
    else
      v4 = &CLockSharedData::LockTelemetry + 2 * (int)*a1;
    ++*(_DWORD *)v4;
    return a1;
  }
  switch ( *a1 )
  {
    case 0u:
      goto LABEL_8;
    case 1u:
      v6 = &SRW_PTSLock;
      break;
    case 2u:
      v6 = &SRW_IdealHDCLock;
      break;
    default:
LABEL_8:
      v6 = &SRW_RELock;
      break;
  }
  AcquireSRWLockExclusive(v6);
  CurrentThreadId = GetCurrentThreadId();
  v8 = *a1 <= 3;
  v9 = (int)*a1;
  *((_DWORD *)&CLockSharedData::LockOwner + v9) = CurrentThreadId;
  if ( v8 )
    v10 = (__int64)&dword_1802DF74C[4 * v9];
  else
    v10 = 4;
  ++*(_DWORD *)v10;
  return a1;
}

```

## disassembly

```asm
0x18002abb0  mov     [rsp+arg_0], rbx
0x18002abb5  mov     [rsp+arg_8], rsi
0x18002abba  push    rdi
0x18002abbb  sub     rsp, 20h
0x18002abbf  movsxd  rax, edx
0x18002abc2  lea     rsi, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002abc9  mov     rbx, rcx
0x18002abcc  mov     [rcx], edx
0x18002abce  mov     edi, [rsi+rax*4]
0x18002abd1  test    edi, edi
0x18002abd3  jz      short loc_18002AC0A
0x18002abd5  call    cs:__imp_GetCurrentThreadId
0x18002abdb  cmp     edi, eax
0x18002abdd  jnz     short loc_18002AC0A
0x18002abdf  cmp     dword ptr [rbx], 3
0x18002abe2  ja      short loc_18002AC53
0x18002abe4  movsxd  rax, dword ptr [rbx]
0x18002abe7  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002abee  shl     rax, 4
0x18002abf2  add     rax, rcx
0x18002abf5  inc     dword ptr [rax]
0x18002abf7  mov     rsi, [rsp+28h+arg_8]
0x18002abfc  mov     rax, rbx
0x18002abff  mov     rbx, [rsp+28h+arg_0]
0x18002ac04  add     rsp, 20h
0x18002ac08  pop     rdi
0x18002ac09  retn
0x18002ac0a  mov     ecx, [rbx]
0x18002ac0c  test    ecx, ecx
0x18002ac0e  jnz     short loc_18002AC40
0x18002ac10  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002ac17  call    cs:__imp_AcquireSRWLockExclusive
0x18002ac1d  call    cs:__imp_GetCurrentThreadId
0x18002ac23  cmp     dword ptr [rbx], 3
0x18002ac26  movsxd  rcx, dword ptr [rbx]
0x18002ac29  mov     [rsi+rcx*4], eax
0x18002ac2c  ja      short loc_18002AC57
0x18002ac2e  shl     rcx, 4
0x18002ac32  lea     rax, dword_1802DF74C
0x18002ac39  add     rcx, rax
0x18002ac3c  inc     dword ptr [rcx]
0x18002ac3e  jmp     short loc_18002ABF7
0x18002ac40  sub     ecx, 1
0x18002ac43  jz      short loc_18002AC5E
0x18002ac45  cmp     ecx, 1
0x18002ac48  jnz     short loc_18002AC10
0x18002ac4a  lea     rcx, ?SRW_IdealHDCLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_IdealHDCLock
0x18002ac51  jmp     short loc_18002AC17
0x18002ac53  xor     eax, eax
0x18002ac55  jmp     short loc_18002ABF5
0x18002ac57  mov     ecx, 4
0x18002ac5c  jmp     short loc_18002AC3C
0x18002ac5e  lea     rcx, ?SRW_PTSLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SRW_PTSLock
0x18002ac65  jmp     short loc_18002AC17
```
