# CCbsIdleHandler::~CCbsIdleHandler(void)

- ea: `0x14000e430`
- end: `0x14000e508`
- name: `??1CCbsIdleHandler@@UEAA@XZ`
- size: `216`
- prototype: `void __fastcall(CCbsIdleHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14000ea20`

## callees

- `0x140006344`
- `0x14000695c`
- `0x14000e430`
- `0x14001c6c0`
- `0x14002b010`

## pseudocode

```c
void __fastcall CCbsIdleHandler::~CCbsIdleHandler(CCbsIdleHandler *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  _BYTE v5[40]; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)this = &CCbsIdleHandler::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &CCbsIdleHandler::`vftable'{for `ITaskHandler'};
  v2 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  *(_DWORD *)((char *)this + v2 + 4) = v2 - 48;
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v5,
    (struct MonitoredCritSec *)&vScavengeHandlerLock,
    1);
  CCbsTiSession::m_pIdleScavengeHandler = 0;
  MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v5);
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 4) = 0;
  }
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v5);
  *(_QWORD *)this = &CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `ITaskHandler'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 4) = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) - 24;
}

```

## disassembly

```asm
0x14000e430  push    rbx
0x14000e432  sub     rsp, 40h
0x14000e436  lea     rax, ??_7CCbsIdleHandler@@6B?$CCbsIUnknownImpl@UITaskHandler@@$$V@@@; const CCbsIdleHandler::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'}
0x14000e43d  mov     rbx, rcx
0x14000e440  mov     [rcx], rax
0x14000e443  mov     rax, [rcx+8]
0x14000e447  movsxd  rdx, dword ptr [rax+4]
0x14000e44b  lea     rax, ??_7CCbsIdleHandler@@6BITaskHandler@@@; const CCbsIdleHandler::`vftable'{for `ITaskHandler'}
0x14000e452  mov     [rdx+rcx+8], rax
0x14000e457  mov     rax, [rcx+8]
0x14000e45b  movsxd  rdx, dword ptr [rax+4]
0x14000e45f  lea     r8d, [rdx-30h]
0x14000e463  mov     [rdx+rcx+4], r8d
0x14000e468  mov     rcx, [rcx+18h]
0x14000e46c  test    rcx, rcx
0x14000e46f  jz      short loc_14000E485
0x14000e471  mov     rax, [rcx]
0x14000e474  mov     rax, [rax+10h]
0x14000e478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e47d  mov     qword ptr [rbx+18h], 0
0x14000e485  mov     r8b, 1; bool
0x14000e488  lea     rdx, ?vScavengeHandlerLock@@3UMonitoredCritSec@@A; struct MonitoredCritSec *
0x14000e48f  lea     rcx, [rsp+48h+var_28]; this
0x14000e494  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x14000e499  lea     rcx, [rsp+48h+var_28]; this
0x14000e49e  mov     cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA, 0; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000e4a9  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000e4ae  mov     rcx, [rbx+20h]
0x14000e4b2  test    rcx, rcx
0x14000e4b5  jz      short loc_14000E4CB
0x14000e4b7  mov     rax, [rcx]
0x14000e4ba  mov     rax, [rax+10h]
0x14000e4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4c3  mov     qword ptr [rbx+20h], 0
0x14000e4cb  lea     rcx, [rsp+48h+var_28]; this
0x14000e4d0  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000e4d5  lea     rax, ??_7?$CCbsIUnknownImpl@UITaskHandler@@$$V@@6B0@@; const CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'}
0x14000e4dc  mov     [rbx], rax
0x14000e4df  mov     rax, [rbx+8]
0x14000e4e3  movsxd  rcx, dword ptr [rax+4]
0x14000e4e7  lea     rax, ??_7?$CCbsIUnknownImpl@UITaskHandler@@$$V@@6BITaskHandler@@@; const CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `ITaskHandler'}
0x14000e4ee  mov     [rcx+rbx+8], rax
0x14000e4f3  mov     rax, [rbx+8]
0x14000e4f7  movsxd  rcx, dword ptr [rax+4]
0x14000e4fb  lea     edx, [rcx-18h]
0x14000e4fe  mov     [rcx+rbx+4], edx
0x14000e502  add     rsp, 40h
0x14000e506  pop     rbx
0x14000e507  retn
```
