# Windows::Internal::ComTaskPool::QueueTask<_lambda_62052a4312895de2745c1598789222b9_>(Windows::Internal::TaskApartment,_lambda_62052a4312895de2745c1598789222b9_ &&)

- ea: `0x180017b84`
- end: `0x180017c36`
- name: `??$QueueTask@V_lambda_62052a4312895de2745c1598789222b9_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_62052a4312895de2745c1598789222b9_@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018170`

## callees

- `0x1800175c0`
- `0x18001788c`
- `0x180017b84`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bd9`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017bf8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017bf8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_62052a4312895de2745c1598789222b9_>(
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
  v2 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_62052a4312895de2745c1598789222b9_>,_lambda_62052a4312895de2745c1598789222b9_>(&v8);
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
0x180017b84  mov     rax, rsp
0x180017b87  mov     [rax+8], rbx
0x180017b8b  mov     [rax+20h], rsi
0x180017b8f  mov     [rax+10h], rdx
0x180017b93  push    rdi
0x180017b94  sub     rsp, 40h
0x180017b98  mov     dword ptr [rax-18h], 0
0x180017b9f  lea     rcx, [rax+10h]
0x180017ba3  call    ??$Make@V?$CTaskWrapper@V_lambda_62052a4312895de2745c1598789222b9_@@@ComTaskPool@Internal@Windows@@V_lambda_62052a4312895de2745c1598789222b9_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_62052a4312895de2745c1598789222b9_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_62052a4312895de2745c1598789222b9_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_62052a4312895de2745c1598789222b9_>,_lambda_62052a4312895de2745c1598789222b9_>(_lambda_62052a4312895de2745c1598789222b9_ &&)
0x180017ba8  nop
0x180017ba9  mov     rbx, [rax]
0x180017bac  mov     [rsp+48h+arg_10], rbx
0x180017bb1  mov     qword ptr [rax], 0
0x180017bb8  mov     edi, 1
0x180017bbd  mov     [rsp+48h+var_18], edi
0x180017bc1  mov     rcx, [rsp+48h+arg_8]
0x180017bc6  test    rcx, rcx
0x180017bc9  jz      short loc_180017BD9
0x180017bcb  mov     [rsp+48h+arg_8], 0
0x180017bd4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x180017bd9  call    cs:__imp_GetCurrentThreadId
0x180017bdf  mov     [rsp+48h+var_20], 0
0x180017be8  mov     [rsp+48h+var_28], rbx
0x180017bed  xor     r9d, r9d
0x180017bf0  mov     r8d, eax
0x180017bf3  xor     edx, edx
0x180017bf5  lea     ecx, [rdx+3]
0x180017bf8  call    cs:__imp_SHTaskPoolQueueTask
0x180017bfe  mov     esi, eax
0x180017c00  and     edi, 0FFFFFFFEh
0x180017c03  mov     [rsp+48h+var_18], edi
0x180017c07  test    rbx, rbx
0x180017c0a  jz      short loc_180017C24
0x180017c0c  mov     [rsp+48h+arg_10], 0
0x180017c15  mov     rdx, [rbx]
0x180017c18  mov     rcx, rbx
0x180017c1b  mov     rax, [rdx+10h]
0x180017c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c24  mov     eax, esi
0x180017c26  mov     rbx, [rsp+48h+arg_0]
0x180017c2b  mov     rsi, [rsp+48h+arg_18]
0x180017c30  add     rsp, 40h
0x180017c34  pop     rdi
0x180017c35  retn
```
