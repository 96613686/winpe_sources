# TimeUpdate::TimeUpdate(void)

- ea: `0x180004fd0`
- end: `0x18000519a`
- name: `??0TimeUpdate@@QEAA@XZ`
- size: `458`
- prototype: `TimeUpdate *__fastcall(TimeUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008d7c`

## callees

- `0x18000365c`
- `0x180004d08`
- `0x180004d3c`
- `0x180004d60`
- `0x180004fd0`
- `0x1800051a0`
- `0x18000b5a4`
- `0x18000bbf0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005018`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005160`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005018`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005160`

## pseudocode

```c
TimeUpdate *__fastcall TimeUpdate::TimeUpdate(TimeUpdate *this)
{
  __int64 v2; // r8
  __int64 v3; // r8

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkListManagerEvents>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkListManagerEvents>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INetworkListManagerEvents>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &TimeUpdate::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0);
  std::atomic<bool>::atomic<bool>((char *)this + 56);
  *((_DWORD *)this + 15) = 0;
  WNFNotificationDispatcher::WNFNotificationDispatcher((TimeUpdate *)((char *)this + 64));
  WNFNotificationDispatcher::WNFNotificationDispatcher((TimeUpdate *)((char *)this + 144));
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_BYTE *)this + 240) = 0;
  std::atomic<bool>::atomic<bool>((char *)this + 241);
  *((_QWORD *)this + 31) = 0;
  WnfSubscription::WnfSubscription(
    (char *)this + 256,
    &WNF_CELL_NITZ_INFO,
    0,
    lambda_aea6636b59e6efc99a34558288aee7a9_::_lambda_invoker_cdecl__void_const___unsigned_long_,
    32);
  WnfSubscription::WnfSubscription(
    (char *)this + 312,
    &WNF_PROV_TURN_COMPLETE,
    v2,
    lambda_3c5bb343e8f3f2e45d0a2f3c793d09fb_::_lambda_invoker_cdecl__void_const___unsigned_long_,
    4,
    -1);
  WnfSubscription::WnfSubscription(
    (char *)this + 368,
    &WNF_TZ_NETWORK_TIME_SYNC_TRIGGER,
    v3,
    lambda_3c5bb343e8f3f2e45d0a2f3c793d09fb_::_lambda_invoker_cdecl__void_const___unsigned_long_,
    4);
  WnfSubscription::WnfSubscription(
    (char *)this + 424,
    &WNF_TZ_AUTOTIMEUPDATE_STATE_CHANGED,
    1,
    lambda_99ff526e6fabc8093bb39e8947287108_::_lambda_invoker_cdecl_,
    4);
  *((_OWORD *)this + 30) = 0;
  memset_0((char *)this + 496, 0, 0x50u);
  std::atomic<unsigned long>::atomic<unsigned long>((char *)this + 576);
  *((_QWORD *)this + 73) = 0;
  *((_DWORD *)this + 148) = 0;
  *((_BYTE *)this + 596) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 15, 0, 0);
  *((_QWORD *)this + 80) = 0;
  *((_DWORD *)this + 124) = 2;
  *((_QWORD *)this + 64) = this;
  *((_QWORD *)this + 63) = TimeUpdate::NlmStateCallback;
  return this;
}

```

## disassembly

```asm
0x180004fd0  mov     [rsp+arg_0], rbx
0x180004fd5  push    rdi
0x180004fd6  sub     rsp, 30h
0x180004fda  mov     rdi, rcx
0x180004fdd  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINetworkListManagerEvents@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkListManagerEvents>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkListManagerEvents>(void)
0x180004fe2  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINetworkListManagerEvents@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INetworkListManagerEvents>::`vftable'
0x180004fe9  mov     [rdi], rcx
0x180004fec  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004ff3  test    rcx, rcx
0x180004ff6  jz      short loc_180005005
0x180004ff8  mov     rax, [rcx]
0x180004ffb  mov     rax, [rax+8]
0x180004fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005004  nop
0x180005005  lea     rax, ??_7TimeUpdate@@6B@; const TimeUpdate::`vftable'
0x18000500c  mov     [rdi], rax
0x18000500f  lea     rcx, [rdi+10h]; lpCriticalSection
0x180005013  xor     r8d, r8d; Flags
0x180005016  xor     edx, edx; dwSpinCount
0x180005018  call    cs:__imp_InitializeCriticalSectionEx
0x18000501e  lea     rcx, [rdi+38h]
0x180005022  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x180005027  mov     dword ptr [rdi+3Ch], 0
0x18000502e  lea     rcx, [rdi+40h]; this
0x180005032  call    ??0WNFNotificationDispatcher@@QEAA@XZ; WNFNotificationDispatcher::WNFNotificationDispatcher(void)
0x180005037  lea     rcx, [rdi+90h]; this
0x18000503e  call    ??0WNFNotificationDispatcher@@QEAA@XZ; WNFNotificationDispatcher::WNFNotificationDispatcher(void)
0x180005043  mov     qword ptr [rdi+0E0h], 0
0x18000504e  mov     qword ptr [rdi+0E8h], 0
0x180005059  mov     byte ptr [rdi+0F0h], 0
0x180005060  lea     rcx, [rdi+0F1h]
0x180005067  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x18000506c  mov     qword ptr [rdi+0F8h], 0
0x180005077  lea     rbx, [rdi+100h]
0x18000507e  mov     [rsp+38h+var_18], 20h ; ' '
0x180005086  lea     r9, _lambda_aea6636b59e6efc99a34558288aee7a9____lambda_invoker_cdecl__void_const___unsigned_long_
0x18000508d  xor     r8d, r8d
0x180005090  lea     rdx, WNF_CELL_NITZ_INFO
0x180005097  mov     rcx, rbx
0x18000509a  call    ??0WnfSubscription@@QEAA@AEBU_WNF_STATE_NAME@@W4WnfSubscriptionType@@P6A?AW4ActionType@@PEBXK@ZK@Z; WnfSubscription::WnfSubscription(_WNF_STATE_NAME const &,WnfSubscriptionType,ActionType (*)(void const *,ulong),ulong)
0x18000509f  lea     rcx, [rbx+38h]
0x1800050a3  mov     [rsp+38h+var_10], 0FFFFFFFFh
0x1800050ab  mov     [rsp+38h+var_18], 4
0x1800050b3  lea     r9, _lambda_3c5bb343e8f3f2e45d0a2f3c793d09fb____lambda_invoker_cdecl__void_const___unsigned_long_
0x1800050ba  lea     rdx, WNF_PROV_TURN_COMPLETE
0x1800050c1  call    ??0WnfSubscription@@QEAA@AEBU_WNF_STATE_NAME@@W4WnfSubscriptionType@@P6A?AW4ActionType@@PEBXK@ZKK@Z; WnfSubscription::WnfSubscription(_WNF_STATE_NAME const &,WnfSubscriptionType,ActionType (*)(void const *,ulong),ulong,ulong)
0x1800050c6  lea     rcx, [rbx+70h]
0x1800050ca  mov     [rsp+38h+var_18], 4
0x1800050d2  lea     r9, _lambda_3c5bb343e8f3f2e45d0a2f3c793d09fb____lambda_invoker_cdecl__void_const___unsigned_long_
0x1800050d9  lea     rdx, WNF_TZ_NETWORK_TIME_SYNC_TRIGGER
0x1800050e0  call    ??0WnfSubscription@@QEAA@AEBU_WNF_STATE_NAME@@W4WnfSubscriptionType@@P6A?AW4ActionType@@PEBXK@ZK@Z; WnfSubscription::WnfSubscription(_WNF_STATE_NAME const &,WnfSubscriptionType,ActionType (*)(void const *,ulong),ulong)
0x1800050e5  lea     rcx, [rbx+0A8h]
0x1800050ec  mov     [rsp+38h+var_18], 4
0x1800050f4  lea     r9, _lambda_99ff526e6fabc8093bb39e8947287108____lambda_invoker_cdecl_
0x1800050fb  mov     r8d, 1
0x180005101  lea     rdx, WNF_TZ_AUTOTIMEUPDATE_STATE_CHANGED
0x180005108  call    ??0WnfSubscription@@QEAA@AEBU_WNF_STATE_NAME@@W4WnfSubscriptionType@@P6A?AW4ActionType@@PEBXK@ZK@Z; WnfSubscription::WnfSubscription(_WNF_STATE_NAME const &,WnfSubscriptionType,ActionType (*)(void const *,ulong),ulong)
0x18000510d  xorps   xmm0, xmm0
0x180005110  movups  xmmword ptr [rdi+1E0h], xmm0
0x180005117  lea     rbx, [rdi+1F0h]
0x18000511e  xor     edx, edx; Val
0x180005120  lea     r8d, [rdx+50h]; Size
0x180005124  mov     rcx, rbx; void *
0x180005127  call    memset_0
0x18000512c  lea     rcx, [rdi+240h]
0x180005133  call    ??0?$atomic@K@std@@QEAA@K@Z; std::atomic<ulong>::atomic<ulong>(ulong)
0x180005138  mov     qword ptr [rdi+248h], 0
0x180005143  mov     dword ptr [rdi+250h], 0
0x18000514d  mov     byte ptr [rdi+254h], 0
0x180005154  lea     rcx, [rdi+258h]; lpCriticalSection
0x18000515b  xor     r8d, r8d; Flags
0x18000515e  xor     edx, edx; dwSpinCount
0x180005160  call    cs:__imp_InitializeCriticalSectionEx
0x180005166  mov     qword ptr [rdi+280h], 0
0x180005171  mov     dword ptr [rbx], 2
0x180005177  mov     [rdi+200h], rdi
0x18000517e  lea     rax, ?NlmStateCallback@TimeUpdate@@CAXPEAX@Z; TimeUpdate::NlmStateCallback(void *)
0x180005185  mov     [rdi+1F8h], rax
0x18000518c  mov     rax, rdi
0x18000518f  mov     rbx, [rsp+38h+arg_0]
0x180005194  add     rsp, 30h
0x180005198  pop     rdi
0x180005199  retn
```
