# CScheduleMgr::~CScheduleMgr(void)

- ea: `0x18000ed5c`
- end: `0x18000ed8d`
- name: `??1CScheduleMgr@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CScheduleMgr *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180021590`

## callees

- `0x18000ed94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed76`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed76`

## pseudocode

```c
void __fastcall CScheduleMgr::~CScheduleMgr(CScheduleMgr *this)
{
  DeleteCriticalSection(&CScheduleMgr::CritLockExpired);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>((char *)this + 336);
}

```

## disassembly

```asm
0x18000ed5c  push    rbx
0x18000ed5e  sub     rsp, 20h
0x18000ed62  mov     rbx, rcx
0x18000ed65  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ed6c  call    cs:__imp_DeleteCriticalSection
0x18000ed72  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000ed76  call    cs:__imp_DeleteCriticalSection
0x18000ed7c  lea     rcx, [rbx+150h]
0x18000ed83  add     rsp, 20h
0x18000ed87  pop     rbx
0x18000ed88  jmp     ??1?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>(void)
```
