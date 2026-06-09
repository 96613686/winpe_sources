# CacheContextImpl::GetElementData(IElementKey const &,CachedElementData *)

- ea: `0x180002740`
- end: `0x1800028ac`
- name: `?GetElementData@CacheContextImpl@@UEAAXAEBVIElementKey@@PEAUCachedElementData@@@Z`
- size: `364`
- prototype: `void __fastcall(CacheContextImpl *__hidden this, const struct IElementKey *, struct CachedElementData *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063950`

## callees

- `0x18000219c`
- `0x1800026c0`
- `0x180002740`
- `0x1800031e8`
- `0x1800033c8`
- `0x18000344c`
- `0x1800034bc`
- `0x1800103f0`
- `0x1800a1558`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002893`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002830`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002796`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002796`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CacheContextImpl::GetElementData(
        CacheContextImpl *this,
        const struct IElementKey *a2,
        struct CachedElementData *a3)
{
  const struct LockHolder *v6; // rdx
  struct IElementConstructionTask *Task; // rax
  const struct LockHolder *v8; // rdx
  struct IElementConstructionTask *v9; // rsi
  struct IElementConstructionTask *v10; // rax
  struct IElementConstructionTask *v11; // rdi
  __int64 v12; // rcx
  int v13; // eax
  HANDLE EventW; // rax

  if ( !(*(unsigned __int8 (__fastcall **)(CacheContextImpl *))(*(_QWORD *)this + 56LL))(this) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
    if ( (*(unsigned __int8 (__fastcall **)(CacheContextImpl *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
           this,
           a2,
           a3) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
      v12 = 0;
    }
    else
    {
      Task = ElementTaskList::FindTask((CacheContextImpl *)((char *)this + 288), v6, a2);
      v9 = Task;
      if ( Task )
      {
        v11 = Task;
        _InterlockedIncrement((volatile signed __int32 *)Task + 2);
        ReleaseReference<IElementConstructionTask>(0);
        if ( !*((_QWORD *)v9 + 3) && *((_DWORD *)v9 + 8) == 1 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)v9 + 3) = EventW;
          if ( !EventW )
            OSException::ThrowLastError();
        }
      }
      else
      {
        v10 = ElementTaskList::AddTask((CacheContextImpl *)((char *)this + 288), v8, this, a2);
        v11 = v10;
        if ( v10 )
          _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
        ReleaseReference<IElementConstructionTask>(0);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
      if ( v9 )
      {
        v13 = IElementConstructionTask::WaitForCompletion(v9);
        LogAndThrowIfFailed<OSException>(v13);
      }
      else
      {
        ElementTaskList::ExecuteTask((CacheContextImpl *)((char *)this + 288), this, v11, 1);
      }
      CachedElementData::operator=(a3, (char *)v11 + 40);
      v12 = (__int64)v11;
    }
    ReleaseReference<IElementConstructionTask>(v12);
  }
}

```

## disassembly

```asm
0x180002740  mov     [rsp+arg_8], rbx
0x180002745  mov     [rsp+arg_10], rbp
0x18000274a  push    rsi
0x18000274b  push    rdi
0x18000274c  push    r14
0x18000274e  sub     rsp, 20h
0x180002752  mov     rbp, r8
0x180002755  mov     rdi, rdx
0x180002758  mov     r14, rcx
0x18000275b  mov     rax, [rcx]
0x18000275e  mov     rax, [rax+38h]
0x180002762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002767  test    al, al
0x180002769  jz      short loc_18000277E
0x18000276b  mov     rbx, [rsp+38h+arg_8]
0x180002770  mov     rbp, [rsp+38h+arg_10]
0x180002775  add     rsp, 20h
0x180002779  pop     r14
0x18000277b  pop     rdi
0x18000277c  pop     rsi
0x18000277d  retn
0x18000277e  lea     rbx, [r14+120h]
0x180002785  mov     [rsp+38h+arg_0], 0
0x18000278e  mov     [rsp+38h+arg_18], rbx
0x180002793  mov     rcx, rbx; lpCriticalSection
0x180002796  call    cs:__imp_EnterCriticalSection
0x18000279c  nop
0x18000279d  mov     rax, [r14]
0x1800027a0  mov     r8, rbp
0x1800027a3  mov     rdx, rdi
0x1800027a6  mov     rcx, r14
0x1800027a9  mov     rax, [rax+38h]
0x1800027ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b2  test    al, al
0x1800027b4  jnz     short loc_18000282D
0x1800027b6  mov     r8, rdi; struct IElementKey *
0x1800027b9  mov     rcx, rbx; this
0x1800027bc  call    ?FindTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@AEBVIElementKey@@@Z; ElementTaskList::FindTask(LockHolder const &,IElementKey const &)
0x1800027c1  mov     rsi, rax
0x1800027c4  test    rax, rax
0x1800027c7  jnz     loc_18000285F
0x1800027cd  mov     r9, rdi; struct IElementKey *
0x1800027d0  mov     r8, r14; struct IBaseCacheContext *
0x1800027d3  mov     rcx, rbx; this
0x1800027d6  call    ?AddTask@ElementTaskList@@AEAAPEAVIElementConstructionTask@@AEBVLockHolder@@PEAUIBaseCacheContext@@AEBVIElementKey@@@Z; ElementTaskList::AddTask(LockHolder const &,IBaseCacheContext *,IElementKey const &)
0x1800027db  mov     rdi, rax
0x1800027de  mov     [rsp+38h+arg_0], rax
0x1800027e3  test    rax, rax
0x1800027e6  jz      short loc_1800027EC
0x1800027e8  lock inc dword ptr [rax+8]
0x1800027ec  xor     ecx, ecx
0x1800027ee  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x1800027f3  nop
0x1800027f4  mov     rcx, rbx; lpCriticalSection
0x1800027f7  call    cs:__imp_LeaveCriticalSection
0x1800027fd  test    rsi, rsi
0x180002800  jnz     short loc_18000283B
0x180002802  mov     r9b, 1; bool
0x180002805  mov     r8, rdi; struct IElementConstructionTask *
0x180002808  mov     rdx, r14; struct IBaseCacheContext *
0x18000280b  mov     rcx, rbx; this
0x18000280e  call    ?ExecuteTask@ElementTaskList@@QEAAJPEAUIBaseCacheContext@@PEAVIElementConstructionTask@@_N@Z; ElementTaskList::ExecuteTask(IBaseCacheContext *,IElementConstructionTask *,bool)
0x180002813  lea     rdx, [rdi+28h]
0x180002817  mov     rcx, rbp
0x18000281a  call    ??4CachedElementData@@QEAAAEAU0@AEBU0@@Z; CachedElementData::operator=(CachedElementData const &)
0x18000281f  nop
0x180002820  mov     rcx, rdi
0x180002823  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002828  jmp     loc_18000276B
0x18000282d  mov     rcx, rbx; lpCriticalSection
0x180002830  call    cs:__imp_LeaveCriticalSection
0x180002836  nop
0x180002837  xor     ecx, ecx
0x180002839  jmp     short loc_180002823
0x18000283b  mov     rbx, 4445746567h
0x180002845  mov     rcx, rsi; this
0x180002848  call    ?WaitForCompletion@IElementConstructionTask@@AEAAJXZ; IElementConstructionTask::WaitForCompletion(void)
0x18000284d  mov     ecx, eax; int
0x18000284f  mov     r8d, 0AAh
0x180002855  mov     rdx, rbx
0x180002858  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x18000285d  jmp     short loc_180002813
0x18000285f  mov     rdi, rsi
0x180002862  mov     [rsp+38h+arg_0], rsi
0x180002867  lock inc dword ptr [rax+8]
0x18000286b  xor     ecx, ecx
0x18000286d  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180002872  cmp     qword ptr [rsi+18h], 0
0x180002877  jnz     loc_1800027F4
0x18000287d  cmp     dword ptr [rsi+20h], 1
0x180002881  jnz     loc_1800027F4
0x180002887  xor     r9d, r9d; lpName
0x18000288a  xor     r8d, r8d; bInitialState
0x18000288d  lea     edx, [r9+1]; bManualReset
0x180002891  xor     ecx, ecx; lpEventAttributes
0x180002893  call    cs:__imp_CreateEventW
0x180002899  mov     [rsi+18h], rax
0x18000289d  test    rax, rax
0x1800028a0  jnz     loc_1800027F4
0x1800028a6  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
