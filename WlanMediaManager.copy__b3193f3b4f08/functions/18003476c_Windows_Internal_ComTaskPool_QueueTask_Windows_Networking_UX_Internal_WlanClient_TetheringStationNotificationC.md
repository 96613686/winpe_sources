# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1___

- ea: `0x18003476c`
- end: `0x1800347ff`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1___`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034e90`

## callees

- `0x1800043bc`
- `0x180011ccc`
- `0x1800346fc`
- `0x18003476c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347b7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800347d5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800347d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1___::CTaskWrapper__Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1_____Windows::Networking::UX::Internal::WlanClient::_TetheringStationNotificationCommon_::_2_::_lambda_1___(
           v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::StateDiscovery::EnterState_::_34_::_lambda_1____::_3_::_lambda_1_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::StateDiscovery::EnterState_::_34_::_lambda_1____::_3_::_lambda_1_____(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x18003476c  mov     [rsp+arg_0], rbx
0x180034771  push    rdi
0x180034772  sub     rsp, 30h
0x180034776  mov     rdi, rdx
0x180034779  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034780  mov     ecx, 30h ; '0'; unsigned __int64
0x180034785  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003478a  mov     [rsp+38h+arg_10], rax
0x18003478f  xor     ebx, ebx
0x180034791  test    rax, rax
0x180034794  jz      short loc_1800347AD
0x180034796  mov     rdx, rdi
0x180034799  mov     rcx, rax
0x18003479c  call    Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__WlanClient___TetheringStationNotificationCommon____2____lambda_1_____CTaskWrapper__Windows__Networking__UX__Internal__WlanClient___TetheringStationNotificationCommon____2____lambda_1_____Windows__Networking__UX__Internal__WlanClient___TetheringStationNotificationCommon____2____lambda_1___
0x1800347a1  mov     rbx, rax
0x1800347a4  mov     [rsp+38h+arg_10], 0
0x1800347ad  lea     rcx, [rsp+38h+arg_10]
0x1800347b2  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__StateDiscovery__EnterState____34____lambda_1_______3____lambda_1________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__StateDiscovery__EnterState____34____lambda_1_______3____lambda_1_____
0x1800347b7  call    cs:__imp_GetCurrentThreadId
0x1800347bd  mov     [rsp+38h+var_10], 0
0x1800347c6  mov     [rsp+38h+var_18], rbx
0x1800347cb  xor     r9d, r9d
0x1800347ce  mov     r8d, eax
0x1800347d1  xor     edx, edx
0x1800347d3  xor     ecx, ecx
0x1800347d5  call    cs:__imp_SHTaskPoolQueueTask
0x1800347db  mov     edi, eax
0x1800347dd  test    rbx, rbx
0x1800347e0  jz      short loc_1800347F2
0x1800347e2  mov     rdx, [rbx]
0x1800347e5  mov     rcx, rbx
0x1800347e8  mov     rax, [rdx+10h]
0x1800347ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347f1  nop
0x1800347f2  mov     eax, edi
0x1800347f4  mov     rbx, [rsp+38h+arg_0]
0x1800347f9  add     rsp, 30h
0x1800347fd  pop     rdi
0x1800347fe  retn
```
