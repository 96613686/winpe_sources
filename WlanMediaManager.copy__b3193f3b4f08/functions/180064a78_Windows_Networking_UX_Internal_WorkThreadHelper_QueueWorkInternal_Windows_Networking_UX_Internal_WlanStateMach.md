# Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1_____

- ea: `0x180064a78`
- end: `0x180064b60`
- name: `Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1_____`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064a3c`

## callees

- `0x1800645e8`
- `0x180064a78`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064b1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064b1c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180064b3c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180064b3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1_____(
        signed __int64 *a1)
{
  signed __int64 v1; // rax
  unsigned __int64 i; // r8
  signed __int64 v3; // rtt
  unsigned int v4; // edi
  __int64 *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+60h] [rbp+18h]

  _m_prefetchw(a1);
  v1 = *a1;
  for ( i = *a1 + 1; ; i = v1 + 1 )
  {
    if ( i <= 1 )
    {
      v4 = -2147019873;
      if ( i != 1 )
        __fastfail(0xEu);
      return v4;
    }
    v3 = v1;
    v1 = _InterlockedCompareExchange64(a1, i, v1);
    if ( v3 == v1 )
      break;
  }
  try
  {
    v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1____Windows::Networking::UX::Internal::WorkThreadHelper____Windows::Networking::UX::Internal::WlanStateMachine::_SubmitEventWorker_::_2_::_lambda_1___();
    v7 = *v6;
    *v6 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    CurrentThreadId = GetCurrentThreadId();
    v4 = SHTaskPoolQueueTask(0, 2, CurrentThreadId, 0, v7, 0);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7D,
                           (unsigned int)"onecoreuap\\net\\ux\\inc\\workthreadhelper.h",
                           v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180064a78  mov     [rsp+arg_8], rbx
0x180064a7d  push    rdi
0x180064a7e  sub     rsp, 40h
0x180064a82  mov     [rsp+48h+arg_0], 0
0x180064a8a  prefetchw byte ptr [rcx]
0x180064a8d  mov     rax, [rcx]
0x180064a90  lea     r8, [rax+1]
0x180064a94  jmp     short loc_180064AA3
0x180064a96  lock cmpxchg [rcx], r8
0x180064a9b  mov     r8, rax
0x180064a9e  jz      short loc_180064ACE
0x180064aa0  inc     r8
0x180064aa3  cmp     r8, 1
0x180064aa7  ja      short loc_180064A96
0x180064aa9  mov     edi, 8007139Fh
0x180064aae  cmp     r8, 1
0x180064ab2  jz      short loc_180064ABB
0x180064ab4  mov     ecx, 0Eh
0x180064ab9  int     29h; Win8: RtlFailFast(ecx)
0x180064abb  mov     eax, edi
0x180064abd  jmp     short loc_180064AC3
0x180064abf  mov     eax, [rsp+48h+arg_0]
0x180064ac3  mov     rbx, [rsp+48h+arg_8]
0x180064ac8  add     rsp, 40h
0x180064acc  pop     rdi
0x180064acd  retn
0x180064ace  mov     [rsp+48h+arg_18], rcx
0x180064ad3  mov     r8, rdx
0x180064ad6  lea     rdx, [rsp+48h+arg_18]
0x180064adb  lea     rcx, [rsp+48h+arg_10]
0x180064ae0  call    Microsoft__WRL__Details__Make_Windows__Networking__UX__Internal__WorkThreadHelper__CTaskWrapperForCurrentEffectiveUser__Windows__Networking__UX__Internal__WlanStateMachine___SubmitEventWorker____2____lambda_1____Windows__Networking__UX__Internal__WorkThreadHelper____Windows__Networking__UX__Internal__WlanStateMachine___SubmitEventWorker____2____lambda_1___
0x180064ae5  mov     rbx, [rax]
0x180064ae8  mov     [rsp+48h+var_18], rbx
0x180064aed  mov     qword ptr [rax], 0
0x180064af4  mov     [rsp+48h+arg_0], 1
0x180064afc  mov     rcx, [rsp+48h+arg_10]
0x180064b01  test    rcx, rcx
0x180064b04  jz      short loc_180064B1C
0x180064b06  mov     [rsp+48h+arg_10], 0
0x180064b0f  mov     rax, [rcx]
0x180064b12  mov     rax, [rax+10h]
0x180064b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b1b  nop
0x180064b1c  call    cs:__imp_GetCurrentThreadId
0x180064b22  mov     [rsp+48h+var_20], 0
0x180064b2b  mov     [rsp+48h+var_28], rbx
0x180064b30  xor     r9d, r9d
0x180064b33  mov     r8d, eax
0x180064b36  lea     edx, [r9+2]
0x180064b3a  xor     ecx, ecx
0x180064b3c  call    cs:__imp_SHTaskPoolQueueTask
0x180064b42  mov     edi, eax
0x180064b44  test    rbx, rbx
0x180064b47  jz      short loc_180064B59
0x180064b49  mov     rdx, [rbx]
0x180064b4c  mov     rcx, rbx
0x180064b4f  mov     rax, [rdx+10h]
0x180064b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b58  nop
0x180064b59  jmp     loc_180064ABB
```
