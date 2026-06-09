# CHostedCacheProtocol::~CHostedCacheProtocol(void)

- ea: `0x1800f6328`
- end: `0x1800f6416`
- name: `??1CHostedCacheProtocol@@UEAA@XZ`
- size: `238`
- prototype: `void __fastcall(CHostedCacheProtocol *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800ef484`
- `0x1800f65d0`
- `0x18015181c`

## callees

- `0x1800024f0`
- `0x18000573c`
- `0x18000e58c`
- `0x180018ec0`
- `0x18001edc0`
- `0x180020f60`
- `0x1800a7bd0`
- `0x1800f6270`
- `0x1800f6294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6354`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6398`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f63ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6354`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6398`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f63ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f640f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHostedCacheProtocol::~CHostedCacheProtocol(CHostedCacheProtocol *this)
{
  *(_QWORD *)this = &CHostedCacheProtocol::`vftable';
  *((_QWORD *)this + 132) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1064));
  operator delete(*((void **)this + 130));
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))this + 129);
  std::_Tree<std::_Tmap_traits<void *,CTnoCfgMgr::cfgmgr_notification_entry_tag,std::less<void *>,std::allocator<std::pair<void * const,CTnoCfgMgr::cfgmgr_notification_entry_tag>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoCfgMgr::cfgmgr_notification_entry_tag,std::less<void *>,std::allocator<std::pair<void * const,CTnoCfgMgr::cfgmgr_notification_entry_tag>>,0>>((char *)this + 1016);
  std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::~deque<tag_HOSTED_CACHE_QUEUED_OFFER>((__int64)this + 976);
  *((_QWORD *)this + 116) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
  *((_QWORD *)this + 106) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 856));
  std::_Tree<std::_Tmap_traits<TnoHoHoDk,unsigned long,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<TnoHoHoDk,unsigned long,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,unsigned long>>,0>>((char *)this + 832);
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CHostedCacheProtocol *)((char *)this + 704));
  DllHandle::Close((CHostedCacheProtocol *)((char *)this + 152));
  *((_QWORD *)this + 13) = &CHostedCacheList::`vftable';
  std::list<std::wstring>::~list<std::wstring>((char *)this + 112);
  operator delete(*((void **)this + 12));
  SmartPointer<CHostedCacheListManager>::Release((char *)this + 88);
  *(_QWORD *)this = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800f6328  mov     [rsp+arg_0], rbx
0x1800f632d  push    rdi
0x1800f632e  sub     rsp, 20h
0x1800f6332  mov     rbx, rcx
0x1800f6335  lea     rax, ??_7CHostedCacheProtocol@@6B@; const CHostedCacheProtocol::`vftable'
0x1800f633c  mov     [rcx], rax
0x1800f633f  lea     rdi, ??_7CritSec@@6B@; const CritSec::`vftable'
0x1800f6346  mov     [rcx+420h], rdi
0x1800f634d  add     rcx, 428h; lpCriticalSection
0x1800f6354  call    cs:__imp_DeleteCriticalSection
0x1800f635a  mov     rcx, [rbx+410h]; Block
0x1800f6361  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f6366  lea     rcx, [rbx+408h]
0x1800f636d  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x1800f6372  lea     rcx, [rbx+3F8h]
0x1800f6379  call    ??1?$_Tree@V?$_Tmap_traits@PEAXUcfgmgr_notification_entry_tag@CTnoCfgMgr@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXUcfgmgr_notification_entry_tag@CTnoCfgMgr@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,CTnoCfgMgr::cfgmgr_notification_entry_tag,std::less<void *>,std::allocator<std::pair<void * const,CTnoCfgMgr::cfgmgr_notification_entry_tag>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoCfgMgr::cfgmgr_notification_entry_tag,std::less<void *>,std::allocator<std::pair<void * const,CTnoCfgMgr::cfgmgr_notification_entry_tag>>,0>>(void)
0x1800f637e  lea     rcx, [rbx+3D0h]
0x1800f6385  call    ??1?$deque@Utag_HOSTED_CACHE_QUEUED_OFFER@@V?$allocator@Utag_HOSTED_CACHE_QUEUED_OFFER@@@std@@@std@@QEAA@XZ; std::deque<tag_HOSTED_CACHE_QUEUED_OFFER>::~deque<tag_HOSTED_CACHE_QUEUED_OFFER>(void)
0x1800f638a  mov     [rbx+3A0h], rdi
0x1800f6391  lea     rcx, [rbx+3A8h]; lpCriticalSection
0x1800f6398  call    cs:__imp_DeleteCriticalSection
0x1800f639e  mov     [rbx+350h], rdi
0x1800f63a5  lea     rcx, [rbx+358h]; lpCriticalSection
0x1800f63ac  call    cs:__imp_DeleteCriticalSection
0x1800f63b2  lea     rcx, [rbx+340h]
0x1800f63b9  call    ??1?$_Tree@V?$_Tmap_traits@VTnoHoHoDk@@KUTnoHoHoDkLess@@V?$allocator@U?$pair@$$CBVTnoHoHoDk@@K@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<TnoHoHoDk,ulong,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,ulong>>,0>>::~_Tree<std::_Tmap_traits<TnoHoHoDk,ulong,TnoHoHoDkLess,std::allocator<std::pair<TnoHoHoDk const,ulong>>,0>>(void)
0x1800f63be  lea     rcx, [rbx+2C0h]; this
0x1800f63c5  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x1800f63ca  nop
0x1800f63cb  lea     rcx, [rbx+98h]; this
0x1800f63d2  call    ?Close@DllHandle@@QEAAXXZ; DllHandle::Close(void)
0x1800f63d7  nop
0x1800f63d8  lea     rax, ??_7CHostedCacheList@@6B@; const CHostedCacheList::`vftable'
0x1800f63df  mov     [rbx+68h], rax
0x1800f63e3  lea     rcx, [rbx+70h]; void *
0x1800f63e7  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x1800f63ec  mov     rcx, [rbx+60h]; Block
0x1800f63f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f63f5  lea     rcx, [rbx+58h]
0x1800f63f9  call    ?Release@?$SmartPointer@VCHostedCacheListManager@@@@IEAAXXZ; SmartPointer<CHostedCacheListManager>::Release(void)
0x1800f63fe  mov     [rbx], rdi
0x1800f6401  lea     rcx, [rbx+8]
0x1800f6405  mov     rbx, [rsp+28h+arg_0]
0x1800f640a  add     rsp, 20h
0x1800f640e  pop     rdi
0x1800f640f  jmp     cs:__imp_DeleteCriticalSection
```
