# NetSetupLegacyPlugin::ApplyPnpChanges(StackLock &)

- ea: `0x1800377b8`
- end: `0x180037850`
- name: `?ApplyPnpChanges@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@@Z`
- size: `152`
- prototype: `void __fastcall(NetSetupLegacyPlugin *this, struct StackLock *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18005a004`

## callees

- `0x180033600`
- `0x1800375dc`
- `0x1800377b8`
- `0x180037e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800377f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800377f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037829`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037801`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037801`

## pseudocode

```c
void __fastcall NetSetupLegacyPlugin::ApplyPnpChanges(NetSetupLegacyPlugin *this, struct StackLock *a2)
{
  __int64 v4; // rbx
  char *v5; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx

  v4 = *((unsigned int *)this + 9);
  v5 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v4;
  *((_DWORD *)v5 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v5);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_5570fb626d276c52d31c6299f819aa0e___((__int64)this, (__int64)this);
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)v5);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = *((_QWORD *)a2 + 3);
    if ( *(_DWORD *)(v7 + 12) == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v5);
  }
  *(_QWORD *)v7 = 0;
  *((_DWORD *)v5 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v5);
}

```

## disassembly

```asm
0x1800377b8  push    rbx
0x1800377ba  push    rbp
0x1800377bb  push    rsi
0x1800377bc  push    rdi
0x1800377bd  sub     rsp, 48h
0x1800377c1  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800377ca  mov     rbp, rdx
0x1800377cd  mov     rdi, rcx
0x1800377d0  mov     ebx, [rcx+24h]
0x1800377d3  mov     [rsp+68h+var_40], rdx
0x1800377d8  mov     [rsp+68h+var_38], rbx
0x1800377dd  lea     rsi, [rdx+8]
0x1800377e1  mov     rcx, rsi; this
0x1800377e4  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x1800377e9  mov     rax, [rbp+18h]
0x1800377ed  mov     [rax], rbx
0x1800377f0  xor     ebx, ebx
0x1800377f2  mov     [rsi+8], ebx
0x1800377f5  mov     rcx, rsi; SRWLock
0x1800377f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800377fe  mov     rcx, rbp; ConditionVariable
0x180037801  call    cs:__imp_WakeAllConditionVariable
0x180037807  nop
0x180037808  mov     rdx, rdi
0x18003780b  mov     rcx, rdi
0x18003780e  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_5570fb626d276c52d31c6299f819aa0e___
0x180037813  nop
0x180037814  mov     rcx, rsi; this
0x180037817  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18003781c  jmp     short loc_180037829
0x18003781e  mov     rdx, rsi; SRWLock
0x180037821  mov     rcx, rbp; ConditionVariable
0x180037824  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180037829  call    cs:__imp_GetCurrentThreadId
0x18003782f  mov     rcx, [rbp+18h]
0x180037833  cmp     [rcx+0Ch], eax
0x180037836  jnz     short loc_18003781E
0x180037838  mov     [rcx], rbx
0x18003783b  mov     [rsi+8], ebx
0x18003783e  mov     rcx, rsi
0x180037841  add     rsp, 48h
0x180037845  pop     rdi
0x180037846  pop     rsi
0x180037847  pop     rbp
0x180037848  pop     rbx
0x180037849  jmp     cs:__imp_ReleaseSRWLockExclusive
```
