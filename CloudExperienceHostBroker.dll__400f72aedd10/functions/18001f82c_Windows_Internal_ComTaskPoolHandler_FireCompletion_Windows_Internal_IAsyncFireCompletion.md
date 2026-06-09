# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18001f82c`
- end: `0x18001f92c`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e340`

## callees

- `0x180016f70`
- `0x18001c924`
- `0x18001df74`
- `0x18001e4fc`
- `0x18001eb94`
- `0x18001ebd4`
- `0x18001f82c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f892`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f8ad`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001f8ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v2 = 0;
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v3 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
         &v10,
         &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
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
0x18001f82c  mov     [rsp+arg_0], rbx
0x18001f831  push    rbp
0x18001f832  push    rsi
0x18001f833  push    rdi
0x18001f834  sub     rsp, 30h
0x18001f838  mov     rbx, rcx
0x18001f83b  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18001f840  cmp     eax, 4
0x18001f843  jle     loc_18001F902
0x18001f849  xor     ebp, ebp
0x18001f84b  mov     [rsp+48h+arg_8], rbx
0x18001f850  lea     rcx, [rsp+48h+arg_8]
0x18001f855  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18001f85a  mov     [rsp+48h+arg_8], rbx
0x18001f85f  lea     rcx, [rsp+48h+arg_8]
0x18001f864  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18001f869  lea     rdx, [rsp+48h+arg_8]
0x18001f86e  lea     rcx, [rsp+48h+arg_10]
0x18001f873  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18001f878  mov     rsi, [rax]
0x18001f87b  mov     [rax], rbp
0x18001f87e  mov     rcx, [rsp+48h+arg_10]
0x18001f883  test    rcx, rcx
0x18001f886  jz      short loc_18001F892
0x18001f888  mov     [rsp+48h+arg_10], rbp
0x18001f88d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001f892  call    cs:__imp_GetCurrentThreadId
0x18001f898  mov     [rsp+48h+var_20], rbp
0x18001f89d  mov     [rsp+48h+var_28], rsi
0x18001f8a2  xor     r9d, r9d
0x18001f8a5  mov     r8d, eax
0x18001f8a8  xor     edx, edx
0x18001f8aa  lea     ecx, [rdx+3]
0x18001f8ad  call    cs:__imp_SHTaskPoolQueueTask
0x18001f8b3  mov     edi, eax
0x18001f8b5  test    rsi, rsi
0x18001f8b8  jz      short loc_18001F8CA
0x18001f8ba  mov     rdx, [rsi]
0x18001f8bd  mov     rcx, rsi
0x18001f8c0  mov     rax, [rdx+10h]
0x18001f8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8c9  nop
0x18001f8ca  shr     edi, 1Fh
0x18001f8cd  xor     dil, 1
0x18001f8d1  mov     rcx, [rsp+48h+arg_8]
0x18001f8d6  test    rcx, rcx
0x18001f8d9  jz      short loc_18001F8E8
0x18001f8db  mov     rax, [rcx]
0x18001f8de  mov     rax, [rax+10h]
0x18001f8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8e7  nop
0x18001f8e8  test    rbx, rbx
0x18001f8eb  jz      short loc_18001F8FD
0x18001f8ed  mov     rax, [rbx]
0x18001f8f0  mov     rcx, rbx
0x18001f8f3  mov     rax, [rax+10h]
0x18001f8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8fc  nop
0x18001f8fd  test    dil, dil
0x18001f900  jnz     short loc_18001F91D
0x18001f902  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18001f907  mov     rax, [rbx]
0x18001f90a  mov     rcx, rbx
0x18001f90d  mov     rax, [rax+18h]
0x18001f911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f916  mov     ebp, eax
0x18001f918  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18001f91d  mov     eax, ebp
0x18001f91f  mov     rbx, [rsp+48h+arg_0]
0x18001f924  add     rsp, 30h
0x18001f928  pop     rdi
0x18001f929  pop     rsi
0x18001f92a  pop     rbp
0x18001f92b  retn
```
