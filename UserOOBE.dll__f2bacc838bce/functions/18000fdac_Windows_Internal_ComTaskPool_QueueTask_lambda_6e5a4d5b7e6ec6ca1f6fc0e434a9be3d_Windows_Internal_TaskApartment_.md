# Windows::Internal::ComTaskPool::QueueTask<_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>(Windows::Internal::TaskApartment,_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_ &&)

- ea: `0x18000fdac`
- end: `0x18000fe2b`
- name: `??$QueueTask@V_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014604`

## callees

- `0x18000d400`
- `0x18000f1d8`
- `0x18000fdac`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000fe01`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000fe01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fde2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fde2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask<_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  __int64 v2; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v4; // edi
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>,_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>(&v6);
  v1 = *v0;
  *v0 = 0;
  v2 = v6;
  if ( v6 )
  {
    v6 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v2);
  }
  CurrentThreadId = GetCurrentThreadId();
  v4 = SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0, v1, 0);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v4;
}

```

## disassembly

```asm
0x18000fdac  mov     [rsp+arg_0], rbx
0x18000fdb1  push    rdi
0x18000fdb2  sub     rsp, 30h
0x18000fdb6  lea     rcx, [rsp+38h+arg_10]
0x18000fdbb  call    ??$Make@V?$CTaskWrapper@V_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@ComTaskPool@Internal@Windows@@V_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>,_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_>(_lambda_6e5a4d5b7e6ec6ca1f6fc0e434a9be3d_ &&)
0x18000fdc0  mov     rbx, [rax]
0x18000fdc3  mov     qword ptr [rax], 0
0x18000fdca  mov     rcx, [rsp+38h+arg_10]
0x18000fdcf  test    rcx, rcx
0x18000fdd2  jz      short loc_18000FDE2
0x18000fdd4  mov     [rsp+38h+arg_10], 0
0x18000fddd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x18000fde2  call    cs:__imp_GetCurrentThreadId
0x18000fde8  mov     [rsp+38h+var_10], 0
0x18000fdf1  mov     [rsp+38h+var_18], rbx
0x18000fdf6  xor     r9d, r9d
0x18000fdf9  mov     r8d, eax
0x18000fdfc  xor     edx, edx
0x18000fdfe  lea     ecx, [rdx+1]
0x18000fe01  call    cs:__imp_SHTaskPoolQueueTask
0x18000fe07  mov     edi, eax
0x18000fe09  test    rbx, rbx
0x18000fe0c  jz      short loc_18000FE1E
0x18000fe0e  mov     rdx, [rbx]
0x18000fe11  mov     rcx, rbx
0x18000fe14  mov     rax, [rdx+10h]
0x18000fe18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe1d  nop
0x18000fe1e  mov     eax, edi
0x18000fe20  mov     rbx, [rsp+38h+arg_0]
0x18000fe25  add     rsp, 30h
0x18000fe29  pop     rdi
0x18000fe2a  retn
```
