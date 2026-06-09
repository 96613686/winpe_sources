# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___

- ea: `0x1800242ac`
- end: `0x18002433f`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___`
- size: `147`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033538`

## callees

- `0x180002a04`
- `0x1800228b4`
- `0x1800242ac`
- `0x1800280c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024315`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180024315`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_____Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___(
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
0x1800242ac  mov     [rsp+arg_0], rbx
0x1800242b1  push    rdi
0x1800242b2  sub     rsp, 30h
0x1800242b6  mov     rdi, rdx
0x1800242b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800242c0  mov     ecx, 28h ; '('; unsigned __int64
0x1800242c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800242ca  mov     [rsp+38h+arg_10], rax
0x1800242cf  xor     ebx, ebx
0x1800242d1  test    rax, rax
0x1800242d4  jz      short loc_1800242ED
0x1800242d6  mov     rdx, rdi
0x1800242d9  mov     rcx, rax
0x1800242dc  call    Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2___
0x1800242e1  mov     rbx, rax
0x1800242e4  mov     [rsp+38h+arg_10], 0
0x1800242ed  lea     rcx, [rsp+38h+arg_10]
0x1800242f2  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____
0x1800242f7  call    cs:__imp_GetCurrentThreadId
0x1800242fd  mov     [rsp+38h+var_10], 0
0x180024306  mov     [rsp+38h+var_18], rbx
0x18002430b  xor     r9d, r9d
0x18002430e  mov     r8d, eax
0x180024311  xor     edx, edx
0x180024313  xor     ecx, ecx
0x180024315  call    cs:__imp_SHTaskPoolQueueTask
0x18002431b  mov     edi, eax
0x18002431d  test    rbx, rbx
0x180024320  jz      short loc_180024332
0x180024322  mov     rdx, [rbx]
0x180024325  mov     rcx, rbx
0x180024328  mov     rax, [rdx+10h]
0x18002432c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024331  nop
0x180024332  mov     eax, edi
0x180024334  mov     rbx, [rsp+38h+arg_0]
0x180024339  add     rsp, 30h
0x18002433d  pop     rdi
0x18002433e  retn
```
