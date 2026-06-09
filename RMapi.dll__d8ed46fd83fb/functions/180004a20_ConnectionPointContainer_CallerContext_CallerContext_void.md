# ConnectionPointContainer::CallerContext::~CallerContext(void)

- ea: `0x180004a20`
- end: `0x180004acf`
- name: `??1CallerContext@ConnectionPointContainer@@QEAA@XZ`
- size: `175`
- prototype: `void __fastcall(ConnectionPointContainer::CallerContext *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004a10`

## callees

- `0x180004a20`
- `0x180004ad8`
- `0x180004b08`
- `0x18000a4e8`
- `0x18000a534`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a81`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004ac7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004ac7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180004abe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180004abe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180004a77`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180004a77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectionPointContainer::CallerContext::~CallerContext(ConnectionPointContainer::CallerContext *this)
{
  struct _TP_WORK *v2; // rdi
  struct _TP_POOL *v3; // rcx
  __int64 v4; // rcx

  WcmCommon::ThreadPoolWorkQueue::Cancel((ConnectionPointContainer::CallerContext *)((char *)this + 16));
  std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::~deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>((char *)this + 248);
  std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>((char *)this + 208);
  std::deque<std::function<void (void)>>::~deque<std::function<void (void)>>((char *)this + 168);
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 18);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 18), 1);
    CloseThreadpoolWork(v2);
  }
  v3 = (struct _TP_POOL *)*((_QWORD *)this + 17);
  if ( v3 )
    CloseThreadpool(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    *((_QWORD *)this + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180004a20  mov     [rsp+arg_0], rbx
0x180004a25  mov     [rsp+arg_8], rsi
0x180004a2a  push    rdi
0x180004a2b  sub     rsp, 20h
0x180004a2f  mov     rsi, rcx
0x180004a32  add     rcx, 10h; this
0x180004a36  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x180004a3b  lea     rcx, [rsi+0F8h]
0x180004a42  call    ??1?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::~deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(void)
0x180004a47  lea     rcx, [rsi+0D0h]
0x180004a4e  call    ??1?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAA@XZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180004a53  lea     rcx, [rsi+0A8h]
0x180004a5a  call    ??1?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::~deque<std::function<void (void)>>(void)
0x180004a5f  mov     rdi, [rsi+90h]
0x180004a66  test    rdi, rdi
0x180004a69  jnz     short loc_180004AB6
0x180004a6b  mov     rcx, [rsi+88h]; ptpp
0x180004a72  test    rcx, rcx
0x180004a75  jz      short loc_180004A7D
0x180004a77  call    cs:__imp_CloseThreadpool
0x180004a7d  lea     rcx, [rsi+18h]; lpCriticalSection
0x180004a81  call    cs:__imp_DeleteCriticalSection
0x180004a87  nop
0x180004a88  mov     rcx, [rsi+8]
0x180004a8c  test    rcx, rcx
0x180004a8f  jz      short loc_180004AA6
0x180004a91  mov     qword ptr [rsi+8], 0
0x180004a99  mov     rax, [rcx]
0x180004a9c  mov     rax, [rax+10h]
0x180004aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa5  nop
0x180004aa6  mov     rbx, [rsp+28h+arg_0]
0x180004aab  mov     rsi, [rsp+28h+arg_8]
0x180004ab0  add     rsp, 20h
0x180004ab4  pop     rdi
0x180004ab5  retn
0x180004ab6  mov     edx, 1; fCancelPendingCallbacks
0x180004abb  mov     rcx, rdi; pwk
0x180004abe  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180004ac4  mov     rcx, rdi; pwk
0x180004ac7  call    cs:__imp_CloseThreadpoolWork
0x180004acd  jmp     short loc_180004A6B
```
