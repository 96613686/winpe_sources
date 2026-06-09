# Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1___

- ea: `0x18002405c`
- end: `0x1800240f8`
- name: `Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1___`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e094`

## callees

- `0x180002a04`
- `0x1800227cc`
- `0x18002405c`
- `0x1800280c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800240c9`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800240c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  void *v10; // [rsp+30h] [rbp-18h] BYREF

  v6 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1___::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1_____Windows::Networking::UX::NetworkUXManager::OnCategoryChange_::_2_::_lambda_1___(
           v6,
           a4);
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_____(&v10);
  v8 = SHTaskPoolQueueTask(0, 2, a3);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x18002405c  mov     [rsp+arg_0], rbx
0x180024061  mov     [rsp+arg_8], rsi
0x180024066  push    rdi
0x180024067  sub     rsp, 40h
0x18002406b  mov     rdi, r9
0x18002406e  mov     esi, r8d
0x180024071  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024078  mov     ecx, 30h ; '0'; unsigned __int64
0x18002407d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024082  mov     [rsp+48h+var_18], rax
0x180024087  xor     ebx, ebx
0x180024089  test    rax, rax
0x18002408c  jz      short loc_1800240A5
0x18002408e  mov     rdx, rdi
0x180024091  mov     rcx, rax
0x180024094  call    Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager__OnCategoryChange____2____lambda_1_____CTaskWrapper__Windows__Networking__UX__NetworkUXManager__OnCategoryChange____2____lambda_1_____Windows__Networking__UX__NetworkUXManager__OnCategoryChange____2____lambda_1___
0x180024099  mov     rbx, rax
0x18002409c  mov     [rsp+48h+var_18], 0
0x1800240a5  lea     rcx, [rsp+48h+var_18]
0x1800240aa  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____
0x1800240af  mov     [rsp+48h+var_20], 0
0x1800240b8  mov     [rsp+48h+var_28], rbx
0x1800240bd  xor     r9d, r9d
0x1800240c0  mov     r8d, esi
0x1800240c3  lea     edx, [r9+2]
0x1800240c7  xor     ecx, ecx
0x1800240c9  call    cs:__imp_SHTaskPoolQueueTask
0x1800240cf  mov     edi, eax
0x1800240d1  test    rbx, rbx
0x1800240d4  jz      short loc_1800240E6
0x1800240d6  mov     rdx, [rbx]
0x1800240d9  mov     rcx, rbx
0x1800240dc  mov     rax, [rdx+10h]
0x1800240e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240e5  nop
0x1800240e6  mov     eax, edi
0x1800240e8  mov     rbx, [rsp+48h+arg_0]
0x1800240ed  mov     rsi, [rsp+48h+arg_8]
0x1800240f2  add     rsp, 40h
0x1800240f6  pop     rdi
0x1800240f7  retn
```
