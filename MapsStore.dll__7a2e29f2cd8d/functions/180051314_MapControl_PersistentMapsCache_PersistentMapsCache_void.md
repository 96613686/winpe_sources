# MapControl::PersistentMapsCache::~PersistentMapsCache(void)

- ea: `0x180051314`
- end: `0x1800513e7`
- name: `??1PersistentMapsCache@MapControl@@UEAA@XZ`
- size: `211`
- prototype: `void __fastcall(MapControl::PersistentMapsCache *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051c60`

## callees

- `0x180012720`
- `0x18001b9e0`
- `0x18002f15c`
- `0x18002f420`
- `0x180032964`
- `0x180041120`
- `0x180050d70`
- `0x180050f38`
- `0x180051044`
- `0x180051314`
- `0x180054000`
- `0x1800779d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800513b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800513b3`

## pseudocode

```c
void __fastcall MapControl::PersistentMapsCache::~PersistentMapsCache(MapControl::PersistentMapsCache *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &MapControl::PersistentMapsCache::`vftable';
  Pal::UntypedAsyncOperationCancelList::cancelAll((LPCRITICAL_SECTION)((char *)this + 72));
  Pal::TaskQueue::cancelAllTasks((MapControl::PersistentMapsCache *)((char *)this + 8));
  Pal::TaskQueue::waitForAllTasksToComplete((MapControl::PersistentMapsCache *)((char *)this + 8));
  Pal::TaskQueue::cancelAllTasks((MapControl::PersistentMapsCache *)((char *)this + 368));
  MapControl::PersistentMapsCache::flush(this);
  Pal::Lockable<std::map<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>::~Lockable<std::map<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>((char *)this + 400);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 47);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  std::wstring::_Tidy_deallocate((char *)this + 336);
  std::wstring::_Tidy_deallocate((char *)this + 304);
  std::_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>((char *)this + 280);
  std::_Hash<std::_Umap_traits<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>,std::_Uhash_compare<MapControl::PersistentDataKey const,std::hash<MapControl::PersistentDataKey const>,std::equal_to<MapControl::PersistentDataKey const>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>>>,1>>::~_Hash<std::_Umap_traits<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>,std::_Uhash_compare<MapControl::PersistentDataKey const,std::hash<MapControl::PersistentDataKey const>,std::equal_to<MapControl::PersistentDataKey const>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>>>,1>>((char *)this + 216);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList((MapControl::PersistentMapsCache *)((char *)this + 72));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  MapControl::PersistentCache::~PersistentCache(this);
}

```

## disassembly

```asm
0x180051314  mov     [rsp+arg_0], rbx
0x180051319  mov     [rsp+arg_8], rsi
0x18005131e  push    rdi
0x18005131f  sub     rsp, 20h
0x180051323  mov     rdi, rcx
0x180051326  lea     rax, ??_7PersistentMapsCache@MapControl@@6B@; const MapControl::PersistentMapsCache::`vftable'
0x18005132d  mov     [rcx], rax
0x180051330  add     rcx, 48h ; 'H'; lpCriticalSection
0x180051334  call    ?cancelAll@UntypedAsyncOperationCancelList@Pal@@QEAAXXZ; Pal::UntypedAsyncOperationCancelList::cancelAll(void)
0x180051339  lea     rcx, [rdi+8]; this
0x18005133d  call    ?cancelAllTasks@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::cancelAllTasks(void)
0x180051342  lea     rcx, [rdi+8]; this
0x180051346  call    ?waitForAllTasksToComplete@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::waitForAllTasksToComplete(void)
0x18005134b  lea     rcx, [rdi+170h]; this
0x180051352  call    ?cancelAllTasks@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::cancelAllTasks(void)
0x180051357  mov     rcx, rdi; this
0x18005135a  call    ?flush@PersistentMapsCache@MapControl@@UEAAXXZ; MapControl::PersistentMapsCache::flush(void)
0x18005135f  lea     rcx, [rdi+190h]
0x180051366  call    ??1?$Lockable@V?$map@UPersistentDataKey@MapControl@@V?$list@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@V?$allocator@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@@2@@std@@U?$less@UPersistentDataKey@MapControl@@@4@V?$allocator@U?$pair@$$CBUPersistentDataKey@MapControl@@V?$list@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@V?$allocator@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@@2@@std@@@std@@@4@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::map<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>::~Lockable<std::map<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>(void)
0x18005136b  mov     rcx, [rdi+178h]; this
0x180051372  test    rcx, rcx
0x180051375  jz      short loc_18005137C
0x180051377  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005137c  lea     rcx, [rdi+150h]
0x180051383  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051388  lea     rcx, [rdi+130h]
0x18005138f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051394  lea     rcx, [rdi+118h]
0x18005139b  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@ULessIndexLru@PersistentMapsCache@MapControl@@V?$allocator@V?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>,MapControl::PersistentMapsCache::LessIndexLru,std::allocator<std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry>>,0>>(void)
0x1800513a0  lea     rcx, [rdi+0D8h]
0x1800513a7  call    ??1?$_Hash@V?$_Umap_traits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@@Utility@@@std@@V?$_Uhash_compare@$$CBUPersistentDataKey@MapControl@@U?$hash@$$CBUPersistentDataKey@MapControl@@@std@@U?$equal_to@$$CBUPersistentDataKey@MapControl@@@4@@4@V?$allocator@U?$pair@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@@Utility@@@std@@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>,std::_Uhash_compare<MapControl::PersistentDataKey const,std::hash<MapControl::PersistentDataKey const>,std::equal_to<MapControl::PersistentDataKey const>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>>>,1>>::~_Hash<std::_Umap_traits<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>,std::_Uhash_compare<MapControl::PersistentDataKey const,std::hash<MapControl::PersistentDataKey const>,std::equal_to<MapControl::PersistentDataKey const>>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::shared_ptr<Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::CacheEntry>>>,1>>(void)
0x1800513ac  lea     rcx, [rdi+0B0h]; lpCriticalSection
0x1800513b3  call    cs:__imp_DeleteCriticalSection
0x1800513b9  lea     rcx, [rdi+48h]; this
0x1800513bd  call    ??1UntypedAsyncOperationCancelList@Pal@@QEAA@XZ; Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList(void)
0x1800513c2  mov     rcx, [rdi+40h]; this
0x1800513c6  test    rcx, rcx
0x1800513c9  jz      short loc_1800513D0
0x1800513cb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800513d0  mov     rcx, rdi; this
0x1800513d3  mov     rbx, [rsp+28h+arg_0]
0x1800513d8  mov     rsi, [rsp+28h+arg_8]
0x1800513dd  add     rsp, 20h
0x1800513e1  pop     rdi
0x1800513e2  jmp     ??1PersistentCache@MapControl@@UEAA@XZ; MapControl::PersistentCache::~PersistentCache(void)
```
