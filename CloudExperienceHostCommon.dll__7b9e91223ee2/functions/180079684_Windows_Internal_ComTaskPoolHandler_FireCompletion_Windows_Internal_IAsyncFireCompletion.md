# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180079684`
- end: `0x180079784`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180075f30`

## callees

- `0x180014c54`
- `0x180021170`
- `0x180072ee4`
- `0x180075a30`
- `0x180076384`
- `0x180076c84`
- `0x180079684`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800796ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800796ea`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180079705`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180079705`

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
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(&v9);
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(&v9);
  v3 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
         &v10,
         &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IElevationBrokerContext>::Release();
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
0x180079684  mov     [rsp+arg_0], rbx
0x180079689  push    rbp
0x18007968a  push    rsi
0x18007968b  push    rdi
0x18007968c  sub     rsp, 30h
0x180079690  mov     rbx, rcx
0x180079693  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x180079698  cmp     eax, 4
0x18007969b  jle     loc_18007975A
0x1800796a1  xor     ebp, ebp
0x1800796a3  mov     [rsp+48h+arg_8], rbx
0x1800796a8  lea     rcx, [rsp+48h+arg_8]
0x1800796ad  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x1800796b2  mov     [rsp+48h+arg_8], rbx
0x1800796b7  lea     rcx, [rsp+48h+arg_8]
0x1800796bc  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x1800796c1  lea     rdx, [rsp+48h+arg_8]
0x1800796c6  lea     rcx, [rsp+48h+arg_10]
0x1800796cb  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x1800796d0  mov     rsi, [rax]
0x1800796d3  mov     [rax], rbp
0x1800796d6  mov     rcx, [rsp+48h+arg_10]
0x1800796db  test    rcx, rcx
0x1800796de  jz      short loc_1800796EA
0x1800796e0  mov     [rsp+48h+arg_10], rbp
0x1800796e5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIElevationBrokerContext@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IElevationBrokerContext>::Release(void)
0x1800796ea  call    cs:__imp_GetCurrentThreadId
0x1800796f0  mov     [rsp+48h+var_20], rbp
0x1800796f5  mov     [rsp+48h+var_28], rsi
0x1800796fa  xor     r9d, r9d
0x1800796fd  mov     r8d, eax
0x180079700  xor     edx, edx
0x180079702  lea     ecx, [rdx+3]
0x180079705  call    cs:__imp_SHTaskPoolQueueTask
0x18007970b  mov     edi, eax
0x18007970d  test    rsi, rsi
0x180079710  jz      short loc_180079722
0x180079712  mov     rdx, [rsi]
0x180079715  mov     rcx, rsi
0x180079718  mov     rax, [rdx+10h]
0x18007971c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079721  nop
0x180079722  shr     edi, 1Fh
0x180079725  xor     dil, 1
0x180079729  mov     rcx, [rsp+48h+arg_8]
0x18007972e  test    rcx, rcx
0x180079731  jz      short loc_180079740
0x180079733  mov     rax, [rcx]
0x180079736  mov     rax, [rax+10h]
0x18007973a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007973f  nop
0x180079740  test    rbx, rbx
0x180079743  jz      short loc_180079755
0x180079745  mov     rax, [rbx]
0x180079748  mov     rcx, rbx
0x18007974b  mov     rax, [rax+10h]
0x18007974f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079754  nop
0x180079755  test    dil, dil
0x180079758  jnz     short loc_180079775
0x18007975a  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18007975f  mov     rax, [rbx]
0x180079762  mov     rcx, rbx
0x180079765  mov     rax, [rax+18h]
0x180079769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007976e  mov     ebp, eax
0x180079770  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x180079775  mov     eax, ebp
0x180079777  mov     rbx, [rsp+48h+arg_0]
0x18007977c  add     rsp, 30h
0x180079780  pop     rdi
0x180079781  pop     rsi
0x180079782  pop     rbp
0x180079783  retn
```
