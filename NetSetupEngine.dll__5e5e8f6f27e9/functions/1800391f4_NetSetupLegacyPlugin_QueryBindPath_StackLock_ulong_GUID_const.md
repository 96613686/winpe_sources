# NetSetupLegacyPlugin::QueryBindPath(StackLock &,ulong,_GUID const &)

- ea: `0x1800391f4`
- end: `0x1800392f2`
- name: `?QueryBindPath@NetSetupLegacyPlugin@@QEAA_NAEAVStackLock@@KAEBU_GUID@@@Z`
- size: `254`
- prototype: `bool __fastcall(NetSetupLegacyPlugin *this, struct StackLock *, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180037a1c`

## callees

- `0x180033600`
- `0x180037e40`
- `0x1800391f4`
- `0x180039718`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039255`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800392ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039255`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800392ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800392a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800392a9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18003925e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18003925e`

## pseudocode

```c
bool __fastcall NetSetupLegacyPlugin::QueryBindPath(
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
  v14 = 0;
  v13[0] = this;
  v13[1] = &v15;
  v13[2] = a4;
  v13[3] = &v14;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_bfbc7b1bf99b9707957f142b2f5036a8___((__int64)this, (__int64)v13);
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
0x1800391f4  mov     rax, rsp
0x1800391f7  mov     [rax+18h], r8d
0x1800391fb  push    rbp
0x1800391fc  push    rsi
0x1800391fd  push    rdi
0x1800391fe  push    r14
0x180039200  push    r15
0x180039202  mov     rbp, rsp
0x180039205  sub     rsp, 70h
0x180039209  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180039211  mov     [rax+10h], rbx
0x180039215  mov     rax, cs:__security_cookie
0x18003921c  xor     rax, rsp
0x18003921f  mov     [rbp+var_10], rax
0x180039223  mov     rdi, r9
0x180039226  mov     r15, rdx
0x180039229  mov     rsi, rcx
0x18003922c  mov     ebx, [rcx+24h]
0x18003922f  mov     [rbp+var_28], rdx
0x180039233  mov     [rbp+var_20], rbx
0x180039237  lea     r14, [rdx+8]
0x18003923b  mov     rcx, r14; this
0x18003923e  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180039243  mov     rax, [r15+18h]
0x180039247  mov     [rax], rbx
0x18003924a  mov     dword ptr [r14+8], 0
0x180039252  mov     rcx, r14; SRWLock
0x180039255  call    cs:__imp_ReleaseSRWLockExclusive
0x18003925b  mov     rcx, r15; ConditionVariable
0x18003925e  call    cs:__imp_WakeAllConditionVariable
0x180039264  nop
0x180039265  mov     [rbp+var_18], 0
0x180039269  mov     [rbp+var_50], rsi
0x18003926d  lea     rax, [rbp+arg_10]
0x180039271  mov     [rbp+var_48], rax
0x180039275  mov     [rbp+var_40], rdi
0x180039279  lea     rax, [rbp+var_18]
0x18003927d  mov     [rbp+var_38], rax
0x180039281  lea     rdx, [rbp+var_50]
0x180039285  mov     rcx, rsi
0x180039288  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_bfbc7b1bf99b9707957f142b2f5036a8___
0x18003928d  cmp     [rbp+var_18], 0
0x180039291  setnz   bl
0x180039294  mov     rcx, r14; this
0x180039297  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18003929c  jmp     short loc_1800392A9
0x18003929e  mov     rdx, r14; SRWLock
0x1800392a1  mov     rcx, r15; ConditionVariable
0x1800392a4  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x1800392a9  call    cs:__imp_GetCurrentThreadId
0x1800392af  mov     rcx, [r15+18h]
0x1800392b3  cmp     [rcx+0Ch], eax
0x1800392b6  jnz     short loc_18003929E
0x1800392b8  mov     qword ptr [rcx], 0
0x1800392bf  mov     dword ptr [r14+8], 0
0x1800392c7  mov     rcx, r14; SRWLock
0x1800392ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800392d0  mov     al, bl
0x1800392d2  mov     rcx, [rbp+var_10]
0x1800392d6  xor     rcx, rsp; StackCookie
0x1800392d9  call    __security_check_cookie
0x1800392de  mov     rbx, [rsp+70h+arg_8]
0x1800392e6  add     rsp, 70h
0x1800392ea  pop     r15
0x1800392ec  pop     r14
0x1800392ee  pop     rdi
0x1800392ef  pop     rsi
0x1800392f0  pop     rbp
0x1800392f1  retn
```
