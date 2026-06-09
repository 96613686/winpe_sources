# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180019c00`
- end: `0x180019d00`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002def0`

## callees

- `0x180011a80`
- `0x180016eec`
- `0x18001770c`
- `0x180018e78`
- `0x180018fb0`
- `0x180018ff0`
- `0x180019c00`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c66`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180019c81`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180019c81`

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
0x180019c00  mov     [rsp+arg_0], rbx
0x180019c05  push    rbp
0x180019c06  push    rsi
0x180019c07  push    rdi
0x180019c08  sub     rsp, 30h
0x180019c0c  mov     rbx, rcx
0x180019c0f  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x180019c14  cmp     eax, 4
0x180019c17  jle     loc_180019CD6
0x180019c1d  xor     ebp, ebp
0x180019c1f  mov     [rsp+48h+arg_8], rbx
0x180019c24  lea     rcx, [rsp+48h+arg_8]
0x180019c29  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180019c2e  mov     [rsp+48h+arg_8], rbx
0x180019c33  lea     rcx, [rsp+48h+arg_8]
0x180019c38  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180019c3d  lea     rdx, [rsp+48h+arg_8]
0x180019c42  lea     rcx, [rsp+48h+arg_10]
0x180019c47  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x180019c4c  mov     rsi, [rax]
0x180019c4f  mov     [rax], rbp
0x180019c52  mov     rcx, [rsp+48h+arg_10]
0x180019c57  test    rcx, rcx
0x180019c5a  jz      short loc_180019C66
0x180019c5c  mov     [rsp+48h+arg_10], rbp
0x180019c61  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180019c66  call    cs:__imp_GetCurrentThreadId
0x180019c6c  mov     [rsp+48h+var_20], rbp
0x180019c71  mov     [rsp+48h+var_28], rsi
0x180019c76  xor     r9d, r9d
0x180019c79  mov     r8d, eax
0x180019c7c  xor     edx, edx
0x180019c7e  lea     ecx, [rdx+3]
0x180019c81  call    cs:__imp_SHTaskPoolQueueTask
0x180019c87  mov     edi, eax
0x180019c89  test    rsi, rsi
0x180019c8c  jz      short loc_180019C9E
0x180019c8e  mov     rdx, [rsi]
0x180019c91  mov     rcx, rsi
0x180019c94  mov     rax, [rdx+10h]
0x180019c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c9d  nop
0x180019c9e  shr     edi, 1Fh
0x180019ca1  xor     dil, 1
0x180019ca5  mov     rcx, [rsp+48h+arg_8]
0x180019caa  test    rcx, rcx
0x180019cad  jz      short loc_180019CBC
0x180019caf  mov     rax, [rcx]
0x180019cb2  mov     rax, [rax+10h]
0x180019cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cbb  nop
0x180019cbc  test    rbx, rbx
0x180019cbf  jz      short loc_180019CD1
0x180019cc1  mov     rax, [rbx]
0x180019cc4  mov     rcx, rbx
0x180019cc7  mov     rax, [rax+10h]
0x180019ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cd0  nop
0x180019cd1  test    dil, dil
0x180019cd4  jnz     short loc_180019CF1
0x180019cd6  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x180019cdb  mov     rax, [rbx]
0x180019cde  mov     rcx, rbx
0x180019ce1  mov     rax, [rax+18h]
0x180019ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cea  mov     ebp, eax
0x180019cec  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x180019cf1  mov     eax, ebp
0x180019cf3  mov     rbx, [rsp+48h+arg_0]
0x180019cf8  add     rsp, 30h
0x180019cfc  pop     rdi
0x180019cfd  pop     rsi
0x180019cfe  pop     rbp
0x180019cff  retn
```
