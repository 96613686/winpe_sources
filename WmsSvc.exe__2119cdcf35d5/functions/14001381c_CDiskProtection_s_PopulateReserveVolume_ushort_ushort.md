# CDiskProtection::s_PopulateReserveVolume(ushort,ushort)

- ea: `0x14001381c`
- end: `0x140013de5`
- name: `?s_PopulateReserveVolume@CDiskProtection@@KAJGG@Z`
- size: `1481`
- prototype: `__int64 __fastcall(unsigned __int16, WCHAR)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140012eb4`

## callees

- `0x14000ec2c`
- `0x140012b88`
- `0x14001381c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140066898`
- `0x1400690bc`
- `0x1400691bc`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x14001393b`
- `ADVAPI32!RegSetKeyValueW` at `0x1400139f9`
- `ADVAPI32!RegSetKeyValueW` at `0x140013d2b`
- `ADVAPI32!RegSetKeyValueW` at `0x14001393b`
- `ADVAPI32!RegSetKeyValueW` at `0x1400139f9`
- `ADVAPI32!RegSetKeyValueW` at `0x140013d2b`
- `KERNEL32!CreateDirectoryW` at `0x140013a93`
- `KERNEL32!CreateDirectoryW` at `0x140013b3d`
- `KERNEL32!CreateDirectoryW` at `0x140013bfc`
- `KERNEL32!CreateDirectoryW` at `0x140013a93`
- `KERNEL32!CreateDirectoryW` at `0x140013b3d`
- `KERNEL32!CreateDirectoryW` at `0x140013bfc`
- `KERNEL32!GetLastError` at `0x140013a9d`
- `KERNEL32!GetLastError` at `0x140013b47`
- `KERNEL32!GetLastError` at `0x140013c06`
- `KERNEL32!GetLastError` at `0x140013a9d`
- `KERNEL32!GetLastError` at `0x140013b47`
- `KERNEL32!GetLastError` at `0x140013c06`
- `KERNEL32!IsDebuggerPresent` at `0x14001398e`
- `KERNEL32!IsDebuggerPresent` at `0x140013a48`
- `KERNEL32!IsDebuggerPresent` at `0x140013af4`
- `KERNEL32!IsDebuggerPresent` at `0x140013b9e`
- `KERNEL32!IsDebuggerPresent` at `0x140013c5d`
- `KERNEL32!IsDebuggerPresent` at `0x140013d80`
- `KERNEL32!IsDebuggerPresent` at `0x14001398e`
- `KERNEL32!IsDebuggerPresent` at `0x140013a48`
- `KERNEL32!IsDebuggerPresent` at `0x140013af4`
- `KERNEL32!IsDebuggerPresent` at `0x140013b9e`
- `KERNEL32!IsDebuggerPresent` at `0x140013c5d`
- `KERNEL32!IsDebuggerPresent` at `0x140013d80`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_PopulateReserveVolume(unsigned __int16 a1, WCHAR a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  const unsigned __int16 *v6; // r15
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  signed int LastError; // eax
  unsigned int v11; // edx
  signed int v12; // eax
  unsigned int v13; // edx
  signed int v14; // eax
  LSTATUS v15; // eax
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR PathName; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[22]; // [rsp+4Ah] [rbp-B6h]
  WCHAR v21; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+62h] [rbp-9Eh]
  __int128 v23; // [rsp+72h] [rbp-8Eh]
  wchar_t v24; // [rsp+82h] [rbp-7Eh]
  WCHAR Src; // [rsp+88h] [rbp-78h] BYREF
  __int128 v26; // [rsp+8Ah] [rbp-76h]
  __int128 v27; // [rsp+9Ah] [rbp-66h]
  int v28; // [rsp+AAh] [rbp-56h]
  WCHAR Data; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[26]; // [rsp+B2h] [rbp-4Eh]
  WCHAR lpData; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v32; // [rsp+D2h] [rbp-2Eh]
  __int128 v33; // [rsp+E2h] [rbp-1Eh]
  __int64 v34; // [rsp+F2h] [rbp-Eh]

  v28 = *(_DWORD *)L"s";
  v32 = *(_OWORD *)L":\\pagefile.sys 0 0";
  v24 = aXMultipointlog[17];
  v33 = *(_OWORD *)L"le.sys 0 0";
  lpData = a2;
  Data = a2;
  v34 = *(_QWORD *)L" 0";
  PathName = a2;
  *(_OWORD *)v30 = *(_OWORD *)L":\\MEMORY.DMP";
  Src = a2;
  v21 = a2;
  *(_OWORD *)&v30[10] = *(_OWORD *)L"ORY.DMP";
  *(_OWORD *)v20 = *(_OWORD *)L":\\Minidump";
  v18 = 0;
  v17 = 0;
  *(_QWORD *)&v20[14] = *(_QWORD *)L"ump";
  v26 = *(_OWORD *)L":\\MultiPointDumps";
  v27 = *(_OWORD *)L"ointDumps";
  v23 = *(_OWORD *)L"ointLogs";
  v22 = *(_OWORD *)L":\\MultiPointLogs";
  v4 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
         L"DumpFile",
         2u,
         &Data,
         0x1Cu);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x18D8u,
      L"CDiskProtection::s_PopulateReserveVolume",
      L"CBRAEx",
      L"err == 0L",
      v5);
    if ( IsDebuggerPresent() )
    {
      v7 = 6360;
LABEL_6:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v7,
        L"CDiskProtection::s_PopulateReserveVolume",
        L"CBRAEx",
        v6,
        v5);
      return (unsigned int)v5;
    }
    v8 = 6360;
    goto LABEL_57;
  }
  v9 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
         L"MinidumpDir",
         2u,
         &PathName,
         0x18u);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x18E0u,
      L"CDiskProtection::s_PopulateReserveVolume",
      L"CBRAEx",
      L"err == 0L",
      v5);
    if ( IsDebuggerPresent() )
    {
      v7 = 6368;
      goto LABEL_6;
    }
    v8 = 6368;
LABEL_57:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::s_PopulateReserveVolume",
      L"CBRAEx",
      v6,
      v5);
    return (unsigned int)v5;
  }
  v5 = DoesDirectoryExist(&PathName, (enum EObjectPresence *)&v17);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( !v17 && !CreateDirectoryW(&PathName, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    v6 = L"fSuccess";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x18E8u,
      L"CDiskProtection::s_PopulateReserveVolume",
      L"CBRAEx",
      L"fSuccess",
      v5);
    if ( IsDebuggerPresent() )
    {
      v7 = 6376;
      goto LABEL_6;
    }
    v8 = 6376;
    goto LABEL_57;
  }
  v5 = DoesDirectoryExist(&Src, (enum EObjectPresence *)&v17);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( !v17 && !CreateDirectoryW(&Src, 0) )
  {
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    v6 = L"fSuccess";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x18F5u,
      L"CDiskProtection::s_PopulateReserveVolume",
      L"CBRAEx",
      L"fSuccess",
      v5);
    if ( IsDebuggerPresent() )
    {
      v7 = 6389;
      goto LABEL_6;
    }
    v8 = 6389;
    goto LABEL_57;
  }
  v5 = SetWmsDumpDirectory(&Src, v11);
  if ( v5 >= 0 )
  {
    v5 = DoesDirectoryExist(&v21, (enum EObjectPresence *)&v17);
    if ( v5 >= 0 )
    {
      if ( !v17 && !CreateDirectoryW(&v21, 0) )
      {
        v14 = GetLastError();
        v5 = v14;
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
        v6 = L"fSuccess";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0x1905u,
          L"CDiskProtection::s_PopulateReserveVolume",
          L"CBRAEx",
          L"fSuccess",
          v5);
        if ( IsDebuggerPresent() )
        {
          v7 = 6405;
          goto LABEL_6;
        }
        v8 = 6405;
        goto LABEL_57;
      }
      v5 = SetWmsLogsDirectory(&v21, v13);
      if ( v5 >= 0 )
      {
        v5 = CDiskProtection::s_MoveEventLogs(a2);
        if ( v5 >= 0 )
        {
          v5 = CDiskProtection::s_CheckPageFileSetting(a1, L"ExistingPageFiles", &v18);
          if ( v5 >= 0 )
          {
            if ( !v18 )
            {
              v5 = 0;
              DEBUGMSGLEVEL(
                4u,
                L"%s(%d) - %s - Test failed:  %s\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                6425,
                L"CDiskProtection::s_PopulateReserveVolume",
                L"Page file is not active on system volume - OK!");
              return (unsigned int)v5;
            }
            v15 = RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
                    L"PagingFiles",
                    7u,
                    &lpData,
                    0x2Au);
            if ( !v15 )
              return (unsigned int)v5;
            if ( v15 > 0 )
              v5 = (unsigned __int16)v15 | 0x80070000;
            else
              v5 = v15;
            v6 = L"err == 0L";
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1921u,
              L"CDiskProtection::s_PopulateReserveVolume",
              L"CBRAEx",
              L"err == 0L",
              v5);
            if ( IsDebuggerPresent() )
            {
              v7 = 6433;
              goto LABEL_6;
            }
            v8 = 6433;
            goto LABEL_57;
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001381c  mov     [rsp-8+arg_10], rbx
0x140013821  mov     [rsp-8+arg_18], rsi
0x140013826  push    rbp
0x140013827  push    rdi
0x140013828  push    r13
0x14001382a  push    r14
0x14001382c  push    r15
0x14001382e  lea     rbp, [rsp-10h]
0x140013833  sub     rsp, 110h
0x14001383a  mov     rax, cs:__security_cookie
0x140013841  xor     rax, rsp
0x140013844  mov     [rbp+30h+var_30], rax
0x140013848  mov     eax, dword ptr cs:aXMultipointdum+22h; "s"
0x14001384e  lea     r8, ?s_kszRegValueDumpFile@CDiskProtection@@1QBGB; "DumpFile"
0x140013855  movups  xmm0, xmmword ptr cs:aXPagefileSys00+2; ":\\pagefile.sys 0 0"
0x14001385c  mov     [rbp+30h+var_86], eax
0x14001385f  movzx   edi, dx
0x140013862  movups  xmm1, xmmword ptr cs:aXPagefileSys00+12h; "le.sys 0 0"
0x140013869  movzx   eax, word ptr cs:aXMultipointlog+22h; ""
0x140013870  movzx   esi, cx
0x140013873  movups  [rbp+30h+var_5E], xmm0
0x140013877  mov     r13d, 2
0x14001387d  mov     [rbp+30h+var_AE], ax
0x140013881  movsd   xmm0, qword ptr cs:aXPagefileSys00+22h; " 0"
0x140013889  lea     rax, [rbp+30h+Data]
0x14001388d  movups  [rbp+30h+var_4E], xmm1
0x140013891  mov     [rbp+30h+var_60], dx
0x140013895  mov     r14, 0FFFFFFFF80000002h
0x14001389c  movups  xmm1, xmmword ptr cs:aXMemoryDmp+2; ":\\MEMORY.DMP"
0x1400138a3  mov     r9d, r13d; dwType
0x1400138a6  mov     [rbp+30h+Data], dx
0x1400138aa  movsd   [rbp+30h+var_3E], xmm0
0x1400138af  mov     rcx, r14; hKey
0x1400138b2  movups  xmm0, xmmword ptr cs:aXMemoryDmp+0Ch; "ORY.DMP"
0x1400138b9  mov     [rsp+130h+PathName], dx
0x1400138be  movups  xmmword ptr [rbp+30h+var_7E], xmm1
0x1400138c2  mov     [rbp+30h+Src], dx
0x1400138c6  movups  xmm1, xmmword ptr cs:aXMinidump+2; ":\\Minidump"
0x1400138cd  mov     [rsp+130h+var_D0], dx
0x1400138d2  lea     rdx, ?s_kszRegKeyCrashControl@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x1400138d9  movups  xmmword ptr [rbp+30h+var_7E+0Ah], xmm0
0x1400138dd  mov     [rsp+130h+cbData], 1Ch; cbData
0x1400138e5  movsd   xmm0, qword ptr cs:aXMinidump+10h; "ump"
0x1400138ed  movups  xmmword ptr [rsp+130h+var_E6], xmm1
0x1400138f2  mov     [rsp+130h+var_EC], 0
0x1400138fa  movups  xmm1, xmmword ptr cs:aXMultipointdum+2; ":\\MultiPointDumps"
0x140013901  mov     [rsp+130h+var_F0], 0
0x140013909  movsd   qword ptr [rsp+130h+var_E6+0Eh], xmm0
0x14001390f  movups  xmm0, xmmword ptr cs:aXMultipointdum+12h; "ointDumps"
0x140013916  mov     [rsp+130h+lpData], rax; lpData
0x14001391b  movups  [rbp+30h+var_A6], xmm1
0x14001391f  movups  xmm1, xmmword ptr cs:aXMultipointlog+12h; "ointLogs"
0x140013926  movups  [rbp+30h+var_96], xmm0
0x14001392a  movups  xmm0, xmmword ptr cs:aXMultipointlog+2; ":\\MultiPointLogs"
0x140013931  movups  [rsp+130h+var_BE], xmm1
0x140013936  movups  [rsp+130h+var_CE], xmm0
0x14001393b  call    cs:__imp_RegSetKeyValueW
0x140013941  mov     ebx, eax
0x140013943  test    eax, eax
0x140013945  jz      loc_1400139D3
0x14001394b  jle     short loc_140013956
0x14001394d  movzx   ebx, ax
0x140013950  or      ebx, 80070000h
0x140013956  lea     r14, aCbraex; "CBRAEx"
0x14001395d  mov     [rsp+130h+cbData], ebx; int
0x140013961  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013968  mov     r9, r14; unsigned __int16 *
0x14001396b  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013972  mov     r8, rsi; unsigned __int16 *
0x140013975  lea     r15, aErr0l; "err == 0L"
0x14001397c  mov     rcx, rdi; unsigned __int16 *
0x14001397f  mov     edx, 18D8h; unsigned int
0x140013984  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x140013989  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001398e  call    cs:__imp_IsDebuggerPresent
0x140013994  test    eax, eax
0x140013996  jz      short loc_1400139C8
0x140013998  mov     r9d, 18D8h
0x14001399e  mov     [rsp+130h+var_F8], ebx
0x1400139a2  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400139a9  mov     [rsp+130h+var_100], r15
0x1400139ae  mov     r8, rdi
0x1400139b1  mov     qword ptr [rsp+130h+cbData], r14
0x1400139b6  mov     ecx, r13d; unsigned __int8
0x1400139b9  mov     [rsp+130h+lpData], rsi
0x1400139be  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400139c3  jmp     loc_140013DBB
0x1400139c8  mov     r8d, 18D8h
0x1400139ce  jmp     loc_140013D9B
0x1400139d3  lea     rax, [rsp+130h+PathName]
0x1400139d8  mov     [rsp+130h+cbData], 18h; cbData
0x1400139e0  mov     r9d, r13d; dwType
0x1400139e3  mov     [rsp+130h+lpData], rax; lpData
0x1400139e8  lea     r8, ?s_kszRegValueMiniDumpDir@CDiskProtection@@1QBGB; "MinidumpDir"
0x1400139ef  mov     rcx, r14; hKey
0x1400139f2  lea     rdx, ?s_kszRegKeyCrashControl@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x1400139f9  call    cs:__imp_RegSetKeyValueW
0x1400139ff  mov     ebx, eax
0x140013a01  test    eax, eax
0x140013a03  jz      short loc_140013A68
0x140013a05  jle     short loc_140013A10
0x140013a07  movzx   ebx, ax
0x140013a0a  or      ebx, 80070000h
0x140013a10  lea     r14, aCbraex; "CBRAEx"
0x140013a17  mov     [rsp+130h+cbData], ebx; int
0x140013a1b  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013a22  mov     r9, r14; unsigned __int16 *
0x140013a25  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013a2c  mov     r8, rsi; unsigned __int16 *
0x140013a2f  lea     r15, aErr0l; "err == 0L"
0x140013a36  mov     rcx, rdi; unsigned __int16 *
0x140013a39  mov     edx, 18E0h; unsigned int
0x140013a3e  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x140013a43  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013a48  call    cs:__imp_IsDebuggerPresent
0x140013a4e  test    eax, eax
0x140013a50  jz      short loc_140013A5D
0x140013a52  mov     r9d, 18E0h
0x140013a58  jmp     loc_14001399E
0x140013a5d  mov     r8d, 18E0h
0x140013a63  jmp     loc_140013D9B
0x140013a68  lea     rdx, [rsp+130h+var_F0]; enum EObjectPresence *
0x140013a6d  lea     rcx, [rsp+130h+PathName]; lpSrc
0x140013a72  call    ?DoesDirectoryExist@@YAJPEBGPEAW4EObjectPresence@@@Z; DoesDirectoryExist(ushort const *,EObjectPresence *)
0x140013a77  mov     ebx, eax
0x140013a79  test    eax, eax
0x140013a7b  js      loc_140013DBB
0x140013a81  cmp     [rsp+130h+var_F0], 0
0x140013a86  jnz     loc_140013B14
0x140013a8c  xor     edx, edx; lpSecurityAttributes
0x140013a8e  lea     rcx, [rsp+130h+PathName]; lpPathName
0x140013a93  call    cs:__imp_CreateDirectoryW
0x140013a99  test    eax, eax
0x140013a9b  jnz     short loc_140013B14
0x140013a9d  call    cs:__imp_GetLastError
0x140013aa3  mov     ebx, eax
0x140013aa5  test    eax, eax
0x140013aa7  jle     short loc_140013AB2
0x140013aa9  movzx   ebx, ax
0x140013aac  or      ebx, 80070000h
0x140013ab2  mov     eax, 80004005h
0x140013ab7  lea     r14, aCbraex; "CBRAEx"
0x140013abe  test    ebx, ebx
0x140013ac0  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013ac7  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013ace  mov     r9, r14; unsigned __int16 *
0x140013ad1  cmovns  ebx, eax
0x140013ad4  lea     r15, aFsuccess; "fSuccess"
0x140013adb  mov     [rsp+130h+cbData], ebx; int
0x140013adf  mov     r8, rsi; unsigned __int16 *
0x140013ae2  mov     edx, 18E8h; unsigned int
0x140013ae7  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x140013aec  mov     rcx, rdi; unsigned __int16 *
0x140013aef  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013af4  call    cs:__imp_IsDebuggerPresent
0x140013afa  test    eax, eax
0x140013afc  jz      short loc_140013B09
0x140013afe  mov     r9d, 18E8h
0x140013b04  jmp     loc_14001399E
0x140013b09  mov     r8d, 18E8h
0x140013b0f  jmp     loc_140013D9B
0x140013b14  lea     rdx, [rsp+130h+var_F0]; enum EObjectPresence *
0x140013b19  lea     rcx, [rbp+30h+Src]; lpSrc
0x140013b1d  call    ?DoesDirectoryExist@@YAJPEBGPEAW4EObjectPresence@@@Z; DoesDirectoryExist(ushort const *,EObjectPresence *)
0x140013b22  mov     ebx, eax
0x140013b24  test    eax, eax
0x140013b26  js      loc_140013DBB
0x140013b2c  cmp     [rsp+130h+var_F0], 0
0x140013b31  jnz     loc_140013BBE
0x140013b37  xor     edx, edx; lpSecurityAttributes
0x140013b39  lea     rcx, [rbp+30h+Src]; lpPathName
0x140013b3d  call    cs:__imp_CreateDirectoryW
0x140013b43  test    eax, eax
0x140013b45  jnz     short loc_140013BBE
0x140013b47  call    cs:__imp_GetLastError
0x140013b4d  mov     ebx, eax
0x140013b4f  test    eax, eax
0x140013b51  jle     short loc_140013B5C
0x140013b53  movzx   ebx, ax
0x140013b56  or      ebx, 80070000h
0x140013b5c  mov     eax, 80004005h
0x140013b61  lea     r14, aCbraex; "CBRAEx"
0x140013b68  test    ebx, ebx
0x140013b6a  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013b71  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013b78  mov     r9, r14; unsigned __int16 *
0x140013b7b  cmovns  ebx, eax
0x140013b7e  lea     r15, aFsuccess; "fSuccess"
0x140013b85  mov     [rsp+130h+cbData], ebx; int
0x140013b89  mov     r8, rsi; unsigned __int16 *
0x140013b8c  mov     edx, 18F5h; unsigned int
0x140013b91  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x140013b96  mov     rcx, rdi; unsigned __int16 *
0x140013b99  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013b9e  call    cs:__imp_IsDebuggerPresent
0x140013ba4  test    eax, eax
0x140013ba6  jz      short loc_140013BB3
0x140013ba8  mov     r9d, 18F5h
0x140013bae  jmp     loc_14001399E
0x140013bb3  mov     r8d, 18F5h
0x140013bb9  jmp     loc_140013D9B
0x140013bbe  lea     rcx, [rbp+30h+Src]; lpData
0x140013bc2  call    ?SetWmsDumpDirectory@@YAJPEBGK@Z; SetWmsDumpDirectory(ushort const *,ulong)
0x140013bc7  mov     ebx, eax
0x140013bc9  test    eax, eax
0x140013bcb  js      loc_140013DBB
0x140013bd1  lea     rdx, [rsp+130h+var_F0]; enum EObjectPresence *
0x140013bd6  lea     rcx, [rsp+130h+var_D0]; lpSrc
0x140013bdb  call    ?DoesDirectoryExist@@YAJPEBGPEAW4EObjectPresence@@@Z; DoesDirectoryExist(ushort const *,EObjectPresence *)
0x140013be0  mov     ebx, eax
0x140013be2  test    eax, eax
0x140013be4  js      loc_140013DBB
0x140013bea  cmp     [rsp+130h+var_F0], 0
0x140013bef  jnz     loc_140013C7D
0x140013bf5  xor     edx, edx; lpSecurityAttributes
0x140013bf7  lea     rcx, [rsp+130h+var_D0]; lpPathName
0x140013bfc  call    cs:__imp_CreateDirectoryW
0x140013c02  test    eax, eax
0x140013c04  jnz     short loc_140013C7D
0x140013c06  call    cs:__imp_GetLastError
0x140013c0c  mov     ebx, eax
0x140013c0e  test    eax, eax
0x140013c10  jle     short loc_140013C1B
0x140013c12  movzx   ebx, ax
0x140013c15  or      ebx, 80070000h
0x140013c1b  mov     eax, 80004005h
0x140013c20  lea     r14, aCbraex; "CBRAEx"
0x140013c27  test    ebx, ebx
0x140013c29  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013c30  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013c37  mov     r9, r14; unsigned __int16 *
0x140013c3a  cmovns  ebx, eax
0x140013c3d  lea     r15, aFsuccess; "fSuccess"
0x140013c44  mov     [rsp+130h+cbData], ebx; int
0x140013c48  mov     r8, rsi; unsigned __int16 *
0x140013c4b  mov     edx, 1905h; unsigned int
0x140013c50  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x140013c55  mov     rcx, rdi; unsigned __int16 *
0x140013c58  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013c5d  call    cs:__imp_IsDebuggerPresent
0x140013c63  test    eax, eax
0x140013c65  jz      short loc_140013C72
0x140013c67  mov     r9d, 1905h
0x140013c6d  jmp     loc_14001399E
0x140013c72  mov     r8d, 1905h
0x140013c78  jmp     loc_140013D9B
0x140013c7d  lea     rcx, [rsp+130h+var_D0]; lpData
0x140013c82  call    ?SetWmsLogsDirectory@@YAJPEBGK@Z; SetWmsLogsDirectory(ushort const *,ulong)
0x140013c87  mov     ebx, eax
0x140013c89  test    eax, eax
0x140013c8b  js      loc_140013DBB
0x140013c91  movzx   ecx, di; unsigned __int16
0x140013c94  call    ?s_MoveEventLogs@CDiskProtection@@KAJG@Z; CDiskProtection::s_MoveEventLogs(ushort)
0x140013c99  mov     ebx, eax
0x140013c9b  test    eax, eax
0x140013c9d  js      loc_140013DBB
0x140013ca3  lea     r8, [rsp+130h+var_EC]; int *
0x140013ca8  movzx   ecx, si; unsigned __int16
0x140013cab  lea     rdx, ?s_kszRegValueExistingPageFiles@CDiskProtection@@1QBGB; "ExistingPageFiles"
0x140013cb2  call    ?s_CheckPageFileSetting@CDiskProtection@@KAJGPEBGPEAH@Z; CDiskProtection::s_CheckPageFileSetting(ushort,ushort const *,int *)
0x140013cb7  mov     ebx, eax
0x140013cb9  test    eax, eax
0x140013cbb  js      loc_140013DBB
0x140013cc1  cmp     [rsp+130h+var_EC], 0
0x140013cc6  jnz     short loc_140013D03
0x140013cc8  xor     ebx, ebx
0x140013cca  lea     rax, aPageFileIsNotA; "Page file is not active on system volum"...
0x140013cd1  mov     qword ptr [rsp+130h+cbData], rax
0x140013cd6  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013cdd  mov     r9d, 1919h
0x140013ce3  mov     [rsp+130h+lpData], rsi
0x140013ce8  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013cef  lea     ecx, [rbx+4]; unsigned __int8
0x140013cf2  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140013cf9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140013cfe  jmp     loc_140013DBB
0x140013d03  lea     rax, [rbp+30h+var_60]
0x140013d07  mov     [rsp+130h+cbData], 2Ah ; '*'; cbData
0x140013d0f  mov     r9d, 7; dwType
0x140013d15  mov     [rsp+130h+lpData], rax; lpData
0x140013d1a  lea     r8, ?s_kszRegValuePagingFiles@CDiskProtection@@1QBGB; "PagingFiles"
0x140013d21  mov     rcx, r14; hKey
0x140013d24  lea     rdx, ?s_kszRegKeyMemoryManagement@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x140013d2b  call    cs:__imp_RegSetKeyValueW
0x140013d31  test    eax, eax
0x140013d33  jz      loc_140013DBB
0x140013d39  jg      short loc_140013D3F
0x140013d3b  mov     ebx, eax
0x140013d3d  jmp     short loc_140013D48
0x140013d3f  movzx   ebx, ax
0x140013d42  or      ebx, 80070000h
0x140013d48  lea     r14, aCbraex; "CBRAEx"
0x140013d4f  mov     [rsp+130h+cbData], ebx; int
0x140013d53  lea     rsi, aCdiskprotectio_119; "CDiskProtection::s_PopulateReserveVolum"...
0x140013d5a  mov     r9, r14; unsigned __int16 *
0x140013d5d  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013d64  mov     r8, rsi; unsigned __int16 *
0x140013d67  lea     r15, aErr0l; "err == 0L"
0x140013d6e  mov     rcx, rdi; unsigned __int16 *
0x140013d71  mov     edx, 1921h; unsigned int
  ... truncated ...
```
