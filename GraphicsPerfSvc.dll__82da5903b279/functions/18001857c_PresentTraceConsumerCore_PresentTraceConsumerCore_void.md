# PresentTraceConsumerCore::~PresentTraceConsumerCore(void)

- ea: `0x18001857c`
- end: `0x180018685`
- name: `??1PresentTraceConsumerCore@@UEAA@XZ`
- size: `265`
- prototype: `void __fastcall(PresentTraceConsumerCore *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011f40`
- `0x180018860`

## callees

- `0x18000b550`
- `0x18000d778`
- `0x180017d0c`
- `0x180017d68`
- `0x180017e20`
- `0x180017f6c`
- `0x180018250`
- `0x18001857c`
- `0x1800269d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018671`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018671`

## pseudocode

```c
void __fastcall PresentTraceConsumerCore::~PresentTraceConsumerCore(PresentTraceConsumerCore *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &PresentTraceConsumerCore::`vftable'{for `ITraceConsumer'};
  *((_QWORD *)this + 1) = &ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'};
  v2 = (void *)*((_QWORD *)this + 99);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 101) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 99) = 0;
    *((_QWORD *)this + 100) = 0;
    *((_QWORD *)this + 101) = 0;
  }
  std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>((__int64)this + 720);
  std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::~_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>((__int64)this + 656);
  std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>((__int64)this + 592);
  std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>((__int64)this + 520);
  std::string::_Tidy_deallocate((char *)this + 448);
  std::unique_ptr<PMTraceConsumer>::~unique_ptr<PMTraceConsumer>((PMTraceConsumer **)this + 33);
  v3 = (void *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    std::_Deallocate<16>(v3, *((_QWORD *)this + 32) - (_QWORD)v3);
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 31) = 0;
    *((_QWORD *)this + 32) = 0;
  }
  std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>((char *)this + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  TraceSession::~TraceSession((PresentTraceConsumerCore *)((char *)this + 16));
}

```

## disassembly

```asm
0x18001857c  push    rbx
0x18001857e  sub     rsp, 20h
0x180018582  lea     rax, ??_7PresentTraceConsumerCore@@6BITraceConsumer@@@; const PresentTraceConsumerCore::`vftable'{for `ITraceConsumer'}
0x180018589  mov     rbx, rcx
0x18001858c  mov     [rcx], rax
0x18001858f  lea     rax, ??_7ServiceTraceConsumer@@6BITelemetryCounters@@@; const ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'}
0x180018596  mov     [rcx+8], rax
0x18001859a  mov     rcx, [rcx+318h]
0x1800185a1  test    rcx, rcx
0x1800185a4  jz      short loc_1800185DA
0x1800185a6  mov     rdx, [rbx+328h]
0x1800185ad  sub     rdx, rcx
0x1800185b0  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800185b4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800185b9  mov     qword ptr [rbx+318h], 0
0x1800185c4  mov     qword ptr [rbx+320h], 0
0x1800185cf  mov     qword ptr [rbx+328h], 0
0x1800185da  lea     rcx, [rbx+2D0h]
0x1800185e1  call    ??1?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>(void)
0x1800185e6  lea     rcx, [rbx+290h]
0x1800185ed  call    ??1?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::~_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>(void)
0x1800185f2  lea     rcx, [rbx+250h]
0x1800185f9  call    ??1?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>(void)
0x1800185fe  lea     rcx, [rbx+208h]
0x180018605  call    ??1?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>(void)
0x18001860a  lea     rcx, [rbx+1C0h]
0x180018611  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018616  lea     rcx, [rbx+108h]
0x18001861d  call    ??1?$unique_ptr@UPMTraceConsumer@@U?$default_delete@UPMTraceConsumer@@@std@@@std@@QEAA@XZ; std::unique_ptr<PMTraceConsumer>::~unique_ptr<PMTraceConsumer>(void)
0x180018622  mov     rcx, [rbx+0F0h]
0x180018629  test    rcx, rcx
0x18001862c  jz      short loc_18001865E
0x18001862e  mov     rdx, [rbx+100h]
0x180018635  sub     rdx, rcx
0x180018638  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001863d  mov     qword ptr [rbx+0F0h], 0
0x180018648  mov     qword ptr [rbx+0F8h], 0
0x180018653  mov     qword ptr [rbx+100h], 0
0x18001865e  lea     rcx, [rbx+0C8h]
0x180018665  call    ??1?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>(void)
0x18001866a  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180018671  call    cs:__imp_DeleteCriticalSection
0x180018677  lea     rcx, [rbx+10h]; this
0x18001867b  add     rsp, 20h
0x18001867f  pop     rbx
0x180018680  jmp     ??1TraceSession@@QEAA@XZ; TraceSession::~TraceSession(void)
```
