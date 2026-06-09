# Windows::Networking::UX::Internal::WorkThreadHelper::SubmitWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1_____

- ea: `0x180064c10`
- end: `0x180064cf6`
- name: `Windows::Networking::UX::Internal::WorkThreadHelper::SubmitWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1_____`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064bd4`

## callees

- `0x18006453c`
- `0x180064c10`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064cb4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180064cd2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180064cd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WorkThreadHelper::SubmitWorkInternal__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1_____(
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
    v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapperForCurrentEffectiveUser__Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1____Windows::Networking::UX::Internal::WorkThreadHelper____Windows::Networking::UX::Internal::WlanStateMachine::ProbeAuthProxyCreds_::_2_::_lambda_1___();
    v7 = *v6;
    *v6 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    CurrentThreadId = GetCurrentThreadId();
    v4 = SHTaskPoolQueueTask(0, 0, CurrentThreadId);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x64,
                           (unsigned int)"onecoreuap\\net\\ux\\inc\\workthreadhelper.h",
                           v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180064c10  mov     [rsp+arg_8], rbx
0x180064c15  push    rdi
0x180064c16  sub     rsp, 40h
0x180064c1a  mov     [rsp+48h+arg_0], 0
0x180064c22  prefetchw byte ptr [rcx]
0x180064c25  mov     rax, [rcx]
0x180064c28  lea     r8, [rax+1]
0x180064c2c  jmp     short loc_180064C3B
0x180064c2e  lock cmpxchg [rcx], r8
0x180064c33  mov     r8, rax
0x180064c36  jz      short loc_180064C66
0x180064c38  inc     r8
0x180064c3b  cmp     r8, 1
0x180064c3f  ja      short loc_180064C2E
0x180064c41  mov     edi, 8007139Fh
0x180064c46  cmp     r8, 1
0x180064c4a  jz      short loc_180064C53
0x180064c4c  mov     ecx, 0Eh
0x180064c51  int     29h; Win8: RtlFailFast(ecx)
0x180064c53  mov     eax, edi
0x180064c55  jmp     short loc_180064C5B
0x180064c57  mov     eax, [rsp+48h+arg_0]
0x180064c5b  mov     rbx, [rsp+48h+arg_8]
0x180064c60  add     rsp, 40h
0x180064c64  pop     rdi
0x180064c65  retn
0x180064c66  mov     [rsp+48h+arg_18], rcx
0x180064c6b  mov     r8, rdx
0x180064c6e  lea     rdx, [rsp+48h+arg_18]
0x180064c73  lea     rcx, [rsp+48h+arg_10]
0x180064c78  call    Microsoft__WRL__Details__Make_Windows__Networking__UX__Internal__WorkThreadHelper__CTaskWrapperForCurrentEffectiveUser__Windows__Networking__UX__Internal__WlanStateMachine__ProbeAuthProxyCreds____2____lambda_1____Windows__Networking__UX__Internal__WorkThreadHelper____Windows__Networking__UX__Internal__WlanStateMachine__ProbeAuthProxyCreds____2____lambda_1___
0x180064c7d  mov     rbx, [rax]
0x180064c80  mov     [rsp+48h+var_18], rbx
0x180064c85  mov     qword ptr [rax], 0
0x180064c8c  mov     [rsp+48h+arg_0], 1
0x180064c94  mov     rcx, [rsp+48h+arg_10]
0x180064c99  test    rcx, rcx
0x180064c9c  jz      short loc_180064CB4
0x180064c9e  mov     [rsp+48h+arg_10], 0
0x180064ca7  mov     rax, [rcx]
0x180064caa  mov     rax, [rax+10h]
0x180064cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cb3  nop
0x180064cb4  call    cs:__imp_GetCurrentThreadId
0x180064cba  mov     [rsp+48h+var_20], 0
0x180064cc3  mov     [rsp+48h+var_28], rbx
0x180064cc8  xor     r9d, r9d
0x180064ccb  mov     r8d, eax
0x180064cce  xor     edx, edx
0x180064cd0  xor     ecx, ecx
0x180064cd2  call    cs:__imp_SHTaskPoolQueueTask
0x180064cd8  mov     edi, eax
0x180064cda  test    rbx, rbx
0x180064cdd  jz      short loc_180064CEF
0x180064cdf  mov     rdx, [rbx]
0x180064ce2  mov     rcx, rbx
0x180064ce5  mov     rax, [rdx+10h]
0x180064ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cee  nop
0x180064cef  jmp     loc_180064C53
```
