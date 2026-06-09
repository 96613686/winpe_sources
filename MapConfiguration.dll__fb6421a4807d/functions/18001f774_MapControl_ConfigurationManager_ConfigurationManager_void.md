# MapControl::ConfigurationManager::~ConfigurationManager(void)

- ea: `0x18001f774`
- end: `0x18001f939`
- name: `??1ConfigurationManager@MapControl@@QEAA@XZ`
- size: `453`
- prototype: `void __fastcall(MapControl::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bbf4`

## callees

- `0x18000b938`
- `0x18000c354`
- `0x180010f34`
- `0x180013da8`
- `0x18001a79c`
- `0x18001b2f4`
- `0x18001b884`
- `0x18001d71c`
- `0x18001d758`
- `0x18001dc60`
- `0x18001f668`
- `0x18001f774`
- `0x180020ad4`
- `0x1800222a4`
- `0x180029eb8`
- `0x180034538`
- `0x18003ae34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f907`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f907`

## pseudocode

```c
void __fastcall MapControl::ConfigurationManager::~ConfigurationManager(
        MapControl::ConfigurationManager *this,
        __int64 a2)
{
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  std::_Ref_count_base *v6; // rcx

  LOBYTE(a2) = 1;
  std::_Atomic_storage<bool,1>::store((char *)this + 563, a2);
  Pal::CppEvent<>::detach(*((_QWORD *)this + 21) + 56LL, (char *)this + 184);
  MapControl::ConfigurationManager::stopTimer(this);
  Pal::UntypedAsyncOperationCancelList::cancelAll((LPCRITICAL_SECTION)((char *)this + 456));
  Pal::TaskQueue::cancelAllTasks(*((Pal::TaskQueue **)this + 14));
  Utility::PrioritizedTaskQueue::cancelAllTasks(*((Utility::PrioritizedTaskQueue **)this + 40));
  if ( *((_BYTE *)this + 561) )
    *((_BYTE *)this + 561) = 0;
  Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList((MapControl::ConfigurationManager *)((char *)this + 456));
  std::wstring::_Tidy_deallocate((char *)this + 416);
  std::wstring::_Tidy_deallocate((char *)this + 368);
  std::wstring::_Tidy_deallocate((char *)this + 336);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>((char *)this + 320);
  Json::Value::~Value((MapControl::ConfigurationManager *)((char *)this + 272));
  std::wstring::_Tidy_deallocate((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 22);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>(v4, *((_QWORD *)this + 19));
    std::_Deallocate<16>(
      *((void **)this + 18),
      (*((_QWORD *)this + 20) - *((_QWORD *)this + 18)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
  }
  v5 = *((_QWORD *)this + 15);
  if ( v5 )
  {
    std::_Destroy_range<std::allocator<std::map<enum MapControl::ConfigurationKeys,std::wstring>>>(
      v5,
      *((_QWORD *)this + 16));
    std::_Deallocate<16>(
      *((void **)this + 15),
      (*((_QWORD *)this + 17) - *((_QWORD *)this + 15)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
  }
  std::unique_ptr<Pal::TaskQueue>::~unique_ptr<Pal::TaskQueue>((char *)this + 112);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 12);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    (void **)this + 4,
    (__int64)this + 32);
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    (void **)this + 2,
    (__int64)this + 16);
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    (void **)this,
    (__int64)this);
}

```

## disassembly

```asm
0x18001f774  push    rbx
0x18001f776  push    rsi
0x18001f777  push    rdi
0x18001f778  push    r14
0x18001f77a  sub     rsp, 28h
0x18001f77e  mov     rbx, rcx
0x18001f781  add     rcx, 233h
0x18001f788  mov     dl, 1
0x18001f78a  call    ?store@?$_Atomic_storage@_N$00@std@@QEAAX_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::store(bool,std::memory_order)
0x18001f78f  lea     rdx, [rbx+0B8h]
0x18001f796  mov     rcx, [rbx+0A8h]
0x18001f79d  add     rcx, 38h ; '8'
0x18001f7a1  call    ?detach@?$CppEvent@$$V@Pal@@QEAA_NPEAVEventId@2@@Z; Pal::CppEvent<>::detach(Pal::EventId *)
0x18001f7a6  mov     rcx, rbx; this
0x18001f7a9  call    ?stopTimer@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::stopTimer(void)
0x18001f7ae  lea     rsi, [rbx+1C8h]
0x18001f7b5  mov     rcx, rsi; lpCriticalSection
0x18001f7b8  call    ?cancelAll@UntypedAsyncOperationCancelList@Pal@@QEAAXXZ; Pal::UntypedAsyncOperationCancelList::cancelAll(void)
0x18001f7bd  mov     rcx, [rbx+70h]; this
0x18001f7c1  call    ?cancelAllTasks@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::cancelAllTasks(void)
0x18001f7c6  lea     r14, [rbx+140h]
0x18001f7cd  mov     rcx, [r14]; this
0x18001f7d0  call    ?cancelAllTasks@PrioritizedTaskQueue@Utility@@QEAAXXZ; Utility::PrioritizedTaskQueue::cancelAllTasks(void)
0x18001f7d5  cmp     byte ptr [rbx+231h], 0
0x18001f7dc  jz      short loc_18001F7E5
0x18001f7de  mov     byte ptr [rbx+231h], 0
0x18001f7e5  mov     rcx, rsi; this
0x18001f7e8  call    ??1UntypedAsyncOperationCancelList@Pal@@QEAA@XZ; Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList(void)
0x18001f7ed  lea     rcx, [rbx+1A0h]
0x18001f7f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f7f9  lea     rcx, [rbx+170h]
0x18001f800  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f805  lea     rcx, [rbx+150h]
0x18001f80c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f811  mov     rcx, r14
0x18001f814  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18001f819  lea     rcx, [rbx+110h]; this
0x18001f820  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18001f825  lea     rcx, [rbx+0E8h]
0x18001f82c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f831  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001f838  call    cs:__imp_DeleteCriticalSection
0x18001f83e  mov     rcx, [rbx+0B0h]; this
0x18001f845  test    rcx, rcx
0x18001f848  jz      short loc_18001F84F
0x18001f84a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f84f  mov     rcx, [rbx+90h]
0x18001f856  test    rcx, rcx
0x18001f859  jz      short loc_18001F8A2
0x18001f85b  mov     rdx, [rbx+98h]
0x18001f862  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPrioritizableTask@Utility@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>(std::shared_ptr<Utility::PrioritizableTask> *,std::shared_ptr<Utility::PrioritizableTask> * const,std::allocator<std::shared_ptr<Utility::PrioritizableTask>> &)
0x18001f867  mov     rcx, [rbx+90h]
0x18001f86e  mov     rdx, [rbx+0A0h]
0x18001f875  sub     rdx, rcx
0x18001f878  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001f87c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001f881  mov     qword ptr [rbx+90h], 0
0x18001f88c  mov     qword ptr [rbx+98h], 0
0x18001f897  mov     qword ptr [rbx+0A0h], 0
0x18001f8a2  mov     rcx, [rbx+78h]
0x18001f8a6  test    rcx, rcx
0x18001f8a9  jz      short loc_18001F8EC
0x18001f8ab  mov     rdx, [rbx+80h]
0x18001f8b2  call    ??$_Destroy_range@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@std@@@std@@YAXPEAV?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@0@QEAV10@AEAV?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::map<MapControl::ConfigurationKeys,std::wstring>>>(std::map<MapControl::ConfigurationKeys,std::wstring> *,std::map<MapControl::ConfigurationKeys,std::wstring> * const,std::allocator<std::map<MapControl::ConfigurationKeys,std::wstring>> &)
0x18001f8b7  mov     rcx, [rbx+78h]
0x18001f8bb  mov     rdx, [rbx+88h]
0x18001f8c2  sub     rdx, rcx
0x18001f8c5  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001f8c9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001f8ce  mov     qword ptr [rbx+78h], 0
0x18001f8d6  mov     qword ptr [rbx+80h], 0
0x18001f8e1  mov     qword ptr [rbx+88h], 0
0x18001f8ec  lea     rcx, [rbx+70h]
0x18001f8f0  call    ??1?$unique_ptr@VTaskQueue@Pal@@U?$default_delete@VTaskQueue@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::TaskQueue>::~unique_ptr<Pal::TaskQueue>(void)
0x18001f8f5  mov     rcx, [rbx+60h]; this
0x18001f8f9  test    rcx, rcx
0x18001f8fc  jz      short loc_18001F903
0x18001f8fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f903  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001f907  call    cs:__imp_DeleteCriticalSection
0x18001f90d  lea     rcx, [rbx+20h]
0x18001f911  mov     rdx, rcx
0x18001f914  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
0x18001f919  lea     rcx, [rbx+10h]
0x18001f91d  mov     rdx, rcx
0x18001f920  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
0x18001f925  mov     rdx, rbx
0x18001f928  mov     rcx, rbx
0x18001f92b  add     rsp, 28h
0x18001f92f  pop     r14
0x18001f931  pop     rdi
0x18001f932  pop     rsi
0x18001f933  pop     rbx
0x18001f934  jmp     ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
```
