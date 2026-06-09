# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x1801862d4`
- end: `0x1801867a0`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1228`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180187170`
- `0x180187390`
- `0x1801873f0`

## callees

- `0x1800a0104`
- `0x1800a4444`
- `0x1800e8ec8`
- `0x1800f0260`
- `0x1800f10e4`
- `0x1801862d4`
- `0x180187004`

## import_xrefs

- `StateRepository.Core!sqlite3_snprintf` at `0x18018649f`
- `StateRepository.Core!sqlite3_snprintf` at `0x180186618`
- `StateRepository.Core!sqlite3_snprintf` at `0x1801866a0`
- `StateRepository.Core!sqlite3_snprintf` at `0x18018672d`
- `StateRepository.Core!sqlite3_snprintf` at `0x18018649f`
- `StateRepository.Core!sqlite3_snprintf` at `0x180186618`
- `StateRepository.Core!sqlite3_snprintf` at `0x1801866a0`
- `StateRepository.Core!sqlite3_snprintf` at `0x18018672d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018641e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180186519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018662c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801866b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018641e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180186519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018662c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801866b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801866ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180186623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801866ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180186749`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180186749`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18018632e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18018632e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1801864c6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1801864c6`

## string_xrefs

- `0x18018638a`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StateRepository::Logging::LogToFile(int a1, int a2, const char *a3)
{
  char v6; // di
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  const char *v12; // r12
  DWORD v13; // ebx
  DWORD v14; // eax
  PVOID v15; // rbx
  PVOID v16; // rdi
  PVOID v17; // rsi
  PVOID v18; // r14
  PVOID v19; // r15
  PVOID v20; // r12
  PVOID v21; // r13
  DWORD v22; // eax
  DWORD CurrentThreadId; // r15d
  DWORD CurrentProcessId; // eax
  DWORD v25; // ebx
  DWORD v26; // eax
  const char *v27; // rdx
  int i; // ebx
  const char *v29; // [rsp+28h] [rbp-138h]
  const char *v30; // [rsp+E0h] [rbp-80h] BYREF
  int v31; // [rsp+E8h] [rbp-78h]
  DWORD v32; // [rsp+ECh] [rbp-74h]
  PVOID v33; // [rsp+F0h] [rbp-70h]
  PVOID v34; // [rsp+F8h] [rbp-68h]
  PVOID v35; // [rsp+100h] [rbp-60h]
  PVOID v36; // [rsp+108h] [rbp-58h]
  PVOID v37; // [rsp+110h] [rbp-50h]
  const char *v38; // [rsp+118h] [rbp-48h]
  struct _SYSTEMTIME SystemTime; // [rsp+120h] [rbp-40h] BYREF
  PVOID BackTrace[12]; // [rsp+130h] [rbp-30h] BYREF
  _BYTE Buffer[2048]; // [rsp+190h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+878h]

  v38 = a3;
  v31 = a2;
  v6 = dword_1802E1844;
  if ( (dword_1802E1844 & 1) != 0 )
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
        if ( a1 != 32 && a1 != 33 && a1 != 34 && (unsigned int)(a1 - 35) >= 2 )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
            (const char *)0x8000FFFFLL,
            (int)"LogToFile(severity=Unknown,...)",
            v29);
          return;
        }
        v7 = a1 - 16;
        if ( v7 )
        {
          v8 = v7 - 16;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                v11 = v10 - 1;
                if ( v11 )
                {
                  if ( v11 == 1 )
                    v12 = "Verbose";
                  else
                    v12 = "???";
                }
                else
                {
                  v12 = "Information";
                }
              }
              else
              {
                v12 = "Warning";
              }
            }
            else
            {
              v12 = "Error";
            }
          }
          else
          {
            v12 = "Critical";
          }
        }
        else
        {
          v12 = "Trace";
        }
        v30 = v12;
        if ( (v6 & 2) != 0 )
        {
          v13 = GetCurrentThreadId();
          v14 = GetCurrentProcessId();
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
            v12,
            v31,
            v14,
            v13,
            a3);
        }
        else
        {
          memset_0(BackTrace, 0, sizeof(BackTrace));
          RtlCaptureStackBackTrace(0, 0xCu, BackTrace, 0);
          v15 = BackTrace[11];
          v16 = BackTrace[10];
          v17 = BackTrace[9];
          v18 = BackTrace[8];
          v19 = BackTrace[7];
          v20 = BackTrace[6];
          v21 = BackTrace[5];
          v33 = BackTrace[4];
          v34 = BackTrace[3];
          v35 = BackTrace[2];
          v36 = BackTrace[1];
          v37 = BackTrace[0];
          v32 = GetCurrentThreadId();
          v22 = GetCurrentProcessId();
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
            v30,
            v31,
            v22,
            v32,
            v38,
            v37,
            v36,
            v35,
            v34,
            v33,
            v21,
            v20,
            v19,
            v18,
            v17,
            v16,
            v15);
        }
      }
    }
    else
    {
      v25 = GetCurrentThreadId();
      v26 = GetCurrentProcessId();
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
        v26,
        v25,
        a3);
    }
    wil::run_as_self_failfast(&v30);
    for ( i = 0; i < 100; ++i )
    {
      if ( i > 0 )
        Sleep(0);
      if ( (int)StateRepository::Logging::_WriteLogToFile(Buffer, v27) >= 0 )
        break;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v30);
  }
}

```

## disassembly

```asm
0x1801862d4  mov     [rsp-8+arg_0], rbx
0x1801862d9  push    rbp
0x1801862da  push    rsi
0x1801862db  push    rdi
0x1801862dc  push    r12
0x1801862de  push    r13
0x1801862e0  push    r14
0x1801862e2  push    r15
0x1801862e4  lea     rbp, [rsp-840h]
0x1801862ec  sub     rsp, 9A0h
0x1801862f3  mov     rax, cs:__security_cookie
0x1801862fa  xor     rax, rsp
0x1801862fd  mov     [rbp+870h+var_40], rax
0x180186304  mov     r13, r8
0x180186307  mov     [rbp+870h+var_8B8], r8
0x18018630b  mov     r12d, edx
0x18018630e  mov     [rbp+870h+var_8E8], edx
0x180186311  mov     ebx, ecx
0x180186313  mov     edi, cs:dword_1802E1844
0x180186319  test    dil, 1
0x18018631d  jz      loc_180186776
0x180186323  xorps   xmm0, xmm0
0x180186326  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x18018632a  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x18018632e  call    cs:__imp_GetLocalTime
0x180186334  xor     edx, edx; Val
0x180186336  mov     r8d, 800h; Size
0x18018633c  lea     rcx, [rbp+870h+Buffer]; void *
0x180186340  call    memset_0
0x180186345  mov     ecx, ebx
0x180186347  test    ebx, ebx
0x180186349  jz      loc_1801866AB
0x18018634f  sub     ecx, 10h
0x180186352  jz      loc_180186623
0x180186358  sub     ecx, 10h
0x18018635b  jz      short loc_1801863A0
0x18018635d  sub     ecx, 1
0x180186360  jz      short loc_1801863A0
0x180186362  sub     ecx, 1
0x180186365  jz      short loc_1801863A0
0x180186367  sub     ecx, 1
0x18018636a  jz      short loc_1801863A0
0x18018636c  cmp     ecx, 1
0x18018636f  jz      short loc_1801863A0
0x180186371  mov     rcx, [rbp+878h]; this
0x180186378  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x18018637f  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x180186384  mov     r9d, 8000FFFFh; char *
0x18018638a  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180186391  mov     edx, 0F1h; void *
0x180186396  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18018639b  jmp     loc_180186776
0x1801863a0  test    ebx, ebx
0x1801863a2  jz      short loc_180186401
0x1801863a4  sub     ebx, 10h
0x1801863a7  jz      short loc_1801863F8
0x1801863a9  sub     ebx, 10h
0x1801863ac  jz      short loc_1801863EF
0x1801863ae  sub     ebx, 1
0x1801863b1  jz      short loc_1801863E6
0x1801863b3  sub     ebx, 1
0x1801863b6  jz      short loc_1801863DD
0x1801863b8  sub     ebx, 1
0x1801863bb  jz      short loc_1801863D4
0x1801863bd  cmp     ebx, 1
0x1801863c0  jz      short loc_1801863CB
0x1801863c2  lea     r12, asc_18027CD50; "???"
0x1801863c9  jmp     short loc_180186408
0x1801863cb  lea     r12, aVerbose; "Verbose"
0x1801863d2  jmp     short loc_180186408
0x1801863d4  lea     r12, aInformation; "Information"
0x1801863db  jmp     short loc_180186408
0x1801863dd  lea     r12, aWarning; "Warning"
0x1801863e4  jmp     short loc_180186408
0x1801863e6  lea     r12, aError_0; "Error"
0x1801863ed  jmp     short loc_180186408
0x1801863ef  lea     r12, aCritical; "Critical"
0x1801863f6  jmp     short loc_180186408
0x1801863f8  lea     r12, aTrace; "Trace"
0x1801863ff  jmp     short loc_180186408
0x180186401  lea     r12, aProfile; "Profile"
0x180186408  mov     [rbp+870h+var_8F0], r12
0x18018640c  test    dil, 2
0x180186410  jz      loc_1801864AA
0x180186416  call    cs:__imp_GetCurrentThreadId
0x18018641c  mov     ebx, eax
0x18018641e  call    cs:__imp_GetCurrentProcessId
0x180186424  mov     r8d, eax
0x180186427  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18018642c  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180186431  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x180186435  movzx   esi, [rbp+870h+SystemTime.wHour]
0x180186439  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x18018643e  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x180186443  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x180186448  mov     eax, 51EB851Fh
0x18018644d  mul     r9d
0x180186450  shr     edx, 5
0x180186453  imul    ecx, edx, 64h ; 'd'
0x180186456  sub     r9d, ecx
0x180186459  mov     [rsp+9D0h+var_960], r13
0x18018645e  mov     dword ptr [rsp+9D0h+var_968], ebx
0x180186462  mov     dword ptr [rsp+9D0h+var_970], r8d
0x180186467  mov     eax, [rbp+870h+var_8E8]
0x18018646a  mov     [rsp+9D0h+var_978], eax
0x18018646e  mov     [rsp+9D0h+var_980], r12
0x180186473  mov     [rsp+9D0h+var_988], r10d
0x180186478  mov     [rsp+9D0h+var_990], r11d
0x18018647d  mov     [rsp+9D0h+var_998], edi
0x180186481  mov     [rsp+9D0h+var_9A0], esi
0x180186485  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x18018648a  mov     [rsp+9D0h+var_9B0], r15d
0x18018648f  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x180186496  lea     rdx, [rbp+870h+Buffer]
0x18018649a  mov     ecx, 800h
0x18018649f  call    cs:__imp_sqlite3_snprintf
0x1801864a5  jmp     loc_180186733
0x1801864aa  xor     edx, edx; Val
0x1801864ac  lea     r8d, [rdx+60h]; Size
0x1801864b0  lea     rcx, [rbp+870h+BackTrace]; void *
0x1801864b4  call    memset_0
0x1801864b9  xor     r9d, r9d; BackTraceHash
0x1801864bc  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x1801864c0  lea     edx, [r9+0Ch]; FramesToCapture
0x1801864c4  xor     ecx, ecx; FramesToSkip
0x1801864c6  call    cs:__imp_RtlCaptureStackBackTrace
0x1801864cc  mov     rbx, [rbp+870h+var_848]
0x1801864d0  mov     rdi, [rbp+870h+var_850]
0x1801864d4  mov     rsi, [rbp+870h+var_858]
0x1801864d8  mov     r14, [rbp+870h+var_860]
0x1801864dc  mov     r15, [rbp+870h+var_868]
0x1801864e0  mov     r12, [rbp+870h+var_870]
0x1801864e4  mov     r13, [rbp+870h+var_878]
0x1801864e8  mov     rax, [rbp+870h+var_880]
0x1801864ec  mov     [rbp+870h+var_8E0], rax
0x1801864f0  mov     rax, [rbp+870h+var_888]
0x1801864f4  mov     [rbp+870h+var_8D8], rax
0x1801864f8  mov     rax, [rbp+870h+var_890]
0x1801864fc  mov     [rbp+870h+var_8D0], rax
0x180186500  mov     rax, [rbp+870h+var_898]
0x180186504  mov     [rbp+870h+var_8C8], rax
0x180186508  mov     rax, [rbp+870h+BackTrace]
0x18018650c  mov     [rbp+870h+var_8C0], rax
0x180186510  call    cs:__imp_GetCurrentThreadId
0x180186516  mov     [rbp+870h+var_8E4], eax
0x180186519  call    cs:__imp_GetCurrentProcessId
0x18018651f  mov     r8d, eax
0x180186522  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180186527  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18018652c  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x180186531  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x180186535  mov     eax, 51EB851Fh
0x18018653a  mul     ecx
0x18018653c  shr     edx, 5
0x18018653f  imul    ecx, edx, 64h ; 'd'
0x180186542  movzx   edx, [rbp+870h+SystemTime.wYear]
0x180186546  sub     edx, ecx
0x180186548  mov     [rsp+9D0h+var_900], rbx
0x180186550  mov     [rsp+9D0h+var_908], rdi
0x180186558  mov     [rsp+9D0h+var_910], rsi
0x180186560  mov     [rsp+9D0h+var_918], r14
0x180186568  mov     [rsp+9D0h+var_920], r15
0x180186570  mov     [rsp+9D0h+var_928], r12
0x180186578  mov     [rsp+9D0h+var_930], r13
0x180186580  mov     rax, [rbp+870h+var_8E0]
0x180186584  mov     [rsp+9D0h+var_938], rax
0x18018658c  mov     rax, [rbp+870h+var_8D8]
0x180186590  mov     [rsp+9D0h+var_940], rax
0x180186598  mov     rax, [rbp+870h+var_8D0]
0x18018659c  mov     [rsp+9D0h+var_948], rax
0x1801865a4  mov     rax, [rbp+870h+var_8C8]
0x1801865a8  mov     [rsp+9D0h+var_950], rax
0x1801865b0  mov     rax, [rbp+870h+var_8C0]
0x1801865b4  mov     [rsp+9D0h+var_958], rax
0x1801865b9  mov     rax, [rbp+870h+var_8B8]
0x1801865bd  mov     [rsp+9D0h+var_960], rax
0x1801865c2  mov     eax, [rbp+870h+var_8E4]
0x1801865c5  mov     dword ptr [rsp+9D0h+var_968], eax
0x1801865c9  mov     dword ptr [rsp+9D0h+var_970], r8d
0x1801865ce  mov     eax, [rbp+870h+var_8E8]
0x1801865d1  mov     [rsp+9D0h+var_978], eax
0x1801865d5  mov     rax, [rbp+870h+var_8F0]
0x1801865d9  mov     [rsp+9D0h+var_980], rax
0x1801865de  mov     [rsp+9D0h+var_988], r10d
0x1801865e3  mov     [rsp+9D0h+var_990], r11d
0x1801865e8  mov     [rsp+9D0h+var_998], r9d
0x1801865ed  movzx   eax, [rbp+870h+SystemTime.wHour]
0x1801865f1  mov     [rsp+9D0h+var_9A0], eax
0x1801865f5  movzx   eax, [rbp+870h+SystemTime.wDay]
0x1801865f9  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x1801865fd  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x180186601  mov     [rsp+9D0h+var_9B0], eax
0x180186605  mov     r9d, edx
0x180186608  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x18018660f  lea     rdx, [rbp+870h+Buffer]
0x180186613  mov     ecx, 800h
0x180186618  call    cs:__imp_sqlite3_snprintf
0x18018661e  jmp     loc_180186733
0x180186623  call    cs:__imp_GetCurrentThreadId
0x180186629  mov     r15d, eax
0x18018662c  call    cs:__imp_GetCurrentProcessId
0x180186632  mov     r8d, eax
0x180186635  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18018663a  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18018663f  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x180186643  movzx   edi, [rbp+870h+SystemTime.wHour]
0x180186647  movzx   esi, [rbp+870h+SystemTime.wDay]
0x18018664b  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x180186650  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x180186655  mov     eax, 51EB851Fh
0x18018665a  mul     r9d
0x18018665d  shr     edx, 5
0x180186660  imul    ecx, edx, 64h ; 'd'
0x180186663  sub     r9d, ecx
0x180186666  mov     [rsp+9D0h+var_970], r13
0x18018666b  mov     [rsp+9D0h+var_978], r15d
0x180186670  mov     dword ptr [rsp+9D0h+var_980], r8d
0x180186675  mov     [rsp+9D0h+var_988], r10d
0x18018667a  mov     [rsp+9D0h+var_990], r11d
0x18018667f  mov     [rsp+9D0h+var_998], ebx
0x180186683  mov     [rsp+9D0h+var_9A0], edi
0x180186687  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x18018668b  mov     [rsp+9D0h+var_9B0], r14d
0x180186690  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x180186697  lea     rdx, [rbp+870h+Buffer]
0x18018669b  mov     ecx, 800h
0x1801866a0  call    cs:__imp_sqlite3_snprintf
0x1801866a6  jmp     loc_180186733
0x1801866ab  call    cs:__imp_GetCurrentThreadId
0x1801866b1  mov     ebx, eax
0x1801866b3  call    cs:__imp_GetCurrentProcessId
0x1801866b9  mov     r8d, eax
0x1801866bc  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1801866c1  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1801866c6  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1801866ca  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1801866ce  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1801866d3  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x1801866d8  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1801866dd  mov     eax, 51EB851Fh
0x1801866e2  mul     r9d
0x1801866e5  shr     edx, 5
0x1801866e8  imul    ecx, edx, 64h ; 'd'
0x1801866eb  sub     r9d, ecx
0x1801866ee  mov     [rsp+9D0h+var_968], r13
0x1801866f3  mov     dword ptr [rsp+9D0h+var_970], ebx
0x1801866f7  mov     [rsp+9D0h+var_978], r8d
0x1801866fc  mov     dword ptr [rsp+9D0h+var_980], r12d
0x180186701  mov     [rsp+9D0h+var_988], r10d
0x180186706  mov     [rsp+9D0h+var_990], r11d
0x18018670b  mov     [rsp+9D0h+var_998], edi
0x18018670f  mov     [rsp+9D0h+var_9A0], esi
0x180186713  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180186718  mov     [rsp+9D0h+var_9B0], r15d
0x18018671d  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x180186724  lea     rdx, [rbp+870h+Buffer]
0x180186728  mov     ecx, 800h
0x18018672d  call    cs:__imp_sqlite3_snprintf
0x180186733  lea     rcx, [rbp+870h+var_8F0]
0x180186737  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x18018673c  xor     ebx, ebx
0x18018673e  cmp     ebx, 64h ; 'd'
0x180186741  jge     short loc_18018676C
0x180186743  test    ebx, ebx
0x180186745  jle     short loc_18018674F
0x180186747  xor     ecx, ecx; dwMilliseconds
0x180186749  call    cs:__imp_Sleep
0x18018674f  lea     rcx, [rbp+870h+Buffer]; lpBuffer
0x180186753  call    ?_WriteLogToFile@Logging@StateRepository@@YAJPEBD@Z; StateRepository::Logging::_WriteLogToFile(char const *)
0x180186758  test    eax, eax
0x18018675a  jns     short loc_180186760
0x18018675c  inc     ebx
0x18018675e  jmp     short loc_18018673E
0x180186760  lea     rcx, [rbp+870h+var_8F0]
0x180186764  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180186769  nop
0x18018676a  jmp     short loc_180186776
0x18018676c  lea     rcx, [rbp+870h+var_8F0]
0x180186770  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180186775  nop
0x180186776  mov     rcx, [rbp+870h+var_40]
0x18018677d  xor     rcx, rsp; StackCookie
0x180186780  call    __security_check_cookie
0x180186785  mov     rbx, [rsp+9D0h+arg_0]
0x18018678d  add     rsp, 9A0h
0x180186794  pop     r15
0x180186796  pop     r14
0x180186798  pop     r13
0x18018679a  pop     r12
0x18018679c  pop     rdi
0x18018679d  pop     rsi
0x18018679e  pop     rbp
0x18018679f  retn
```
