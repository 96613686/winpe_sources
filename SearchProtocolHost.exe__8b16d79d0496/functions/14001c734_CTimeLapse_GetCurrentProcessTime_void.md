# CTimeLapse::GetCurrentProcessTime(void)

- ea: `0x14001c734`
- end: `0x14001c7e2`
- name: `?GetCurrentProcessTime@CTimeLapse@@AEAA_KXZ`
- size: `174`
- prototype: `unsigned __int64 __fastcall(CTimeLapse *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x14001c734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c7b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c78e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c78e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14001c7ac`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14001c7ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c768`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x14001c786`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x14001c786`

## pseudocode

```c
__int64 __fastcall CTimeLapse::GetCurrentProcessTime(CTimeLapse *this)
{
  bool v1; // zf
  HANDLE CurrentThread; // rax
  BOOL ProcessTimes; // eax
  HANDLE CurrentProcess; // rax
  __int64 v6; // rbx
  signed int LastError; // eax
  struct _FILETIME UserTime; // [rsp+50h] [rbp+20h] BYREF
  struct _FILETIME KernelTime; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME ExitTime; // [rsp+60h] [rbp+30h] BYREF
  struct _FILETIME CreationTime; // [rsp+68h] [rbp+38h] BYREF

  v1 = *((_BYTE *)this + 1) == 0;
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( v1 )
  {
    CurrentProcess = GetCurrentProcess();
    ProcessTimes = GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    ProcessTimes = GetThreadTimes(CurrentThread, &CreationTime, &ExitTime, &KernelTime, &UserTime);
  }
  if ( ProcessTimes )
    return *(_QWORD *)&UserTime + *(_QWORD *)&KernelTime;
  v6 = 0;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  *((_DWORD *)this + 6) = LastError;
  return v6;
}

```

## disassembly

```asm
0x14001c734  push    rbp
0x14001c736  push    rbx
0x14001c737  push    rdi
0x14001c738  mov     rbp, rsp
0x14001c73b  sub     rsp, 30h
0x14001c73f  cmp     byte ptr [rcx+1], 0
0x14001c743  mov     rdi, rcx
0x14001c746  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x14001c74e  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x14001c756  mov     qword ptr [rbp+KernelTime.dwLowDateTime], 0
0x14001c75e  mov     qword ptr [rbp+UserTime.dwLowDateTime], 0
0x14001c766  jz      short loc_14001C78E
0x14001c768  call    cs:__imp_GetCurrentThread
0x14001c76e  mov     rcx, rax; hThread
0x14001c771  lea     r9, [rbp+KernelTime]; lpKernelTime
0x14001c775  lea     rax, [rbp+UserTime]
0x14001c779  lea     r8, [rbp+ExitTime]; lpExitTime
0x14001c77d  mov     [rsp+30h+lpUserTime], rax; lpUserTime
0x14001c782  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14001c786  call    cs:__imp_GetThreadTimes
0x14001c78c  jmp     short loc_14001C7B2
0x14001c78e  call    cs:__imp_GetCurrentProcess
0x14001c794  mov     rcx, rax; hProcess
0x14001c797  lea     r9, [rbp+KernelTime]; lpKernelTime
0x14001c79b  lea     rax, [rbp+UserTime]
0x14001c79f  lea     r8, [rbp+ExitTime]; lpExitTime
0x14001c7a3  mov     [rsp+30h+lpUserTime], rax; lpUserTime
0x14001c7a8  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14001c7ac  call    cs:__imp_GetProcessTimes
0x14001c7b2  test    eax, eax
0x14001c7b4  jnz     short loc_14001C7CF
0x14001c7b6  xor     ebx, ebx
0x14001c7b8  call    cs:__imp_GetLastError
0x14001c7be  test    eax, eax
0x14001c7c0  jle     short loc_14001C7CA
0x14001c7c2  movzx   eax, ax
0x14001c7c5  or      eax, 80070000h
0x14001c7ca  mov     [rdi+18h], eax
0x14001c7cd  jmp     short loc_14001C7D7
0x14001c7cf  mov     rbx, qword ptr [rbp+KernelTime.dwLowDateTime]
0x14001c7d3  add     rbx, qword ptr [rbp+UserTime.dwLowDateTime]
0x14001c7d7  mov     rax, rbx
0x14001c7da  add     rsp, 30h
0x14001c7de  pop     rdi
0x14001c7df  pop     rbx
0x14001c7e0  pop     rbp
0x14001c7e1  retn
```
