# CUpdateDeploymentJob::CreateDeploymentWorker(void)

- ea: `0x180032a9c`
- end: `0x180032ba2`
- name: `?CreateDeploymentWorker@CUpdateDeploymentJob@@AEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180032d44`

## callees

- `0x180002214`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180028c34`
- `0x180032a9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032acb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032b3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032b3f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180032b48`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180032b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ae0`

## string_xrefs

- `0x180032afa`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032b2b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032b6b`: `Deployment job Id %ws : Created DeploymentWorker(%d) successfully.`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::CreateDeploymentWorker(struct _GUID *this)
{
  HANDLE Thread; // rax
  const char *v3; // r9
  void *v4; // rcx
  HANDLE v5; // rbx
  int v7; // eax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  __int64 v10; // rax
  int dwCreationFlags; // [rsp+20h] [rbp-78h]
  _BYTE v12[88]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  Thread = CreateThread(0, 0, CUpdateDeploymentJob::InvokeDeployUpdates, this, 0, 0);
  v4 = *(void **)&this[46].Data1;
  v5 = Thread;
  if ( v4 )
    CloseHandle(v4);
  *(_QWORD *)&this[46].Data1 = v5;
  if ( !v5 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x116C,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
             v3);
  v7 = CUpdateDeploymentJob::SetAppropriateThreadPriority(v4, v5, *(unsigned int *)this[51].Data4);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x116E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v7,
      dwCreationFlags);
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v10 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v12, this + 1);
  WUTrace(
    0,
    0,
    0x1000000,
    4,
    0,
    L"Deployment job Id %ws : Created DeploymentWorker(%d) successfully.",
    v10,
    ThreadPriority);
  return 0;
}

```

## disassembly

```asm
0x180032a9c  mov     [rsp+arg_0], rbx
0x180032aa1  push    rdi
0x180032aa2  sub     rsp, 90h
0x180032aa9  mov     rdi, rcx
0x180032aac  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x180032ab5  mov     r9, rcx; lpParameter
0x180032ab8  mov     [rsp+98h+dwCreationFlags], 0; int
0x180032ac0  xor     ecx, ecx; lpThreadAttributes
0x180032ac2  lea     r8, ?InvokeDeployUpdates@CUpdateDeploymentJob@@CAKPEAX@Z; lpStartAddress
0x180032ac9  xor     edx, edx; dwStackSize
0x180032acb  call    cs:__imp_CreateThread
0x180032ad1  mov     rcx, [rdi+2E0h]; hObject
0x180032ad8  mov     rbx, rax
0x180032adb  test    rcx, rcx
0x180032ade  jz      short loc_180032AE6
0x180032ae0  call    cs:__imp_CloseHandle
0x180032ae6  mov     [rdi+2E0h], rbx
0x180032aed  test    rbx, rbx
0x180032af0  jnz     short loc_180032B10
0x180032af2  mov     rcx, [rsp+98h]; this
0x180032afa  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032b01  mov     edx, 116Ch; void *
0x180032b06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032b0b  jmp     loc_180032B91
0x180032b10  mov     r8d, [rdi+338h]
0x180032b17  mov     rdx, rbx
0x180032b1a  call    ?SetAppropriateThreadPriority@CUpdateDeploymentJob@@AEAAJPEAXW4tagDeploymentOperationPriority@@@Z; CUpdateDeploymentJob::SetAppropriateThreadPriority(void *,tagDeploymentOperationPriority)
0x180032b1f  test    eax, eax
0x180032b21  jns     short loc_180032B3F
0x180032b23  mov     rcx, [rsp+98h]; this
0x180032b2b  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032b32  mov     r9d, eax; char *
0x180032b35  mov     edx, 116Eh; void *
0x180032b3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032b3f  call    cs:__imp_GetCurrentThread
0x180032b45  mov     rcx, rax; hThread
0x180032b48  call    cs:__imp_GetThreadPriority
0x180032b4e  lea     rdx, [rdi+10h]; struct _GUID *
0x180032b52  mov     ebx, eax
0x180032b54  lea     rcx, [rsp+98h+var_58]; this
0x180032b59  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180032b5e  mov     [rsp+98h+var_60], ebx
0x180032b62  xor     edx, edx
0x180032b64  mov     [rsp+98h+var_68], rax
0x180032b69  xor     ecx, ecx
0x180032b6b  lea     rax, aDeploymentJobI_64; "Deployment job Id %ws : Created Deploym"...
0x180032b72  mov     r8d, 1000000h
0x180032b78  mov     [rsp+98h+lpThreadId], rax
0x180032b7d  lea     r9d, [rdx+4]
0x180032b81  mov     qword ptr [rsp+98h+dwCreationFlags], 0
0x180032b8a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180032b8f  xor     eax, eax
0x180032b91  mov     rbx, [rsp+98h+arg_0]
0x180032b99  add     rsp, 90h
0x180032ba0  pop     rdi
0x180032ba1  retn
```
