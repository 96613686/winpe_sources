# MigrationManager::CleanupMigration(void)

- ea: `0x14014d348`
- end: `0x14014d428`
- name: `?CleanupMigration@MigrationManager@@QEAAXXZ`
- size: `224`
- prototype: `void __fastcall(MigrationManager *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400ad490`
- `0x1400ad864`
- `0x140167e10`
- `0x1401680c0`
- `0x14021bfcc`
- `0x140222400`

## callees

- `0x140021fb8`
- `0x14002dd68`
- `0x140055af0`
- `0x1400841e4`
- `0x14014d348`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14014d3ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14014d3ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14014d361`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14014d361`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14014d381`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14014d381`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MigrationManager::CleanupMigration(PTP_WAIT *this)
{
  SetThreadpoolWait(this[28], 0, 0);
  if ( !*((_DWORD *)this + 58) )
  {
    WaitForThreadpoolWaitCallbacks(this[28], 1);
    if ( !*((_DWORD *)this + 58) )
      Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)this);
  }
  *((_DWORD *)this + 53) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 30,
    0);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(this + 20));
  this[10] = 0;
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 44) = 0;
  Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(this + 13, 0);
  *((_DWORD *)this + 42) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
  (*(void (__fastcall **)(PTP_WAIT))(*(_QWORD *)this[31] + 80LL))(this[31]);
}

```

## disassembly

```asm
0x14014d348  mov     [rsp+arg_8], rbx
0x14014d34d  push    rdi
0x14014d34e  sub     rsp, 30h
0x14014d352  mov     rdi, rcx
0x14014d355  xor     r8d, r8d; pftTimeout
0x14014d358  xor     edx, edx; h
0x14014d35a  mov     rcx, [rcx+0E0h]; pwa
0x14014d361  call    cs:__imp_SetThreadpoolWait
0x14014d368  nop     dword ptr [rax+rax+00h]
0x14014d36d  mov     eax, [rdi+0E8h]
0x14014d373  test    eax, eax
0x14014d375  jnz     short loc_14014D39F
0x14014d377  lea     edx, [rax+1]; fCancelPendingCallbacks
0x14014d37a  mov     rcx, [rdi+0E0h]; pwa
0x14014d381  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14014d388  nop     dword ptr [rax+rax+00h]
0x14014d38d  mov     eax, [rdi+0E8h]
0x14014d393  test    eax, eax
0x14014d395  jnz     short loc_14014D39F
0x14014d397  mov     rcx, rdi; this
0x14014d39a  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14014d39f  mov     dword ptr [rdi+0D4h], 0
0x14014d3a9  lea     rcx, [rdi+0F0h]
0x14014d3b0  xor     edx, edx
0x14014d3b2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14014d3b7  lea     rbx, [rdi+0A0h]
0x14014d3be  mov     rcx, rbx; this
0x14014d3c1  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14014d3c6  mov     [rsp+38h+var_18], rbx
0x14014d3cb  mov     [rsp+38h+var_10], 1
0x14014d3d0  mov     qword ptr [rdi+50h], 0
0x14014d3d8  mov     dword ptr [rdi+58h], 0
0x14014d3df  mov     dword ptr [rdi+0B0h], 0
0x14014d3e9  lea     rcx, [rdi+68h]
0x14014d3ed  xor     edx, edx
0x14014d3ef  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14014d3f4  nop
0x14014d3f5  mov     dword ptr [rbx+8], 0
0x14014d3fc  mov     rcx, rbx; SRWLock
0x14014d3ff  call    cs:__imp_ReleaseSRWLockExclusive
0x14014d406  nop     dword ptr [rax+rax+00h]
0x14014d40b  mov     rcx, [rdi+0F8h]
0x14014d412  mov     rax, [rcx]
0x14014d415  mov     rax, [rax+50h]
0x14014d419  mov     rbx, [rsp+38h+arg_8]
0x14014d41e  add     rsp, 30h
0x14014d422  pop     rdi
0x14014d423  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
