# WaitForServiceStatusChange(ushort const *,ulong,void *,EServiceStatusChangeWaitResult *)

- ea: `0x1400697ec`
- end: `0x140069c2f`
- name: `?WaitForServiceStatusChange@@YAJPEBGKPEAXPEAW4EServiceStatusChangeWaitResult@@@Z`
- size: `1091`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, void *, enum EServiceStatusChangeWaitResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140065368`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400697ec`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140069864`
- `ADVAPI32!OpenSCManagerW` at `0x140069864`
- `ADVAPI32!OpenServiceW` at `0x140069939`
- `ADVAPI32!OpenServiceW` at `0x140069939`
- `ADVAPI32!CloseServiceHandle` at `0x140069be9`
- `ADVAPI32!CloseServiceHandle` at `0x140069bf2`
- `ADVAPI32!CloseServiceHandle` at `0x140069be9`
- `ADVAPI32!CloseServiceHandle` at `0x140069bf2`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140069a13`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140069a13`
- `KERNEL32!SleepEx` at `0x140069a50`
- `KERNEL32!SleepEx` at `0x140069a50`
- `KERNEL32!WaitForSingleObjectEx` at `0x140069a42`
- `KERNEL32!WaitForSingleObjectEx` at `0x140069a42`
- `KERNEL32!GetLastError` at `0x140069876`
- `KERNEL32!GetLastError` at `0x140069942`
- `KERNEL32!GetLastError` at `0x140069876`
- `KERNEL32!GetLastError` at `0x140069942`
- `KERNEL32!IsDebuggerPresent` at `0x1400698d1`
- `KERNEL32!IsDebuggerPresent` at `0x14006999c`
- `KERNEL32!IsDebuggerPresent` at `0x140069af8`
- `KERNEL32!IsDebuggerPresent` at `0x140069b86`
- `KERNEL32!IsDebuggerPresent` at `0x1400698d1`
- `KERNEL32!IsDebuggerPresent` at `0x14006999c`
- `KERNEL32!IsDebuggerPresent` at `0x140069af8`
- `KERNEL32!IsDebuggerPresent` at `0x140069b86`

## string_xrefs

- `0x140069982`: `hService != 0`
- `0x14006983d`: `ServicesActive`
- `0x1400698a6`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069978`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069ad0`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069b6e`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400698b0`: `hServiceManager != 0`
- `0x140069899`: `WaitForServiceStatusChange`
- `0x14006996b`: `WaitForServiceStatusChange`
- `0x140069abf`: `WaitForServiceStatusChange`
- `0x140069b61`: `WaitForServiceStatusChange`
- `0x140069a23`: `WaitForServiceStatusChange - waiting for status change\n`
- `0x140069a98`: `WaitForServiceStatusChange - APC received\n`
- `0x140069a6b`: `WaitForServiceStatusChange - some other APC was received\n`
- `0x140069aae`: `WaitForServiceStatusChange - dwRet = %u\n`
- `0x140069bfa`: `WaitForServiceStatusChange - Exiting, hr = 0x%X\n`

## pseudocode

```c
__int64 __fastcall WaitForServiceStatusChange(
        LPCWSTR lpServiceName,
        __int64 a2,
        char *a3,
        enum EServiceStatusChangeWaitResult *a4)
{
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r12
  signed int v9; // eax
  unsigned int v10; // ebx
  SC_HANDLE v11; // r15
  signed int LastError; // eax
  signed int v13; // eax
  DWORD v14; // eax
  _DWORD v16[4]; // [rsp+40h] [rbp-49h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-39h] BYREF

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v16[0] = 0;
  pNotifyBuffer.pContext = v16;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NotifyServiceStatusChangeCallback;
  pNotifyBuffer.dwVersion = 2;
  v7 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v8 = v7;
  if ( v7 )
  {
    v11 = OpenServiceW(v7, lpServiceName, 0x80000000);
    LastError = GetLastError();
    v10 = LastError;
    if ( v11 )
    {
      while ( 1 )
      {
        v13 = NotifyServiceStatusChangeW(v11, 8u, &pNotifyBuffer);
        v10 = v13;
        if ( v13 )
          break;
        DEBUGMSG(L"WaitForServiceStatusChange - waiting for status change\n");
        if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          v14 = SleepEx(0xFFFFFFFF, 1);
        else
          v14 = WaitForSingleObjectEx(a3, 0xFFFFFFFF, 1);
        if ( !v14 )
        {
          v10 = -2147467260;
          goto LABEL_33;
        }
        if ( v14 != 192 )
        {
          DEBUGMSG(L"WaitForServiceStatusChange - dwRet = %u\n", v14);
          v10 = -2147418113;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            0xA73u,
            L"WaitForServiceStatusChange",
            L"CHRA",
            L"((HRESULT)0x8000FFFFL)",
            -2147418113);
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
              2675,
              L"WaitForServiceStatusChange",
              L"CHRA",
              L"((HRESULT)0x8000FFFFL)",
              -2147418113);
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
              2675,
              L"WaitForServiceStatusChange",
              L"CHRA",
              L"((HRESULT)0x8000FFFFL)",
              -2147418113);
          goto LABEL_33;
        }
        if ( v16[0] )
        {
          v10 = 0;
          DEBUGMSG(L"WaitForServiceStatusChange - APC received\n");
          *(_DWORD *)a4 = 1;
          goto LABEL_33;
        }
        DEBUGMSG(L"WaitForServiceStatusChange - some other APC was received\n");
        pNotifyBuffer.dwVersion = 2;
        pNotifyBuffer.pContext = v16;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NotifyServiceStatusChangeCallback;
      }
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA4Bu,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"dwRet == 0L",
        v10);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2635,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"dwRet == 0L",
          v10);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2635,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"dwRet == 0L",
          v10);
LABEL_33:
      CloseServiceHandle(v11);
    }
    else
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA45u,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hService != 0",
        v10);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2629,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"hService != 0",
          v10);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2629,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"hService != 0",
          v10);
    }
    CloseServiceHandle(v8);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
      v10 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xA40u,
      L"WaitForServiceStatusChange",
      L"CBRAEx",
      L"hServiceManager != 0",
      v10);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        2624,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hServiceManager != 0",
        v10);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        2624,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hServiceManager != 0",
        v10);
  }
  DEBUGMSG(L"WaitForServiceStatusChange - Exiting, hr = 0x%X\n", v10);
  return v10;
}

```

## disassembly

```asm
0x1400697ec  mov     [rsp-8+arg_8], rbx
0x1400697f1  push    rbp
0x1400697f2  push    rsi
0x1400697f3  push    rdi
0x1400697f4  push    r12
0x1400697f6  push    r13
0x1400697f8  push    r14
0x1400697fa  push    r15
0x1400697fc  lea     rbp, [rsp-27h]
0x140069801  sub     rsp, 0B0h
0x140069808  mov     rax, cs:__security_cookie
0x14006980f  xor     rax, rsp
0x140069812  mov     [rbp+57h+var_40], rax
0x140069816  xor     edx, edx; Val
0x140069818  mov     rdi, r8
0x14006981b  mov     rbx, rcx
0x14006981e  mov     rsi, r9
0x140069821  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x140069825  lea     r8d, [rdx+50h]; Size
0x140069829  call    memset_0
0x14006982e  lea     rax, [rbp+57h+var_A0]
0x140069832  mov     [rbp+57h+var_A0], 0
0x140069839  mov     [rbp+57h+pNotifyBuffer.pContext], rax
0x14006983d  lea     rdx, DatabaseName; "ServicesActive"
0x140069844  lea     rax, ?NotifyServiceStatusChangeCallback@@YAXPEAX@Z; NotifyServiceStatusChangeCallback(void *)
0x14006984b  mov     r14d, 80000000h
0x140069851  mov     r13d, 2
0x140069857  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x14006985b  mov     r8d, r14d; dwDesiredAccess
0x14006985e  mov     [rbp+57h+pNotifyBuffer.dwVersion], r13d
0x140069862  xor     ecx, ecx; lpMachineName
0x140069864  call    cs:__imp_OpenSCManagerW
0x14006986a  mov     r12, rax
0x14006986d  test    rax, rax
0x140069870  jnz     loc_140069930
0x140069876  call    cs:__imp_GetLastError
0x14006987c  mov     ebx, eax
0x14006987e  test    eax, eax
0x140069880  jle     short loc_14006988B
0x140069882  movzx   ebx, ax
0x140069885  or      ebx, 80070000h
0x14006988b  mov     eax, 80004005h
0x140069890  lea     r14, aCbraex; "CBRAEx"
0x140069897  test    ebx, ebx
0x140069899  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x1400698a0  mov     r15d, 0A40h
0x1400698a6  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400698ad  cmovns  ebx, eax
0x1400698b0  lea     r12, aHservicemanage; "hServiceManager != 0"
0x1400698b7  mov     [rsp+0E0h+var_B8], ebx; int
0x1400698bb  mov     r9, r14; unsigned __int16 *
0x1400698be  mov     r8, rsi; unsigned __int16 *
0x1400698c1  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x1400698c6  mov     edx, r15d; unsigned int
0x1400698c9  mov     rcx, rdi; unsigned __int16 *
0x1400698cc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400698d1  call    cs:__imp_IsDebuggerPresent
0x1400698d7  test    eax, eax
0x1400698d9  jz      short loc_140069908
0x1400698db  mov     [rsp+0E0h+var_A8], ebx
0x1400698df  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400698e6  mov     [rsp+0E0h+var_B0], r12
0x1400698eb  mov     r9d, r15d
0x1400698ee  mov     qword ptr [rsp+0E0h+var_B8], r14
0x1400698f3  mov     r8, rdi
0x1400698f6  mov     ecx, r13d; unsigned __int8
0x1400698f9  mov     [rsp+0E0h+var_C0], rsi
0x1400698fe  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140069903  jmp     loc_140069BF8
0x140069908  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14006990c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140069913  mov     qword ptr [rsp+0E0h+var_B8], r12
0x140069918  mov     r9, rsi
0x14006991b  mov     r8d, r15d
0x14006991e  mov     [rsp+0E0h+var_C0], r14
0x140069923  mov     rdx, rdi
0x140069926  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006992b  jmp     loc_140069BF8
0x140069930  mov     r8d, r14d; dwDesiredAccess
0x140069933  mov     rdx, rbx; lpServiceName
0x140069936  mov     rcx, r12; hSCManager
0x140069939  call    cs:__imp_OpenServiceW
0x14006993f  mov     r15, rax
0x140069942  call    cs:__imp_GetLastError
0x140069948  mov     ebx, eax
0x14006994a  test    r15, r15
0x14006994d  jnz     loc_1400699FD
0x140069953  test    eax, eax
0x140069955  jle     short loc_140069960
0x140069957  movzx   ebx, ax
0x14006995a  or      ebx, 80070000h
0x140069960  lea     r14, aCbraex; "CBRAEx"
0x140069967  mov     [rsp+0E0h+var_B8], ebx; int
0x14006996b  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140069972  mov     r15d, 0A45h
0x140069978  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006997f  mov     r9, r14; unsigned __int16 *
0x140069982  lea     r13, aHservice0; "hService != 0"
0x140069989  mov     r8, rsi; unsigned __int16 *
0x14006998c  mov     edx, r15d; unsigned int
0x14006998f  mov     [rsp+0E0h+var_C0], r13; unsigned __int16 *
0x140069994  mov     rcx, rdi; unsigned __int16 *
0x140069997  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006999c  call    cs:__imp_IsDebuggerPresent
0x1400699a2  test    eax, eax
0x1400699a4  jz      short loc_1400699D5
0x1400699a6  mov     [rsp+0E0h+var_A8], ebx
0x1400699aa  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400699b1  mov     [rsp+0E0h+var_B0], r13
0x1400699b6  mov     r9d, r15d
0x1400699b9  mov     qword ptr [rsp+0E0h+var_B8], r14
0x1400699be  mov     r8, rdi
0x1400699c1  mov     ecx, 2; unsigned __int8
0x1400699c6  mov     [rsp+0E0h+var_C0], rsi
0x1400699cb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400699d0  jmp     loc_140069BEF
0x1400699d5  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x1400699d9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400699e0  mov     qword ptr [rsp+0E0h+var_B8], r13
0x1400699e5  mov     r9, rsi
0x1400699e8  mov     r8d, r15d
0x1400699eb  mov     [rsp+0E0h+var_C0], r14
0x1400699f0  mov     rdx, rdi
0x1400699f3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400699f8  jmp     loc_140069BEF
0x1400699fd  mov     r14d, 1
0x140069a03  or      r13d, 0FFFFFFFFh
0x140069a07  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x140069a0b  mov     edx, 8; dwNotifyMask
0x140069a10  mov     rcx, r15; hService
0x140069a13  call    cs:__imp_NotifyServiceStatusChangeW
0x140069a19  mov     ebx, eax
0x140069a1b  test    eax, eax
0x140069a1d  jnz     loc_140069B3F
0x140069a23  lea     rcx, aWaitforservice_2; "WaitForServiceStatusChange - waiting fo"...
0x140069a2a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069a2f  lea     rax, [rdi-1]
0x140069a33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140069a37  ja      short loc_140069A4A
0x140069a39  mov     r8d, r14d; bAlertable
0x140069a3c  mov     edx, r13d; dwMilliseconds
0x140069a3f  mov     rcx, rdi; hHandle
0x140069a42  call    cs:__imp_WaitForSingleObjectEx
0x140069a48  jmp     short loc_140069A56
0x140069a4a  mov     edx, r14d; bAlertable
0x140069a4d  mov     ecx, r13d; dwMilliseconds
0x140069a50  call    cs:__imp_SleepEx
0x140069a56  test    eax, eax
0x140069a58  jz      loc_140069B35
0x140069a5e  cmp     eax, 0C0h
0x140069a63  jnz     short loc_140069AAC
0x140069a65  cmp     [rbp+57h+var_A0], 0
0x140069a69  jnz     short loc_140069A96
0x140069a6b  lea     rcx, aWaitforservice_6; "WaitForServiceStatusChange - some other"...
0x140069a72  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069a77  lea     rax, [rbp+57h+var_A0]
0x140069a7b  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x140069a82  mov     [rbp+57h+pNotifyBuffer.pContext], rax
0x140069a86  lea     rax, ?NotifyServiceStatusChangeCallback@@YAXPEAX@Z; NotifyServiceStatusChangeCallback(void *)
0x140069a8d  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x140069a91  jmp     loc_140069A07
0x140069a96  xor     ebx, ebx
0x140069a98  lea     rcx, aWaitforservice_4; "WaitForServiceStatusChange - APC receiv"...
0x140069a9f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069aa4  mov     [rsi], r14d
0x140069aa7  jmp     loc_140069BE6
0x140069aac  mov     edx, eax
0x140069aae  lea     rcx, aWaitforservice_3; "WaitForServiceStatusChange - dwRet = %u"...
0x140069ab5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069aba  mov     ebx, 8000FFFFh
0x140069abf  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140069ac6  mov     r14d, 0A73h
0x140069acc  mov     [rsp+0E0h+var_B8], ebx; int
0x140069ad0  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069ad7  mov     r8, rsi; unsigned __int16 *
0x140069ada  lea     r13, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x140069ae1  mov     edx, r14d; unsigned int
0x140069ae4  mov     rcx, rdi; unsigned __int16 *
0x140069ae7  mov     [rsp+0E0h+var_C0], r13; unsigned __int16 *
0x140069aec  lea     r9, aChra; "CHRA"
0x140069af3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069af8  call    cs:__imp_IsDebuggerPresent
0x140069afe  test    eax, eax
0x140069b00  lea     rax, aChra; "CHRA"
0x140069b07  jz      short loc_140069B1F
0x140069b09  mov     [rsp+0E0h+var_A8], ebx
0x140069b0d  mov     r9d, r14d
0x140069b10  mov     [rsp+0E0h+var_B0], r13
0x140069b15  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140069b1a  jmp     loc_140069BA8
0x140069b1f  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140069b23  mov     r8d, r14d
0x140069b26  mov     qword ptr [rsp+0E0h+var_B8], r13
0x140069b2b  mov     [rsp+0E0h+var_C0], rax
0x140069b30  jmp     loc_140069BD4
0x140069b35  mov     ebx, 80004004h
0x140069b3a  jmp     loc_140069BE6
0x140069b3f  jle     short loc_140069B4A
0x140069b41  movzx   ebx, ax
0x140069b44  or      ebx, 80070000h
0x140069b4a  lea     rax, aDwret0l; "dwRet == 0L"
0x140069b51  mov     [rsp+0E0h+var_B8], ebx; int
0x140069b55  lea     r14, aCbraex; "CBRAEx"
0x140069b5c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x140069b61  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140069b68  mov     r13d, 0A4Bh
0x140069b6e  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069b75  mov     r9, r14; unsigned __int16 *
0x140069b78  mov     r8, rsi; unsigned __int16 *
0x140069b7b  mov     edx, r13d; unsigned int
0x140069b7e  mov     rcx, rdi; unsigned __int16 *
0x140069b81  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069b86  call    cs:__imp_IsDebuggerPresent
0x140069b8c  test    eax, eax
0x140069b8e  lea     rax, aDwret0l; "dwRet == 0L"
0x140069b95  jz      short loc_140069BC3
0x140069b97  mov     [rsp+0E0h+var_A8], ebx
0x140069b9b  mov     r9d, r13d
0x140069b9e  mov     [rsp+0E0h+var_B0], rax
0x140069ba3  mov     qword ptr [rsp+0E0h+var_B8], r14
0x140069ba8  mov     r8, rdi
0x140069bab  mov     [rsp+0E0h+var_C0], rsi
0x140069bb0  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140069bb7  mov     ecx, 2; unsigned __int8
0x140069bbc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140069bc1  jmp     short loc_140069BE6
0x140069bc3  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140069bc7  mov     r8d, r13d
0x140069bca  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140069bcf  mov     [rsp+0E0h+var_C0], r14
0x140069bd4  mov     r9, rsi
0x140069bd7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140069bde  mov     rdx, rdi
0x140069be1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140069be6  mov     rcx, r15; hSCObject
0x140069be9  call    cs:__imp_CloseServiceHandle
0x140069bef  mov     rcx, r12; hSCObject
0x140069bf2  call    cs:__imp_CloseServiceHandle
0x140069bf8  mov     edx, ebx
0x140069bfa  lea     rcx, aWaitforservice; "WaitForServiceStatusChange - Exiting, h"...
0x140069c01  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140069c06  mov     eax, ebx
0x140069c08  mov     rcx, [rbp+57h+var_40]
0x140069c0c  xor     rcx, rsp; StackCookie
0x140069c0f  call    __security_check_cookie
0x140069c14  mov     rbx, [rsp+0E0h+arg_8]
0x140069c1c  add     rsp, 0B0h
0x140069c23  pop     r15
0x140069c25  pop     r14
0x140069c27  pop     r13
0x140069c29  pop     r12
0x140069c2b  pop     rdi
0x140069c2c  pop     rsi
0x140069c2d  pop     rbp
0x140069c2e  retn
```
