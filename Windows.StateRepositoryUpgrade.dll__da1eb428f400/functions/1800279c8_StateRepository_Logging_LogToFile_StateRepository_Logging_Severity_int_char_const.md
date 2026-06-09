# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x1800279c8`
- end: `0x180027dfb`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1075`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180028950`
- `0x180028b64`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x18000baf4`
- `0x1800279c8`
- `0x1800283a0`
- `0x1800284b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027bae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027d48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027bae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027d48`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180027a22`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180027a22`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027b34`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027cad`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027d35`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027dc2`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027b34`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027cad`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027d35`
- `StateRepository.Core!sqlite3_snprintf` at `0x180027dc2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180027b5b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180027b5b`

## string_xrefs

- `0x180027a7e`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

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
  _BYTE v34[2048]; // [rsp+190h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+878h]

  v3 = dword_18004B904;
  if ( (dword_18004B904 & 1) != 0 )
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    memset_0(v34, 0, sizeof(v34));
    if ( a1 )
    {
      if ( a1 == 16 )
      {
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        sqlite3_snprintf(
          2048,
          v34,
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
            v34,
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
            v34,
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
        v34,
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
    StateRepository::Logging::WriteLogToFile((StateRepository::Logging *)v34, v9);
  }
}

```

## disassembly

```asm
0x1800279c8  mov     [rsp-8+arg_18], rbx
0x1800279cd  push    rbp
0x1800279ce  push    rsi
0x1800279cf  push    rdi
0x1800279d0  push    r12
0x1800279d2  push    r13
0x1800279d4  push    r14
0x1800279d6  push    r15
0x1800279d8  lea     rbp, [rsp-840h]
0x1800279e0  sub     rsp, 9A0h
0x1800279e7  mov     rax, cs:__security_cookie
0x1800279ee  xor     rax, rsp
0x1800279f1  mov     [rbp+870h+var_40], rax
0x1800279f8  mov     edi, cs:dword_18004B904
0x1800279fe  mov     r12, r8
0x180027a01  mov     [rbp+870h+var_8B8], r8
0x180027a05  mov     r13d, edx
0x180027a08  mov     [rbp+870h+var_8EC], edx
0x180027a0b  mov     ebx, ecx
0x180027a0d  test    dil, 1
0x180027a11  jz      loc_180027DD1
0x180027a17  xorps   xmm0, xmm0
0x180027a1a  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x180027a1e  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x180027a22  call    cs:__imp_GetLocalTime
0x180027a28  xor     edx, edx; Val
0x180027a2a  lea     rcx, [rbp+870h+var_840]; void *
0x180027a2e  mov     r8d, 800h; Size
0x180027a34  call    memset_0
0x180027a39  mov     ecx, ebx
0x180027a3b  test    ebx, ebx
0x180027a3d  jz      loc_180027D40
0x180027a43  sub     ecx, 10h
0x180027a46  jz      loc_180027CB8
0x180027a4c  sub     ecx, 10h
0x180027a4f  jz      short loc_180027A94
0x180027a51  sub     ecx, 1
0x180027a54  jz      short loc_180027A94
0x180027a56  sub     ecx, 1
0x180027a59  jz      short loc_180027A94
0x180027a5b  sub     ecx, 1
0x180027a5e  jz      short loc_180027A94
0x180027a60  cmp     ecx, 1
0x180027a63  jz      short loc_180027A94
0x180027a65  mov     rcx, [rbp+878h]; this
0x180027a6c  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x180027a73  mov     r9d, 8000FFFFh; char *
0x180027a79  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x180027a7e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180027a85  mov     edx, 0F1h; void *
0x180027a8a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027a8f  jmp     loc_180027DD1
0x180027a94  mov     ecx, ebx
0x180027a96  call    ?SeverityToString@Logging@StateRepository@@YAPEBDW4Severity@12@@Z; StateRepository::Logging::SeverityToString(StateRepository::Logging::Severity)
0x180027a9b  mov     [rbp+870h+var_8E8], rax
0x180027a9f  test    dil, 2
0x180027aa3  jz      loc_180027B3F
0x180027aa9  call    cs:__imp_GetCurrentThreadId
0x180027aaf  mov     ebx, eax
0x180027ab1  call    cs:__imp_GetCurrentProcessId
0x180027ab7  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x180027abc  mov     r8d, eax
0x180027abf  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180027ac4  mov     eax, 51EB851Fh
0x180027ac9  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180027ace  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x180027ad2  movzx   esi, [rbp+870h+SystemTime.wHour]
0x180027ad6  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x180027adb  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x180027ae0  mov     [rsp+9D0h+var_960], r12
0x180027ae5  mov     dword ptr [rsp+9D0h+var_968], ebx
0x180027ae9  mov     dword ptr [rsp+9D0h+var_970], r8d
0x180027aee  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x180027af5  mov     [rsp+9D0h+var_978], r13d
0x180027afa  mul     r9d
0x180027afd  mov     rax, [rbp+870h+var_8E8]
0x180027b01  mov     [rsp+9D0h+var_980], rax
0x180027b06  mov     [rsp+9D0h+var_988], r10d
0x180027b0b  mov     [rsp+9D0h+var_990], r11d
0x180027b10  shr     edx, 5
0x180027b13  imul    ecx, edx, 64h ; 'd'
0x180027b16  lea     rdx, [rbp+870h+var_840]
0x180027b1a  mov     [rsp+9D0h+var_998], edi
0x180027b1e  mov     [rsp+9D0h+var_9A0], esi
0x180027b22  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180027b27  mov     [rsp+9D0h+var_9B0], r15d
0x180027b2c  sub     r9d, ecx
0x180027b2f  mov     ecx, 800h
0x180027b34  call    cs:__imp_sqlite3_snprintf
0x180027b3a  jmp     loc_180027DC8
0x180027b3f  xor     edx, edx; Val
0x180027b41  lea     rcx, [rbp+870h+BackTrace]; void *
0x180027b45  lea     r8d, [rdx+60h]; Size
0x180027b49  call    memset_0
0x180027b4e  xor     r9d, r9d; BackTraceHash
0x180027b51  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x180027b55  xor     ecx, ecx; FramesToSkip
0x180027b57  lea     edx, [r9+0Ch]; FramesToCapture
0x180027b5b  call    cs:__imp_RtlCaptureStackBackTrace
0x180027b61  mov     rax, [rbp+870h+var_880]
0x180027b65  mov     rbx, [rbp+870h+var_848]
0x180027b69  mov     rdi, [rbp+870h+var_850]
0x180027b6d  mov     rsi, [rbp+870h+var_858]
0x180027b71  mov     r14, [rbp+870h+var_860]
0x180027b75  mov     r15, [rbp+870h+var_868]
0x180027b79  mov     r12, [rbp+870h+var_870]
0x180027b7d  mov     r13, [rbp+870h+var_878]
0x180027b81  mov     [rbp+870h+var_8E0], rax
0x180027b85  mov     rax, [rbp+870h+var_888]
0x180027b89  mov     [rbp+870h+var_8D8], rax
0x180027b8d  mov     rax, [rbp+870h+var_890]
0x180027b91  mov     [rbp+870h+var_8D0], rax
0x180027b95  mov     rax, [rbp+870h+var_898]
0x180027b99  mov     [rbp+870h+var_8C8], rax
0x180027b9d  mov     rax, [rbp+870h+BackTrace]
0x180027ba1  mov     [rbp+870h+var_8C0], rax
0x180027ba5  call    cs:__imp_GetCurrentThreadId
0x180027bab  mov     [rbp+870h+var_8F0], eax
0x180027bae  call    cs:__imp_GetCurrentProcessId
0x180027bb4  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x180027bb8  mov     r8d, eax
0x180027bbb  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x180027bc0  mov     eax, 51EB851Fh
0x180027bc5  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180027bca  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180027bcf  mov     [rsp+9D0h+var_900], rbx
0x180027bd7  mov     [rsp+9D0h+var_908], rdi
0x180027bdf  mov     [rsp+9D0h+var_910], rsi
0x180027be7  mov     [rsp+9D0h+var_918], r14
0x180027bef  mov     [rsp+9D0h+var_920], r15
0x180027bf7  mul     ecx
0x180027bf9  mov     rax, [rbp+870h+var_8E0]
0x180027bfd  mov     [rsp+9D0h+var_928], r12
0x180027c05  mov     [rsp+9D0h+var_930], r13
0x180027c0d  mov     [rsp+9D0h+var_938], rax
0x180027c15  mov     rax, [rbp+870h+var_8D8]
0x180027c19  mov     [rsp+9D0h+var_940], rax
0x180027c21  mov     rax, [rbp+870h+var_8D0]
0x180027c25  mov     [rsp+9D0h+var_948], rax
0x180027c2d  mov     rax, [rbp+870h+var_8C8]
0x180027c31  mov     [rsp+9D0h+var_950], rax
0x180027c39  mov     rax, [rbp+870h+var_8C0]
0x180027c3d  mov     [rsp+9D0h+var_958], rax
0x180027c42  mov     rax, [rbp+870h+var_8B8]
0x180027c46  mov     [rsp+9D0h+var_960], rax
0x180027c4b  mov     eax, [rbp+870h+var_8F0]
0x180027c4e  mov     dword ptr [rsp+9D0h+var_968], eax
0x180027c52  mov     eax, [rbp+870h+var_8EC]
0x180027c55  mov     dword ptr [rsp+9D0h+var_970], r8d
0x180027c5a  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x180027c61  mov     [rsp+9D0h+var_978], eax
0x180027c65  mov     rax, [rbp+870h+var_8E8]
0x180027c69  mov     [rsp+9D0h+var_980], rax
0x180027c6e  movzx   eax, [rbp+870h+SystemTime.wHour]
0x180027c72  mov     [rsp+9D0h+var_988], r10d
0x180027c77  shr     edx, 5
0x180027c7a  imul    ecx, edx, 64h ; 'd'
0x180027c7d  movzx   edx, [rbp+870h+SystemTime.wYear]
0x180027c81  mov     [rsp+9D0h+var_990], r11d
0x180027c86  mov     [rsp+9D0h+var_998], r9d
0x180027c8b  mov     [rsp+9D0h+var_9A0], eax
0x180027c8f  movzx   eax, [rbp+870h+SystemTime.wDay]
0x180027c93  sub     edx, ecx
0x180027c95  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x180027c99  mov     r9d, edx
0x180027c9c  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x180027ca0  lea     rdx, [rbp+870h+var_840]
0x180027ca4  mov     ecx, 800h
0x180027ca9  mov     [rsp+9D0h+var_9B0], eax
0x180027cad  call    cs:__imp_sqlite3_snprintf
0x180027cb3  jmp     loc_180027DC8
0x180027cb8  call    cs:__imp_GetCurrentThreadId
0x180027cbe  mov     r15d, eax
0x180027cc1  call    cs:__imp_GetCurrentProcessId
0x180027cc7  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x180027ccc  mov     r8d, eax
0x180027ccf  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180027cd4  mov     eax, 51EB851Fh
0x180027cd9  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180027cde  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x180027ce2  movzx   edi, [rbp+870h+SystemTime.wHour]
0x180027ce6  movzx   esi, [rbp+870h+SystemTime.wDay]
0x180027cea  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x180027cef  mov     [rsp+9D0h+var_970], r12
0x180027cf4  mov     [rsp+9D0h+var_978], r15d
0x180027cf9  mov     dword ptr [rsp+9D0h+var_980], r8d
0x180027cfe  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x180027d05  mov     [rsp+9D0h+var_988], r10d
0x180027d0a  mov     [rsp+9D0h+var_990], r11d
0x180027d0f  mul     r9d
0x180027d12  mov     [rsp+9D0h+var_998], ebx
0x180027d16  shr     edx, 5
0x180027d19  imul    ecx, edx, 64h ; 'd'
0x180027d1c  lea     rdx, [rbp+870h+var_840]
0x180027d20  mov     [rsp+9D0h+var_9A0], edi
0x180027d24  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x180027d28  mov     [rsp+9D0h+var_9B0], r14d
0x180027d2d  sub     r9d, ecx
0x180027d30  mov     ecx, 800h
0x180027d35  call    cs:__imp_sqlite3_snprintf
0x180027d3b  jmp     loc_180027DC8
0x180027d40  call    cs:__imp_GetCurrentThreadId
0x180027d46  mov     ebx, eax
0x180027d48  call    cs:__imp_GetCurrentProcessId
0x180027d4e  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x180027d53  mov     r8d, eax
0x180027d56  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180027d5b  mov     eax, 51EB851Fh
0x180027d60  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180027d65  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x180027d69  movzx   esi, [rbp+870h+SystemTime.wHour]
0x180027d6d  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x180027d72  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x180027d77  mov     [rsp+9D0h+var_968], r12
0x180027d7c  mov     dword ptr [rsp+9D0h+var_970], ebx
0x180027d80  mov     [rsp+9D0h+var_978], r8d
0x180027d85  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x180027d8c  mov     dword ptr [rsp+9D0h+var_980], r13d
0x180027d91  mov     [rsp+9D0h+var_988], r10d
0x180027d96  mov     [rsp+9D0h+var_990], r11d
0x180027d9b  mul     r9d
0x180027d9e  mov     [rsp+9D0h+var_998], edi
0x180027da2  shr     edx, 5
0x180027da5  imul    ecx, edx, 64h ; 'd'
0x180027da8  lea     rdx, [rbp+870h+var_840]
0x180027dac  mov     [rsp+9D0h+var_9A0], esi
0x180027db0  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180027db5  mov     [rsp+9D0h+var_9B0], r15d
0x180027dba  sub     r9d, ecx
0x180027dbd  mov     ecx, 800h
0x180027dc2  call    cs:__imp_sqlite3_snprintf
0x180027dc8  lea     rcx, [rbp+870h+var_840]; this
0x180027dcc  call    ?WriteLogToFile@Logging@StateRepository@@YAXPEBD@Z; StateRepository::Logging::WriteLogToFile(char const *)
0x180027dd1  mov     rcx, [rbp+870h+var_40]
0x180027dd8  xor     rcx, rsp; StackCookie
0x180027ddb  call    __security_check_cookie
0x180027de0  mov     rbx, [rsp+9D0h+arg_18]
0x180027de8  add     rsp, 9A0h
0x180027def  pop     r15
0x180027df1  pop     r14
0x180027df3  pop     r13
0x180027df5  pop     r12
0x180027df7  pop     rdi
0x180027df8  pop     rsi
0x180027df9  pop     rbp
0x180027dfa  retn
```
