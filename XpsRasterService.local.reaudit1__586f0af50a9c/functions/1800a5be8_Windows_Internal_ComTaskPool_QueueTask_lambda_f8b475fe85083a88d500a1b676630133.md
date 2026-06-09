# Windows::Internal::ComTaskPool::QueueTask__lambda_f8b475fe85083a88d500a1b676630133___

- ea: `0x1800a5be8`
- end: `0x1800a5c85`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_f8b475fe85083a88d500a1b676630133___`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a7810`

## callees

- `0x1800031a4`
- `0x1800a5b0c`
- `0x1800a5be8`
- `0x1800a63bc`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800a5c56`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800a5c56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_f8b475fe85083a88d500a1b676630133___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  void *v10; // [rsp+30h] [rbp-18h] BYREF

  v6 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133___::CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____lambda_f8b475fe85083a88d500a1b676630133___(
           v6,
           a4);
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____(&v10);
  v8 = SHTaskPoolQueueTask(0, 4096, a3, 0, v7, 0, v10);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x1800a5be8  mov     [rsp+arg_0], rbx
0x1800a5bed  mov     [rsp+arg_8], rsi
0x1800a5bf2  push    rdi
0x1800a5bf3  sub     rsp, 40h
0x1800a5bf7  mov     rdi, r9
0x1800a5bfa  mov     esi, r8d
0x1800a5bfd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a5c04  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800a5c09  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a5c0e  mov     [rsp+48h+var_18], rax
0x1800a5c13  xor     ebx, ebx
0x1800a5c15  test    rax, rax
0x1800a5c18  jz      short loc_1800A5C31
0x1800a5c1a  mov     rdx, rdi
0x1800a5c1d  mov     rcx, rax
0x1800a5c20  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____lambda_f8b475fe85083a88d500a1b676630133___
0x1800a5c25  mov     rbx, rax
0x1800a5c28  mov     [rsp+48h+var_18], 0
0x1800a5c31  lea     rcx, [rsp+48h+var_18]
0x1800a5c36  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f8b475fe85083a88d500a1b676630133_____
0x1800a5c3b  mov     [rsp+48h+var_20], 0
0x1800a5c44  mov     [rsp+48h+var_28], rbx
0x1800a5c49  xor     r9d, r9d
0x1800a5c4c  mov     r8d, esi
0x1800a5c4f  mov     edx, 1000h
0x1800a5c54  xor     ecx, ecx
0x1800a5c56  call    cs:__imp_SHTaskPoolQueueTask
0x1800a5c5c  mov     edi, eax
0x1800a5c5e  test    rbx, rbx
0x1800a5c61  jz      short loc_1800A5C73
0x1800a5c63  mov     rdx, [rbx]
0x1800a5c66  mov     rcx, rbx
0x1800a5c69  mov     rax, [rdx+10h]
0x1800a5c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c72  nop
0x1800a5c73  mov     eax, edi
0x1800a5c75  mov     rbx, [rsp+48h+arg_0]
0x1800a5c7a  mov     rsi, [rsp+48h+arg_8]
0x1800a5c7f  add     rsp, 40h
0x1800a5c83  pop     rdi
0x1800a5c84  retn
```
