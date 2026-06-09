# Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(Windows::Internal::TaskApartment,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)

- ea: `0x1800177bc`
- end: `0x180017848`
- name: `??$QueueTask@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800185c0`

## callees

- `0x180012120`
- `0x180017640`
- `0x1800177bc`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800177f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800177f2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017817`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180017817`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v3; // edi
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(&v5);
  v1 = *v0;
  *v0 = 0;
  if ( v5 )
  {
    v5 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v3 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v1, 0);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x1800177bc  mov     [rsp+arg_0], rbx
0x1800177c1  push    rdi
0x1800177c2  sub     rsp, 30h
0x1800177c6  lea     rcx, [rsp+38h+arg_10]
0x1800177cb  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x1800177d0  mov     rbx, [rax]
0x1800177d3  mov     qword ptr [rax], 0
0x1800177da  mov     rcx, [rsp+38h+arg_10]
0x1800177df  test    rcx, rcx
0x1800177e2  jz      short loc_1800177F2
0x1800177e4  mov     [rsp+38h+arg_10], 0
0x1800177ed  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800177f2  call    cs:__imp_GetCurrentThreadId
0x1800177f9  nop     dword ptr [rax+rax+00h]
0x1800177fe  mov     [rsp+38h+var_10], 0
0x180017807  mov     [rsp+38h+var_18], rbx
0x18001780c  xor     r9d, r9d
0x18001780f  mov     r8d, eax
0x180017812  xor     edx, edx
0x180017814  lea     ecx, [rdx+3]
0x180017817  call    cs:__imp_SHTaskPoolQueueTask
0x18001781e  nop     dword ptr [rax+rax+00h]
0x180017823  mov     edi, eax
0x180017825  test    rbx, rbx
0x180017828  jz      short loc_18001783A
0x18001782a  mov     rdx, [rbx]
0x18001782d  mov     rcx, rbx
0x180017830  mov     rax, [rdx+10h]
0x180017834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017839  nop
0x18001783a  mov     eax, edi
0x18001783c  mov     rbx, [rsp+38h+arg_0]
0x180017841  add     rsp, 30h
0x180017845  pop     rdi
0x180017846  retn
```
