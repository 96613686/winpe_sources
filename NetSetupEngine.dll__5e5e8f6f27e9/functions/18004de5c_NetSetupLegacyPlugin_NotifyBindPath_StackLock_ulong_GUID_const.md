# NetSetupLegacyPlugin::NotifyBindPath(StackLock &,ulong,_GUID const &)

- ea: `0x18004de5c`
- end: `0x18004df27`
- name: `?NotifyBindPath@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@KAEBU_GUID@@@Z`
- size: `203`
- prototype: `void(NetSetupLegacyPlugin *__hidden this, struct StackLock *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180037a1c`

## callees

- `0x180033600`
- `0x180037e40`
- `0x18004de5c`
- `0x18004faf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004deaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004df0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004deaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004df0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004def4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004def4`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004deb3`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004deb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::NotifyBindPath(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        int a3,
        const struct _GUID *a4)
{
  __int64 v7; // rbx
  char *v8; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  _QWORD v11[8]; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+90h] [rbp+18h] BYREF

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
  v11[2] = a4;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_a66bc2f62f1d8440140ec23d318ebe6d___((__int64)this, (__int64)v11);
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
0x18004de5c  mov     rax, rsp
0x18004de5f  mov     [rax+18h], r8d
0x18004de63  push    rsi
0x18004de64  push    rdi
0x18004de65  push    r14
0x18004de67  sub     rsp, 60h
0x18004de6b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18004de73  mov     [rax+10h], rbx
0x18004de77  mov     [rax+20h], rbp
0x18004de7b  mov     rsi, r9
0x18004de7e  mov     r14, rdx
0x18004de81  mov     rdi, rcx
0x18004de84  mov     ebx, [rcx+24h]
0x18004de87  mov     [rax-30h], rdx
0x18004de8b  mov     [rax-28h], rbx
0x18004de8f  lea     rbp, [rdx+8]
0x18004de93  mov     rcx, rbp; this
0x18004de96  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004de9b  mov     rax, [r14+18h]
0x18004de9f  mov     [rax], rbx
0x18004dea2  xor     ebx, ebx
0x18004dea4  mov     [rbp+8], ebx
0x18004dea7  mov     rcx, rbp; SRWLock
0x18004deaa  call    cs:__imp_ReleaseSRWLockExclusive
0x18004deb0  mov     rcx, r14; ConditionVariable
0x18004deb3  call    cs:__imp_WakeAllConditionVariable
0x18004deb9  nop
0x18004deba  mov     [rsp+78h+var_58], rdi
0x18004debf  lea     rax, [rsp+78h+arg_10]
0x18004dec7  mov     [rsp+78h+var_50], rax
0x18004decc  mov     [rsp+78h+var_48], rsi
0x18004ded1  lea     rdx, [rsp+78h+var_58]
0x18004ded6  mov     rcx, rdi
0x18004ded9  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_a66bc2f62f1d8440140ec23d318ebe6d___
0x18004dede  nop
0x18004dedf  mov     rcx, rbp; this
0x18004dee2  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004dee7  jmp     short loc_18004DEF4
0x18004dee9  mov     rdx, rbp; SRWLock
0x18004deec  mov     rcx, r14; ConditionVariable
0x18004deef  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18004def4  call    cs:__imp_GetCurrentThreadId
0x18004defa  mov     rcx, [r14+18h]
0x18004defe  cmp     [rcx+0Ch], eax
0x18004df01  jnz     short loc_18004DEE9
0x18004df03  mov     [rcx], rbx
0x18004df06  mov     [rbp+8], ebx
0x18004df09  mov     rcx, rbp; SRWLock
0x18004df0c  call    cs:__imp_ReleaseSRWLockExclusive
0x18004df12  lea     r11, [rsp+78h+var_18]
0x18004df17  mov     rbx, [r11+28h]
0x18004df1b  mov     rbp, [r11+38h]
0x18004df1f  mov     rsp, r11
0x18004df22  pop     r14
0x18004df24  pop     rdi
0x18004df25  pop     rsi
0x18004df26  retn
```
