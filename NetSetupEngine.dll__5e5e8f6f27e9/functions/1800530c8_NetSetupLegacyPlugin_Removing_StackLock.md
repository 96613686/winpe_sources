# NetSetupLegacyPlugin::Removing(StackLock &)

- ea: `0x1800530c8`
- end: `0x180053160`
- name: `?Removing@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@@Z`
- size: `152`
- prototype: `void(NetSetupLegacyPlugin *__hidden this, struct StackLock *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180036a00`

## callees

- `0x180033600`
- `0x180037e40`
- `0x18005187c`
- `0x1800530c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053139`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180053111`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180053111`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::Removing(NetSetupLegacyPlugin *this, struct StackLock *a2)
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
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_c1e271eba6077259925ba562b2055329___((__int64)this, (__int64)this);
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
0x1800530c8  push    rbx
0x1800530ca  push    rbp
0x1800530cb  push    rsi
0x1800530cc  push    rdi
0x1800530cd  sub     rsp, 48h
0x1800530d1  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800530da  mov     rbp, rdx
0x1800530dd  mov     rdi, rcx
0x1800530e0  mov     ebx, [rcx+24h]
0x1800530e3  mov     [rsp+68h+var_40], rdx
0x1800530e8  mov     [rsp+68h+var_38], rbx
0x1800530ed  lea     rsi, [rdx+8]
0x1800530f1  mov     rcx, rsi; this
0x1800530f4  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x1800530f9  mov     rax, [rbp+18h]
0x1800530fd  mov     [rax], rbx
0x180053100  xor     ebx, ebx
0x180053102  mov     [rsi+8], ebx
0x180053105  mov     rcx, rsi; SRWLock
0x180053108  call    cs:__imp_ReleaseSRWLockExclusive
0x18005310e  mov     rcx, rbp; ConditionVariable
0x180053111  call    cs:__imp_WakeAllConditionVariable
0x180053117  nop
0x180053118  mov     rdx, rdi
0x18005311b  mov     rcx, rdi
0x18005311e  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_c1e271eba6077259925ba562b2055329___
0x180053123  nop
0x180053124  mov     rcx, rsi; this
0x180053127  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18005312c  jmp     short loc_180053139
0x18005312e  mov     rdx, rsi; SRWLock
0x180053131  mov     rcx, rbp; ConditionVariable
0x180053134  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180053139  call    cs:__imp_GetCurrentThreadId
0x18005313f  mov     rcx, [rbp+18h]
0x180053143  cmp     [rcx+0Ch], eax
0x180053146  jnz     short loc_18005312E
0x180053148  mov     [rcx], rbx
0x18005314b  mov     [rsi+8], ebx
0x18005314e  mov     rcx, rsi
0x180053151  add     rsp, 48h
0x180053155  pop     rdi
0x180053156  pop     rsi
0x180053157  pop     rbp
0x180053158  pop     rbx
0x180053159  jmp     cs:__imp_ReleaseSRWLockExclusive
```
