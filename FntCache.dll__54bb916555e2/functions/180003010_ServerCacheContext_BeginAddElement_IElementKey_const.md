# ServerCacheContext::BeginAddElement(IElementKey const &)

- ea: `0x180003010`
- end: `0x1800031e2`
- name: `?BeginAddElement@ServerCacheContext@@UEAAJAEBVIElementKey@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(ServerCacheContext *__hidden this, const struct IElementKey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180002260`

## callees

- `0x180003010`
- `0x1800031e8`
- `0x18000321c`
- `0x180003374`
- `0x180068e24`
- `0x1800983d8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000312c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003140`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000312c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003140`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003182`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000305c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000305c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003112`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003136`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003136`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ServerCacheContext::BeginAddElement(ServerCacheContext *this, const struct IElementKey *a2)
{
  struct IElementConstructionTask *v4; // rbx
  __int64 v5; // r12
  struct IElementConstructionTask **AsynchronousTask; // rax
  void *v8; // rax
  bool v9; // r8
  struct IElementConstructionTask *v10; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h]

  if ( (*(unsigned __int8 (__fastcall **)(const struct IElementKey *))(*(_QWORD *)a2 + 16LL))(a2) )
    return 1;
  v4 = 0;
  v10 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 12);
  if ( *((_BYTE *)this + 536) )
    goto LABEL_12;
  v5 = *((_QWORD *)this + 44);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5) )
    goto LABEL_4;
  v8 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
  if ( !Event::Wait(v8, 0, v9) )
  {
LABEL_12:
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 12);
    ReleaseReference<IElementConstructionTask>(0);
    return 1;
  }
  _mm_lfence();
LABEL_4:
  if ( !*((_QWORD *)this + 66) )
    ThreadpoolWork::Initialize(
      (ServerCacheContext *)((char *)this + 528),
      (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))ServerCacheContext::TaskExecutionProc,
      this);
  if ( (*(unsigned __int8 (__fastcall **)(ServerCacheContext *, const struct IElementKey *, _QWORD))(*(_QWORD *)this + 56LL))(
         this,
         a2,
         0) )
  {
    goto LABEL_12;
  }
  AsynchronousTask = (struct IElementConstructionTask **)ElementTaskList::CreateAsynchronousTask((ServerCacheContext *)((char *)this + 288));
  if ( AsynchronousTask != &v10 )
  {
    v4 = *AsynchronousTask;
    *AsynchronousTask = 0;
    v10 = v4;
    ReleaseReference<IElementConstructionTask>(0);
  }
  ReleaseReference<IElementConstructionTask>(v11);
  if ( v4 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    ElementTaskQueue::PushBack((ServerCacheContext *)((char *)this + 416), v4);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    SubmitThreadpoolWork(*((PTP_WORK *)this + 66));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 12);
  ReleaseReference<IElementConstructionTask>((__int64)v4);
  return 1;
}

```

## disassembly

```asm
0x180003010  mov     [rsp+arg_18], rbx
0x180003015  mov     [rsp+arg_0], rcx
0x18000301a  push    rsi
0x18000301b  push    rdi
0x18000301c  push    r12
0x18000301e  push    r14
0x180003020  push    r15
0x180003022  sub     rsp, 30h
0x180003026  mov     r15, rdx
0x180003029  mov     rdi, rcx
0x18000302c  mov     rax, [rdx]
0x18000302f  mov     rcx, rdx
0x180003032  mov     rax, [rax+10h]
0x180003036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303b  test    al, al
0x18000303d  jnz     loc_180003178
0x180003043  xor     ebx, ebx
0x180003045  mov     [rsp+58h+var_38], rbx
0x18000304a  lea     esi, [rbx+1]
0x18000304d  lea     r14, [rdi+1E0h]
0x180003054  mov     [rsp+58h+arg_10], r14
0x180003059  mov     rcx, r14; lpCriticalSection
0x18000305c  call    cs:__imp_EnterCriticalSection
0x180003062  nop
0x180003063  cmp     [rdi+218h], bl
0x180003069  jnz     loc_18000317F
0x18000306f  mov     r12, [rdi+160h]
0x180003076  mov     rax, [r12]
0x18000307a  mov     rcx, r12
0x18000307d  mov     rax, [rax+58h]
0x180003081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003086  test    al, al
0x180003088  jz      loc_180003194
0x18000308e  lea     r12, [rdi+210h]
0x180003095  cmp     qword ptr [r12], 0
0x18000309a  jz      loc_1800031BC
0x1800030a0  mov     rax, [rdi]
0x1800030a3  xor     r8d, r8d
0x1800030a6  mov     rdx, r15
0x1800030a9  mov     rcx, rdi
0x1800030ac  mov     rax, [rax+38h]
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  test    al, al
0x1800030b7  jnz     loc_180003163
0x1800030bd  lea     rcx, [rdi+120h]; this
0x1800030c4  mov     r9, r15
0x1800030c7  mov     r8, rdi
0x1800030ca  lea     rdx, [rsp+58h+arg_8]
0x1800030cf  call    ?CreateAsynchronousTask@ElementTaskList@@QEAA?AV?$IntrusivePtr@VIElementConstructionTask@@@@PEAUIBaseCacheContext@@AEBVIElementKey@@@Z; ElementTaskList::CreateAsynchronousTask(IBaseCacheContext *,IElementKey const &)
0x1800030d4  lea     rcx, [rsp+58h+var_38]
0x1800030d9  cmp     rax, rcx
0x1800030dc  jz      short loc_1800030F4
0x1800030de  mov     rbx, [rax]
0x1800030e1  mov     qword ptr [rax], 0
0x1800030e8  mov     [rsp+58h+var_38], rbx
0x1800030ed  xor     ecx, ecx
0x1800030ef  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x1800030f4  mov     rcx, [rsp+58h+arg_8]
0x1800030f9  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x1800030fe  test    rbx, rbx
0x180003101  jz      short loc_18000313D
0x180003103  lea     r15, [rdi+178h]
0x18000310a  mov     [rsp+58h+arg_8], r15
0x18000310f  mov     rcx, r15; lpCriticalSection
0x180003112  call    cs:__imp_EnterCriticalSection
0x180003118  nop
0x180003119  lea     rcx, [rdi+1A0h]; this
0x180003120  mov     rdx, rbx; struct IElementConstructionTask *
0x180003123  call    ?PushBack@ElementTaskQueue@@QEAAXPEAVIElementConstructionTask@@@Z; ElementTaskQueue::PushBack(IElementConstructionTask *)
0x180003128  nop
0x180003129  mov     rcx, r15; lpCriticalSection
0x18000312c  call    cs:__imp_LeaveCriticalSection
0x180003132  mov     rcx, [r12]; pwk
0x180003136  call    cs:__imp_SubmitThreadpoolWork
0x18000313c  nop
0x18000313d  mov     rcx, r14; lpCriticalSection
0x180003140  call    cs:__imp_LeaveCriticalSection
0x180003146  nop
0x180003147  mov     rcx, rbx
0x18000314a  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x18000314f  mov     eax, esi
0x180003151  mov     rbx, [rsp+58h+arg_18]
0x180003156  add     rsp, 30h
0x18000315a  pop     r15
0x18000315c  pop     r14
0x18000315e  pop     r12
0x180003160  pop     rdi
0x180003161  pop     rsi
0x180003162  retn
0x180003163  mov     rcx, r14; lpCriticalSection
0x180003166  call    cs:__imp_LeaveCriticalSection
0x18000316c  nop
0x18000316d  xor     ecx, ecx
0x18000316f  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180003174  mov     eax, esi
0x180003176  jmp     short loc_180003151
0x180003178  mov     eax, 1
0x18000317d  jmp     short loc_180003151
0x18000317f  mov     rcx, r14; lpCriticalSection
0x180003182  call    cs:__imp_LeaveCriticalSection
0x180003188  nop
0x180003189  xor     ecx, ecx
0x18000318b  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180003190  mov     eax, esi
0x180003192  jmp     short loc_180003151
0x180003194  mov     rax, [r12]
0x180003198  mov     rcx, r12
0x18000319b  mov     rax, [rax+60h]
0x18000319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a4  mov     rcx, rax; hHandle
0x1800031a7  xor     edx, edx; dwMilliseconds
0x1800031a9  call    ?Wait@Event@@SA_NPEAXI_N@Z; Event::Wait(void *,uint,bool)
0x1800031ae  test    al, al
0x1800031b0  jz      short loc_18000317F
0x1800031b2  nop
0x1800031b3  lfence
0x1800031b6  nop
0x1800031b7  jmp     loc_18000308E
0x1800031bc  mov     r8, rdi; void *
0x1800031bf  lea     rdx, ?TaskExecutionProc@ServerCacheContext@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x1800031c6  mov     rcx, r12; this
0x1800031c9  call    ?Initialize@ThreadpoolWork@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; ThreadpoolWork::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800031ce  jmp     loc_1800030A0
0x1800031d3  mov     rbx, [rsp+58h+var_38]
0x1800031d8  mov     esi, dword ptr [rsp+58h+arg_8]
0x1800031dc  jmp     loc_180003147
```
