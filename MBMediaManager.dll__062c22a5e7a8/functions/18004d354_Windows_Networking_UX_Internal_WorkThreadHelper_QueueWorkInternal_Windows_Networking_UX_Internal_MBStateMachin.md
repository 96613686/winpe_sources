# Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1_____

- ea: `0x18004d354`
- end: `0x18004d427`
- name: `Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1_____`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e4b0`

## callees

- `0x18004d2ac`
- `0x18004d354`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d3e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d3e3`
- `SHCORE!SHTaskPoolQueueTask` at `0x18004d403`
- `SHCORE!SHTaskPoolQueueTask` at `0x18004d403`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::WorkThreadHelper::QueueWorkInternal__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1__Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1_____(
        signed __int64 *a1,
        __int64 a2)
{
  signed __int64 v2; // rax
  unsigned __int64 i; // r8
  signed __int64 v4; // rtt
  unsigned int v5; // ebx
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  DWORD CurrentThreadId; // eax
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  signed __int64 *v14; // [rsp+50h] [rbp+18h] BYREF

  _m_prefetchw(a1);
  v2 = *a1;
  for ( i = *a1 + 1; ; i = v2 + 1 )
  {
    if ( i <= 1 )
    {
      v5 = -2147019873;
      if ( i != 1 )
        __fastfail(0xEu);
      return v5;
    }
    v4 = v2;
    v2 = _InterlockedCompareExchange64(a1, i, v2);
    if ( v4 == v2 )
      break;
  }
  v14 = a1;
  v7 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1____Windows::Networking::UX::Internal::WorkThreadHelper____Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1___(
                    &v13,
                    &v14,
                    a2);
  try
  {
    v8 = *v7;
    *v7 = 0;
    v9 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    CurrentThreadId = GetCurrentThreadId();
    v5 = SHTaskPoolQueueTask(0, 2, CurrentThreadId, 0, v8, 0);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7D,
                           (unsigned int)"onecoreuap\\net\\ux\\inc\\workthreadhelper.h",
                           v11);
  }
  return v5;
}

```

## disassembly

```asm
0x18004d354  mov     [rsp+arg_8], rbx
0x18004d359  push    rdi
0x18004d35a  sub     rsp, 30h
0x18004d35e  prefetchw byte ptr [rcx]
0x18004d361  mov     rax, [rcx]
0x18004d364  lea     r8, [rax+1]
0x18004d368  jmp     short loc_18004D377
0x18004d36a  lock cmpxchg [rcx], r8
0x18004d36f  mov     r8, rax
0x18004d372  jz      short loc_18004D3A2
0x18004d374  inc     r8
0x18004d377  cmp     r8, 1
0x18004d37b  ja      short loc_18004D36A
0x18004d37d  mov     ebx, 8007139Fh
0x18004d382  cmp     r8, 1
0x18004d386  jz      short loc_18004D38F
0x18004d388  mov     ecx, 0Eh
0x18004d38d  int     29h; Win8: RtlFailFast(ecx)
0x18004d38f  mov     eax, ebx
0x18004d391  jmp     short loc_18004D397
0x18004d393  mov     eax, dword ptr [rsp+38h+arg_0]
0x18004d397  mov     rbx, [rsp+38h+arg_8]
0x18004d39c  add     rsp, 30h
0x18004d3a0  pop     rdi
0x18004d3a1  retn
0x18004d3a2  mov     [rsp+38h+arg_10], rcx
0x18004d3a7  mov     r8, rdx
0x18004d3aa  lea     rdx, [rsp+38h+arg_10]
0x18004d3af  lea     rcx, [rsp+38h+arg_0]
0x18004d3b4  call    Microsoft__WRL__Details__Make_Windows__Networking__UX__Internal__WorkThreadHelper__CTaskWrapper__Windows__Networking__UX__Internal__MBStateMachine__PostMediaEvent____2____lambda_1____Windows__Networking__UX__Internal__WorkThreadHelper____Windows__Networking__UX__Internal__MBStateMachine__PostMediaEvent____2____lambda_1___
0x18004d3b9  mov     rdi, [rax]
0x18004d3bc  mov     qword ptr [rax], 0
0x18004d3c3  mov     rcx, [rsp+38h+arg_0]
0x18004d3c8  test    rcx, rcx
0x18004d3cb  jz      short loc_18004D3E3
0x18004d3cd  mov     [rsp+38h+arg_0], 0
0x18004d3d6  mov     rax, [rcx]
0x18004d3d9  mov     rax, [rax+10h]
0x18004d3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3e2  nop
0x18004d3e3  call    cs:__imp_GetCurrentThreadId
0x18004d3e9  mov     [rsp+38h+var_10], 0
0x18004d3f2  mov     [rsp+38h+var_18], rdi
0x18004d3f7  xor     r9d, r9d
0x18004d3fa  mov     r8d, eax
0x18004d3fd  lea     edx, [r9+2]
0x18004d401  xor     ecx, ecx
0x18004d403  call    cs:__imp_SHTaskPoolQueueTask
0x18004d409  mov     ebx, eax
0x18004d40b  test    rdi, rdi
0x18004d40e  jz      short loc_18004D420
0x18004d410  mov     rdx, [rdi]
0x18004d413  mov     rcx, rdi
0x18004d416  mov     rax, [rdx+10h]
0x18004d41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d41f  nop
0x18004d420  jmp     loc_18004D38F
```
