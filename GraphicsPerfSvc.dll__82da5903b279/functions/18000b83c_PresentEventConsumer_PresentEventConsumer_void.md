# PresentEventConsumer::~PresentEventConsumer(void)

- ea: `0x18000b83c`
- end: `0x18000b889`
- name: `??1PresentEventConsumer@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(PresentEventConsumer *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b890`
- `0x1800134e4`
- `0x180014ab0`
- `0x18002f54b`

## callees

- `0x18000b704`
- `0x18000b734`
- `0x18000b7a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b873`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b873`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PresentEventConsumer::~PresentEventConsumer(PresentEventConsumer *this)
{
  std::unique_ptr<ITrackedProcessConsumer>::~unique_ptr<ITrackedProcessConsumer>((__int64 (__fastcall ****)(_QWORD, __int64))this + 23);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>((void **)this + 17);
  std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>((char *)this + 88);
  std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_QWORD *)this = &IPresentEventConsumer::`vftable';
}

```

## disassembly

```asm
0x18000b83c  push    rbx
0x18000b83e  sub     rsp, 20h
0x18000b842  mov     rbx, rcx
0x18000b845  add     rcx, 0B8h
0x18000b84c  call    ??1?$unique_ptr@UITrackedProcessConsumer@@U?$default_delete@UITrackedProcessConsumer@@@std@@@std@@QEAA@XZ; std::unique_ptr<ITrackedProcessConsumer>::~unique_ptr<ITrackedProcessConsumer>(void)
0x18000b851  lea     rcx, [rbx+88h]
0x18000b858  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>(void)
0x18000b85d  lea     rcx, [rbx+58h]
0x18000b861  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000b866  lea     rcx, [rbx+30h]
0x18000b86a  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000b86f  lea     rcx, [rbx+8]; lpCriticalSection
0x18000b873  call    cs:__imp_DeleteCriticalSection
0x18000b879  lea     rax, ??_7IPresentEventConsumer@@6B@; const IPresentEventConsumer::`vftable'
0x18000b880  mov     [rbx], rax
0x18000b883  add     rsp, 20h
0x18000b887  pop     rbx
0x18000b888  retn
```
