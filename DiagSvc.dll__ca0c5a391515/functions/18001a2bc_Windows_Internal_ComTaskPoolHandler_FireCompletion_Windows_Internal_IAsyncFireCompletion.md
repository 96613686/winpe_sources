# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18001a2bc`
- end: `0x18001a3bc`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017a70`

## callees

- `0x1800056d8`
- `0x18000f850`
- `0x1800141a0`
- `0x180016cfc`
- `0x180017de0`
- `0x180018704`
- `0x18001a2bc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a322`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a322`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001a33d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001a33d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rcx
  DWORD CurrentThreadId; // eax
  int v7; // edi
  bool v8; // di
  struct Windows::Internal::IAsyncFireCompletion *v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  if ( (int)Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  v2 = 0;
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  v3 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
         &v11,
         &v10);
  v4 = *v3;
  *v3 = 0;
  v5 = v11;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v8 = v7 >= 0;
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v8 )
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
0x18001a2bc  mov     [rsp+arg_0], rbx
0x18001a2c1  push    rbp
0x18001a2c2  push    rsi
0x18001a2c3  push    rdi
0x18001a2c4  sub     rsp, 30h
0x18001a2c8  mov     rbx, rcx
0x18001a2cb  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18001a2d0  cmp     eax, 4
0x18001a2d3  jle     loc_18001A392
0x18001a2d9  xor     ebp, ebp
0x18001a2db  mov     [rsp+48h+arg_8], rbx
0x18001a2e0  lea     rcx, [rsp+48h+arg_8]
0x18001a2e5  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001a2ea  mov     [rsp+48h+arg_8], rbx
0x18001a2ef  lea     rcx, [rsp+48h+arg_8]
0x18001a2f4  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001a2f9  lea     rdx, [rsp+48h+arg_8]
0x18001a2fe  lea     rcx, [rsp+48h+arg_10]
0x18001a303  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18001a308  mov     rsi, [rax]
0x18001a30b  mov     [rax], rbp
0x18001a30e  mov     rcx, [rsp+48h+arg_10]
0x18001a313  test    rcx, rcx
0x18001a316  jz      short loc_18001A322
0x18001a318  mov     [rsp+48h+arg_10], rbp
0x18001a31d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001a322  call    cs:__imp_GetCurrentThreadId
0x18001a328  mov     [rsp+48h+var_20], rbp
0x18001a32d  mov     [rsp+48h+var_28], rsi
0x18001a332  xor     r9d, r9d
0x18001a335  mov     r8d, eax
0x18001a338  xor     edx, edx
0x18001a33a  lea     ecx, [rdx+3]
0x18001a33d  call    cs:__imp_SHTaskPoolQueueTask
0x18001a343  mov     edi, eax
0x18001a345  test    rsi, rsi
0x18001a348  jz      short loc_18001A35A
0x18001a34a  mov     rdx, [rsi]
0x18001a34d  mov     rcx, rsi
0x18001a350  mov     rax, [rdx+10h]
0x18001a354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a359  nop
0x18001a35a  shr     edi, 1Fh
0x18001a35d  xor     dil, 1
0x18001a361  mov     rcx, [rsp+48h+arg_8]
0x18001a366  test    rcx, rcx
0x18001a369  jz      short loc_18001A378
0x18001a36b  mov     rax, [rcx]
0x18001a36e  mov     rax, [rax+10h]
0x18001a372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a377  nop
0x18001a378  test    rbx, rbx
0x18001a37b  jz      short loc_18001A38D
0x18001a37d  mov     rax, [rbx]
0x18001a380  mov     rcx, rbx
0x18001a383  mov     rax, [rax+10h]
0x18001a387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a38c  nop
0x18001a38d  test    dil, dil
0x18001a390  jnz     short loc_18001A3AD
0x18001a392  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18001a397  mov     rax, [rbx]
0x18001a39a  mov     rcx, rbx
0x18001a39d  mov     rax, [rax+18h]
0x18001a3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3a6  mov     ebp, eax
0x18001a3a8  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18001a3ad  mov     eax, ebp
0x18001a3af  mov     rbx, [rsp+48h+arg_0]
0x18001a3b4  add     rsp, 30h
0x18001a3b8  pop     rdi
0x18001a3b9  pop     rsi
0x18001a3ba  pop     rbp
0x18001a3bb  retn
```
