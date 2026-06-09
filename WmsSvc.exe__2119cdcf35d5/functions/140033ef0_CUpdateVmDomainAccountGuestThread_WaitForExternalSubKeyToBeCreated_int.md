# CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated(int *)

- ea: `0x140033ef0`
- end: `0x1400343cf`
- name: `?WaitForExternalSubKeyToBeCreated@CUpdateVmDomainAccountGuestThread@@IEAAJPEAH@Z`
- size: `1247`
- prototype: `__int64 __fastcall(CUpdateVmDomainAccountGuestThread *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140033ca0`

## callees

- `0x140033ef0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140033f46`
- `ADVAPI32!RegOpenKeyExW` at `0x140034139`
- `ADVAPI32!RegOpenKeyExW` at `0x140033f46`
- `ADVAPI32!RegOpenKeyExW` at `0x140034139`
- `ADVAPI32!RegCloseKey` at `0x140034397`
- `ADVAPI32!RegCloseKey` at `0x1400343ae`
- `ADVAPI32!RegCloseKey` at `0x140034397`
- `ADVAPI32!RegCloseKey` at `0x1400343ae`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400340b8`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140034185`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400340b8`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140034185`
- `KERNEL32!CloseHandle` at `0x140034380`
- `KERNEL32!CloseHandle` at `0x140034380`
- `KERNEL32!ResetEvent` at `0x140034150`
- `KERNEL32!ResetEvent` at `0x140034150`
- `KERNEL32!WaitForMultipleObjects` at `0x140034102`
- `KERNEL32!WaitForMultipleObjects` at `0x140034102`
- `KERNEL32!CreateEventW` at `0x14003400d`
- `KERNEL32!CreateEventW` at `0x14003400d`
- `KERNEL32!GetLastError` at `0x140034020`
- `KERNEL32!GetLastError` at `0x14003420a`
- `KERNEL32!GetLastError` at `0x1400342e1`
- `KERNEL32!GetLastError` at `0x140034020`
- `KERNEL32!GetLastError` at `0x14003420a`
- `KERNEL32!GetLastError` at `0x1400342e1`
- `KERNEL32!IsDebuggerPresent` at `0x140033f9d`
- `KERNEL32!IsDebuggerPresent` at `0x14003407b`
- `KERNEL32!IsDebuggerPresent` at `0x1400341e1`
- `KERNEL32!IsDebuggerPresent` at `0x140034265`
- `KERNEL32!IsDebuggerPresent` at `0x1400342c2`
- `KERNEL32!IsDebuggerPresent` at `0x14003433c`
- `KERNEL32!IsDebuggerPresent` at `0x140033f9d`
- `KERNEL32!IsDebuggerPresent` at `0x14003407b`
- `KERNEL32!IsDebuggerPresent` at `0x1400341e1`
- `KERNEL32!IsDebuggerPresent` at `0x140034265`
- `KERNEL32!IsDebuggerPresent` at `0x1400342c2`
- `KERNEL32!IsDebuggerPresent` at `0x14003433c`

## string_xrefs

- `0x14003405a`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x140033f7c`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034050`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x1400341be`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x14003423a`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x1400342aa`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034311`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140033f67`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x140034043`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x1400341b4`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14003422d`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14003429d`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x140034304`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x1400340de`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for HKLM\SOFTWARE\Microsoft\Virtual Machine\External to be created\n`
- `0x140034361`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n`
- `0x140034162`: `CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n`

## pseudocode

```c
__int64 __fastcall CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated(HANDLE *this, int *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  unsigned int v6; // r12d
  __int64 v7; // r9
  __int64 v8; // r8
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v11; // r15d
  LSTATUS v12; // eax
  int v13; // edi
  DWORD v14; // eax
  LSTATUS v15; // eax
  signed int v16; // eax
  bool v17; // zf
  const unsigned __int16 *v18; // rax
  signed int v19; // eax
  const unsigned __int16 *v21; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v22; // [rsp+30h] [rbp-20h]
  int v23; // [rsp+30h] [rbp-20h]
  int v24; // [rsp+38h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  phkResult = 0;
  *(_OWORD *)Handles = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine", 0, 0x10u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = 79;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
      v6,
      L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
      L"CBRAEx",
      L"lr == 0L",
      v5);
    if ( !IsDebuggerPresent() )
    {
      v8 = v6;
      goto LABEL_9;
    }
    v24 = v5;
    v7 = v6;
    v22 = L"lr == 0L";
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Handles[1] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v11 = 82;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
      0x52u,
      L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
      L"CBRAEx",
      L"rghEvents[ET_REGISTRY_CHANGE] != 0",
      v5);
    if ( !IsDebuggerPresent() )
    {
      v23 = v5;
      v21 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
LABEL_19:
      v8 = v11;
      goto LABEL_10;
    }
    v24 = v5;
    v7 = 82;
    v22 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
    goto LABEL_7;
  }
  v12 = RegNotifyChangeKeyValue(hKey, 0, 1u, EventW, 1);
  v5 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    v6 = 85;
    goto LABEL_5;
  }
  v13 = 0;
  Handles[0] = this[3];
  DEBUGMSG(
    L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for HKLM\\SOFTWARE\\Microsoft\\V"
     "irtual Machine\\External to be created\n");
  while ( 1 )
  {
    v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v14 )
    {
      DEBUGMSG(L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n");
LABEL_56:
      v5 = 0;
      *a2 = v13;
      goto LABEL_57;
    }
    if ( v14 != 1 )
    {
      v19 = GetLastError();
      v5 = v19;
      if ( v19 > 0 )
        v5 = (unsigned __int16)v19 | 0x80070000;
      v11 = 126;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        0x7Eu,
        L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"0",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"0";
LABEL_53:
      if ( !v17 )
      {
LABEL_54:
        v24 = v5;
        v7 = v11;
        v22 = v18;
LABEL_7:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
          v7,
          L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
          L"CBRAEx",
          v22,
          v24,
          Handles[0]);
        goto LABEL_57;
      }
LABEL_47:
      v23 = v5;
      v21 = v18;
      goto LABEL_19;
    }
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &phkResult);
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      v11 = 104;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        0x68u,
        L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"lr == 0L || lr == 2L";
      if ( !v17 )
        goto LABEL_54;
      goto LABEL_47;
    }
    if ( !ResetEvent(Handles[1]) )
    {
      v16 = GetLastError();
      v5 = v16;
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      v11 = 107;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        0x6Bu,
        L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"fSuccess",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"fSuccess";
      goto LABEL_53;
    }
    if ( v5 )
      break;
    DEBUGMSG(L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n");
    v13 = 1;
LABEL_32:
    if ( v13 )
      goto LABEL_56;
  }
  v15 = RegNotifyChangeKeyValue(hKey, 0, 1u, Handles[1], 1);
  v5 = v15;
  if ( !v15 )
    goto LABEL_32;
  if ( v15 > 0 )
    v5 = (unsigned __int16)v15 | 0x80070000;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
    0x76u,
    L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
    L"CBRAEx",
    L"lr == 0L",
    v5);
  if ( IsDebuggerPresent() )
  {
    v24 = v5;
    v7 = 118;
    v22 = L"lr == 0L";
    goto LABEL_7;
  }
  v8 = 118;
LABEL_9:
  v23 = v5;
  v21 = L"lr == 0L";
LABEL_10:
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
    v8,
    L"CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated",
    L"CBRAEx",
    v21,
    v23);
LABEL_57:
  if ( (unsigned __int64)Handles[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(Handles[1]);
    Handles[1] = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140033ef0  mov     [rsp-28h+arg_0], rbx
0x140033ef5  mov     [rsp-28h+arg_8], rsi
0x140033efa  push    rbp
0x140033efb  push    rdi
0x140033efc  push    r12
0x140033efe  push    r14
0x140033f00  push    r15
0x140033f02  mov     rbp, rsp
0x140033f05  sub     rsp, 50h
0x140033f09  mov     r14, rdx
0x140033f0c  mov     [rbp+hKey], 0
0x140033f14  mov     rsi, rcx
0x140033f17  mov     [rbp+arg_18], 0
0x140033f1f  xorps   xmm0, xmm0
0x140033f22  lea     rax, [rbp+hKey]
0x140033f26  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Virtual Machine"
0x140033f2d  mov     [rsp+50h+phkResult], rax; phkResult
0x140033f32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140033f39  mov     r9d, 10h; samDesired
0x140033f3f  xor     r8d, r8d; ulOptions
0x140033f42  movups  xmmword ptr [rbp+Handles], xmm0
0x140033f46  call    cs:__imp_RegOpenKeyExW
0x140033f4c  mov     ebx, eax
0x140033f4e  test    eax, eax
0x140033f50  jz      loc_140033FFE
0x140033f56  jle     short loc_140033F61
0x140033f58  movzx   ebx, ax
0x140033f5b  or      ebx, 80070000h
0x140033f61  mov     r12d, 4Fh ; 'O'
0x140033f67  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140033f6e  mov     [rsp+50h+var_28], ebx; int
0x140033f72  lea     r14, aCbraex; "CBRAEx"
0x140033f79  mov     r8, rsi; unsigned __int16 *
0x140033f7c  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140033f83  mov     r9, r14; unsigned __int16 *
0x140033f86  lea     r15, aLr0l; "lr == 0L"
0x140033f8d  mov     rcx, rdi; unsigned __int16 *
0x140033f90  mov     edx, r12d; unsigned int
0x140033f93  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x140033f98  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140033f9d  call    cs:__imp_IsDebuggerPresent
0x140033fa3  test    eax, eax
0x140033fa5  jz      short loc_140033FD6
0x140033fa7  mov     [rsp+50h+var_18], ebx
0x140033fab  mov     r9d, r12d
0x140033fae  mov     [rsp+50h+var_20], r15
0x140033fb3  mov     ecx, 2; unsigned __int8
0x140033fb8  mov     qword ptr [rsp+50h+var_28], r14
0x140033fbd  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140033fc4  mov     r8, rdi
0x140033fc7  mov     [rsp+50h+phkResult], rsi
0x140033fcc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140033fd1  jmp     loc_140034372
0x140033fd6  mov     r8d, r12d
0x140033fd9  mov     dword ptr [rsp+50h+var_20], ebx
0x140033fdd  mov     qword ptr [rsp+50h+var_28], r15
0x140033fe2  mov     r9, rsi
0x140033fe5  mov     [rsp+50h+phkResult], r14
0x140033fea  mov     rdx, rdi
0x140033fed  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140033ff4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140033ff9  jmp     loc_140034372
0x140033ffe  xor     r9d, r9d; lpName
0x140034001  xor     r8d, r8d; bInitialState
0x140034004  xor     ecx, ecx; lpEventAttributes
0x140034006  lea     r15d, [r9+1]
0x14003400a  mov     edx, r15d; bManualReset
0x14003400d  call    cs:__imp_CreateEventW
0x140034013  mov     [rbp+Handles+8], rax
0x140034017  test    rax, rax
0x14003401a  jnz     loc_1400340A7
0x140034020  call    cs:__imp_GetLastError
0x140034026  mov     ebx, eax
0x140034028  test    eax, eax
0x14003402a  jle     short loc_140034035
0x14003402c  movzx   ebx, ax
0x14003402f  or      ebx, 80070000h
0x140034035  mov     eax, 80004005h
0x14003403a  lea     r14, aCbraex; "CBRAEx"
0x140034041  test    ebx, ebx
0x140034043  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003404a  mov     r15d, 52h ; 'R'
0x140034050  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034057  cmovns  ebx, eax
0x14003405a  lea     r12, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x140034061  mov     [rsp+50h+var_28], ebx; int
0x140034065  mov     r9, r14; unsigned __int16 *
0x140034068  mov     r8, rsi; unsigned __int16 *
0x14003406b  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x140034070  mov     edx, r15d; unsigned int
0x140034073  mov     rcx, rdi; unsigned __int16 *
0x140034076  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003407b  call    cs:__imp_IsDebuggerPresent
0x140034081  test    eax, eax
0x140034083  jz      short loc_140034096
0x140034085  mov     [rsp+50h+var_18], ebx
0x140034089  mov     r9d, r15d
0x14003408c  mov     [rsp+50h+var_20], r12
0x140034091  jmp     loc_140033FB3
0x140034096  mov     dword ptr [rsp+50h+var_20], ebx
0x14003409a  mov     qword ptr [rsp+50h+var_28], r12
0x14003409f  mov     r8d, r15d
0x1400340a2  jmp     loc_140033FE2
0x1400340a7  mov     rcx, [rbp+hKey]; hKey
0x1400340ab  mov     r9, rax; hEvent
0x1400340ae  mov     r8d, r15d; dwNotifyFilter
0x1400340b1  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x1400340b6  xor     edx, edx; bWatchSubtree
0x1400340b8  call    cs:__imp_RegNotifyChangeKeyValue
0x1400340be  mov     ebx, eax
0x1400340c0  test    eax, eax
0x1400340c2  jz      short loc_1400340DA
0x1400340c4  jle     short loc_1400340CF
0x1400340c6  movzx   ebx, ax
0x1400340c9  or      ebx, 80070000h
0x1400340cf  mov     r12d, 55h ; 'U'
0x1400340d5  jmp     loc_140033F67
0x1400340da  mov     rax, [rsi+18h]
0x1400340de  lea     rcx, aCupdatevmdomai_6; "CUpdateVmDomainAccountGuestThread::Wait"...
0x1400340e5  xor     edi, edi
0x1400340e7  mov     [rbp+Handles], rax
0x1400340eb  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400340f0  lea     r12d, [rdi+2]
0x1400340f4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400340f8  lea     rdx, [rbp+Handles]; lpHandles
0x1400340fc  xor     r8d, r8d; bWaitAll
0x1400340ff  mov     ecx, r12d; nCount
0x140034102  call    cs:__imp_WaitForMultipleObjects
0x140034108  test    eax, eax
0x14003410a  jz      loc_140034361
0x140034110  cmp     eax, r15d
0x140034113  jnz     loc_1400342E1
0x140034119  lea     rax, [rbp+arg_18]
0x14003411d  mov     r9d, 20019h; samDesired
0x140034123  xor     r8d, r8d; ulOptions
0x140034126  mov     [rsp+50h+phkResult], rax; phkResult
0x14003412b  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x140034132  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140034139  call    cs:__imp_RegOpenKeyExW
0x14003413f  mov     ebx, eax
0x140034141  test    eax, 0FFFFFFFDh
0x140034146  jnz     loc_140034279
0x14003414c  mov     rcx, [rbp+Handles+8]; hEvent
0x140034150  call    cs:__imp_ResetEvent
0x140034156  test    eax, eax
0x140034158  jz      loc_14003420A
0x14003415e  test    ebx, ebx
0x140034160  jnz     short loc_140034173
0x140034162  lea     rcx, aCupdatevmdomai_5; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140034169  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003416e  mov     edi, r15d
0x140034171  jmp     short loc_140034191
0x140034173  mov     r9, [rbp+Handles+8]; hEvent
0x140034177  mov     r8d, r15d; dwNotifyFilter
0x14003417a  mov     rcx, [rbp+hKey]; hKey
0x14003417e  xor     edx, edx; bWatchSubtree
0x140034180  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x140034185  call    cs:__imp_RegNotifyChangeKeyValue
0x14003418b  mov     ebx, eax
0x14003418d  test    eax, eax
0x14003418f  jnz     short loc_14003419E
0x140034191  test    edi, edi
0x140034193  jnz     loc_14003436D
0x140034199  jmp     loc_1400340F4
0x14003419e  jle     short loc_1400341A9
0x1400341a0  movzx   ebx, ax
0x1400341a3  or      ebx, 80070000h
0x1400341a9  lea     r14, aCbraex; "CBRAEx"
0x1400341b0  mov     [rsp+50h+var_28], ebx; int
0x1400341b4  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x1400341bb  mov     r9, r14; unsigned __int16 *
0x1400341be  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400341c5  mov     r8, rsi; unsigned __int16 *
0x1400341c8  lea     r15, aLr0l; "lr == 0L"
0x1400341cf  mov     rcx, rdi; unsigned __int16 *
0x1400341d2  mov     edx, 76h ; 'v'; unsigned int
0x1400341d7  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x1400341dc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400341e1  call    cs:__imp_IsDebuggerPresent
0x1400341e7  test    eax, eax
0x1400341e9  jz      short loc_1400341FF
0x1400341eb  mov     [rsp+50h+var_18], ebx
0x1400341ef  mov     r9d, 76h ; 'v'
0x1400341f5  mov     [rsp+50h+var_20], r15
0x1400341fa  jmp     loc_140034359
0x1400341ff  mov     r8d, 76h ; 'v'
0x140034205  jmp     loc_140033FD9
0x14003420a  call    cs:__imp_GetLastError
0x140034210  mov     ebx, eax
0x140034212  test    eax, eax
0x140034214  jle     short loc_14003421F
0x140034216  movzx   ebx, ax
0x140034219  or      ebx, 80070000h
0x14003421f  mov     eax, 80004005h
0x140034224  lea     r14, aCbraex; "CBRAEx"
0x14003422b  test    ebx, ebx
0x14003422d  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140034234  mov     r15d, 6Bh ; 'k'
0x14003423a  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034241  cmovns  ebx, eax
0x140034244  mov     r9, r14; unsigned __int16 *
0x140034247  lea     rax, aFsuccess; "fSuccess"
0x14003424e  mov     [rsp+50h+var_28], ebx; int
0x140034252  mov     r8, rsi; unsigned __int16 *
0x140034255  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14003425a  mov     edx, r15d; unsigned int
0x14003425d  mov     rcx, rdi; unsigned __int16 *
0x140034260  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140034265  call    cs:__imp_IsDebuggerPresent
0x14003426b  test    eax, eax
0x14003426d  lea     rax, aFsuccess; "fSuccess"
0x140034274  jmp     loc_14003434B
0x140034279  test    ebx, ebx
0x14003427b  jle     short loc_140034286
0x14003427d  movzx   ebx, bx
0x140034280  or      ebx, 80070000h
0x140034286  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14003428d  mov     [rsp+50h+var_28], ebx; int
0x140034291  lea     r14, aCbraex; "CBRAEx"
0x140034298  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14003429d  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x1400342a4  mov     r15d, 68h ; 'h'
0x1400342aa  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400342b1  mov     r9, r14; unsigned __int16 *
0x1400342b4  mov     r8, rsi; unsigned __int16 *
0x1400342b7  mov     edx, r15d; unsigned int
0x1400342ba  mov     rcx, rdi; unsigned __int16 *
0x1400342bd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400342c2  call    cs:__imp_IsDebuggerPresent
0x1400342c8  test    eax, eax
0x1400342ca  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x1400342d1  jnz     short loc_14003434D
0x1400342d3  mov     dword ptr [rsp+50h+var_20], ebx
0x1400342d7  mov     qword ptr [rsp+50h+var_28], rax
0x1400342dc  jmp     loc_14003409F
0x1400342e1  call    cs:__imp_GetLastError
0x1400342e7  mov     ebx, eax
0x1400342e9  test    eax, eax
0x1400342eb  jle     short loc_1400342F6
0x1400342ed  movzx   ebx, ax
0x1400342f0  or      ebx, 80070000h
0x1400342f6  mov     eax, 80004005h
0x1400342fb  lea     r14, aCbraex; "CBRAEx"
0x140034302  test    ebx, ebx
0x140034304  lea     rsi, aCupdatevmdomai; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003430b  mov     r15d, 7Eh ; '~'
0x140034311  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034318  cmovns  ebx, eax
0x14003431b  mov     r9, r14; unsigned __int16 *
0x14003431e  lea     rax, a0; "0"
0x140034325  mov     [rsp+50h+var_28], ebx; int
0x140034329  mov     r8, rsi; unsigned __int16 *
0x14003432c  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x140034331  mov     edx, r15d; unsigned int
0x140034334  mov     rcx, rdi; unsigned __int16 *
0x140034337  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003433c  call    cs:__imp_IsDebuggerPresent
0x140034342  test    eax, eax
0x140034344  lea     rax, a0; "0"
0x14003434b  jz      short loc_1400342D3
0x14003434d  mov     [rsp+50h+var_18], ebx
0x140034351  mov     r9d, r15d
0x140034354  mov     [rsp+50h+var_20], rax
0x140034359  mov     ecx, r12d
0x14003435c  jmp     loc_140033FB8
0x140034361  lea     rcx, aCupdatevmdomai_25; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140034368  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003436d  xor     ebx, ebx
0x14003436f  mov     [r14], edi
0x140034372  mov     rcx, [rbp+Handles+8]; hObject
0x140034376  lea     rax, [rcx-1]
0x14003437a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003437e  ja      short loc_14003438E
0x140034380  call    cs:__imp_CloseHandle
0x140034386  mov     [rbp+Handles+8], 0
0x14003438e  mov     rcx, [rbp+arg_18]; hKey
0x140034392  test    rcx, rcx
0x140034395  jz      short loc_1400343A5
0x140034397  call    cs:__imp_RegCloseKey
0x14003439d  mov     [rbp+arg_18], 0
0x1400343a5  mov     rcx, [rbp+hKey]; hKey
0x1400343a9  test    rcx, rcx
0x1400343ac  jz      short loc_1400343B4
0x1400343ae  call    cs:__imp_RegCloseKey
0x1400343b4  lea     r11, [rsp+50h+var_s0]
0x1400343b9  mov     eax, ebx
0x1400343bb  mov     rbx, [r11+30h]
0x1400343bf  mov     rsi, [r11+38h]
0x1400343c3  mov     rsp, r11
0x1400343c6  pop     r15
0x1400343c8  pop     r14
0x1400343ca  pop     r12
0x1400343cc  pop     rdi
0x1400343cd  pop     rbp
0x1400343ce  retn
```
