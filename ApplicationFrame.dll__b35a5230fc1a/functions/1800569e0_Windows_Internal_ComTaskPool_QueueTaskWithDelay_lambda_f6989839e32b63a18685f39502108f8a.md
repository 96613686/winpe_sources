# Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_f6989839e32b63a18685f39502108f8a___

- ea: `0x1800569e0`
- end: `0x180056a85`
- name: `Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_f6989839e32b63a18685f39502108f8a___`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e69c`

## callees

- `0x18004229c`
- `0x180046b0c`
- `0x1800558b8`
- `0x1800569e0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056a37`
- `SHCORE!SHTaskPoolQueueTask` at `0x180056a56`
- `SHCORE!SHTaskPoolQueueTask` at `0x180056a56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_f6989839e32b63a18685f39502108f8a___(
        __int64 a1,
        unsigned int a2,
        void *a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v9; // edi
  void *v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = a3;
  v6 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f6989839e32b63a18685f39502108f8a___::CTaskWrapper__lambda_f6989839e32b63a18685f39502108f8a_____lambda_f6989839e32b63a18685f39502108f8a___(
           v6,
           a4);
    v11 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_a659ac14e83ba6c7164f343f4d2dc7d1__const_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_a659ac14e83ba6c7164f343f4d2dc7d1__const_____(&v11);
  CurrentThreadId = GetCurrentThreadId();
  v9 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v9;
}

```

## disassembly

```asm
0x1800569e0  mov     [rsp+arg_0], rbx
0x1800569e5  mov     [rsp+arg_8], rsi
0x1800569ea  mov     [rsp+arg_10], r8
0x1800569ef  push    rdi
0x1800569f0  sub     rsp, 30h
0x1800569f4  mov     rdi, r9
0x1800569f7  mov     esi, edx
0x1800569f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180056a00  mov     ecx, 28h ; '('; unsigned __int64
0x180056a05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180056a0a  mov     [rsp+38h+arg_10], rax
0x180056a0f  xor     ebx, ebx
0x180056a11  test    rax, rax
0x180056a14  jz      short loc_180056A2D
0x180056a16  mov     rdx, rdi
0x180056a19  mov     rcx, rax
0x180056a1c  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f6989839e32b63a18685f39502108f8a_____CTaskWrapper__lambda_f6989839e32b63a18685f39502108f8a_____lambda_f6989839e32b63a18685f39502108f8a___
0x180056a21  mov     rbx, rax
0x180056a24  mov     [rsp+38h+arg_10], 0
0x180056a2d  lea     rcx, [rsp+38h+arg_10]
0x180056a32  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_a659ac14e83ba6c7164f343f4d2dc7d1__const________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_a659ac14e83ba6c7164f343f4d2dc7d1__const_____
0x180056a37  call    cs:__imp_GetCurrentThreadId
0x180056a3d  mov     [rsp+38h+var_10], 0
0x180056a46  mov     [rsp+38h+var_18], rbx
0x180056a4b  mov     r9d, esi
0x180056a4e  mov     r8d, eax
0x180056a51  xor     edx, edx
0x180056a53  lea     ecx, [rdx+3]
0x180056a56  call    cs:__imp_SHTaskPoolQueueTask
0x180056a5c  mov     edi, eax
0x180056a5e  test    rbx, rbx
0x180056a61  jz      short loc_180056A73
0x180056a63  mov     rdx, [rbx]
0x180056a66  mov     rcx, rbx
0x180056a69  mov     rax, [rdx+10h]
0x180056a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a72  nop
0x180056a73  mov     eax, edi
0x180056a75  mov     rbx, [rsp+38h+arg_0]
0x180056a7a  mov     rsi, [rsp+38h+arg_8]
0x180056a7f  add     rsp, 30h
0x180056a83  pop     rdi
0x180056a84  retn
```
