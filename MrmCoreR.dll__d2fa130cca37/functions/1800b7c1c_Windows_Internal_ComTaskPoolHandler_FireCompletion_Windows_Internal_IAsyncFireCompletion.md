# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x1800b7c1c`
- end: `0x1800b7d6e`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b6880`

## callees

- `0x180058c84`
- `0x180076230`
- `0x180088a84`
- `0x1800b5bfc`
- `0x1800b7c1c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7cb4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800b7ccf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800b7ccf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  struct Windows::Internal::IAsyncFireCompletion *v1; // rdi
  __int64 v2; // rdx
  __int64 v3; // rbx
  unsigned int v4; // ebp
  __int64 *v5; // rax
  __int64 v6; // r14
  DWORD CurrentThreadId; // eax
  int v8; // esi
  bool v9; // si
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct Windows::Internal::IAsyncFireCompletion *v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v1 = a1;
  v2 = (unsigned int)tls_index;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v3 + 12) )
    ((void (*)(void))_dyn_tls_on_demand_init)();
  if ( *(int *)(v3 + 4) <= 4 )
    goto LABEL_21;
  v4 = 0;
  v13 = v1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v13);
  v13 = v1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v13);
  v5 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v14,
                    &v13);
  v6 = *v5;
  *v5 = 0;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v8 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v9 = v8 >= 0;
  a1 = v13;
  if ( v13 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( !v9 )
  {
LABEL_21:
    if ( !*(_BYTE *)(v3 + 12) )
      _dyn_tls_on_demand_init(a1, v2);
    ++*(_DWORD *)(v3 + 4);
    v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 24LL))(v1);
    if ( !*(_BYTE *)(v3 + 12) )
      _dyn_tls_on_demand_init(v11, v10);
    --*(_DWORD *)(v3 + 4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800b7c1c  mov     [rsp+arg_0], rbx
0x1800b7c21  mov     [rsp+arg_18], rbp
0x1800b7c26  push    rsi
0x1800b7c27  push    rdi
0x1800b7c28  push    r12
0x1800b7c2a  push    r13
0x1800b7c2c  push    r14
0x1800b7c2e  sub     rsp, 30h
0x1800b7c32  mov     rdi, rcx
0x1800b7c35  mov     edx, cs:_tls_index
0x1800b7c3b  mov     rax, gs:58h
0x1800b7c44  mov     rbx, [rax+rdx*8]
0x1800b7c48  mov     r13d, 0Ch
0x1800b7c4e  cmp     byte ptr [rbx+r13], 0
0x1800b7c53  jnz     short loc_1800B7C5A
0x1800b7c55  call    __dyn_tls_on_demand_init
0x1800b7c5a  mov     r12d, 4
0x1800b7c60  cmp     dword ptr [r12+rbx], 4
0x1800b7c65  jle     loc_1800B7D24
0x1800b7c6b  xor     ebp, ebp
0x1800b7c6d  mov     [rsp+58h+arg_8], rdi
0x1800b7c72  lea     rcx, [rsp+58h+arg_8]
0x1800b7c77  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800b7c7c  mov     [rsp+58h+arg_8], rdi
0x1800b7c81  lea     rcx, [rsp+58h+arg_8]
0x1800b7c86  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800b7c8b  lea     rdx, [rsp+58h+arg_8]
0x1800b7c90  lea     rcx, [rsp+58h+arg_10]
0x1800b7c95  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x1800b7c9a  mov     r14, [rax]
0x1800b7c9d  mov     [rax], rbp
0x1800b7ca0  mov     rcx, [rsp+58h+arg_10]
0x1800b7ca5  test    rcx, rcx
0x1800b7ca8  jz      short loc_1800B7CB4
0x1800b7caa  mov     [rsp+58h+arg_10], rbp
0x1800b7caf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800b7cb4  call    cs:__imp_GetCurrentThreadId
0x1800b7cba  mov     [rsp+58h+var_30], rbp
0x1800b7cbf  mov     [rsp+58h+var_38], r14
0x1800b7cc4  xor     r9d, r9d
0x1800b7cc7  mov     r8d, eax
0x1800b7cca  xor     edx, edx
0x1800b7ccc  lea     ecx, [rdx+3]
0x1800b7ccf  call    cs:__imp_SHTaskPoolQueueTask
0x1800b7cd5  mov     esi, eax
0x1800b7cd7  test    r14, r14
0x1800b7cda  jz      short loc_1800B7CEC
0x1800b7cdc  mov     rax, [r14]
0x1800b7cdf  mov     rcx, r14
0x1800b7ce2  mov     rax, [rax+10h]
0x1800b7ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ceb  nop
0x1800b7cec  shr     esi, 1Fh
0x1800b7cef  xor     sil, 1
0x1800b7cf3  mov     rcx, [rsp+58h+arg_8]
0x1800b7cf8  test    rcx, rcx
0x1800b7cfb  jz      short loc_1800B7D0A
0x1800b7cfd  mov     rax, [rcx]
0x1800b7d00  mov     rax, [rax+10h]
0x1800b7d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d09  nop
0x1800b7d0a  test    rdi, rdi
0x1800b7d0d  jz      short loc_1800B7D1F
0x1800b7d0f  mov     rax, [rdi]
0x1800b7d12  mov     rcx, rdi
0x1800b7d15  mov     rax, [rax+10h]
0x1800b7d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d1e  nop
0x1800b7d1f  test    sil, sil
0x1800b7d22  jnz     short loc_1800B7D55
0x1800b7d24  cmp     byte ptr [rbx+r13], 0
0x1800b7d29  jnz     short loc_1800B7D30
0x1800b7d2b  call    __dyn_tls_on_demand_init
0x1800b7d30  inc     dword ptr [r12+rbx]
0x1800b7d34  mov     rax, [rdi]
0x1800b7d37  mov     rcx, rdi
0x1800b7d3a  mov     rax, [rax+18h]
0x1800b7d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d43  mov     ebp, eax
0x1800b7d45  cmp     byte ptr [rbx+r13], 0
0x1800b7d4a  jnz     short loc_1800B7D51
0x1800b7d4c  call    __dyn_tls_on_demand_init
0x1800b7d51  dec     dword ptr [r12+rbx]
0x1800b7d55  mov     eax, ebp
0x1800b7d57  mov     rbx, [rsp+58h+arg_0]
0x1800b7d5c  mov     rbp, [rsp+58h+arg_18]
0x1800b7d61  add     rsp, 30h
0x1800b7d65  pop     r14
0x1800b7d67  pop     r13
0x1800b7d69  pop     r12
0x1800b7d6b  pop     rdi
0x1800b7d6c  pop     rsi
0x1800b7d6d  retn
```
