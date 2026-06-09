# CUpdateDeploymentJob::CreateCallbackWorker(void)

- ea: `0x18003291c`
- end: `0x180032a95`
- name: `?CreateCallbackWorker@CUpdateDeploymentJob@@AEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180032d44`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180028c34`
- `0x18003291c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800329be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800329be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032a32`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180032a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180032a3b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032936`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003294b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003294b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800329d3`

## string_xrefs

- `0x180032965`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032984`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800329ed`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032a1e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032a5e`: `Deployment job Id %ws : Created CallbackWorker(%d) successfully.`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::CreateCallbackWorker(CUpdateDeploymentJob *this)
{
  HANDLE EventW; // rax
  const char *v3; // r9
  void *v4; // rcx
  HANDLE v5; // rbx
  int LastError; // eax
  unsigned int v7; // ebx
  HANDLE Thread; // rax
  const char *v10; // r9
  void *v11; // rcx
  HANDLE v12; // rbx
  int v13; // eax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  __int64 v16; // rax
  int dwCreationFlags; // [rsp+20h] [rbp-78h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-78h]
  _BYTE v19[88]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  EventW = CreateEventW(0, 0, 0, 0);
  v4 = (void *)*((_QWORD *)this + 97);
  v5 = EventW;
  if ( v4 )
    CloseHandle(v4);
  *((_QWORD *)this + 97) = v5;
  if ( v5
    || (LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1137,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                      v3),
        v7 = LastError,
        LastError >= 0) )
  {
    Thread = CreateThread(0, 0, CUpdateDeploymentJob::CallbackWorker, this, 0, 0);
    v11 = (void *)*((_QWORD *)this + 93);
    v12 = Thread;
    if ( v11 )
      CloseHandle(v11);
    *((_QWORD *)this + 93) = v12;
    if ( v12 )
    {
      v13 = CUpdateDeploymentJob::SetAppropriateThreadPriority(v11, v12, *((unsigned int *)this + 206));
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x114B,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v13,
          dwCreationFlagsa);
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      v16 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v19, (const struct _GUID *)this + 1);
      WUTrace(
        0,
        0,
        0x1000000,
        4,
        0,
        L"Deployment job Id %ws : Created CallbackWorker(%d) successfully.",
        v16,
        ThreadPriority);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1149,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
               v10);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x113E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)LastError,
      dwCreationFlags);
    return v7;
  }
}

```

## disassembly

```asm
0x18003291c  mov     [rsp+arg_0], rbx
0x180032921  push    rdi
0x180032922  sub     rsp, 90h
0x180032929  mov     rdi, rcx
0x18003292c  xor     r9d, r9d; lpName
0x18003292f  xor     ecx, ecx; lpEventAttributes
0x180032931  xor     r8d, r8d; bInitialState
0x180032934  xor     edx, edx; bManualReset
0x180032936  call    cs:__imp_CreateEventW
0x18003293c  mov     rcx, [rdi+308h]; hObject
0x180032943  mov     rbx, rax
0x180032946  test    rcx, rcx
0x180032949  jz      short loc_180032951
0x18003294b  call    cs:__imp_CloseHandle
0x180032951  mov     [rdi+308h], rbx
0x180032958  test    rbx, rbx
0x18003295b  jnz     short loc_18003299F
0x18003295d  mov     rcx, [rsp+98h]; this
0x180032965  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003296c  mov     edx, 1137h; void *
0x180032971  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032976  mov     ebx, eax
0x180032978  test    eax, eax
0x18003297a  jns     short loc_18003299F
0x18003297c  mov     rcx, [rsp+98h]; this
0x180032984  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003298b  mov     r9d, eax; char *
0x18003298e  mov     edx, 113Eh; void *
0x180032993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032998  mov     eax, ebx
0x18003299a  jmp     loc_180032A84
0x18003299f  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x1800329a8  lea     r8, ?CallbackWorker@CUpdateDeploymentJob@@CAKPEAX@Z; lpStartAddress
0x1800329af  mov     r9, rdi; lpParameter
0x1800329b2  mov     [rsp+98h+dwCreationFlags], 0; int
0x1800329ba  xor     edx, edx; dwStackSize
0x1800329bc  xor     ecx, ecx; lpThreadAttributes
0x1800329be  call    cs:__imp_CreateThread
0x1800329c4  mov     rcx, [rdi+2E8h]; hObject
0x1800329cb  mov     rbx, rax
0x1800329ce  test    rcx, rcx
0x1800329d1  jz      short loc_1800329D9
0x1800329d3  call    cs:__imp_CloseHandle
0x1800329d9  mov     [rdi+2E8h], rbx
0x1800329e0  test    rbx, rbx
0x1800329e3  jnz     short loc_180032A03
0x1800329e5  mov     rcx, [rsp+98h]; this
0x1800329ed  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800329f4  mov     edx, 1149h; void *
0x1800329f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800329fe  jmp     loc_180032A84
0x180032a03  mov     r8d, [rdi+338h]
0x180032a0a  mov     rdx, rbx
0x180032a0d  call    ?SetAppropriateThreadPriority@CUpdateDeploymentJob@@AEAAJPEAXW4tagDeploymentOperationPriority@@@Z; CUpdateDeploymentJob::SetAppropriateThreadPriority(void *,tagDeploymentOperationPriority)
0x180032a12  test    eax, eax
0x180032a14  jns     short loc_180032A32
0x180032a16  mov     rcx, [rsp+98h]; this
0x180032a1e  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032a25  mov     r9d, eax; char *
0x180032a28  mov     edx, 114Bh; void *
0x180032a2d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032a32  call    cs:__imp_GetCurrentThread
0x180032a38  mov     rcx, rax; hThread
0x180032a3b  call    cs:__imp_GetThreadPriority
0x180032a41  lea     rdx, [rdi+10h]; struct _GUID *
0x180032a45  mov     ebx, eax
0x180032a47  lea     rcx, [rsp+98h+var_58]; this
0x180032a4c  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180032a51  mov     [rsp+98h+var_60], ebx
0x180032a55  xor     edx, edx
0x180032a57  mov     [rsp+98h+var_68], rax
0x180032a5c  xor     ecx, ecx
0x180032a5e  lea     rax, aDeploymentJobI_18; "Deployment job Id %ws : Created Callbac"...
0x180032a65  mov     r8d, 1000000h
0x180032a6b  mov     [rsp+98h+lpThreadId], rax
0x180032a70  lea     r9d, [rdx+4]
0x180032a74  mov     qword ptr [rsp+98h+dwCreationFlags], 0
0x180032a7d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180032a82  xor     eax, eax
0x180032a84  mov     rbx, [rsp+98h+arg_0]
0x180032a8c  add     rsp, 90h
0x180032a93  pop     rdi
0x180032a94  retn
```
