# MapControl::PersistentMapsCache::removeAllFiles(void)

- ea: `0x180054e90`
- end: `0x180054fa7`
- name: `?removeAllFiles@PersistentMapsCache@MapControl@@UEAAXXZ`
- size: `279`
- prototype: `void __fastcall(MapControl::PersistentMapsCache *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d090`
- `0x180011d90`
- `0x180012720`
- `0x18002de08`
- `0x18002f99c`
- `0x18002f9c4`
- `0x180032964`
- `0x1800403ac`
- `0x180053c9c`
- `0x180053cf4`
- `0x1800779ec`
- `0x180077c34`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054f2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054f4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054f4f`

## string_xrefs

- `0x180054eea`: `mapscache`
- `0x180054f5b`: `mapscache`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall MapControl::PersistentMapsCache::removeAllFiles(MapControl::PersistentMapsCache *this)
{
  RTL_SRWLOCK *Instance; // rbx
  struct Pal::Infrastructure *v3; // rax
  _BYTE v4[16]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v5[32]; // [rsp+38h] [rbp-30h] BYREF

  Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance();
  Pal::PerformanceTracer::traceEvent<>(Instance, (struct Pal::PerformanceEventId *)&dword_1800F1078);
  Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(
    (Pal::ScopedPerformanceSpan *)v4,
    (struct Pal::PerformanceTracer *)Instance,
    (const struct Pal::PerformanceEventId *)&dword_1800F1084);
  Pal::TaskQueue::cancelAllTasks((MapControl::PersistentMapsCache *)((char *)this + 368));
  LODWORD(Instance) = *((_DWORD *)this + 96);
  std::wstring::wstring(v5, L"mapscache");
  v3 = Pal::Infrastructure::getInstance();
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)v3 + 1) + 72LL))(
    *((_QWORD *)v3 + 1),
    v5,
    (unsigned int)Instance);
  std::wstring::_Tidy_deallocate(v5);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  std::_Hash<std::_Umap_traits<MapControl::PersistentDataKey,std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,std::_Uhash_compare<MapControl::PersistentDataKey,std::hash<MapControl::PersistentDataKey>,std::equal_to<MapControl::PersistentDataKey>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>>,0>>::clear((char *)this + 216);
  std::_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>::clear((char *)this + 280);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  LODWORD(Instance) = *((_DWORD *)this + 96);
  std::wstring::wstring(v5, L"mapscache");
  Pal::IO::createFolder(v5, (unsigned int)Instance);
  std::wstring::_Tidy_deallocate(v5);
  Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan((Pal::ScopedPerformanceSpan *)v4);
}

```

## disassembly

```asm
0x180054e90  mov     [rsp+arg_8], rbx
0x180054e95  push    rdi
0x180054e96  sub     rsp, 60h
0x180054e9a  mov     rax, cs:__security_cookie
0x180054ea1  xor     rax, rsp
0x180054ea4  mov     [rsp+68h+var_10], rax
0x180054ea9  mov     rdi, rcx
0x180054eac  call    ?getInstance@?$PerformanceTracerSingleton@VDataLoaderPerformanceTracer@MapControl@@@Pal@@KAAEAVDataLoaderPerformanceTracer@MapControl@@XZ; Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance(void)
0x180054eb1  mov     rbx, rax
0x180054eb4  lea     rdx, dword_1800F1078; struct Pal::PerformanceEventId *
0x180054ebb  mov     rcx, rax; SRWLock
0x180054ebe  call    ??$traceEvent@$$V@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@@Z; Pal::PerformanceTracer::traceEvent<>(Pal::PerformanceEventId const &)
0x180054ec3  lea     r8, dword_1800F1084; struct Pal::PerformanceEventId *
0x180054eca  mov     rdx, rbx; struct Pal::PerformanceTracer *
0x180054ecd  lea     rcx, [rsp+68h+var_40]; this
0x180054ed2  call    ??0ScopedPerformanceSpan@Pal@@QEAA@PEAVPerformanceTracer@1@AEBVPerformanceEventId@1@@Z; Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(Pal::PerformanceTracer *,Pal::PerformanceEventId const &)
0x180054ed7  nop
0x180054ed8  lea     rcx, [rdi+170h]; this
0x180054edf  call    ?cancelAllTasks@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::cancelAllTasks(void)
0x180054ee4  mov     ebx, [rdi+180h]
0x180054eea  lea     rdx, aMapscache_0; "mapscache"
0x180054ef1  lea     rcx, [rsp+68h+var_30]
0x180054ef6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054efb  nop
0x180054efc  call    ?getInstance@Infrastructure@Pal@@CAAEAV12@XZ; Pal::Infrastructure::getInstance(void)
0x180054f01  mov     rcx, [rax+8]
0x180054f05  mov     rax, [rcx]
0x180054f08  mov     r8d, ebx
0x180054f0b  lea     rdx, [rsp+68h+var_30]
0x180054f10  mov     rax, [rax+48h]
0x180054f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f19  nop
0x180054f1a  lea     rcx, [rsp+68h+var_30]
0x180054f1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054f24  lea     rbx, [rdi+0B0h]
0x180054f2b  mov     rcx, rbx; lpCriticalSection
0x180054f2e  call    cs:__imp_EnterCriticalSection
0x180054f34  lea     rcx, [rdi+0D8h]
0x180054f3b  call    ?clear@?$_Hash@V?$_Umap_traits@UPersistentDataKey@MapControl@@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@V?$_Uhash_compare@UPersistentDataKey@MapControl@@U?$hash@UPersistentDataKey@MapControl@@@std@@U?$equal_to@UPersistentDataKey@MapControl@@@4@@4@V?$allocator@U?$pair@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<MapControl::PersistentDataKey,std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,std::_Uhash_compare<MapControl::PersistentDataKey,std::hash<MapControl::PersistentDataKey>,std::equal_to<MapControl::PersistentDataKey>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>>,0>>::clear(void)
0x180054f40  lea     rcx, [rdi+118h]
0x180054f47  call    ?clear@?$_Tree@V?$_Tset_traits@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@ULessIndexLru@PersistentMapsCache@MapControl@@V?$allocator@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>::clear(void)
0x180054f4c  mov     rcx, rbx; lpCriticalSection
0x180054f4f  call    cs:__imp_LeaveCriticalSection
0x180054f55  mov     ebx, [rdi+180h]
0x180054f5b  lea     rdx, aMapscache_0; "mapscache"
0x180054f62  lea     rcx, [rsp+68h+var_30]
0x180054f67  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054f6c  nop
0x180054f6d  mov     edx, ebx
0x180054f6f  lea     rcx, [rsp+68h+var_30]
0x180054f74  call    ?createFolder@IO@Pal@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z; Pal::IO::createFolder(std::wstring const &,Pal::FileLocation)
0x180054f79  nop
0x180054f7a  lea     rcx, [rsp+68h+var_30]
0x180054f7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054f84  nop
0x180054f85  lea     rcx, [rsp+68h+var_40]; this
0x180054f8a  call    ??1ScopedPerformanceSpan@Pal@@QEAA@XZ; Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan(void)
0x180054f8f  mov     rcx, [rsp+68h+var_10]
0x180054f94  xor     rcx, rsp; StackCookie
0x180054f97  call    __security_check_cookie
0x180054f9c  mov     rbx, [rsp+68h+arg_8]
0x180054fa1  add     rsp, 60h
0x180054fa5  pop     rdi
0x180054fa6  retn
```
