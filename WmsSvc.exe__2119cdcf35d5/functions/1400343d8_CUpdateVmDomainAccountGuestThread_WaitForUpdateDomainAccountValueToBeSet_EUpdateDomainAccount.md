# CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet(EUpdateDomainAccount *)

- ea: `0x1400343d8`
- end: `0x1400347e9`
- name: `?WaitForUpdateDomainAccountValueToBeSet@CUpdateVmDomainAccountGuestThread@@IEAAJPEAW4EUpdateDomainAccount@@@Z`
- size: `1041`
- prototype: `__int64 __fastcall(CUpdateVmDomainAccountGuestThread *__hidden this, enum EUpdateDomainAccount *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140033ca0`

## callees

- `0x1400343d8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400675d8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140034427`
- `ADVAPI32!RegOpenKeyExW` at `0x140034427`
- `ADVAPI32!RegCloseKey` at `0x1400347c9`
- `ADVAPI32!RegCloseKey` at `0x1400347c9`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400345a0`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14003465d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400345a0`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14003465d`
- `KERNEL32!CloseHandle` at `0x1400347b2`
- `KERNEL32!CloseHandle` at `0x1400347b2`
- `KERNEL32!ResetEvent` at `0x140034622`
- `KERNEL32!ResetEvent` at `0x140034622`
- `KERNEL32!WaitForMultipleObjects` at `0x1400345f4`
- `KERNEL32!WaitForMultipleObjects` at `0x1400345f4`
- `KERNEL32!CreateEventW` at `0x1400344ee`
- `KERNEL32!CreateEventW` at `0x1400344ee`
- `KERNEL32!GetLastError` at `0x140034501`
- `KERNEL32!GetLastError` at `0x1400346ea`
- `KERNEL32!GetLastError` at `0x14003471c`
- `KERNEL32!GetLastError` at `0x140034501`
- `KERNEL32!GetLastError` at `0x1400346ea`
- `KERNEL32!GetLastError` at `0x14003471c`
- `KERNEL32!IsDebuggerPresent` at `0x14003447e`
- `KERNEL32!IsDebuggerPresent` at `0x14003455c`
- `KERNEL32!IsDebuggerPresent` at `0x1400346b6`
- `KERNEL32!IsDebuggerPresent` at `0x140034777`
- `KERNEL32!IsDebuggerPresent` at `0x14003447e`
- `KERNEL32!IsDebuggerPresent` at `0x14003455c`
- `KERNEL32!IsDebuggerPresent` at `0x1400346b6`
- `KERNEL32!IsDebuggerPresent` at `0x140034777`

## string_xrefs

- `0x14003453b`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x14003445d`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034531`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034692`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034753`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140034448`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet`
- `0x140034524`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet`
- `0x140034685`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet`
- `0x14003474c`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet`
- `0x1400345c6`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Starting wait for %s to be set to 1\n`
- `0x140034795`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Termination event occured\n`
- `0x14003463e`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Continue to wait for %s to be set to 1\n`
- `0x1400346d9`: `CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - %s is set\n`
- `0x1400345cd`: `UpdateDomainAccount`

## pseudocode

```c
__int64 __fastcall CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet(
        HANDLE *this,
        enum EUpdateDomainAccount *a2)
{
  int v2; // edi
  LSTATUS v5; // eax
  signed int UpdateVmDomainAccountValue; // ebx
  unsigned int v7; // r12d
  __int64 v8; // r9
  __int64 v9; // r8
  HANDLE EventW; // rax
  signed int v11; // eax
  unsigned int v12; // r15d
  LSTATUS v13; // eax
  DWORD v14; // eax
  LSTATUS v15; // eax
  signed int LastError; // eax
  const unsigned __int16 *v17; // r13
  signed int v18; // eax
  const unsigned __int16 *v20; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v21; // [rsp+30h] [rbp-20h]
  signed int v22; // [rsp+30h] [rbp-20h]
  signed int v23; // [rsp+38h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  int v25; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  hKey = 0;
  v25 = 0;
  *(_OWORD *)Handles = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x10u, &hKey);
  UpdateVmDomainAccountValue = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      UpdateVmDomainAccountValue = (unsigned __int16)v5 | 0x80070000;
    v7 = 163;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
      v7,
      L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
      L"CBRAEx",
      L"lr == 0L",
      UpdateVmDomainAccountValue);
    if ( IsDebuggerPresent() )
    {
      v23 = UpdateVmDomainAccountValue;
      v8 = v7;
      v21 = L"lr == 0L";
LABEL_7:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        v8,
        L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
        L"CBRAEx",
        v21,
        v23,
        Handles[0]);
      goto LABEL_51;
    }
    v9 = v7;
LABEL_9:
    v22 = UpdateVmDomainAccountValue;
    v20 = L"lr == 0L";
    goto LABEL_10;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Handles[1] = EventW;
  if ( EventW )
  {
    v13 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
    UpdateVmDomainAccountValue = v13;
    if ( !v13 )
    {
      Handles[0] = this[3];
      UpdateVmDomainAccountValue = 0;
      DEBUGMSG(
        L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Starting wait for %s to be set to 1\n",
        L"UpdateDomainAccount");
      while ( 1 )
      {
        v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( !v14 )
        {
          DEBUGMSG(L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Termination event occured\n");
          goto LABEL_50;
        }
        if ( v14 != 1 )
          break;
        UpdateVmDomainAccountValue = GetUpdateVmDomainAccountValue((enum EUpdateDomainAccount *)&v25);
        if ( UpdateVmDomainAccountValue < 0 )
          goto LABEL_51;
        if ( !ResetEvent(Handles[1]) )
        {
          LastError = GetLastError();
          UpdateVmDomainAccountValue = LastError;
          if ( LastError > 0 )
            UpdateVmDomainAccountValue = (unsigned __int16)LastError | 0x80070000;
          v17 = L"fSuccess";
          v12 = 193;
          goto LABEL_45;
        }
        v2 = v25;
        if ( v25 )
        {
          DEBUGMSG(
            L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - %s is set\n",
            L"UpdateDomainAccount");
LABEL_50:
          *(_DWORD *)a2 = v2;
          goto LABEL_51;
        }
        DEBUGMSG(
          L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet - Continue to wait for %s to be set to 1\n",
          L"UpdateDomainAccount");
        v15 = RegNotifyChangeKeyValue(hKey, 1, 4u, Handles[1], 1);
        if ( v15 )
        {
          if ( v15 > 0 )
            UpdateVmDomainAccountValue = (unsigned __int16)v15 | 0x80070000;
          else
            UpdateVmDomainAccountValue = v15;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
            0xC7u,
            L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
            L"CBRAEx",
            L"lr == 0L",
            UpdateVmDomainAccountValue);
          if ( IsDebuggerPresent() )
          {
            v23 = UpdateVmDomainAccountValue;
            v8 = 199;
            v21 = L"lr == 0L";
            goto LABEL_7;
          }
          v9 = 199;
          goto LABEL_9;
        }
      }
      v18 = GetLastError();
      UpdateVmDomainAccountValue = v18;
      if ( v18 > 0 )
        UpdateVmDomainAccountValue = (unsigned __int16)v18 | 0x80070000;
      v17 = L"0";
      v12 = 212;
LABEL_45:
      if ( UpdateVmDomainAccountValue >= 0 )
        UpdateVmDomainAccountValue = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        v12,
        L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
        L"CBRAEx",
        v17,
        UpdateVmDomainAccountValue);
      if ( !IsDebuggerPresent() )
      {
        v22 = UpdateVmDomainAccountValue;
        v20 = v17;
        goto LABEL_19;
      }
      v23 = UpdateVmDomainAccountValue;
      v8 = v12;
      v21 = v17;
      goto LABEL_7;
    }
    if ( v13 > 0 )
      UpdateVmDomainAccountValue = (unsigned __int16)v13 | 0x80070000;
    v7 = 169;
    goto LABEL_5;
  }
  v11 = GetLastError();
  UpdateVmDomainAccountValue = v11;
  if ( v11 > 0 )
    UpdateVmDomainAccountValue = (unsigned __int16)v11 | 0x80070000;
  v12 = 166;
  if ( UpdateVmDomainAccountValue >= 0 )
    UpdateVmDomainAccountValue = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
    0xA6u,
    L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
    L"CBRAEx",
    L"rghEvents[ET_REGISTRY_CHANGE] != 0",
    UpdateVmDomainAccountValue);
  if ( IsDebuggerPresent() )
  {
    v23 = UpdateVmDomainAccountValue;
    v8 = 166;
    v21 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
    goto LABEL_7;
  }
  v22 = UpdateVmDomainAccountValue;
  v20 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
LABEL_19:
  v9 = v12;
LABEL_10:
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
    v9,
    L"CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet",
    L"CBRAEx",
    v20,
    v22);
LABEL_51:
  if ( (unsigned __int64)Handles[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(Handles[1]);
    Handles[1] = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)UpdateVmDomainAccountValue;
}

```

## disassembly

```asm
0x1400343d8  mov     [rsp-38h+arg_0], rbx
0x1400343dd  push    rbp
0x1400343de  push    rsi
0x1400343df  push    rdi
0x1400343e0  push    r12
0x1400343e2  push    r13
0x1400343e4  push    r14
0x1400343e6  push    r15
0x1400343e8  mov     rbp, rsp
0x1400343eb  sub     rsp, 50h
0x1400343ef  xor     edi, edi
0x1400343f1  mov     [rbp+hKey], 0
0x1400343f9  mov     r14, rdx
0x1400343fc  mov     [rbp+arg_10], edi
0x1400343ff  mov     rsi, rcx
0x140034402  lea     rax, [rbp+hKey]
0x140034406  xorps   xmm0, xmm0
0x140034409  mov     [rsp+50h+phkResult], rax; phkResult
0x14003440e  lea     r9d, [rdi+10h]; samDesired
0x140034412  xor     r8d, r8d; ulOptions
0x140034415  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x14003441c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140034423  movups  xmmword ptr [rbp+Handles], xmm0
0x140034427  call    cs:__imp_RegOpenKeyExW
0x14003442d  mov     ebx, eax
0x14003442f  test    eax, eax
0x140034431  jz      loc_1400344DF
0x140034437  jle     short loc_140034442
0x140034439  movzx   ebx, ax
0x14003443c  or      ebx, 80070000h
0x140034442  mov     r12d, 0A3h
0x140034448  lea     rsi, aCupdatevmdomai_2; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003444f  mov     [rsp+50h+var_28], ebx; int
0x140034453  lea     r14, aCbraex; "CBRAEx"
0x14003445a  mov     r8, rsi; unsigned __int16 *
0x14003445d  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034464  mov     r9, r14; unsigned __int16 *
0x140034467  lea     r15, aLr0l; "lr == 0L"
0x14003446e  mov     rcx, rdi; unsigned __int16 *
0x140034471  mov     edx, r12d; unsigned int
0x140034474  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x140034479  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003447e  call    cs:__imp_IsDebuggerPresent
0x140034484  test    eax, eax
0x140034486  jz      short loc_1400344B7
0x140034488  mov     [rsp+50h+var_18], ebx
0x14003448c  mov     r9d, r12d
0x14003448f  mov     [rsp+50h+var_20], r15
0x140034494  mov     ecx, 2; unsigned __int8
0x140034499  mov     qword ptr [rsp+50h+var_28], r14
0x14003449e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400344a5  mov     r8, rdi
0x1400344a8  mov     [rsp+50h+phkResult], rsi
0x1400344ad  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400344b2  jmp     loc_1400347A4
0x1400344b7  mov     r8d, r12d
0x1400344ba  mov     dword ptr [rsp+50h+var_20], ebx
0x1400344be  mov     qword ptr [rsp+50h+var_28], r15
0x1400344c3  mov     r9, rsi
0x1400344c6  mov     [rsp+50h+phkResult], r14
0x1400344cb  mov     rdx, rdi
0x1400344ce  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400344d5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400344da  jmp     loc_1400347A4
0x1400344df  xor     r9d, r9d; lpName
0x1400344e2  xor     r8d, r8d; bInitialState
0x1400344e5  xor     ecx, ecx; lpEventAttributes
0x1400344e7  lea     r15d, [r9+1]
0x1400344eb  mov     edx, r15d; bManualReset
0x1400344ee  call    cs:__imp_CreateEventW
0x1400344f4  mov     [rbp+Handles+8], rax
0x1400344f8  test    rax, rax
0x1400344fb  jnz     loc_140034588
0x140034501  call    cs:__imp_GetLastError
0x140034507  mov     ebx, eax
0x140034509  test    eax, eax
0x14003450b  jle     short loc_140034516
0x14003450d  movzx   ebx, ax
0x140034510  or      ebx, 80070000h
0x140034516  mov     eax, 80004005h
0x14003451b  lea     r14, aCbraex; "CBRAEx"
0x140034522  test    ebx, ebx
0x140034524  lea     rsi, aCupdatevmdomai_2; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003452b  mov     r15d, 0A6h
0x140034531  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034538  cmovns  ebx, eax
0x14003453b  lea     r12, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x140034542  mov     [rsp+50h+var_28], ebx; int
0x140034546  mov     r9, r14; unsigned __int16 *
0x140034549  mov     r8, rsi; unsigned __int16 *
0x14003454c  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x140034551  mov     edx, r15d; unsigned int
0x140034554  mov     rcx, rdi; unsigned __int16 *
0x140034557  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003455c  call    cs:__imp_IsDebuggerPresent
0x140034562  test    eax, eax
0x140034564  jz      short loc_140034577
0x140034566  mov     [rsp+50h+var_18], ebx
0x14003456a  mov     r9d, r15d
0x14003456d  mov     [rsp+50h+var_20], r12
0x140034572  jmp     loc_140034494
0x140034577  mov     dword ptr [rsp+50h+var_20], ebx
0x14003457b  mov     qword ptr [rsp+50h+var_28], r12
0x140034580  mov     r8d, r15d
0x140034583  jmp     loc_1400344C3
0x140034588  mov     rcx, [rbp+hKey]; hKey
0x14003458c  mov     r13d, 4
0x140034592  mov     r8d, r13d; dwNotifyFilter
0x140034595  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x14003459a  mov     r9, rax; hEvent
0x14003459d  mov     edx, r15d; bWatchSubtree
0x1400345a0  call    cs:__imp_RegNotifyChangeKeyValue
0x1400345a6  mov     ebx, eax
0x1400345a8  test    eax, eax
0x1400345aa  jz      short loc_1400345C2
0x1400345ac  jle     short loc_1400345B7
0x1400345ae  movzx   ebx, ax
0x1400345b1  or      ebx, 80070000h
0x1400345b7  mov     r12d, 0A9h
0x1400345bd  jmp     loc_140034448
0x1400345c2  mov     rax, [rsi+18h]
0x1400345c6  lea     rcx, aCupdatevmdomai_12; "CUpdateVmDomainAccountGuestThread::Wait"...
0x1400345cd  lea     rsi, aUpdatedomainac; "UpdateDomainAccount"
0x1400345d4  mov     [rbp+Handles], rax
0x1400345d8  mov     rdx, rsi
0x1400345db  xor     ebx, ebx
0x1400345dd  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400345e2  lea     r12d, [rbx+2]
0x1400345e6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400345ea  lea     rdx, [rbp+Handles]; lpHandles
0x1400345ee  xor     r8d, r8d; bWaitAll
0x1400345f1  mov     ecx, r12d; nCount
0x1400345f4  call    cs:__imp_WaitForMultipleObjects
0x1400345fa  test    eax, eax
0x1400345fc  jz      loc_140034795
0x140034602  cmp     eax, r15d
0x140034605  jnz     loc_14003471C
0x14003460b  lea     rcx, [rbp+arg_10]; enum EUpdateDomainAccount *
0x14003460f  call    ?GetUpdateVmDomainAccountValue@@YAJPEAW4EUpdateDomainAccount@@@Z; GetUpdateVmDomainAccountValue(EUpdateDomainAccount *)
0x140034614  mov     ebx, eax
0x140034616  test    eax, eax
0x140034618  js      loc_1400347A4
0x14003461e  mov     rcx, [rbp+Handles+8]; hEvent
0x140034622  call    cs:__imp_ResetEvent
0x140034628  test    eax, eax
0x14003462a  jz      loc_1400346EA
0x140034630  mov     edi, [rbp+arg_10]
0x140034633  mov     rdx, rsi
0x140034636  test    edi, edi
0x140034638  jnz     loc_1400346D9
0x14003463e  lea     rcx, aCupdatevmdomai_23; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140034645  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003464a  mov     r9, [rbp+Handles+8]; hEvent
0x14003464e  mov     r8d, r13d; dwNotifyFilter
0x140034651  mov     rcx, [rbp+hKey]; hKey
0x140034655  mov     edx, r15d; bWatchSubtree
0x140034658  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x14003465d  call    cs:__imp_RegNotifyChangeKeyValue
0x140034663  test    eax, eax
0x140034665  jz      loc_1400345E6
0x14003466b  jg      short loc_140034671
0x14003466d  mov     ebx, eax
0x14003466f  jmp     short loc_14003467A
0x140034671  movzx   ebx, ax
0x140034674  or      ebx, 80070000h
0x14003467a  lea     r14, aCbraex; "CBRAEx"
0x140034681  mov     [rsp+50h+var_28], ebx; int
0x140034685  lea     rsi, aCupdatevmdomai_2; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003468c  mov     r13d, 0C7h
0x140034692  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140034699  mov     r9, r14; unsigned __int16 *
0x14003469c  lea     r15, aLr0l; "lr == 0L"
0x1400346a3  mov     r8, rsi; unsigned __int16 *
0x1400346a6  mov     edx, r13d; unsigned int
0x1400346a9  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x1400346ae  mov     rcx, rdi; unsigned __int16 *
0x1400346b1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400346b6  call    cs:__imp_IsDebuggerPresent
0x1400346bc  test    eax, eax
0x1400346be  jz      short loc_1400346D1
0x1400346c0  mov     [rsp+50h+var_18], ebx
0x1400346c4  mov     r9d, r13d
0x1400346c7  mov     [rsp+50h+var_20], r15
0x1400346cc  jmp     loc_14003478D
0x1400346d1  mov     r8d, r13d
0x1400346d4  jmp     loc_1400344BA
0x1400346d9  lea     rcx, aCupdatevmdomai_26; "CUpdateVmDomainAccountGuestThread::Wait"...
0x1400346e0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400346e5  jmp     loc_1400347A1
0x1400346ea  call    cs:__imp_GetLastError
0x1400346f0  mov     ebx, eax
0x1400346f2  test    eax, eax
0x1400346f4  jle     short loc_1400346FF
0x1400346f6  movzx   ebx, ax
0x1400346f9  or      ebx, 80070000h
0x1400346ff  lea     r13, aFsuccess; "fSuccess"
0x140034706  mov     r15d, 0C1h
0x14003470c  jmp     short loc_14003473E
0x14003470e  mov     dword ptr [rsp+50h+var_20], ebx
0x140034712  mov     qword ptr [rsp+50h+var_28], r13
0x140034717  jmp     loc_140034580
0x14003471c  call    cs:__imp_GetLastError
0x140034722  mov     ebx, eax
0x140034724  test    eax, eax
0x140034726  jle     short loc_140034731
0x140034728  movzx   ebx, ax
0x14003472b  or      ebx, 80070000h
0x140034731  lea     r13, a0; "0"
0x140034738  mov     r15d, 0D4h
0x14003473e  mov     eax, 80004005h
0x140034743  lea     r14, aCbraex; "CBRAEx"
0x14003474a  test    ebx, ebx
0x14003474c  lea     rsi, aCupdatevmdomai_2; "CUpdateVmDomainAccountGuestThread::Wait"...
0x140034753  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x14003475a  mov     r9, r14; unsigned __int16 *
0x14003475d  cmovns  ebx, eax
0x140034760  mov     r8, rsi; unsigned __int16 *
0x140034763  mov     [rsp+50h+var_28], ebx; int
0x140034767  mov     edx, r15d; unsigned int
0x14003476a  mov     rcx, rdi; unsigned __int16 *
0x14003476d  mov     [rsp+50h+phkResult], r13; unsigned __int16 *
0x140034772  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140034777  call    cs:__imp_IsDebuggerPresent
0x14003477d  test    eax, eax
0x14003477f  jz      short loc_14003470E
0x140034781  mov     [rsp+50h+var_18], ebx
0x140034785  mov     r9d, r15d
0x140034788  mov     [rsp+50h+var_20], r13
0x14003478d  mov     ecx, r12d
0x140034790  jmp     loc_140034499
0x140034795  lea     rcx, aCupdatevmdomai_0; "CUpdateVmDomainAccountGuestThread::Wait"...
0x14003479c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400347a1  mov     [r14], edi
0x1400347a4  mov     rcx, [rbp+Handles+8]; hObject
0x1400347a8  lea     rax, [rcx-1]
0x1400347ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400347b0  ja      short loc_1400347C0
0x1400347b2  call    cs:__imp_CloseHandle
0x1400347b8  mov     [rbp+Handles+8], 0
0x1400347c0  mov     rcx, [rbp+hKey]; hKey
0x1400347c4  test    rcx, rcx
0x1400347c7  jz      short loc_1400347CF
0x1400347c9  call    cs:__imp_RegCloseKey
0x1400347cf  mov     eax, ebx
0x1400347d1  mov     rbx, [rsp+50h+arg_0]
0x1400347d9  add     rsp, 50h
0x1400347dd  pop     r15
0x1400347df  pop     r14
0x1400347e1  pop     r13
0x1400347e3  pop     r12
0x1400347e5  pop     rdi
0x1400347e6  pop     rsi
0x1400347e7  pop     rbp
0x1400347e8  retn
```
