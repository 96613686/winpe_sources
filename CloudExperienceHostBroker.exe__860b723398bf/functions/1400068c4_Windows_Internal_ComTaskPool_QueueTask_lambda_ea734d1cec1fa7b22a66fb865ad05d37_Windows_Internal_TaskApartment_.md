# Windows::Internal::ComTaskPool::QueueTask<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(Windows::Internal::TaskApartment,_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ &&)

- ea: `0x1400068c4`
- end: `0x140006957`
- name: `??$QueueTask@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008a10`

## callees

- `0x1400021a8`
- `0x14000622c`
- `0x1400068c4`
- `0x140007360`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000690f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000690f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14000692d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14000692d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  _QWORD *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(
           v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x1400068c4  mov     [rsp+arg_0], rbx
0x1400068c9  push    rdi
0x1400068ca  sub     rsp, 30h
0x1400068ce  mov     rdi, rdx
0x1400068d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400068d8  mov     ecx, 28h ; '('; unsigned __int64
0x1400068dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400068e2  mov     [rsp+38h+arg_10], rax
0x1400068e7  xor     ebx, ebx
0x1400068e9  test    rax, rax
0x1400068ec  jz      short loc_140006905
0x1400068ee  mov     rdx, rdi
0x1400068f1  mov     rcx, rax
0x1400068f4  call    ??$?0V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ &&)
0x1400068f9  mov     rbx, rax
0x1400068fc  mov     [rsp+38h+arg_10], 0
0x140006905  lea     rcx, [rsp+38h+arg_10]
0x14000690a  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(void)
0x14000690f  call    cs:__imp_GetCurrentThreadId
0x140006915  mov     [rsp+38h+var_10], 0
0x14000691e  mov     [rsp+38h+var_18], rbx
0x140006923  xor     r9d, r9d
0x140006926  mov     r8d, eax
0x140006929  xor     edx, edx
0x14000692b  xor     ecx, ecx
0x14000692d  call    cs:__imp_SHTaskPoolQueueTask
0x140006933  mov     edi, eax
0x140006935  test    rbx, rbx
0x140006938  jz      short loc_14000694A
0x14000693a  mov     rdx, [rbx]
0x14000693d  mov     rcx, rbx
0x140006940  mov     rax, [rdx+10h]
0x140006944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006949  nop
0x14000694a  mov     eax, edi
0x14000694c  mov     rbx, [rsp+38h+arg_0]
0x140006951  add     rsp, 30h
0x140006955  pop     rdi
0x140006956  retn
```
