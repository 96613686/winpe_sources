# NetSetupLegacyPlugin::SysNotifyComponent(StackLock &,ulong,NetSetupObjectId const &)

- ea: `0x18004d764`
- end: `0x18004d82f`
- name: `?SysNotifyComponent@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@KAEBUNetSetupObjectId@@@Z`
- size: `203`
- prototype: `void(NetSetupLegacyPlugin *__hidden this, struct StackLock *, unsigned int, const struct NetSetupObjectId *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180036a00`
- `0x18005b728`

## callees

- `0x180033600`
- `0x180037e40`
- `0x18004d764`
- `0x18004f788`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d7b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d814`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d7b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d814`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d7fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d7fc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004d7bb`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004d7bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::SysNotifyComponent(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        int a3,
        const struct NetSetupObjectId *a4)
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
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_612fd87467808efebf3a2cf71eae569d___((__int64)this, (__int64)v11);
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
0x18004d764  mov     rax, rsp
0x18004d767  mov     [rax+18h], r8d
0x18004d76b  push    rsi
0x18004d76c  push    rdi
0x18004d76d  push    r14
0x18004d76f  sub     rsp, 60h
0x18004d773  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18004d77b  mov     [rax+10h], rbx
0x18004d77f  mov     [rax+20h], rbp
0x18004d783  mov     rsi, r9
0x18004d786  mov     r14, rdx
0x18004d789  mov     rdi, rcx
0x18004d78c  mov     ebx, [rcx+24h]
0x18004d78f  mov     [rax-30h], rdx
0x18004d793  mov     [rax-28h], rbx
0x18004d797  lea     rbp, [rdx+8]
0x18004d79b  mov     rcx, rbp; this
0x18004d79e  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004d7a3  mov     rax, [r14+18h]
0x18004d7a7  mov     [rax], rbx
0x18004d7aa  xor     ebx, ebx
0x18004d7ac  mov     [rbp+8], ebx
0x18004d7af  mov     rcx, rbp; SRWLock
0x18004d7b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d7b8  mov     rcx, r14; ConditionVariable
0x18004d7bb  call    cs:__imp_WakeAllConditionVariable
0x18004d7c1  nop
0x18004d7c2  mov     [rsp+78h+var_58], rdi
0x18004d7c7  lea     rax, [rsp+78h+arg_10]
0x18004d7cf  mov     [rsp+78h+var_50], rax
0x18004d7d4  mov     [rsp+78h+var_48], rsi
0x18004d7d9  lea     rdx, [rsp+78h+var_58]
0x18004d7de  mov     rcx, rdi
0x18004d7e1  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_612fd87467808efebf3a2cf71eae569d___
0x18004d7e6  nop
0x18004d7e7  mov     rcx, rbp; this
0x18004d7ea  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004d7ef  jmp     short loc_18004D7FC
0x18004d7f1  mov     rdx, rbp; SRWLock
0x18004d7f4  mov     rcx, r14; ConditionVariable
0x18004d7f7  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18004d7fc  call    cs:__imp_GetCurrentThreadId
0x18004d802  mov     rcx, [r14+18h]
0x18004d806  cmp     [rcx+0Ch], eax
0x18004d809  jnz     short loc_18004D7F1
0x18004d80b  mov     [rcx], rbx
0x18004d80e  mov     [rbp+8], ebx
0x18004d811  mov     rcx, rbp; SRWLock
0x18004d814  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d81a  lea     r11, [rsp+78h+var_18]
0x18004d81f  mov     rbx, [r11+28h]
0x18004d823  mov     rbp, [r11+38h]
0x18004d827  mov     rsp, r11
0x18004d82a  pop     r14
0x18004d82c  pop     rdi
0x18004d82d  pop     rsi
0x18004d82e  retn
```
