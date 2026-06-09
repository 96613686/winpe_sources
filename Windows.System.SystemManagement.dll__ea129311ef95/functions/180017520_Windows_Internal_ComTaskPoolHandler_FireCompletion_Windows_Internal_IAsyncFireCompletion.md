# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180017520`
- end: `0x180017620`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800155c0`

## callees

- `0x18000cc80`
- `0x1800134f0`
- `0x180015178`
- `0x1800158ec`
- `0x180015f94`
- `0x180016054`
- `0x180017520`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017586`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800175a1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800175a1`

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
0x180017520  mov     [rsp+arg_0], rbx
0x180017525  push    rbp
0x180017526  push    rsi
0x180017527  push    rdi
0x180017528  sub     rsp, 30h
0x18001752c  mov     rbx, rcx
0x18001752f  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x180017534  cmp     eax, 4
0x180017537  jle     loc_1800175F6
0x18001753d  xor     ebp, ebp
0x18001753f  mov     [rsp+48h+arg_8], rbx
0x180017544  lea     rcx, [rsp+48h+arg_8]
0x180017549  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001754e  mov     [rsp+48h+arg_8], rbx
0x180017553  lea     rcx, [rsp+48h+arg_8]
0x180017558  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001755d  lea     rdx, [rsp+48h+arg_8]
0x180017562  lea     rcx, [rsp+48h+arg_10]
0x180017567  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18001756c  mov     rsi, [rax]
0x18001756f  mov     [rax], rbp
0x180017572  mov     rcx, [rsp+48h+arg_10]
0x180017577  test    rcx, rcx
0x18001757a  jz      short loc_180017586
0x18001757c  mov     [rsp+48h+arg_10], rbp
0x180017581  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180017586  call    cs:__imp_GetCurrentThreadId
0x18001758c  mov     [rsp+48h+var_20], rbp
0x180017591  mov     [rsp+48h+var_28], rsi
0x180017596  xor     r9d, r9d
0x180017599  mov     r8d, eax
0x18001759c  xor     edx, edx
0x18001759e  lea     ecx, [rdx+3]
0x1800175a1  call    cs:__imp_SHTaskPoolQueueTask
0x1800175a7  mov     edi, eax
0x1800175a9  test    rsi, rsi
0x1800175ac  jz      short loc_1800175BE
0x1800175ae  mov     rdx, [rsi]
0x1800175b1  mov     rcx, rsi
0x1800175b4  mov     rax, [rdx+10h]
0x1800175b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175bd  nop
0x1800175be  shr     edi, 1Fh
0x1800175c1  xor     dil, 1
0x1800175c5  mov     rcx, [rsp+48h+arg_8]
0x1800175ca  test    rcx, rcx
0x1800175cd  jz      short loc_1800175DC
0x1800175cf  mov     rax, [rcx]
0x1800175d2  mov     rax, [rax+10h]
0x1800175d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175db  nop
0x1800175dc  test    rbx, rbx
0x1800175df  jz      short loc_1800175F1
0x1800175e1  mov     rax, [rbx]
0x1800175e4  mov     rcx, rbx
0x1800175e7  mov     rax, [rax+10h]
0x1800175eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175f0  nop
0x1800175f1  test    dil, dil
0x1800175f4  jnz     short loc_180017611
0x1800175f6  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x1800175fb  mov     rax, [rbx]
0x1800175fe  mov     rcx, rbx
0x180017601  mov     rax, [rax+18h]
0x180017605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001760a  mov     ebp, eax
0x18001760c  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x180017611  mov     eax, ebp
0x180017613  mov     rbx, [rsp+48h+arg_0]
0x180017618  add     rsp, 30h
0x18001761c  pop     rdi
0x18001761d  pop     rsi
0x18001761e  pop     rbp
0x18001761f  retn
```
