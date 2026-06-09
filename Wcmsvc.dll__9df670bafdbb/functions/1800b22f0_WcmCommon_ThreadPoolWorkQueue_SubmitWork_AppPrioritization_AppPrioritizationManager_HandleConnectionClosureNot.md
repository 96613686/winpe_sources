# WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionClosureNotification_::_3_::_lambda_1___

- ea: `0x1800b22f0`
- end: `0x1800b2380`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionClosureNotification_::_3_::_lambda_1___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b4834`

## callees

- `0x180027630`
- `0x1800b22f0`
- `0x1800b2820`
- `0x1800b28bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b232f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b235a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b232f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b235a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b236f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b236f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionClosureNotification_::_3_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, a1 + 8);
  if ( *(_BYTE *)(a1 + 272) )
  {
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
  }
  else
  {
    if ( *(_DWORD *)a1 == 1 )
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__AppPrioritization::AppPrioritizationManager::HandleConnectionClosureNotification_::_3_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__AppPrioritization::AppPrioritizationManager::HandleConnectionClosureNotification_::_3_::_lambda_1___(
        a1 + 232,
        a2);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
  }
}

```

## disassembly

```asm
0x1800b22f0  mov     [rsp+arg_8], rbx
0x1800b22f5  push    rdi
0x1800b22f6  sub     rsp, 30h
0x1800b22fa  mov     rdi, rdx
0x1800b22fd  mov     rbx, rcx
0x1800b2300  mov     [rsp+38h+lpCriticalSection], 0
0x1800b2309  lea     rdx, [rcx+8]
0x1800b230d  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800b2312  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800b2317  nop
0x1800b2318  lea     rcx, [rbx+98h]
0x1800b231f  cmp     byte ptr [rcx+78h], 0
0x1800b2323  jz      short loc_1800B2337
0x1800b2325  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800b232a  test    rcx, rcx
0x1800b232d  jz      short loc_1800B2375
0x1800b232f  call    cs:__imp_LeaveCriticalSection
0x1800b2335  jmp     short loc_1800B2375
0x1800b2337  mov     rdx, rdi
0x1800b233a  cmp     dword ptr [rbx], 1
0x1800b233d  jnz     short loc_1800B2346
0x1800b233f  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__AppPrioritization__AppPrioritizationManager__HandleConnectionClosureNotification____3____lambda_1___
0x1800b2344  jmp     short loc_1800B2350
0x1800b2346  add     rcx, 50h ; 'P'
0x1800b234a  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__AppPrioritization__AppPrioritizationManager__HandleConnectionClosureNotification____3____lambda_1___
0x1800b234f  nop
0x1800b2350  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800b2355  test    rcx, rcx
0x1800b2358  jz      short loc_1800B2360
0x1800b235a  call    cs:__imp_LeaveCriticalSection
0x1800b2360  lock inc qword ptr [rbx+88h]
0x1800b2368  mov     rcx, [rbx+80h]; pwk
0x1800b236f  call    cs:__imp_SubmitThreadpoolWork
0x1800b2375  mov     rbx, [rsp+38h+arg_8]
0x1800b237a  add     rsp, 30h
0x1800b237e  pop     rdi
0x1800b237f  retn
```
