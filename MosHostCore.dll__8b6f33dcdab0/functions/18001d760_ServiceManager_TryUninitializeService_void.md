# ServiceManager::TryUninitializeService(void)

- ea: `0x18001d760`
- end: `0x18001d7bc`
- name: `?TryUninitializeService@ServiceManager@@AEAAJXZ`
- size: `92`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180009c88`
- `0x180011c84`
- `0x1800122fc`
- `0x18001d760`
- `0x18001d870`
- `0x1800228ec`
- `0x1800229b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceManager::TryUninitializeService(ServiceManager *this, __int64 a2, void (*a3)(void))
{
  _BYTE v5[16]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE Context[40]; // [rsp+30h] [rbp-28h] BYREF

  ScopedWatchdogTimer::ScopedWatchdogTimer(Context, a2, a3);
  CriticalSectionWithConditionVariable::Lock((struct _RTL_CRITICAL_SECTION *)this + 85, (__int64)v5);
  if ( !ClientsTracker::HasClientsRequiringServiceInitialized((LPCRITICAL_SECTION)((char *)this + 3816)) )
    ServiceManager::UninitializeService(this);
  RelockableGate::~RelockableGate((RelockableGate *)v5);
  ScopedWatchdogTimer::~ScopedWatchdogTimer((ScopedWatchdogTimer *)Context);
  return 0;
}

```

## disassembly

```asm
0x18001d760  push    rbx
0x18001d762  sub     rsp, 50h
0x18001d766  mov     rbx, rcx
0x18001d769  lea     rcx, [rsp+58h+Context]; Context
0x18001d76e  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x18001d773  nop
0x18001d774  lea     rcx, [rbx+0D48h]
0x18001d77b  lea     rdx, [rsp+58h+var_38]
0x18001d780  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001d785  nop
0x18001d786  lea     rcx, [rbx+0EE8h]; lpCriticalSection
0x18001d78d  call    ?HasClientsRequiringServiceInitialized@ClientsTracker@@QEAA_NXZ; ClientsTracker::HasClientsRequiringServiceInitialized(void)
0x18001d792  test    al, al
0x18001d794  jnz     short loc_18001D79F
0x18001d796  mov     rcx, rbx; this
0x18001d799  call    ?UninitializeService@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeService(void)
0x18001d79e  nop
0x18001d79f  lea     rcx, [rsp+58h+var_38]; this
0x18001d7a4  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001d7a9  nop
0x18001d7aa  lea     rcx, [rsp+58h+Context]; this
0x18001d7af  call    ??1ScopedWatchdogTimer@@QEAA@XZ; ScopedWatchdogTimer::~ScopedWatchdogTimer(void)
0x18001d7b4  xor     eax, eax
0x18001d7b6  add     rsp, 50h
0x18001d7ba  pop     rbx
0x18001d7bb  retn
```
