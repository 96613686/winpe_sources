# dxg::svc::ServiceRefCount::AddRef(void)

- ea: `0x18000ec10`
- end: `0x18000ec73`
- name: `?AddRef@ServiceRefCount@svc@dxg@@UEAAKXZ`
- size: `99`
- prototype: `__int64 __fastcall(dxg::svc::ServiceRefCount *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000e418`
- `0x18000e700`
- `0x18000ec10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000ec30`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000ec30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ec46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ec46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ec55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ec55`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall dxg::svc::ServiceRefCount::AddRef(dxg::svc::ServiceRefCount *this)
{
  struct _TP_TIMER *v2; // rcx
  unsigned int v3; // ebx
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, (char *)this + 16);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 && IsThreadpoolTimerSet(v2) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 12), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
  }
  v3 = ++*((_DWORD *)this + 2);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v5);
  return v3;
}

```

## disassembly

```asm
0x18000ec10  push    rbx
0x18000ec12  sub     rsp, 30h
0x18000ec16  mov     rbx, rcx
0x18000ec19  lea     rdx, [rcx+10h]
0x18000ec1d  lea     rcx, [rsp+38h+var_18]
0x18000ec22  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000ec27  mov     rcx, [rbx+60h]; pti
0x18000ec2b  test    rcx, rcx
0x18000ec2e  jz      short loc_18000EC5B
0x18000ec30  call    cs:__imp_IsThreadpoolTimerSet
0x18000ec36  test    eax, eax
0x18000ec38  jz      short loc_18000EC5B
0x18000ec3a  mov     rcx, [rbx+60h]; pti
0x18000ec3e  xor     r9d, r9d; msWindowLength
0x18000ec41  xor     r8d, r8d; msPeriod
0x18000ec44  xor     edx, edx; pftDueTime
0x18000ec46  call    cs:__imp_SetThreadpoolTimer
0x18000ec4c  mov     rcx, [rbx+60h]; pti
0x18000ec50  mov     edx, 1; fCancelPendingCallbacks
0x18000ec55  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ec5b  inc     dword ptr [rbx+8]
0x18000ec5e  lea     rcx, [rsp+38h+var_18]
0x18000ec63  mov     ebx, [rbx+8]
0x18000ec66  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000ec6b  mov     eax, ebx
0x18000ec6d  add     rsp, 30h
0x18000ec71  pop     rbx
0x18000ec72  retn
```
