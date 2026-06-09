# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1___

- ea: `0x180024210`
- end: `0x1800242a3`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1___`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031dec`

## callees

- `0x180002a04`
- `0x18002282c`
- `0x180024210`
- `0x1800280c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002425b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002425b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024279`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024279`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1___::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1_____Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1___(
           v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_____(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180024210  mov     [rsp+arg_0], rbx
0x180024215  push    rdi
0x180024216  sub     rsp, 30h
0x18002421a  mov     rdi, rdx
0x18002421d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024224  mov     ecx, 50h ; 'P'; unsigned __int64
0x180024229  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002422e  mov     [rsp+38h+arg_10], rax
0x180024233  xor     ebx, ebx
0x180024235  test    rax, rax
0x180024238  jz      short loc_180024251
0x18002423a  mov     rdx, rdi
0x18002423d  mov     rcx, rax
0x180024240  call    Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager__WaitForInitializeComplete____35____lambda_1_____CTaskWrapper__Windows__Networking__UX__NetworkUXManager__WaitForInitializeComplete____35____lambda_1_____Windows__Networking__UX__NetworkUXManager__WaitForInitializeComplete____35____lambda_1___
0x180024245  mov     rbx, rax
0x180024248  mov     [rsp+38h+arg_10], 0
0x180024251  lea     rcx, [rsp+38h+arg_10]
0x180024256  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____
0x18002425b  call    cs:__imp_GetCurrentThreadId
0x180024261  mov     [rsp+38h+var_10], 0
0x18002426a  mov     [rsp+38h+var_18], rbx
0x18002426f  xor     r9d, r9d
0x180024272  mov     r8d, eax
0x180024275  xor     edx, edx
0x180024277  xor     ecx, ecx
0x180024279  call    cs:__imp_SHTaskPoolQueueTask
0x18002427f  mov     edi, eax
0x180024281  test    rbx, rbx
0x180024284  jz      short loc_180024296
0x180024286  mov     rdx, [rbx]
0x180024289  mov     rcx, rbx
0x18002428c  mov     rax, [rdx+10h]
0x180024290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024295  nop
0x180024296  mov     eax, edi
0x180024298  mov     rbx, [rsp+38h+arg_0]
0x18002429d  add     rsp, 30h
0x1800242a1  pop     rdi
0x1800242a2  retn
```
