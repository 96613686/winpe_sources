# CWmsWebService::ThreadProcCertExpiry(void)

- ea: `0x14004b218`
- end: `0x14004b79a`
- name: `?ThreadProcCertExpiry@CWmsWebService@@AEAAJXZ`
- size: `1410`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x14004d3d0`

## callees

- `0x140004730`
- `0x140004a04`
- `0x140047f10`
- `0x14004ac94`
- `0x14004b0f0`
- `0x14004b218`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14004b75f`
- `KERNEL32!CloseHandle` at `0x14004b772`
- `KERNEL32!CloseHandle` at `0x14004b75f`
- `KERNEL32!CloseHandle` at `0x14004b772`
- `KERNEL32!WaitForMultipleObjects` at `0x14004b475`
- `KERNEL32!WaitForMultipleObjects` at `0x14004b475`
- `KERNEL32!GetLastError` at `0x14004b287`
- `KERNEL32!GetLastError` at `0x14004b348`
- `KERNEL32!GetLastError` at `0x14004b50e`
- `KERNEL32!GetLastError` at `0x14004b585`
- `KERNEL32!GetLastError` at `0x14004b634`
- `KERNEL32!GetLastError` at `0x14004b6a5`
- `KERNEL32!GetLastError` at `0x14004b287`
- `KERNEL32!GetLastError` at `0x14004b348`
- `KERNEL32!GetLastError` at `0x14004b50e`
- `KERNEL32!GetLastError` at `0x14004b585`
- `KERNEL32!GetLastError` at `0x14004b634`
- `KERNEL32!GetLastError` at `0x14004b6a5`
- `KERNEL32!IsDebuggerPresent` at `0x14004b2e2`
- `KERNEL32!IsDebuggerPresent` at `0x14004b3a3`
- `KERNEL32!IsDebuggerPresent` at `0x14004b565`
- `KERNEL32!IsDebuggerPresent` at `0x14004b5dc`
- `KERNEL32!IsDebuggerPresent` at `0x14004b68b`
- `KERNEL32!IsDebuggerPresent` at `0x14004b6fc`
- `KERNEL32!IsDebuggerPresent` at `0x14004b2e2`
- `KERNEL32!IsDebuggerPresent` at `0x14004b3a3`
- `KERNEL32!IsDebuggerPresent` at `0x14004b565`
- `KERNEL32!IsDebuggerPresent` at `0x14004b5dc`
- `KERNEL32!IsDebuggerPresent` at `0x14004b68b`
- `KERNEL32!IsDebuggerPresent` at `0x14004b6fc`
- `KERNEL32!CancelWaitableTimer` at `0x14004b459`
- `KERNEL32!CancelWaitableTimer` at `0x14004b459`
- `KERNEL32!SetWaitableTimer` at `0x14004b409`
- `KERNEL32!SetWaitableTimer` at `0x14004b444`
- `KERNEL32!SetWaitableTimer` at `0x14004b409`
- `KERNEL32!SetWaitableTimer` at `0x14004b444`
- `KERNEL32!CreateWaitableTimerW` at `0x14004b271`
- `KERNEL32!CreateWaitableTimerW` at `0x14004b33a`
- `KERNEL32!CreateWaitableTimerW` at `0x14004b271`
- `KERNEL32!CreateWaitableTimerW` at `0x14004b33a`

## string_xrefs

- `0x14004b2b7`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b378`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b538`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b5af`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b65e`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b6cf`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004b252`: `CWmsWebService::ThreadProcCertExpiry - Start.\n`
- `0x14004b2aa`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b36b`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b531`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b5a8`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b657`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b6c8`: `CWmsWebService::ThreadProcCertExpiry`
- `0x14004b385`: `hWaitableTimerReplacementCert != 0`
- `0x14004b3ab`: `hWaitableTimerReplacementCert != 0`
- `0x14004b623`: `CWmsWebService::ThreadProcCertExpiry - Told to stop.\n`
- `0x14004b4be`: `CWmsWebService::ThreadProcCertExpiry - Current server certificate has expired!\n`
- `0x14004b491`: `CWmsWebService::ThreadProcCertExpiry - Time to generate a replacement cert!\n`
- `0x14004b745`: `CWmsWebService::ThreadProcCertExpiry - returning 0x%08X.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::ThreadProcCertExpiry(CWmsWebService *this)
{
  int v2; // esi
  char *WaitableTimerW; // r13
  signed int v4; // eax
  signed int ReplacementCert; // ebx
  unsigned int v6; // r12d
  bool v7; // zf
  const unsigned __int16 *v8; // rax
  __int64 v9; // r9
  signed int v10; // eax
  HANDLE v11; // r14
  DWORD v12; // ecx
  DWORD v13; // eax
  DWORD v14; // eax
  __int64 v15; // r8
  const unsigned __int16 *v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // r9
  signed int v20; // eax
  __int64 v21; // r8
  signed int v22; // eax
  signed int v23; // eax
  signed int LastError; // eax
  const unsigned __int16 *v26; // [rsp+30h] [rbp-39h]
  signed int v27; // [rsp+38h] [rbp-31h]
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp-29h] BYREF
  LARGE_INTEGER v29; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK v30; // [rsp+50h] [rbp-19h] BYREF
  HANDLE hTimer; // [rsp+58h] [rbp-11h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-9h] BYREF
  char *v33; // [rsp+70h] [rbp+7h]

  DueTime.QuadPart = 0;
  v29.QuadPart = 0;
  v33 = 0;
  *(_OWORD *)Handles = 0;
  DEBUGMSG(L"CWmsWebService::ThreadProcCertExpiry - Start.\n");
  v2 = 1;
  hTimer = CreateWaitableTimerW(0, 1, 0);
  if ( hTimer )
  {
    WaitableTimerW = (char *)CreateWaitableTimerW(0, 1, 0);
    if ( WaitableTimerW )
    {
      ReplacementCert = 0;
      v11 = hTimer;
      Handles[0] = *((HANDLE *)this + 39);
      Handles[1] = hTimer;
      v33 = WaitableTimerW;
      while ( 1 )
      {
        DueTime = *(LARGE_INTEGER *)(*(_QWORD *)(*((_QWORD *)this + 41) + 24LL) + 72LL);
        if ( !SetWaitableTimer(v11, &DueTime, 0, 0, 0, 0) )
        {
          LastError = GetLastError();
          ReplacementCert = LastError;
          if ( LastError > 0 )
            ReplacementCert = (unsigned __int16)LastError | 0x80070000;
          if ( ReplacementCert >= 0 )
            ReplacementCert = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            0x80Eu,
            L"CWmsWebService::ThreadProcCertExpiry",
            L"CBRAEx",
            L"fSuccess",
            ReplacementCert);
          if ( IsDebuggerPresent() )
          {
            v9 = 2062;
            goto LABEL_61;
          }
          v21 = 2062;
          goto LABEL_63;
        }
        if ( v2 )
        {
          v29 = *(LARGE_INTEGER *)((char *)this + 336);
          if ( !SetWaitableTimer(WaitableTimerW, &v29, 0, 0, 0, 0) )
          {
            v20 = GetLastError();
            ReplacementCert = v20;
            if ( v20 > 0 )
              ReplacementCert = (unsigned __int16)v20 | 0x80070000;
            if ( ReplacementCert >= 0 )
              ReplacementCert = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x81Bu,
              L"CWmsWebService::ThreadProcCertExpiry",
              L"CBRAEx",
              L"fSuccess",
              ReplacementCert);
            if ( IsDebuggerPresent() )
            {
              v9 = 2075;
LABEL_61:
              v27 = ReplacementCert;
              v26 = L"fSuccess";
              goto LABEL_9;
            }
            v21 = 2075;
            goto LABEL_63;
          }
          v12 = 3;
        }
        else
        {
          if ( !CancelWaitableTimer(WaitableTimerW) )
          {
            v23 = GetLastError();
            ReplacementCert = v23;
            if ( v23 > 0 )
              ReplacementCert = (unsigned __int16)v23 | 0x80070000;
            if ( ReplacementCert >= 0 )
              ReplacementCert = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x820u,
              L"CWmsWebService::ThreadProcCertExpiry",
              L"CBRAEx",
              L"fSuccess",
              ReplacementCert);
            if ( IsDebuggerPresent() )
            {
              v9 = 2080;
              goto LABEL_61;
            }
            v21 = 2080;
LABEL_63:
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              v21,
              L"CWmsWebService::ThreadProcCertExpiry",
              L"CBRAEx",
              L"fSuccess",
              ReplacementCert);
            goto LABEL_64;
          }
          v12 = 2;
        }
        v13 = WaitForMultipleObjects(v12, Handles, 0, 0xFFFFFFFF);
        if ( !v13 )
        {
          DEBUGMSG(L"CWmsWebService::ThreadProcCertExpiry - Told to stop.\n");
          goto LABEL_64;
        }
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 != 1 )
          {
            v22 = GetLastError();
            ReplacementCert = v22;
            if ( v22 > 0 )
              ReplacementCert = (unsigned __int16)v22 | 0x80070000;
            if ( ReplacementCert >= 0 )
              ReplacementCert = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x851u,
              L"CWmsWebService::ThreadProcCertExpiry",
              L"CBRAEx",
              L"0",
              ReplacementCert);
            if ( IsDebuggerPresent() )
            {
              v27 = ReplacementCert;
              v9 = 2129;
              v26 = L"0";
              goto LABEL_9;
            }
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              2129,
              L"CWmsWebService::ThreadProcCertExpiry",
              L"CBRAEx",
              L"0",
              ReplacementCert);
            goto LABEL_64;
          }
          DEBUGMSG(L"CWmsWebService::ThreadProcCertExpiry - Time to generate a replacement cert!\n");
          ReplacementCert = CWmsWebService::GenerateReplacementCert(this, *((const struct _CERT_CONTEXT **)this + 41));
          if ( ReplacementCert < 0 )
            goto LABEL_64;
          v2 = 0;
        }
        else
        {
          DEBUGMSG(L"CWmsWebService::ThreadProcCertExpiry - Current server certificate has expired!\n");
          CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v30, (CWmsWebService *)((char *)this + 24), v15, v16);
          ReplacementCert = CWmsWebService::StopWebService(this);
          if ( ReplacementCert < 0 || (ReplacementCert = CWmsWebService::StartWebService(this), ReplacementCert < 0) )
          {
            CAutoWriteLock::~CAutoWriteLock(&v30, v17, v18, v19);
            goto LABEL_64;
          }
          CAutoWriteLock::~CAutoWriteLock(&v30, v17, v18, v19);
          v2 = 1;
        }
      }
    }
    v10 = GetLastError();
    ReplacementCert = v10;
    if ( v10 > 0 )
      ReplacementCert = (unsigned __int16)v10 | 0x80070000;
    v6 = 2040;
    if ( ReplacementCert >= 0 )
      ReplacementCert = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x7F8u,
      L"CWmsWebService::ThreadProcCertExpiry",
      L"CBRAEx",
      L"hWaitableTimerReplacementCert != 0",
      ReplacementCert);
    v7 = !IsDebuggerPresent();
    v8 = L"hWaitableTimerReplacementCert != 0";
  }
  else
  {
    WaitableTimerW = 0;
    v4 = GetLastError();
    ReplacementCert = v4;
    if ( v4 > 0 )
      ReplacementCert = (unsigned __int16)v4 | 0x80070000;
    v6 = 2037;
    if ( ReplacementCert >= 0 )
      ReplacementCert = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x7F5u,
      L"CWmsWebService::ThreadProcCertExpiry",
      L"CBRAEx",
      L"hWaitableTimerCertExpiry != 0",
      ReplacementCert);
    v7 = !IsDebuggerPresent();
    v8 = L"hWaitableTimerCertExpiry != 0";
  }
  if ( v7 )
  {
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v6,
      L"CWmsWebService::ThreadProcCertExpiry",
      L"CBRAEx",
      v8,
      ReplacementCert);
  }
  else
  {
    v27 = ReplacementCert;
    v9 = v6;
    v26 = v8;
LABEL_9:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v9,
      L"CWmsWebService::ThreadProcCertExpiry",
      L"CBRAEx",
      v26,
      v27);
  }
LABEL_64:
  DEBUGMSG(L"CWmsWebService::ThreadProcCertExpiry - returning 0x%08X.\n", (unsigned int)ReplacementCert);
  if ( (char *)hTimer - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hTimer);
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  return (unsigned int)ReplacementCert;
}

```

## disassembly

```asm
0x14004b218  push    rbp
0x14004b21a  push    rbx
0x14004b21b  push    rsi
0x14004b21c  push    rdi
0x14004b21d  push    r12
0x14004b21f  push    r13
0x14004b221  push    r14
0x14004b223  push    r15
0x14004b225  lea     rbp, [rsp-1Fh]
0x14004b22a  sub     rsp, 88h
0x14004b231  mov     rax, cs:__security_cookie
0x14004b238  xor     rax, rsp
0x14004b23b  mov     [rbp+57h+var_48], rax
0x14004b23f  mov     rdi, rcx
0x14004b242  xor     r15d, r15d
0x14004b245  xorps   xmm0, xmm0
0x14004b248  mov     qword ptr [rbp+57h+DueTime], r15
0x14004b24c  xor     eax, eax
0x14004b24e  mov     qword ptr [rbp+57h+var_78], r15
0x14004b252  lea     rcx, aCwmswebservice_74; "CWmsWebService::ThreadProcCertExpiry - "...
0x14004b259  mov     [rbp+57h+var_50], rax
0x14004b25d  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x14004b261  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004b266  lea     esi, [r15+1]
0x14004b26a  xor     r8d, r8d; lpTimerName
0x14004b26d  mov     edx, esi; bManualReset
0x14004b26f  xor     ecx, ecx; lpTimerAttributes
0x14004b271  call    cs:__imp_CreateWaitableTimerW
0x14004b277  mov     [rbp+57h+hTimer], rax
0x14004b27b  test    rax, rax
0x14004b27e  jnz     loc_14004B333
0x14004b284  mov     r13d, r15d
0x14004b287  call    cs:__imp_GetLastError
0x14004b28d  mov     ebx, eax
0x14004b28f  test    eax, eax
0x14004b291  jle     short loc_14004B29C
0x14004b293  movzx   ebx, ax
0x14004b296  or      ebx, 80070000h
0x14004b29c  mov     eax, 80004005h
0x14004b2a1  lea     r14, aCbraex; "CBRAEx"
0x14004b2a8  test    ebx, ebx
0x14004b2aa  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b2b1  mov     r12d, 7F5h
0x14004b2b7  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b2be  cmovns  ebx, eax
0x14004b2c1  mov     r9, r14; unsigned __int16 *
0x14004b2c4  lea     rax, aHwaitabletimer_0; "hWaitableTimerCertExpiry != 0"
0x14004b2cb  mov     [rsp+0C0h+fResume], ebx; int
0x14004b2cf  mov     r8, rsi; unsigned __int16 *
0x14004b2d2  mov     [rsp+0C0h+lpArgToCompletionRoutine], rax; unsigned __int16 *
0x14004b2d7  mov     edx, r12d; unsigned int
0x14004b2da  mov     rcx, rdi; unsigned __int16 *
0x14004b2dd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b2e2  call    cs:__imp_IsDebuggerPresent
0x14004b2e8  test    eax, eax
0x14004b2ea  lea     rax, aHwaitabletimer_0; "hWaitableTimerCertExpiry != 0"
0x14004b2f1  jz      short loc_14004B322
0x14004b2f3  mov     [rsp+0C0h+var_88], ebx
0x14004b2f7  mov     r9d, r12d
0x14004b2fa  mov     [rsp+0C0h+var_90], rax
0x14004b2ff  mov     ecx, 2; unsigned __int8
0x14004b304  mov     qword ptr [rsp+0C0h+fResume], r14
0x14004b309  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004b310  mov     r8, rdi
0x14004b313  mov     [rsp+0C0h+lpArgToCompletionRoutine], rsi
0x14004b318  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004b31d  jmp     loc_14004B743
0x14004b322  mov     dword ptr [rsp+0C0h+var_90], ebx
0x14004b326  mov     r8d, r12d
0x14004b329  mov     qword ptr [rsp+0C0h+fResume], rax
0x14004b32e  jmp     loc_14004B72C
0x14004b333  xor     r8d, r8d; lpTimerName
0x14004b336  mov     edx, esi; bManualReset
0x14004b338  xor     ecx, ecx; lpTimerAttributes
0x14004b33a  call    cs:__imp_CreateWaitableTimerW
0x14004b340  mov     r13, rax
0x14004b343  test    rax, rax
0x14004b346  jnz     short loc_14004B3B7
0x14004b348  call    cs:__imp_GetLastError
0x14004b34e  mov     ebx, eax
0x14004b350  test    eax, eax
0x14004b352  jle     short loc_14004B35D
0x14004b354  movzx   ebx, ax
0x14004b357  or      ebx, 80070000h
0x14004b35d  mov     eax, 80004005h
0x14004b362  lea     r14, aCbraex; "CBRAEx"
0x14004b369  test    ebx, ebx
0x14004b36b  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b372  mov     r12d, 7F8h
0x14004b378  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b37f  cmovns  ebx, eax
0x14004b382  mov     r9, r14; unsigned __int16 *
0x14004b385  lea     rax, aHwaitabletimer; "hWaitableTimerReplacementCert != 0"
0x14004b38c  mov     [rsp+0C0h+fResume], ebx; int
0x14004b390  mov     r8, rsi; unsigned __int16 *
0x14004b393  mov     [rsp+0C0h+lpArgToCompletionRoutine], rax; unsigned __int16 *
0x14004b398  mov     edx, r12d; unsigned int
0x14004b39b  mov     rcx, rdi; unsigned __int16 *
0x14004b39e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b3a3  call    cs:__imp_IsDebuggerPresent
0x14004b3a9  test    eax, eax
0x14004b3ab  lea     rax, aHwaitabletimer; "hWaitableTimerReplacementCert != 0"
0x14004b3b2  jmp     loc_14004B2F1
0x14004b3b7  mov     rax, [rdi+138h]
0x14004b3be  mov     ebx, r15d
0x14004b3c1  mov     r14, [rbp+57h+hTimer]
0x14004b3c5  mov     r12d, 2
0x14004b3cb  mov     [rbp+57h+Handles], rax
0x14004b3cf  mov     [rbp+57h+Handles+8], r14
0x14004b3d3  mov     [rbp+57h+var_50], r13
0x14004b3d7  mov     rdx, [rdi+148h]
0x14004b3de  xor     r9d, r9d; pfnCompletionRoutine
0x14004b3e1  mov     [rsp+0C0h+fResume], r15d; fResume
0x14004b3e6  xor     r8d, r8d; lPeriod
0x14004b3e9  mov     [rsp+0C0h+lpArgToCompletionRoutine], r15; lpArgToCompletionRoutine
0x14004b3ee  mov     rax, [rdx+18h]
0x14004b3f2  mov     ecx, [rax+4Ch]
0x14004b3f5  mov     dword ptr [rbp+57h+DueTime+4], ecx
0x14004b3f8  mov     rax, [rdx+18h]
0x14004b3fc  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x14004b400  mov     ecx, [rax+48h]
0x14004b403  mov     dword ptr [rbp+57h+DueTime], ecx
0x14004b406  mov     rcx, r14; hTimer
0x14004b409  call    cs:__imp_SetWaitableTimer
0x14004b40f  test    eax, eax
0x14004b411  jz      loc_14004B6A5
0x14004b417  mov     rcx, r13; hTimer
0x14004b41a  test    esi, esi
0x14004b41c  jz      short loc_14004B459
0x14004b41e  mov     eax, [rdi+154h]
0x14004b424  lea     rdx, [rbp+57h+var_78]; lpDueTime
0x14004b428  mov     dword ptr [rbp+57h+var_78+4], eax
0x14004b42b  xor     r9d, r9d; pfnCompletionRoutine
0x14004b42e  mov     eax, [rdi+150h]
0x14004b434  xor     r8d, r8d; lPeriod
0x14004b437  mov     [rsp+0C0h+fResume], r15d; fResume
0x14004b43c  mov     dword ptr [rbp+57h+var_78], eax
0x14004b43f  mov     [rsp+0C0h+lpArgToCompletionRoutine], r15; lpArgToCompletionRoutine
0x14004b444  call    cs:__imp_SetWaitableTimer
0x14004b44a  test    eax, eax
0x14004b44c  jz      loc_14004B50E
0x14004b452  mov     ecx, 3
0x14004b457  jmp     short loc_14004B46A
0x14004b459  call    cs:__imp_CancelWaitableTimer
0x14004b45f  test    eax, eax
0x14004b461  jz      loc_14004B634
0x14004b467  mov     ecx, r12d; nCount
0x14004b46a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14004b46e  lea     rdx, [rbp+57h+Handles]; lpHandles
0x14004b472  xor     r8d, r8d; bWaitAll
0x14004b475  call    cs:__imp_WaitForMultipleObjects
0x14004b47b  test    eax, eax
0x14004b47d  jz      loc_14004B623
0x14004b483  sub     eax, 1
0x14004b486  jz      short loc_14004B4BE
0x14004b488  cmp     eax, 1
0x14004b48b  jnz     loc_14004B585
0x14004b491  lea     rcx, aCwmswebservice_36; "CWmsWebService::ThreadProcCertExpiry - "...
0x14004b498  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004b49d  mov     rdx, [rdi+148h]; struct _CERT_CONTEXT *
0x14004b4a4  mov     rcx, rdi; this
0x14004b4a7  call    ?GenerateReplacementCert@CWmsWebService@@AEAAJPEBU_CERT_CONTEXT@@@Z; CWmsWebService::GenerateReplacementCert(_CERT_CONTEXT const *)
0x14004b4ac  mov     ebx, eax
0x14004b4ae  test    eax, eax
0x14004b4b0  js      loc_14004B743
0x14004b4b6  mov     esi, r15d
0x14004b4b9  jmp     loc_14004B3D7
0x14004b4be  lea     rcx, aCwmswebservice_51; "CWmsWebService::ThreadProcCertExpiry - "...
0x14004b4c5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004b4ca  lea     rdx, [rdi+18h]; struct CSharedReaderWriterLock *
0x14004b4ce  lea     rcx, [rbp+57h+var_70]; this
0x14004b4d2  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x14004b4d7  mov     rcx, rdi; this
0x14004b4da  call    ?StopWebService@CWmsWebService@@QEAAJXZ; CWmsWebService::StopWebService(void)
0x14004b4df  mov     ebx, eax
0x14004b4e1  test    eax, eax
0x14004b4e3  js      loc_14004B615
0x14004b4e9  mov     rcx, rdi; this
0x14004b4ec  call    ?StartWebService@CWmsWebService@@AEAAJXZ; CWmsWebService::StartWebService(void)
0x14004b4f1  lea     rcx, [rbp+57h+var_70]; this
0x14004b4f5  mov     ebx, eax
0x14004b4f7  test    eax, eax
0x14004b4f9  js      loc_14004B619
0x14004b4ff  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14004b504  mov     esi, 1
0x14004b509  jmp     loc_14004B3D7
0x14004b50e  call    cs:__imp_GetLastError
0x14004b514  mov     ebx, eax
0x14004b516  test    eax, eax
0x14004b518  jle     short loc_14004B523
0x14004b51a  movzx   ebx, ax
0x14004b51d  or      ebx, 80070000h
0x14004b523  mov     eax, 80004005h
0x14004b528  lea     r14, aCbraex; "CBRAEx"
0x14004b52f  test    ebx, ebx
0x14004b531  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b538  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b53f  mov     r9, r14; unsigned __int16 *
0x14004b542  cmovns  ebx, eax
0x14004b545  lea     r15, aFsuccess; "fSuccess"
0x14004b54c  mov     [rsp+0C0h+fResume], ebx; int
0x14004b550  mov     r8, rsi; unsigned __int16 *
0x14004b553  mov     edx, 81Bh; unsigned int
0x14004b558  mov     [rsp+0C0h+lpArgToCompletionRoutine], r15; unsigned __int16 *
0x14004b55d  mov     rcx, rdi; unsigned __int16 *
0x14004b560  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b565  call    cs:__imp_IsDebuggerPresent
0x14004b56b  test    eax, eax
0x14004b56d  jz      short loc_14004B57A
0x14004b56f  mov     r9d, 81Bh
0x14004b575  jmp     loc_14004B70C
0x14004b57a  mov     r8d, 81Bh
0x14004b580  jmp     loc_14004B723
0x14004b585  call    cs:__imp_GetLastError
0x14004b58b  mov     ebx, eax
0x14004b58d  test    eax, eax
0x14004b58f  jle     short loc_14004B59A
0x14004b591  movzx   ebx, ax
0x14004b594  or      ebx, 80070000h
0x14004b59a  mov     eax, 80004005h
0x14004b59f  lea     r14, aCbraex; "CBRAEx"
0x14004b5a6  test    ebx, ebx
0x14004b5a8  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b5af  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b5b6  mov     r9, r14; unsigned __int16 *
0x14004b5b9  cmovns  ebx, eax
0x14004b5bc  mov     r8, rsi; unsigned __int16 *
0x14004b5bf  lea     rax, a0; "0"
0x14004b5c6  mov     [rsp+0C0h+fResume], ebx; int
0x14004b5ca  mov     edx, 851h; unsigned int
0x14004b5cf  mov     [rsp+0C0h+lpArgToCompletionRoutine], rax; unsigned __int16 *
0x14004b5d4  mov     rcx, rdi; unsigned __int16 *
0x14004b5d7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b5dc  call    cs:__imp_IsDebuggerPresent
0x14004b5e2  test    eax, eax
0x14004b5e4  lea     rax, a0; "0"
0x14004b5eb  jz      short loc_14004B601
0x14004b5ed  mov     [rsp+0C0h+var_88], ebx
0x14004b5f1  mov     r9d, 851h
0x14004b5f7  mov     [rsp+0C0h+var_90], rax
0x14004b5fc  jmp     loc_14004B715
0x14004b601  mov     dword ptr [rsp+0C0h+var_90], ebx
0x14004b605  mov     r8d, 851h
0x14004b60b  mov     qword ptr [rsp+0C0h+fResume], rax
0x14004b610  jmp     loc_14004B72C
0x14004b615  lea     rcx, [rbp+57h+var_70]; this
0x14004b619  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14004b61e  jmp     loc_14004B743
0x14004b623  lea     rcx, aCwmswebservice_26; "CWmsWebService::ThreadProcCertExpiry - "...
0x14004b62a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004b62f  jmp     loc_14004B743
0x14004b634  call    cs:__imp_GetLastError
0x14004b63a  mov     ebx, eax
0x14004b63c  test    eax, eax
0x14004b63e  jle     short loc_14004B649
0x14004b640  movzx   ebx, ax
0x14004b643  or      ebx, 80070000h
0x14004b649  mov     eax, 80004005h
0x14004b64e  lea     r14, aCbraex; "CBRAEx"
0x14004b655  test    ebx, ebx
0x14004b657  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b65e  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b665  mov     r9, r14; unsigned __int16 *
0x14004b668  cmovns  ebx, eax
0x14004b66b  lea     r15, aFsuccess; "fSuccess"
0x14004b672  mov     [rsp+0C0h+fResume], ebx; int
0x14004b676  mov     r8, rsi; unsigned __int16 *
0x14004b679  mov     edx, 820h; unsigned int
0x14004b67e  mov     [rsp+0C0h+lpArgToCompletionRoutine], r15; unsigned __int16 *
0x14004b683  mov     rcx, rdi; unsigned __int16 *
0x14004b686  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b68b  call    cs:__imp_IsDebuggerPresent
0x14004b691  test    eax, eax
0x14004b693  jz      short loc_14004B69D
0x14004b695  mov     r9d, 820h
0x14004b69b  jmp     short loc_14004B70C
0x14004b69d  mov     r8d, 820h
0x14004b6a3  jmp     short loc_14004B723
0x14004b6a5  call    cs:__imp_GetLastError
0x14004b6ab  mov     ebx, eax
0x14004b6ad  test    eax, eax
0x14004b6af  jle     short loc_14004B6BA
0x14004b6b1  movzx   ebx, ax
0x14004b6b4  or      ebx, 80070000h
0x14004b6ba  mov     eax, 80004005h
0x14004b6bf  lea     r14, aCbraex; "CBRAEx"
0x14004b6c6  test    ebx, ebx
0x14004b6c8  lea     rsi, aCwmswebservice_20; "CWmsWebService::ThreadProcCertExpiry"
0x14004b6cf  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004b6d6  mov     r9, r14; unsigned __int16 *
0x14004b6d9  cmovns  ebx, eax
0x14004b6dc  lea     r15, aFsuccess; "fSuccess"
0x14004b6e3  mov     [rsp+0C0h+fResume], ebx; int
0x14004b6e7  mov     r8, rsi; unsigned __int16 *
0x14004b6ea  mov     edx, 80Eh; unsigned int
0x14004b6ef  mov     [rsp+0C0h+lpArgToCompletionRoutine], r15; unsigned __int16 *
0x14004b6f4  mov     rcx, rdi; unsigned __int16 *
0x14004b6f7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004b6fc  call    cs:__imp_IsDebuggerPresent
0x14004b702  test    eax, eax
  ... truncated ...
```
