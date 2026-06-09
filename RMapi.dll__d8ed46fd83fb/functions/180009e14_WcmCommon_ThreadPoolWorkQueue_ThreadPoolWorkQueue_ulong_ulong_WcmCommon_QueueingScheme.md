# WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)

- ea: `0x180009e14`
- end: `0x180009ee2`
- name: `??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009db0`
- `0x18001b69c`

## callees

- `0x180005300`
- `0x180005390`
- `0x180005bb0`
- `0x180006e88`
- `0x180009e14`
- `0x180009ee8`
- `0x180009f20`
- `0x180009f44`
- `0x180009f78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009e3b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009e3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _TP_WORK **__fastcall WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(struct _TP_WORK **a1)
{
  struct _TP_WORK **v2; // rax
  PTP_WORK v4; // [rsp+20h] [rbp-28h] BYREF

  *(_DWORD *)a1 = 1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 1), 0x1F4u, 0);
  WcmCommon::details::TPEnvironment::TPEnvironment((WcmCommon::details::TPEnvironment *)(a1 + 6));
  a1[16] = 0;
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 17);
  std::atomic<unsigned long>::atomic<unsigned long>(a1 + 18);
  v4 = (PTP_WORK)(a1 + 19);
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(a1 + 19);
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(a1 + 24);
  std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(a1 + 29);
  *((_BYTE *)a1 + 272) = 0;
  v2 = WcmCommon::details::TPEnvironment::create_tp(
         (__int64)(a1 + 6),
         &v4,
         (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))WcmCommon::ThreadPoolWorkQueue::WorkCallback,
         a1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
    a1 + 16,
    v2);
  if ( v4 )
    wil::details::DestroyThreadPoolWork<0>::Destroy(v4);
  return a1;
}

```

## disassembly

```asm
0x180009e14  mov     [rsp+arg_8], rbx
0x180009e19  mov     [rsp+arg_0], rcx
0x180009e1e  push    rsi
0x180009e1f  push    rdi
0x180009e20  push    r14
0x180009e22  sub     rsp, 30h
0x180009e26  mov     r14, rcx
0x180009e29  mov     dword ptr [rcx], 1
0x180009e2f  add     rcx, 8; lpCriticalSection
0x180009e33  xor     r8d, r8d; Flags
0x180009e36  mov     edx, 1F4h; dwSpinCount
0x180009e3b  call    cs:__imp_InitializeCriticalSectionEx
0x180009e41  nop
0x180009e42  lea     rcx, [r14+30h]; this
0x180009e46  call    ??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z; WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)
0x180009e4b  nop
0x180009e4c  lea     rdi, [r14+80h]
0x180009e53  mov     qword ptr [rdi], 0
0x180009e5a  lea     rcx, [r14+88h]
0x180009e61  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180009e66  lea     rcx, [r14+90h]
0x180009e6d  call    ??0?$atomic@K@std@@QEAA@K@Z; std::atomic<ulong>::atomic<ulong>(ulong)
0x180009e72  lea     rbx, [r14+98h]
0x180009e79  mov     [rsp+48h+var_28], rbx
0x180009e7e  mov     rcx, rbx
0x180009e81  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x180009e86  nop
0x180009e87  lea     rcx, [rbx+28h]
0x180009e8b  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x180009e90  nop
0x180009e91  lea     rcx, [rbx+50h]
0x180009e95  call    ??0?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(void)
0x180009e9a  mov     byte ptr [rbx+78h], 0
0x180009e9e  mov     r9, r14
0x180009ea1  lea     r8, ?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x180009ea8  lea     rdx, [rsp+48h+var_28]
0x180009ead  lea     rcx, [r14+30h]
0x180009eb1  call    ?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x180009eb6  mov     rdx, rax
0x180009eb9  mov     rcx, rdi
0x180009ebc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> &&)
0x180009ec1  mov     rcx, [rsp+48h+var_28]
0x180009ec6  test    rcx, rcx
0x180009ec9  jz      short loc_180009ED1
0x180009ecb  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x180009ed0  nop
0x180009ed1  mov     rax, r14
0x180009ed4  mov     rbx, [rsp+48h+arg_8]
0x180009ed9  add     rsp, 30h
0x180009edd  pop     r14
0x180009edf  pop     rdi
0x180009ee0  pop     rsi
0x180009ee1  retn
```
