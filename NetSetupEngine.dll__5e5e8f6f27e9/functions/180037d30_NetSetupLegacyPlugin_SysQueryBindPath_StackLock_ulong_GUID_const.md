# NetSetupLegacyPlugin::SysQueryBindPath(StackLock &,ulong,_GUID const &)

- ea: `0x180037d30`
- end: `0x180037e2e`
- name: `?SysQueryBindPath@NetSetupLegacyPlugin@@QEAA_NAEAVStackLock@@KAEBU_GUID@@@Z`
- size: `254`
- prototype: `bool __fastcall(NetSetupLegacyPlugin *this, struct StackLock *, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180037a1c`

## callees

- `0x180033600`
- `0x180037d30`
- `0x180037e40`
- `0x180037e64`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037e06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037e06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037dd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037dd8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037d9a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037d9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall NetSetupLegacyPlugin::SysQueryBindPath(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        int a3,
        const struct _GUID *a4)
{
  __int64 v7; // rbx
  char *v8; // r14
  bool v9; // bl
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  _QWORD v13[7]; // [rsp+20h] [rbp-50h] BYREF
  char v14; // [rsp+58h] [rbp-18h] BYREF
  int v15; // [rsp+B0h] [rbp+40h] BYREF

  v15 = a3;
  v13[4] = -2;
  v7 = *((unsigned int *)this + 9);
  v13[5] = a2;
  v13[6] = v7;
  v8 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v7;
  *((_DWORD *)v8 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  v14 = 1;
  v13[0] = this;
  v13[1] = &v15;
  v13[2] = a4;
  v13[3] = &v14;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_1a0a074716cda426a9506ec028960679___((__int64)this, (__int64)v13);
  v9 = v14 != 0;
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)v8);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)a2 + 3);
    if ( *(_DWORD *)(v11 + 12) == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v8);
  }
  *(_QWORD *)v11 = 0;
  *((_DWORD *)v8 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
  return v9;
}

```

## disassembly

```asm
0x180037d30  mov     rax, rsp
0x180037d33  mov     [rax+18h], r8d
0x180037d37  push    rbp
0x180037d38  push    rsi
0x180037d39  push    rdi
0x180037d3a  push    r14
0x180037d3c  push    r15
0x180037d3e  mov     rbp, rsp
0x180037d41  sub     rsp, 70h
0x180037d45  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180037d4d  mov     [rax+10h], rbx
0x180037d51  mov     rax, cs:__security_cookie
0x180037d58  xor     rax, rsp
0x180037d5b  mov     [rbp+var_10], rax
0x180037d5f  mov     rdi, r9
0x180037d62  mov     r15, rdx
0x180037d65  mov     rsi, rcx
0x180037d68  mov     ebx, [rcx+24h]
0x180037d6b  mov     [rbp+var_28], rdx
0x180037d6f  mov     [rbp+var_20], rbx
0x180037d73  lea     r14, [rdx+8]
0x180037d77  mov     rcx, r14; this
0x180037d7a  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037d7f  mov     rax, [r15+18h]
0x180037d83  mov     [rax], rbx
0x180037d86  mov     dword ptr [r14+8], 0
0x180037d8e  mov     rcx, r14; SRWLock
0x180037d91  call    cs:__imp_ReleaseSRWLockExclusive
0x180037d97  mov     rcx, r15; ConditionVariable
0x180037d9a  call    cs:__imp_WakeAllConditionVariable
0x180037da0  nop
0x180037da1  mov     [rbp+var_18], 1
0x180037da5  mov     [rbp+var_50], rsi
0x180037da9  lea     rax, [rbp+arg_10]
0x180037dad  mov     [rbp+var_48], rax
0x180037db1  mov     [rbp+var_40], rdi
0x180037db5  lea     rax, [rbp+var_18]
0x180037db9  mov     [rbp+var_38], rax
0x180037dbd  lea     rdx, [rbp+var_50]
0x180037dc1  mov     rcx, rsi
0x180037dc4  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_1a0a074716cda426a9506ec028960679___
0x180037dc9  cmp     [rbp+var_18], 0
0x180037dcd  setnz   bl
0x180037dd0  mov     rcx, r14; this
0x180037dd3  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037dd8  call    cs:__imp_GetCurrentThreadId
0x180037dde  mov     rcx, [r15+18h]
0x180037de2  cmp     [rcx+0Ch], eax
0x180037de5  jz      short loc_180037DF4
0x180037de7  mov     rdx, r14; SRWLock
0x180037dea  mov     rcx, r15; ConditionVariable
0x180037ded  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180037df2  jmp     short loc_180037DD8
0x180037df4  mov     qword ptr [rcx], 0
0x180037dfb  mov     dword ptr [r14+8], 0
0x180037e03  mov     rcx, r14; SRWLock
0x180037e06  call    cs:__imp_ReleaseSRWLockExclusive
0x180037e0c  mov     al, bl
0x180037e0e  mov     rcx, [rbp+var_10]
0x180037e12  xor     rcx, rsp; StackCookie
0x180037e15  call    __security_check_cookie
0x180037e1a  mov     rbx, [rsp+70h+arg_8]
0x180037e22  add     rsp, 70h
0x180037e26  pop     r15
0x180037e28  pop     r14
0x180037e2a  pop     rdi
0x180037e2b  pop     rsi
0x180037e2c  pop     rbp
0x180037e2d  retn
```
