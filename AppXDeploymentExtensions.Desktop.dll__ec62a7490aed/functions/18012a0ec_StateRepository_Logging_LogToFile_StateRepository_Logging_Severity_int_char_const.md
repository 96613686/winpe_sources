# StateRepository::Logging::LogToFile(StateRepository::Logging::Severity,int,char const *)

- ea: `0x18012a0ec`
- end: `0x18012a613`
- name: `?LogToFile@Logging@StateRepository@@YAXW4Severity@12@HPEBD@Z`
- size: `1319`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18012acd0`
- `0x18012aef0`
- `0x18012af50`

## callees

- `0x180006564`
- `0x18004ce78`
- `0x180075bdc`
- `0x1800ab918`
- `0x1800aed10`
- `0x1800af918`
- `0x18012a0ec`

## import_xrefs

- `StateRepository.Core!sqlite3_snprintf` at `0x18012a2c9`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a45a`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a4f4`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a593`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a2c9`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a45a`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a4f4`
- `StateRepository.Core!sqlite3_snprintf` at `0x18012a593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a46b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a46b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012a505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a47a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a513`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a47a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012a513`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012a5b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18012a5b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18012a146`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18012a146`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18012a2f6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18012a2f6`

## string_xrefs

- `0x18012a1a8`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

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
  v6 = dword_180245004;
  if ( (dword_180245004 & 1) != 0 )
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
0x18012a0ec  mov     [rsp-8+arg_0], rbx
0x18012a0f1  push    rbp
0x18012a0f2  push    rsi
0x18012a0f3  push    rdi
0x18012a0f4  push    r12
0x18012a0f6  push    r13
0x18012a0f8  push    r14
0x18012a0fa  push    r15
0x18012a0fc  lea     rbp, [rsp-840h]
0x18012a104  sub     rsp, 9A0h
0x18012a10b  mov     rax, cs:__security_cookie
0x18012a112  xor     rax, rsp
0x18012a115  mov     [rbp+870h+var_40], rax
0x18012a11c  mov     r13, r8
0x18012a11f  mov     [rbp+870h+var_8B8], r8
0x18012a123  mov     r12d, edx
0x18012a126  mov     [rbp+870h+var_8E8], edx
0x18012a129  mov     ebx, ecx
0x18012a12b  mov     edi, cs:dword_180245004
0x18012a131  test    dil, 1
0x18012a135  jz      loc_18012A5E8
0x18012a13b  xorps   xmm0, xmm0
0x18012a13e  movups  xmmword ptr [rbp+870h+SystemTime.wYear], xmm0
0x18012a142  lea     rcx, [rbp+870h+SystemTime]; lpSystemTime
0x18012a146  call    cs:__imp_GetLocalTime
0x18012a14d  nop     dword ptr [rax+rax+00h]
0x18012a152  xor     edx, edx; Val
0x18012a154  mov     r8d, 800h; Size
0x18012a15a  lea     rcx, [rbp+870h+Buffer]; void *
0x18012a15e  call    memset_0
0x18012a163  mov     ecx, ebx
0x18012a165  test    ebx, ebx
0x18012a167  jz      loc_18012A505
0x18012a16d  sub     ecx, 10h
0x18012a170  jz      loc_18012A46B
0x18012a176  sub     ecx, 10h
0x18012a179  jz      short loc_18012A1BE
0x18012a17b  sub     ecx, 1
0x18012a17e  jz      short loc_18012A1BE
0x18012a180  sub     ecx, 1
0x18012a183  jz      short loc_18012A1BE
0x18012a185  sub     ecx, 1
0x18012a188  jz      short loc_18012A1BE
0x18012a18a  cmp     ecx, 1
0x18012a18d  jz      short loc_18012A1BE
0x18012a18f  mov     rcx, [rbp+878h]; this
0x18012a196  lea     rax, aLogtofileSever; "LogToFile(severity=Unknown,...)"
0x18012a19d  mov     qword ptr [rsp+9D0h+var_9B0], rax; int
0x18012a1a2  mov     r9d, 8000FFFFh; char *
0x18012a1a8  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18012a1af  mov     edx, 0F1h; void *
0x18012a1b4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012a1b9  jmp     loc_18012A5E8
0x18012a1be  test    ebx, ebx
0x18012a1c0  jz      short loc_18012A21F
0x18012a1c2  sub     ebx, 10h
0x18012a1c5  jz      short loc_18012A216
0x18012a1c7  sub     ebx, 10h
0x18012a1ca  jz      short loc_18012A20D
0x18012a1cc  sub     ebx, 1
0x18012a1cf  jz      short loc_18012A204
0x18012a1d1  sub     ebx, 1
0x18012a1d4  jz      short loc_18012A1FB
0x18012a1d6  sub     ebx, 1
0x18012a1d9  jz      short loc_18012A1F2
0x18012a1db  cmp     ebx, 1
0x18012a1de  jz      short loc_18012A1E9
0x18012a1e0  lea     r12, asc_1801F1BB0; "???"
0x18012a1e7  jmp     short loc_18012A226
0x18012a1e9  lea     r12, aVerbose; "Verbose"
0x18012a1f0  jmp     short loc_18012A226
0x18012a1f2  lea     r12, aInformation; "Information"
0x18012a1f9  jmp     short loc_18012A226
0x18012a1fb  lea     r12, aWarning; "Warning"
0x18012a202  jmp     short loc_18012A226
0x18012a204  lea     r12, aError; "Error"
0x18012a20b  jmp     short loc_18012A226
0x18012a20d  lea     r12, aCritical; "Critical"
0x18012a214  jmp     short loc_18012A226
0x18012a216  lea     r12, aTrace; "Trace"
0x18012a21d  jmp     short loc_18012A226
0x18012a21f  lea     r12, aProfile_0; "Profile"
0x18012a226  mov     [rbp+870h+var_8F0], r12
0x18012a22a  test    dil, 2
0x18012a22e  jz      loc_18012A2DA
0x18012a234  call    cs:__imp_GetCurrentThreadId
0x18012a23b  nop     dword ptr [rax+rax+00h]
0x18012a240  mov     ebx, eax
0x18012a242  call    cs:__imp_GetCurrentProcessId
0x18012a249  nop     dword ptr [rax+rax+00h]
0x18012a24e  mov     r8d, eax
0x18012a251  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18012a256  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18012a25b  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x18012a25f  movzx   esi, [rbp+870h+SystemTime.wHour]
0x18012a263  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x18012a268  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x18012a26d  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x18012a272  mov     eax, 51EB851Fh
0x18012a277  mul     r9d
0x18012a27a  shr     edx, 5
0x18012a27d  imul    ecx, edx, 64h ; 'd'
0x18012a280  sub     r9d, ecx
0x18012a283  mov     [rsp+9D0h+var_960], r13
0x18012a288  mov     dword ptr [rsp+9D0h+var_968], ebx
0x18012a28c  mov     dword ptr [rsp+9D0h+var_970], r8d
0x18012a291  mov     eax, [rbp+870h+var_8E8]
0x18012a294  mov     [rsp+9D0h+var_978], eax
0x18012a298  mov     [rsp+9D0h+var_980], r12
0x18012a29d  mov     [rsp+9D0h+var_988], r10d
0x18012a2a2  mov     [rsp+9D0h+var_990], r11d
0x18012a2a7  mov     [rsp+9D0h+var_998], edi
0x18012a2ab  mov     [rsp+9D0h+var_9A0], esi
0x18012a2af  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x18012a2b4  mov     [rsp+9D0h+var_9B0], r15d
0x18012a2b9  lea     r8, a02u02u02u02u02_1; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x18012a2c0  lea     rdx, [rbp+870h+Buffer]
0x18012a2c4  mov     ecx, 800h
0x18012a2c9  call    cs:__imp_sqlite3_snprintf
0x18012a2d0  nop     dword ptr [rax+rax+00h]
0x18012a2d5  jmp     loc_18012A59F
0x18012a2da  xor     edx, edx; Val
0x18012a2dc  lea     r8d, [rdx+60h]; Size
0x18012a2e0  lea     rcx, [rbp+870h+BackTrace]; void *
0x18012a2e4  call    memset_0
0x18012a2e9  xor     r9d, r9d; BackTraceHash
0x18012a2ec  lea     r8, [rbp+870h+BackTrace]; BackTrace
0x18012a2f0  lea     edx, [r9+0Ch]; FramesToCapture
0x18012a2f4  xor     ecx, ecx; FramesToSkip
0x18012a2f6  call    cs:__imp_RtlCaptureStackBackTrace
0x18012a2fd  nop     dword ptr [rax+rax+00h]
0x18012a302  mov     rbx, [rbp+870h+var_848]
0x18012a306  mov     rdi, [rbp+870h+var_850]
0x18012a30a  mov     rsi, [rbp+870h+var_858]
0x18012a30e  mov     r14, [rbp+870h+var_860]
0x18012a312  mov     r15, [rbp+870h+var_868]
0x18012a316  mov     r12, [rbp+870h+var_870]
0x18012a31a  mov     r13, [rbp+870h+var_878]
0x18012a31e  mov     rax, [rbp+870h+var_880]
0x18012a322  mov     [rbp+870h+var_8E0], rax
0x18012a326  mov     rax, [rbp+870h+var_888]
0x18012a32a  mov     [rbp+870h+var_8D8], rax
0x18012a32e  mov     rax, [rbp+870h+var_890]
0x18012a332  mov     [rbp+870h+var_8D0], rax
0x18012a336  mov     rax, [rbp+870h+var_898]
0x18012a33a  mov     [rbp+870h+var_8C8], rax
0x18012a33e  mov     rax, [rbp+870h+BackTrace]
0x18012a342  mov     [rbp+870h+var_8C0], rax
0x18012a346  call    cs:__imp_GetCurrentThreadId
0x18012a34d  nop     dword ptr [rax+rax+00h]
0x18012a352  mov     [rbp+870h+var_8E4], eax
0x18012a355  call    cs:__imp_GetCurrentProcessId
0x18012a35c  nop     dword ptr [rax+rax+00h]
0x18012a361  mov     r8d, eax
0x18012a364  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18012a369  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18012a36e  movzx   r9d, [rbp+870h+SystemTime.wMinute]
0x18012a373  movzx   ecx, [rbp+870h+SystemTime.wYear]
0x18012a377  mov     eax, 51EB851Fh
0x18012a37c  mul     ecx
0x18012a37e  shr     edx, 5
0x18012a381  imul    ecx, edx, 64h ; 'd'
0x18012a384  movzx   edx, [rbp+870h+SystemTime.wYear]
0x18012a388  sub     edx, ecx
0x18012a38a  mov     [rsp+9D0h+var_900], rbx
0x18012a392  mov     [rsp+9D0h+var_908], rdi
0x18012a39a  mov     [rsp+9D0h+var_910], rsi
0x18012a3a2  mov     [rsp+9D0h+var_918], r14
0x18012a3aa  mov     [rsp+9D0h+var_920], r15
0x18012a3b2  mov     [rsp+9D0h+var_928], r12
0x18012a3ba  mov     [rsp+9D0h+var_930], r13
0x18012a3c2  mov     rax, [rbp+870h+var_8E0]
0x18012a3c6  mov     [rsp+9D0h+var_938], rax
0x18012a3ce  mov     rax, [rbp+870h+var_8D8]
0x18012a3d2  mov     [rsp+9D0h+var_940], rax
0x18012a3da  mov     rax, [rbp+870h+var_8D0]
0x18012a3de  mov     [rsp+9D0h+var_948], rax
0x18012a3e6  mov     rax, [rbp+870h+var_8C8]
0x18012a3ea  mov     [rsp+9D0h+var_950], rax
0x18012a3f2  mov     rax, [rbp+870h+var_8C0]
0x18012a3f6  mov     [rsp+9D0h+var_958], rax
0x18012a3fb  mov     rax, [rbp+870h+var_8B8]
0x18012a3ff  mov     [rsp+9D0h+var_960], rax
0x18012a404  mov     eax, [rbp+870h+var_8E4]
0x18012a407  mov     dword ptr [rsp+9D0h+var_968], eax
0x18012a40b  mov     dword ptr [rsp+9D0h+var_970], r8d
0x18012a410  mov     eax, [rbp+870h+var_8E8]
0x18012a413  mov     [rsp+9D0h+var_978], eax
0x18012a417  mov     rax, [rbp+870h+var_8F0]
0x18012a41b  mov     [rsp+9D0h+var_980], rax
0x18012a420  mov     [rsp+9D0h+var_988], r10d
0x18012a425  mov     [rsp+9D0h+var_990], r11d
0x18012a42a  mov     [rsp+9D0h+var_998], r9d
0x18012a42f  movzx   eax, [rbp+870h+SystemTime.wHour]
0x18012a433  mov     [rsp+9D0h+var_9A0], eax
0x18012a437  movzx   eax, [rbp+870h+SystemTime.wDay]
0x18012a43b  mov     dword ptr [rsp+9D0h+var_9A8], eax
0x18012a43f  movzx   eax, [rbp+870h+SystemTime.wMonth]
0x18012a443  mov     [rsp+9D0h+var_9B0], eax
0x18012a447  mov     r9d, edx
0x18012a44a  lea     r8, a02u02u02u02u02_2; "%02u%02u%02u %02u%02u%02u.%03u [%s 0x%0"...
0x18012a451  lea     rdx, [rbp+870h+Buffer]
0x18012a455  mov     ecx, 800h
0x18012a45a  call    cs:__imp_sqlite3_snprintf
0x18012a461  nop     dword ptr [rax+rax+00h]
0x18012a466  jmp     loc_18012A59F
0x18012a46b  call    cs:__imp_GetCurrentThreadId
0x18012a472  nop     dword ptr [rax+rax+00h]
0x18012a477  mov     r15d, eax
0x18012a47a  call    cs:__imp_GetCurrentProcessId
0x18012a481  nop     dword ptr [rax+rax+00h]
0x18012a486  mov     r8d, eax
0x18012a489  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18012a48e  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18012a493  movzx   ebx, [rbp+870h+SystemTime.wMinute]
0x18012a497  movzx   edi, [rbp+870h+SystemTime.wHour]
0x18012a49b  movzx   esi, [rbp+870h+SystemTime.wDay]
0x18012a49f  movzx   r14d, [rbp+870h+SystemTime.wMonth]
0x18012a4a4  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x18012a4a9  mov     eax, 51EB851Fh
0x18012a4ae  mul     r9d
0x18012a4b1  shr     edx, 5
0x18012a4b4  imul    ecx, edx, 64h ; 'd'
0x18012a4b7  sub     r9d, ecx
0x18012a4ba  mov     [rsp+9D0h+var_970], r13
0x18012a4bf  mov     [rsp+9D0h+var_978], r15d
0x18012a4c4  mov     dword ptr [rsp+9D0h+var_980], r8d
0x18012a4c9  mov     [rsp+9D0h+var_988], r10d
0x18012a4ce  mov     [rsp+9D0h+var_990], r11d
0x18012a4d3  mov     [rsp+9D0h+var_998], ebx
0x18012a4d7  mov     [rsp+9D0h+var_9A0], edi
0x18012a4db  mov     dword ptr [rsp+9D0h+var_9A8], esi
0x18012a4df  mov     [rsp+9D0h+var_9B0], r14d
0x18012a4e4  lea     r8, a02u02u02u02u02; "%02u%02u%02u %02u%02u%02u.%03u [Trace] "...
0x18012a4eb  lea     rdx, [rbp+870h+Buffer]
0x18012a4ef  mov     ecx, 800h
0x18012a4f4  call    cs:__imp_sqlite3_snprintf
0x18012a4fb  nop     dword ptr [rax+rax+00h]
0x18012a500  jmp     loc_18012A59F
0x18012a505  call    cs:__imp_GetCurrentThreadId
0x18012a50c  nop     dword ptr [rax+rax+00h]
0x18012a511  mov     ebx, eax
0x18012a513  call    cs:__imp_GetCurrentProcessId
0x18012a51a  nop     dword ptr [rax+rax+00h]
0x18012a51f  mov     r8d, eax
0x18012a522  movzx   r10d, [rbp+870h+SystemTime.wMilliseconds]
0x18012a527  movzx   r11d, [rbp+870h+SystemTime.wSecond]
0x18012a52c  movzx   edi, [rbp+870h+SystemTime.wMinute]
0x18012a530  movzx   esi, [rbp+870h+SystemTime.wHour]
0x18012a534  movzx   r14d, [rbp+870h+SystemTime.wDay]
0x18012a539  movzx   r15d, [rbp+870h+SystemTime.wMonth]
0x18012a53e  movzx   r9d, [rbp+870h+SystemTime.wYear]
0x18012a543  mov     eax, 51EB851Fh
0x18012a548  mul     r9d
0x18012a54b  shr     edx, 5
0x18012a54e  imul    ecx, edx, 64h ; 'd'
0x18012a551  sub     r9d, ecx
0x18012a554  mov     [rsp+9D0h+var_968], r13
0x18012a559  mov     dword ptr [rsp+9D0h+var_970], ebx
0x18012a55d  mov     [rsp+9D0h+var_978], r8d
0x18012a562  mov     dword ptr [rsp+9D0h+var_980], r12d
0x18012a567  mov     [rsp+9D0h+var_988], r10d
0x18012a56c  mov     [rsp+9D0h+var_990], r11d
0x18012a571  mov     [rsp+9D0h+var_998], edi
0x18012a575  mov     [rsp+9D0h+var_9A0], esi
0x18012a579  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x18012a57e  mov     [rsp+9D0h+var_9B0], r15d
0x18012a583  lea     r8, a02u02u02u02u02_0; "%02u%02u%02u %02u%02u%02u.%03u [Profile"...
0x18012a58a  lea     rdx, [rbp+870h+Buffer]
0x18012a58e  mov     ecx, 800h
0x18012a593  call    cs:__imp_sqlite3_snprintf
0x18012a59a  nop     dword ptr [rax+rax+00h]
0x18012a59f  lea     rcx, [rbp+870h+var_8F0]
0x18012a5a3  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x18012a5a8  xor     ebx, ebx
0x18012a5aa  cmp     ebx, 64h ; 'd'
0x18012a5ad  jge     short loc_18012A5DE
0x18012a5af  test    ebx, ebx
0x18012a5b1  jle     short loc_18012A5C1
0x18012a5b3  xor     ecx, ecx; dwMilliseconds
0x18012a5b5  call    cs:__imp_Sleep
0x18012a5bc  nop     dword ptr [rax+rax+00h]
0x18012a5c1  lea     rcx, [rbp+870h+Buffer]; lpBuffer
0x18012a5c5  call    ?_WriteLogToFile@Logging@StateRepository@@YAJPEBD@Z; StateRepository::Logging::_WriteLogToFile(char const *)
0x18012a5ca  test    eax, eax
0x18012a5cc  jns     short loc_18012A5D2
0x18012a5ce  inc     ebx
0x18012a5d0  jmp     short loc_18012A5AA
0x18012a5d2  lea     rcx, [rbp+870h+var_8F0]
0x18012a5d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18012a5db  nop
0x18012a5dc  jmp     short loc_18012A5E8
0x18012a5de  lea     rcx, [rbp+870h+var_8F0]
0x18012a5e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18012a5e7  nop
0x18012a5e8  mov     rcx, [rbp+870h+var_40]
0x18012a5ef  xor     rcx, rsp; StackCookie
0x18012a5f2  call    __security_check_cookie
0x18012a5f7  mov     rbx, [rsp+9D0h+arg_0]
0x18012a5ff  add     rsp, 9A0h
  ... truncated ...
```
