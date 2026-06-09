# WaitForServiceStatusChange(ushort const *,ulong,void *,EServiceStatusChangeWaitResult *)

- ea: `0x14000988c`
- end: `0x140009ca5`
- name: `?WaitForServiceStatusChange@@YAJPEBGKPEAXPEAW4EServiceStatusChangeWaitResult@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, void *, enum EServiceStatusChangeWaitResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400068bc`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000988c`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140009aad`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140009aad`
- `ADVAPI32!OpenServiceW` at `0x1400099d3`
- `ADVAPI32!OpenServiceW` at `0x1400099d3`
- `ADVAPI32!CloseServiceHandle` at `0x140009c66`
- `ADVAPI32!CloseServiceHandle` at `0x140009c6f`
- `ADVAPI32!CloseServiceHandle` at `0x140009c66`
- `ADVAPI32!CloseServiceHandle` at `0x140009c6f`
- `ADVAPI32!OpenSCManagerW` at `0x1400098fa`
- `ADVAPI32!OpenSCManagerW` at `0x1400098fa`
- `KERNEL32!IsDebuggerPresent` at `0x140009967`
- `KERNEL32!IsDebuggerPresent` at `0x140009a36`
- `KERNEL32!IsDebuggerPresent` at `0x140009b67`
- `KERNEL32!IsDebuggerPresent` at `0x140009bff`
- `KERNEL32!IsDebuggerPresent` at `0x140009967`
- `KERNEL32!IsDebuggerPresent` at `0x140009a36`
- `KERNEL32!IsDebuggerPresent` at `0x140009b67`
- `KERNEL32!IsDebuggerPresent` at `0x140009bff`
- `KERNEL32!GetLastError` at `0x14000990c`
- `KERNEL32!GetLastError` at `0x1400099dc`
- `KERNEL32!GetLastError` at `0x14000990c`
- `KERNEL32!GetLastError` at `0x1400099dc`
- `KERNEL32!SleepEx` at `0x140009ace`
- `KERNEL32!SleepEx` at `0x140009ace`

## string_xrefs

- `0x1400099fa`: `hService != 0`
- `0x140009a3e`: `hService != 0`
- `0x14000993c`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009a1e`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009b4b`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009be8`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400098ed`: `ServicesActive`
- `0x140009946`: `hServiceManager != 0`
- `0x14000992f`: `WaitForServiceStatusChange`
- `0x140009a11`: `WaitForServiceStatusChange`
- `0x140009b35`: `WaitForServiceStatusChange`
- `0x140009bde`: `WaitForServiceStatusChange`
- `0x140009abd`: `WaitForServiceStatusChange - waiting for status change\n`
- `0x140009b08`: `WaitForServiceStatusChange - APC received\n`
- `0x140009ae8`: `WaitForServiceStatusChange - some other APC was received\n`
- `0x140009b1d`: `WaitForServiceStatusChange - dwRet = %u\n`
- `0x140009c77`: `WaitForServiceStatusChange - Exiting, hr = 0x%X\n`

## pseudocode

```c
__int64 __fastcall WaitForServiceStatusChange(
        const unsigned __int16 *a1,
        __int64 a2,
        void *a3,
        enum EServiceStatusChangeWaitResult *a4)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r12
  signed int v7; // eax
  unsigned int v8; // ebx
  SC_HANDLE v9; // r15
  signed int LastError; // eax
  signed int v11; // eax
  DWORD v12; // eax
  _DWORD v14[4]; // [rsp+40h] [rbp-59h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-49h] BYREF

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v14[0] = 0;
  pNotifyBuffer.pContext = v14;
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NotifyServiceStatusChangeCallback;
  v5 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v6 = v5;
  if ( v5 )
  {
    v9 = OpenServiceW(v5, L"Wms", 0x80000000);
    LastError = GetLastError();
    v8 = LastError;
    if ( v9 )
    {
      while ( 1 )
      {
        v11 = NotifyServiceStatusChangeW(v9, 8u, &pNotifyBuffer);
        v8 = v11;
        if ( v11 )
          break;
        DEBUGMSG(L"WaitForServiceStatusChange - waiting for status change\n");
        v12 = SleepEx(0xFFFFFFFF, 1);
        if ( !v12 )
        {
          v8 = -2147467260;
          goto LABEL_30;
        }
        if ( v12 != 192 )
        {
          DEBUGMSG(L"WaitForServiceStatusChange - dwRet = %u\n", v12);
          v8 = -2147418113;
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
          goto LABEL_30;
        }
        if ( v14[0] != v8 )
        {
          v8 = 0;
          DEBUGMSG(L"WaitForServiceStatusChange - APC received\n");
          *(_DWORD *)a4 = 1;
          goto LABEL_30;
        }
        DEBUGMSG(L"WaitForServiceStatusChange - some other APC was received\n");
        pNotifyBuffer.dwVersion = 2;
        pNotifyBuffer.pContext = v14;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NotifyServiceStatusChangeCallback;
      }
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA4Bu,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"dwRet == 0L",
        v8);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2635,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"dwRet == 0L",
          v8);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2635,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"dwRet == 0L",
          v8);
LABEL_30:
      CloseServiceHandle(v9);
    }
    else
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA45u,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hService != 0",
        v8);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2629,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"hService != 0",
          v8);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2629,
          L"WaitForServiceStatusChange",
          L"CBRAEx",
          L"hService != 0",
          v8);
    }
    CloseServiceHandle(v6);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (v8 & 0x80000000) == 0 )
      v8 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xA40u,
      L"WaitForServiceStatusChange",
      L"CBRAEx",
      L"hServiceManager != 0",
      v8);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        2624,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hServiceManager != 0",
        v8);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        2624,
        L"WaitForServiceStatusChange",
        L"CBRAEx",
        L"hServiceManager != 0",
        v8);
  }
  DEBUGMSG(L"WaitForServiceStatusChange - Exiting, hr = 0x%X\n", v8);
  return v8;
}

```

## disassembly

```asm
0x14000988c  push    rbp
0x14000988e  push    rbx
0x14000988f  push    rsi
0x140009890  push    rdi
0x140009891  push    r12
0x140009893  push    r13
0x140009895  push    r14
0x140009897  push    r15
0x140009899  lea     rbp, [rsp-1Fh]
0x14000989e  sub     rsp, 0B8h
0x1400098a5  mov     rax, cs:__security_cookie
0x1400098ac  xor     rax, rsp
0x1400098af  mov     [rbp+57h+var_50], rax
0x1400098b3  xor     edx, edx; Val
0x1400098b5  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x1400098b9  mov     rdi, r9
0x1400098bc  lea     r8d, [rdx+50h]; Size
0x1400098c0  call    memset_0
0x1400098c5  lea     rax, [rbp+57h+var_B0]
0x1400098c9  mov     [rbp+57h+var_B0], 0
0x1400098d0  mov     ebx, 80000000h
0x1400098d5  mov     [rbp+57h+pNotifyBuffer.pContext], rax
0x1400098d9  mov     r13d, 2
0x1400098df  lea     r14, ?NotifyServiceStatusChangeCallback@@YAXPEAX@Z; NotifyServiceStatusChangeCallback(void *)
0x1400098e6  mov     r8d, ebx; dwDesiredAccess
0x1400098e9  mov     [rbp+57h+pNotifyBuffer.dwVersion], r13d
0x1400098ed  lea     rdx, DatabaseName; "ServicesActive"
0x1400098f4  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], r14
0x1400098f8  xor     ecx, ecx; lpMachineName
0x1400098fa  call    cs:__imp_OpenSCManagerW
0x140009900  mov     r12, rax
0x140009903  test    rax, rax
0x140009906  jnz     loc_1400099C6
0x14000990c  call    cs:__imp_GetLastError
0x140009912  mov     ebx, eax
0x140009914  test    eax, eax
0x140009916  jle     short loc_140009921
0x140009918  movzx   ebx, ax
0x14000991b  or      ebx, 80070000h
0x140009921  mov     eax, 80004005h
0x140009926  lea     r14, aCbraex; "CBRAEx"
0x14000992d  test    ebx, ebx
0x14000992f  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140009936  mov     r15d, 0A40h
0x14000993c  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009943  cmovns  ebx, eax
0x140009946  lea     r12, aHservicemanage; "hServiceManager != 0"
0x14000994d  mov     [rsp+0F0h+var_C8], ebx; int
0x140009951  mov     r9, r14; unsigned __int16 *
0x140009954  mov     r8, rsi; unsigned __int16 *
0x140009957  mov     [rsp+0F0h+var_D0], r12; unsigned __int16 *
0x14000995c  mov     edx, r15d; unsigned int
0x14000995f  mov     rcx, rdi; unsigned __int16 *
0x140009962  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009967  call    cs:__imp_IsDebuggerPresent
0x14000996d  test    eax, eax
0x14000996f  jz      short loc_14000999E
0x140009971  mov     [rsp+0F0h+var_B8], ebx
0x140009975  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000997c  mov     [rsp+0F0h+var_C0], r12
0x140009981  mov     r9d, r15d
0x140009984  mov     qword ptr [rsp+0F0h+var_C8], r14
0x140009989  mov     r8, rdi
0x14000998c  mov     ecx, r13d; unsigned __int8
0x14000998f  mov     [rsp+0F0h+var_D0], rsi
0x140009994  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009999  jmp     loc_140009C75
0x14000999e  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x1400099a2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400099a9  mov     qword ptr [rsp+0F0h+var_C8], r12
0x1400099ae  mov     r9, rsi
0x1400099b1  mov     r8d, r15d
0x1400099b4  mov     [rsp+0F0h+var_D0], r14
0x1400099b9  mov     rdx, rdi
0x1400099bc  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400099c1  jmp     loc_140009C75
0x1400099c6  mov     r8d, ebx; dwDesiredAccess
0x1400099c9  lea     rdx, ServiceName; "Wms"
0x1400099d0  mov     rcx, r12; hSCManager
0x1400099d3  call    cs:__imp_OpenServiceW
0x1400099d9  mov     r15, rax
0x1400099dc  call    cs:__imp_GetLastError
0x1400099e2  mov     ebx, eax
0x1400099e4  test    r15, r15
0x1400099e7  jnz     loc_140009A9C
0x1400099ed  test    eax, eax
0x1400099ef  jle     short loc_1400099FA
0x1400099f1  movzx   ebx, ax
0x1400099f4  or      ebx, 80070000h
0x1400099fa  lea     rax, aHservice0; "hService != 0"
0x140009a01  mov     [rsp+0F0h+var_C8], ebx; int
0x140009a05  lea     r14, aCbraex; "CBRAEx"
0x140009a0c  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x140009a11  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140009a18  mov     r15d, 0A45h
0x140009a1e  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009a25  mov     r9, r14; unsigned __int16 *
0x140009a28  mov     r8, rsi; unsigned __int16 *
0x140009a2b  mov     edx, r15d; unsigned int
0x140009a2e  mov     rcx, rdi; unsigned __int16 *
0x140009a31  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009a36  call    cs:__imp_IsDebuggerPresent
0x140009a3c  test    eax, eax
0x140009a3e  lea     rax, aHservice0; "hService != 0"
0x140009a45  jz      short loc_140009A74
0x140009a47  mov     [rsp+0F0h+var_B8], ebx
0x140009a4b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009a52  mov     [rsp+0F0h+var_C0], rax
0x140009a57  mov     r9d, r15d
0x140009a5a  mov     qword ptr [rsp+0F0h+var_C8], r14
0x140009a5f  mov     r8, rdi
0x140009a62  mov     ecx, r13d; unsigned __int8
0x140009a65  mov     [rsp+0F0h+var_D0], rsi
0x140009a6a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009a6f  jmp     loc_140009C6C
0x140009a74  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x140009a78  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009a7f  mov     qword ptr [rsp+0F0h+var_C8], rax
0x140009a84  mov     r9, rsi
0x140009a87  mov     r8d, r15d
0x140009a8a  mov     [rsp+0F0h+var_D0], r14
0x140009a8f  mov     rdx, rdi
0x140009a92  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009a97  jmp     loc_140009C6C
0x140009a9c  mov     esi, 1
0x140009aa1  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x140009aa5  mov     edx, 8; dwNotifyMask
0x140009aaa  mov     rcx, r15; hService
0x140009aad  call    cs:__imp_NotifyServiceStatusChangeW
0x140009ab3  mov     ebx, eax
0x140009ab5  test    eax, eax
0x140009ab7  jnz     loc_140009BBC
0x140009abd  lea     rcx, aWaitforservice_1; "WaitForServiceStatusChange - waiting fo"...
0x140009ac4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009ac9  mov     edx, esi; bAlertable
0x140009acb  or      ecx, 0FFFFFFFFh; dwMilliseconds
0x140009ace  call    cs:__imp_SleepEx
0x140009ad4  test    eax, eax
0x140009ad6  jz      loc_140009BB2
0x140009adc  cmp     eax, 0C0h
0x140009ae1  jnz     short loc_140009B1B
0x140009ae3  cmp     [rbp+57h+var_B0], ebx
0x140009ae6  jnz     short loc_140009B06
0x140009ae8  lea     rcx, aWaitforservice_4; "WaitForServiceStatusChange - some other"...
0x140009aef  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009af4  lea     rax, [rbp+57h+var_B0]
0x140009af8  mov     [rbp+57h+pNotifyBuffer.dwVersion], r13d
0x140009afc  mov     [rbp+57h+pNotifyBuffer.pContext], rax
0x140009b00  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], r14
0x140009b04  jmp     short loc_140009AA1
0x140009b06  xor     ebx, ebx
0x140009b08  lea     rcx, aWaitforservice_3; "WaitForServiceStatusChange - APC receiv"...
0x140009b0f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009b14  mov     [rdi], esi
0x140009b16  jmp     loc_140009C63
0x140009b1b  mov     edx, eax
0x140009b1d  lea     rcx, aWaitforservice_2; "WaitForServiceStatusChange - dwRet = %u"...
0x140009b24  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009b29  lea     rax, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x140009b30  mov     ebx, 8000FFFFh
0x140009b35  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140009b3c  mov     [rsp+0F0h+var_C8], ebx; int
0x140009b40  mov     r14d, 0A73h
0x140009b46  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x140009b4b  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009b52  mov     r8, rsi; unsigned __int16 *
0x140009b55  mov     edx, r14d; unsigned int
0x140009b58  lea     r9, aChra; "CHRA"
0x140009b5f  mov     rcx, rdi; unsigned __int16 *
0x140009b62  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009b67  call    cs:__imp_IsDebuggerPresent
0x140009b6d  test    eax, eax
0x140009b6f  lea     rax, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x140009b76  jz      short loc_140009B95
0x140009b78  mov     [rsp+0F0h+var_B8], ebx
0x140009b7c  mov     r9d, r14d
0x140009b7f  mov     [rsp+0F0h+var_C0], rax
0x140009b84  lea     rax, aChra; "CHRA"
0x140009b8b  mov     qword ptr [rsp+0F0h+var_C8], rax
0x140009b90  jmp     loc_140009C24
0x140009b95  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x140009b99  mov     r8d, r14d
0x140009b9c  mov     qword ptr [rsp+0F0h+var_C8], rax
0x140009ba1  lea     rax, aChra; "CHRA"
0x140009ba8  mov     [rsp+0F0h+var_D0], rax
0x140009bad  jmp     loc_140009C51
0x140009bb2  mov     ebx, 80004004h
0x140009bb7  jmp     loc_140009C63
0x140009bbc  jle     short loc_140009BC7
0x140009bbe  movzx   ebx, ax
0x140009bc1  or      ebx, 80070000h
0x140009bc7  lea     rax, aDwret0l; "dwRet == 0L"
0x140009bce  mov     [rsp+0F0h+var_C8], ebx; int
0x140009bd2  lea     r14, aCbraex; "CBRAEx"
0x140009bd9  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x140009bde  lea     rsi, aWaitforservice_0; "WaitForServiceStatusChange"
0x140009be5  mov     r9, r14; unsigned __int16 *
0x140009be8  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009bef  mov     r8, rsi; unsigned __int16 *
0x140009bf2  mov     rcx, rdi; unsigned __int16 *
0x140009bf5  mov     edx, 0A4Bh; unsigned int
0x140009bfa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140009bff  call    cs:__imp_IsDebuggerPresent
0x140009c05  test    eax, eax
0x140009c07  lea     rax, aDwret0l; "dwRet == 0L"
0x140009c0e  jz      short loc_140009C3D
0x140009c10  mov     [rsp+0F0h+var_B8], ebx
0x140009c14  mov     r9d, 0A4Bh
0x140009c1a  mov     [rsp+0F0h+var_C0], rax
0x140009c1f  mov     qword ptr [rsp+0F0h+var_C8], r14
0x140009c24  mov     r8, rdi
0x140009c27  mov     [rsp+0F0h+var_D0], rsi
0x140009c2c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009c33  mov     ecx, r13d; unsigned __int8
0x140009c36  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009c3b  jmp     short loc_140009C63
0x140009c3d  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x140009c41  mov     r8d, 0A4Bh
0x140009c47  mov     qword ptr [rsp+0F0h+var_C8], rax
0x140009c4c  mov     [rsp+0F0h+var_D0], r14
0x140009c51  mov     r9, rsi
0x140009c54  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009c5b  mov     rdx, rdi
0x140009c5e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009c63  mov     rcx, r15; hSCObject
0x140009c66  call    cs:__imp_CloseServiceHandle
0x140009c6c  mov     rcx, r12; hSCObject
0x140009c6f  call    cs:__imp_CloseServiceHandle
0x140009c75  mov     edx, ebx
0x140009c77  lea     rcx, aWaitforservice; "WaitForServiceStatusChange - Exiting, h"...
0x140009c7e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009c83  mov     eax, ebx
0x140009c85  mov     rcx, [rbp+57h+var_50]
0x140009c89  xor     rcx, rsp; StackCookie
0x140009c8c  call    __security_check_cookie
0x140009c91  add     rsp, 0B8h
0x140009c98  pop     r15
0x140009c9a  pop     r14
0x140009c9c  pop     r13
0x140009c9e  pop     r12
0x140009ca0  pop     rdi
0x140009ca1  pop     rsi
0x140009ca2  pop     rbx
0x140009ca3  pop     rbp
0x140009ca4  retn
```
