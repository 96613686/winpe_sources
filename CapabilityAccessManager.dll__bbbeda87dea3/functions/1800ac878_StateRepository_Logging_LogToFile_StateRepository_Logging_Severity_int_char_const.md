# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x1800ac878`
- end: `0x1800accab`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1075`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800ad530`
- `0x1800ad740`
- `0x1800ad7a0`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x1800a1610`
- `0x1800ac878`
- `0x1800acf84`
- `0x1800ad0a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ac959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aca55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acb68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ac959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aca55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acb68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aca5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acb71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acbf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aca5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acb71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acbf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800ac8d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800ac8d2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800aca0b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800aca0b`
- `winsqlite3!sqlite3_snprintf` at `0x1800ac9e4`
- `winsqlite3!sqlite3_snprintf` at `0x1800acb5d`
- `winsqlite3!sqlite3_snprintf` at `0x1800acbe5`
- `winsqlite3!sqlite3_snprintf` at `0x1800acc72`
- `winsqlite3!sqlite3_snprintf` at `0x1800ac9e4`
- `winsqlite3!sqlite3_snprintf` at `0x1800acb5d`
- `winsqlite3!sqlite3_snprintf` at `0x1800acbe5`
- `winsqlite3!sqlite3_snprintf` at `0x1800acc72`

## string_xrefs

- `0x1800ac92e`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

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
  struct _SYSTEMTIME SystemTime; // [rsp+120h] [rbp-40h] BYREF
  PVOID BackTrace[12]; // [rsp+130h] [rbp-30h] BYREF
  _BYTE v34[2048]; // [rsp+190h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+878h]

  v3 = dword_180166488;
  if ( (dword_180166488 & 1) != 0 )
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
0x1800ac878  mov     [rsp-8+arg_18], rbx
0x1800ac87d  push    rbp
0x1800ac87e  push    rsi
0x1800ac87f  push    rdi
0x1800ac880  push    r12
0x1800ac882  push    r13
0x1800ac884  push    r14
0x1800ac886  push    r15
0x1800ac888  lea     rbp, [rsp-840h]
0x1800ac890  sub     rsp, 9A0h
0x1800ac897  mov     rax, cs:__security_cookie
0x1800ac89e  xor     rax, rsp
0x1800ac8a1  mov     [rbp+870h+var_40], rax
0x1800ac8a8  mov     edi, cs:dword_180166488
0x1800ac8ae  mov     r12, r8
0x1800ac8b1  mov     [rbp+870h+var_8B8], r8
0x1800ac8b5  mov     r13d, edx
0x1800ac8b8  mov     [rbp+870h+var_8EC], edx
0x1800ac8bb  mov     ebx, ecx
0x1800ac8bd  test    dil, 1
0x1800ac8c1  jz      loc_1800ACC81
0x1800ac8c7  xorps   xmm0, xmm0
0x1800ac8ca  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x1800ac8ce  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x1800ac8d2  call    cs:__imp_GetLocalTime
0x1800ac8d8  xor     edx, edx; Val
0x1800ac8da  lea     rcx, [rbp+870h+var_840]; void *
0x1800ac8de  mov     r8d, 800h; Size
0x1800ac8e4  call    memset_0
0x1800ac8e9  mov     ecx, ebx
0x1800ac8eb  test    ebx, ebx
0x1800ac8ed  jz      loc_1800ACBF0
0x1800ac8f3  sub     ecx, 10h
0x1800ac8f6  jz      loc_1800ACB68
0x1800ac8fc  sub     ecx, 10h
0x1800ac8ff  jz      short loc_1800AC944
0x1800ac901  sub     ecx, 1
0x1800ac904  jz      short loc_1800AC944
0x1800ac906  sub     ecx, 1
0x1800ac909  jz      short loc_1800AC944
0x1800ac90b  sub     ecx, 1
0x1800ac90e  jz      short loc_1800AC944
0x1800ac910  cmp     ecx, 1
0x1800ac913  jz      short loc_1800AC944
0x1800ac915  mov     rcx, [rbp+878h]; this
0x1800ac91c  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x1800ac923  mov     r9d, 8000FFFFh; char *
0x1800ac929  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x1800ac92e  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x1800ac935  mov     edx, 0F1h; void *
0x1800ac93a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800ac93f  jmp     loc_1800ACC81
0x1800ac944  mov     ecx, ebx
0x1800ac946  call    ?SeverityToString@Logging@StateRepository@@YAPEBDW4Severity@12@@Z; StateRepository::Logging::SeverityToString(StateRepository::Logging::Severity)
0x1800ac94b  mov     [rbp+870h+var_8E8], rax
0x1800ac94f  test    dil, 2
0x1800ac953  jz      loc_1800AC9EF
0x1800ac959  call    cs:__imp_GetCurrentThreadId
0x1800ac95f  mov     ebx, eax
0x1800ac961  call    cs:__imp_GetCurrentProcessId
0x1800ac967  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800ac96c  mov     r8d, eax
0x1800ac96f  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800ac974  mov     eax, 51EB851Fh
0x1800ac979  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800ac97e  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1800ac982  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1800ac986  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1800ac98b  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x1800ac990  mov     [rsp+9D0h+var_960], r12
0x1800ac995  mov     dword ptr [rsp+9D0h+var_968], ebx
0x1800ac999  mov     dword ptr [rsp+9D0h+var_970], r8d
0x1800ac99e  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x1800ac9a5  mov     [rsp+9D0h+var_978], r13d
0x1800ac9aa  mul     r9d
0x1800ac9ad  mov     rax, [rbp+870h+var_8E8]
0x1800ac9b1  mov     [rsp+9D0h+var_980], rax
0x1800ac9b6  mov     [rsp+9D0h+var_988], r10d
0x1800ac9bb  mov     [rsp+9D0h+var_990], r11d
0x1800ac9c0  shr     edx, 5
0x1800ac9c3  imul    ecx, edx, 64h ; 'd'
0x1800ac9c6  lea     rdx, [rbp+870h+var_840]
0x1800ac9ca  mov     [rsp+9D0h+var_998], edi
0x1800ac9ce  mov     [rsp+9D0h+var_9A0], esi
0x1800ac9d2  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x1800ac9d7  mov     [rsp+9D0h+var_9B0], r15d
0x1800ac9dc  sub     r9d, ecx
0x1800ac9df  mov     ecx, 800h
0x1800ac9e4  call    cs:__imp_sqlite3_snprintf
0x1800ac9ea  jmp     loc_1800ACC78
0x1800ac9ef  xor     edx, edx; Val
0x1800ac9f1  lea     rcx, [rbp+870h+BackTrace]; void *
0x1800ac9f5  lea     r8d, [rdx+60h]; Size
0x1800ac9f9  call    memset_0
0x1800ac9fe  xor     r9d, r9d; BackTraceHash
0x1800aca01  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x1800aca05  xor     ecx, ecx; FramesToSkip
0x1800aca07  lea     edx, [r9+0Ch]; FramesToCapture
0x1800aca0b  call    cs:__imp_RtlCaptureStackBackTrace
0x1800aca11  mov     rax, [rbp+870h+var_880]
0x1800aca15  mov     rbx, [rbp+870h+var_848]
0x1800aca19  mov     rdi, [rbp+870h+var_850]
0x1800aca1d  mov     rsi, [rbp+870h+var_858]
0x1800aca21  mov     r14, [rbp+870h+var_860]
0x1800aca25  mov     r15, [rbp+870h+var_868]
0x1800aca29  mov     r12, [rbp+870h+var_870]
0x1800aca2d  mov     r13, [rbp+870h+var_878]
0x1800aca31  mov     [rbp+870h+var_8E0], rax
0x1800aca35  mov     rax, [rbp+870h+var_888]
0x1800aca39  mov     [rbp+870h+var_8D8], rax
0x1800aca3d  mov     rax, [rbp+870h+var_890]
0x1800aca41  mov     [rbp+870h+var_8D0], rax
0x1800aca45  mov     rax, [rbp+870h+var_898]
0x1800aca49  mov     [rbp+870h+var_8C8], rax
0x1800aca4d  mov     rax, [rbp+870h+BackTrace]
0x1800aca51  mov     [rbp+870h+var_8C0], rax
0x1800aca55  call    cs:__imp_GetCurrentThreadId
0x1800aca5b  mov     [rbp+870h+var_8F0], eax
0x1800aca5e  call    cs:__imp_GetCurrentProcessId
0x1800aca64  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x1800aca68  mov     r8d, eax
0x1800aca6b  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x1800aca70  mov     eax, 51EB851Fh
0x1800aca75  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800aca7a  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800aca7f  mov     [rsp+9D0h+var_900], rbx
0x1800aca87  mov     [rsp+9D0h+var_908], rdi
0x1800aca8f  mov     [rsp+9D0h+var_910], rsi
0x1800aca97  mov     [rsp+9D0h+var_918], r14
0x1800aca9f  mov     [rsp+9D0h+var_920], r15
0x1800acaa7  mul     ecx
0x1800acaa9  mov     rax, [rbp+870h+var_8E0]
0x1800acaad  mov     [rsp+9D0h+var_928], r12
0x1800acab5  mov     [rsp+9D0h+var_930], r13
0x1800acabd  mov     [rsp+9D0h+var_938], rax
0x1800acac5  mov     rax, [rbp+870h+var_8D8]
0x1800acac9  mov     [rsp+9D0h+var_940], rax
0x1800acad1  mov     rax, [rbp+870h+var_8D0]
0x1800acad5  mov     [rsp+9D0h+var_948], rax
0x1800acadd  mov     rax, [rbp+870h+var_8C8]
0x1800acae1  mov     [rsp+9D0h+var_950], rax
0x1800acae9  mov     rax, [rbp+870h+var_8C0]
0x1800acaed  mov     [rsp+9D0h+var_958], rax
0x1800acaf2  mov     rax, [rbp+870h+var_8B8]
0x1800acaf6  mov     [rsp+9D0h+var_960], rax
0x1800acafb  mov     eax, [rbp+870h+var_8F0]
0x1800acafe  mov     dword ptr [rsp+9D0h+var_968], eax
0x1800acb02  mov     eax, [rbp+870h+var_8EC]
0x1800acb05  mov     dword ptr [rsp+9D0h+var_970], r8d
0x1800acb0a  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x1800acb11  mov     [rsp+9D0h+var_978], eax
0x1800acb15  mov     rax, [rbp+870h+var_8E8]
0x1800acb19  mov     [rsp+9D0h+var_980], rax
0x1800acb1e  movzx   eax, [rbp+870h+SystemTime.wHour]
0x1800acb22  mov     [rsp+9D0h+var_988], r10d
0x1800acb27  shr     edx, 5
0x1800acb2a  imul    ecx, edx, 64h ; 'd'
0x1800acb2d  movzx   edx, [rbp+870h+SystemTime.wYear]
0x1800acb31  mov     [rsp+9D0h+var_990], r11d
0x1800acb36  mov     [rsp+9D0h+var_998], r9d
0x1800acb3b  mov     [rsp+9D0h+var_9A0], eax
0x1800acb3f  movzx   eax, [rbp+870h+SystemTime.wDay]
0x1800acb43  sub     edx, ecx
0x1800acb45  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x1800acb49  mov     r9d, edx
0x1800acb4c  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x1800acb50  lea     rdx, [rbp+870h+var_840]
0x1800acb54  mov     ecx, 800h
0x1800acb59  mov     [rsp+9D0h+var_9B0], eax
0x1800acb5d  call    cs:__imp_sqlite3_snprintf
0x1800acb63  jmp     loc_1800ACC78
0x1800acb68  call    cs:__imp_GetCurrentThreadId
0x1800acb6e  mov     r15d, eax
0x1800acb71  call    cs:__imp_GetCurrentProcessId
0x1800acb77  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800acb7c  mov     r8d, eax
0x1800acb7f  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800acb84  mov     eax, 51EB851Fh
0x1800acb89  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800acb8e  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x1800acb92  movzx   edi, [rbp+870h+SystemTime.wHour]
0x1800acb96  movzx   esi, [rbp+870h+SystemTime.wDay]
0x1800acb9a  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x1800acb9f  mov     [rsp+9D0h+var_970], r12
0x1800acba4  mov     [rsp+9D0h+var_978], r15d
0x1800acba9  mov     dword ptr [rsp+9D0h+var_980], r8d
0x1800acbae  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x1800acbb5  mov     [rsp+9D0h+var_988], r10d
0x1800acbba  mov     [rsp+9D0h+var_990], r11d
0x1800acbbf  mul     r9d
0x1800acbc2  mov     [rsp+9D0h+var_998], ebx
0x1800acbc6  shr     edx, 5
0x1800acbc9  imul    ecx, edx, 64h ; 'd'
0x1800acbcc  lea     rdx, [rbp+870h+var_840]
0x1800acbd0  mov     [rsp+9D0h+var_9A0], edi
0x1800acbd4  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x1800acbd8  mov     [rsp+9D0h+var_9B0], r14d
0x1800acbdd  sub     r9d, ecx
0x1800acbe0  mov     ecx, 800h
0x1800acbe5  call    cs:__imp_sqlite3_snprintf
0x1800acbeb  jmp     loc_1800ACC78
0x1800acbf0  call    cs:__imp_GetCurrentThreadId
0x1800acbf6  mov     ebx, eax
0x1800acbf8  call    cs:__imp_GetCurrentProcessId
0x1800acbfe  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1800acc03  mov     r8d, eax
0x1800acc06  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1800acc0b  mov     eax, 51EB851Fh
0x1800acc10  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1800acc15  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1800acc19  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1800acc1d  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1800acc22  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x1800acc27  mov     [rsp+9D0h+var_968], r12
0x1800acc2c  mov     dword ptr [rsp+9D0h+var_970], ebx
0x1800acc30  mov     [rsp+9D0h+var_978], r8d
0x1800acc35  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x1800acc3c  mov     dword ptr [rsp+9D0h+var_980], r13d
0x1800acc41  mov     [rsp+9D0h+var_988], r10d
0x1800acc46  mov     [rsp+9D0h+var_990], r11d
0x1800acc4b  mul     r9d
0x1800acc4e  mov     [rsp+9D0h+var_998], edi
0x1800acc52  shr     edx, 5
0x1800acc55  imul    ecx, edx, 64h ; 'd'
0x1800acc58  lea     rdx, [rbp+870h+var_840]
0x1800acc5c  mov     [rsp+9D0h+var_9A0], esi
0x1800acc60  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x1800acc65  mov     [rsp+9D0h+var_9B0], r15d
0x1800acc6a  sub     r9d, ecx
0x1800acc6d  mov     ecx, 800h
0x1800acc72  call    cs:__imp_sqlite3_snprintf
0x1800acc78  lea     rcx, [rbp+870h+var_840]; this
0x1800acc7c  call    ?WriteLogToFile@Logging@StateRepository@@YAXPEBD@Z; StateRepository::Logging::WriteLogToFile(char const *)
0x1800acc81  mov     rcx, [rbp+870h+var_40]
0x1800acc88  xor     rcx, rsp; StackCookie
0x1800acc8b  call    __security_check_cookie
0x1800acc90  mov     rbx, [rsp+9D0h+arg_18]
0x1800acc98  add     rsp, 9A0h
0x1800acc9f  pop     r15
0x1800acca1  pop     r14
0x1800acca3  pop     r13
0x1800acca5  pop     r12
0x1800acca7  pop     rdi
0x1800acca8  pop     rsi
0x1800acca9  pop     rbp
0x1800accaa  retn
```
