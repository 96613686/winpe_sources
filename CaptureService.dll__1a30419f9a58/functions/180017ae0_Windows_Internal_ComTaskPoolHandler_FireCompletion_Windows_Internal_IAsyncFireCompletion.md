# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180017ae0`
- end: `0x180017be0`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010130`

## callees

- `0x18000c1c4`
- `0x18000fa38`
- `0x180010f1c`
- `0x180011f98`
- `0x1800122c0`
- `0x180013b80`
- `0x180017ae0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017b46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017b46`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017b61`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017b61`

## pseudocode

```c
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
0x180017ae0  mov     [rsp+arg_0], rbx
0x180017ae5  push    rbp
0x180017ae6  push    rsi
0x180017ae7  push    rdi
0x180017ae8  sub     rsp, 30h
0x180017aec  mov     rbx, rcx
0x180017aef  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x180017af4  cmp     eax, 4
0x180017af7  jle     loc_180017BB6
0x180017afd  xor     ebp, ebp
0x180017aff  mov     [rsp+48h+arg_8], rbx
0x180017b04  lea     rcx, [rsp+48h+arg_8]
0x180017b09  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180017b0e  mov     [rsp+48h+arg_8], rbx
0x180017b13  lea     rcx, [rsp+48h+arg_8]
0x180017b18  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180017b1d  lea     rdx, [rsp+48h+arg_8]
0x180017b22  lea     rcx, [rsp+48h+arg_10]
0x180017b27  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x180017b2c  mov     rsi, [rax]
0x180017b2f  mov     [rax], rbp
0x180017b32  mov     rcx, [rsp+48h+arg_10]
0x180017b37  test    rcx, rcx
0x180017b3a  jz      short loc_180017B46
0x180017b3c  mov     [rsp+48h+arg_10], rbp
0x180017b41  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180017b46  call    cs:__imp_GetCurrentThreadId
0x180017b4c  mov     [rsp+48h+var_20], rbp
0x180017b51  mov     [rsp+48h+var_28], rsi
0x180017b56  xor     r9d, r9d
0x180017b59  mov     r8d, eax
0x180017b5c  xor     edx, edx
0x180017b5e  lea     ecx, [rdx+3]
0x180017b61  call    cs:__imp_SHTaskPoolQueueTask
0x180017b67  mov     edi, eax
0x180017b69  test    rsi, rsi
0x180017b6c  jz      short loc_180017B7E
0x180017b6e  mov     rdx, [rsi]
0x180017b71  mov     rcx, rsi
0x180017b74  mov     rax, [rdx+10h]
0x180017b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b7d  nop
0x180017b7e  shr     edi, 1Fh
0x180017b81  xor     dil, 1
0x180017b85  mov     rcx, [rsp+48h+arg_8]
0x180017b8a  test    rcx, rcx
0x180017b8d  jz      short loc_180017B9C
0x180017b8f  mov     rax, [rcx]
0x180017b92  mov     rax, [rax+10h]
0x180017b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b9b  nop
0x180017b9c  test    rbx, rbx
0x180017b9f  jz      short loc_180017BB1
0x180017ba1  mov     rax, [rbx]
0x180017ba4  mov     rcx, rbx
0x180017ba7  mov     rax, [rax+10h]
0x180017bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb0  nop
0x180017bb1  test    dil, dil
0x180017bb4  jnz     short loc_180017BD1
0x180017bb6  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x180017bbb  mov     rax, [rbx]
0x180017bbe  mov     rcx, rbx
0x180017bc1  mov     rax, [rax+18h]
0x180017bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bca  mov     ebp, eax
0x180017bcc  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x180017bd1  mov     eax, ebp
0x180017bd3  mov     rbx, [rsp+48h+arg_0]
0x180017bd8  add     rsp, 30h
0x180017bdc  pop     rdi
0x180017bdd  pop     rsi
0x180017bde  pop     rbp
0x180017bdf  retn
```
