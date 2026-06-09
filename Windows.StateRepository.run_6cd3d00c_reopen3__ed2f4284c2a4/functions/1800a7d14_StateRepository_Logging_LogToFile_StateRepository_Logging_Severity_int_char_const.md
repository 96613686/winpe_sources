# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x1800a7d14`
- end: `0x1800a8147`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1075`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180263fd0`
- `0x1802641f0`
- `0x180264250`

## callees

- `0x180068c44`
- `0x1800a7d14`
- `0x1800ae814`
- `0x18018f650`
- `0x180190234`
- `0x180263c8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7efa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a800d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7efa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a800d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7ef1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a808c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7ef1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a808c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a7d6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a7d6e`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a7e80`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a7ff9`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a8081`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a810e`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a7e80`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a7ff9`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a8081`
- `StateRepository.Core!sqlite3_snprintf` at `0x1800a810e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800a7ea7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800a7ea7`

## string_xrefs

- `0x1800a7dca`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
void __fastcall StateRepository::Logging::LogToFile(unsigned int a1, int a2, const char *a3)
{
  char v3; // di
  DWORD v7; // ebx
  DWORD v8; // eax
  const char *v9; // rdx
  PVOID v10; // rbx
  PVOID v11; // rdi
  PVOID v12; // rsi
  PVOID v13; // r14
  PVOID v14; // r15
  PVOID v15; // r12
  PVOID v16; // r13
  DWORD v17; // eax
  DWORD CurrentThreadId; // r15d
  DWORD CurrentProcessId; // eax
  DWORD v20; // ebx
  DWORD v21; // eax
  const char *v22; // [rsp+28h] [rbp-138h]
  DWORD v23; // [rsp+E0h] [rbp-80h]
  const char *v25; // [rsp+E8h] [rbp-78h]
  PVOID v26; // [rsp+F0h] [rbp-70h]
  PVOID v27; // [rsp+F8h] [rbp-68h]
  PVOID v28; // [rsp+100h] [rbp-60h]
  PVOID v29; // [rsp+108h] [rbp-58h]
  PVOID v30; // [rsp+110h] [rbp-50h]
  _SYSTEMTIME SystemTime; // [rsp+120h] [rbp-40h] BYREF
  PVOID BackTrace[12]; // [rsp+130h] [rbp-30h] BYREF
  _BYTE Buffer[2048]; // [rsp+190h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+878h]

  v3 = dword_1804DF348;
  if ( (dword_1804DF348 & 1) != 0 )
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( a1 )
    {
      if ( a1 == 16 )
      {
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        sqlite3_snprintf(
          2048,
          Buffer,
          "%02u%02u%02u %02u%02u%02u.%03u [Trace] P%x T%x: %s\r\n",
          SystemTime.wYear % 0x64u,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds,
          CurrentProcessId,
          CurrentThreadId,
          a3);
      }
      else
      {
        if ( a1 != 32 && a1 != 33 && a1 != 34 && a1 - 35 >= 2 )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
            (const char *)0x8000FFFFLL,
            (int)"LogToFile(severity=Unknown,...)",
            v22);
          return;
        }
        v25 = (const char *)StateRepository::Logging::SeverityToString(a1);
        if ( (v3 & 2) != 0 )
        {
          v7 = GetCurrentThreadId();
          v8 = GetCurrentProcessId();
          sqlite3_snprintf(
            2048,
            Buffer,
            "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%08X] P%x T%x: %s\r\n",
            SystemTime.wYear % 0x64u,
            SystemTime.wMonth,
            SystemTime.wDay,
            SystemTime.wHour,
            SystemTime.wMinute,
            SystemTime.wSecond,
            SystemTime.wMilliseconds,
            v25,
            a2,
            v8,
            v7,
            a3);
        }
        else
        {
          memset_0(BackTrace, 0, sizeof(BackTrace));
          RtlCaptureStackBackTrace(0, 0xCu, BackTrace, 0);
          v10 = BackTrace[11];
          v11 = BackTrace[10];
          v12 = BackTrace[9];
          v13 = BackTrace[8];
          v14 = BackTrace[7];
          v15 = BackTrace[6];
          v16 = BackTrace[5];
          v26 = BackTrace[4];
          v27 = BackTrace[3];
          v28 = BackTrace[2];
          v29 = BackTrace[1];
          v30 = BackTrace[0];
          v23 = GetCurrentThreadId();
          v17 = GetCurrentProcessId();
          sqlite3_snprintf(
            2048,
            Buffer,
            "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%08X] P%x T%x: %s\r\n"
            "                                     Callstack: %p %p %p %p %p %p %p %p %p %p %p %p\r\n",
            SystemTime.wYear % 0x64u,
            SystemTime.wMonth,
            SystemTime.wDay,
            SystemTime.wHour,
            SystemTime.wMinute,
            SystemTime.wSecond,
            SystemTime.wMilliseconds,
            v25,
            a2,
            v17,
            v23,
            a3,
            v30,
            v29,
            v28,
            v27,
            v26,
            v16,
            v15,
            v14,
            v13,
            v12,
            v11,
            v10);
        }
      }
    }
    else
    {
      v20 = GetCurrentThreadId();
      v21 = GetCurrentProcessId();
      sqlite3_snprintf(
        2048,
        Buffer,
        "%02u%02u%02u %02u%02u%02u.%03u [Profile %ums] P%x T%x: %s\r\n",
        SystemTime.wYear % 0x64u,
        SystemTime.wMonth,
        SystemTime.wDay,
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond,
        SystemTime.wMilliseconds,
        a2,
        v21,
        v20,
        a3);
    }
    StateRepository::Logging::WriteLogToFile(Buffer, v9);
  }
}

```

## disassembly

```asm
0x1800a7d14  mov     [rsp-8+arg_18], rbx
0x1800a7d19  push    rbp
0x1800a7d1a  push    rsi
0x1800a7d1b  push    rdi
0x1800a7d1c  push    r12
0x1800a7d1e  push    r13
0x1800a7d20  push    r14
0x1800a7d22  push    r15
0x1800a7d24  lea     rbp, [rsp-840h]
0x1800a7d2c  sub     rsp, 9A0h
0x1800a7d33  mov     rax, cs:__security_cookie
0x1800a7d3a  xor     rax, rsp
0x1800a7d3d  mov     [rbp+870h+var_40], rax
0x1800a7d44  mov     edi, cs:dword_1804DF348
0x1800a7d4a  mov     r12, r8
0x1800a7d4d  mov     [rbp+870h+var_8B8], r8
0x1800a7d51  mov     r13d, edx
0x1800a7d54  mov     [rbp+870h+var_8EC], edx
0x1800a7d57  mov     ebx, ecx
0x1800a7d59  test    dil, 1
0x1800a7d5d  jz      loc_1800A811D
0x1800a7d63  xorps   xmm0, xmm0
0x1800a7d66  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x1800a7d6a  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x1800a7d6e  call    cs:__imp_GetLocalTime
0x1800a7d74  xor     edx, edx; Val
0x1800a7d76  lea     rcx, [rbp+870h+Buffer]; void *
0x1800a7d7a  mov     r8d, 800h; Size
0x1800a7d80  call    memset_0
0x1800a7d85  mov     ecx, ebx
0x1800a7d87  test    ebx, ebx
0x1800a7d89  jz      loc_1800A808C
0x1800a7d8f  sub     ecx, 10h
0x1800a7d92  jz      loc_1800A8004
0x1800a7d98  sub     ecx, 10h
0x1800a7d9b  jz      short loc_1800A7DE0
0x1800a7d9d  sub     ecx, 1
0x1800a7da0  jz      short loc_1800A7DE0
0x1800a7da2  sub     ecx, 1
0x1800a7da5  jz      short loc_1800A7DE0
0x1800a7da7  sub     ecx, 1
0x1800a7daa  jz      short loc_1800A7DE0
0x1800a7dac  cmp     ecx, 1
0x1800a7daf  jz      short loc_1800A7DE0
0x1800a7db1  mov     rcx, [rbp+878h]; this
0x1800a7db8  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x1800a7dbf  mov     r9d, 8000FFFFh; char *
0x1800a7dc5  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x1800a7dca  lea     r8, aOnecoreBaseApp_130; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7dd1  mov     edx, 0F1h; void *
0x1800a7dd6  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a7ddb  jmp     loc_1800A811D
0x1800a7de0  mov     ecx, ebx
0x1800a7de2  call    ?SeverityToString@Logging@StateRepository@@YAPEBDW4Severity@12@@Z; StateRepository::Logging::SeverityToString(StateRepository::Logging::Severity)
0x1800a7de7  mov     [rbp+870h+var_8E8], rax
0x1800a7deb  test    dil, 2
0x1800a7def  jz      loc_1800A7E8B
0x1800a7df5  call    cs:__imp_GetCurrentThreadId
0x1800a7dfb  mov     ebx, eax
0x1800a7dfd  call    cs:__imp_GetCurrentProcessId
0x1800a7e03  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800a7e08  mov     r8d, eax
0x1800a7e0b  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800a7e10  mov     eax, 51EB851Fh
0x1800a7e15  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800a7e1a  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1800a7e1e  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1800a7e22  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1800a7e27  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x1800a7e2c  mov     [rsp+9D0h+var_960], r12
0x1800a7e31  mov     dword ptr [rsp+9D0h+var_968], ebx
0x1800a7e35  mov     dword ptr [rsp+9D0h+var_970], r8d
0x1800a7e3a  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x1800a7e41  mov     [rsp+9D0h+var_978], r13d
0x1800a7e46  mul     r9d
0x1800a7e49  mov     rax, [rbp+870h+var_8E8]
0x1800a7e4d  mov     [rsp+9D0h+var_980], rax
0x1800a7e52  mov     [rsp+9D0h+var_988], r10d
0x1800a7e57  mov     [rsp+9D0h+var_990], r11d
0x1800a7e5c  shr     edx, 5
0x1800a7e5f  imul    ecx, edx, 64h ; 'd'
0x1800a7e62  lea     rdx, [rbp+870h+Buffer]
0x1800a7e66  mov     [rsp+9D0h+var_998], edi
0x1800a7e6a  mov     [rsp+9D0h+var_9A0], esi
0x1800a7e6e  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x1800a7e73  mov     [rsp+9D0h+var_9B0], r15d
0x1800a7e78  sub     r9d, ecx
0x1800a7e7b  mov     ecx, 800h
0x1800a7e80  call    cs:__imp_sqlite3_snprintf
0x1800a7e86  jmp     loc_1800A8114
0x1800a7e8b  xor     edx, edx; Val
0x1800a7e8d  lea     rcx, [rbp+870h+BackTrace]; void *
0x1800a7e91  lea     r8d, [rdx+60h]; Size
0x1800a7e95  call    memset_0
0x1800a7e9a  xor     r9d, r9d; BackTraceHash
0x1800a7e9d  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x1800a7ea1  xor     ecx, ecx; FramesToSkip
0x1800a7ea3  lea     edx, [r9+0Ch]; FramesToCapture
0x1800a7ea7  call    cs:__imp_RtlCaptureStackBackTrace
0x1800a7ead  mov     rax, [rbp+870h+var_880]
0x1800a7eb1  mov     rbx, [rbp+870h+var_848]
0x1800a7eb5  mov     rdi, [rbp+870h+var_850]
0x1800a7eb9  mov     rsi, [rbp+870h+var_858]
0x1800a7ebd  mov     r14, [rbp+870h+var_860]
0x1800a7ec1  mov     r15, [rbp+870h+var_868]
0x1800a7ec5  mov     r12, [rbp+870h+var_870]
0x1800a7ec9  mov     r13, [rbp+870h+var_878]
0x1800a7ecd  mov     [rbp+870h+var_8E0], rax
0x1800a7ed1  mov     rax, [rbp+870h+var_888]
0x1800a7ed5  mov     [rbp+870h+var_8D8], rax
0x1800a7ed9  mov     rax, [rbp+870h+var_890]
0x1800a7edd  mov     [rbp+870h+var_8D0], rax
0x1800a7ee1  mov     rax, [rbp+870h+var_898]
0x1800a7ee5  mov     [rbp+870h+var_8C8], rax
0x1800a7ee9  mov     rax, [rbp+870h+BackTrace]
0x1800a7eed  mov     [rbp+870h+var_8C0], rax
0x1800a7ef1  call    cs:__imp_GetCurrentThreadId
0x1800a7ef7  mov     [rbp+870h+var_8F0], eax
0x1800a7efa  call    cs:__imp_GetCurrentProcessId
0x1800a7f00  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x1800a7f04  mov     r8d, eax
0x1800a7f07  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x1800a7f0c  mov     eax, 51EB851Fh
0x1800a7f11  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800a7f16  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800a7f1b  mov     [rsp+9D0h+var_900], rbx
0x1800a7f23  mov     [rsp+9D0h+var_908], rdi
0x1800a7f2b  mov     [rsp+9D0h+var_910], rsi
0x1800a7f33  mov     [rsp+9D0h+var_918], r14
0x1800a7f3b  mov     [rsp+9D0h+var_920], r15
0x1800a7f43  mul     ecx
0x1800a7f45  mov     rax, [rbp+870h+var_8E0]
0x1800a7f49  mov     [rsp+9D0h+var_928], r12
0x1800a7f51  mov     [rsp+9D0h+var_930], r13
0x1800a7f59  mov     [rsp+9D0h+var_938], rax
0x1800a7f61  mov     rax, [rbp+870h+var_8D8]
0x1800a7f65  mov     [rsp+9D0h+var_940], rax
0x1800a7f6d  mov     rax, [rbp+870h+var_8D0]
0x1800a7f71  mov     [rsp+9D0h+var_948], rax
0x1800a7f79  mov     rax, [rbp+870h+var_8C8]
0x1800a7f7d  mov     [rsp+9D0h+var_950], rax
0x1800a7f85  mov     rax, [rbp+870h+var_8C0]
0x1800a7f89  mov     [rsp+9D0h+var_958], rax
0x1800a7f8e  mov     rax, [rbp+870h+var_8B8]
0x1800a7f92  mov     [rsp+9D0h+var_960], rax
0x1800a7f97  mov     eax, [rbp+870h+var_8F0]
0x1800a7f9a  mov     dword ptr [rsp+9D0h+var_968], eax
0x1800a7f9e  mov     eax, [rbp+870h+var_8EC]
0x1800a7fa1  mov     dword ptr [rsp+9D0h+var_970], r8d
0x1800a7fa6  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x1800a7fad  mov     [rsp+9D0h+var_978], eax
0x1800a7fb1  mov     rax, [rbp+870h+var_8E8]
0x1800a7fb5  mov     [rsp+9D0h+var_980], rax
0x1800a7fba  movzx   eax, [rbp+870h+SystemTime.wHour]
0x1800a7fbe  mov     [rsp+9D0h+var_988], r10d
0x1800a7fc3  shr     edx, 5
0x1800a7fc6  imul    ecx, edx, 64h ; 'd'
0x1800a7fc9  movzx   edx, [rbp+870h+SystemTime.wYear]
0x1800a7fcd  mov     [rsp+9D0h+var_990], r11d
0x1800a7fd2  mov     [rsp+9D0h+var_998], r9d
0x1800a7fd7  mov     [rsp+9D0h+var_9A0], eax
0x1800a7fdb  movzx   eax, [rbp+870h+SystemTime.wDay]
0x1800a7fdf  sub     edx, ecx
0x1800a7fe1  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x1800a7fe5  mov     r9d, edx
0x1800a7fe8  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x1800a7fec  lea     rdx, [rbp+870h+Buffer]
0x1800a7ff0  mov     ecx, 800h
0x1800a7ff5  mov     [rsp+9D0h+var_9B0], eax
0x1800a7ff9  call    cs:__imp_sqlite3_snprintf
0x1800a7fff  jmp     loc_1800A8114
0x1800a8004  call    cs:__imp_GetCurrentThreadId
0x1800a800a  mov     r15d, eax
0x1800a800d  call    cs:__imp_GetCurrentProcessId
0x1800a8013  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800a8018  mov     r8d, eax
0x1800a801b  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800a8020  mov     eax, 51EB851Fh
0x1800a8025  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800a802a  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x1800a802e  movzx   edi, [rbp+870h+SystemTime.wHour]
0x1800a8032  movzx   esi, [rbp+870h+SystemTime.wDay]
0x1800a8036  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x1800a803b  mov     [rsp+9D0h+var_970], r12
0x1800a8040  mov     [rsp+9D0h+var_978], r15d
0x1800a8045  mov     dword ptr [rsp+9D0h+var_980], r8d
0x1800a804a  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x1800a8051  mov     [rsp+9D0h+var_988], r10d
0x1800a8056  mov     [rsp+9D0h+var_990], r11d
0x1800a805b  mul     r9d
0x1800a805e  mov     [rsp+9D0h+var_998], ebx
0x1800a8062  shr     edx, 5
0x1800a8065  imul    ecx, edx, 64h ; 'd'
0x1800a8068  lea     rdx, [rbp+870h+Buffer]
0x1800a806c  mov     [rsp+9D0h+var_9A0], edi
0x1800a8070  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x1800a8074  mov     [rsp+9D0h+var_9B0], r14d
0x1800a8079  sub     r9d, ecx
0x1800a807c  mov     ecx, 800h
0x1800a8081  call    cs:__imp_sqlite3_snprintf
0x1800a8087  jmp     loc_1800A8114
0x1800a808c  call    cs:__imp_GetCurrentThreadId
0x1800a8092  mov     ebx, eax
0x1800a8094  call    cs:__imp_GetCurrentProcessId
0x1800a809a  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800a809f  mov     r8d, eax
0x1800a80a2  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800a80a7  mov     eax, 51EB851Fh
0x1800a80ac  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800a80b1  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1800a80b5  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1800a80b9  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1800a80be  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x1800a80c3  mov     [rsp+9D0h+var_968], r12
0x1800a80c8  mov     dword ptr [rsp+9D0h+var_970], ebx
0x1800a80cc  mov     [rsp+9D0h+var_978], r8d
0x1800a80d1  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x1800a80d8  mov     dword ptr [rsp+9D0h+var_980], r13d
0x1800a80dd  mov     [rsp+9D0h+var_988], r10d
0x1800a80e2  mov     [rsp+9D0h+var_990], r11d
0x1800a80e7  mul     r9d
0x1800a80ea  mov     [rsp+9D0h+var_998], edi
0x1800a80ee  shr     edx, 5
0x1800a80f1  imul    ecx, edx, 64h ; 'd'
0x1800a80f4  lea     rdx, [rbp+870h+Buffer]
0x1800a80f8  mov     [rsp+9D0h+var_9A0], esi
0x1800a80fc  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x1800a8101  mov     [rsp+9D0h+var_9B0], r15d
0x1800a8106  sub     r9d, ecx
0x1800a8109  mov     ecx, 800h
0x1800a810e  call    cs:__imp_sqlite3_snprintf
0x1800a8114  lea     rcx, [rbp+870h+Buffer]; lpBuffer
0x1800a8118  call    ?WriteLogToFile@Logging@StateRepository@@YAXPEBD@Z; StateRepository::Logging::WriteLogToFile(char const *)
0x1800a811d  mov     rcx, [rbp+870h+var_40]
0x1800a8124  xor     rcx, rsp; StackCookie
0x1800a8127  call    __security_check_cookie
0x1800a812c  mov     rbx, [rsp+9D0h+arg_18]
0x1800a8134  add     rsp, 9A0h
0x1800a813b  pop     r15
0x1800a813d  pop     r14
0x1800a813f  pop     r13
0x1800a8141  pop     r12
0x1800a8143  pop     rdi
0x1800a8144  pop     rsi
0x1800a8145  pop     rbp
0x1800a8146  retn
```
