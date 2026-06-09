# Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_e5d792188a602bc9285e5592076bd83e___

- ea: `0x180040540`
- end: `0x1800405c0`
- name: `Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_e5d792188a602bc9285e5592076bd83e___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000592c`

## callees

- `0x180040540`
- `0x180042998`
- `0x180046b0c`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040577`
- `SHCORE!SHTaskPoolQueueTask` at `0x180040596`
- `SHCORE!SHTaskPoolQueueTask` at `0x180040596`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTaskWithDelay__lambda_e5d792188a602bc9285e5592076bd83e___(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v9; // edi

  v6 = operator new(0x178u, (const struct std::nothrow_t *)std::nothrow);
  if ( v6 )
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_e5d792188a602bc9285e5592076bd83e___::CTaskWrapper__lambda_e5d792188a602bc9285e5592076bd83e_____lambda_e5d792188a602bc9285e5592076bd83e___(
           v6,
           a4);
  else
    v7 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v9 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v9;
}

```

## disassembly

```asm
0x180040540  mov     [rsp+arg_0], rbx
0x180040545  push    rdi
0x180040546  sub     rsp, 30h
0x18004054a  mov     rbx, r9
0x18004054d  mov     edi, edx
0x18004054f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040556  mov     ecx, 178h; unsigned __int64
0x18004055b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180040560  test    rax, rax
0x180040563  jz      short loc_180040575
0x180040565  mov     rdx, rbx
0x180040568  mov     rcx, rax
0x18004056b  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_e5d792188a602bc9285e5592076bd83e_____CTaskWrapper__lambda_e5d792188a602bc9285e5592076bd83e_____lambda_e5d792188a602bc9285e5592076bd83e___
0x180040570  mov     rbx, rax
0x180040573  jmp     short loc_180040577
0x180040575  xor     ebx, ebx
0x180040577  call    cs:__imp_GetCurrentThreadId
0x18004057d  mov     [rsp+38h+var_10], 0
0x180040586  mov     [rsp+38h+var_18], rbx
0x18004058b  mov     r9d, edi
0x18004058e  mov     r8d, eax
0x180040591  xor     edx, edx
0x180040593  lea     ecx, [rdx+3]
0x180040596  call    cs:__imp_SHTaskPoolQueueTask
0x18004059c  mov     edi, eax
0x18004059e  test    rbx, rbx
0x1800405a1  jz      short loc_1800405B3
0x1800405a3  mov     rcx, [rbx]
0x1800405a6  mov     rax, [rcx+10h]
0x1800405aa  mov     rcx, rbx
0x1800405ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405b2  nop
0x1800405b3  mov     eax, edi
0x1800405b5  mov     rbx, [rsp+38h+arg_0]
0x1800405ba  add     rsp, 30h
0x1800405be  pop     rdi
0x1800405bf  retn
```
