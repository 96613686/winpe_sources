# Wns::CPTransactionRequestManager::~CPTransactionRequestManager(void)

- ea: `0x18002d3ec`
- end: `0x18002d46c`
- name: `??1CPTransactionRequestManager@Wns@@QEAA@XZ`
- size: `128`
- prototype: `void __fastcall(Wns::CPTransactionRequestManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d4ac`
- `0x180035a23`

## callees

- `0x180006160`
- `0x18001664c`
- `0x18002d114`
- `0x18002d170`
- `0x18002d1cc`
- `0x18002d338`
- `0x18002d3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d3fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d3fc`

## pseudocode

```c
void __fastcall Wns::CPTransactionRequestManager::~CPTransactionRequestManager(Wns::CPTransactionRequestManager *this)
{
  __int64 v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  std::_Hash<std::_Umap_traits<unsigned __int64,enum Wns::CPTMode,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,enum Wns::CPTMode>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,enum Wns::CPTMode,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,enum Wns::CPTMode>>,0>>((_QWORD *)this + 21);
  std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>((_QWORD *)this + 13);
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(
      v2,
      *((_QWORD *)this + 11));
    std::_Deallocate<16>(
      *((_QWORD **)this + 10),
      (*((_QWORD *)this + 12) - *((_QWORD *)this + 10)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<void (void *),&void Wns::CleanupTimerQueue(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<void (void *),&void Wns::CleanupTimerQueue(void *)>>((char *)this + 72);
  std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::~_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18002d3ec  push    rbx
0x18002d3ee  sub     rsp, 20h
0x18002d3f2  mov     rbx, rcx
0x18002d3f5  add     rcx, 0F0h; lpCriticalSection
0x18002d3fc  call    cs:__imp_DeleteCriticalSection
0x18002d402  lea     rcx, [rbx+0A8h]
0x18002d409  call    ??1?$_Hash@V?$_Umap_traits@_KW4CPTMode@Wns@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KW4CPTMode@Wns@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<unsigned __int64,Wns::CPTMode,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Wns::CPTMode>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,Wns::CPTMode,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Wns::CPTMode>>,0>>(void)
0x18002d40e  lea     rcx, [rbx+68h]
0x18002d412  call    ??1?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>(void)
0x18002d417  mov     rcx, [rbx+50h]
0x18002d41b  test    rcx, rcx
0x18002d41e  jz      short loc_18002D455
0x18002d420  mov     rdx, [rbx+58h]
0x18002d424  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>> &)
0x18002d429  mov     rcx, [rbx+50h]
0x18002d42d  mov     rdx, [rbx+60h]
0x18002d431  sub     rdx, rcx
0x18002d434  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002d438  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d43d  mov     qword ptr [rbx+50h], 0
0x18002d445  mov     qword ptr [rbx+58h], 0
0x18002d44d  mov     qword ptr [rbx+60h], 0
0x18002d455  lea     rcx, [rbx+48h]
0x18002d459  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@$$A6AXPEAX@Z$1?CleanupTimerQueue@Wns@@YAX0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<void (void *),&Wns::CleanupTimerQueue(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<void (void *),&Wns::CleanupTimerQueue(void *)>>(void)
0x18002d45e  lea     rcx, [rbx+8]
0x18002d462  add     rsp, 20h
0x18002d466  pop     rbx
0x18002d467  jmp     ??1?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::~_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>(void)
```
