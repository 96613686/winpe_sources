# SharedSocket::~SharedSocket(void)

- ea: `0x1800022e4`
- end: `0x18000237a`
- name: `??1SharedSocket@@QEAA@XZ`
- size: `150`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001e90`
- `0x180026be8`
- `0x1800324b7`

## callees

- `0x180001ebc`
- `0x1800022e4`
- `0x180002430`
- `0x180002548`
- `0x1800025c0`
- `0x1800026ec`
- `0x1800028cc`
- `0x180003ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000234b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000234b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002367`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002367`

## pseudocode

```c
void __fastcall SharedSocket::~SharedSocket(struct _RTL_CRITICAL_SECTION *this)
{
  SocketBrokerContext *DebugInfo; // rcx
  HANDLE LockSemaphore; // rcx
  struct _TP_WORK *OwningThread; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&SharedSocket::`vftable';
  SharedSocket::Cleanup((SharedSocket *)this);
  DebugInfo = (SocketBrokerContext *)this[2].DebugInfo;
  if ( DebugInfo )
  {
    SocketBrokerContext::ReleaseRef(DebugInfo);
    this[2].DebugInfo = 0;
  }
  SharedSocket::FreeSslContext((SharedSocket *)this);
  SharedSocket::FreeDnsRegistrationData((SharedSocket *)this);
  SharedSocket::DeleteRetryTriggerTimer((SharedSocket *)this);
  LockSemaphore = this[2].LockSemaphore;
  if ( LockSemaphore )
  {
    VpnFree(LockSemaphore);
    this[2].LockSemaphore = 0;
  }
  SharedSocket::DeleteCleanupTimer((SharedSocket *)this);
  OwningThread = (struct _TP_WORK *)this[6].OwningThread;
  if ( OwningThread )
  {
    CloseThreadpoolWork(OwningThread);
    this[6].OwningThread = 0;
  }
  DeleteCriticalSection(this + 1);
}

```

## disassembly

```asm
0x1800022e4  push    rbx
0x1800022e6  sub     rsp, 20h
0x1800022ea  mov     rbx, rcx
0x1800022ed  lea     rax, ??_7SharedSocket@@6B@; const SharedSocket::`vftable'
0x1800022f4  mov     [rcx], rax
0x1800022f7  call    ?Cleanup@SharedSocket@@UEAAXXZ; SharedSocket::Cleanup(void)
0x1800022fc  mov     rcx, [rbx+50h]; this
0x180002300  test    rcx, rcx
0x180002303  jnz     short loc_180002358
0x180002305  mov     rcx, rbx; this
0x180002308  call    ?FreeSslContext@SharedSocket@@AEAAXXZ; SharedSocket::FreeSslContext(void)
0x18000230d  mov     rcx, rbx; this
0x180002310  call    ?FreeDnsRegistrationData@SharedSocket@@AEAAXXZ; SharedSocket::FreeDnsRegistrationData(void)
0x180002315  mov     rcx, rbx; this
0x180002318  call    ?DeleteRetryTriggerTimer@SharedSocket@@AEAAXXZ; SharedSocket::DeleteRetryTriggerTimer(void)
0x18000231d  mov     rcx, [rbx+68h]; lpMem
0x180002321  test    rcx, rcx
0x180002324  jz      short loc_180002333
0x180002326  call    VpnFree
0x18000232b  mov     qword ptr [rbx+68h], 0
0x180002333  mov     rcx, rbx; this
0x180002336  call    ?DeleteCleanupTimer@SharedSocket@@QEAAXXZ; SharedSocket::DeleteCleanupTimer(void)
0x18000233b  mov     rcx, [rbx+100h]; pwk
0x180002342  test    rcx, rcx
0x180002345  jnz     short loc_180002367
0x180002347  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000234b  call    cs:__imp_DeleteCriticalSection
0x180002351  nop
0x180002352  add     rsp, 20h
0x180002356  pop     rbx
0x180002357  retn
0x180002358  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x18000235d  mov     qword ptr [rbx+50h], 0
0x180002365  jmp     short loc_180002305
0x180002367  call    cs:__imp_CloseThreadpoolWork
0x18000236d  mov     qword ptr [rbx+100h], 0
0x180002378  jmp     short loc_180002347
```
