# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::~DefaultAgent(void)

- ea: `0x1800115bc`
- end: `0x1800116f0`
- name: `??1DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `308`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011588`

## callees

- `0x1800115bc`
- `0x180014efc`
- `0x180014f78`
- `0x180015048`
- `0x18004b640`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180011639`
- `KERNEL32!FreeLibrary` at `0x180011639`
- `KERNEL32!DeleteCriticalSection` at `0x180011646`
- `KERNEL32!DeleteCriticalSection` at `0x18001165f`
- `KERNEL32!DeleteCriticalSection` at `0x180011681`
- `KERNEL32!DeleteCriticalSection` at `0x180011646`
- `KERNEL32!DeleteCriticalSection` at `0x18001165f`
- `KERNEL32!DeleteCriticalSection` at `0x180011681`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::~DefaultAgent(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this)
{
  __int64 v2; // rcx
  HMODULE v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorMessageAgent'};
  *((_QWORD *)this + 1) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorMultiProcessGraphingAgent'};
  *((_QWORD *)this + 2) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorBasicDebuggerAgent'};
  *((_QWORD *)this + 3) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorEventsCallbackAgent'};
  *((_QWORD *)this + 4) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorEtwAgent'};
  *((_QWORD *)this + 5) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorConfigurableAgent'};
  *((_QWORD *)this + 6) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `CModuleRefCount'};
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = (HMODULE)*((_QWORD *)this + 13);
  if ( v3 )
    FreeLibrary(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  std::vector<CollectorGraphPoint>::~vector<CollectorGraphPoint>((char *)this + 288);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  std::deque<std::pair<unsigned __int64,unsigned __int64>>::~deque<std::pair<unsigned __int64,unsigned __int64>>((char *)this + 200);
  std::vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters>>::~vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters>>((char *)this + 176);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  v4 = *((_QWORD *)this + 14);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 11);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *((_QWORD *)this + 6) = &CModuleRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *((_QWORD *)this + 6) = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x1800115bc  push    rbx
0x1800115be  sub     rsp, 20h
0x1800115c2  mov     rbx, rcx
0x1800115c5  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorMessageAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorMessageAgent'}
0x1800115cc  mov     [rcx], rax
0x1800115cf  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorMultiProcessGraphingAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorMultiProcessGraphingAgent'}
0x1800115d6  mov     [rcx+8], rax
0x1800115da  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorBasicDebuggerAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorBasicDebuggerAgent'}
0x1800115e1  mov     [rcx+10h], rax
0x1800115e5  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorEventsCallbackAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorEventsCallbackAgent'}
0x1800115ec  mov     [rcx+18h], rax
0x1800115f0  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorEtwAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorEtwAgent'}
0x1800115f7  mov     [rcx+20h], rax
0x1800115fb  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorConfigurableAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `IStandardCollectorConfigurableAgent'}
0x180011602  mov     [rcx+28h], rax
0x180011606  lea     rax, ??_7DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::`vftable'{for `CModuleRefCount'}
0x18001160d  mov     [rcx+30h], rax
0x180011611  mov     rcx, [rcx+70h]
0x180011615  test    rcx, rcx
0x180011618  jz      short loc_180011630
0x18001161a  mov     qword ptr [rbx+70h], 0
0x180011622  mov     rax, [rcx]
0x180011625  mov     rax, [rax+10h]
0x180011629  call    cs:__guard_dispatch_icall_fptr
0x18001162f  nop
0x180011630  mov     rcx, [rbx+68h]; hLibModule
0x180011634  test    rcx, rcx
0x180011637  jz      short loc_18001163F
0x180011639  call    cs:__imp_FreeLibrary
0x18001163f  lea     rcx, [rbx+138h]; lpCriticalSection
0x180011646  call    cs:__imp_DeleteCriticalSection
0x18001164c  lea     rcx, [rbx+120h]
0x180011653  call    ??1?$vector@UCollectorGraphPoint@@V?$allocator@UCollectorGraphPoint@@@std@@@std@@QEAA@XZ; std::vector<CollectorGraphPoint>::~vector<CollectorGraphPoint>(void)
0x180011658  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x18001165f  call    cs:__imp_DeleteCriticalSection
0x180011665  lea     rcx, [rbx+0C8h]
0x18001166c  call    ??1?$deque@U?$pair@_K_K@std@@V?$allocator@U?$pair@_K_K@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<unsigned __int64,unsigned __int64>>::~deque<std::pair<unsigned __int64,unsigned __int64>>(void)
0x180011671  lea     rcx, [rbx+0B0h]
0x180011678  call    ??1?$vector@V?$unique_ptr@VProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters>>::~vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters>>(void)
0x18001167d  lea     rcx, [rbx+78h]; lpCriticalSection
0x180011681  call    cs:__imp_DeleteCriticalSection
0x180011687  nop
0x180011688  mov     rcx, [rbx+70h]
0x18001168c  test    rcx, rcx
0x18001168f  jz      short loc_18001169F
0x180011691  mov     rax, [rcx]
0x180011694  mov     rax, [rax+10h]
0x180011698  call    cs:__guard_dispatch_icall_fptr
0x18001169e  nop
0x18001169f  mov     rcx, [rbx+60h]
0x1800116a3  test    rcx, rcx
0x1800116a6  jz      short loc_1800116B6
0x1800116a8  mov     rax, [rcx]
0x1800116ab  mov     rax, [rax+10h]
0x1800116af  call    cs:__guard_dispatch_icall_fptr
0x1800116b5  nop
0x1800116b6  mov     rcx, [rbx+58h]
0x1800116ba  test    rcx, rcx
0x1800116bd  jz      short loc_1800116CD
0x1800116bf  mov     rax, [rcx]
0x1800116c2  mov     rax, [rax+10h]
0x1800116c6  call    cs:__guard_dispatch_icall_fptr
0x1800116cc  nop
0x1800116cd  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x1800116d4  mov     [rbx+30h], rax
0x1800116d8  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x1800116df  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1800116e6  mov     [rbx+30h], rax
0x1800116ea  add     rsp, 20h
0x1800116ee  pop     rbx
0x1800116ef  retn
```
