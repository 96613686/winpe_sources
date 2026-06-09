# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18001b2d8`
- end: `0x18001b3d8`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800161a0`

## callees

- `0x180012480`
- `0x180015afc`
- `0x1800169f8`
- `0x180017be0`
- `0x180018170`
- `0x180019a50`
- `0x18001b2d8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b33e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b33e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b359`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b359`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001b2d8  mov     [rsp+arg_0], rbx
0x18001b2dd  push    rbp
0x18001b2de  push    rsi
0x18001b2df  push    rdi
0x18001b2e0  sub     rsp, 30h
0x18001b2e4  mov     rbx, rcx
0x18001b2e7  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18001b2ec  cmp     eax, 4
0x18001b2ef  jle     loc_18001B3AE
0x18001b2f5  xor     ebp, ebp
0x18001b2f7  mov     [rsp+48h+arg_8], rbx
0x18001b2fc  lea     rcx, [rsp+48h+arg_8]
0x18001b301  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001b306  mov     [rsp+48h+arg_8], rbx
0x18001b30b  lea     rcx, [rsp+48h+arg_8]
0x18001b310  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001b315  lea     rdx, [rsp+48h+arg_8]
0x18001b31a  lea     rcx, [rsp+48h+arg_10]
0x18001b31f  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18001b324  mov     rsi, [rax]
0x18001b327  mov     [rax], rbp
0x18001b32a  mov     rcx, [rsp+48h+arg_10]
0x18001b32f  test    rcx, rcx
0x18001b332  jz      short loc_18001B33E
0x18001b334  mov     [rsp+48h+arg_10], rbp
0x18001b339  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001b33e  call    cs:__imp_GetCurrentThreadId
0x18001b344  mov     [rsp+48h+var_20], rbp
0x18001b349  mov     [rsp+48h+var_28], rsi
0x18001b34e  xor     r9d, r9d
0x18001b351  mov     r8d, eax
0x18001b354  xor     edx, edx
0x18001b356  lea     ecx, [rdx+3]
0x18001b359  call    cs:__imp_SHTaskPoolQueueTask
0x18001b35f  mov     edi, eax
0x18001b361  test    rsi, rsi
0x18001b364  jz      short loc_18001B376
0x18001b366  mov     rdx, [rsi]
0x18001b369  mov     rcx, rsi
0x18001b36c  mov     rax, [rdx+10h]
0x18001b370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b375  nop
0x18001b376  shr     edi, 1Fh
0x18001b379  xor     dil, 1
0x18001b37d  mov     rcx, [rsp+48h+arg_8]
0x18001b382  test    rcx, rcx
0x18001b385  jz      short loc_18001B394
0x18001b387  mov     rax, [rcx]
0x18001b38a  mov     rax, [rax+10h]
0x18001b38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b393  nop
0x18001b394  test    rbx, rbx
0x18001b397  jz      short loc_18001B3A9
0x18001b399  mov     rax, [rbx]
0x18001b39c  mov     rcx, rbx
0x18001b39f  mov     rax, [rax+10h]
0x18001b3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3a8  nop
0x18001b3a9  test    dil, dil
0x18001b3ac  jnz     short loc_18001B3C9
0x18001b3ae  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18001b3b3  mov     rax, [rbx]
0x18001b3b6  mov     rcx, rbx
0x18001b3b9  mov     rax, [rax+18h]
0x18001b3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3c2  mov     ebp, eax
0x18001b3c4  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18001b3c9  mov     eax, ebp
0x18001b3cb  mov     rbx, [rsp+48h+arg_0]
0x18001b3d0  add     rsp, 30h
0x18001b3d4  pop     rdi
0x18001b3d5  pop     rsi
0x18001b3d6  pop     rbp
0x18001b3d7  retn
```
