# Windows::Internal::ComTaskPool::QueueTask__lambda_dcf910a5157ede129762ce7cf8f28c5c___

- ea: `0x18001376c`
- end: `0x1800137ea`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_dcf910a5157ede129762ce7cf8f28c5c___`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017340`

## callees

- `0x1800109e0`
- `0x18001315c`
- `0x18001376c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137a2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800137c0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800137c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask__lambda_dcf910a5157ede129762ce7cf8f28c5c___()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v3; // edi
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_dcf910a5157ede129762ce7cf8f28c5c_____lambda_dcf910a5157ede129762ce7cf8f28c5c___(&v5);
  v1 = *v0;
  *v0 = 0;
  if ( v5 )
  {
    v5 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v3 = SHTaskPoolQueueTask(0, 0, CurrentThreadId);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x18001376c  mov     [rsp+arg_0], rbx
0x180013771  push    rdi
0x180013772  sub     rsp, 30h
0x180013776  lea     rcx, [rsp+38h+arg_10]
0x18001377b  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_dcf910a5157ede129762ce7cf8f28c5c_____lambda_dcf910a5157ede129762ce7cf8f28c5c___
0x180013780  mov     rbx, [rax]
0x180013783  mov     qword ptr [rax], 0
0x18001378a  mov     rcx, [rsp+38h+arg_10]
0x18001378f  test    rcx, rcx
0x180013792  jz      short loc_1800137A2
0x180013794  mov     [rsp+38h+arg_10], 0
0x18001379d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release(void)
0x1800137a2  call    cs:__imp_GetCurrentThreadId
0x1800137a8  mov     [rsp+38h+var_10], 0
0x1800137b1  mov     [rsp+38h+var_18], rbx
0x1800137b6  xor     r9d, r9d
0x1800137b9  mov     r8d, eax
0x1800137bc  xor     edx, edx
0x1800137be  xor     ecx, ecx
0x1800137c0  call    cs:__imp_SHTaskPoolQueueTask
0x1800137c6  mov     edi, eax
0x1800137c8  test    rbx, rbx
0x1800137cb  jz      short loc_1800137DD
0x1800137cd  mov     rdx, [rbx]
0x1800137d0  mov     rcx, rbx
0x1800137d3  mov     rax, [rdx+10h]
0x1800137d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137dc  nop
0x1800137dd  mov     eax, edi
0x1800137df  mov     rbx, [rsp+38h+arg_0]
0x1800137e4  add     rsp, 30h
0x1800137e8  pop     rdi
0x1800137e9  retn
```
