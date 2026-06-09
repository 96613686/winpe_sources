# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180028420`
- end: `0x180028572`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025750`

## callees

- `0x1800061e4`
- `0x180023608`
- `0x180026bc0`
- `0x180027600`
- `0x180028420`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800284b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800284b8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800284d3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800284d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  __int64 v2; // rbx
  unsigned int v3; // ebp
  __int64 *v4; // rax
  __int64 v5; // r14
  DWORD CurrentThreadId; // eax
  int v7; // esi
  bool v8; // si
  struct Windows::Internal::IAsyncFireCompletion *v10; // [rsp+68h] [rbp+10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v2 + 8) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(v2 + 12) <= 4 )
    goto LABEL_21;
  v3 = 0;
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  v4 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v11,
                    &v10);
  v5 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v5, 0);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v8 = v7 >= 0;
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v8 )
  {
LABEL_21:
    if ( !*(_BYTE *)(v2 + 8) )
      _dyn_tls_on_demand_init();
    ++*(_DWORD *)(v2 + 12);
    v3 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( !*(_BYTE *)(v2 + 8) )
      _dyn_tls_on_demand_init();
    --*(_DWORD *)(v2 + 12);
  }
  return v3;
}

```

## disassembly

```asm
0x180028420  mov     [rsp+arg_0], rbx
0x180028425  mov     [rsp+arg_18], rbp
0x18002842a  push    rsi
0x18002842b  push    rdi
0x18002842c  push    r12
0x18002842e  push    r13
0x180028430  push    r14
0x180028432  sub     rsp, 30h
0x180028436  mov     rdi, rcx
0x180028439  mov     edx, cs:_tls_index
0x18002843f  mov     rax, gs:58h
0x180028448  mov     rbx, [rax+rdx*8]
0x18002844c  mov     r13d, 8
0x180028452  cmp     byte ptr [rbx+r13], 0
0x180028457  jnz     short loc_18002845E
0x180028459  call    __dyn_tls_on_demand_init
0x18002845e  mov     r12d, 0Ch
0x180028464  cmp     dword ptr [r12+rbx], 4
0x180028469  jle     loc_180028528
0x18002846f  xor     ebp, ebp
0x180028471  mov     [rsp+58h+arg_8], rdi
0x180028476  lea     rcx, [rsp+58h+arg_8]
0x18002847b  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180028480  mov     [rsp+58h+arg_8], rdi
0x180028485  lea     rcx, [rsp+58h+arg_8]
0x18002848a  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18002848f  lea     rdx, [rsp+58h+arg_8]
0x180028494  lea     rcx, [rsp+58h+arg_10]
0x180028499  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18002849e  mov     r14, [rax]
0x1800284a1  mov     [rax], rbp
0x1800284a4  mov     rcx, [rsp+58h+arg_10]
0x1800284a9  test    rcx, rcx
0x1800284ac  jz      short loc_1800284B8
0x1800284ae  mov     [rsp+58h+arg_10], rbp
0x1800284b3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800284b8  call    cs:__imp_GetCurrentThreadId
0x1800284be  mov     [rsp+58h+var_30], rbp
0x1800284c3  mov     [rsp+58h+var_38], r14
0x1800284c8  xor     r9d, r9d
0x1800284cb  mov     r8d, eax
0x1800284ce  xor     edx, edx
0x1800284d0  lea     ecx, [rdx+3]
0x1800284d3  call    cs:__imp_SHTaskPoolQueueTask
0x1800284d9  mov     esi, eax
0x1800284db  test    r14, r14
0x1800284de  jz      short loc_1800284F0
0x1800284e0  mov     rax, [r14]
0x1800284e3  mov     rcx, r14
0x1800284e6  mov     rax, [rax+10h]
0x1800284ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284ef  nop
0x1800284f0  shr     esi, 1Fh
0x1800284f3  xor     sil, 1
0x1800284f7  mov     rcx, [rsp+58h+arg_8]
0x1800284fc  test    rcx, rcx
0x1800284ff  jz      short loc_18002850E
0x180028501  mov     rax, [rcx]
0x180028504  mov     rax, [rax+10h]
0x180028508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002850d  nop
0x18002850e  test    rdi, rdi
0x180028511  jz      short loc_180028523
0x180028513  mov     rax, [rdi]
0x180028516  mov     rcx, rdi
0x180028519  mov     rax, [rax+10h]
0x18002851d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028522  nop
0x180028523  test    sil, sil
0x180028526  jnz     short loc_180028559
0x180028528  cmp     byte ptr [rbx+r13], 0
0x18002852d  jnz     short loc_180028534
0x18002852f  call    __dyn_tls_on_demand_init
0x180028534  inc     dword ptr [r12+rbx]
0x180028538  mov     rax, [rdi]
0x18002853b  mov     rcx, rdi
0x18002853e  mov     rax, [rax+18h]
0x180028542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028547  mov     ebp, eax
0x180028549  cmp     byte ptr [rbx+r13], 0
0x18002854e  jnz     short loc_180028555
0x180028550  call    __dyn_tls_on_demand_init
0x180028555  dec     dword ptr [r12+rbx]
0x180028559  mov     eax, ebp
0x18002855b  mov     rbx, [rsp+58h+arg_0]
0x180028560  mov     rbp, [rsp+58h+arg_18]
0x180028565  add     rsp, 30h
0x180028569  pop     r14
0x18002856b  pop     r13
0x18002856d  pop     r12
0x18002856f  pop     rdi
0x180028570  pop     rsi
0x180028571  retn
```
