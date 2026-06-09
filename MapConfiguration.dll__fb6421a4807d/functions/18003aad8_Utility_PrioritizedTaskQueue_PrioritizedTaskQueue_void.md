# Utility::PrioritizedTaskQueue::~PrioritizedTaskQueue(void)

- ea: `0x18003aad8`
- end: `0x18003ab5f`
- name: `??1PrioritizedTaskQueue@Utility@@UEAA@XZ`
- size: `135`
- prototype: `void __fastcall(Utility::PrioritizedTaskQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18003ab70`

## callees

- `0x18000b938`
- `0x18001d758`
- `0x180029e1c`
- `0x18003aad8`
- `0x18003ae34`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ab46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ab46`

## pseudocode

```c
void __fastcall Utility::PrioritizedTaskQueue::~PrioritizedTaskQueue(Utility::PrioritizedTaskQueue *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &Utility::PrioritizedTaskQueue::`vftable';
  Utility::PrioritizedTaskQueue::cancelAllTasks(this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>(v2, *((_QWORD *)this + 9));
    std::_Deallocate<16>(*((void **)this + 8), (*((_QWORD *)this + 10) - *((_QWORD *)this + 8)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  Pal::TaskQueue::~TaskQueue((Utility::PrioritizedTaskQueue *)((char *)this + 16));
}

```

## disassembly

```asm
0x18003aad8  mov     [rsp+arg_0], rbx
0x18003aadd  push    rdi
0x18003aade  sub     rsp, 20h
0x18003aae2  mov     rbx, rcx
0x18003aae5  lea     rax, ??_7PrioritizedTaskQueue@Utility@@6B@; const Utility::PrioritizedTaskQueue::`vftable'
0x18003aaec  mov     [rcx], rax
0x18003aaef  call    ?cancelAllTasks@PrioritizedTaskQueue@Utility@@QEAAXXZ; Utility::PrioritizedTaskQueue::cancelAllTasks(void)
0x18003aaf4  mov     rcx, [rbx+10h]
0x18003aaf8  mov     rax, [rcx]
0x18003aafb  mov     rax, [rax+18h]
0x18003aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab04  mov     rcx, [rbx+40h]
0x18003ab08  test    rcx, rcx
0x18003ab0b  jz      short loc_18003AB42
0x18003ab0d  mov     rdx, [rbx+48h]
0x18003ab11  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPrioritizableTask@Utility@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>(std::shared_ptr<Utility::PrioritizableTask> *,std::shared_ptr<Utility::PrioritizableTask> * const,std::allocator<std::shared_ptr<Utility::PrioritizableTask>> &)
0x18003ab16  mov     rcx, [rbx+40h]
0x18003ab1a  mov     rdx, [rbx+50h]
0x18003ab1e  sub     rdx, rcx
0x18003ab21  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18003ab25  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003ab2a  mov     qword ptr [rbx+40h], 0
0x18003ab32  mov     qword ptr [rbx+48h], 0
0x18003ab3a  mov     qword ptr [rbx+50h], 0
0x18003ab42  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003ab46  call    cs:__imp_DeleteCriticalSection
0x18003ab4c  lea     rcx, [rbx+10h]; this
0x18003ab50  mov     rbx, [rsp+28h+arg_0]
0x18003ab55  add     rsp, 20h
0x18003ab59  pop     rdi
0x18003ab5a  jmp     ??1TaskQueue@Pal@@QEAA@XZ; Pal::TaskQueue::~TaskQueue(void)
```
