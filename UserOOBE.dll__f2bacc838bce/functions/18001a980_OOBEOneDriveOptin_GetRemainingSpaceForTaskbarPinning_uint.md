# OOBEOneDriveOptin::GetRemainingSpaceForTaskbarPinning(uint *)

- ea: `0x18001a980`
- end: `0x18001a9e1`
- name: `?GetRemainingSpaceForTaskbarPinning@OOBEOneDriveOptin@@UEAAJPEAI@Z`
- size: `97`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007134`
- `0x180011010`
- `0x180017b34`
- `0x18001a980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9a5`

## string_xrefs

- `0x18001a9c1`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall OOBEOneDriveOptin::GetRemainingSpaceForTaskbarPinning(OOBEOneDriveOptin *this, unsigned int *a2)
{
  __int64 v2; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v9[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int *v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = a2;
  *a2 = 0;
  v2 = _lambda_ced754b16811b5f4be632a806d8f3385_::_lambda_ced754b16811b5f4be632a806d8f3385_(v9, this, &v11);
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::QueueTask__lambda_bf68870c162f8c84f8547abd8527d5b9___(
         v5,
         v4,
         CurrentThreadId,
         v2);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x119,
    (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v6,
    v9[0]);
  return v7;
}

```

## disassembly

```asm
0x18001a980  mov     [rsp+arg_8], rdx
0x18001a985  push    rbx
0x18001a986  sub     rsp, 30h
0x18001a98a  mov     dword ptr [rdx], 0
0x18001a990  lea     r8, [rsp+38h+arg_8]
0x18001a995  mov     rdx, rcx
0x18001a998  lea     rcx, [rsp+38h+var_18]
0x18001a99d  call    ??0_lambda_ced754b16811b5f4be632a806d8f3385_@@QEAA@AEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAVOOBEMonitor@@@Z
0x18001a9a2  mov     rbx, rax
0x18001a9a5  call    cs:__imp_GetCurrentThreadId
0x18001a9ab  mov     r8d, eax
0x18001a9ae  mov     r9, rbx
0x18001a9b1  call    Windows__Internal__ComTaskPool__QueueTask__lambda_bf68870c162f8c84f8547abd8527d5b9___
0x18001a9b6  mov     ebx, eax
0x18001a9b8  test    eax, eax
0x18001a9ba  jns     short loc_18001A9D9
0x18001a9bc  mov     rcx, [rsp+38h]; this
0x18001a9c1  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a9c8  mov     r9d, eax; char *
0x18001a9cb  mov     edx, 119h; void *
0x18001a9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9d5  mov     eax, ebx
0x18001a9d7  jmp     short loc_18001A9DB
0x18001a9d9  xor     eax, eax
0x18001a9db  add     rsp, 30h
0x18001a9df  pop     rbx
0x18001a9e0  retn
```
