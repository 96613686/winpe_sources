# Windows::Internal::ComTaskPool::QueueTask__lambda_5ce3936d8ad826038f88bbedacf4b390___

- ea: `0x180013b88`
- end: `0x180013c25`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_5ce3936d8ad826038f88bbedacf4b390___`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015120`

## callees

- `0x1800032b8`
- `0x1800138d8`
- `0x180013b88`
- `0x180014698`
- `0x18002a010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180013bf6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180013bf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_5ce3936d8ad826038f88bbedacf4b390___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  void *v10; // [rsp+30h] [rbp-18h] BYREF

  v6 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390___::CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____lambda_5ce3936d8ad826038f88bbedacf4b390___(
           v6,
           a4);
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____(&v10);
  v8 = SHTaskPoolQueueTask(1, 64, a3);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x180013b88  mov     [rsp+arg_0], rbx
0x180013b8d  mov     [rsp+arg_8], rsi
0x180013b92  push    rdi
0x180013b93  sub     rsp, 40h
0x180013b97  mov     rdi, r9
0x180013b9a  mov     esi, r8d
0x180013b9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013ba4  mov     ecx, 20h ; ' '; unsigned __int64
0x180013ba9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013bae  mov     [rsp+48h+var_18], rax
0x180013bb3  xor     ebx, ebx
0x180013bb5  test    rax, rax
0x180013bb8  jz      short loc_180013BD1
0x180013bba  mov     rdx, rdi
0x180013bbd  mov     rcx, rax
0x180013bc0  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____lambda_5ce3936d8ad826038f88bbedacf4b390___
0x180013bc5  mov     rbx, rax
0x180013bc8  mov     [rsp+48h+var_18], 0
0x180013bd1  lea     rcx, [rsp+48h+var_18]
0x180013bd6  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_5ce3936d8ad826038f88bbedacf4b390_____
0x180013bdb  mov     [rsp+48h+var_20], 0
0x180013be4  mov     [rsp+48h+var_28], rbx
0x180013be9  xor     r9d, r9d
0x180013bec  mov     r8d, esi
0x180013bef  lea     edx, [r9+40h]
0x180013bf3  lea     ecx, [rdx-3Fh]
0x180013bf6  call    cs:__imp_SHTaskPoolQueueTask
0x180013bfc  mov     edi, eax
0x180013bfe  test    rbx, rbx
0x180013c01  jz      short loc_180013C13
0x180013c03  mov     rdx, [rbx]
0x180013c06  mov     rcx, rbx
0x180013c09  mov     rax, [rdx+10h]
0x180013c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c12  nop
0x180013c13  mov     eax, edi
0x180013c15  mov     rbx, [rsp+48h+arg_0]
0x180013c1a  mov     rsi, [rsp+48h+arg_8]
0x180013c1f  add     rsp, 40h
0x180013c23  pop     rdi
0x180013c24  retn
```
