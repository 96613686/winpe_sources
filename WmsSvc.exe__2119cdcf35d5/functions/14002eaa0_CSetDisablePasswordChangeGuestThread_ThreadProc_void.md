# CSetDisablePasswordChangeGuestThread::ThreadProc(void)

- ea: `0x14002eaa0`
- end: `0x14002f14a`
- name: `?ThreadProc@CSetDisablePasswordChangeGuestThread@@MEAAJXZ`
- size: `1706`
- prototype: `__int64 __fastcall(CSetDisablePasswordChangeGuestThread *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1400016b8`
- `0x14002eaa0`
- `0x14002f150`
- `0x14002f784`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`
- `0x140067bf4`
- `0x140067e64`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002eb29`
- `ADVAPI32!RegOpenKeyExW` at `0x14002ec28`
- `ADVAPI32!RegOpenKeyExW` at `0x14002ecd1`
- `ADVAPI32!RegOpenKeyExW` at `0x14002eb29`
- `ADVAPI32!RegOpenKeyExW` at `0x14002ec28`
- `ADVAPI32!RegOpenKeyExW` at `0x14002ecd1`
- `ADVAPI32!RegCloseKey` at `0x14002ecb2`
- `ADVAPI32!RegCloseKey` at `0x14002f11e`
- `ADVAPI32!RegCloseKey` at `0x14002ecb2`
- `ADVAPI32!RegCloseKey` at `0x14002f11e`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002ee4b`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002ef9a`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002ee4b`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002ef9a`
- `KERNEL32!CloseHandle` at `0x14002f10b`
- `KERNEL32!CloseHandle` at `0x14002f10b`
- `KERNEL32!ResetEvent` at `0x14002ef78`
- `KERNEL32!ResetEvent` at `0x14002ef78`
- `KERNEL32!WaitForMultipleObjects` at `0x14002eef4`
- `KERNEL32!WaitForMultipleObjects` at `0x14002eef4`
- `KERNEL32!CreateEventW` at `0x14002edbb`
- `KERNEL32!CreateEventW` at `0x14002edbb`
- `KERNEL32!GetLastError` at `0x14002edca`
- `KERNEL32!GetLastError` at `0x14002ef06`
- `KERNEL32!GetLastError` at `0x14002f083`
- `KERNEL32!GetLastError` at `0x14002edca`
- `KERNEL32!GetLastError` at `0x14002ef06`
- `KERNEL32!GetLastError` at `0x14002f083`
- `KERNEL32!IsDebuggerPresent` at `0x14002eb8b`
- `KERNEL32!IsDebuggerPresent` at `0x14002ec77`
- `KERNEL32!IsDebuggerPresent` at `0x14002ed20`
- `KERNEL32!IsDebuggerPresent` at `0x14002ee24`
- `KERNEL32!IsDebuggerPresent` at `0x14002ee9c`
- `KERNEL32!IsDebuggerPresent` at `0x14002ef60`
- `KERNEL32!IsDebuggerPresent` at `0x14002f051`
- `KERNEL32!IsDebuggerPresent` at `0x14002f0dd`
- `KERNEL32!IsDebuggerPresent` at `0x14002eb8b`
- `KERNEL32!IsDebuggerPresent` at `0x14002ec77`
- `KERNEL32!IsDebuggerPresent` at `0x14002ed20`
- `KERNEL32!IsDebuggerPresent` at `0x14002ee24`
- `KERNEL32!IsDebuggerPresent` at `0x14002ee9c`
- `KERNEL32!IsDebuggerPresent` at `0x14002ef60`
- `KERNEL32!IsDebuggerPresent` at `0x14002f051`
- `KERNEL32!IsDebuggerPresent` at `0x14002f0dd`

## string_xrefs

- `0x14002ee01`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x14002ee2c`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x14002eb73`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002ec54`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002ecfd`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002edf4`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002ee79`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002ef30`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f02e`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f0ad`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002eb66`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002ec4a`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002ecf3`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002edea`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002ee6f`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002ef26`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002f024`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002f0a3`: `CSetDisablePasswordChangeGuestThread::ThreadProc`
- `0x14002eed2`: `CSetDisablePasswordChangeGuestThread::ThreadProc - Start waiting for %s to be changed\n`
- `0x14002f0f1`: `CSetDisablePasswordChangeGuestThread::ThreadProc - Termination event occured\n`
- `0x14002effd`: `CSetDisablePasswordChangeGuestThread::ThreadProc - Continue waiting for %s to be changed\n`

## pseudocode

```c
__int64 __fastcall CSetDisablePasswordChangeGuestThread::ThreadProc(CSetDisablePasswordChangeGuestThread *this)
{
  void *v1; // r12
  signed int v3; // ebx
  LSTATUS v4; // eax
  unsigned int v5; // r15d
  bool v6; // zf
  const unsigned __int16 *v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int StringValue; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  LSTATUS v13; // eax
  DWORD v14; // eax
  signed int v15; // eax
  LSTATUS v16; // eax
  int v17; // eax
  signed int v18; // eax
  void *Block; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-18h] BYREF
  int v22; // [rsp+A8h] [rbp+48h] BYREF
  int v23; // [rsp+B0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+58h] BYREF

  v22 = 0;
  v1 = 0;
  v23 = 0;
  *(_OWORD *)Handles = 0;
  hKey = 0;
  Block = 0;
  if ( !(unsigned int)IsWmsVirtualMachine() )
    goto LABEL_2;
  v3 = IsLocalMachineDomainJoined(&v22);
  if ( v3 < 0 )
    goto LABEL_77;
  if ( !v22 )
    goto LABEL_2;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
  v3 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      v5 = 210;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        0xD2u,
        L"CSetDisablePasswordChangeGuestThread::ThreadProc",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v3);
      v6 = !IsDebuggerPresent();
      v7 = L"lr == 0L || lr == 2L";
LABEL_10:
      if ( v6 )
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
          v5,
          L"CSetDisablePasswordChangeGuestThread::ThreadProc",
          L"CBRAEx",
          v7,
          v3);
      else
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
          v5,
          L"CSetDisablePasswordChangeGuestThread::ThreadProc",
          L"CBRAEx",
          v7,
          v3);
      goto LABEL_77;
    }
    v3 = CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated(this, &v23);
    if ( v3 < 0 )
      goto LABEL_77;
    if ( v23 )
    {
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
      v3 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v3 = (unsigned __int16)v8 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
          0xDBu,
          L"CSetDisablePasswordChangeGuestThread::ThreadProc",
          L"CBRAEx",
          L"lr == 0L",
          v3);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
            219,
            L"CSetDisablePasswordChangeGuestThread::ThreadProc",
            L"CBRAEx",
            L"lr == 0L",
            v3);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
            219,
            L"CSetDisablePasswordChangeGuestThread::ThreadProc",
            L"CBRAEx",
            L"lr == 0L",
            v3);
        goto LABEL_77;
      }
      goto LABEL_23;
    }
LABEL_2:
    v3 = 0;
    goto LABEL_77;
  }
LABEL_23:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
  v3 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0xE1u,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"lr == 0L",
      v3);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        225,
        L"CSetDisablePasswordChangeGuestThread::ThreadProc",
        L"CBRAEx",
        L"lr == 0L",
        v3);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        225,
        L"CSetDisablePasswordChangeGuestThread::ThreadProc",
        L"CBRAEx",
        L"lr == 0L",
        v3);
    goto LABEL_77;
  }
  StringValue = RegUtil::GetStringValue(1, hKey, L"DisablePasswordChange", &Block);
  v1 = Block;
  v3 = StringValue;
  if ( StringValue >= 0 )
  {
    if ( Block )
    {
      if ( *(_WORD *)Block )
      {
        v3 = CSetDisablePasswordChangeGuestThread::s_UpdateDisablePasswordChangeValue(hKey, (wchar_t *)Block);
        if ( v3 < 0 )
          goto LABEL_77;
      }
    }
  }
  else if ( StringValue != -2147024894 )
  {
LABEL_33:
    v3 = -2147467259;
    goto LABEL_77;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Handles[1] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v3 = LastError;
    v5 = 237;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0xEDu,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"rghEvents[ET_REGISTRY_CHANGE] != 0",
      LastError);
    v6 = !IsDebuggerPresent();
    v7 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
    goto LABEL_10;
  }
  v13 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
  if ( v13 )
  {
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    else
      v3 = v13;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0xF0u,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"lr == 0L",
      v3);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        240,
        L"CSetDisablePasswordChangeGuestThread::ThreadProc",
        L"CBRAEx",
        L"lr == 0L",
        v3);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        240,
        L"CSetDisablePasswordChangeGuestThread::ThreadProc",
        L"CBRAEx",
        L"lr == 0L",
        v3);
    goto LABEL_77;
  }
  Handles[0] = *((HANDLE *)this + 3);
  DEBUGMSG(
    L"CSetDisablePasswordChangeGuestThread::ThreadProc - Start waiting for %s to be changed\n",
    L"DisablePasswordChange");
  v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( !v14 )
  {
    DEBUGMSG(L"CSetDisablePasswordChangeGuestThread::ThreadProc - Termination event occured\n");
    goto LABEL_77;
  }
  if ( v14 != 1 )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    if ( v15 >= 0 )
      v15 = -2147467259;
    v3 = v15;
    v5 = 282;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0x11Au,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"0",
      v15);
    v6 = !IsDebuggerPresent();
    v7 = L"0";
    goto LABEL_10;
  }
  if ( !ResetEvent(Handles[1]) )
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    if ( v18 >= 0 )
      v18 = -2147467259;
    v3 = v18;
    v5 = 260;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0x104u,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"fSuccess",
      v18);
    v6 = !IsDebuggerPresent();
    v7 = L"fSuccess";
    goto LABEL_10;
  }
  v16 = RegNotifyChangeKeyValue(hKey, 1, 4u, Handles[1], 1);
  v3 = v16;
  if ( !v16 )
  {
    operator delete(v1);
    Block = 0;
    v17 = RegUtil::GetStringValue(1, hKey, L"DisablePasswordChange", &Block);
    v1 = Block;
    v3 = v17;
    if ( v17 >= 0 )
    {
      if ( Block )
      {
        if ( *(_WORD *)Block )
        {
          v3 = CSetDisablePasswordChangeGuestThread::s_UpdateDisablePasswordChangeValue(hKey, (wchar_t *)Block);
          if ( v3 < 0 )
            goto LABEL_77;
        }
      }
    }
    else if ( v17 != -2147024894 )
    {
      goto LABEL_33;
    }
    DEBUGMSG(
      L"CSetDisablePasswordChangeGuestThread::ThreadProc - Continue waiting for %s to be changed\n",
      L"DisablePasswordChange");
    goto LABEL_77;
  }
  if ( v16 > 0 )
    v3 = (unsigned __int16)v16 | 0x80070000;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
    0x107u,
    L"CSetDisablePasswordChangeGuestThread::ThreadProc",
    L"CBRAEx",
    L"lr == 0L",
    v3);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      263,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"lr == 0L",
      v3);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      263,
      L"CSetDisablePasswordChangeGuestThread::ThreadProc",
      L"CBRAEx",
      L"lr == 0L",
      v3);
LABEL_77:
  if ( (unsigned __int64)Handles[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(Handles[1]);
    Handles[1] = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  operator delete(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002eaa0  mov     [rsp-38h+arg_0], rbx
0x14002eaa5  push    rbp
0x14002eaa6  push    rsi
0x14002eaa7  push    rdi
0x14002eaa8  push    r12
0x14002eaaa  push    r13
0x14002eaac  push    r14
0x14002eaae  push    r15
0x14002eab0  mov     rbp, rsp
0x14002eab3  sub     rsp, 60h
0x14002eab7  xor     r13d, r13d
0x14002eaba  xorps   xmm0, xmm0
0x14002eabd  mov     [rbp+arg_8], r13d
0x14002eac1  mov     r12d, r13d
0x14002eac4  mov     [rbp+arg_10], r13d
0x14002eac8  mov     rdi, rcx
0x14002eacb  movups  xmmword ptr [rbp+Handles], xmm0
0x14002eacf  mov     [rbp+hKey], r13
0x14002ead3  mov     [rbp+Block], r13
0x14002ead7  call    ?IsWmsVirtualMachine@@YAHXZ; IsWmsVirtualMachine(void)
0x14002eadc  test    eax, eax
0x14002eade  jnz     short loc_14002EAE8
0x14002eae0  mov     ebx, r13d
0x14002eae3  jmp     loc_14002F0FD
0x14002eae8  lea     rcx, [rbp+arg_8]; int *
0x14002eaec  call    ?IsLocalMachineDomainJoined@@YAJPEAH@Z; IsLocalMachineDomainJoined(int *)
0x14002eaf1  mov     ebx, eax
0x14002eaf3  test    eax, eax
0x14002eaf5  js      loc_14002F0FD
0x14002eafb  cmp     [rbp+arg_8], r13d
0x14002eaff  jz      short loc_14002EAE0
0x14002eb01  lea     rax, [rbp+hKey]
0x14002eb05  mov     esi, 20019h
0x14002eb0a  lea     r14, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x14002eb11  mov     [rsp+60h+phkResult], rax; phkResult
0x14002eb16  mov     r15, 0FFFFFFFF80000002h
0x14002eb1d  mov     r9d, esi; samDesired
0x14002eb20  mov     rdx, r14; lpSubKey
0x14002eb23  mov     rcx, r15; hKey
0x14002eb26  xor     r8d, r8d; ulOptions
0x14002eb29  call    cs:__imp_RegOpenKeyExW
0x14002eb2f  mov     ebx, eax
0x14002eb31  test    eax, eax
0x14002eb33  jz      loc_14002ECA9
0x14002eb39  cmp     eax, 2
0x14002eb3c  jz      loc_14002EBF3
0x14002eb42  test    eax, eax
0x14002eb44  jle     short loc_14002EB4F
0x14002eb46  movzx   ebx, ax
0x14002eb49  or      ebx, 80070000h
0x14002eb4f  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14002eb56  mov     [rsp+60h+var_38], ebx; int
0x14002eb5a  lea     r14, aCbraex; "CBRAEx"
0x14002eb61  mov     [rsp+60h+phkResult], rax; unsigned __int16 *
0x14002eb66  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002eb6d  mov     r15d, 0D2h
0x14002eb73  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002eb7a  mov     r9, r14; unsigned __int16 *
0x14002eb7d  mov     r8, rsi; unsigned __int16 *
0x14002eb80  mov     edx, r15d; unsigned int
0x14002eb83  mov     rcx, rdi; unsigned __int16 *
0x14002eb86  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002eb8b  call    cs:__imp_IsDebuggerPresent
0x14002eb91  test    eax, eax
0x14002eb93  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14002eb9a  jz      short loc_14002EBCB
0x14002eb9c  mov     [rsp+60h+var_28], ebx
0x14002eba0  mov     r9d, r15d
0x14002eba3  mov     [rsp+60h+var_30], rax
0x14002eba8  mov     qword ptr [rsp+60h+var_38], r14
0x14002ebad  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002ebb4  mov     r8, rdi
0x14002ebb7  mov     [rsp+60h+phkResult], rsi
0x14002ebbc  mov     ecx, 2; unsigned __int8
0x14002ebc1  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002ebc6  jmp     loc_14002F0FD
0x14002ebcb  mov     dword ptr [rsp+60h+var_30], ebx
0x14002ebcf  mov     r8d, r15d
0x14002ebd2  mov     qword ptr [rsp+60h+var_38], rax
0x14002ebd7  mov     r9, rsi
0x14002ebda  mov     [rsp+60h+phkResult], r14
0x14002ebdf  mov     rdx, rdi
0x14002ebe2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002ebe9  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002ebee  jmp     loc_14002F0FD
0x14002ebf3  lea     rdx, [rbp+arg_10]; int *
0x14002ebf7  mov     rcx, rdi; this
0x14002ebfa  call    ?WaitForExternalSubKeyToBeCreated@CSetDisablePasswordChangeGuestThread@@IEAAJPEAH@Z; CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated(int *)
0x14002ebff  mov     ebx, eax
0x14002ec01  test    eax, eax
0x14002ec03  js      loc_14002F0FD
0x14002ec09  cmp     [rbp+arg_10], r13d
0x14002ec0d  jz      loc_14002EAE0
0x14002ec13  lea     rax, [rbp+hKey]
0x14002ec17  mov     r9d, esi; samDesired
0x14002ec1a  xor     r8d, r8d; ulOptions
0x14002ec1d  mov     [rsp+60h+phkResult], rax; phkResult
0x14002ec22  mov     rdx, r14; lpSubKey
0x14002ec25  mov     rcx, r15; hKey
0x14002ec28  call    cs:__imp_RegOpenKeyExW
0x14002ec2e  mov     ebx, eax
0x14002ec30  test    eax, eax
0x14002ec32  jz      short loc_14002ECA9
0x14002ec34  jle     short loc_14002EC3F
0x14002ec36  movzx   ebx, ax
0x14002ec39  or      ebx, 80070000h
0x14002ec3f  lea     r14, aCbraex; "CBRAEx"
0x14002ec46  mov     [rsp+60h+var_38], ebx; int
0x14002ec4a  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002ec51  mov     r9, r14; unsigned __int16 *
0x14002ec54  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002ec5b  mov     r8, rsi; unsigned __int16 *
0x14002ec5e  lea     r15, aLr0l; "lr == 0L"
0x14002ec65  mov     rcx, rdi; unsigned __int16 *
0x14002ec68  mov     edx, 0DBh; unsigned int
0x14002ec6d  mov     [rsp+60h+phkResult], r15; unsigned __int16 *
0x14002ec72  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ec77  call    cs:__imp_IsDebuggerPresent
0x14002ec7d  test    eax, eax
0x14002ec7f  jz      short loc_14002EC95
0x14002ec81  mov     [rsp+60h+var_28], ebx
0x14002ec85  mov     r9d, 0DBh
0x14002ec8b  mov     [rsp+60h+var_30], r15
0x14002ec90  jmp     loc_14002EBA8
0x14002ec95  mov     dword ptr [rsp+60h+var_30], ebx
0x14002ec99  mov     r8d, 0DBh
0x14002ec9f  mov     qword ptr [rsp+60h+var_38], r15
0x14002eca4  jmp     loc_14002EBD7
0x14002eca9  mov     rcx, [rbp+hKey]; hKey
0x14002ecad  test    rcx, rcx
0x14002ecb0  jz      short loc_14002ECBC
0x14002ecb2  call    cs:__imp_RegCloseKey
0x14002ecb8  mov     [rbp+hKey], r13
0x14002ecbc  lea     rax, [rbp+hKey]
0x14002ecc0  mov     r9d, esi; samDesired
0x14002ecc3  xor     r8d, r8d; ulOptions
0x14002ecc6  mov     [rsp+60h+phkResult], rax; phkResult
0x14002eccb  mov     rdx, r14; lpSubKey
0x14002ecce  mov     rcx, r15; hKey
0x14002ecd1  call    cs:__imp_RegOpenKeyExW
0x14002ecd7  mov     ebx, eax
0x14002ecd9  test    eax, eax
0x14002ecdb  jz      short loc_14002ED52
0x14002ecdd  jle     short loc_14002ECE8
0x14002ecdf  movzx   ebx, ax
0x14002ece2  or      ebx, 80070000h
0x14002ece8  lea     r14, aCbraex; "CBRAEx"
0x14002ecef  mov     [rsp+60h+var_38], ebx; int
0x14002ecf3  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002ecfa  mov     r9, r14; unsigned __int16 *
0x14002ecfd  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002ed04  mov     r8, rsi; unsigned __int16 *
0x14002ed07  lea     r15, aLr0l; "lr == 0L"
0x14002ed0e  mov     rcx, rdi; unsigned __int16 *
0x14002ed11  mov     edx, 0E1h; unsigned int
0x14002ed16  mov     [rsp+60h+phkResult], r15; unsigned __int16 *
0x14002ed1b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ed20  call    cs:__imp_IsDebuggerPresent
0x14002ed26  test    eax, eax
0x14002ed28  jz      short loc_14002ED3E
0x14002ed2a  mov     [rsp+60h+var_28], ebx
0x14002ed2e  mov     r9d, 0E1h
0x14002ed34  mov     [rsp+60h+var_30], r15
0x14002ed39  jmp     loc_14002EBA8
0x14002ed3e  mov     dword ptr [rsp+60h+var_30], ebx
0x14002ed42  mov     r8d, 0E1h
0x14002ed48  mov     qword ptr [rsp+60h+var_38], r15
0x14002ed4d  jmp     loc_14002EBD7
0x14002ed52  mov     rdx, [rbp+hKey]
0x14002ed56  lea     r14, aDisablepasswor; "DisablePasswordChange"
0x14002ed5d  mov     esi, 1
0x14002ed62  lea     r9, [rbp+Block]
0x14002ed66  mov     r8, r14
0x14002ed69  mov     ecx, esi
0x14002ed6b  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14002ed70  mov     r12, [rbp+Block]
0x14002ed74  mov     ebx, eax
0x14002ed76  mov     r15d, 80070002h
0x14002ed7c  test    eax, eax
0x14002ed7e  jns     short loc_14002ED8F
0x14002ed80  cmp     eax, r15d
0x14002ed83  jz      short loc_14002EDB1
0x14002ed85  mov     ebx, 80004005h
0x14002ed8a  jmp     loc_14002F0FD
0x14002ed8f  test    r12, r12
0x14002ed92  jz      short loc_14002EDB1
0x14002ed94  cmp     [r12], r13w
0x14002ed99  jz      short loc_14002EDB1
0x14002ed9b  mov     rcx, [rbp+hKey]; hKey
0x14002ed9f  mov     rdx, r12; String
0x14002eda2  call    ?s_UpdateDisablePasswordChangeValue@CSetDisablePasswordChangeGuestThread@@KAJPEAUHKEY__@@PEBG@Z; CSetDisablePasswordChangeGuestThread::s_UpdateDisablePasswordChangeValue(HKEY__ *,ushort const *)
0x14002eda7  mov     ebx, eax
0x14002eda9  test    eax, eax
0x14002edab  js      loc_14002F0FD
0x14002edb1  xor     r9d, r9d; lpName
0x14002edb4  xor     r8d, r8d; bInitialState
0x14002edb7  mov     edx, esi; bManualReset
0x14002edb9  xor     ecx, ecx; lpEventAttributes
0x14002edbb  call    cs:__imp_CreateEventW
0x14002edc1  mov     [rbp+Handles+8], rax
0x14002edc5  test    rax, rax
0x14002edc8  jnz     short loc_14002EE38
0x14002edca  call    cs:__imp_GetLastError
0x14002edd0  test    eax, eax
0x14002edd2  jle     short loc_14002EDDC
0x14002edd4  movzx   eax, ax
0x14002edd7  or      eax, 80070000h
0x14002eddc  test    eax, eax
0x14002edde  lea     r14, aCbraex; "CBRAEx"
0x14002ede5  mov     ebx, 80004005h
0x14002edea  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002edf1  cmovns  eax, ebx
0x14002edf4  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002edfb  mov     [rsp+60h+var_38], eax; int
0x14002edff  mov     ebx, eax
0x14002ee01  lea     rax, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x14002ee08  mov     r15d, 0EDh
0x14002ee0e  mov     r9, r14; unsigned __int16 *
0x14002ee11  mov     [rsp+60h+phkResult], rax; unsigned __int16 *
0x14002ee16  mov     r8, rsi; unsigned __int16 *
0x14002ee19  mov     edx, r15d; unsigned int
0x14002ee1c  mov     rcx, rdi; unsigned __int16 *
0x14002ee1f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ee24  call    cs:__imp_IsDebuggerPresent
0x14002ee2a  test    eax, eax
0x14002ee2c  lea     rax, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x14002ee33  jmp     loc_14002EB9A
0x14002ee38  mov     rcx, [rbp+hKey]; hKey
0x14002ee3c  mov     r9, rax; hEvent
0x14002ee3f  mov     r8d, 4; dwNotifyFilter
0x14002ee45  mov     dword ptr [rsp+60h+phkResult], esi; fAsynchronous
0x14002ee49  mov     edx, esi; bWatchSubtree
0x14002ee4b  call    cs:__imp_RegNotifyChangeKeyValue
0x14002ee51  test    eax, eax
0x14002ee53  jz      short loc_14002EECE
0x14002ee55  jg      short loc_14002EE5B
0x14002ee57  mov     ebx, eax
0x14002ee59  jmp     short loc_14002EE64
0x14002ee5b  movzx   ebx, ax
0x14002ee5e  or      ebx, 80070000h
0x14002ee64  lea     r14, aCbraex; "CBRAEx"
0x14002ee6b  mov     [rsp+60h+var_38], ebx; int
0x14002ee6f  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002ee76  mov     r9, r14; unsigned __int16 *
0x14002ee79  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002ee80  mov     r8, rsi; unsigned __int16 *
0x14002ee83  lea     r15, aLr0l; "lr == 0L"
0x14002ee8a  mov     rcx, rdi; unsigned __int16 *
0x14002ee8d  mov     edx, 0F0h; unsigned int
0x14002ee92  mov     [rsp+60h+phkResult], r15; unsigned __int16 *
0x14002ee97  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ee9c  call    cs:__imp_IsDebuggerPresent
0x14002eea2  test    eax, eax
0x14002eea4  jz      short loc_14002EEBA
0x14002eea6  mov     [rsp+60h+var_28], ebx
0x14002eeaa  mov     r9d, 0F0h
0x14002eeb0  mov     [rsp+60h+var_30], r15
0x14002eeb5  jmp     loc_14002EBA8
0x14002eeba  mov     dword ptr [rsp+60h+var_30], ebx
0x14002eebe  mov     r8d, 0F0h
0x14002eec4  mov     qword ptr [rsp+60h+var_38], r15
0x14002eec9  jmp     loc_14002EBD7
0x14002eece  mov     rax, [rdi+18h]
0x14002eed2  lea     rcx, aCsetdisablepas_9; "CSetDisablePasswordChangeGuestThread::T"...
0x14002eed9  mov     rdx, r14
0x14002eedc  mov     [rbp+Handles], rax
0x14002eee0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002eee5  xor     r8d, r8d; bWaitAll
0x14002eee8  lea     rdx, [rbp+Handles]; lpHandles
0x14002eeec  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14002eef0  lea     ecx, [r8+2]; nCount
0x14002eef4  call    cs:__imp_WaitForMultipleObjects
0x14002eefa  test    eax, eax
0x14002eefc  jz      loc_14002F0F1
0x14002ef02  cmp     eax, esi
0x14002ef04  jz      short loc_14002EF74
0x14002ef06  call    cs:__imp_GetLastError
0x14002ef0c  test    eax, eax
0x14002ef0e  jle     short loc_14002EF18
0x14002ef10  movzx   eax, ax
0x14002ef13  or      eax, 80070000h
0x14002ef18  test    eax, eax
0x14002ef1a  lea     r14, aCbraex; "CBRAEx"
0x14002ef21  mov     ebx, 80004005h
0x14002ef26  lea     rsi, aCsetdisablepas_15; "CSetDisablePasswordChangeGuestThread::T"...
0x14002ef2d  cmovns  eax, ebx
0x14002ef30  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002ef37  mov     [rsp+60h+var_38], eax; int
0x14002ef3b  mov     ebx, eax
0x14002ef3d  lea     rax, a0; "0"
0x14002ef44  mov     r15d, 11Ah
0x14002ef4a  mov     r9, r14; unsigned __int16 *
0x14002ef4d  mov     [rsp+60h+phkResult], rax; unsigned __int16 *
0x14002ef52  mov     r8, rsi; unsigned __int16 *
0x14002ef55  mov     edx, r15d; unsigned int
0x14002ef58  mov     rcx, rdi; unsigned __int16 *
0x14002ef5b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ef60  call    cs:__imp_IsDebuggerPresent
0x14002ef66  test    eax, eax
0x14002ef68  lea     rax, a0; "0"
  ... truncated ...
```
