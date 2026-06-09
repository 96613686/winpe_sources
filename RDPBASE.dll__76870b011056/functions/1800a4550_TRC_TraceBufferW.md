# TRC_TraceBufferW

- ea: `0x1800a4550`
- end: `0x1800a468f`
- name: `TRC_TraceBufferW`
- size: `319`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, STRSAFE_LPCWSTR pszFormat, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800506f4`
- `0x18006e6a8`
- `0x180078c20`
- `0x1800a4550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a4600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a4600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a45f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a45f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a45b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a45b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a45a0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a45a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a4666`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a4666`

## pseudocode

```c
void TRC_TraceBufferW(int a1, int a2, int a3, __int64 a4, int a5, int a6, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t *v7; // r8
  int wMilliseconds; // edi
  int wSecond; // esi
  int wMinute; // r14d
  int wHour; // r15d
  int wDay; // r12d
  int wMonth; // r13d
  va_list argList; // [rsp+20h] [rbp-E0h]
  DWORD CurrentProcessId; // [rsp+50h] [rbp-B0h]
  DWORD CurrentThreadId; // [rsp+58h] [rbp-A8h]
  unsigned int wYear; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  wchar_t pszDest[128]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR OutputString[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  va_list va; // [rsp+448h] [rbp+348h] BYREF

  va_start(va, pszFormat);
  SystemTime = 0;
  if ( a1 == 4 )
  {
    DebugBreak();
  }
  else if ( a1 != 3 )
  {
    return;
  }
  GetSystemTime(&SystemTime);
  StringVPrintfWorkerW(pszDest, 0x80u, v7, pszFormat, va);
  wMilliseconds = SystemTime.wMilliseconds;
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  wYear = SystemTime.wYear;
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(argList) = wMonth;
  StringCchPrintfW(
    OutputString,
    0xFFu,
    L"%04d-%02d-%02d %02d:%02d:%02d.%03d PID:0x%x TID:0x%x L:%04d:%s - %s\r\n",
    wYear,
    argList,
    wDay,
    wHour,
    wMinute,
    wSecond,
    wMilliseconds,
    CurrentProcessId,
    CurrentThreadId,
    a3,
    a4,
    pszDest);
  OutputDebugStringW(OutputString);
}

```

## disassembly

```asm
0x1800a4550  push    rbp
0x1800a4552  push    rbx
0x1800a4553  push    rsi
0x1800a4554  push    rdi
0x1800a4555  push    r12
0x1800a4557  push    r13
0x1800a4559  push    r14
0x1800a455b  push    r15
0x1800a455d  lea     rbp, [rsp-2C8h]
0x1800a4565  sub     rsp, 3C8h
0x1800a456c  mov     rax, cs:__security_cookie
0x1800a4573  xor     rax, rsp
0x1800a4576  mov     [rbp+300h+var_50], rax
0x1800a457d  mov     [rbp+300h+var_370], r9
0x1800a4581  xorps   xmm0, xmm0
0x1800a4584  mov     [rbp+300h+var_380], r8d
0x1800a4588  lea     rbx, [rbp+300h+arg_38]
0x1800a458f  mov     [rbp+300h+var_378], 0
0x1800a4597  movups  xmmword ptr [rbp+300h+SystemTime.wYear], xmm0
0x1800a459b  cmp     ecx, 4
0x1800a459e  jnz     short loc_1800A45A8
0x1800a45a0  call    cs:__imp_DebugBreak
0x1800a45a6  jmp     short loc_1800A45B1
0x1800a45a8  cmp     ecx, 3
0x1800a45ab  jnz     loc_1800A466C
0x1800a45b1  lea     rcx, [rbp+300h+SystemTime]; lpSystemTime
0x1800a45b5  call    cs:__imp_GetSystemTime
0x1800a45bb  mov     r9, [rbp+300h+pszFormat]; pszFormat
0x1800a45c2  lea     rcx, [rbp+300h+pszDest]; pszDest
0x1800a45c6  mov     edx, 80h; cchDest
0x1800a45cb  mov     [rsp+400h+argList], rbx; argList
0x1800a45d0  call    StringVPrintfWorkerW
0x1800a45d5  movzx   eax, [rbp+300h+SystemTime.wYear]
0x1800a45d9  movzx   edi, [rbp+300h+SystemTime.wMilliseconds]
0x1800a45dd  movzx   esi, [rbp+300h+SystemTime.wSecond]
0x1800a45e1  movzx   r14d, [rbp+300h+SystemTime.wMinute]
0x1800a45e6  movzx   r15d, [rbp+300h+SystemTime.wHour]
0x1800a45eb  movzx   r12d, [rbp+300h+SystemTime.wDay]
0x1800a45f0  movzx   r13d, [rbp+300h+SystemTime.wMonth]
0x1800a45f5  mov     dword ptr [rbp+300h+var_378], eax
0x1800a45f8  call    cs:__imp_GetCurrentThreadId
0x1800a45fe  mov     ebx, eax
0x1800a4600  call    cs:__imp_GetCurrentProcessId
0x1800a4606  mov     r9d, dword ptr [rbp+300h+var_378]
0x1800a460a  lea     rcx, [rbp+300h+pszDest]
0x1800a460e  mov     [rsp+400h+var_390], rcx
0x1800a4613  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d.%03d PID:"...
0x1800a461a  mov     rcx, [rbp+300h+var_370]
0x1800a461e  mov     edx, 0FFh; unsigned __int64
0x1800a4623  mov     [rsp+400h+var_398], rcx
0x1800a4628  mov     ecx, [rbp+300h+var_380]
0x1800a462b  mov     [rsp+400h+var_3A0], ecx
0x1800a462f  lea     rcx, [rbp+300h+OutputString]; unsigned __int16 *
0x1800a4636  mov     [rsp+400h+var_3A8], ebx
0x1800a463a  mov     [rsp+400h+var_3B0], eax
0x1800a463e  mov     [rsp+400h+var_3B8], edi
0x1800a4642  mov     [rsp+400h+var_3C0], esi
0x1800a4646  mov     [rsp+400h+var_3C8], r14d
0x1800a464b  mov     [rsp+400h+var_3D0], r15d
0x1800a4650  mov     [rsp+400h+var_3D8], r12d
0x1800a4655  mov     dword ptr [rsp+400h+argList], r13d
0x1800a465a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a465f  lea     rcx, [rbp+300h+OutputString]; lpOutputString
0x1800a4666  call    cs:__imp_OutputDebugStringW
0x1800a466c  mov     rcx, [rbp+300h+var_50]
0x1800a4673  xor     rcx, rsp; StackCookie
0x1800a4676  call    __security_check_cookie
0x1800a467b  add     rsp, 3C8h
0x1800a4682  pop     r15
0x1800a4684  pop     r14
0x1800a4686  pop     r13
0x1800a4688  pop     r12
0x1800a468a  pop     rdi
0x1800a468b  pop     rsi
0x1800a468c  pop     rbx
0x1800a468d  pop     rbp
0x1800a468e  retn
```
