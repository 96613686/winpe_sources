# Windows::Internal::ComTaskPool::QueueTask<_lambda_17fcd30ddbc55d1a344c922581f42f74_>(Windows::Internal::TaskApartment,_lambda_17fcd30ddbc55d1a344c922581f42f74_ &&)

- ea: `0x18001ca54`
- end: `0x18001cb02`
- name: `??$QueueTask@V_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d2e0`

## callees

- `0x1800175c0`
- `0x18001c66c`
- `0x18001ca54`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001caa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001caa5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001cac4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001cac4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_17fcd30ddbc55d1a344c922581f42f74_>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // esi
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h]

  v2 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_17fcd30ddbc55d1a344c922581f42f74_>,_lambda_17fcd30ddbc55d1a344c922581f42f74_>(
         &v8,
         a2);
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
0x18001ca54  mov     rax, rsp
0x18001ca57  mov     [rax+8], rbx
0x18001ca5b  mov     [rax+10h], rsi
0x18001ca5f  push    rdi
0x18001ca60  sub     rsp, 40h
0x18001ca64  mov     dword ptr [rax-18h], 0
0x18001ca6b  lea     rcx, [rax+18h]
0x18001ca6f  call    ??$Make@V?$CTaskWrapper@V_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@ComTaskPool@Internal@Windows@@V_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_17fcd30ddbc55d1a344c922581f42f74_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_17fcd30ddbc55d1a344c922581f42f74_>,_lambda_17fcd30ddbc55d1a344c922581f42f74_>(_lambda_17fcd30ddbc55d1a344c922581f42f74_ &&)
0x18001ca74  nop
0x18001ca75  mov     rbx, [rax]
0x18001ca78  mov     [rsp+48h+arg_18], rbx
0x18001ca7d  mov     qword ptr [rax], 0
0x18001ca84  mov     edi, 1
0x18001ca89  mov     [rsp+48h+var_18], edi
0x18001ca8d  mov     rcx, [rsp+48h+arg_10]
0x18001ca92  test    rcx, rcx
0x18001ca95  jz      short loc_18001CAA5
0x18001ca97  mov     [rsp+48h+arg_10], 0
0x18001caa0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x18001caa5  call    cs:__imp_GetCurrentThreadId
0x18001caab  mov     [rsp+48h+var_20], 0
0x18001cab4  mov     [rsp+48h+var_28], rbx
0x18001cab9  xor     r9d, r9d
0x18001cabc  mov     r8d, eax
0x18001cabf  xor     edx, edx
0x18001cac1  lea     ecx, [rdx+3]
0x18001cac4  call    cs:__imp_SHTaskPoolQueueTask
0x18001caca  mov     esi, eax
0x18001cacc  and     edi, 0FFFFFFFEh
0x18001cacf  mov     [rsp+48h+var_18], edi
0x18001cad3  test    rbx, rbx
0x18001cad6  jz      short loc_18001CAF0
0x18001cad8  mov     [rsp+48h+arg_18], 0
0x18001cae1  mov     rdx, [rbx]
0x18001cae4  mov     rcx, rbx
0x18001cae7  mov     rax, [rdx+10h]
0x18001caeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caf0  mov     eax, esi
0x18001caf2  mov     rbx, [rsp+48h+arg_0]
0x18001caf7  mov     rsi, [rsp+48h+arg_8]
0x18001cafc  add     rsp, 40h
0x18001cb00  pop     rdi
0x18001cb01  retn
```
