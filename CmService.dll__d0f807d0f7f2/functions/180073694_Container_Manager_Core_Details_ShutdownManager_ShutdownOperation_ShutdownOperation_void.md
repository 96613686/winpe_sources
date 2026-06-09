# Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)

- ea: `0x180073694`
- end: `0x180073840`
- name: `??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ`
- size: `428`
- prototype: `void __fastcall(Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800733fc`
- `0x1800ba9a0`
- `0x1800bb000`
- `0x1800bb37c`
- `0x1800bbf3c`

## callees

- `0x180004fc4`
- `0x180007dd4`
- `0x180009ba0`
- `0x18004b37c`
- `0x180066c94`
- `0x1800670c8`
- `0x180073694`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800736c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800737d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800736c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800737d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007377e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007377e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073737`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800736ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800736ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073766`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(
        Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *this)
{
  struct _TP_TIMER *v1; // rsi
  DWORD LastError; // ebx
  Container::Manager::Core::Details::InProcClientActivity *v4; // rcx
  Container::Manager::Core::Details::InProcClientActivity *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rsi
  RTL_SRWLOCK *v8; // rbx
  int v9; // ebx
  Container::Manager::Core::Details::InProcClientContainerHandle *v10; // rbx
  struct _TP_TIMER *v11; // rcx
  Container::Manager::Core::Details::InProcClientActivity *v12; // rbx
  Container::Manager::Core::Details::InProcClientContainerHandle *v13; // rbx

  v1 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v1 )
  {
    LastError = GetLastError();
    CloseThreadpoolTimer(v1);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = 0;
  v4 = (Container::Manager::Core::Details::InProcClientActivity *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    Container::Manager::Core::Details::InProcClientActivity::DisableAndWaitForNotificationCallback(v4);
    v5 = (Container::Manager::Core::Details::InProcClientActivity *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v5 )
    {
      Container::Manager::Core::Details::InProcClientActivity::~InProcClientActivity(v5);
      operator delete(v5, (const struct std::nothrow_t *)0x18);
    }
  }
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 32);
    if ( v7 )
    {
      v8 = (RTL_SRWLOCK *)(*(_QWORD *)(v7 + 8) + 16LL);
      AcquireSRWLockExclusive(v8);
      *(_BYTE *)(*(_QWORD *)(v7 + 8) + 112LL) = 1;
      if ( v8 )
        ReleaseSRWLockExclusive(v8);
      v9 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 108LL);
      if ( v9 != GetCurrentThreadId() )
        WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)v7, 1);
    }
    v10 = (Container::Manager::Core::Details::InProcClientContainerHandle *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = 0;
    if ( v10 )
    {
      Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v10);
      operator delete(v10, (const struct std::nothrow_t *)0x28);
    }
  }
  *((_QWORD *)this + 5) = &CmTraceProvider::ContainerShutdownOperation::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy((char *)this + 40);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((char *)this + 40);
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v11 )
    CloseThreadpoolTimer(v11);
  v12 = (Container::Manager::Core::Details::InProcClientActivity *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v12 )
  {
    Container::Manager::Core::Details::InProcClientActivity::~InProcClientActivity(v12);
    operator delete(v12, (const struct std::nothrow_t *)0x18);
  }
  v13 = (Container::Manager::Core::Details::InProcClientContainerHandle *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v13 )
  {
    Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v13);
    operator delete(v13, (const struct std::nothrow_t *)0x28);
  }
}

```

## disassembly

```asm
0x180073694  mov     [rsp+arg_0], rbx
0x180073699  mov     [rsp+arg_8], rsi
0x18007369e  push    rdi
0x18007369f  sub     rsp, 20h
0x1800736a3  mov     rsi, [rcx+18h]
0x1800736a7  mov     rdi, rcx
0x1800736aa  test    rsi, rsi
0x1800736ad  jz      short loc_1800736DA
0x1800736af  call    cs:__imp_GetLastError
0x1800736b6  nop     dword ptr [rax+rax+00h]
0x1800736bb  mov     rcx, rsi; pti
0x1800736be  mov     ebx, eax
0x1800736c0  call    cs:__imp_CloseThreadpoolTimer
0x1800736c7  nop     dword ptr [rax+rax+00h]
0x1800736cc  mov     ecx, ebx; dwErrCode
0x1800736ce  call    cs:__imp_SetLastError
0x1800736d5  nop     dword ptr [rax+rax+00h]
0x1800736da  mov     qword ptr [rdi+18h], 0
0x1800736e2  mov     rcx, [rdi+10h]; this
0x1800736e6  test    rcx, rcx
0x1800736e9  jz      short loc_180073716
0x1800736eb  call    ?DisableAndWaitForNotificationCallback@InProcClientActivity@Details@Core@Manager@Container@@QEAAXXZ; Container::Manager::Core::Details::InProcClientActivity::DisableAndWaitForNotificationCallback(void)
0x1800736f0  mov     rbx, [rdi+10h]
0x1800736f4  mov     qword ptr [rdi+10h], 0
0x1800736fc  test    rbx, rbx
0x1800736ff  jz      short loc_180073716
0x180073701  mov     rcx, rbx; this
0x180073704  call    ??1InProcClientActivity@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientActivity::~InProcClientActivity(void)
0x180073709  mov     edx, 18h; struct std::nothrow_t *
0x18007370e  mov     rcx, rbx; void *
0x180073711  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073716  mov     rsi, [rdi+8]
0x18007371a  test    rsi, rsi
0x18007371d  jz      loc_1800737B0
0x180073723  mov     rsi, [rsi+20h]
0x180073727  test    rsi, rsi
0x18007372a  jz      short loc_18007378A
0x18007372c  mov     rbx, [rsi+8]
0x180073730  add     rbx, 10h
0x180073734  mov     rcx, rbx; SRWLock
0x180073737  call    cs:__imp_AcquireSRWLockExclusive
0x18007373e  nop     dword ptr [rax+rax+00h]
0x180073743  mov     rax, [rsi+8]
0x180073747  mov     byte ptr [rax+70h], 1
0x18007374b  test    rbx, rbx
0x18007374e  jz      short loc_18007375F
0x180073750  mov     rcx, rbx; SRWLock
0x180073753  call    cs:__imp_ReleaseSRWLockExclusive
0x18007375a  nop     dword ptr [rax+rax+00h]
0x18007375f  mov     rax, [rsi+8]
0x180073763  mov     ebx, [rax+6Ch]
0x180073766  call    cs:__imp_GetCurrentThreadId
0x18007376d  nop     dword ptr [rax+rax+00h]
0x180073772  cmp     ebx, eax
0x180073774  jz      short loc_18007378A
0x180073776  mov     rcx, [rsi]; pwk
0x180073779  mov     edx, 1; fCancelPendingCallbacks
0x18007377e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180073785  nop     dword ptr [rax+rax+00h]
0x18007378a  mov     rbx, [rdi+8]
0x18007378e  mov     qword ptr [rdi+8], 0
0x180073796  test    rbx, rbx
0x180073799  jz      short loc_1800737B0
0x18007379b  mov     rcx, rbx; this
0x18007379e  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800737a3  mov     edx, 28h ; '('; struct std::nothrow_t *
0x1800737a8  mov     rcx, rbx; void *
0x1800737ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800737b0  lea     rbx, [rdi+28h]
0x1800737b4  lea     rax, ??_7ContainerShutdownOperation@CmTraceProvider@@6B@; const CmTraceProvider::ContainerShutdownOperation::`vftable'
0x1800737bb  mov     rcx, rbx
0x1800737be  mov     [rbx], rax
0x1800737c1  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800737c6  mov     rcx, rbx
0x1800737c9  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800737ce  mov     rcx, [rdi+18h]; pti
0x1800737d2  test    rcx, rcx
0x1800737d5  jz      short loc_1800737E3
0x1800737d7  call    cs:__imp_CloseThreadpoolTimer
0x1800737de  nop     dword ptr [rax+rax+00h]
0x1800737e3  mov     rbx, [rdi+10h]
0x1800737e7  mov     qword ptr [rdi+10h], 0
0x1800737ef  test    rbx, rbx
0x1800737f2  jz      short loc_180073809
0x1800737f4  mov     rcx, rbx; this
0x1800737f7  call    ??1InProcClientActivity@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientActivity::~InProcClientActivity(void)
0x1800737fc  mov     edx, 18h; struct std::nothrow_t *
0x180073801  mov     rcx, rbx; void *
0x180073804  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073809  mov     rbx, [rdi+8]
0x18007380d  mov     qword ptr [rdi+8], 0
0x180073815  test    rbx, rbx
0x180073818  jz      short loc_18007382F
0x18007381a  mov     rcx, rbx; this
0x18007381d  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x180073822  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180073827  mov     rcx, rbx; void *
0x18007382a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007382f  mov     rbx, [rsp+28h+arg_0]
0x180073834  mov     rsi, [rsp+28h+arg_8]
0x180073839  add     rsp, 20h
0x18007383d  pop     rdi
0x18007383e  retn
```
