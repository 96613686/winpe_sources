# Windows::Internal::ComTaskPool::QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___

- ea: `0x18003ff24`
- end: `0x18003ffa3`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040914`

## callees

- `0x18000d400`
- `0x18003fe04`
- `0x18003ff24`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003ff79`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003ff79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ff5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ff5a`

## pseudocode

```c
__int64 Windows::Internal::ComTaskPool::QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  __int64 v2; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v4; // edi
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_983deade1ef85b175d24d05d87d8a1b3_____lambda_983deade1ef85b175d24d05d87d8a1b3___(&v6);
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
0x18003ff24  mov     [rsp+arg_0], rbx
0x18003ff29  push    rdi
0x18003ff2a  sub     rsp, 30h
0x18003ff2e  lea     rcx, [rsp+38h+arg_10]
0x18003ff33  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_983deade1ef85b175d24d05d87d8a1b3_____lambda_983deade1ef85b175d24d05d87d8a1b3___
0x18003ff38  mov     rbx, [rax]
0x18003ff3b  mov     qword ptr [rax], 0
0x18003ff42  mov     rcx, [rsp+38h+arg_10]
0x18003ff47  test    rcx, rcx
0x18003ff4a  jz      short loc_18003FF5A
0x18003ff4c  mov     [rsp+38h+arg_10], 0
0x18003ff55  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x18003ff5a  call    cs:__imp_GetCurrentThreadId
0x18003ff60  mov     [rsp+38h+var_10], 0
0x18003ff69  mov     [rsp+38h+var_18], rbx
0x18003ff6e  xor     r9d, r9d
0x18003ff71  mov     r8d, eax
0x18003ff74  xor     edx, edx
0x18003ff76  lea     ecx, [rdx+1]
0x18003ff79  call    cs:__imp_SHTaskPoolQueueTask
0x18003ff7f  mov     edi, eax
0x18003ff81  test    rbx, rbx
0x18003ff84  jz      short loc_18003FF96
0x18003ff86  mov     rdx, [rbx]
0x18003ff89  mov     rcx, rbx
0x18003ff8c  mov     rax, [rdx+10h]
0x18003ff90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff95  nop
0x18003ff96  mov     eax, edi
0x18003ff98  mov     rbx, [rsp+38h+arg_0]
0x18003ff9d  add     rsp, 30h
0x18003ffa1  pop     rdi
0x18003ffa2  retn
```
