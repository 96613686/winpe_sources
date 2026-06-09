# NetSetupLegacyPlugin::SysNotifyBindPath(StackLock &,ulong,_GUID const &)

- ea: `0x180037ba0`
- end: `0x180037c6b`
- name: `?SysNotifyBindPath@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@KAEBU_GUID@@@Z`
- size: `203`
- prototype: `void(NetSetupLegacyPlugin *__hidden this, struct StackLock *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180037a1c`

## callees

- `0x180033600`
- `0x180037ba0`
- `0x180037e40`
- `0x1800388e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037bee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037bee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c38`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037bf7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180037bf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::SysNotifyBindPath(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        int a3,
        const struct _GUID *a4)
{
  __int64 v7; // rbx
  char *v8; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int64 v11[8]; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+90h] [rbp+18h] BYREF

  v12 = a3;
  v11[4] = -2;
  v7 = *((unsigned int *)this + 9);
  v11[5] = (__int64)a2;
  v11[6] = v7;
  v8 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v7;
  *((_DWORD *)v8 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  v11[0] = (__int64)this;
  v11[1] = (__int64)&v12;
  v11[2] = (__int64)a4;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_a66d6419aed55a64c85ed972d9f8840b___((__int64)this, v11);
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
0x180037ba0  mov     rax, rsp
0x180037ba3  mov     [rax+18h], r8d
0x180037ba7  push    rsi
0x180037ba8  push    rdi
0x180037ba9  push    r14
0x180037bab  sub     rsp, 60h
0x180037baf  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180037bb7  mov     [rax+10h], rbx
0x180037bbb  mov     [rax+20h], rbp
0x180037bbf  mov     rsi, r9
0x180037bc2  mov     r14, rdx
0x180037bc5  mov     rdi, rcx
0x180037bc8  mov     ebx, [rcx+24h]
0x180037bcb  mov     [rax-30h], rdx
0x180037bcf  mov     [rax-28h], rbx
0x180037bd3  lea     rbp, [rdx+8]
0x180037bd7  mov     rcx, rbp; this
0x180037bda  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037bdf  mov     rax, [r14+18h]
0x180037be3  mov     [rax], rbx
0x180037be6  xor     ebx, ebx
0x180037be8  mov     [rbp+8], ebx
0x180037beb  mov     rcx, rbp; SRWLock
0x180037bee  call    cs:__imp_ReleaseSRWLockExclusive
0x180037bf4  mov     rcx, r14; ConditionVariable
0x180037bf7  call    cs:__imp_WakeAllConditionVariable
0x180037bfd  nop
0x180037bfe  mov     [rsp+78h+var_58], rdi
0x180037c03  lea     rax, [rsp+78h+arg_10]
0x180037c0b  mov     [rsp+78h+var_50], rax
0x180037c10  mov     [rsp+78h+var_48], rsi
0x180037c15  lea     rdx, [rsp+78h+var_58]
0x180037c1a  mov     rcx, rdi
0x180037c1d  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_a66d6419aed55a64c85ed972d9f8840b___
0x180037c22  nop
0x180037c23  mov     rcx, rbp; this
0x180037c26  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180037c2b  jmp     short loc_180037C38
0x180037c2d  mov     rdx, rbp; SRWLock
0x180037c30  mov     rcx, r14; ConditionVariable
0x180037c33  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180037c38  call    cs:__imp_GetCurrentThreadId
0x180037c3e  mov     rcx, [r14+18h]
0x180037c42  cmp     [rcx+0Ch], eax
0x180037c45  jnz     short loc_180037C2D
0x180037c47  mov     [rcx], rbx
0x180037c4a  mov     [rbp+8], ebx
0x180037c4d  mov     rcx, rbp; SRWLock
0x180037c50  call    cs:__imp_ReleaseSRWLockExclusive
0x180037c56  lea     r11, [rsp+78h+var_18]
0x180037c5b  mov     rbx, [r11+28h]
0x180037c5f  mov     rbp, [r11+38h]
0x180037c63  mov     rsp, r11
0x180037c66  pop     r14
0x180037c68  pop     rdi
0x180037c69  pop     rsi
0x180037c6a  retn
```
