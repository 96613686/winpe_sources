# NetSetupLegacyPlugin::Install(StackLock &,ulong,wchar_t const *,wchar_t const *)

- ea: `0x180053168`
- end: `0x18005322a`
- name: `?Install@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@KPEB_W1@Z`
- size: `194`
- prototype: `void __fastcall(NetSetupLegacyPlugin *this, struct StackLock *, int, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18005b728`

## callees

- `0x180033600`
- `0x180037e40`
- `0x180051a58`
- `0x180053168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053219`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053201`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800531bc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800531bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::Install(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v7; // rbx
  char *v8; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  _QWORD v11[8]; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v13; // [rsp+A8h] [rbp+48h] BYREF

  v13 = a4;
  v12 = a3;
  v11[4] = -2;
  v7 = *((unsigned int *)this + 9);
  v11[5] = a2;
  v11[6] = v7;
  v8 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v7;
  *((_DWORD *)v8 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  v11[0] = this;
  v11[1] = &v12;
  v11[2] = &v13;
  v11[3] = &a5;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_265efd9c3b15903850c401bf29fdd152___((__int64)this, (__int64)v11);
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)v8);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)a2 + 3);
    if ( *(_DWORD *)(v10 + 12) == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v8);
  }
  *(_QWORD *)v10 = 0;
  *((_DWORD *)v8 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
}

```

## disassembly

```asm
0x180053168  mov     [rsp-28h+arg_18], r9
0x18005316d  mov     [rsp-28h+arg_10], r8d
0x180053172  push    rbp
0x180053173  push    rbx
0x180053174  push    rsi
0x180053175  push    rdi
0x180053176  push    r14
0x180053178  mov     rbp, rsp
0x18005317b  sub     rsp, 60h
0x18005317f  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180053187  mov     r14, rdx
0x18005318a  mov     rdi, rcx
0x18005318d  mov     ebx, [rcx+24h]
0x180053190  mov     [rbp+var_18], rdx
0x180053194  mov     [rbp+var_10], rbx
0x180053198  lea     rsi, [rdx+8]
0x18005319c  mov     rcx, rsi; this
0x18005319f  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x1800531a4  mov     rax, [r14+18h]
0x1800531a8  mov     [rax], rbx
0x1800531ab  xor     ebx, ebx
0x1800531ad  mov     [rsi+8], ebx
0x1800531b0  mov     rcx, rsi; SRWLock
0x1800531b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800531b9  mov     rcx, r14; ConditionVariable
0x1800531bc  call    cs:__imp_WakeAllConditionVariable
0x1800531c2  nop
0x1800531c3  mov     [rbp+var_40], rdi
0x1800531c7  lea     rax, [rbp+arg_10]
0x1800531cb  mov     [rbp+var_38], rax
0x1800531cf  lea     rax, [rbp+arg_18]
0x1800531d3  mov     [rbp+var_30], rax
0x1800531d7  lea     rax, [rbp+arg_20]
0x1800531db  mov     [rbp+var_28], rax
0x1800531df  lea     rdx, [rbp+var_40]
0x1800531e3  mov     rcx, rdi
0x1800531e6  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_265efd9c3b15903850c401bf29fdd152___
0x1800531eb  nop
0x1800531ec  mov     rcx, rsi; this
0x1800531ef  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x1800531f4  jmp     short loc_180053201
0x1800531f6  mov     rdx, rsi; SRWLock
0x1800531f9  mov     rcx, r14; ConditionVariable
0x1800531fc  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180053201  call    cs:__imp_GetCurrentThreadId
0x180053207  mov     rcx, [r14+18h]
0x18005320b  cmp     [rcx+0Ch], eax
0x18005320e  jnz     short loc_1800531F6
0x180053210  mov     [rcx], rbx
0x180053213  mov     [rsi+8], ebx
0x180053216  mov     rcx, rsi; SRWLock
0x180053219  call    cs:__imp_ReleaseSRWLockExclusive
0x18005321f  add     rsp, 60h
0x180053223  pop     r14
0x180053225  pop     rdi
0x180053226  pop     rsi
0x180053227  pop     rbx
0x180053228  pop     rbp
0x180053229  retn
```
