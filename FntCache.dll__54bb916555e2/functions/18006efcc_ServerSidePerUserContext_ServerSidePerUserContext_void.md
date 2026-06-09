# ServerSidePerUserContext::~ServerSidePerUserContext(void)

- ea: `0x18006efcc`
- end: `0x18006f03d`
- name: `??1ServerSidePerUserContext@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(ServerSidePerUserContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006ef90`

## callees

- `0x180028c50`
- `0x18004ff84`
- `0x18006e0a4`
- `0x18006f044`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f025`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f025`

## pseudocode

```c
void __fastcall ServerSidePerUserContext::~ServerSidePerUserContext(ServerSidePerUserContext *this)
{
  *(_QWORD *)this = &ServerSidePerUserContext::`vftable';
  ServerCacheContext::EndQueuedTasks(this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 77) + 32LL))(*((_QWORD *)this + 77));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 616);
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 75));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 592);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  ServerCacheContext::~ServerCacheContext(this);
}

```

## disassembly

```asm
0x18006efcc  mov     [rsp+arg_0], rbx
0x18006efd1  push    rdi
0x18006efd2  sub     rsp, 20h
0x18006efd6  mov     rdi, rcx
0x18006efd9  lea     rax, ??_7ServerSidePerUserContext@@6B@; const ServerSidePerUserContext::`vftable'
0x18006efe0  mov     [rcx], rax
0x18006efe3  call    ?EndQueuedTasks@ServerCacheContext@@QEAAXXZ; ServerCacheContext::EndQueuedTasks(void)
0x18006efe8  lea     rbx, [rdi+268h]
0x18006efef  mov     rcx, [rbx]
0x18006eff2  mov     rax, [rcx]
0x18006eff5  mov     rax, [rax+20h]
0x18006eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006effe  mov     rcx, rbx
0x18006f001  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006f006  mov     rcx, [rdi+258h]; struct DWrite::RefString::Data *
0x18006f00d  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006f012  lea     rcx, [rdi+250h]
0x18006f019  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006f01e  lea     rcx, [rdi+228h]; lpCriticalSection
0x18006f025  call    cs:__imp_DeleteCriticalSection
0x18006f02b  mov     rcx, rdi; this
0x18006f02e  mov     rbx, [rsp+28h+arg_0]
0x18006f033  add     rsp, 20h
0x18006f037  pop     rdi
0x18006f038  jmp     ??1ServerCacheContext@@UEAA@XZ; ServerCacheContext::~ServerCacheContext(void)
```
