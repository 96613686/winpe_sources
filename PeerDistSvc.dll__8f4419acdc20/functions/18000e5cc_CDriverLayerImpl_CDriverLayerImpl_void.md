# CDriverLayerImpl::~CDriverLayerImpl(void)

- ea: `0x18000e5cc`
- end: `0x18000e6c4`
- name: `??1CDriverLayerImpl@@UEAA@XZ`
- size: `248`
- prototype: `void __fastcall(CDriverLayerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e770`

## callees

- `0x1800024f0`
- `0x18000e55c`
- `0x18000e58c`
- `0x18000ecf4`
- `0x18001edc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e633`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e653`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e633`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e653`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6a9`

## pseudocode

```c
void __fastcall CDriverLayerImpl::~CDriverLayerImpl(CDriverLayerImpl *this)
{
  *(_QWORD *)this = &CDriverLayerImpl::`vftable'{for `ITnoDriverLayer'};
  *((_QWORD *)this + 1) = &CDriverLayerImpl::`vftable'{for `CritSec'};
  operator delete(*((void **)this + 154));
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))this + 155);
  SmartPointer<CRepubJetSessionContext>::Release((char *)this + 1224);
  std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>((void **)this + 150);
  *((_QWORD *)this + 144) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 29);
  std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>((void **)this + 142);
  *((_QWORD *)this + 136) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))this + 134);
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CDriverLayerImpl *)((char *)this + 936));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CDriverLayerImpl *)((char *)this + 824));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CDriverLayerImpl *)((char *)this + 712));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CDriverLayerImpl *)((char *)this + 600));
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))this + 74);
  *((_QWORD *)this + 1) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ITnoNetCostMonitor::`vftable';
}

```

## disassembly

```asm
0x18000e5cc  mov     [rsp+arg_0], rbx
0x18000e5d1  push    rdi
0x18000e5d2  sub     rsp, 20h
0x18000e5d6  lea     rax, ??_7CDriverLayerImpl@@6BITnoDriverLayer@@@; const CDriverLayerImpl::`vftable'{for `ITnoDriverLayer'}
0x18000e5dd  mov     rbx, rcx
0x18000e5e0  mov     [rcx], rax
0x18000e5e3  lea     rax, ??_7CDriverLayerImpl@@6BCritSec@@@; const CDriverLayerImpl::`vftable'{for `CritSec'}
0x18000e5ea  mov     [rcx+8], rax
0x18000e5ee  mov     rcx, [rcx+4D0h]; Block
0x18000e5f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e5fa  lea     rcx, [rbx+4D8h]
0x18000e601  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18000e606  lea     rcx, [rbx+4C8h]
0x18000e60d  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18000e612  lea     rcx, [rbx+4B0h]
0x18000e619  call    ??1?$_Tree@V?$_Tmap_traits@PEAXPEAVCTnoDecompressor@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXPEAVCTnoDecompressor@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>(void)
0x18000e61e  lea     rdi, ??_7CritSec@@6B@; const CritSec::`vftable'
0x18000e625  lea     rcx, [rbx+488h]; lpCriticalSection
0x18000e62c  mov     [rbx+480h], rdi
0x18000e633  call    cs:__imp_DeleteCriticalSection
0x18000e639  lea     rcx, [rbx+470h]
0x18000e640  call    ??1?$_Tree@V?$_Tmap_traits@PEAXPEAVCTnoDecompressor@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXPEAVCTnoDecompressor@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>(void)
0x18000e645  lea     rcx, [rbx+448h]; lpCriticalSection
0x18000e64c  mov     [rbx+440h], rdi
0x18000e653  call    cs:__imp_DeleteCriticalSection
0x18000e659  lea     rcx, [rbx+430h]
0x18000e660  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18000e665  lea     rcx, [rbx+3A8h]; this
0x18000e66c  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18000e671  lea     rcx, [rbx+338h]; this
0x18000e678  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18000e67d  lea     rcx, [rbx+2C8h]; this
0x18000e684  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18000e689  lea     rcx, [rbx+258h]; this
0x18000e690  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18000e695  lea     rcx, [rbx+250h]
0x18000e69c  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18000e6a1  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000e6a5  mov     [rbx+8], rdi
0x18000e6a9  call    cs:__imp_DeleteCriticalSection
0x18000e6af  lea     rax, ??_7ITnoNetCostMonitor@@6B@; const ITnoNetCostMonitor::`vftable'
0x18000e6b6  mov     [rbx], rax
0x18000e6b9  mov     rbx, [rsp+28h+arg_0]
0x18000e6be  add     rsp, 20h
0x18000e6c2  pop     rdi
0x18000e6c3  retn
```
