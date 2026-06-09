# CEventNotificationService::s_CheckRdshLicensing(int *,ulong *)

- ea: `0x140027868`
- end: `0x140027f20`
- name: `?s_CheckRdshLicensing@CEventNotificationService@@KAJPEAHPEAK@Z`
- size: `1720`
- prototype: `__int64 __fastcall(int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14001d920`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140027868`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400278fa`
- `ADVAPI32!RegGetValueW` at `0x1400279ee`
- `ADVAPI32!RegGetValueW` at `0x140027b0c`
- `ADVAPI32!RegGetValueW` at `0x140027bad`
- `ADVAPI32!RegGetValueW` at `0x140027d16`
- `ADVAPI32!RegGetValueW` at `0x1400278fa`
- `ADVAPI32!RegGetValueW` at `0x1400279ee`
- `ADVAPI32!RegGetValueW` at `0x140027b0c`
- `ADVAPI32!RegGetValueW` at `0x140027bad`
- `ADVAPI32!RegGetValueW` at `0x140027d16`
- `KERNEL32!GetComputerNameW` at `0x140027dfa`
- `KERNEL32!GetComputerNameW` at `0x140027dfa`
- `KERNEL32!IsDebuggerPresent` at `0x14002795c`
- `KERNEL32!IsDebuggerPresent` at `0x140027a47`
- `KERNEL32!IsDebuggerPresent` at `0x140027b66`
- `KERNEL32!IsDebuggerPresent` at `0x140027c07`
- `KERNEL32!IsDebuggerPresent` at `0x140027c7b`
- `KERNEL32!IsDebuggerPresent` at `0x140027d74`
- `KERNEL32!IsDebuggerPresent` at `0x140027e42`
- `KERNEL32!IsDebuggerPresent` at `0x140027ee5`
- `KERNEL32!IsDebuggerPresent` at `0x14002795c`
- `KERNEL32!IsDebuggerPresent` at `0x140027a47`
- `KERNEL32!IsDebuggerPresent` at `0x140027b66`
- `KERNEL32!IsDebuggerPresent` at `0x140027c07`
- `KERNEL32!IsDebuggerPresent` at `0x140027c7b`
- `KERNEL32!IsDebuggerPresent` at `0x140027d74`
- `KERNEL32!IsDebuggerPresent` at `0x140027e42`
- `KERNEL32!IsDebuggerPresent` at `0x140027ee5`
- `msvcrt!_wcsnicmp` at `0x140027e94`
- `msvcrt!_wcsnicmp` at `0x140027e94`

## string_xrefs

- `0x14002792f`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027a1a`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027b39`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027bda`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027c49`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027d47`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027e10`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027eb7`: `CEventNotificationService::s_CheckRdshLicensing`
- `0x140027b02`: `SYSTEM\CurrentControlSet\Services\TermService\Parameters\LicenseServers`
- `0x1400279db`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x140027b93`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x140027cfb`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::s_CheckRdshLicensing(int *a1, unsigned int *a2)
{
  int v2; // r12d
  void *v3; // r13
  LSTATUS ValueW; // eax
  signed int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // r8
  int v8; // edi
  LSTATUS v9; // eax
  int v10; // eax
  int v11; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  unsigned __int64 v15; // rdi
  LSTATUS v16; // eax
  unsigned __int64 v17; // rdi
  _WORD *v18; // rax
  unsigned __int64 i; // rsi
  LPDWORD pcbData; // [rsp+30h] [rbp-39h]
  DWORD v21; // [rsp+40h] [rbp-29h] BYREF
  int v22; // [rsp+44h] [rbp-25h]
  int pvData; // [rsp+48h] [rbp-21h] BYREF
  int v24; // [rsp+4Ch] [rbp-1Dh] BYREF
  DWORD nSize; // [rsp+50h] [rbp-19h] BYREF
  int *v26; // [rsp+58h] [rbp-11h]
  unsigned int *v27; // [rsp+60h] [rbp-9h]
  WCHAR Buffer[8]; // [rsp+68h] [rbp-1h] BYREF
  __int128 v29; // [rsp+78h] [rbp+Fh]

  v26 = a1;
  v27 = a2;
  v22 = 0;
  pvData = 0;
  v24 = 0;
  nSize = 16;
  v21 = 4;
  v2 = 5;
  v3 = 0;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Licensing Core",
             L"LicensingMode",
             0x10u,
             0,
             &pvData,
             &v21);
  v5 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x9A1u,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v5);
      if ( IsDebuggerPresent() )
      {
        v6 = 2465;
LABEL_7:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v6,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          v5);
LABEL_59:
        if ( v5 < 0 )
          goto LABEL_26;
        v11 = v22;
        goto LABEL_25;
      }
      v7 = 2465;
      goto LABEL_58;
    }
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( pvData != 5 )
      v2 = pvData;
  }
  v21 = 4;
  v9 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         L"LicensingMode",
         0x10u,
         0,
         &v24,
         &v21);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x9ABu,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v5);
      if ( IsDebuggerPresent() )
      {
        v6 = 2475;
        goto LABEL_7;
      }
      v7 = 2475;
LABEL_58:
      LODWORD(pcbData) = v5;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v7,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        pcbData);
      goto LABEL_59;
    }
    v10 = 0;
  }
  else
  {
    v10 = 1;
    if ( v24 != 5 )
      v2 = v24;
  }
  if ( v8 )
  {
    if ( v10 && pvData != 5 && v24 != 5 && pvData != v24 )
      goto LABEL_24;
  }
  else if ( !v10 )
  {
    goto LABEL_24;
  }
  v21 = 0;
  v13 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermService\\Parameters\\LicenseServers",
          L"LicenseServers",
          0x20u,
          0,
          0,
          &v21);
  v5 = v13;
  if ( !v13 )
    goto LABEL_24;
  if ( v13 != 2 )
  {
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x9BEu,
      L"CEventNotificationService::s_CheckRdshLicensing",
      L"CBRAEx",
      L"lr == 0L || lr == 2L",
      v5);
    if ( IsDebuggerPresent() )
    {
      v6 = 2494;
      goto LABEL_7;
    }
    v7 = 2494;
    goto LABEL_58;
  }
  v21 = 0;
  v14 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          L"LicenseServers",
          2u,
          0,
          0,
          &v21);
  v5 = v14;
  if ( v14 )
  {
    if ( v14 != 2 )
    {
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x9C8u,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v5);
      if ( IsDebuggerPresent() )
      {
        v6 = 2504;
        goto LABEL_7;
      }
      v7 = 2504;
      goto LABEL_58;
    }
    goto LABEL_24;
  }
  v15 = v21;
  v3 = operator new(v21);
  if ( v3 )
  {
    v16 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
            L"LicenseServers",
            2u,
            0,
            v3,
            &v21);
    v5 = v16;
    if ( v16 )
    {
      if ( v16 != 2 )
      {
        if ( v16 > 0 )
          v5 = (unsigned __int16)v16 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0x9D2u,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          v5);
        if ( IsDebuggerPresent() )
        {
          v6 = 2514;
          goto LABEL_7;
        }
        v7 = 2514;
        goto LABEL_58;
      }
      goto LABEL_24;
    }
    v17 = v15 >> 1;
    v18 = v3;
    for ( i = v17; v17; --v17 )
    {
      if ( !*v18 )
        break;
      ++v18;
    }
    v5 = v17 == 0 ? 0x80070057 : 0;
    if ( v17 )
    {
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        if ( i - v17 == nSize && !_wcsnicmp(Buffer, (const wchar_t *)v3, nSize) )
        {
          v11 = 1;
          goto LABEL_25;
        }
LABEL_24:
        v5 = 0;
        v11 = 0;
LABEL_25:
        *v26 = v11;
        *v27 = v2;
        goto LABEL_26;
      }
      v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x9DAu,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CBRA",
        L"fSuccess",
        -2147467259);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2522,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CBRA",
          L"fSuccess",
          -2147467259);
      }
      else
      {
        LODWORD(pcbData) = -2147467259;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2522,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CBRA",
          L"fSuccess",
          pcbData);
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x9D6u,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CHRA",
        L"hr",
        -2147024809);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2518,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CHRA",
          L"hr",
          v17 == 0 ? 0x80070057 : 0);
      }
      else
      {
        LODWORD(pcbData) = v17 == 0 ? 0x80070057 : 0;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2518,
          L"CEventNotificationService::s_CheckRdshLicensing",
          L"CHRA",
          L"hr",
          pcbData);
      }
    }
  }
  else
  {
    v5 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x9D0u,
      L"CEventNotificationService::s_CheckRdshLicensing",
      L"CPR",
      L"pszLicenseServer",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2512,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CPR",
        L"pszLicenseServer",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2512,
        L"CEventNotificationService::s_CheckRdshLicensing",
        L"CPR",
        L"pszLicenseServer",
        pcbData);
    }
  }
LABEL_26:
  operator delete(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140027868  mov     [rsp-8+arg_10], rbx
0x14002786d  push    rbp
0x14002786e  push    rsi
0x14002786f  push    rdi
0x140027870  push    r12
0x140027872  push    r13
0x140027874  push    r14
0x140027876  push    r15
0x140027878  lea     rbp, [rsp-27h]
0x14002787d  sub     rsp, 90h
0x140027884  mov     rax, cs:__security_cookie
0x14002788b  xor     rax, rsp
0x14002788e  mov     [rbp+57h+var_38], rax
0x140027892  xor     r14d, r14d
0x140027895  mov     [rbp+57h+var_68], rcx
0x140027899  xorps   xmm0, xmm0
0x14002789c  mov     [rbp+57h+var_60], rdx
0x1400278a0  lea     rax, [rbp+57h+var_80]
0x1400278a4  mov     [rbp+57h+var_7C], r14d
0x1400278a8  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1400278ad  lea     r8, ?g_kszLicensingMode@@3QBGB; "LicensingMode"
0x1400278b4  lea     esi, [r14+5]
0x1400278b8  mov     [rbp+57h+var_78], r14d
0x1400278bc  lea     ecx, [rsi+0Bh]
0x1400278bf  mov     [rbp+57h+var_74], r14d
0x1400278c3  lea     rax, [rbp+57h+var_78]
0x1400278c7  mov     [rbp+57h+nSize], ecx
0x1400278ca  mov     r9d, ecx; dwFlags
0x1400278cd  mov     [rsp+0C0h+pvData], rax; pvData
0x1400278d2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400278d9  mov     [rbp+57h+var_80], 4
0x1400278e0  lea     rdx, ?g_kszTsLicensingCoreRegKeyPath@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1400278e7  mov     [rsp+0C0h+pdwType], r14; pdwType
0x1400278ec  mov     r12d, esi
0x1400278ef  mov     r13d, r14d
0x1400278f2  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1400278f6  movups  [rbp+57h+var_48], xmm0
0x1400278fa  call    cs:__imp_RegGetValueW
0x140027900  lea     r15d, [r14+2]
0x140027904  mov     ebx, eax
0x140027906  test    eax, eax
0x140027908  jz      loc_1400279A8
0x14002790e  cmp     eax, r15d
0x140027911  jz      loc_1400279A3
0x140027917  test    eax, eax
0x140027919  jle     short loc_140027924
0x14002791b  movzx   ebx, ax
0x14002791e  or      ebx, 80070000h
0x140027924  lea     r15, aCbraex; "CBRAEx"
0x14002792b  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x14002792f  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027936  mov     r9, r15; unsigned __int16 *
0x140027939  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027940  mov     r8, rsi; unsigned __int16 *
0x140027943  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14002794a  mov     rcx, rdi; unsigned __int16 *
0x14002794d  mov     edx, 9A1h; unsigned int
0x140027952  mov     [rsp+0C0h+pdwType], r14; unsigned __int16 *
0x140027957  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002795c  call    cs:__imp_IsDebuggerPresent
0x140027962  test    eax, eax
0x140027964  jz      short loc_140027998
0x140027966  mov     r9d, 9A1h
0x14002796c  mov     [rsp+0C0h+var_88], ebx
0x140027970  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140027977  mov     [rsp+0C0h+pcbData], r14
0x14002797c  mov     r8, rdi
0x14002797f  mov     [rsp+0C0h+pvData], r15
0x140027984  mov     ecx, 2; unsigned __int8
0x140027989  mov     [rsp+0C0h+pdwType], rsi
0x14002798e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140027993  jmp     loc_140027DAF
0x140027998  mov     r8d, 9A1h
0x14002799e  jmp     loc_140027D8F
0x1400279a3  mov     edi, r14d
0x1400279a6  jmp     short loc_1400279B5
0x1400279a8  cmp     [rbp+57h+var_78], esi
0x1400279ab  mov     edi, 1
0x1400279b0  cmovnz  r12d, [rbp+57h+var_78]
0x1400279b5  lea     rax, [rbp+57h+var_80]
0x1400279b9  mov     [rbp+57h+var_80], 4
0x1400279c0  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1400279c5  lea     r8, ?g_kszLicensingMode@@3QBGB; "LicensingMode"
0x1400279cc  lea     rax, [rbp+57h+var_74]
0x1400279d0  mov     r9d, 10h; dwFlags
0x1400279d6  mov     [rsp+0C0h+pvData], rax; pvData
0x1400279db  lea     rdx, ?g_kszTsPoliciesRegKeyPath@@3QBGB; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x1400279e2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400279e9  mov     [rsp+0C0h+pdwType], r14; pdwType
0x1400279ee  call    cs:__imp_RegGetValueW
0x1400279f4  mov     ecx, [rbp+57h+var_74]
0x1400279f7  mov     ebx, eax
0x1400279f9  test    eax, eax
0x1400279fb  jz      short loc_140027A6C
0x1400279fd  cmp     eax, r15d
0x140027a00  jz      short loc_140027A67
0x140027a02  test    eax, eax
0x140027a04  jle     short loc_140027A0F
0x140027a06  movzx   ebx, ax
0x140027a09  or      ebx, 80070000h
0x140027a0f  lea     r15, aCbraex; "CBRAEx"
0x140027a16  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x140027a1a  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027a21  mov     r9, r15; unsigned __int16 *
0x140027a24  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027a2b  mov     r8, rsi; unsigned __int16 *
0x140027a2e  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140027a35  mov     rcx, rdi; unsigned __int16 *
0x140027a38  mov     edx, 9ABh; unsigned int
0x140027a3d  mov     [rsp+0C0h+pdwType], r14; unsigned __int16 *
0x140027a42  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140027a47  call    cs:__imp_IsDebuggerPresent
0x140027a4d  test    eax, eax
0x140027a4f  jz      short loc_140027A5C
0x140027a51  mov     r9d, 9ABh
0x140027a57  jmp     loc_14002796C
0x140027a5c  mov     r8d, 9ABh
0x140027a62  jmp     loc_140027D8F
0x140027a67  mov     eax, r14d
0x140027a6a  jmp     short loc_140027A77
0x140027a6c  cmp     ecx, esi
0x140027a6e  mov     eax, 1
0x140027a73  cmovnz  r12d, ecx
0x140027a77  test    edi, edi
0x140027a79  jnz     short loc_140027AC2
0x140027a7b  test    eax, eax
0x140027a7d  jnz     short loc_140027AD4
0x140027a7f  mov     ebx, r14d
0x140027a82  mov     eax, ebx
0x140027a84  mov     rcx, [rbp+57h+var_68]
0x140027a88  mov     [rcx], eax
0x140027a8a  mov     rax, [rbp+57h+var_60]
0x140027a8e  mov     [rax], r12d
0x140027a91  mov     rcx, r13; Block
0x140027a94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140027a99  mov     eax, ebx
0x140027a9b  mov     rcx, [rbp+57h+var_38]
0x140027a9f  xor     rcx, rsp; StackCookie
0x140027aa2  call    __security_check_cookie
0x140027aa7  mov     rbx, [rsp+0C0h+arg_10]
0x140027aaf  add     rsp, 90h
0x140027ab6  pop     r15
0x140027ab8  pop     r14
0x140027aba  pop     r13
0x140027abc  pop     r12
0x140027abe  pop     rdi
0x140027abf  pop     rsi
0x140027ac0  pop     rbp
0x140027ac1  retn
0x140027ac2  test    eax, eax
0x140027ac4  jz      short loc_140027AD4
0x140027ac6  cmp     [rbp+57h+var_78], esi
0x140027ac9  jz      short loc_140027AD4
0x140027acb  cmp     ecx, esi
0x140027acd  jz      short loc_140027AD4
0x140027acf  cmp     [rbp+57h+var_78], ecx
0x140027ad2  jnz     short loc_140027A7F
0x140027ad4  lea     rax, [rbp+57h+var_80]
0x140027ad8  mov     [rbp+57h+var_80], r14d
0x140027adc  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140027ae1  lea     rsi, ?g_kszLicenseServers@@3QBGB; "LicenseServers"
0x140027ae8  mov     rdi, 0FFFFFFFF80000002h
0x140027aef  mov     [rsp+0C0h+pvData], r14; pvData
0x140027af4  mov     r9d, 20h ; ' '; dwFlags
0x140027afa  mov     [rsp+0C0h+pdwType], r14; pdwType
0x140027aff  mov     r8, rsi; lpValue
0x140027b02  lea     rdx, ?g_kszTsWmiLicenseServersRegKeyPath@@3QBGB; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x140027b09  mov     rcx, rdi; hkey
0x140027b0c  call    cs:__imp_RegGetValueW
0x140027b12  mov     ebx, eax
0x140027b14  test    eax, eax
0x140027b16  jz      loc_140027A7F
0x140027b1c  cmp     eax, r15d
0x140027b1f  jz      short loc_140027B86
0x140027b21  test    eax, eax
0x140027b23  jle     short loc_140027B2E
0x140027b25  movzx   ebx, ax
0x140027b28  or      ebx, 80070000h
0x140027b2e  lea     r15, aCbraex; "CBRAEx"
0x140027b35  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x140027b39  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027b40  mov     r9, r15; unsigned __int16 *
0x140027b43  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027b4a  mov     r8, rsi; unsigned __int16 *
0x140027b4d  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140027b54  mov     rcx, rdi; unsigned __int16 *
0x140027b57  mov     edx, 9BEh; unsigned int
0x140027b5c  mov     [rsp+0C0h+pdwType], r14; unsigned __int16 *
0x140027b61  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140027b66  call    cs:__imp_IsDebuggerPresent
0x140027b6c  test    eax, eax
0x140027b6e  jz      short loc_140027B7B
0x140027b70  mov     r9d, 9BEh
0x140027b76  jmp     loc_14002796C
0x140027b7b  mov     r8d, 9BEh
0x140027b81  jmp     loc_140027D8F
0x140027b86  lea     rax, [rbp+57h+var_80]
0x140027b8a  mov     [rbp+57h+var_80], r14d
0x140027b8e  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140027b93  lea     rdx, ?g_kszTsPoliciesRegKeyPath@@3QBGB; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x140027b9a  mov     [rsp+0C0h+pvData], r14; pvData
0x140027b9f  mov     r9d, r15d; dwFlags
0x140027ba2  mov     r8, rsi; lpValue
0x140027ba5  mov     [rsp+0C0h+pdwType], r14; pdwType
0x140027baa  mov     rcx, rdi; hkey
0x140027bad  call    cs:__imp_RegGetValueW
0x140027bb3  mov     ebx, eax
0x140027bb5  test    eax, eax
0x140027bb7  jz      short loc_140027C27
0x140027bb9  cmp     eax, r15d
0x140027bbc  jz      loc_140027A7F
0x140027bc2  test    eax, eax
0x140027bc4  jle     short loc_140027BCF
0x140027bc6  movzx   ebx, ax
0x140027bc9  or      ebx, 80070000h
0x140027bcf  lea     r15, aCbraex; "CBRAEx"
0x140027bd6  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x140027bda  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027be1  mov     r9, r15; unsigned __int16 *
0x140027be4  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027beb  mov     r8, rsi; unsigned __int16 *
0x140027bee  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140027bf5  mov     rcx, rdi; unsigned __int16 *
0x140027bf8  mov     edx, 9C8h; unsigned int
0x140027bfd  mov     [rsp+0C0h+pdwType], r14; unsigned __int16 *
0x140027c02  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140027c07  call    cs:__imp_IsDebuggerPresent
0x140027c0d  test    eax, eax
0x140027c0f  jz      short loc_140027C1C
0x140027c11  mov     r9d, 9C8h
0x140027c17  jmp     loc_14002796C
0x140027c1c  mov     r8d, 9C8h
0x140027c22  jmp     loc_140027D8F
0x140027c27  mov     edi, [rbp+57h+var_80]
0x140027c2a  mov     ecx, edi; Size
0x140027c2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140027c31  mov     r13, rax
0x140027c34  test    rax, rax
0x140027c37  jnz     loc_140027CEF
0x140027c3d  lea     rax, aPszlicenseserv; "pszLicenseServer"
0x140027c44  mov     ebx, 8007000Eh
0x140027c49  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027c50  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x140027c54  mov     r12d, 9D0h
0x140027c5a  mov     [rsp+0C0h+pdwType], rax; unsigned __int16 *
0x140027c5f  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027c66  mov     r8, rsi; unsigned __int16 *
0x140027c69  mov     edx, r12d; unsigned int
0x140027c6c  lea     r9, aCpr; "CPR"
0x140027c73  mov     rcx, rdi; unsigned __int16 *
0x140027c76  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140027c7b  call    cs:__imp_IsDebuggerPresent
0x140027c81  test    eax, eax
0x140027c83  lea     rax, aPszlicenseserv; "pszLicenseServer"
0x140027c8a  jz      short loc_140027CC0
0x140027c8c  mov     [rsp+0C0h+var_88], ebx
0x140027c90  mov     [rsp+0C0h+pcbData], rax
0x140027c95  lea     rax, aCpr; "CPR"
0x140027c9c  mov     [rsp+0C0h+pvData], rax
0x140027ca1  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140027ca8  mov     r9d, r12d
0x140027cab  mov     [rsp+0C0h+pdwType], rsi
0x140027cb0  mov     r8, rdi
0x140027cb3  mov     ecx, r15d; unsigned __int8
0x140027cb6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140027cbb  jmp     loc_140027A91
0x140027cc0  mov     dword ptr [rsp+0C0h+pcbData], ebx
0x140027cc4  mov     [rsp+0C0h+pvData], rax
0x140027cc9  lea     rax, aCpr; "CPR"
0x140027cd0  mov     r9, rsi
0x140027cd3  mov     [rsp+0C0h+pdwType], rax
0x140027cd8  mov     r8d, r12d
0x140027cdb  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140027ce2  mov     rdx, rdi
0x140027ce5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140027cea  jmp     loc_140027A91
0x140027cef  lea     rax, [rbp+57h+var_80]
0x140027cf3  mov     r9d, r15d; dwFlags
0x140027cf6  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140027cfb  lea     rdx, ?g_kszTsPoliciesRegKeyPath@@3QBGB; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x140027d02  mov     [rsp+0C0h+pvData], r13; pvData
0x140027d07  mov     r8, rsi; lpValue
0x140027d0a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140027d11  mov     [rsp+0C0h+pdwType], r14; pdwType
0x140027d16  call    cs:__imp_RegGetValueW
0x140027d1c  mov     ebx, eax
0x140027d1e  test    eax, eax
0x140027d20  jz      loc_140027DBF
0x140027d26  cmp     eax, r15d
0x140027d29  jz      loc_140027A7F
0x140027d2f  test    eax, eax
0x140027d31  jle     short loc_140027D3C
0x140027d33  movzx   ebx, ax
0x140027d36  or      ebx, 80070000h
0x140027d3c  lea     r15, aCbraex; "CBRAEx"
0x140027d43  mov     dword ptr [rsp+0C0h+pvData], ebx; int
0x140027d47  lea     rsi, aCeventnotifica_103; "CEventNotificationService::s_CheckRdshL"...
0x140027d4e  mov     r9, r15; unsigned __int16 *
0x140027d51  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140027d58  mov     r8, rsi; unsigned __int16 *
  ... truncated ...
```
