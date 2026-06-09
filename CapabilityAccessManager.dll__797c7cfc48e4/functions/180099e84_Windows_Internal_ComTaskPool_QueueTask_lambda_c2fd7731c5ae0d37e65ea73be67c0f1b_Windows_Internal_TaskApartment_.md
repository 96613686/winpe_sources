# Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(Windows::Internal::TaskApartment,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)

- ea: `0x180099e84`
- end: `0x180099f18`
- name: `??$QueueTask@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009e264`

## callees

- `0x180009528`
- `0x180016968`
- `0x180099b74`
- `0x180099e84`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ecf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ecf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180099eee`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180099eee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
        __int64 a1,
        _QWORD *a2)
{
  void *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
           (__int64)v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180099e84  mov     [rsp+arg_0], rbx
0x180099e89  push    rdi
0x180099e8a  sub     rsp, 30h
0x180099e8e  mov     rdi, rdx
0x180099e91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180099e98  mov     ecx, 18h; unsigned __int64
0x180099e9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180099ea2  mov     [rsp+38h+arg_10], rax
0x180099ea7  xor     ebx, ebx
0x180099ea9  test    rax, rax
0x180099eac  jz      short loc_180099EC5
0x180099eae  mov     rdx, rdi
0x180099eb1  mov     rcx, rax
0x180099eb4  call    ??$?0V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x180099eb9  mov     rbx, rax
0x180099ebc  mov     [rsp+38h+arg_10], 0
0x180099ec5  lea     rcx, [rsp+38h+arg_10]
0x180099eca  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180099ecf  call    cs:__imp_GetCurrentThreadId
0x180099ed5  mov     [rsp+38h+var_10], 0
0x180099ede  mov     [rsp+38h+var_18], rbx
0x180099ee3  xor     r9d, r9d
0x180099ee6  mov     r8d, eax
0x180099ee9  xor     edx, edx
0x180099eeb  lea     ecx, [rdx+3]
0x180099eee  call    cs:__imp_SHTaskPoolQueueTask
0x180099ef4  mov     edi, eax
0x180099ef6  test    rbx, rbx
0x180099ef9  jz      short loc_180099F0B
0x180099efb  mov     rdx, [rbx]
0x180099efe  mov     rcx, rbx
0x180099f01  mov     rax, [rdx+10h]
0x180099f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f0a  nop
0x180099f0b  mov     eax, edi
0x180099f0d  mov     rbx, [rsp+38h+arg_0]
0x180099f12  add     rsp, 30h
0x180099f16  pop     rdi
0x180099f17  retn
```
