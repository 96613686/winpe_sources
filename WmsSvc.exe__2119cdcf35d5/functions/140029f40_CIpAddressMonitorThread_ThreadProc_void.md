# CIpAddressMonitorThread::ThreadProc(void)

- ea: `0x140029f40`
- end: `0x14002a4be`
- name: `?ThreadProc@CIpAddressMonitorThread@@MEAAJXZ`
- size: `1406`
- prototype: `__int64 __fastcall(PVOID CallerContext)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x140004730`
- `0x140004a04`
- `0x140029f40`
- `0x14002a4c4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x1400757ac`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140029f79`
- `ADVAPI32!OpenSCManagerW` at `0x140029f79`
- `ADVAPI32!OpenServiceW` at `0x14002a057`
- `ADVAPI32!OpenServiceW` at `0x14002a057`
- `ADVAPI32!CloseServiceHandle` at `0x14002a46b`
- `ADVAPI32!CloseServiceHandle` at `0x14002a474`
- `ADVAPI32!CloseServiceHandle` at `0x14002a46b`
- `ADVAPI32!CloseServiceHandle` at `0x14002a474`
- `KERNEL32!GetLastError` at `0x140029f8f`
- `KERNEL32!GetLastError` at `0x14002a06d`
- `KERNEL32!GetLastError` at `0x140029f8f`
- `KERNEL32!GetLastError` at `0x14002a06d`
- `KERNEL32!IsDebuggerPresent` at `0x140029fea`
- `KERNEL32!IsDebuggerPresent` at `0x14002a0c8`
- `KERNEL32!IsDebuggerPresent` at `0x14002a1bb`
- `KERNEL32!IsDebuggerPresent` at `0x14002a2e9`
- `KERNEL32!IsDebuggerPresent` at `0x140029fea`
- `KERNEL32!IsDebuggerPresent` at `0x14002a0c8`
- `KERNEL32!IsDebuggerPresent` at `0x14002a1bb`
- `KERNEL32!IsDebuggerPresent` at `0x14002a2e9`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x14002a297`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x14002a430`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x14002a297`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x14002a430`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x14002a3f4`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x14002a3f4`

## string_xrefs

- `0x14002a0a7`: `hService != 0`
- `0x140029fbf`: `termsrv\wms\src\devices\wmssvc\ipaddressmonitorthread.cpp`
- `0x14002a09d`: `termsrv\wms\src\devices\wmssvc\ipaddressmonitorthread.cpp`
- `0x14002a16c`: `termsrv\wms\src\devices\wmssvc\ipaddressmonitorthread.cpp`
- `0x14002a190`: `termsrv\wms\src\devices\wmssvc\ipaddressmonitorthread.cpp`
- `0x140029f61`: `CIpAddressMonitorThread::ThreadProc - Entering\n`
- `0x140029fc9`: `hServiceControlManager != 0`
- `0x140029fb2`: `CIpAddressMonitorThread::ThreadProc`
- `0x14002a090`: `CIpAddressMonitorThread::ThreadProc`
- `0x14002a14d`: `CIpAddressMonitorThread::ThreadProc`
- `0x14002a15c`: `Thread kill event was signalled`
- `0x14002a19d`: `eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged`
- `0x14002a1c3`: `eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged`
- `0x14002a270`: `CIpAddressMonitorThread::ThreadProc - Requesting Ip address change notifications\n`
- `0x14002a357`: `CIpAddressMonitorThread::ThreadProc - waiting for Network Store Interface Service to stop\n`
- `0x14002a38c`: `CIpAddressMonitorThread::ThreadProc - Network Store Interface Service was stopped, waiting for restart notification\n`
- `0x14002a3c1`: `CIpAddressMonitorThread::ThreadProc - Network Store Interface Service was restarted, reregistering Ip address change notifications\n`
- `0x14002a3e4`: `CIpAddressMonitorThread::ThreadProc - cancelling previous address change notification request\n`
- `0x14002a408`: `CIpAddressMonitorThread::ThreadProc - CancelMibChangeNotify2 returned 0x%X\n`
- `0x14002a457`: `CIpAddressMonitorThread::ThreadProc - thread kill event was signalled\n`
- `0x14002a47c`: `CIpAddressMonitorThread::ThreadProc - Exiting, hr = 0x%X\n`

## pseudocode

```c
__int64 __fastcall CIpAddressMonitorThread::ThreadProc(HANDLE *CallerContext)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r12
  signed int v4; // eax
  int v5; // ebx
  SC_HANDLE v6; // rax
  struct SC_HANDLE__ *v7; // r14
  signed int LastError; // eax
  __int64 v9; // r8
  const unsigned __int16 *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  const unsigned __int16 *v13; // r9
  HANDLE *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // r8
  const unsigned __int16 *v17; // r9
  PlatformUtils *v18; // rcx
  unsigned int v19; // r13d
  __int64 v20; // r8
  const unsigned __int16 *v21; // r9
  int v22; // eax
  NTSTATUS v23; // r14d
  __int64 v24; // rdx
  __int64 v25; // r8
  const unsigned __int16 *v26; // r9
  __int64 v28; // [rsp+30h] [rbp-20h]
  SC_HANDLE hSCObject; // [rsp+40h] [rbp-10h]
  int v30; // [rsp+98h] [rbp+48h] BYREF
  SC_HANDLE v31; // [rsp+A0h] [rbp+50h]
  PSRWLOCK v32; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  DEBUGMSG(L"CIpAddressMonitorThread::ThreadProc - Entering\n");
  v2 = OpenSCManagerW(0, 0, 4u);
  v31 = v2;
  v3 = v2;
  if ( v2 )
  {
    v6 = OpenServiceW(v2, L"Nsi", 4u);
    hSCObject = v6;
    v7 = v6;
    if ( v6 )
    {
      v5 = CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(
             (CIpAddressMonitorThread *)CallerContext,
             v6,
             8u,
             (enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)&v30);
      if ( v5 >= 0 )
      {
        if ( v30 == 2 )
        {
          v5 = 0;
          DEBUGMSGLEVEL(
            4u,
            L"%s(%d) - %s - Test failed:  %s\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
            107,
            L"CIpAddressMonitorThread::ThreadProc",
            L"Thread kill event was signalled");
        }
        else
        {
          if ( v30 != 1 )
          {
            LOGASSERT(
              L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
              0x6Cu,
              L"CIpAddressMonitorThread::ThreadProc",
              v10,
              L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
                108,
                L"CIpAddressMonitorThread::ThreadProc",
                L"ASSERT",
                L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
                108,
                L"CIpAddressMonitorThread::ThreadProc",
                L"ASSERT",
                L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
          }
          CAutoWriteLock::CAutoWriteLock(
            (CAutoWriteLock *)&v32,
            (struct CSharedReaderWriterLock *)(CallerContext + 42),
            v9,
            v10);
          if ( *((_DWORD *)CallerContext + 154) )
          {
            v5 = 0;
            DEBUGMSGLEVEL(
              4u,
              L"%s(%d) - %s - Test failed:  %s\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
              117,
              L"CIpAddressMonitorThread::ThreadProc",
              L"IP address change notifications were cancelled before NotifyUnicastIpAddressChange was called");
            CAutoWriteLock::~CAutoWriteLock(&v32, v11, v12, v13);
          }
          else
          {
            DEBUGMSG(L"CIpAddressMonitorThread::ThreadProc - Requesting Ip address change notifications\n");
            v14 = CallerContext + 41;
            v5 = NotifyUnicastIpAddressChange(
                   0,
                   CIpAddressMonitorThread::s_NotifyUnicastIpAddressChangeCallback,
                   CallerContext,
                   0,
                   CallerContext + 41);
            CAutoWriteLock::~CAutoWriteLock(&v32, v15, v16, v17);
            if ( v5 )
            {
              if ( v5 > 0 )
                v5 = (unsigned __int16)v5 | 0x80070000;
              v19 = 121;
LABEL_30:
              LOGASSERTHR(
                L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
                v19,
                L"CIpAddressMonitorThread::ThreadProc",
                L"CBRAEx",
                L"dwError == 0L",
                v5);
              if ( IsDebuggerPresent() )
              {
                DEBUGMSGLEVEL(
                  2u,
                  L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
                  v19,
                  L"CIpAddressMonitorThread::ThreadProc",
                  L"CBRAEx",
                  L"dwError == 0L",
                  v5);
              }
              else
              {
                LODWORD(v28) = v5;
                DEBUGMSGBOX(
                  L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
                  v19,
                  L"CIpAddressMonitorThread::ThreadProc",
                  L"CBRAEx",
                  L"dwError == 0L",
                  v28);
              }
            }
            else
            {
              v5 = PlatformUtils::SetVmNetworkToPrivate(v18);
              if ( v5 >= 0 )
              {
                while ( 1 )
                {
                  DEBUGMSG(L"CIpAddressMonitorThread::ThreadProc - waiting for Network Store Interface Service to stop\n");
                  v5 = CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(
                         (CIpAddressMonitorThread *)CallerContext,
                         v7,
                         1u,
                         (enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)&v30);
                  if ( v5 < 0 )
                    break;
                  if ( v30 == 2 )
                    goto LABEL_45;
                  DEBUGMSG(
                    L"CIpAddressMonitorThread::ThreadProc - Network Store Interface Service was stopped, waiting for resta"
                     "rt notification\n");
                  v5 = CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(
                         (CIpAddressMonitorThread *)CallerContext,
                         v7,
                         8u,
                         (enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)&v30);
                  if ( v5 < 0 )
                    break;
                  if ( v30 == 1 )
                  {
                    DEBUGMSG(
                      L"CIpAddressMonitorThread::ThreadProc - Network Store Interface Service was restarted, reregistering"
                       " Ip address change notifications\n");
                    CAutoWriteLock::CAutoWriteLock(
                      (CAutoWriteLock *)&v32,
                      (struct CSharedReaderWriterLock *)(CallerContext + 42),
                      v20,
                      v21);
                    if ( *v14 )
                    {
                      DEBUGMSG(
                        L"CIpAddressMonitorThread::ThreadProc - cancelling previous address change notification request\n");
                      v22 = CancelMibChangeNotify2(*v14);
                      if ( v22 > 0 )
                        v22 = (unsigned __int16)v22 | 0x80070000;
                      DEBUGMSG(
                        L"CIpAddressMonitorThread::ThreadProc - CancelMibChangeNotify2 returned 0x%X\n",
                        (unsigned int)v22);
                      *v14 = 0;
                    }
                    v23 = NotifyUnicastIpAddressChange(
                            0,
                            CIpAddressMonitorThread::s_NotifyUnicastIpAddressChangeCallback,
                            CallerContext,
                            0,
                            CallerContext + 41);
                    CAutoWriteLock::~CAutoWriteLock(&v32, v24, v25, v26);
                    if ( v23 )
                    {
                      if ( v23 > 0 )
                        v5 = (unsigned __int16)v23 | 0x80070000;
                      else
                        v5 = v23;
                      v19 = 170;
                      goto LABEL_30;
                    }
                    v7 = hSCObject;
                  }
                  if ( v30 == 2 )
                  {
LABEL_45:
                    DEBUGMSG(
                      L"CIpAddressMonitorThread::ThreadProc - thread kill event was signalled\n",
                      (unsigned int)v5);
                    break;
                  }
                }
              }
            }
            v3 = v31;
          }
        }
      }
      CloseServiceHandle(hSCObject);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
        0x64u,
        L"CIpAddressMonitorThread::ThreadProc",
        L"CBRAEx",
        L"hService != 0",
        v5);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
          100,
          L"CIpAddressMonitorThread::ThreadProc",
          L"CBRAEx",
          L"hService != 0",
          v5);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
          100,
          L"CIpAddressMonitorThread::ThreadProc",
          L"CBRAEx",
          L"hService != 0",
          v5);
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
      0x60u,
      L"CIpAddressMonitorThread::ThreadProc",
      L"CBRAEx",
      L"hServiceControlManager != 0",
      v5);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
        96,
        L"CIpAddressMonitorThread::ThreadProc",
        L"CBRAEx",
        L"hServiceControlManager != 0",
        v5);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\ipaddressmonitorthread.cpp",
        96,
        L"CIpAddressMonitorThread::ThreadProc",
        L"CBRAEx",
        L"hServiceControlManager != 0",
        v5);
  }
  DEBUGMSG(L"CIpAddressMonitorThread::ThreadProc - Exiting, hr = 0x%X\n", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140029f40  mov     [rsp-38h+arg_0], rbx
0x140029f45  push    rbp
0x140029f46  push    rsi
0x140029f47  push    rdi
0x140029f48  push    r12
0x140029f4a  push    r13
0x140029f4c  push    r14
0x140029f4e  push    r15
0x140029f50  mov     rbp, rsp
0x140029f53  sub     rsp, 50h
0x140029f57  mov     r13, rcx
0x140029f5a  mov     [rbp+arg_8], 0
0x140029f61  lea     rcx, aCipaddressmoni_12; "CIpAddressMonitorThread::ThreadProc - E"...
0x140029f68  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140029f6d  mov     ebx, 4
0x140029f72  xor     edx, edx; lpDatabaseName
0x140029f74  mov     r8d, ebx; dwDesiredAccess
0x140029f77  xor     ecx, ecx; lpMachineName
0x140029f79  call    cs:__imp_OpenSCManagerW
0x140029f7f  mov     [rbp+arg_10], rax
0x140029f83  mov     r12, rax
0x140029f86  test    rax, rax
0x140029f89  jnz     loc_14002A04A
0x140029f8f  call    cs:__imp_GetLastError
0x140029f95  mov     ebx, eax
0x140029f97  test    eax, eax
0x140029f99  jle     short loc_140029FA4
0x140029f9b  movzx   ebx, ax
0x140029f9e  or      ebx, 80070000h
0x140029fa4  mov     eax, 80004005h
0x140029fa9  lea     r14, aCbraex; "CBRAEx"
0x140029fb0  test    ebx, ebx
0x140029fb2  lea     rsi, aCipaddressmoni_13; "CIpAddressMonitorThread::ThreadProc"
0x140029fb9  mov     r15d, 60h ; '`'
0x140029fbf  lea     rdi, aTermsrvWmsSrcD_24; "termsrv\\wms\\src\\devices\\wmssvc\\ipa"...
0x140029fc6  cmovns  ebx, eax
0x140029fc9  lea     r12, aHservicecontro; "hServiceControlManager != 0"
0x140029fd0  mov     [rsp+50h+var_28], ebx; int
0x140029fd4  mov     r9, r14; unsigned __int16 *
0x140029fd7  mov     r8, rsi; unsigned __int16 *
0x140029fda  mov     [rsp+50h+NotificationHandle], r12; unsigned __int16 *
0x140029fdf  mov     edx, r15d; unsigned int
0x140029fe2  mov     rcx, rdi; unsigned __int16 *
0x140029fe5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140029fea  call    cs:__imp_IsDebuggerPresent
0x140029ff0  test    eax, eax
0x140029ff2  jz      short loc_14002A022
0x140029ff4  mov     [rsp+50h+var_18], ebx
0x140029ff8  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140029fff  mov     [rsp+50h+var_20], r12
0x14002a004  lea     ecx, [r15-5Eh]; unsigned __int8
0x14002a008  mov     qword ptr [rsp+50h+var_28], r14
0x14002a00d  mov     r9d, r15d
0x14002a010  mov     r8, rdi
0x14002a013  mov     [rsp+50h+NotificationHandle], rsi
0x14002a018  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a01d  jmp     loc_14002A47A
0x14002a022  mov     dword ptr [rsp+50h+var_20], ebx
0x14002a026  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002a02d  mov     qword ptr [rsp+50h+var_28], r12
0x14002a032  mov     r9, rsi
0x14002a035  mov     r8d, r15d
0x14002a038  mov     [rsp+50h+NotificationHandle], r14
0x14002a03d  mov     rdx, rdi
0x14002a040  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002a045  jmp     loc_14002A47A
0x14002a04a  mov     r8d, ebx; dwDesiredAccess
0x14002a04d  lea     rdx, aNsi; "Nsi"
0x14002a054  mov     rcx, rax; hSCManager
0x14002a057  call    cs:__imp_OpenServiceW
0x14002a05d  mov     [rbp+hSCObject], rax
0x14002a061  mov     r14, rax
0x14002a064  test    rax, rax
0x14002a067  jnz     loc_14002A128
0x14002a06d  call    cs:__imp_GetLastError
0x14002a073  mov     ebx, eax
0x14002a075  test    eax, eax
0x14002a077  jle     short loc_14002A082
0x14002a079  movzx   ebx, ax
0x14002a07c  or      ebx, 80070000h
0x14002a082  mov     eax, 80004005h
0x14002a087  lea     r14, aCbraex; "CBRAEx"
0x14002a08e  test    ebx, ebx
0x14002a090  lea     rsi, aCipaddressmoni_13; "CIpAddressMonitorThread::ThreadProc"
0x14002a097  mov     r15d, 64h ; 'd'
0x14002a09d  lea     rdi, aTermsrvWmsSrcD_24; "termsrv\\wms\\src\\devices\\wmssvc\\ipa"...
0x14002a0a4  cmovns  ebx, eax
0x14002a0a7  lea     r13, aHservice0; "hService != 0"
0x14002a0ae  mov     [rsp+50h+var_28], ebx; int
0x14002a0b2  mov     r9, r14; unsigned __int16 *
0x14002a0b5  mov     r8, rsi; unsigned __int16 *
0x14002a0b8  mov     [rsp+50h+NotificationHandle], r13; unsigned __int16 *
0x14002a0bd  mov     edx, r15d; unsigned int
0x14002a0c0  mov     rcx, rdi; unsigned __int16 *
0x14002a0c3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002a0c8  call    cs:__imp_IsDebuggerPresent
0x14002a0ce  test    eax, eax
0x14002a0d0  jz      short loc_14002A100
0x14002a0d2  mov     [rsp+50h+var_18], ebx
0x14002a0d6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002a0dd  mov     [rsp+50h+var_20], r13
0x14002a0e2  lea     ecx, [r15-62h]; unsigned __int8
0x14002a0e6  mov     qword ptr [rsp+50h+var_28], r14
0x14002a0eb  mov     r9d, r15d
0x14002a0ee  mov     r8, rdi
0x14002a0f1  mov     [rsp+50h+NotificationHandle], rsi
0x14002a0f6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a0fb  jmp     loc_14002A471
0x14002a100  mov     dword ptr [rsp+50h+var_20], ebx
0x14002a104  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002a10b  mov     qword ptr [rsp+50h+var_28], r13
0x14002a110  mov     r9, rsi
0x14002a113  mov     r8d, r15d
0x14002a116  mov     [rsp+50h+NotificationHandle], r14
0x14002a11b  mov     rdx, rdi
0x14002a11e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002a123  jmp     loc_14002A471
0x14002a128  lea     r9, [rbp+arg_8]; enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *
0x14002a12c  mov     r8d, 8; unsigned int
0x14002a132  mov     rdx, rax; struct SC_HANDLE__ *
0x14002a135  mov     rcx, r13; this
0x14002a138  call    ?WaitForServiceStatusChangeOrThreadKillEvent@CIpAddressMonitorThread@@IEAAJPEAUSC_HANDLE__@@KPEAW4EServiceStatusChangeWaitResult@1@@Z; CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(SC_HANDLE__ *,ulong,CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)
0x14002a13d  mov     ebx, eax
0x14002a13f  test    eax, eax
0x14002a141  js      loc_14002A467
0x14002a147  mov     r15d, 2
0x14002a14d  lea     rsi, aCipaddressmoni_13; "CIpAddressMonitorThread::ThreadProc"
0x14002a154  cmp     [rbp+arg_8], r15d
0x14002a158  jnz     short loc_14002A18C
0x14002a15a  xor     ebx, ebx
0x14002a15c  lea     rax, aThreadKillEven; "Thread kill event was signalled"
0x14002a163  mov     qword ptr [rsp+50h+var_28], rax
0x14002a168  lea     r9d, [r15+69h]
0x14002a16c  lea     r8, aTermsrvWmsSrcD_24; "termsrv\\wms\\src\\devices\\wmssvc\\ipa"...
0x14002a173  mov     [rsp+50h+NotificationHandle], rsi
0x14002a178  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002a17f  lea     ecx, [rbx+4]; unsigned __int8
0x14002a182  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a187  jmp     loc_14002A467
0x14002a18c  cmp     [rbp+arg_8], 1
0x14002a190  lea     rdi, aTermsrvWmsSrcD_24; "termsrv\\wms\\src\\devices\\wmssvc\\ipa"...
0x14002a197  jz      loc_14002A21F
0x14002a19d  lea     rax, aEservicestatus; "eServiceStatusChangeWaitResult == SSWR_"...
0x14002a1a4  mov     ebx, 6Ch ; 'l'
0x14002a1a9  mov     edx, ebx; unsigned int
0x14002a1ab  mov     [rsp+50h+NotificationHandle], rax; unsigned __int16 *
0x14002a1b0  mov     r8, rsi; unsigned __int16 *
0x14002a1b3  mov     rcx, rdi; unsigned __int16 *
0x14002a1b6  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14002a1bb  call    cs:__imp_IsDebuggerPresent
0x14002a1c1  test    eax, eax
0x14002a1c3  lea     rax, aEservicestatus; "eServiceStatusChangeWaitResult == SSWR_"...
0x14002a1ca  jz      short loc_14002A1F9
0x14002a1cc  mov     [rsp+50h+var_20], rax
0x14002a1d1  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002a1d8  lea     rax, aAssert; "ASSERT"
0x14002a1df  mov     r9d, ebx
0x14002a1e2  mov     qword ptr [rsp+50h+var_28], rax
0x14002a1e7  mov     r8, rdi
0x14002a1ea  mov     ecx, r15d; unsigned __int8
0x14002a1ed  mov     [rsp+50h+NotificationHandle], rsi
0x14002a1f2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a1f7  jmp     short loc_14002A21F
0x14002a1f9  mov     qword ptr [rsp+50h+var_28], rax
0x14002a1fe  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002a205  lea     rax, aAssert; "ASSERT"
0x14002a20c  mov     r9, rsi
0x14002a20f  mov     r8d, ebx
0x14002a212  mov     [rsp+50h+NotificationHandle], rax
0x14002a217  mov     rdx, rdi
0x14002a21a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002a21f  lea     rdx, [r13+150h]; struct CSharedReaderWriterLock *
0x14002a226  lea     rcx, [rbp+arg_18]; this
0x14002a22a  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x14002a22f  cmp     dword ptr [r13+268h], 0
0x14002a237  jz      short loc_14002A270
0x14002a239  xor     ebx, ebx
0x14002a23b  lea     rax, aIpAddressChang; "IP address change notifications were ca"...
0x14002a242  mov     qword ptr [rsp+50h+var_28], rax
0x14002a247  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002a24e  mov     r8, rdi
0x14002a251  mov     [rsp+50h+NotificationHandle], rsi
0x14002a256  lea     r9d, [rbx+75h]
0x14002a25a  lea     ecx, [rbx+4]; unsigned __int8
0x14002a25d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a262  lea     rcx, [rbp+arg_18]; this
0x14002a266  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002a26b  jmp     loc_14002A467
0x14002a270  lea     rcx, aCipaddressmoni_6; "CIpAddressMonitorThread::ThreadProc - R"...
0x14002a277  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a27c  lea     r12, [r13+148h]
0x14002a283  xor     ecx, ecx; Family
0x14002a285  xor     r9d, r9d; InitialNotification
0x14002a288  mov     [rsp+50h+NotificationHandle], r12; NotificationHandle
0x14002a28d  mov     r8, r13; CallerContext
0x14002a290  lea     rdx, ?s_NotifyUnicastIpAddressChangeCallback@CIpAddressMonitorThread@@KAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x14002a297  call    cs:__imp_NotifyUnicastIpAddressChange
0x14002a29d  lea     rcx, [rbp+arg_18]; this
0x14002a2a1  mov     ebx, eax
0x14002a2a3  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002a2a8  test    ebx, ebx
0x14002a2aa  jz      loc_14002A348
0x14002a2b0  jle     short loc_14002A2BB
0x14002a2b2  movzx   ebx, bx
0x14002a2b5  or      ebx, 80070000h
0x14002a2bb  mov     r13d, 79h ; 'y'
0x14002a2c1  lea     r14, aCbraex; "CBRAEx"
0x14002a2c8  mov     [rsp+50h+var_28], ebx; int
0x14002a2cc  lea     r12, aDwerror0l; "dwError == 0L"
0x14002a2d3  mov     r9, r14; unsigned __int16 *
0x14002a2d6  mov     r8, rsi; unsigned __int16 *
0x14002a2d9  mov     [rsp+50h+NotificationHandle], r12; unsigned __int16 *
0x14002a2de  mov     edx, r13d; unsigned int
0x14002a2e1  mov     rcx, rdi; unsigned __int16 *
0x14002a2e4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002a2e9  call    cs:__imp_IsDebuggerPresent
0x14002a2ef  test    eax, eax
0x14002a2f1  jz      short loc_14002A320
0x14002a2f3  mov     [rsp+50h+var_18], ebx
0x14002a2f7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002a2fe  mov     [rsp+50h+var_20], r12
0x14002a303  mov     r9d, r13d
0x14002a306  mov     qword ptr [rsp+50h+var_28], r14
0x14002a30b  mov     r8, rdi
0x14002a30e  mov     ecx, r15d; unsigned __int8
0x14002a311  mov     [rsp+50h+NotificationHandle], rsi
0x14002a316  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002a31b  jmp     loc_14002A463
0x14002a320  mov     dword ptr [rsp+50h+var_20], ebx
0x14002a324  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002a32b  mov     qword ptr [rsp+50h+var_28], r12
0x14002a330  mov     r9, rsi
0x14002a333  mov     r8d, r13d
0x14002a336  mov     [rsp+50h+NotificationHandle], r14
0x14002a33b  mov     rdx, rdi
0x14002a33e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002a343  jmp     loc_14002A463
0x14002a348  call    ?SetVmNetworkToPrivate@PlatformUtils@@YAJXZ; PlatformUtils::SetVmNetworkToPrivate(void)
0x14002a34d  mov     ebx, eax
0x14002a34f  test    eax, eax
0x14002a351  js      loc_14002A463
0x14002a357  lea     rcx, aCipaddressmoni_2; "CIpAddressMonitorThread::ThreadProc - w"...
0x14002a35e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a363  lea     r9, [rbp+arg_8]; enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *
0x14002a367  mov     r8d, 1; unsigned int
0x14002a36d  mov     rdx, r14; struct SC_HANDLE__ *
0x14002a370  mov     rcx, r13; this
0x14002a373  call    ?WaitForServiceStatusChangeOrThreadKillEvent@CIpAddressMonitorThread@@IEAAJPEAUSC_HANDLE__@@KPEAW4EServiceStatusChangeWaitResult@1@@Z; CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(SC_HANDLE__ *,ulong,CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)
0x14002a378  mov     ebx, eax
0x14002a37a  test    eax, eax
0x14002a37c  js      loc_14002A463
0x14002a382  cmp     [rbp+arg_8], r15d
0x14002a386  jz      loc_14002A455
0x14002a38c  lea     rcx, aCipaddressmoni_22; "CIpAddressMonitorThread::ThreadProc - N"...
0x14002a393  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a398  lea     r9, [rbp+arg_8]; enum CIpAddressMonitorThread::EServiceStatusChangeWaitResult *
0x14002a39c  mov     r8d, 8; unsigned int
0x14002a3a2  mov     rdx, r14; struct SC_HANDLE__ *
0x14002a3a5  mov     rcx, r13; this
0x14002a3a8  call    ?WaitForServiceStatusChangeOrThreadKillEvent@CIpAddressMonitorThread@@IEAAJPEAUSC_HANDLE__@@KPEAW4EServiceStatusChangeWaitResult@1@@Z; CIpAddressMonitorThread::WaitForServiceStatusChangeOrThreadKillEvent(SC_HANDLE__ *,ulong,CIpAddressMonitorThread::EServiceStatusChangeWaitResult *)
0x14002a3ad  mov     ebx, eax
0x14002a3af  test    eax, eax
0x14002a3b1  js      loc_14002A463
0x14002a3b7  cmp     [rbp+arg_8], 1
0x14002a3bb  jnz     loc_14002A44B
0x14002a3c1  lea     rcx, aCipaddressmoni_15; "CIpAddressMonitorThread::ThreadProc - N"...
0x14002a3c8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a3cd  lea     rdx, [r13+150h]; struct CSharedReaderWriterLock *
0x14002a3d4  lea     rcx, [rbp+arg_18]; this
0x14002a3d8  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x14002a3dd  cmp     qword ptr [r12], 0
0x14002a3e2  jz      short loc_14002A41C
0x14002a3e4  lea     rcx, aCipaddressmoni_4; "CIpAddressMonitorThread::ThreadProc - c"...
0x14002a3eb  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a3f0  mov     rcx, [r12]; NotificationHandle
0x14002a3f4  call    cs:__imp_CancelMibChangeNotify2
0x14002a3fa  test    eax, eax
0x14002a3fc  jle     short loc_14002A406
0x14002a3fe  movzx   eax, ax
0x14002a401  or      eax, 80070000h
0x14002a406  mov     edx, eax
0x14002a408  lea     rcx, aCipaddressmoni_0; "CIpAddressMonitorThread::ThreadProc - C"...
0x14002a40f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002a414  mov     qword ptr [r12], 0
0x14002a41c  xor     ecx, ecx; Family
0x14002a41e  mov     [rsp+50h+NotificationHandle], r12; NotificationHandle
0x14002a423  xor     r9d, r9d; InitialNotification
0x14002a426  lea     rdx, ?s_NotifyUnicastIpAddressChangeCallback@CIpAddressMonitorThread@@KAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x14002a42d  mov     r8, r13; CallerContext
0x14002a430  call    cs:__imp_NotifyUnicastIpAddressChange
0x14002a436  lea     rcx, [rbp+arg_18]; this
0x14002a43a  mov     r14d, eax
0x14002a43d  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002a442  test    r14d, r14d
0x14002a445  jnz     short loc_14002A4A2
0x14002a447  mov     r14, [rbp+hSCObject]
0x14002a44b  cmp     [rbp+arg_8], r15d
0x14002a44f  jnz     loc_14002A357
0x14002a455  mov     edx, ebx
0x14002a457  lea     rcx, aCipaddressmoni_8; "CIpAddressMonitorThread::ThreadProc - t"...
  ... truncated ...
```
