# CTimeLapse::GetCurrentProcessTime(void)

- ea: `0x14001fdfc`
- end: `0x14001feaa`
- name: `?GetCurrentProcessTime@CTimeLapse@@AEAA_KXZ`
- size: `174`
- prototype: `unsigned __int64 __fastcall(CTimeLapse *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b418`
- `0x14001f490`
- `0x140020eb0`
- `0x140021210`

## callees

- `0x14001fdfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001fe30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001fe30`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14001fe74`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14001fe74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001fe56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001fe56`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x14001fe4e`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x14001fe4e`

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
0x14001fdfc  push    rbp
0x14001fdfe  push    rbx
0x14001fdff  push    rdi
0x14001fe00  mov     rbp, rsp
0x14001fe03  sub     rsp, 30h
0x14001fe07  cmp     byte ptr [rcx+1], 0
0x14001fe0b  mov     rdi, rcx
0x14001fe0e  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x14001fe16  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x14001fe1e  mov     qword ptr [rbp+KernelTime.dwLowDateTime], 0
0x14001fe26  mov     qword ptr [rbp+UserTime.dwLowDateTime], 0
0x14001fe2e  jz      short loc_14001FE56
0x14001fe30  call    cs:__imp_GetCurrentThread
0x14001fe36  mov     rcx, rax; hThread
0x14001fe39  lea     r9, [rbp+KernelTime]; lpKernelTime
0x14001fe3d  lea     rax, [rbp+UserTime]
0x14001fe41  lea     r8, [rbp+ExitTime]; lpExitTime
0x14001fe45  mov     [rsp+30h+lpUserTime], rax; lpUserTime
0x14001fe4a  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14001fe4e  call    cs:__imp_GetThreadTimes
0x14001fe54  jmp     short loc_14001FE7A
0x14001fe56  call    cs:__imp_GetCurrentProcess
0x14001fe5c  mov     rcx, rax; hProcess
0x14001fe5f  lea     r9, [rbp+KernelTime]; lpKernelTime
0x14001fe63  lea     rax, [rbp+UserTime]
0x14001fe67  lea     r8, [rbp+ExitTime]; lpExitTime
0x14001fe6b  mov     [rsp+30h+lpUserTime], rax; lpUserTime
0x14001fe70  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14001fe74  call    cs:__imp_GetProcessTimes
0x14001fe7a  test    eax, eax
0x14001fe7c  jnz     short loc_14001FE97
0x14001fe7e  xor     ebx, ebx
0x14001fe80  call    cs:__imp_GetLastError
0x14001fe86  test    eax, eax
0x14001fe88  jle     short loc_14001FE92
0x14001fe8a  movzx   eax, ax
0x14001fe8d  or      eax, 80070000h
0x14001fe92  mov     [rdi+18h], eax
0x14001fe95  jmp     short loc_14001FE9F
0x14001fe97  mov     rbx, qword ptr [rbp+KernelTime.dwLowDateTime]
0x14001fe9b  add     rbx, qword ptr [rbp+UserTime.dwLowDateTime]
0x14001fe9f  mov     rax, rbx
0x14001fea2  add     rsp, 30h
0x14001fea6  pop     rdi
0x14001fea7  pop     rbx
0x14001fea8  pop     rbp
0x14001fea9  retn
```
