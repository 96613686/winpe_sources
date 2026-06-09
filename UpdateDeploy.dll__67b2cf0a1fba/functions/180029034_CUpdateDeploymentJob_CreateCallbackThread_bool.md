# CUpdateDeploymentJob::CreateCallbackThread(bool)

- ea: `0x180029034`
- end: `0x1800291c5`
- name: `?CreateCallbackThread@CUpdateDeploymentJob@@AEAAJ_N@Z`
- size: `401`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *this, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800291d0`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x180028c34`
- `0x180029034`
- `0x180037e40`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029077`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029077`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180029134`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180029134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029172`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029172`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800290e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800290e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a0`

## string_xrefs

- `0x18002908a`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800290b8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002914b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUpdateDeploymentJob::CreateCallbackThread(CUpdateDeploymentJob *this, char a2)
{
  HANDLE Thread; // rax
  __int64 v5; // rcx
  const char *v6; // r9
  void *v7; // rbx
  int v9; // eax
  DWORD v10; // eax
  signed int v11; // ebx
  signed int LastError; // eax
  _QWORD *v13; // rdx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  DWORD ExitCode[2]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Thread = CreateThread(0, 0, CUpdateDeploymentJob::InvokeAsyncCallback, this, 0, 0);
  v7 = Thread;
  if ( !Thread )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x21B,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
             v6);
  v9 = CUpdateDeploymentJob::SetAppropriateThreadPriority(v5, Thread, *((unsigned int *)this + 206));
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21D,
      (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v9);
  if ( a2 )
  {
    ExitCode[0] = 0;
    v10 = WaitForSingleObject(v7, 0xFFFFFFFF);
    if ( v10 )
    {
      if ( v10 == 258 )
      {
        v11 = -2145124319;
        goto LABEL_16;
      }
      if ( v10 != -1 )
      {
        v11 = -2145120257;
LABEL_16:
        ExitCode[0] = v11;
LABEL_19:
        if ( v11 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23E,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v11,
            dwCreationFlags);
        return (unsigned int)v11;
      }
    }
    else if ( GetExitCodeThread(v7, ExitCode) )
    {
      v11 = ExitCode[0];
      goto LABEL_19;
    }
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 >= 0 )
      v11 = -2147418113;
    goto LABEL_16;
  }
  *(_QWORD *)ExitCode = v7;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v13 = (_QWORD *)*((_QWORD *)this + 95);
  if ( v13 == *((_QWORD **)this + 96) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)this + 752, v13, ExitCode);
  }
  else
  {
    *v13 = v7;
    *((_QWORD *)this + 95) += 8LL;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  return 0;
}

```

## disassembly

```asm
0x180029034  mov     [rsp+arg_8], rbx
0x180029039  mov     [rsp+arg_10], rsi
0x18002903e  push    rdi
0x18002903f  sub     rsp, 40h
0x180029043  mov     rax, cs:__security_cookie
0x18002904a  xor     rax, rsp
0x18002904d  mov     [rsp+48h+var_10], rax
0x180029052  mov     sil, dl
0x180029055  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18002905e  mov     rdi, rcx
0x180029061  mov     [rsp+48h+dwCreationFlags], 0; int
0x180029069  mov     r9, rcx; lpParameter
0x18002906c  lea     r8, ?InvokeAsyncCallback@CUpdateDeploymentJob@@CAKPEAX@Z; lpStartAddress
0x180029073  xor     edx, edx; dwStackSize
0x180029075  xor     ecx, ecx; lpThreadAttributes
0x180029077  call    cs:__imp_CreateThread
0x18002907d  mov     rbx, rax
0x180029080  test    rax, rax
0x180029083  jnz     short loc_1800290A0
0x180029085  mov     rcx, [rsp+48h]; this
0x18002908a  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180029091  mov     edx, 21Bh; void *
0x180029096  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002909b  jmp     loc_1800291A8
0x1800290a0  mov     r8d, [rdi+338h]
0x1800290a7  mov     rdx, rbx
0x1800290aa  call    ?SetAppropriateThreadPriority@CUpdateDeploymentJob@@AEAAJPEAXW4tagDeploymentOperationPriority@@@Z; CUpdateDeploymentJob::SetAppropriateThreadPriority(void *,tagDeploymentOperationPriority)
0x1800290af  test    eax, eax
0x1800290b1  jns     short loc_1800290CC
0x1800290b3  mov     rcx, [rsp+48h]; this
0x1800290b8  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800290bf  mov     r9d, eax; char *
0x1800290c2  mov     edx, 21Dh; void *
0x1800290c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800290cc  test    sil, sil
0x1800290cf  jz      loc_180029163
0x1800290d5  or      edi, 0FFFFFFFFh
0x1800290d8  mov     [rsp+48h+ExitCode], 0
0x1800290e0  mov     edx, edi; dwMilliseconds
0x1800290e2  mov     rcx, rbx; hHandle
0x1800290e5  call    cs:__imp_WaitForSingleObject
0x1800290eb  test    eax, eax
0x1800290ed  jz      short loc_18002912C
0x1800290ef  cmp     eax, 102h
0x1800290f4  jz      short loc_180029121
0x1800290f6  cmp     eax, edi
0x1800290f8  jz      short loc_180029101
0x1800290fa  mov     ebx, 80240FFFh
0x1800290ff  jmp     short loc_180029126
0x180029101  call    cs:__imp_GetLastError
0x180029107  movzx   ebx, ax
0x18002910a  or      ebx, 80070000h
0x180029110  test    eax, eax
0x180029112  cmovle  ebx, eax
0x180029115  mov     eax, 8000FFFFh
0x18002911a  test    ebx, ebx
0x18002911c  cmovns  ebx, eax
0x18002911f  jmp     short loc_180029126
0x180029121  mov     ebx, 80240021h
0x180029126  mov     [rsp+48h+ExitCode], ebx
0x18002912a  jmp     short loc_180029142
0x18002912c  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x180029131  mov     rcx, rbx; hThread
0x180029134  call    cs:__imp_GetExitCodeThread
0x18002913a  test    eax, eax
0x18002913c  jz      short loc_180029101
0x18002913e  mov     ebx, [rsp+48h+ExitCode]
0x180029142  test    ebx, ebx
0x180029144  jns     short loc_18002915F
0x180029146  mov     rcx, [rsp+48h]; this
0x18002914b  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180029152  mov     r9d, ebx; char *
0x180029155  mov     edx, 23Eh; void *
0x18002915a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002915f  mov     eax, ebx
0x180029161  jmp     short loc_1800291A8
0x180029163  lea     rsi, [rdi+378h]
0x18002916a  mov     qword ptr [rsp+48h+ExitCode], rbx
0x18002916f  mov     rcx, rsi; lpCriticalSection
0x180029172  call    cs:__imp_EnterCriticalSection
0x180029178  lea     rcx, [rdi+2F0h]
0x18002917f  mov     rdx, [rcx+8]
0x180029183  cmp     rdx, [rcx+10h]
0x180029187  jz      short loc_180029193
0x180029189  mov     [rdx], rbx
0x18002918c  add     qword ptr [rcx+8], 8
0x180029191  jmp     short loc_18002919D
0x180029193  lea     r8, [rsp+48h+ExitCode]
0x180029198  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x18002919d  mov     rcx, rsi; lpCriticalSection
0x1800291a0  call    cs:__imp_LeaveCriticalSection
0x1800291a6  xor     eax, eax
0x1800291a8  mov     rcx, [rsp+48h+var_10]
0x1800291ad  xor     rcx, rsp; StackCookie
0x1800291b0  call    __security_check_cookie
0x1800291b5  mov     rbx, [rsp+48h+arg_8]
0x1800291ba  mov     rsi, [rsp+48h+arg_10]
0x1800291bf  add     rsp, 40h
0x1800291c3  pop     rdi
0x1800291c4  retn
```
