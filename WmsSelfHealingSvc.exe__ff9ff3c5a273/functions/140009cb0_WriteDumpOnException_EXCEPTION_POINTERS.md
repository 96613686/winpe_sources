# WriteDumpOnException(_EXCEPTION_POINTERS *)

- ea: `0x140009cb0`
- end: `0x140009f7f`
- name: `?WriteDumpOnException@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x1400076e0`
- `0x140009cb0`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140009d57`
- `KERNEL32!CreateFileW` at `0x140009d57`
- `KERNEL32!IsDebuggerPresent` at `0x140009dc0`
- `KERNEL32!IsDebuggerPresent` at `0x140009ede`
- `KERNEL32!IsDebuggerPresent` at `0x140009dc0`
- `KERNEL32!IsDebuggerPresent` at `0x140009ede`
- `KERNEL32!GetLastError` at `0x140009d6a`
- `KERNEL32!GetLastError` at `0x140009e86`
- `KERNEL32!GetLastError` at `0x140009d6a`
- `KERNEL32!GetLastError` at `0x140009e86`
- `KERNEL32!CloseHandle` at `0x140009f4e`
- `KERNEL32!CloseHandle` at `0x140009f4e`
- `KERNEL32!GetCurrentProcessId` at `0x140009e40`
- `KERNEL32!GetCurrentProcessId` at `0x140009e40`
- `KERNEL32!GetCurrentThreadId` at `0x140009e29`
- `KERNEL32!GetCurrentThreadId` at `0x140009e29`
- `KERNEL32!GetCurrentProcess` at `0x140009e48`
- `KERNEL32!GetCurrentProcess` at `0x140009e48`
- `dbghelp!MiniDumpWriteDump` at `0x140009e78`
- `dbghelp!MiniDumpWriteDump` at `0x140009e78`

## string_xrefs

- `0x140009da3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009dce`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009e01`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009eb6`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009ef3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009f23`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009cf0`: `WriteDumpOnExceptionUnhandled exception 0x%08X\n`
- `0x140009d8d`: `WriteDumpOnException`
- `0x140009ea9`: `WriteDumpOnException`
- `0x140009d22`: `WriteDumpOnExceptionCreating dump file:  %s\n`

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
  if ( (int)GenerateDumpFileName(FileName, 0x104u) >= 0 )
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
0x140009cb0  mov     [rsp+arg_8], rbx
0x140009cb5  mov     [rsp+arg_10], rbp
0x140009cba  push    rdi
0x140009cbb  push    r13
0x140009cbd  push    r14
0x140009cbf  sub     rsp, 270h
0x140009cc6  mov     rax, cs:__security_cookie
0x140009ccd  xor     rax, rsp
0x140009cd0  mov     [rsp+288h+var_28], rax
0x140009cd8  mov     rbx, rcx
0x140009cdb  xor     edx, edx; Val
0x140009cdd  lea     rcx, [rsp+288h+FileName]; void *
0x140009ce2  mov     r8d, 208h; Size
0x140009ce8  call    memset_0
0x140009ced  mov     rdx, [rbx]
0x140009cf0  lea     rcx, aWritedumponexc; "WriteDumpOnExceptionUnhandled exception"...
0x140009cf7  xorps   xmm0, xmm0
0x140009cfa  movups  xmmword ptr [rsp+288h+ExceptionParam.ThreadId], xmm0
0x140009cff  mov     edx, [rdx]
0x140009d01  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009d06  mov     edx, 104h; unsigned __int64
0x140009d0b  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x140009d10  call    ?GenerateDumpFileName@@YAJPEAG_K@Z; GenerateDumpFileName(ushort *,unsigned __int64)
0x140009d15  test    eax, eax
0x140009d17  js      loc_140009F54
0x140009d1d  lea     rdx, [rsp+288h+FileName]
0x140009d22  lea     rcx, aWritedumponexc_0; "WriteDumpOnExceptionCreating dump file:"...
0x140009d29  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009d2e  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x140009d37  lea     rcx, [rsp+288h+FileName]; lpFileName
0x140009d3c  mov     [rsp+288h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x140009d44  xor     r9d, r9d; lpSecurityAttributes
0x140009d47  xor     r8d, r8d; dwShareMode
0x140009d4a  mov     [rsp+288h+dwCreationDisposition], 2; dwCreationDisposition
0x140009d52  mov     edx, 120116h; dwDesiredAccess
0x140009d57  call    cs:__imp_CreateFileW
0x140009d5d  mov     rdi, rax
0x140009d60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009d64  jnz     loc_140009E29
0x140009d6a  call    cs:__imp_GetLastError
0x140009d70  mov     ebx, eax
0x140009d72  test    eax, eax
0x140009d74  jle     short loc_140009D7F
0x140009d76  movzx   ebx, ax
0x140009d79  or      ebx, 80070000h
0x140009d7f  mov     eax, 80004005h
0x140009d84  lea     r14, aCbraex; "CBRAEx"
0x140009d8b  test    ebx, ebx
0x140009d8d  lea     rbp, aWritedumponexc_1; "WriteDumpOnException"
0x140009d94  mov     edi, 7FDh
0x140009d99  lea     r13, aHfileHandleLon; "hFile != ((HANDLE)(LONG_PTR)-1)"
0x140009da0  cmovns  ebx, eax
0x140009da3  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009daa  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140009dae  mov     r9, r14; unsigned __int16 *
0x140009db1  mov     r8, rbp; unsigned __int16 *
0x140009db4  mov     qword ptr [rsp+288h+dwCreationDisposition], r13; unsigned __int16 *
0x140009db9  mov     edx, edi; unsigned int
0x140009dbb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009dc0  call    cs:__imp_IsDebuggerPresent
0x140009dc6  test    eax, eax
0x140009dc8  jz      short loc_140009DFD
0x140009dca  mov     [rsp+288h+var_250], ebx
0x140009dce  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009dd5  mov     [rsp+288h+hTemplateFile], r13
0x140009dda  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009de1  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r14
0x140009de6  mov     r9d, edi
0x140009de9  mov     ecx, 2; unsigned __int8
0x140009dee  mov     qword ptr [rsp+288h+dwCreationDisposition], rbp
0x140009df3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009df8  jmp     loc_140009F54
0x140009dfd  mov     dword ptr [rsp+288h+hTemplateFile], ebx
0x140009e01  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009e08  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r13
0x140009e0d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009e14  mov     r9, rbp
0x140009e17  mov     qword ptr [rsp+288h+dwCreationDisposition], r14
0x140009e1c  mov     r8d, edi
0x140009e1f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009e24  jmp     loc_140009F54
0x140009e29  call    cs:__imp_GetCurrentThreadId
0x140009e2f  mov     [rsp+288h+ExceptionParam.ThreadId], eax
0x140009e33  mov     [rsp+288h+ExceptionParam.ExceptionPointers], rbx
0x140009e38  mov     [rsp+288h+ExceptionParam.ClientPointers], 1
0x140009e40  call    cs:__imp_GetCurrentProcessId
0x140009e46  mov     ebx, eax
0x140009e48  call    cs:__imp_GetCurrentProcess
0x140009e4e  lea     rcx, [rsp+288h+ExceptionParam]
0x140009e53  mov     [rsp+288h+hTemplateFile], 0; CallbackParam
0x140009e5c  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], 0; UserStreamParam
0x140009e65  mov     r9d, 61926h; DumpType
0x140009e6b  mov     qword ptr [rsp+288h+dwCreationDisposition], rcx; ExceptionParam
0x140009e70  mov     r8, rdi; hFile
0x140009e73  mov     rcx, rax; hProcess
0x140009e76  mov     edx, ebx; ProcessId
0x140009e78  call    cs:__imp_MiniDumpWriteDump
0x140009e7e  test    eax, eax
0x140009e80  jnz     loc_140009F46
0x140009e86  call    cs:__imp_GetLastError
0x140009e8c  mov     ebx, eax
0x140009e8e  test    eax, eax
0x140009e90  jle     short loc_140009E9B
0x140009e92  movzx   ebx, ax
0x140009e95  or      ebx, 80070000h
0x140009e9b  mov     eax, 80004005h
0x140009ea0  lea     r14, aCbraex; "CBRAEx"
0x140009ea7  test    ebx, ebx
0x140009ea9  lea     rbp, aWritedumponexc_1; "WriteDumpOnException"
0x140009eb0  mov     r13d, 80Dh
0x140009eb6  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009ebd  cmovns  ebx, eax
0x140009ec0  mov     r9, r14; unsigned __int16 *
0x140009ec3  lea     rax, aFsuccess; "fSuccess"
0x140009eca  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140009ece  mov     r8, rbp; unsigned __int16 *
0x140009ed1  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; unsigned __int16 *
0x140009ed6  mov     edx, r13d; unsigned int
0x140009ed9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009ede  call    cs:__imp_IsDebuggerPresent
0x140009ee4  test    eax, eax
0x140009ee6  lea     rax, aFsuccess; "fSuccess"
0x140009eed  jz      short loc_140009F1F
0x140009eef  mov     [rsp+288h+var_250], ebx
0x140009ef3  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009efa  mov     [rsp+288h+hTemplateFile], rax
0x140009eff  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009f06  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r14
0x140009f0b  mov     r9d, r13d
0x140009f0e  mov     ecx, 2; unsigned __int8
0x140009f13  mov     qword ptr [rsp+288h+dwCreationDisposition], rbp
0x140009f18  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009f1d  jmp     short loc_140009F46
0x140009f1f  mov     dword ptr [rsp+288h+hTemplateFile], ebx
0x140009f23  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009f2a  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rax
0x140009f2f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009f36  mov     r9, rbp
0x140009f39  mov     qword ptr [rsp+288h+dwCreationDisposition], r14
0x140009f3e  mov     r8d, r13d
0x140009f41  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009f46  test    rdi, rdi
0x140009f49  jz      short loc_140009F54
0x140009f4b  mov     rcx, rdi; hObject
0x140009f4e  call    cs:__imp_CloseHandle
0x140009f54  xor     eax, eax
0x140009f56  mov     rcx, [rsp+288h+var_28]
0x140009f5e  xor     rcx, rsp; StackCookie
0x140009f61  call    __security_check_cookie
0x140009f66  lea     r11, [rsp+288h+var_18]
0x140009f6e  mov     rbx, [r11+28h]
0x140009f72  mov     rbp, [r11+30h]
0x140009f76  mov     rsp, r11
0x140009f79  pop     r14
0x140009f7b  pop     r13
0x140009f7d  pop     rdi
0x140009f7e  retn
```
