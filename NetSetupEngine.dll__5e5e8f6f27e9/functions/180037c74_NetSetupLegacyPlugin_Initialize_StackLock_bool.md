# NetSetupLegacyPlugin::Initialize(StackLock &,bool)

- ea: `0x180037c74`
- end: `0x180037d2a`
- name: `?Initialize@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@_N@Z`
- size: `182`
- prototype: `void __fastcall(NetSetupLegacyPlugin *this, struct StackLock *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800170b4`

## callees

- `0x180033600`
- `0x180037c74`
- `0x180037e40`
- `0x180038620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037cba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037cba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037cff`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037cc3`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037cc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::Initialize(NetSetupLegacyPlugin *this, struct StackLock *a2, char a3)
{
  __int64 v5; // rbx
  char *v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // rcx
  _QWORD v9[9]; // [rsp+20h] [rbp-48h] BYREF
  char v10; // [rsp+80h] [rbp+18h] BYREF

  v10 = a3;
  v9[2] = -2;
  v5 = *((unsigned int *)this + 9);
  v9[3] = a2;
  v9[4] = v5;
  v6 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v5;
  *((_DWORD *)v6 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v6);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  v9[0] = this;
  v9[1] = &v10;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_0c250e71f82107bc96bf25592ce595db___(this, v9);
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)v6);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)a2 + 3);
    if ( *(_DWORD *)(v8 + 12) == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v6);
  }
  *(_QWORD *)v8 = 0;
  *((_DWORD *)v6 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v6);
}

```

## disassembly

```asm
0x180037c74  mov     rax, rsp
0x180037c77  mov     [rax+18h], r8b
0x180037c7b  push    rbp
0x180037c7c  push    rsi
0x180037c7d  push    rdi
0x180037c7e  sub     rsp, 50h
0x180037c82  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180037c8a  mov     [rax+10h], rbx
0x180037c8e  mov     rbp, rdx
0x180037c91  mov     rdi, rcx
0x180037c94  mov     ebx, [rcx+24h]
0x180037c97  mov     [rax-30h], rdx
0x180037c9b  mov     [rax-28h], rbx
0x180037c9f  lea     rsi, [rdx+8]
0x180037ca3  mov     rcx, rsi; this
0x180037ca6  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037cab  mov     rax, [rbp+18h]
0x180037caf  mov     [rax], rbx
0x180037cb2  xor     ebx, ebx
0x180037cb4  mov     [rsi+8], ebx
0x180037cb7  mov     rcx, rsi; SRWLock
0x180037cba  call    cs:__imp_ReleaseSRWLockExclusive
0x180037cc0  mov     rcx, rbp; ConditionVariable
0x180037cc3  call    cs:__imp_WakeAllConditionVariable
0x180037cc9  nop
0x180037cca  mov     [rsp+68h+var_48], rdi
0x180037ccf  lea     rax, [rsp+68h+arg_10]
0x180037cd7  mov     [rsp+68h+var_40], rax
0x180037cdc  lea     rdx, [rsp+68h+var_48]
0x180037ce1  mov     rcx, rdi
0x180037ce4  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_0c250e71f82107bc96bf25592ce595db___
0x180037ce9  nop
0x180037cea  mov     rcx, rsi; this
0x180037ced  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037cf2  jmp     short loc_180037CFF
0x180037cf4  mov     rdx, rsi; SRWLock
0x180037cf7  mov     rcx, rbp; ConditionVariable
0x180037cfa  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180037cff  call    cs:__imp_GetCurrentThreadId
0x180037d05  mov     rcx, [rbp+18h]
0x180037d09  cmp     [rcx+0Ch], eax
0x180037d0c  jnz     short loc_180037CF4
0x180037d0e  mov     [rcx], rbx
0x180037d11  mov     [rsi+8], ebx
0x180037d14  mov     rcx, rsi; SRWLock
0x180037d17  call    cs:__imp_ReleaseSRWLockExclusive
0x180037d1d  mov     rbx, [rsp+68h+arg_8]
0x180037d22  add     rsp, 50h
0x180037d26  pop     rdi
0x180037d27  pop     rsi
0x180037d28  pop     rbp
0x180037d29  retn
```
