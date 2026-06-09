# CWmsWebService::IsItTimeToGenerateCert(_FILETIME const *,ulong,int *)

- ea: `0x140049494`
- end: `0x140049829`
- name: `?IsItTimeToGenerateCert@CWmsWebService@@AEAAJPEBU_FILETIME@@KPEAH@Z`
- size: `917`
- prototype: `int(CWmsWebService *__hidden this, const struct _FILETIME *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140046814`
- `0x140047f10`
- `0x14004a590`

## callees

- `0x140049494`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x1400495c7`
- `KERNEL32!FileTimeToSystemTime` at `0x1400496f2`
- `KERNEL32!FileTimeToSystemTime` at `0x14004976c`
- `KERNEL32!FileTimeToSystemTime` at `0x1400495c7`
- `KERNEL32!FileTimeToSystemTime` at `0x1400496f2`
- `KERNEL32!FileTimeToSystemTime` at `0x14004976c`
- `KERNEL32!GetLastError` at `0x1400495d5`
- `KERNEL32!GetLastError` at `0x1400496fc`
- `KERNEL32!GetLastError` at `0x140049776`
- `KERNEL32!GetLastError` at `0x1400495d5`
- `KERNEL32!GetLastError` at `0x1400496fc`
- `KERNEL32!GetLastError` at `0x140049776`
- `KERNEL32!IsDebuggerPresent` at `0x140049529`
- `KERNEL32!IsDebuggerPresent` at `0x140049630`
- `KERNEL32!IsDebuggerPresent` at `0x140049529`
- `KERNEL32!IsDebuggerPresent` at `0x140049630`
- `KERNEL32!CompareFileTime` at `0x1400497dd`
- `KERNEL32!CompareFileTime` at `0x1400497dd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004975e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004975e`

## string_xrefs

- `0x140049511`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140049605`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400494fa`: `CWmsWebService::IsItTimeToGenerateCert`
- `0x1400495f5`: `CWmsWebService::IsItTimeToGenerateCert`
- `0x1400495a9`: `CWmsWebService::IsItTimeToGenerateCert - cCertReplacementWindowDays = %u\n`
- `0x140049684`: `CWmsWebService::IsItTimeToGenerateCert - stCertExpiration = %u-%02u-%02u %02u:%02u:%02u.%03u\n`
- `0x1400496a6`: `CWmsWebService::IsItTimeToGenerateCert - WARNING, m_fCertTimesInMinutes == TRUE!\n`
- `0x140049744`: `CWmsWebService::IsItTimeToGenerateCert - stCertRenewalStartTime = %u-%02u-%02u %02u:%02u:%02u.%03u\n`
- `0x14004979a`: `CWmsWebService::IsItTimeToGenerateCert - stNow = %u-%02u-%02u %02u:%02u:%02u.%03u\n`
- `0x1400497e7`: `CWmsWebService::IsItTimeToGenerateCert - Time is right to create a new SSL cert.\n`
- `0x1400497fb`: `CWmsWebService::IsItTimeToGenerateCert - Time is not yet right to create a new SSL cert.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::IsItTimeToGenerateCert(
        const FILETIME *this,
        const struct _FILETIME *a2,
        unsigned int a3,
        int *a4)
{
  __int64 v4; // r14
  unsigned int v8; // edi
  const unsigned __int16 *v9; // r13
  unsigned int v10; // r15d
  signed int v11; // eax
  unsigned int v12; // r13d
  __int64 v13; // rax
  const FILETIME *v14; // r14
  signed int v15; // eax
  signed int LastError; // eax
  unsigned __int16 *v18; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v19; // [rsp+20h] [rbp-49h]
  int v20[2]; // [rsp+28h] [rbp-41h]
  int v21[2]; // [rsp+28h] [rbp-41h]
  __int64 v22; // [rsp+30h] [rbp-39h]
  __int64 v23; // [rsp+38h] [rbp-31h]
  FILETIME v24; // [rsp+40h] [rbp-29h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-21h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-19h] BYREF
  struct _SYSTEMTIME v27; // [rsp+60h] [rbp-9h] BYREF
  struct _SYSTEMTIME v28; // [rsp+70h] [rbp+7h] BYREF

  v4 = a3;
  SystemTimeAsFileTime = 0;
  SystemTime = 0;
  v27 = 0;
  v28 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = L"pftCertExpiration != 0";
    v10 = 1794;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v9 = L"pfTimeIsRight != 0";
    v10 = 1795;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v10,
      L"CWmsWebService::IsItTimeToGenerateCert",
      L"CBRAEx",
      v9,
      v8);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v10,
        L"CWmsWebService::IsItTimeToGenerateCert",
        L"CBRAEx",
        v9,
        v8);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v10,
        L"CWmsWebService::IsItTimeToGenerateCert",
        L"CBRAEx",
        v9,
        v8);
    return v8;
  }
  DEBUGMSG(L"CWmsWebService::IsItTimeToGenerateCert - cCertReplacementWindowDays = %u\n", a3);
  v24 = *a2;
  if ( FileTimeToSystemTime(a2, &SystemTime) )
  {
    DEBUGMSG(
      L"CWmsWebService::IsItTimeToGenerateCert - stCertExpiration = %u-%02u-%02u %02u:%02u:%02u.%03u\n",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      SystemTime.wHour,
      SystemTime.wMinute,
      SystemTime.wSecond,
      SystemTime.wMilliseconds);
    if ( this[43].dwLowDateTime )
    {
      DEBUGMSG(L"CWmsWebService::IsItTimeToGenerateCert - WARNING, m_fCertTimesInMinutes == TRUE!\n");
      v13 = *(_QWORD *)&v24 - 600000000 * v4;
    }
    else
    {
      v13 = *(_QWORD *)&v24 - 864000000000LL * v4;
    }
    v14 = this + 42;
    this[42] = (const FILETIME)v13;
    if ( FileTimeToSystemTime(this + 42, &v27) )
    {
      LODWORD(v23) = v27.wMilliseconds;
      LODWORD(v22) = v27.wSecond;
      v20[0] = v27.wMinute;
      LODWORD(v18) = v27.wHour;
      DEBUGMSG(
        L"CWmsWebService::IsItTimeToGenerateCert - stCertRenewalStartTime = %u-%02u-%02u %02u:%02u:%02u.%03u\n",
        v27.wYear,
        v27.wMonth,
        v27.wDay,
        v18,
        *(_QWORD *)v20,
        v22,
        v23);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( FileTimeToSystemTime(&SystemTimeAsFileTime, &v28) )
      {
        v8 = 0;
        LODWORD(v23) = v28.wMilliseconds;
        LODWORD(v22) = v28.wSecond;
        v21[0] = v28.wMinute;
        LODWORD(v19) = v28.wHour;
        DEBUGMSG(
          L"CWmsWebService::IsItTimeToGenerateCert - stNow = %u-%02u-%02u %02u:%02u:%02u.%03u\n",
          v28.wYear,
          v28.wMonth,
          v28.wDay,
          v19,
          *(_QWORD *)v21,
          v22,
          v23);
        if ( CompareFileTime(v14, &SystemTimeAsFileTime) > 0 )
        {
          DEBUGMSG(L"CWmsWebService::IsItTimeToGenerateCert - Time is not yet right to create a new SSL cert.\n");
          *a4 = 0;
        }
        else
        {
          DEBUGMSG(L"CWmsWebService::IsItTimeToGenerateCert - Time is right to create a new SSL cert.\n");
          *a4 = 1;
        }
        return v8;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v12 = 1844;
    }
    else
    {
      v15 = GetLastError();
      v8 = v15;
      if ( v15 > 0 )
        v8 = (unsigned __int16)v15 | 0x80070000;
      v12 = 1830;
    }
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    v12 = 1803;
  }
  if ( (v8 & 0x80000000) == 0 )
    v8 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
    v12,
    L"CWmsWebService::IsItTimeToGenerateCert",
    L"CBRAEx",
    L"fSuccess",
    v8);
  if ( IsDebuggerPresent() )
  {
    LODWORD(v23) = v8;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v12,
      L"CWmsWebService::IsItTimeToGenerateCert",
      L"CBRAEx",
      L"fSuccess",
      v23);
  }
  else
  {
    LODWORD(v22) = v8;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v12,
      L"CWmsWebService::IsItTimeToGenerateCert",
      L"CBRAEx",
      L"fSuccess",
      v22);
  }
  return v8;
}

```

## disassembly

```asm
0x140049494  push    rbp
0x140049496  push    rbx
0x140049497  push    rsi
0x140049498  push    rdi
0x140049499  push    r13
0x14004949b  push    r14
0x14004949d  push    r15
0x14004949f  lea     rbp, [rsp-27h]
0x1400494a4  sub     rsp, 90h
0x1400494ab  mov     rax, cs:__security_cookie
0x1400494b2  xor     rax, rsp
0x1400494b5  mov     [rbp+57h+var_40], rax
0x1400494b9  mov     r14d, r8d
0x1400494bc  xorps   xmm0, xmm0
0x1400494bf  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1400494c7  xorps   xmm1, xmm1
0x1400494ca  mov     rsi, r9
0x1400494cd  mov     rbx, rdx
0x1400494d0  mov     rdi, rcx
0x1400494d3  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1400494d7  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm1
0x1400494db  movups  xmmword ptr [rbp+57h+var_50.wYear], xmm0
0x1400494df  test    rdx, rdx
0x1400494e2  jnz     loc_14004958A
0x1400494e8  mov     edi, 80070057h
0x1400494ed  lea     r13, aPftcertexpirat; "pftCertExpiration != 0"
0x1400494f4  mov     r15d, 702h
0x1400494fa  lea     rsi, aCwmswebservice_57; "CWmsWebService::IsItTimeToGenerateCert"
0x140049501  mov     [rsp+0C0h+var_98], edi; int
0x140049505  lea     r14, aCbraex; "CBRAEx"
0x14004950c  mov     [rsp+0C0h+var_A0], r13; unsigned __int16 *
0x140049511  lea     rbx, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140049518  mov     r8, rsi; unsigned __int16 *
0x14004951b  mov     r9, r14; unsigned __int16 *
0x14004951e  mov     rcx, rbx; unsigned __int16 *
0x140049521  mov     edx, r15d; unsigned int
0x140049524  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140049529  call    cs:__imp_IsDebuggerPresent
0x14004952f  test    eax, eax
0x140049531  jz      short loc_140049562
0x140049533  mov     dword ptr [rsp+0C0h+var_88], edi
0x140049537  mov     r9d, r15d
0x14004953a  mov     [rsp+0C0h+var_90], r13
0x14004953f  mov     qword ptr [rsp+0C0h+var_98], r14
0x140049544  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004954b  mov     r8, rbx
0x14004954e  mov     [rsp+0C0h+var_A0], rsi
0x140049553  mov     ecx, 2; unsigned __int8
0x140049558  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004955d  jmp     loc_140049809
0x140049562  mov     dword ptr [rsp+0C0h+var_90], edi
0x140049566  mov     r8d, r15d
0x140049569  mov     qword ptr [rsp+0C0h+var_98], r13
0x14004956e  mov     r9, rsi
0x140049571  mov     [rsp+0C0h+var_A0], r14
0x140049576  mov     rdx, rbx
0x140049579  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140049580  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140049585  jmp     loc_140049809
0x14004958a  test    rsi, rsi
0x14004958d  jnz     short loc_1400495A6
0x14004958f  mov     edi, 80004003h
0x140049594  lea     r13, aPftimeisright0; "pfTimeIsRight != 0"
0x14004959b  mov     r15d, 703h
0x1400495a1  jmp     loc_1400494FA
0x1400495a6  mov     edx, r14d
0x1400495a9  lea     rcx, aCwmswebservice_84; "CWmsWebService::IsItTimeToGenerateCert "...
0x1400495b0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400495b5  mov     eax, [rbx]
0x1400495b7  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1400495bb  mov     dword ptr [rbp+57h+var_80], eax
0x1400495be  mov     rcx, rbx; lpFileTime
0x1400495c1  mov     eax, [rbx+4]
0x1400495c4  mov     dword ptr [rbp+57h+var_80+4], eax
0x1400495c7  call    cs:__imp_FileTimeToSystemTime
0x1400495cd  test    eax, eax
0x1400495cf  jnz     loc_14004965C
0x1400495d5  call    cs:__imp_GetLastError
0x1400495db  mov     edi, eax
0x1400495dd  test    eax, eax
0x1400495df  jle     short loc_1400495EA
0x1400495e1  movzx   edi, ax
0x1400495e4  or      edi, 80070000h
0x1400495ea  mov     r13d, 70Bh
0x1400495f0  mov     eax, 80004005h
0x1400495f5  lea     rsi, aCwmswebservice_57; "CWmsWebService::IsItTimeToGenerateCert"
0x1400495fc  test    edi, edi
0x1400495fe  lea     r14, aCbraex; "CBRAEx"
0x140049605  lea     rbx, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004960c  mov     r8, rsi; unsigned __int16 *
0x14004960f  cmovns  edi, eax
0x140049612  lea     r15, aFsuccess; "fSuccess"
0x140049619  mov     [rsp+0C0h+var_98], edi; int
0x14004961d  mov     r9, r14; unsigned __int16 *
0x140049620  mov     edx, r13d; unsigned int
0x140049623  mov     [rsp+0C0h+var_A0], r15; unsigned __int16 *
0x140049628  mov     rcx, rbx; unsigned __int16 *
0x14004962b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140049630  call    cs:__imp_IsDebuggerPresent
0x140049636  test    eax, eax
0x140049638  jz      short loc_14004964B
0x14004963a  mov     dword ptr [rsp+0C0h+var_88], edi
0x14004963e  mov     r9d, r13d
0x140049641  mov     [rsp+0C0h+var_90], r15
0x140049646  jmp     loc_14004953F
0x14004964b  mov     dword ptr [rsp+0C0h+var_90], edi
0x14004964f  mov     r8d, r13d
0x140049652  mov     qword ptr [rsp+0C0h+var_98], r15
0x140049657  jmp     loc_14004956E
0x14004965c  movzx   ecx, [rbp+57h+SystemTime.wSecond]
0x140049660  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x140049664  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x140049669  movzx   r11d, [rbp+57h+SystemTime.wHour]
0x14004966e  movzx   r9d, [rbp+57h+SystemTime.wDay]
0x140049673  movzx   r8d, [rbp+57h+SystemTime.wMonth]
0x140049678  movzx   edx, [rbp+57h+SystemTime.wYear]
0x14004967c  mov     dword ptr [rsp+0C0h+var_88], eax
0x140049680  mov     dword ptr [rsp+0C0h+var_90], ecx
0x140049684  lea     rcx, aCwmswebservice_115; "CWmsWebService::IsItTimeToGenerateCert "...
0x14004968b  mov     [rsp+0C0h+var_98], r10d
0x140049690  mov     dword ptr [rsp+0C0h+var_A0], r11d
0x140049695  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004969a  cmp     dword ptr [rdi+158h], 0
0x1400496a1  mov     rbx, r14
0x1400496a4  jz      short loc_1400496C2
0x1400496a6  lea     rcx, aCwmswebservice_91; "CWmsWebService::IsItTimeToGenerateCert "...
0x1400496ad  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400496b2  mov     rax, [rbp+57h+var_80]
0x1400496b6  imul    rcx, rbx, 23C34600h
0x1400496bd  sub     rax, rcx
0x1400496c0  jmp     short loc_1400496D7
0x1400496c2  mov     rax, 0C92A69C000h
0x1400496cc  imul    rbx, rax
0x1400496d0  mov     rax, [rbp+57h+var_80]
0x1400496d4  sub     rax, rbx
0x1400496d7  lea     r14, [rdi+150h]
0x1400496de  mov     [r14], eax
0x1400496e1  lea     rdx, [rbp+57h+var_60]; lpSystemTime
0x1400496e5  shr     rax, 20h
0x1400496e9  mov     rcx, r14; lpFileTime
0x1400496ec  mov     [rdi+154h], eax
0x1400496f2  call    cs:__imp_FileTimeToSystemTime
0x1400496f8  test    eax, eax
0x1400496fa  jnz     short loc_14004971C
0x1400496fc  call    cs:__imp_GetLastError
0x140049702  mov     edi, eax
0x140049704  test    eax, eax
0x140049706  jle     short loc_140049711
0x140049708  movzx   edi, ax
0x14004970b  or      edi, 80070000h
0x140049711  mov     r13d, 726h
0x140049717  jmp     loc_1400495F0
0x14004971c  movzx   ecx, [rbp+57h+var_60.wSecond]
0x140049720  movzx   eax, [rbp+57h+var_60.wMilliseconds]
0x140049724  movzx   r10d, [rbp+57h+var_60.wMinute]
0x140049729  movzx   r11d, [rbp+57h+var_60.wHour]
0x14004972e  movzx   r9d, [rbp+57h+var_60.wDay]
0x140049733  movzx   r8d, [rbp+57h+var_60.wMonth]
0x140049738  movzx   edx, [rbp+57h+var_60.wYear]
0x14004973c  mov     dword ptr [rsp+0C0h+var_88], eax
0x140049740  mov     dword ptr [rsp+0C0h+var_90], ecx
0x140049744  lea     rcx, aCwmswebservice_18; "CWmsWebService::IsItTimeToGenerateCert "...
0x14004974b  mov     [rsp+0C0h+var_98], r10d
0x140049750  mov     dword ptr [rsp+0C0h+var_A0], r11d
0x140049755  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004975a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14004975e  call    cs:__imp_GetSystemTimeAsFileTime
0x140049764  lea     rdx, [rbp+57h+var_50]; lpSystemTime
0x140049768  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime
0x14004976c  call    cs:__imp_FileTimeToSystemTime
0x140049772  test    eax, eax
0x140049774  jnz     short loc_140049796
0x140049776  call    cs:__imp_GetLastError
0x14004977c  mov     edi, eax
0x14004977e  test    eax, eax
0x140049780  jle     short loc_14004978B
0x140049782  movzx   edi, ax
0x140049785  or      edi, 80070000h
0x14004978b  mov     r13d, 734h
0x140049791  jmp     loc_1400495F0
0x140049796  movzx   eax, [rbp+57h+var_50.wMilliseconds]
0x14004979a  lea     rcx, aCwmswebservice_3; "CWmsWebService::IsItTimeToGenerateCert "...
0x1400497a1  movzx   r10d, [rbp+57h+var_50.wSecond]
0x1400497a6  xor     edi, edi
0x1400497a8  movzx   r11d, [rbp+57h+var_50.wMinute]
0x1400497ad  movzx   ebx, [rbp+57h+var_50.wHour]
0x1400497b1  movzx   r9d, [rbp+57h+var_50.wDay]
0x1400497b6  movzx   r8d, [rbp+57h+var_50.wMonth]
0x1400497bb  movzx   edx, [rbp+57h+var_50.wYear]
0x1400497bf  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400497c3  mov     dword ptr [rsp+0C0h+var_90], r10d
0x1400497c8  mov     [rsp+0C0h+var_98], r11d
0x1400497cd  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1400497d1  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400497d6  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x1400497da  mov     rcx, r14; lpFileTime1
0x1400497dd  call    cs:__imp_CompareFileTime
0x1400497e3  test    eax, eax
0x1400497e5  jg      short loc_1400497FB
0x1400497e7  lea     rcx, aCwmswebservice_121; "CWmsWebService::IsItTimeToGenerateCert "...
0x1400497ee  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400497f3  mov     dword ptr [rsi], 1
0x1400497f9  jmp     short loc_140049809
0x1400497fb  lea     rcx, aCwmswebservice_14; "CWmsWebService::IsItTimeToGenerateCert "...
0x140049802  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140049807  mov     [rsi], edi
0x140049809  mov     eax, edi
0x14004980b  mov     rcx, [rbp+57h+var_40]
0x14004980f  xor     rcx, rsp; StackCookie
0x140049812  call    __security_check_cookie
0x140049817  add     rsp, 90h
0x14004981e  pop     r15
0x140049820  pop     r14
0x140049822  pop     r13
0x140049824  pop     rdi
0x140049825  pop     rsi
0x140049826  pop     rbx
0x140049827  pop     rbp
0x140049828  retn
```
