# NetSetupLegacyPlugin::ApplyRegistryChanges(StackLock &)

- ea: `0x1800587b4`
- end: `0x18005884c`
- name: `?ApplyRegistryChanges@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@@Z`
- size: `152`
- prototype: `void(NetSetupLegacyPlugin *__hidden this, struct StackLock *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180058764`

## callees

- `0x180033600`
- `0x180037e40`
- `0x180050e20`
- `0x1800587b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800587f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800587f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058825`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800587fd`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800587fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupLegacyPlugin::ApplyRegistryChanges(NetSetupLegacyPlugin *this, struct StackLock *a2)
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
  NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_48c47b609e3862ca0fd605bb78454d29___((__int64)this, (__int64)this);
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
0x1800587b4  push    rbx
0x1800587b6  push    rbp
0x1800587b7  push    rsi
0x1800587b8  push    rdi
0x1800587b9  sub     rsp, 48h
0x1800587bd  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800587c6  mov     rbp, rdx
0x1800587c9  mov     rdi, rcx
0x1800587cc  mov     ebx, [rcx+24h]
0x1800587cf  mov     [rsp+68h+var_40], rdx
0x1800587d4  mov     [rsp+68h+var_38], rbx
0x1800587d9  lea     rsi, [rdx+8]
0x1800587dd  mov     rcx, rsi; this
0x1800587e0  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x1800587e5  mov     rax, [rbp+18h]
0x1800587e9  mov     [rax], rbx
0x1800587ec  xor     ebx, ebx
0x1800587ee  mov     [rsi+8], ebx
0x1800587f1  mov     rcx, rsi; SRWLock
0x1800587f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800587fa  mov     rcx, rbp; ConditionVariable
0x1800587fd  call    cs:__imp_WakeAllConditionVariable
0x180058803  nop
0x180058804  mov     rdx, rdi
0x180058807  mov     rcx, rdi
0x18005880a  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_48c47b609e3862ca0fd605bb78454d29___
0x18005880f  nop
0x180058810  mov     rcx, rsi; this
0x180058813  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x180058818  jmp     short loc_180058825
0x18005881a  mov     rdx, rsi; SRWLock
0x18005881d  mov     rcx, rbp; ConditionVariable
0x180058820  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180058825  call    cs:__imp_GetCurrentThreadId
0x18005882b  mov     rcx, [rbp+18h]
0x18005882f  cmp     [rcx+0Ch], eax
0x180058832  jnz     short loc_18005881A
0x180058834  mov     [rcx], rbx
0x180058837  mov     [rsi+8], ebx
0x18005883a  mov     rcx, rsi
0x18005883d  add     rsp, 48h
0x180058841  pop     rdi
0x180058842  pop     rsi
0x180058843  pop     rbp
0x180058844  pop     rbx
0x180058845  jmp     cs:__imp_ReleaseSRWLockExclusive
```
