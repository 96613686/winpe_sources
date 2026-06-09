# ServerCacheContext::~ServerCacheContext(void)

- ea: `0x18006e0a4`
- end: `0x18006e11e`
- name: `??1ServerCacheContext@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(ServerCacheContext *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18006efcc`
- `0x1800b59a4`
- `0x1800b5a50`

## callees

- `0x18006c6f8`
- `0x18006de50`
- `0x18006f044`
- `0x18006f0d4`
- `0x18006f41c`
- `0x18006f4ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e0f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e10b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e0f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e10b`

## pseudocode

```c
void __fastcall ServerCacheContext::~ServerCacheContext(ServerCacheContext *this)
{
  *(_QWORD *)this = &ServerCacheContext::`vftable';
  ServerCacheContext::WaitForInitialize(this, 0xFFFFFFFF);
  ServerCacheContext::EndQueuedTasks(this);
  ScopedPtr<GlyphFactoryManager>::~ScopedPtr<GlyphFactoryManager>((char *)this + 544);
  ThreadpoolWork::~ThreadpoolWork((ServerCacheContext *)((char *)this + 528));
  ThreadpoolWork::~ThreadpoolWork((ServerCacheContext *)((char *)this + 520));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 12);
  ElementTaskQueue::~ElementTaskQueue((ServerCacheContext *)((char *)this + 416));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
  CacheContextImpl::~CacheContextImpl(this);
}

```

## disassembly

```asm
0x18006e0a4  push    rbx
0x18006e0a6  sub     rsp, 20h
0x18006e0aa  mov     rbx, rcx
0x18006e0ad  lea     rax, ??_7ServerCacheContext@@6B@; const ServerCacheContext::`vftable'
0x18006e0b4  mov     [rcx], rax
0x18006e0b7  or      edx, 0FFFFFFFFh; unsigned int
0x18006e0ba  call    ?WaitForInitialize@ServerCacheContext@@QEAA_NK@Z; ServerCacheContext::WaitForInitialize(ulong)
0x18006e0bf  mov     rcx, rbx; this
0x18006e0c2  call    ?EndQueuedTasks@ServerCacheContext@@QEAAXXZ; ServerCacheContext::EndQueuedTasks(void)
0x18006e0c7  lea     rcx, [rbx+220h]
0x18006e0ce  call    ??1?$ScopedPtr@VGlyphFactoryManager@@@@QEAA@XZ; ScopedPtr<GlyphFactoryManager>::~ScopedPtr<GlyphFactoryManager>(void)
0x18006e0d3  lea     rcx, [rbx+210h]; this
0x18006e0da  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x18006e0df  lea     rcx, [rbx+208h]; this
0x18006e0e6  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x18006e0eb  lea     rcx, [rbx+1E0h]; lpCriticalSection
0x18006e0f2  call    cs:__imp_DeleteCriticalSection
0x18006e0f8  lea     rcx, [rbx+1A0h]; this
0x18006e0ff  call    ??1ElementTaskQueue@@QEAA@XZ; ElementTaskQueue::~ElementTaskQueue(void)
0x18006e104  lea     rcx, [rbx+178h]; lpCriticalSection
0x18006e10b  call    cs:__imp_DeleteCriticalSection
0x18006e111  mov     rcx, rbx; this
0x18006e114  add     rsp, 20h
0x18006e118  pop     rbx
0x18006e119  jmp     ??1CacheContextImpl@@UEAA@XZ; CacheContextImpl::~CacheContextImpl(void)
```
