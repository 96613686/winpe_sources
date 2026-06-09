# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x180103488`
- end: `0x180103916`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1166`
- prototype: `void __fastcall(int, int, const char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180104450`
- `0x180104690`
- `0x1801046f0`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005640`
- `0x1800fa588`
- `0x180103488`
- `0x180103f28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801035d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801036cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801037de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180103864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801035d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801036cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801037de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180103864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801035ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801036c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801037d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010385c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801035ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801036c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801037d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010385c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1801034e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1801034e2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180103679`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180103679`

## string_xrefs

- `0x18010353e`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
void __fastcall StateRepository::Logging::LogToFile(int a1, int a2, const char *a3)
{
  char v3; // di
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  const char *v12; // r12
  DWORD v13; // ebx
  DWORD v14; // eax
  const char *v15; // rdx
  PVOID v16; // rbx
  PVOID v17; // rdi
  PVOID v18; // rsi
  PVOID v19; // r14
  PVOID v20; // r15
  PVOID v21; // r12
  PVOID v22; // r13
  DWORD v23; // eax
  DWORD CurrentThreadId; // r15d
  DWORD CurrentProcessId; // eax
  DWORD v26; // ebx
  DWORD v27; // eax
  const char *v28; // [rsp+28h] [rbp-138h]
  const char *v29; // [rsp+E0h] [rbp-80h]
  DWORD v31; // [rsp+ECh] [rbp-74h]
  PVOID v32; // [rsp+F0h] [rbp-70h]
  PVOID v33; // [rsp+F8h] [rbp-68h]
  PVOID v34; // [rsp+100h] [rbp-60h]
  PVOID v35; // [rsp+108h] [rbp-58h]
  PVOID v36; // [rsp+110h] [rbp-50h]
  _SYSTEMTIME SystemTime; // [rsp+120h] [rbp-40h] BYREF
  PVOID BackTrace[12]; // [rsp+130h] [rbp-30h] BYREF
  _BYTE Buffer[2048]; // [rsp+190h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+878h]

  v3 = dword_18013F948;
  if ( (dword_18013F948 & 1) != 0 )
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
            v28);
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
        v29 = v12;
        if ( (v3 & 2) != 0 )
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
            a2,
            v14,
            v13,
            a3);
        }
        else
        {
          memset_0(BackTrace, 0, sizeof(BackTrace));
          RtlCaptureStackBackTrace(0, 0xCu, BackTrace, 0);
          v16 = BackTrace[11];
          v17 = BackTrace[10];
          v18 = BackTrace[9];
          v19 = BackTrace[8];
          v20 = BackTrace[7];
          v21 = BackTrace[6];
          v22 = BackTrace[5];
          v32 = BackTrace[4];
          v33 = BackTrace[3];
          v34 = BackTrace[2];
          v35 = BackTrace[1];
          v36 = BackTrace[0];
          v31 = GetCurrentThreadId();
          v23 = GetCurrentProcessId();
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
            v29,
            a2,
            v23,
            v31,
            a3,
            v36,
            v35,
            v34,
            v33,
            v32,
            v22,
            v21,
            v20,
            v19,
            v18,
            v17,
            v16);
        }
      }
    }
    else
    {
      v26 = GetCurrentThreadId();
      v27 = GetCurrentProcessId();
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
        v27,
        v26,
        a3);
    }
    StateRepository::Logging::WriteLogToFile(Buffer, v15);
  }
}

```

## disassembly

```asm
0x180103488  mov     [rsp-8+arg_0], rbx
0x18010348d  push    rbp
0x18010348e  push    rsi
0x18010348f  push    rdi
0x180103490  push    r12
0x180103492  push    r13
0x180103494  push    r14
0x180103496  push    r15
0x180103498  lea     rbp, [rsp-840h]
0x1801034a0  sub     rsp, 9A0h
0x1801034a7  mov     rax, cs:__security_cookie
0x1801034ae  xor     rax, rsp
0x1801034b1  mov     [rbp+870h+var_40], rax
0x1801034b8  mov     edi, cs:dword_18013F948
0x1801034be  mov     r13, r8
0x1801034c1  mov     [rbp+870h+var_8B8], r8
0x1801034c5  mov     r12d, edx
0x1801034c8  mov     [rbp+870h+var_8E8], edx
0x1801034cb  mov     ebx, ecx
0x1801034cd  test    dil, 1
0x1801034d1  jz      loc_1801038EC
0x1801034d7  xorps   xmm0, xmm0
0x1801034da  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x1801034de  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x1801034e2  call    cs:__imp_GetLocalTime
0x1801034e8  xor     edx, edx; Val
0x1801034ea  lea     rcx, [rbp+870h+Buffer]; void *
0x1801034ee  mov     r8d, 800h; Size
0x1801034f4  call    memset_0
0x1801034f9  mov     ecx, ebx
0x1801034fb  test    ebx, ebx
0x1801034fd  jz      loc_18010385C
0x180103503  sub     ecx, 10h
0x180103506  jz      loc_1801037D5
0x18010350c  sub     ecx, 10h
0x18010350f  jz      short loc_180103554
0x180103511  sub     ecx, 1
0x180103514  jz      short loc_180103554
0x180103516  sub     ecx, 1
0x180103519  jz      short loc_180103554
0x18010351b  sub     ecx, 1
0x18010351e  jz      short loc_180103554
0x180103520  cmp     ecx, 1
0x180103523  jz      short loc_180103554
0x180103525  mov     rcx, [rbp+878h]; this
0x18010352c  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x180103533  mov     r9d, 8000FFFFh; char *
0x180103539  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x18010353e  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180103545  mov     edx, 0F1h; void *
0x18010354a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010354f  jmp     loc_1801038EC
0x180103554  test    ebx, ebx
0x180103556  jz      short loc_1801035B5
0x180103558  sub     ebx, 10h
0x18010355b  jz      short loc_1801035AC
0x18010355d  sub     ebx, 10h
0x180103560  jz      short loc_1801035A3
0x180103562  sub     ebx, 1
0x180103565  jz      short loc_18010359A
0x180103567  sub     ebx, 1
0x18010356a  jz      short loc_180103591
0x18010356c  sub     ebx, 1
0x18010356f  jz      short loc_180103588
0x180103571  cmp     ebx, 1
0x180103574  jz      short loc_18010357F
0x180103576  lea     r12, asc_1801278FC; "???"
0x18010357d  jmp     short loc_1801035BC
0x18010357f  lea     r12, aVerbose; "Verbose"
0x180103586  jmp     short loc_1801035BC
0x180103588  lea     r12, aInformation; "Information"
0x18010358f  jmp     short loc_1801035BC
0x180103591  lea     r12, aWarning; "Warning"
0x180103598  jmp     short loc_1801035BC
0x18010359a  lea     r12, aError; "Error"
0x1801035a1  jmp     short loc_1801035BC
0x1801035a3  lea     r12, aCritical; "Critical"
0x1801035aa  jmp     short loc_1801035BC
0x1801035ac  lea     r12, aTrace; "Trace"
0x1801035b3  jmp     short loc_1801035BC
0x1801035b5  lea     r12, aProfile; "Profile"
0x1801035bc  mov     [rbp+870h+var_8F0], r12
0x1801035c0  test    dil, 2
0x1801035c4  jz      loc_18010365D
0x1801035ca  call    cs:__imp_GetCurrentThreadId
0x1801035d0  mov     ebx, eax
0x1801035d2  call    cs:__imp_GetCurrentProcessId
0x1801035d8  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1801035dd  mov     r8d, eax
0x1801035e0  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1801035e5  mov     eax, 51EB851Fh
0x1801035ea  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1801035ef  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x1801035f3  movzx   esi, [rbp+870h+SystemTime.wHour]
0x1801035f7  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x1801035fc  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x180103601  mov     [rsp+9D0h+var_960], r13
0x180103606  mov     dword ptr [rsp+9D0h+var_968], ebx
0x18010360a  mov     dword ptr [rsp+9D0h+var_970], r8d
0x18010360f  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x180103616  mul     r9d
0x180103619  mov     eax, [rbp+870h+var_8E8]
0x18010361c  mov     [rsp+9D0h+var_978], eax
0x180103620  mov     [rsp+9D0h+var_980], r12
0x180103625  mov     [rsp+9D0h+var_988], r10d
0x18010362a  mov     [rsp+9D0h+var_990], r11d
0x18010362f  shr     edx, 5
0x180103632  imul    ecx, edx, 64h ; 'd'
0x180103635  lea     rdx, [rbp+870h+Buffer]
0x180103639  mov     [rsp+9D0h+var_998], edi
0x18010363d  mov     [rsp+9D0h+var_9A0], esi
0x180103641  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180103646  mov     [rsp+9D0h+var_9B0], r15d
0x18010364b  sub     r9d, ecx
0x18010364e  mov     ecx, 800h
0x180103653  call    sqlite3_snprintf
0x180103658  jmp     loc_1801038E3
0x18010365d  xor     edx, edx; Val
0x18010365f  lea     rcx, [rbp+870h+BackTrace]; void *
0x180103663  lea     r8d, [rdx+60h]; Size
0x180103667  call    memset_0
0x18010366c  xor     r9d, r9d; BackTraceHash
0x18010366f  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x180103673  xor     ecx, ecx; FramesToSkip
0x180103675  lea     edx, [r9+0Ch]; FramesToCapture
0x180103679  call    cs:__imp_RtlCaptureStackBackTrace
0x18010367f  mov     rax, [rbp+870h+var_880]
0x180103683  mov     rbx, [rbp+870h+var_848]
0x180103687  mov     rdi, [rbp+870h+var_850]
0x18010368b  mov     rsi, [rbp+870h+var_858]
0x18010368f  mov     r14, [rbp+870h+var_860]
0x180103693  mov     r15, [rbp+870h+var_868]
0x180103697  mov     r12, [rbp+870h+var_870]
0x18010369b  mov     r13, [rbp+870h+var_878]
0x18010369f  mov     [rbp+870h+var_8E0], rax
0x1801036a3  mov     rax, [rbp+870h+var_888]
0x1801036a7  mov     [rbp+870h+var_8D8], rax
0x1801036ab  mov     rax, [rbp+870h+var_890]
0x1801036af  mov     [rbp+870h+var_8D0], rax
0x1801036b3  mov     rax, [rbp+870h+var_898]
0x1801036b7  mov     [rbp+870h+var_8C8], rax
0x1801036bb  mov     rax, [rbp+870h+BackTrace]
0x1801036bf  mov     [rbp+870h+var_8C0], rax
0x1801036c3  call    cs:__imp_GetCurrentThreadId
0x1801036c9  mov     [rbp+870h+var_8E4], eax
0x1801036cc  call    cs:__imp_GetCurrentProcessId
0x1801036d2  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x1801036d6  mov     r8d, eax
0x1801036d9  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x1801036de  mov     eax, 51EB851Fh
0x1801036e3  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1801036e8  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1801036ed  mov     [rsp+9D0h+var_900], rbx
0x1801036f5  mov     [rsp+9D0h+var_908], rdi
0x1801036fd  mov     [rsp+9D0h+var_910], rsi
0x180103705  mov     [rsp+9D0h+var_918], r14
0x18010370d  mov     [rsp+9D0h+var_920], r15
0x180103715  mul     ecx
0x180103717  mov     rax, [rbp+870h+var_8E0]
0x18010371b  mov     [rsp+9D0h+var_928], r12
0x180103723  mov     [rsp+9D0h+var_930], r13
0x18010372b  mov     [rsp+9D0h+var_938], rax
0x180103733  mov     rax, [rbp+870h+var_8D8]
0x180103737  mov     [rsp+9D0h+var_940], rax
0x18010373f  mov     rax, [rbp+870h+var_8D0]
0x180103743  mov     [rsp+9D0h+var_948], rax
0x18010374b  mov     rax, [rbp+870h+var_8C8]
0x18010374f  mov     [rsp+9D0h+var_950], rax
0x180103757  mov     rax, [rbp+870h+var_8C0]
0x18010375b  mov     [rsp+9D0h+var_958], rax
0x180103760  mov     rax, [rbp+870h+var_8B8]
0x180103764  mov     [rsp+9D0h+var_960], rax
0x180103769  mov     eax, [rbp+870h+var_8E4]
0x18010376c  mov     dword ptr [rsp+9D0h+var_968], eax
0x180103770  mov     eax, [rbp+870h+var_8E8]
0x180103773  mov     dword ptr [rsp+9D0h+var_970], r8d
0x180103778  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x18010377f  mov     [rsp+9D0h+var_978], eax
0x180103783  mov     rax, [rbp+870h+var_8F0]
0x180103787  mov     [rsp+9D0h+var_980], rax
0x18010378c  movzx   eax, [rbp+870h+SystemTime.wHour]
0x180103790  mov     [rsp+9D0h+var_988], r10d
0x180103795  shr     edx, 5
0x180103798  imul    ecx, edx, 64h ; 'd'
0x18010379b  movzx   edx, [rbp+870h+SystemTime.wYear]
0x18010379f  mov     [rsp+9D0h+var_990], r11d
0x1801037a4  mov     [rsp+9D0h+var_998], r9d
0x1801037a9  mov     [rsp+9D0h+var_9A0], eax
0x1801037ad  movzx   eax, [rbp+870h+SystemTime.wDay]
0x1801037b1  sub     edx, ecx
0x1801037b3  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x1801037b7  mov     r9d, edx
0x1801037ba  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x1801037be  lea     rdx, [rbp+870h+Buffer]
0x1801037c2  mov     ecx, 800h
0x1801037c7  mov     [rsp+9D0h+var_9B0], eax
0x1801037cb  call    sqlite3_snprintf
0x1801037d0  jmp     loc_1801038E3
0x1801037d5  call    cs:__imp_GetCurrentThreadId
0x1801037db  mov     r15d, eax
0x1801037de  call    cs:__imp_GetCurrentProcessId
0x1801037e4  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x1801037e9  mov     r8d, eax
0x1801037ec  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x1801037f1  mov     eax, 51EB851Fh
0x1801037f6  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x1801037fb  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x1801037ff  movzx   edi, [rbp+870h+SystemTime.wHour]
0x180103803  movzx   esi, [rbp+870h+SystemTime.wDay]
0x180103807  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x18010380c  mov     [rsp+9D0h+var_970], r13
0x180103811  mov     [rsp+9D0h+var_978], r15d
0x180103816  mov     dword ptr [rsp+9D0h+var_980], r8d
0x18010381b  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x180103822  mov     [rsp+9D0h+var_988], r10d
0x180103827  mov     [rsp+9D0h+var_990], r11d
0x18010382c  mul     r9d
0x18010382f  mov     [rsp+9D0h+var_998], ebx
0x180103833  shr     edx, 5
0x180103836  imul    ecx, edx, 64h ; 'd'
0x180103839  lea     rdx, [rbp+870h+Buffer]
0x18010383d  mov     [rsp+9D0h+var_9A0], edi
0x180103841  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x180103845  mov     [rsp+9D0h+var_9B0], r14d
0x18010384a  sub     r9d, ecx
0x18010384d  mov     ecx, 800h
0x180103852  call    sqlite3_snprintf
0x180103857  jmp     loc_1801038E3
0x18010385c  call    cs:__imp_GetCurrentThreadId
0x180103862  mov     ebx, eax
0x180103864  call    cs:__imp_GetCurrentProcessId
0x18010386a  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x18010386f  mov     r8d, eax
0x180103872  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x180103877  mov     eax, 51EB851Fh
0x18010387c  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x180103881  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x180103885  movzx   esi, [rbp+870h+SystemTime.wHour]
0x180103889  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x18010388e  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x180103893  mov     [rsp+9D0h+var_968], r13
0x180103898  mov     dword ptr [rsp+9D0h+var_970], ebx
0x18010389c  mov     [rsp+9D0h+var_978], r8d
0x1801038a1  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x1801038a8  mov     dword ptr [rsp+9D0h+var_980], r12d
0x1801038ad  mov     [rsp+9D0h+var_988], r10d
0x1801038b2  mov     [rsp+9D0h+var_990], r11d
0x1801038b7  mul     r9d
0x1801038ba  mov     [rsp+9D0h+var_998], edi
0x1801038be  shr     edx, 5
0x1801038c1  imul    ecx, edx, 64h ; 'd'
0x1801038c4  lea     rdx, [rbp+870h+Buffer]
0x1801038c8  mov     [rsp+9D0h+var_9A0], esi
0x1801038cc  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x1801038d1  mov     [rsp+9D0h+var_9B0], r15d
0x1801038d6  sub     r9d, ecx
0x1801038d9  mov     ecx, 800h
0x1801038de  call    sqlite3_snprintf
0x1801038e3  lea     rcx, [rbp+870h+Buffer]; lpBuffer
0x1801038e7  call    ?WriteLogToFile@Logging@StateRepository@@YAXPEBD@Z; StateRepository::Logging::WriteLogToFile(char const *)
0x1801038ec  mov     rcx, [rbp+870h+var_40]
0x1801038f3  xor     rcx, rsp; StackCookie
0x1801038f6  call    __security_check_cookie
0x1801038fb  mov     rbx, [rsp+9D0h+arg_0]
0x180103903  add     rsp, 9A0h
0x18010390a  pop     r15
0x18010390c  pop     r14
0x18010390e  pop     r13
0x180103910  pop     r12
0x180103912  pop     rdi
0x180103913  pop     rsi
0x180103914  pop     rbp
0x180103915  retn
```
