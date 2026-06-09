# ServiceManager::~ServiceManager(void)

- ea: `0x180012350`
- end: `0x1800124ad`
- name: `??1ServiceManager@@EEAA@XZ`
- size: `349`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012690`
- `0x1800242b0`

## callees

- `0x1800078d0`
- `0x18000e7fc`
- `0x1800121b4`
- `0x1800121d0`
- `0x1800121f0`
- `0x180012254`
- `0x180012350`
- `0x1800124b4`
- `0x1800124e4`
- `0x1800171d0`
- `0x1800225f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012455`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012455`

## pseudocode

```c
void __fastcall ServiceManager::~ServiceManager(ServiceManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &ServiceManager::`vftable'{for `IServiceManager'};
  *((_QWORD *)this + 1) = &ServiceManager::`vftable'{for `MigrationEngine'};
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease((char *)this + 4368);
  TimerQueue::~TimerQueue((ServiceManager *)((char *)this + 4280));
  TransferMonitor::~TransferMonitor((ServiceManager *)((char *)this + 4112));
  ServiceWatchdog::~ServiceWatchdog((ServiceManager *)((char *)this + 3944));
  ClientsTracker::~ClientsTracker((struct _RTL_CRITICAL_SECTION *)((char *)this + 3816));
  PackageManager::~PackageManager((struct _RTL_CRITICAL_SECTION *)((char *)this + 3568));
  v2 = (void *)*((_QWORD *)this + 437);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 439) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 437) = 0;
    *((_QWORD *)this + 438) = 0;
    *((_QWORD *)this + 439) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 434);
  if ( v3 )
  {
    std::_Deallocate<16>(v3, (*((_QWORD *)this + 436) - (_QWORD)v3) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 434) = 0;
    *((_QWORD *)this + 435) = 0;
    *((_QWORD *)this + 436) = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 3464);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 3456);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 85);
  std::unique_ptr<Threadpool>::~unique_ptr<Threadpool>((_QWORD *)this + 424);
  v4 = (void *)*((_QWORD *)this + 421);
  if ( v4 )
  {
    std::_Deallocate<16>(v4, (*((_QWORD *)this + 423) - (_QWORD)v4) & 0xFFFFFFFFFFFFFFFCuLL);
    *((_QWORD *)this + 421) = 0;
    *((_QWORD *)this + 422) = 0;
    *((_QWORD *)this + 423) = 0;
  }
}

```

## disassembly

```asm
0x180012350  push    rbx
0x180012352  sub     rsp, 20h
0x180012356  lea     rax, ??_7ServiceManager@@6BIServiceManager@@@; const ServiceManager::`vftable'{for `IServiceManager'}
0x18001235d  mov     rbx, rcx
0x180012360  mov     [rcx], rax
0x180012363  lea     rax, ??_7ServiceManager@@6BMigrationEngine@@@; const ServiceManager::`vftable'{for `MigrationEngine'}
0x18001236a  mov     [rcx+8], rax
0x18001236e  add     rcx, 1110h
0x180012375  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x18001237a  lea     rcx, [rbx+10B8h]; this
0x180012381  call    ??1TimerQueue@@QEAA@XZ; TimerQueue::~TimerQueue(void)
0x180012386  lea     rcx, [rbx+1010h]; this
0x18001238d  call    ??1TransferMonitor@@QEAA@XZ; TransferMonitor::~TransferMonitor(void)
0x180012392  lea     rcx, [rbx+0F68h]; this
0x180012399  call    ??1ServiceWatchdog@@QEAA@XZ; ServiceWatchdog::~ServiceWatchdog(void)
0x18001239e  lea     rcx, [rbx+0EE8h]; this
0x1800123a5  call    ??1ClientsTracker@@QEAA@XZ; ClientsTracker::~ClientsTracker(void)
0x1800123aa  lea     rcx, [rbx+0DF0h]; this
0x1800123b1  call    ??1PackageManager@@QEAA@XZ; PackageManager::~PackageManager(void)
0x1800123b6  mov     rcx, [rbx+0DA8h]
0x1800123bd  test    rcx, rcx
0x1800123c0  jz      short loc_1800123F6
0x1800123c2  mov     rdx, [rbx+0DB8h]
0x1800123c9  sub     rdx, rcx
0x1800123cc  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800123d0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800123d5  mov     qword ptr [rbx+0DA8h], 0
0x1800123e0  mov     qword ptr [rbx+0DB0h], 0
0x1800123eb  mov     qword ptr [rbx+0DB8h], 0
0x1800123f6  mov     rcx, [rbx+0D90h]
0x1800123fd  test    rcx, rcx
0x180012400  jz      short loc_180012436
0x180012402  mov     rdx, [rbx+0DA0h]
0x180012409  sub     rdx, rcx
0x18001240c  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180012410  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012415  mov     qword ptr [rbx+0D90h], 0
0x180012420  mov     qword ptr [rbx+0D98h], 0
0x18001242b  mov     qword ptr [rbx+0DA0h], 0
0x180012436  lea     rcx, [rbx+0D88h]
0x18001243d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012442  lea     rcx, [rbx+0D80h]
0x180012449  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001244e  lea     rcx, [rbx+0D48h]; lpCriticalSection
0x180012455  call    cs:__imp_DeleteCriticalSection
0x18001245b  lea     rcx, [rbx+0D40h]
0x180012462  call    ??1?$unique_ptr@VThreadpool@@U?$default_delete@VThreadpool@@@std@@@std@@QEAA@XZ; std::unique_ptr<Threadpool>::~unique_ptr<Threadpool>(void)
0x180012467  mov     rcx, [rbx+0D28h]
0x18001246e  test    rcx, rcx
0x180012471  jz      short loc_1800124A7
0x180012473  mov     rdx, [rbx+0D38h]
0x18001247a  sub     rdx, rcx
0x18001247d  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180012481  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012486  mov     qword ptr [rbx+0D28h], 0
0x180012491  mov     qword ptr [rbx+0D30h], 0
0x18001249c  mov     qword ptr [rbx+0D38h], 0
0x1800124a7  add     rsp, 20h
0x1800124ab  pop     rbx
0x1800124ac  retn
```
