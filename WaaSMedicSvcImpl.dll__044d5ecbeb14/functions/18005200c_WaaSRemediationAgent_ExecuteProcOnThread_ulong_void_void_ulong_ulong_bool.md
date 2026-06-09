# WaaSRemediationAgent::ExecuteProcOnThread(ulong (*)(void *),void *,ulong *,ulong,bool)

- ea: `0x18005200c`
- end: `0x180052184`
- name: `?ExecuteProcOnThread@WaaSRemediationAgent@@CAKP6AKPEAX@Z0PEAKK_N@Z`
- size: `376`
- prototype: `unsigned int __usercall@<eax>(LPTHREAD_START_ROUTINE lpStartAddress@<rcx>, void *lpParameter@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180055f40`
- `0x18005f8e0`
- `0x180062290`
- `0x180062a80`

## callees

- `0x18002e81c`
- `0x18005200c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800520a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800520a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052120`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005203c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005203c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180052116`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180052116`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052171`

## string_xrefs

- `0x180052064`: `Failed to create thread to execute action! hr = 0x%08x`
- `0x1800520f4`: `ExecuteProcOnThread thread abandoned the thread handle!`
- `0x1800520d7`: `Failed to wait for the ExecuteProcOnThread thread! hr=0x%08X`
- `0x180052084`: `WaaS Remediation agent spawned the thread successfully and %s waiting on it.`
- `0x1800520fd`: `ExecuteProcOnThread thread was signaled!`
- `0x18005214f`: `ExecuteProcOnThread thread launch returning. hr = 0x%08x`
- `0x1800520e6`: `ExecuteProcOnThread thread failed to complete in the given timeout: hr=0x%08X`
- `0x180052132`: `ExecuteProcOnThread failed to get thread exit code! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaaSRemediationAgent::ExecuteProcOnThread(
        LPTHREAD_START_ROUTINE lpStartAddress,
        void *lpParameter,
        unsigned int *a3,
        __int64 a4,
        bool a5)
{
  char *Thread; // rdi
  int LastError; // eax
  const unsigned __int16 *v7; // rdx
  bool v8; // bl
  const wchar_t *v9; // r8
  DWORD v10; // eax
  DWORD v11; // ebx
  DWORD ExitCode; // [rsp+58h] [rbp+20h] BYREF

  ExitCode = 0;
  Thread = (char *)CreateThread(0, 0, lpStartAddress, lpParameter, 0, 0);
  if ( ((unsigned __int64)(Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Failed to create thread to execute action! hr = 0x%08x";
LABEL_22:
    ExitCode = LastError;
    LogLevelW(2u, v7);
    goto LABEL_23;
  }
  v8 = a5;
  v9 = &word_180073298;
  if ( !a5 )
    v9 = L"is not";
  LogLevelW(4u, L"WaaS Remediation agent spawned the thread successfully and %s waiting on it.", v9);
  if ( v8 )
  {
    v10 = WaitForSingleObject(Thread, 0xFFFFFFFF);
    if ( v10 )
    {
      switch ( v10 )
      {
        case 0x80u:
          LogLevelW(4u, L"ExecuteProcOnThread thread abandoned the thread handle!");
          break;
        case 0x102u:
          ExitCode = -2147023436;
          LogLevelW(2u, L"ExecuteProcOnThread thread failed to complete in the given timeout: hr=0x%08X");
          goto LABEL_23;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v7 = L"Failed to wait for the ExecuteProcOnThread thread! hr=0x%08X";
          goto LABEL_22;
      }
    }
    else
    {
      LogLevelW(4u, L"ExecuteProcOnThread thread was signaled!");
    }
    if ( GetExitCodeThread(Thread, &ExitCode) )
      goto LABEL_23;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"ExecuteProcOnThread failed to get thread exit code! hr = 0x%08x";
    goto LABEL_22;
  }
LABEL_23:
  LogLevelW(4u, L"ExecuteProcOnThread thread launch returning. hr = 0x%08x", ExitCode);
  v11 = ExitCode;
  if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Thread);
  return v11;
}

```

## disassembly

```asm
0x18005200c  mov     rax, rsp
0x18005200f  mov     [rax+8], rbx
0x180052013  mov     [rax+20h], r9d
0x180052017  push    rdi
0x180052018  sub     rsp, 30h
0x18005201c  mov     r9, rdx; lpParameter
0x18005201f  mov     qword ptr [rax-10h], 0
0x180052027  mov     r8, rcx; lpStartAddress
0x18005202a  mov     dword ptr [rax+20h], 0
0x180052031  xor     edx, edx; dwStackSize
0x180052033  mov     dword ptr [rax-18h], 0
0x18005203a  xor     ecx, ecx; lpThreadAttributes
0x18005203c  call    cs:__imp_CreateThread
0x180052042  mov     rdi, rax
0x180052045  lea     rcx, [rax+1]
0x180052049  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180052050  jnz     short loc_180052070
0x180052052  call    cs:__imp_GetLastError
0x180052058  test    eax, eax
0x18005205a  jle     short loc_180052064
0x18005205c  movzx   eax, ax
0x18005205f  or      eax, 80070000h
0x180052064  lea     rdx, aFailedToCreate; "Failed to create thread to execute acti"...
0x18005206b  jmp     loc_180052139
0x180052070  mov     bl, [rsp+38h+arg_20]
0x180052074  lea     rax, aIsNot; "is not"
0x18005207b  test    bl, bl
0x18005207d  lea     r8, word_180073298
0x180052084  lea     rdx, aWaasRemediatio_5; "WaaS Remediation agent spawned the thre"...
0x18005208b  mov     ecx, 4; unsigned __int8
0x180052090  cmovz   r8, rax
0x180052094  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180052099  test    bl, bl
0x18005209b  jz      loc_18005214A
0x1800520a1  or      ebx, 0FFFFFFFFh
0x1800520a4  mov     rcx, rdi; hHandle
0x1800520a7  mov     edx, ebx; dwMilliseconds
0x1800520a9  call    cs:__imp_WaitForSingleObject
0x1800520af  test    eax, eax
0x1800520b1  jz      short loc_1800520FD
0x1800520b3  cmp     eax, 80h
0x1800520b8  jz      short loc_1800520F4
0x1800520ba  cmp     eax, 102h
0x1800520bf  jz      short loc_1800520E0
0x1800520c1  cmp     eax, ebx
0x1800520c3  jnz     short loc_18005210E
0x1800520c5  call    cs:__imp_GetLastError
0x1800520cb  test    eax, eax
0x1800520cd  jle     short loc_1800520D7
0x1800520cf  movzx   eax, ax
0x1800520d2  or      eax, 80070000h
0x1800520d7  lea     rdx, aFailedToWaitFo_0; "Failed to wait for the ExecuteProcOnThr"...
0x1800520de  jmp     short loc_180052139
0x1800520e0  mov     r8d, 800705B4h
0x1800520e6  lea     rdx, aExecuteprocont; "ExecuteProcOnThread thread failed to co"...
0x1800520ed  mov     [rsp+38h+ExitCode], r8d
0x1800520f2  jmp     short loc_180052140
0x1800520f4  lea     rdx, aExecuteprocont_0; "ExecuteProcOnThread thread abandoned th"...
0x1800520fb  jmp     short loc_180052104
0x1800520fd  lea     rdx, aExecuteprocont_2; "ExecuteProcOnThread thread was signaled"...
0x180052104  mov     ecx, 4; unsigned __int8
0x180052109  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005210e  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180052113  mov     rcx, rdi; hThread
0x180052116  call    cs:__imp_GetExitCodeThread
0x18005211c  test    eax, eax
0x18005211e  jnz     short loc_18005214A
0x180052120  call    cs:__imp_GetLastError
0x180052126  test    eax, eax
0x180052128  jle     short loc_180052132
0x18005212a  movzx   eax, ax
0x18005212d  or      eax, 80070000h
0x180052132  lea     rdx, aExecuteprocont_3; "ExecuteProcOnThread failed to get threa"...
0x180052139  mov     [rsp+38h+ExitCode], eax
0x18005213d  mov     r8d, eax
0x180052140  mov     ecx, 2; unsigned __int8
0x180052145  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005214a  mov     r8d, [rsp+38h+ExitCode]
0x18005214f  lea     rdx, aExecuteprocont_1; "ExecuteProcOnThread thread launch retur"...
0x180052156  mov     ecx, 4; unsigned __int8
0x18005215b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180052160  mov     ebx, [rsp+38h+ExitCode]
0x180052164  lea     rcx, [rdi-1]
0x180052168  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005216c  ja      short loc_180052177
0x18005216e  mov     rcx, rdi; hObject
0x180052171  call    cs:__imp_CloseHandle
0x180052177  mov     eax, ebx
0x180052179  mov     rbx, [rsp+38h+arg_0]
0x18005217e  add     rsp, 30h
0x180052182  pop     rdi
0x180052183  retn
```
