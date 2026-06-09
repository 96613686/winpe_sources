# Windows::Internal::ComTaskPool::QueueTask__lambda_536eb1c8974d2b35d088cee14bcb25f5___

- ea: `0x18003bcf0`
- end: `0x18003bd8d`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_536eb1c8974d2b35d088cee14bcb25f5___`
- size: `157`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040b40`

## callees

- `0x180003110`
- `0x180020428`
- `0x18003ad4c`
- `0x18003bcf0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003bd5e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003bd5e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_536eb1c8974d2b35d088cee14bcb25f5___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  void *v10; // [rsp+30h] [rbp-18h] BYREF

  v6 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5___::CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____lambda_536eb1c8974d2b35d088cee14bcb25f5___(
           v6,
           a4);
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____(&v10);
  v8 = SHTaskPoolQueueTask(0, 4096, a3, 0, v7, 0, v10);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x18003bcf0  mov     [rsp+arg_0], rbx
0x18003bcf5  mov     [rsp+arg_8], rsi
0x18003bcfa  push    rdi
0x18003bcfb  sub     rsp, 40h
0x18003bcff  mov     rdi, r9
0x18003bd02  mov     esi, r8d
0x18003bd05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003bd0c  mov     ecx, 38h ; '8'; unsigned __int64
0x18003bd11  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003bd16  mov     [rsp+48h+var_18], rax
0x18003bd1b  xor     ebx, ebx
0x18003bd1d  test    rax, rax
0x18003bd20  jz      short loc_18003BD39
0x18003bd22  mov     rdx, rdi
0x18003bd25  mov     rcx, rax
0x18003bd28  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____lambda_536eb1c8974d2b35d088cee14bcb25f5___
0x18003bd2d  mov     rbx, rax
0x18003bd30  mov     [rsp+48h+var_18], 0
0x18003bd39  lea     rcx, [rsp+48h+var_18]
0x18003bd3e  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_536eb1c8974d2b35d088cee14bcb25f5_____
0x18003bd43  mov     [rsp+48h+var_20], 0
0x18003bd4c  mov     [rsp+48h+var_28], rbx
0x18003bd51  xor     r9d, r9d
0x18003bd54  mov     r8d, esi
0x18003bd57  mov     edx, 1000h
0x18003bd5c  xor     ecx, ecx
0x18003bd5e  call    cs:__imp_SHTaskPoolQueueTask
0x18003bd64  mov     edi, eax
0x18003bd66  test    rbx, rbx
0x18003bd69  jz      short loc_18003BD7B
0x18003bd6b  mov     rdx, [rbx]
0x18003bd6e  mov     rcx, rbx
0x18003bd71  mov     rax, [rdx+10h]
0x18003bd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd7a  nop
0x18003bd7b  mov     eax, edi
0x18003bd7d  mov     rbx, [rsp+48h+arg_0]
0x18003bd82  mov     rsi, [rsp+48h+arg_8]
0x18003bd87  add     rsp, 40h
0x18003bd8b  pop     rdi
0x18003bd8c  retn
```
