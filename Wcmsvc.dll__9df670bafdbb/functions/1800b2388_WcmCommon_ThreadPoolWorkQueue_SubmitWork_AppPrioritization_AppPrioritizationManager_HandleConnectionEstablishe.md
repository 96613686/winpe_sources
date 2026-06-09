# WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionEstablishedNotification_::_3_::_lambda_1___

- ea: `0x1800b2388`
- end: `0x1800b2418`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionEstablishedNotification_::_3_::_lambda_1___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b4bb0`

## callees

- `0x180027630`
- `0x1800b2388`
- `0x1800b2960`
- `0x1800b29fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b23c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b23f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b23c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b23f2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b2407`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b2407`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__AppPrioritization::AppPrioritizationManager::HandleConnectionEstablishedNotification_::_3_::_lambda_1___(
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
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__AppPrioritization::AppPrioritizationManager::HandleConnectionEstablishedNotification_::_3_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__AppPrioritization::AppPrioritizationManager::HandleConnectionEstablishedNotification_::_3_::_lambda_1___(
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
0x1800b2388  mov     [rsp+arg_10], rbx
0x1800b238d  push    rdi
0x1800b238e  sub     rsp, 30h
0x1800b2392  mov     rdi, rdx
0x1800b2395  mov     rbx, rcx
0x1800b2398  mov     [rsp+38h+lpCriticalSection], 0
0x1800b23a1  lea     rdx, [rcx+8]
0x1800b23a5  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800b23aa  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800b23af  nop
0x1800b23b0  lea     rcx, [rbx+98h]
0x1800b23b7  cmp     byte ptr [rcx+78h], 0
0x1800b23bb  jz      short loc_1800B23CF
0x1800b23bd  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800b23c2  test    rcx, rcx
0x1800b23c5  jz      short loc_1800B240D
0x1800b23c7  call    cs:__imp_LeaveCriticalSection
0x1800b23cd  jmp     short loc_1800B240D
0x1800b23cf  mov     rdx, rdi
0x1800b23d2  cmp     dword ptr [rbx], 1
0x1800b23d5  jnz     short loc_1800B23DE
0x1800b23d7  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__AppPrioritization__AppPrioritizationManager__HandleConnectionEstablishedNotification____3____lambda_1___
0x1800b23dc  jmp     short loc_1800B23E8
0x1800b23de  add     rcx, 50h ; 'P'
0x1800b23e2  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__AppPrioritization__AppPrioritizationManager__HandleConnectionEstablishedNotification____3____lambda_1___
0x1800b23e7  nop
0x1800b23e8  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800b23ed  test    rcx, rcx
0x1800b23f0  jz      short loc_1800B23F8
0x1800b23f2  call    cs:__imp_LeaveCriticalSection
0x1800b23f8  lock inc qword ptr [rbx+88h]
0x1800b2400  mov     rcx, [rbx+80h]; pwk
0x1800b2407  call    cs:__imp_SubmitThreadpoolWork
0x1800b240d  mov     rbx, [rsp+38h+arg_10]
0x1800b2412  add     rsp, 30h
0x1800b2416  pop     rdi
0x1800b2417  retn
```
