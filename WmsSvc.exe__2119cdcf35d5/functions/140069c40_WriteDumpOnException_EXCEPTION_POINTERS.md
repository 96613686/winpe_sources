# WriteDumpOnException(_EXCEPTION_POINTERS *)

- ea: `0x140069c40`
- end: `0x140069f0f`
- name: `?WriteDumpOnException@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `719`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140066ac8`
- `0x140069c40`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140069ede`
- `KERNEL32!CloseHandle` at `0x140069ede`
- `KERNEL32!GetCurrentProcessId` at `0x140069dd0`
- `KERNEL32!GetCurrentProcessId` at `0x140069dd0`
- `KERNEL32!GetCurrentThreadId` at `0x140069db9`
- `KERNEL32!GetCurrentThreadId` at `0x140069db9`
- `KERNEL32!CreateFileW` at `0x140069ce7`
- `KERNEL32!CreateFileW` at `0x140069ce7`
- `KERNEL32!GetLastError` at `0x140069cfa`
- `KERNEL32!GetLastError` at `0x140069e16`
- `KERNEL32!GetLastError` at `0x140069cfa`
- `KERNEL32!GetLastError` at `0x140069e16`
- `KERNEL32!IsDebuggerPresent` at `0x140069d50`
- `KERNEL32!IsDebuggerPresent` at `0x140069e6e`
- `KERNEL32!IsDebuggerPresent` at `0x140069d50`
- `KERNEL32!IsDebuggerPresent` at `0x140069e6e`
- `KERNEL32!GetCurrentProcess` at `0x140069dd8`
- `KERNEL32!GetCurrentProcess` at `0x140069dd8`
- `dbghelp!MiniDumpWriteDump` at `0x140069e08`
- `dbghelp!MiniDumpWriteDump` at `0x140069e08`

## string_xrefs

- `0x140069d33`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069d5e`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069d91`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069e46`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069e83`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069eb3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069c80`: `WriteDumpOnExceptionUnhandled exception 0x%08X\n`
- `0x140069d1d`: `WriteDumpOnException`
- `0x140069e39`: `WriteDumpOnException`
- `0x140069cb2`: `WriteDumpOnExceptionCreating dump file:  %s\n`

## pseudocode

```c
__int64 __fastcall WriteDumpOnException(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  PEXCEPTION_RECORD ExceptionRecord; // rdx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v5; // ebx
  DWORD CurrentProcessId; // ebx
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  signed int v9; // ebx
  HANDLE hTemplateFile; // [rsp+30h] [rbp-258h]
  HANDLE hTemplateFilea; // [rsp+30h] [rbp-258h]
  _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(FileName, 0, 0x208u);
  ExceptionRecord = ExceptionInfo->ExceptionRecord;
  ExceptionParam = 0;
  DEBUGMSG(L"WriteDumpOnExceptionUnhandled exception 0x%08X\n", ExceptionRecord->ExceptionCode);
  if ( (int)GenerateDumpFileName(FileName) >= 0 )
  {
    DEBUGMSG(L"WriteDumpOnExceptionCreating dump file:  %s\n", FileName);
    FileW = CreateFileW(FileName, 0x120116u, 0, 0, 2u, 0x80000080, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x7FDu,
        L"WriteDumpOnException",
        L"CBRAEx",
        L"hFile != ((HANDLE)(LONG_PTR)-1)",
        v5);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2045,
          L"WriteDumpOnException",
          L"CBRAEx",
          L"hFile != ((HANDLE)(LONG_PTR)-1)",
          v5);
      }
      else
      {
        LODWORD(hTemplateFile) = v5;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2045,
          L"WriteDumpOnException",
          L"CBRAEx",
          L"hFile != ((HANDLE)(LONG_PTR)-1)",
          hTemplateFile);
      }
    }
    else
    {
      ExceptionParam.ThreadId = GetCurrentThreadId();
      ExceptionParam.ExceptionPointers = ExceptionInfo;
      ExceptionParam.ClientPointers = 1;
      CurrentProcessId = GetCurrentProcessId();
      CurrentProcess = GetCurrentProcess();
      if ( !MiniDumpWriteDump(
              CurrentProcess,
              CurrentProcessId,
              FileW,
              MiniDumpWithTokenInformation|MiniDumpIgnoreInaccessibleMemory|MiniDumpWithThreadInfo|MiniDumpWithFullMemoryInfo|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData|MiniDumpWithFullMemory,
              &ExceptionParam,
              0,
              0) )
      {
        v8 = GetLastError();
        v9 = v8;
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x80Du,
          L"WriteDumpOnException",
          L"CBRAEx",
          L"fSuccess",
          v9);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2061,
            L"WriteDumpOnException",
            L"CBRAEx",
            L"fSuccess",
            v9,
            ExceptionParam);
        }
        else
        {
          LODWORD(hTemplateFilea) = v9;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2061,
            L"WriteDumpOnException",
            L"CBRAEx",
            L"fSuccess",
            hTemplateFilea);
        }
      }
      if ( FileW )
        CloseHandle(FileW);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140069c40  mov     [rsp+arg_8], rbx
0x140069c45  mov     [rsp+arg_10], rbp
0x140069c4a  push    rdi
0x140069c4b  push    r13
0x140069c4d  push    r14
0x140069c4f  sub     rsp, 270h
0x140069c56  mov     rax, cs:__security_cookie
0x140069c5d  xor     rax, rsp
0x140069c60  mov     [rsp+288h+var_28], rax
0x140069c68  mov     rbx, rcx
0x140069c6b  xor     edx, edx; Val
0x140069c6d  lea     rcx, [rsp+288h+FileName]; void *
0x140069c72  mov     r8d, 208h; Size
0x140069c78  call    memset_0
0x140069c7d  mov     rdx, [rbx]
0x140069c80  lea     rcx, aWritedumponexc; "WriteDumpOnExceptionUnhandled exception"...
0x140069c87  xorps   xmm0, xmm0
0x140069c8a  movups  xmmword ptr [rsp+288h+ExceptionParam.ThreadId], xmm0
0x140069c8f  mov     edx, [rdx]
0x140069c91  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069c96  mov     edx, 104h; unsigned __int64
0x140069c9b  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x140069ca0  call    ?GenerateDumpFileName@@YAJPEAG_K@Z; GenerateDumpFileName(ushort *,unsigned __int64)
0x140069ca5  test    eax, eax
0x140069ca7  js      loc_140069EE4
0x140069cad  lea     rdx, [rsp+288h+FileName]
0x140069cb2  lea     rcx, aWritedumponexc_0; "WriteDumpOnExceptionCreating dump file:"...
0x140069cb9  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069cbe  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x140069cc7  lea     rcx, [rsp+288h+FileName]; lpFileName
0x140069ccc  mov     [rsp+288h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x140069cd4  xor     r9d, r9d; lpSecurityAttributes
0x140069cd7  xor     r8d, r8d; dwShareMode
0x140069cda  mov     [rsp+288h+dwCreationDisposition], 2; dwCreationDisposition
0x140069ce2  mov     edx, 120116h; dwDesiredAccess
0x140069ce7  call    cs:__imp_CreateFileW
0x140069ced  mov     rdi, rax
0x140069cf0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140069cf4  jnz     loc_140069DB9
0x140069cfa  call    cs:__imp_GetLastError
0x140069d00  mov     ebx, eax
0x140069d02  test    eax, eax
0x140069d04  jle     short loc_140069D0F
0x140069d06  movzx   ebx, ax
0x140069d09  or      ebx, 80070000h
0x140069d0f  mov     eax, 80004005h
0x140069d14  lea     r14, aCbraex; "CBRAEx"
0x140069d1b  test    ebx, ebx
0x140069d1d  lea     rbp, aWritedumponexc_1; "WriteDumpOnException"
0x140069d24  mov     edi, 7FDh
0x140069d29  lea     r13, aHfileHandleLon; "hFile != ((HANDLE)(LONG_PTR)-1)"
0x140069d30  cmovns  ebx, eax
0x140069d33  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069d3a  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140069d3e  mov     r9, r14; unsigned __int16 *
0x140069d41  mov     r8, rbp; unsigned __int16 *
0x140069d44  mov     qword ptr [rsp+288h+dwCreationDisposition], r13; unsigned __int16 *
0x140069d49  mov     edx, edi; unsigned int
0x140069d4b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069d50  call    cs:__imp_IsDebuggerPresent
0x140069d56  test    eax, eax
0x140069d58  jz      short loc_140069D8D
0x140069d5a  mov     [rsp+288h+var_250], ebx
0x140069d5e  lea     r8, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069d65  mov     [rsp+288h+hTemplateFile], r13
0x140069d6a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140069d71  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r14
0x140069d76  mov     r9d, edi
0x140069d79  mov     ecx, 2; unsigned __int8
0x140069d7e  mov     qword ptr [rsp+288h+dwCreationDisposition], rbp
0x140069d83  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140069d88  jmp     loc_140069EE4
0x140069d8d  mov     dword ptr [rsp+288h+hTemplateFile], ebx
0x140069d91  lea     rdx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069d98  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r13
0x140069d9d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140069da4  mov     r9, rbp
0x140069da7  mov     qword ptr [rsp+288h+dwCreationDisposition], r14
0x140069dac  mov     r8d, edi
0x140069daf  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140069db4  jmp     loc_140069EE4
0x140069db9  call    cs:__imp_GetCurrentThreadId
0x140069dbf  mov     [rsp+288h+ExceptionParam.ThreadId], eax
0x140069dc3  mov     [rsp+288h+ExceptionParam.ExceptionPointers], rbx
0x140069dc8  mov     [rsp+288h+ExceptionParam.ClientPointers], 1
0x140069dd0  call    cs:__imp_GetCurrentProcessId
0x140069dd6  mov     ebx, eax
0x140069dd8  call    cs:__imp_GetCurrentProcess
0x140069dde  lea     rcx, [rsp+288h+ExceptionParam]
0x140069de3  mov     [rsp+288h+hTemplateFile], 0; CallbackParam
0x140069dec  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], 0; UserStreamParam
0x140069df5  mov     r9d, 61926h; DumpType
0x140069dfb  mov     qword ptr [rsp+288h+dwCreationDisposition], rcx; ExceptionParam
0x140069e00  mov     r8, rdi; hFile
0x140069e03  mov     rcx, rax; hProcess
0x140069e06  mov     edx, ebx; ProcessId
0x140069e08  call    cs:__imp_MiniDumpWriteDump
0x140069e0e  test    eax, eax
0x140069e10  jnz     loc_140069ED6
0x140069e16  call    cs:__imp_GetLastError
0x140069e1c  mov     ebx, eax
0x140069e1e  test    eax, eax
0x140069e20  jle     short loc_140069E2B
0x140069e22  movzx   ebx, ax
0x140069e25  or      ebx, 80070000h
0x140069e2b  mov     eax, 80004005h
0x140069e30  lea     r14, aCbraex; "CBRAEx"
0x140069e37  test    ebx, ebx
0x140069e39  lea     rbp, aWritedumponexc_1; "WriteDumpOnException"
0x140069e40  mov     r13d, 80Dh
0x140069e46  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069e4d  cmovns  ebx, eax
0x140069e50  mov     r9, r14; unsigned __int16 *
0x140069e53  lea     rax, aFsuccess; "fSuccess"
0x140069e5a  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140069e5e  mov     r8, rbp; unsigned __int16 *
0x140069e61  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; unsigned __int16 *
0x140069e66  mov     edx, r13d; unsigned int
0x140069e69  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069e6e  call    cs:__imp_IsDebuggerPresent
0x140069e74  test    eax, eax
0x140069e76  lea     rax, aFsuccess; "fSuccess"
0x140069e7d  jz      short loc_140069EAF
0x140069e7f  mov     [rsp+288h+var_250], ebx
0x140069e83  lea     r8, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069e8a  mov     [rsp+288h+hTemplateFile], rax
0x140069e8f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140069e96  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r14
0x140069e9b  mov     r9d, r13d
0x140069e9e  mov     ecx, 2; unsigned __int8
0x140069ea3  mov     qword ptr [rsp+288h+dwCreationDisposition], rbp
0x140069ea8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140069ead  jmp     short loc_140069ED6
0x140069eaf  mov     dword ptr [rsp+288h+hTemplateFile], ebx
0x140069eb3  lea     rdx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069eba  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rax
0x140069ebf  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140069ec6  mov     r9, rbp
0x140069ec9  mov     qword ptr [rsp+288h+dwCreationDisposition], r14
0x140069ece  mov     r8d, r13d
0x140069ed1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140069ed6  test    rdi, rdi
0x140069ed9  jz      short loc_140069EE4
0x140069edb  mov     rcx, rdi; hObject
0x140069ede  call    cs:__imp_CloseHandle
0x140069ee4  xor     eax, eax
0x140069ee6  mov     rcx, [rsp+288h+var_28]
0x140069eee  xor     rcx, rsp; StackCookie
0x140069ef1  call    __security_check_cookie
0x140069ef6  lea     r11, [rsp+288h+var_18]
0x140069efe  mov     rbx, [r11+28h]
0x140069f02  mov     rbp, [r11+30h]
0x140069f06  mov     rsp, r11
0x140069f09  pop     r14
0x140069f0b  pop     r13
0x140069f0d  pop     rdi
0x140069f0e  retn
```
