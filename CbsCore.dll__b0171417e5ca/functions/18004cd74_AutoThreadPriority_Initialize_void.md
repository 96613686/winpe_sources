# AutoThreadPriority::Initialize(void)

- ea: `0x18004cd74`
- end: `0x18004cf1b`
- name: `?Initialize@AutoThreadPriority@@AEAAXXZ`
- size: `423`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cd20`

## callees

- `0x180010cc0`
- `0x1800150c0`
- `0x18004cd74`
- `0x1800eb920`
- `0x1800f6fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cde0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cde0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004cdd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ce2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004cdd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ce2f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18004ce49`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18004ce49`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ce10`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ce10`
- `ntdll!NtQueryInformationThread` at `0x18004ce7b`
- `ntdll!NtQueryInformationThread` at `0x18004ceab`
- `ntdll!NtQueryInformationThread` at `0x18004cedd`
- `ntdll!NtQueryInformationThread` at `0x18004ce7b`
- `ntdll!NtQueryInformationThread` at `0x18004ceab`
- `ntdll!NtQueryInformationThread` at `0x18004cedd`

## string_xrefs

- `0x18004ce20`: `Failed to duplicate thread handle.`

## pseudocode

```c
void __fastcall AutoThreadPriority::Initialize(AutoThreadPriority *this)
{
  HANDLE *v1; // r14
  HANDLE *InitPointer; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v6; // rax
  HANDLE v7; // rax
  int ThreadPriority; // eax
  int ThreadInformation; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+44h] [rbp-34h] BYREF
  __int64 v11; // [rsp+48h] [rbp-30h] BYREF
  int v12; // [rsp+50h] [rbp-28h]

  ThreadInformation = 2;
  v1 = (HANDLE *)((char *)this + 48);
  v10 = 5;
  v11 = 0;
  v12 = 0;
  InitPointer = (HANDLE *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer((char *)this + 48);
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v6 = GetCurrentProcess();
  if ( !DuplicateHandle(v6, CurrentThread, CurrentProcess, InitPointer, 0, 0, 2u) )
  {
    LogAdapter::TraceAtLevelLastError<>(2, "Failed to duplicate thread handle.");
    v7 = GetCurrentThread();
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(v1, v7);
  }
  ThreadPriority = GetThreadPriority(*v1);
  if ( ThreadPriority != 0x7FFFFFFF )
    *((_DWORD *)this + 14) = ThreadPriority;
  if ( NtQueryInformationThread(*v1, ThreadIoPriority, &ThreadInformation, 4u, 0) >= 0 )
    *((_DWORD *)this + 15) = ThreadInformation;
  if ( NtQueryInformationThread(*v1, ThreadPagePriority, &v10, 4u, 0) >= 0 )
    *((_DWORD *)this + 16) = v10;
  if ( NtQueryInformationThread(*v1, ThreadHideFromDebugger|0x20, &v11, 0xCu, 0) >= 0 )
    *((_BYTE *)this + 68) = v12 == 1;
}

```

## disassembly

```asm
0x18004cd74  mov     [rsp+arg_8], rbx
0x18004cd79  mov     [rsp+arg_10], rbp
0x18004cd7e  push    rsi
0x18004cd7f  push    rdi
0x18004cd80  push    r14
0x18004cd82  sub     rsp, 60h
0x18004cd86  mov     rax, cs:__security_cookie
0x18004cd8d  xor     rax, rsp
0x18004cd90  mov     [rsp+78h+var_20], rax
0x18004cd95  xor     eax, eax
0x18004cd97  mov     [rsp+78h+ThreadInformation], 2
0x18004cd9f  lea     r14, [rcx+30h]
0x18004cda3  mov     [rsp+78h+var_34], 5
0x18004cdab  mov     rbp, rcx
0x18004cdae  mov     [rsp+78h+var_30], rax
0x18004cdb3  mov     rcx, r14
0x18004cdb6  mov     [rsp+78h+var_28], eax
0x18004cdba  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18004cdbf  mov     rsi, rax
0x18004cdc2  call    cs:__imp_GetCurrentProcess
0x18004cdc9  nop     dword ptr [rax+rax+00h]
0x18004cdce  mov     rdi, rax
0x18004cdd1  call    cs:__imp_GetCurrentThread
0x18004cdd8  nop     dword ptr [rax+rax+00h]
0x18004cddd  mov     rbx, rax
0x18004cde0  call    cs:__imp_GetCurrentProcess
0x18004cde7  nop     dword ptr [rax+rax+00h]
0x18004cdec  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18004cdf4  mov     r9, rsi; lpTargetHandle
0x18004cdf7  mov     rcx, rax; hSourceProcessHandle
0x18004cdfa  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18004ce02  mov     r8, rdi; hTargetProcessHandle
0x18004ce05  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18004ce0d  mov     rdx, rbx; hSourceHandle
0x18004ce10  call    cs:__imp_DuplicateHandle
0x18004ce17  nop     dword ptr [rax+rax+00h]
0x18004ce1c  test    eax, eax
0x18004ce1e  jnz     short loc_18004CE46
0x18004ce20  lea     rdx, aFailedToDuplic_0; "Failed to duplicate thread handle."
0x18004ce27  lea     ecx, [rax+2]
0x18004ce2a  call    ??$TraceAtLevelLastError@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevelLastError<>(LogAdapter::LogLevel,char const * const)
0x18004ce2f  call    cs:__imp_GetCurrentThread
0x18004ce36  nop     dword ptr [rax+rax+00h]
0x18004ce3b  mov     rdx, rax
0x18004ce3e  mov     rcx, r14
0x18004ce41  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x18004ce46  mov     rcx, [r14]; hThread
0x18004ce49  call    cs:__imp_GetThreadPriority
0x18004ce50  nop     dword ptr [rax+rax+00h]
0x18004ce55  cmp     eax, 7FFFFFFFh
0x18004ce5a  jz      short loc_18004CE5F
0x18004ce5c  mov     [rbp+38h], eax
0x18004ce5f  mov     rcx, [r14]; ThreadHandle
0x18004ce62  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x18004ce67  mov     ebx, 4
0x18004ce6c  mov     qword ptr [rsp+78h+dwDesiredAccess], 0; ReturnLength
0x18004ce75  mov     r9d, ebx; ThreadInformationLength
0x18004ce78  lea     edx, [rbx+12h]; ThreadInformationClass
0x18004ce7b  call    cs:__imp_NtQueryInformationThread
0x18004ce82  nop     dword ptr [rax+rax+00h]
0x18004ce87  test    eax, eax
0x18004ce89  js      short loc_18004CE92
0x18004ce8b  mov     eax, [rsp+78h+ThreadInformation]
0x18004ce8f  mov     [rbp+3Ch], eax
0x18004ce92  mov     rcx, [r14]; ThreadHandle
0x18004ce95  lea     r8, [rsp+78h+var_34]; ThreadInformation
0x18004ce9a  mov     r9d, ebx; ThreadInformationLength
0x18004ce9d  mov     qword ptr [rsp+78h+dwDesiredAccess], 0; ReturnLength
0x18004cea6  mov     edx, 18h; ThreadInformationClass
0x18004ceab  call    cs:__imp_NtQueryInformationThread
0x18004ceb2  nop     dword ptr [rax+rax+00h]
0x18004ceb7  test    eax, eax
0x18004ceb9  js      short loc_18004CEC2
0x18004cebb  mov     eax, [rsp+78h+var_34]
0x18004cebf  mov     [rbp+40h], eax
0x18004cec2  mov     rcx, [r14]; ThreadHandle
0x18004cec5  lea     r8, [rsp+78h+var_30]; ThreadInformation
0x18004ceca  mov     r9d, 0Ch; ThreadInformationLength
0x18004ced0  mov     qword ptr [rsp+78h+dwDesiredAccess], 0; ReturnLength
0x18004ced9  lea     edx, [r9+25h]; ThreadInformationClass
0x18004cedd  call    cs:__imp_NtQueryInformationThread
0x18004cee4  nop     dword ptr [rax+rax+00h]
0x18004cee9  test    eax, eax
0x18004ceeb  js      short loc_18004CEF8
0x18004ceed  cmp     [rsp+78h+var_28], 1
0x18004cef2  setz    al
0x18004cef5  mov     [rbp+44h], al
0x18004cef8  mov     rcx, [rsp+78h+var_20]
0x18004cefd  xor     rcx, rsp; StackCookie
0x18004cf00  call    __security_check_cookie
0x18004cf05  lea     r11, [rsp+78h+var_18]
0x18004cf0a  mov     rbx, [r11+28h]
0x18004cf0e  mov     rbp, [r11+30h]
0x18004cf12  mov     rsp, r11
0x18004cf15  pop     r14
0x18004cf17  pop     rdi
0x18004cf18  pop     rsi
0x18004cf19  retn
```
