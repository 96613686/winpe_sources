# Windows::Internal::ComTaskPool::QueueTask<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>(Windows::Internal::TaskApartment,_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_ &&)

- ea: `0x180017c3c`
- end: `0x180017cee`
- name: `??$QueueTask@V_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018170`

## callees

- `0x1800175c0`
- `0x18001792c`
- `0x180017c3c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c91`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017cb0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017cb0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // esi
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h]

  v8 = a2;
  v2 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>,_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>(&v8);
  v3 = *v2;
  v9 = *v2;
  *v2 = 0;
  v4 = v8;
  if ( v8 )
  {
    v8 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(v4);
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v3, 0, 1);
  if ( v3 )
  {
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return v6;
}

```

## disassembly

```asm
0x180017c3c  mov     rax, rsp
0x180017c3f  mov     [rax+8], rbx
0x180017c43  mov     [rax+20h], rsi
0x180017c47  mov     [rax+10h], rdx
0x180017c4b  push    rdi
0x180017c4c  sub     rsp, 40h
0x180017c50  mov     dword ptr [rax-18h], 0
0x180017c57  lea     rcx, [rax+10h]
0x180017c5b  call    ??$Make@V?$CTaskWrapper@V_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@ComTaskPool@Internal@Windows@@V_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>,_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>(_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_ &&)
0x180017c60  nop
0x180017c61  mov     rbx, [rax]
0x180017c64  mov     [rsp+48h+arg_10], rbx
0x180017c69  mov     qword ptr [rax], 0
0x180017c70  mov     edi, 1
0x180017c75  mov     [rsp+48h+var_18], edi
0x180017c79  mov     rcx, [rsp+48h+arg_8]
0x180017c7e  test    rcx, rcx
0x180017c81  jz      short loc_180017C91
0x180017c83  mov     [rsp+48h+arg_8], 0
0x180017c8c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x180017c91  call    cs:__imp_GetCurrentThreadId
0x180017c97  mov     [rsp+48h+var_20], 0
0x180017ca0  mov     [rsp+48h+var_28], rbx
0x180017ca5  xor     r9d, r9d
0x180017ca8  mov     r8d, eax
0x180017cab  xor     edx, edx
0x180017cad  lea     ecx, [rdx+3]
0x180017cb0  call    cs:__imp_SHTaskPoolQueueTask
0x180017cb6  mov     esi, eax
0x180017cb8  and     edi, 0FFFFFFFEh
0x180017cbb  mov     [rsp+48h+var_18], edi
0x180017cbf  test    rbx, rbx
0x180017cc2  jz      short loc_180017CDC
0x180017cc4  mov     [rsp+48h+arg_10], 0
0x180017ccd  mov     rdx, [rbx]
0x180017cd0  mov     rcx, rbx
0x180017cd3  mov     rax, [rdx+10h]
0x180017cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cdc  mov     eax, esi
0x180017cde  mov     rbx, [rsp+48h+arg_0]
0x180017ce3  mov     rsi, [rsp+48h+arg_18]
0x180017ce8  add     rsp, 40h
0x180017cec  pop     rdi
0x180017ced  retn
```
