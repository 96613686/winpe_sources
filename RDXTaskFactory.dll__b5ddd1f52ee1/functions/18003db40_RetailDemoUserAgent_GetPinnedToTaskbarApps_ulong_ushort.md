# RetailDemoUserAgent::GetPinnedToTaskbarApps(ulong *,ushort * * *)

- ea: `0x18003db40`
- end: `0x18003dbba`
- name: `?GetPinnedToTaskbarApps@RetailDemoUserAgent@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `122`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aa7c`
- `0x180034ccc`
- `0x180036080`
- `0x18003db40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003db7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003db7c`

## string_xrefs

- `0x18003db98`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
__int64 __fastcall RetailDemoUserAgent::GetPinnedToTaskbarApps(
        RetailDemoUserAgent *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int v10[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int *v12; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 ***v13; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+20h] BYREF

  v13 = a3;
  v12 = a2;
  v14 = 0;
  *a2 = 0;
  *a3 = 0;
  v3 = lambda_cb67e1136dc75a1a448054ae0a8617c0_::_lambda_cb67e1136dc75a1a448054ae0a8617c0_(v10, &v14, &v12, &v13);
  CurrentThreadId = GetCurrentThreadId();
  v7 = Windows::Internal::ComTaskPool::QueueTask__lambda_cb67e1136dc75a1a448054ae0a8617c0___(
         v6,
         v5,
         CurrentThreadId,
         v3);
  v8 = v7;
  if ( v7 >= 0 )
    return v14;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76B,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)(unsigned int)v7,
    v10[0]);
  return v8;
}

```

## disassembly

```asm
0x18003db40  mov     rax, rsp
0x18003db43  mov     [rax+18h], r8
0x18003db47  mov     [rax+10h], rdx
0x18003db4b  push    rbx
0x18003db4c  sub     rsp, 40h
0x18003db50  mov     dword ptr [rax+20h], 0
0x18003db57  lea     r9, [rax+18h]
0x18003db5b  mov     dword ptr [rdx], 0
0x18003db61  lea     rcx, [rax-28h]
0x18003db65  mov     qword ptr [r8], 0
0x18003db6c  lea     rdx, [rax+20h]
0x18003db70  lea     r8, [rax+10h]
0x18003db74  call    _lambda_cb67e1136dc75a1a448054ae0a8617c0____lambda_cb67e1136dc75a1a448054ae0a8617c0_
0x18003db79  mov     rbx, rax
0x18003db7c  call    cs:__imp_GetCurrentThreadId
0x18003db82  mov     r8d, eax
0x18003db85  mov     r9, rbx
0x18003db88  call    Windows__Internal__ComTaskPool__QueueTask__lambda_cb67e1136dc75a1a448054ae0a8617c0___
0x18003db8d  mov     ebx, eax
0x18003db8f  test    eax, eax
0x18003db91  jns     short loc_18003DBB0
0x18003db93  mov     rcx, [rsp+48h]; this
0x18003db98  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003db9f  mov     r9d, eax; char *
0x18003dba2  mov     edx, 76Bh; void *
0x18003dba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dbac  mov     eax, ebx
0x18003dbae  jmp     short loc_18003DBB4
0x18003dbb0  mov     eax, [rsp+48h+arg_18]
0x18003dbb4  add     rsp, 40h
0x18003dbb8  pop     rbx
0x18003dbb9  retn
```
