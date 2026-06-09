# NetSetupLegacyPlugin::ExecuteLegacyInfSection(StackLock &,wchar_t const *,_NETSETUP_SHIM_INF_EXECUTION_PARAMETERS const *)

- ea: `0x18004f540`
- end: `0x18004f60a`
- name: `?ExecuteLegacyInfSection@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@PEB_WPEBU_NETSETUP_SHIM_INF_EXECUTION_PARAMETERS@@@Z`
- size: `202`
- prototype: `void __fastcall(NetSetupLegacyPlugin *this, struct StackLock *, const wchar_t *, const struct _NETSETUP_SHIM_INF_EXECUTION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18004f240`

## callees

- `0x180033600`
- `0x180037e40`
- `0x18004f540`
- `0x1800511d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f58a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f5f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f58a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f5f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f5dc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004f593`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004f593`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::ExecuteLegacyInfSection(
        NetSetupLegacyPlugin *this,
        struct StackLock *a2,
        const wchar_t *a3,
        const struct _NETSETUP_SHIM_INF_EXECUTION_PARAMETERS *a4)
{
  __int64 v6; // rbx
  char *v7; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  _QWORD v10[11]; // [rsp+20h] [rbp-58h] BYREF
  const wchar_t *v11; // [rsp+90h] [rbp+18h] BYREF
  const struct _NETSETUP_SHIM_INF_EXECUTION_PARAMETERS *v12; // [rsp+98h] [rbp+20h] BYREF

  v12 = a4;
  v11 = a3;
  v10[4] = -2;
  v6 = *((unsigned int *)this + 9);
  v10[5] = a2;
  v10[6] = v6;
  v7 = (char *)a2 + 8;
  RtlSrwLock::AcquireExclusive((struct StackLock *)((char *)a2 + 8));
  **((_QWORD **)a2 + 3) = v6;
  *((_DWORD *)v7 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v7);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
  v10[0] = this;
  v10[1] = &v11;
  v10[2] = &v12;
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_206973776a14a208b3b56b929a60470f___((__int64)this, (__int64)v10);
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)v7);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)a2 + 3);
    if ( *(_DWORD *)(v9 + 12) == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v7);
  }
  *(_QWORD *)v9 = 0;
  *((_DWORD *)v7 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v7);
}

```

## disassembly

```asm
0x18004f540  mov     rax, rsp
0x18004f543  mov     [rax+20h], r9
0x18004f547  mov     [rax+18h], r8
0x18004f54b  push    rbp
0x18004f54c  push    rsi
0x18004f54d  push    rdi
0x18004f54e  sub     rsp, 60h
0x18004f552  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18004f55a  mov     [rax+10h], rbx
0x18004f55e  mov     rbp, rdx
0x18004f561  mov     rdi, rcx
0x18004f564  mov     ebx, [rcx+24h]
0x18004f567  mov     [rax-30h], rdx
0x18004f56b  mov     [rax-28h], rbx
0x18004f56f  lea     rsi, [rdx+8]
0x18004f573  mov     rcx, rsi; this
0x18004f576  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004f57b  mov     rax, [rbp+18h]
0x18004f57f  mov     [rax], rbx
0x18004f582  xor     ebx, ebx
0x18004f584  mov     [rsi+8], ebx
0x18004f587  mov     rcx, rsi; SRWLock
0x18004f58a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f590  mov     rcx, rbp; ConditionVariable
0x18004f593  call    cs:__imp_WakeAllConditionVariable
0x18004f599  nop
0x18004f59a  mov     [rsp+78h+var_58], rdi
0x18004f59f  lea     rax, [rsp+78h+arg_10]
0x18004f5a7  mov     [rsp+78h+var_50], rax
0x18004f5ac  lea     rax, [rsp+78h+arg_18]
0x18004f5b4  mov     [rsp+78h+var_48], rax
0x18004f5b9  lea     rdx, [rsp+78h+var_58]
0x18004f5be  mov     rcx, rdi
0x18004f5c1  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_206973776a14a208b3b56b929a60470f___
0x18004f5c6  nop
0x18004f5c7  mov     rcx, rsi; this
0x18004f5ca  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18004f5cf  jmp     short loc_18004F5DC
0x18004f5d1  mov     rdx, rsi; SRWLock
0x18004f5d4  mov     rcx, rbp; ConditionVariable
0x18004f5d7  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18004f5dc  call    cs:__imp_GetCurrentThreadId
0x18004f5e2  mov     rcx, [rbp+18h]
0x18004f5e6  cmp     [rcx+0Ch], eax
0x18004f5e9  jnz     short loc_18004F5D1
0x18004f5eb  mov     [rcx], rbx
0x18004f5ee  mov     [rsi+8], ebx
0x18004f5f1  mov     rcx, rsi; SRWLock
0x18004f5f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f5fa  mov     rbx, [rsp+78h+arg_8]
0x18004f602  add     rsp, 60h
0x18004f606  pop     rdi
0x18004f607  pop     rsi
0x18004f608  pop     rbp
0x18004f609  retn
```
