# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18004c23c`
- end: `0x18004c339`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180045b80`

## callees

- `0x18001d2a0`
- `0x1800204c4`
- `0x18003ee34`
- `0x180045648`
- `0x1800463e4`
- `0x1800482f0`
- `0x18004c23c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c2a2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004c2bd`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004c2bd`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // edi
  bool v7; // di
  struct Windows::Internal::IAsyncFireCompletion *v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( (int)Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  v9 = a1;
  v2 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
  v3 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v10,
                    &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v7 = v6 >= 0;
  if ( v9 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v7 )
  {
LABEL_11:
    Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth();
    v2 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth();
  }
  return v2;
}

```

## disassembly

```asm
0x18004c23c  mov     [rsp+arg_0], rbx
0x18004c241  push    rbp
0x18004c242  push    rsi
0x18004c243  push    rdi
0x18004c244  sub     rsp, 30h
0x18004c248  mov     rbx, rcx
0x18004c24b  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18004c250  cmp     eax, 4
0x18004c253  jle     loc_18004C30F
0x18004c259  lea     rcx, [rsp+48h+arg_8]
0x18004c25e  mov     [rsp+48h+arg_8], rbx
0x18004c263  xor     ebp, ebp
0x18004c265  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004c26a  lea     rcx, [rsp+48h+arg_8]
0x18004c26f  mov     [rsp+48h+arg_8], rbx
0x18004c274  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004c279  lea     rdx, [rsp+48h+arg_8]
0x18004c27e  lea     rcx, [rsp+48h+arg_10]
0x18004c283  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18004c288  mov     rsi, [rax]
0x18004c28b  mov     [rax], rbp
0x18004c28e  mov     rcx, [rsp+48h+arg_10]
0x18004c293  test    rcx, rcx
0x18004c296  jz      short loc_18004C2A2
0x18004c298  mov     [rsp+48h+arg_10], rbp
0x18004c29d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x18004c2a2  call    cs:__imp_GetCurrentThreadId
0x18004c2a8  xor     edx, edx
0x18004c2aa  mov     [rsp+48h+var_20], rbp
0x18004c2af  xor     r9d, r9d
0x18004c2b2  mov     [rsp+48h+var_28], rsi
0x18004c2b7  mov     r8d, eax
0x18004c2ba  lea     ecx, [rdx+3]
0x18004c2bd  call    cs:__imp_SHTaskPoolQueueTask
0x18004c2c3  mov     edi, eax
0x18004c2c5  test    rsi, rsi
0x18004c2c8  jz      short loc_18004C2D9
0x18004c2ca  mov     rdx, [rsi]
0x18004c2cd  mov     rcx, rsi
0x18004c2d0  mov     rax, [rdx+10h]
0x18004c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2d9  mov     rcx, [rsp+48h+arg_8]
0x18004c2de  shr     edi, 1Fh
0x18004c2e1  xor     dil, 1
0x18004c2e5  test    rcx, rcx
0x18004c2e8  jz      short loc_18004C2F6
0x18004c2ea  mov     rax, [rcx]
0x18004c2ed  mov     rax, [rax+10h]
0x18004c2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f6  test    rbx, rbx
0x18004c2f9  jz      short loc_18004C30A
0x18004c2fb  mov     rax, [rbx]
0x18004c2fe  mov     rcx, rbx
0x18004c301  mov     rax, [rax+10h]
0x18004c305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c30a  test    dil, dil
0x18004c30d  jnz     short loc_18004C32A
0x18004c30f  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18004c314  mov     rax, [rbx]
0x18004c317  mov     rcx, rbx
0x18004c31a  mov     rax, [rax+18h]
0x18004c31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c323  mov     ebp, eax
0x18004c325  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18004c32a  mov     rbx, [rsp+48h+arg_0]
0x18004c32f  mov     eax, ebp
0x18004c331  add     rsp, 30h
0x18004c335  pop     rdi
0x18004c336  pop     rsi
0x18004c337  pop     rbp
0x18004c338  retn
```
