# Windows::Internal::ComTaskPool::QueueTask__lambda_1acd6cdd80cddfb63618e898b2901780___

- ea: `0x14000bf88`
- end: `0x14000c007`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_1acd6cdd80cddfb63618e898b2901780___`
- size: `127`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d884`

## callees

- `0x14000becc`
- `0x14000bf88`
- `0x14000d130`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bfbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bfbe`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14000bfdd`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14000bfdd`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_1acd6cdd80cddfb63618e898b2901780___(
        __int64 a1,
        __int64 a2)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  volatile signed __int32 *v8; // [rsp+50h] [rbp+18h] BYREF

  v2 = Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____lambda_1acd6cdd80cddfb63618e898b2901780___(
         &v8,
         a2);
  v3 = *v2;
  *v2 = 0;
  v4 = v8;
  if ( v8 )
  {
    v8 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v4);
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v3, 0);
  if ( v3 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x14000bf88  mov     [rsp+arg_0], rbx
0x14000bf8d  push    rdi
0x14000bf8e  sub     rsp, 30h
0x14000bf92  lea     rcx, [rsp+38h+arg_10]
0x14000bf97  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____lambda_1acd6cdd80cddfb63618e898b2901780___
0x14000bf9c  mov     rbx, [rax]
0x14000bf9f  mov     qword ptr [rax], 0
0x14000bfa6  mov     rcx, [rsp+38h+arg_10]
0x14000bfab  test    rcx, rcx
0x14000bfae  jz      short loc_14000BFBE
0x14000bfb0  mov     [rsp+38h+arg_10], 0
0x14000bfb9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x14000bfbe  call    cs:__imp_GetCurrentThreadId
0x14000bfc4  mov     [rsp+38h+var_10], 0
0x14000bfcd  mov     [rsp+38h+var_18], rbx
0x14000bfd2  xor     r9d, r9d
0x14000bfd5  mov     r8d, eax
0x14000bfd8  xor     edx, edx
0x14000bfda  lea     ecx, [rdx+3]
0x14000bfdd  call    cs:__imp_SHTaskPoolQueueTask
0x14000bfe3  mov     edi, eax
0x14000bfe5  test    rbx, rbx
0x14000bfe8  jz      short loc_14000BFFA
0x14000bfea  mov     rdx, [rbx]
0x14000bfed  mov     rcx, rbx
0x14000bff0  mov     rax, [rdx+10h]
0x14000bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bff9  nop
0x14000bffa  mov     eax, edi
0x14000bffc  mov     rbx, [rsp+38h+arg_0]
0x14000c001  add     rsp, 30h
0x14000c005  pop     rdi
0x14000c006  retn
```
