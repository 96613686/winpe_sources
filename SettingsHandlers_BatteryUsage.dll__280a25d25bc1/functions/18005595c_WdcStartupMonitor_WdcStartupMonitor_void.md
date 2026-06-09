# WdcStartupMonitor::~WdcStartupMonitor(void)

- ea: `0x18005595c`
- end: `0x180055a2f`
- name: `??1WdcStartupMonitor@@QEAA@XZ`
- size: `211`
- prototype: `void __fastcall(WdcStartupMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004ec94`

## callees

- `0x18000fa10`
- `0x18005595c`
- `0x180055a38`
- `0x180055b38`
- `0x180055b64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800559af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800559af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055978`

## pseudocode

```c
void __fastcall WdcStartupMonitor::~WdcStartupMonitor(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v3; // edx
  WdcStartupMonitor *DebugInfo; // rdi
  struct _WDC_DATA_INFO *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 4;
  EnterCriticalSection(this + 4);
  v6 = v2;
  DebugInfo = (WdcStartupMonitor *)this->DebugInfo;
  while ( DebugInfo != (WdcStartupMonitor *)this )
  {
    v5 = DebugInfo;
    DebugInfo = *(WdcStartupMonitor **)DebugInfo;
    WdcStartupMonitor::DataExpire(v5, v3);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v6);
  DeleteCriticalSection(v2);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[3].OwningThread);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[3].LockCount);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[2].SpinCount);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[2].OwningThread);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[2].LockCount);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[2]);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[1].SpinCount);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[1].OwningThread);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this[1]);
  StartupDB::StartupApproval::Uninitialize((StartupDB::StartupApproval *)&this->LockSemaphore);
  wistd::unique_ptr<CStartupImpactHelper,wistd::default_delete<CStartupImpactHelper>>::reset(&this->OwningThread, 0);
}

```

## disassembly

```asm
0x18005595c  mov     [rsp+arg_8], rbx
0x180055961  mov     [rsp+arg_10], rsi
0x180055966  push    rdi
0x180055967  sub     rsp, 20h
0x18005596b  mov     rbx, rcx
0x18005596e  lea     rsi, [rcx+0A0h]
0x180055975  mov     rcx, rsi; lpCriticalSection
0x180055978  call    cs:__imp_EnterCriticalSection
0x18005597e  mov     [rsp+28h+arg_0], rsi
0x180055983  mov     rdi, [rbx]
0x180055986  jmp     short loc_180055993
0x180055988  mov     rcx, rdi; struct _WDC_DATA_INFO *
0x18005598b  mov     rdi, [rdi]
0x18005598e  call    ?DataExpire@WdcStartupMonitor@@SAJPEAU_WDC_DATA_INFO@@K@Z; WdcStartupMonitor::DataExpire(_WDC_DATA_INFO *,ulong)
0x180055993  cmp     rdi, rbx
0x180055996  jnz     short loc_180055988
0x180055998  lea     rcx, [rsp+28h+arg_0]; this
0x18005599d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800559a2  lea     rcx, [rsp+28h+arg_0]; this
0x1800559a7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800559ac  mov     rcx, rsi; lpCriticalSection
0x1800559af  call    cs:__imp_DeleteCriticalSection
0x1800559b5  lea     rcx, [rbx+88h]; this
0x1800559bc  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559c1  lea     rcx, [rbx+80h]; this
0x1800559c8  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559cd  lea     rcx, [rbx+70h]; this
0x1800559d1  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559d6  lea     rcx, [rbx+60h]; this
0x1800559da  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559df  lea     rcx, [rbx+58h]; this
0x1800559e3  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559e8  lea     rcx, [rbx+50h]; this
0x1800559ec  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559f1  lea     rcx, [rbx+48h]; this
0x1800559f5  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x1800559fa  lea     rcx, [rbx+38h]; this
0x1800559fe  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x180055a03  lea     rcx, [rbx+28h]; this
0x180055a07  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x180055a0c  lea     rcx, [rbx+18h]; this
0x180055a10  call    ?Uninitialize@StartupApproval@StartupDB@@QEAAXXZ; StartupDB::StartupApproval::Uninitialize(void)
0x180055a15  lea     rcx, [rbx+10h]
0x180055a19  xor     edx, edx
0x180055a1b  mov     rbx, [rsp+28h+arg_8]
0x180055a20  mov     rsi, [rsp+28h+arg_10]
0x180055a25  add     rsp, 20h
0x180055a29  pop     rdi
0x180055a2a  jmp     ?reset@?$unique_ptr@VCStartupImpactHelper@@U?$default_delete@VCStartupImpactHelper@@@wistd@@@wistd@@QEAAXPEAVCStartupImpactHelper@@@Z; wistd::unique_ptr<CStartupImpactHelper,wistd::default_delete<CStartupImpactHelper>>::reset(CStartupImpactHelper *)
```
