# CWmsWebService::s_ProcessPendingReplacementCerts(void)

- ea: `0x14004cdb0`
- end: `0x14004d1f8`
- name: `?s_ProcessPendingReplacementCerts@CWmsWebService@@SAJXZ`
- size: `1096`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x140035ec0`
- `0x140048d20`

## callees

- `0x14000aa30`
- `0x140012158`
- `0x14004bcc8`
- `0x14004cdb0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x14004cffe`
- `KERNEL32!FindNextFileW` at `0x14004cffe`
- `KERNEL32!DeleteFileW` at `0x14004cfec`
- `KERNEL32!DeleteFileW` at `0x14004cfec`
- `KERNEL32!GetLastError` at `0x14004cec1`
- `KERNEL32!GetLastError` at `0x14004d008`
- `KERNEL32!GetLastError` at `0x14004d020`
- `KERNEL32!GetLastError` at `0x14004cec1`
- `KERNEL32!GetLastError` at `0x14004d008`
- `KERNEL32!GetLastError` at `0x14004d020`
- `KERNEL32!IsDebuggerPresent` at `0x14004cf2c`
- `KERNEL32!IsDebuggerPresent` at `0x14004d077`
- `KERNEL32!IsDebuggerPresent` at `0x14004d100`
- `KERNEL32!IsDebuggerPresent` at `0x14004d16c`
- `KERNEL32!IsDebuggerPresent` at `0x14004cf2c`
- `KERNEL32!IsDebuggerPresent` at `0x14004d077`
- `KERNEL32!IsDebuggerPresent` at `0x14004d100`
- `KERNEL32!IsDebuggerPresent` at `0x14004d16c`
- `KERNEL32!FindClose` at `0x14004d1cd`
- `KERNEL32!FindClose` at `0x14004d1cd`
- `KERNEL32!FindFirstFileW` at `0x14004cea9`
- `KERNEL32!FindFirstFileW` at `0x14004cea9`

## string_xrefs

- `0x14004cf08`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004d04c`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004d0dc`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004d148`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004ce6a`: `CWmsWebService::s_ProcessPendingReplacementCerts\n`
- `0x14004cefb`: `CWmsWebService::s_ProcessPendingReplacementCerts`
- `0x14004d03f`: `CWmsWebService::s_ProcessPendingReplacementCerts`
- `0x14004d0cf`: `CWmsWebService::s_ProcessPendingReplacementCerts`
- `0x14004d13b`: `CWmsWebService::s_ProcessPendingReplacementCerts`
- `0x14004cfd9`: `CWmsWebService::s_ProcessPendingReplacementCertsFailed to add pending certificate "%s" to the certificate store.\n`

## pseudocode

```c
__int64 CWmsWebService::s_ProcessPendingReplacementCerts(void)
{
  signed int ReserveVolume; // ebx
  unsigned __int64 v1; // rdx
  HANDLE FirstFileW; // r12
  signed int LastError; // eax
  int v4; // eax
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v10; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v11; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v12; // [rsp+30h] [rbp-D0h]
  signed int v13; // [rsp+30h] [rbp-D0h]
  signed int v14; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[20]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v18; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v19; // [rsp+2CAh] [rbp+1CAh]
  __int128 v20; // [rsp+2DAh] [rbp+1DAh]
  int v21; // [rsp+2EAh] [rbp+1EAh]
  WCHAR v22[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v15[0] = 0;
  v19 = *(_OWORD *)L":\\MultiPointData\\";
  v21 = *(_DWORD *)L"\\";
  wcscpy(FileName, L"X:\\MultiPointDaa\\*");
  v20 = *(_OWORD *)L"ointData\\";
  memset_0(v22, 0, 0x208u);
  DEBUGMSG(L"CWmsWebService::s_ProcessPendingReplacementCerts\n");
  ReserveVolume = CDiskProtection::s_GetReserveVolume(v15);
  if ( ReserveVolume < 0 )
    return (unsigned int)ReserveVolume;
  v18 = v15[0];
  FileName[0] = v15[0];
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
    goto LABEL_13;
  LastError = GetLastError();
  ReserveVolume = LastError;
  if ( (unsigned int)(LastError - 2) <= 1 )
  {
    ReserveVolume = 0;
    goto LABEL_44;
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError < 0 )
  {
    if ( ReserveVolume > 0 )
      ReserveVolume = (unsigned __int16)ReserveVolume | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x9B8u,
      L"CWmsWebService::s_ProcessPendingReplacementCerts",
      L"CHRA",
      L"HRESULT_FROM_WIN32 (dwError)",
      ReserveVolume);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2488,
        L"CWmsWebService::s_ProcessPendingReplacementCerts",
        L"CHRA",
        L"HRESULT_FROM_WIN32 (dwError)",
        ReserveVolume);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2488,
        L"CWmsWebService::s_ProcessPendingReplacementCerts",
        L"CHRA",
        L"HRESULT_FROM_WIN32 (dwError)",
        ReserveVolume);
    goto LABEL_44;
  }
  while ( 1 )
  {
LABEL_13:
    v4 = PathCchCombineEx(v22, v1, &v18, FindFileData.cFileName, v10);
    ReserveVolume = v4;
    if ( v4 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x9BFu,
        L"CWmsWebService::s_ProcessPendingReplacementCerts",
        L"CHRA",
        L"hr",
        v4);
      if ( IsDebuggerPresent() )
      {
        v14 = ReserveVolume;
        v7 = 2495;
        v12 = L"hr";
        goto LABEL_39;
      }
      v13 = ReserveVolume;
      v8 = 2495;
      v11 = L"hr";
LABEL_42:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v8,
        L"CWmsWebService::s_ProcessPendingReplacementCerts",
        L"CHRA",
        v11,
        v13);
      goto LABEL_43;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( (int)CWmsWebService::s_AddPendingSerializedCertificateToStore(FindFileData.cFileName, v22) < 0 )
        DEBUGMSG(
          L"CWmsWebService::s_ProcessPendingReplacementCertsFailed to add pending certificate \"%s\" to the certificate store.\n",
          v22);
      if ( !DeleteFileW(v22) )
        break;
    }
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v5 = GetLastError();
      ReserveVolume = v5;
      if ( v5 == 18 )
      {
        ReserveVolume = 0;
        goto LABEL_43;
      }
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 >= 0 )
      {
        ReserveVolume = v5;
        goto LABEL_43;
      }
      if ( ReserveVolume > 0 )
        ReserveVolume = (unsigned __int16)ReserveVolume | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x9D5u,
        L"CWmsWebService::s_ProcessPendingReplacementCerts",
        L"CHRA",
        L"HRESULT_FROM_WIN32 (dwError)",
        ReserveVolume);
      if ( IsDebuggerPresent() )
      {
        v14 = ReserveVolume;
        v7 = 2517;
        v12 = L"HRESULT_FROM_WIN32 (dwError)";
LABEL_39:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          v7,
          L"CWmsWebService::s_ProcessPendingReplacementCerts",
          L"CHRA",
          v12,
          v14);
        goto LABEL_43;
      }
      v13 = ReserveVolume;
      v8 = 2517;
      v11 = L"HRESULT_FROM_WIN32 (dwError)";
      goto LABEL_42;
    }
  }
  v6 = GetLastError();
  ReserveVolume = v6;
  if ( v6 > 0 )
    ReserveVolume = (unsigned __int16)v6 | 0x80070000;
  if ( ReserveVolume >= 0 )
    ReserveVolume = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
    0x9CBu,
    L"CWmsWebService::s_ProcessPendingReplacementCerts",
    L"CBRAEx",
    L"fSuccess",
    ReserveVolume);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      2507,
      L"CWmsWebService::s_ProcessPendingReplacementCerts",
      L"CBRAEx",
      L"fSuccess",
      ReserveVolume);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      2507,
      L"CWmsWebService::s_ProcessPendingReplacementCerts",
      L"CBRAEx",
      L"fSuccess",
      ReserveVolume);
LABEL_43:
  if ( FirstFileW )
LABEL_44:
    FindClose(FirstFileW);
  return (unsigned int)ReserveVolume;
}

```

## disassembly

```asm
0x14004cdb0  push    rbp
0x14004cdb2  push    rbx
0x14004cdb3  push    rsi
0x14004cdb4  push    rdi
0x14004cdb5  push    r12
0x14004cdb7  push    r13
0x14004cdb9  push    r14
0x14004cdbb  push    r15
0x14004cdbd  lea     rbp, [rsp-418h]
0x14004cdc5  sub     rsp, 518h
0x14004cdcc  mov     rax, cs:__security_cookie
0x14004cdd3  xor     rax, rsp
0x14004cdd6  mov     [rbp+450h+var_50], rax
0x14004cddd  xor     edx, edx; Val
0x14004cddf  lea     rcx, [rsp+550h+FindFileData]; void *
0x14004cde4  mov     r8d, 250h; Size
0x14004cdea  call    memset_0
0x14004cdef  movups  xmm0, xmmword ptr cs:aXMultipointdat_0+2; ":\\MultiPointData\\"
0x14004cdf6  xor     eax, eax
0x14004cdf8  xor     edx, edx; Val
0x14004cdfa  movups  xmm1, xmmword ptr cs:aXMultipointdat_0+12h; "ointData\\"
0x14004ce01  mov     [rsp+550h+var_510], ax
0x14004ce06  mov     r8d, 208h; Size
0x14004ce0c  mov     eax, dword ptr cs:aXMultipointdat_0+22h; "\\"
0x14004ce12  lea     rcx, [rbp+450h+var_260]; void *
0x14004ce19  movups  [rbp+450h+var_286], xmm0
0x14004ce20  mov     [rbp+450h+var_266], eax
0x14004ce26  mov     eax, 58h ; 'X'
0x14004ce2b  movups  xmm0, xmmword ptr cs:aXMultipointdat_2+2; ":\\MultiPointData\\*"
0x14004ce32  mov     [rbp+450h+FileName], ax
0x14004ce39  movups  [rbp+450h+var_276], xmm1
0x14004ce40  movups  xmm1, xmmword ptr cs:aXMultipointdat_2+12h; "ointData\\*"
0x14004ce47  movups  [rbp+450h+var_2AE], xmm0
0x14004ce4e  movsd   xmm0, qword ptr cs:aXMultipointdat_2+20h; "a\\*"
0x14004ce56  movups  [rbp+450h+var_29E], xmm1
0x14004ce5d  movsd   qword ptr [rbp+450h+var_29E+0Eh], xmm0
0x14004ce65  call    memset_0
0x14004ce6a  lea     rcx, aCwmswebservice_119; "CWmsWebService::s_ProcessPendingReplace"...
0x14004ce71  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004ce76  lea     rcx, [rsp+550h+var_510]; unsigned __int16 *
0x14004ce7b  call    ?s_GetReserveVolume@CDiskProtection@@SAJPEAG@Z; CDiskProtection::s_GetReserveVolume(ushort *)
0x14004ce80  mov     ebx, eax
0x14004ce82  test    eax, eax
0x14004ce84  js      loc_14004D1D3
0x14004ce8a  movzx   eax, [rsp+550h+var_510]
0x14004ce8f  lea     rdx, [rsp+550h+FindFileData]; lpFindFileData
0x14004ce94  lea     rcx, [rbp+450h+FileName]; lpFileName
0x14004ce9b  mov     [rbp+450h+var_288], ax
0x14004cea2  mov     [rbp+450h+FileName], ax
0x14004cea9  call    cs:__imp_FindFirstFileW
0x14004ceaf  mov     r12, rax
0x14004ceb2  mov     edi, 80070000h
0x14004ceb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004cebb  jnz     loc_14004CF94
0x14004cec1  call    cs:__imp_GetLastError
0x14004cec7  mov     ebx, eax
0x14004cec9  lea     ecx, [rax-2]
0x14004cecc  cmp     ecx, 1
0x14004cecf  jbe     loc_14004CF8D
0x14004ced5  movzx   ecx, bx
0x14004ced8  test    eax, eax
0x14004ceda  jle     short loc_14004CEE0
0x14004cedc  mov     eax, ecx
0x14004cede  or      eax, edi
0x14004cee0  test    eax, eax
0x14004cee2  jns     loc_14004CF94
0x14004cee8  test    ebx, ebx
0x14004ceea  jle     short loc_14004CEF0
0x14004ceec  mov     ebx, ecx
0x14004ceee  or      ebx, edi
0x14004cef0  lea     r14, aChra; "CHRA"
0x14004cef7  mov     [rsp+550h+var_528], ebx; int
0x14004cefb  lea     rsi, aCwmswebservice_53; "CWmsWebService::s_ProcessPendingReplace"...
0x14004cf02  mov     r13d, 9B8h
0x14004cf08  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004cf0f  mov     r9, r14; unsigned __int16 *
0x14004cf12  lea     r15, aHresultFromWin_0; "HRESULT_FROM_WIN32 (dwError)"
0x14004cf19  mov     r8, rsi; unsigned __int16 *
0x14004cf1c  mov     edx, r13d; unsigned int
0x14004cf1f  mov     [rsp+550h+var_530], r15; unsigned __int16 *
0x14004cf24  mov     rcx, rdi; unsigned __int16 *
0x14004cf27  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004cf2c  call    cs:__imp_IsDebuggerPresent
0x14004cf32  test    eax, eax
0x14004cf34  jz      short loc_14004CF65
0x14004cf36  mov     [rsp+550h+var_518], ebx
0x14004cf3a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004cf41  mov     [rsp+550h+var_520], r15
0x14004cf46  mov     r9d, r13d
0x14004cf49  mov     qword ptr [rsp+550h+var_528], r14
0x14004cf4e  mov     r8, rdi
0x14004cf51  mov     ecx, 2; unsigned __int8
0x14004cf56  mov     [rsp+550h+var_530], rsi
0x14004cf5b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004cf60  jmp     loc_14004D1CA
0x14004cf65  mov     dword ptr [rsp+550h+var_520], ebx
0x14004cf69  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004cf70  mov     qword ptr [rsp+550h+var_528], r15
0x14004cf75  mov     r9, rsi
0x14004cf78  mov     r8d, r13d
0x14004cf7b  mov     [rsp+550h+var_530], r14
0x14004cf80  mov     rdx, rdi
0x14004cf83  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004cf88  jmp     loc_14004D1CA
0x14004cf8d  xor     ebx, ebx
0x14004cf8f  jmp     loc_14004D1CA
0x14004cf94  lea     r9, [rsp+550h+FindFileData.cFileName]; unsigned __int16 *
0x14004cf99  lea     r8, [rbp+450h+var_288]; unsigned __int16 *
0x14004cfa0  lea     rcx, [rbp+450h+var_260]; unsigned __int16 *
0x14004cfa7  call    ?PathCchCombineEx@@YAJPEAG_KPEBG2K@Z; PathCchCombineEx(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x14004cfac  mov     ebx, eax
0x14004cfae  test    eax, eax
0x14004cfb0  js      loc_14004D130
0x14004cfb6  test    byte ptr [rsp+550h+FindFileData.dwFileAttributes], 10h
0x14004cfbb  jnz     short loc_14004CFF6
0x14004cfbd  lea     rdx, [rbp+450h+var_260]; lpFileName
0x14004cfc4  lea     rcx, [rsp+550h+FindFileData.cFileName]; psz
0x14004cfc9  call    ?s_AddPendingSerializedCertificateToStore@CWmsWebService@@CAJPEBG0@Z; CWmsWebService::s_AddPendingSerializedCertificateToStore(ushort const *,ushort const *)
0x14004cfce  test    eax, eax
0x14004cfd0  jns     short loc_14004CFE5
0x14004cfd2  lea     rdx, [rbp+450h+var_260]
0x14004cfd9  lea     rcx, aCwmswebservice_27; "CWmsWebService::s_ProcessPendingReplace"...
0x14004cfe0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004cfe5  lea     rcx, [rbp+450h+var_260]; lpFileName
0x14004cfec  call    cs:__imp_DeleteFileW
0x14004cff2  test    eax, eax
0x14004cff4  jz      short loc_14004D020
0x14004cff6  lea     rdx, [rsp+550h+FindFileData]; lpFindFileData
0x14004cffb  mov     rcx, r12; hFindFile
0x14004cffe  call    cs:__imp_FindNextFileW
0x14004d004  test    eax, eax
0x14004d006  jnz     short loc_14004CF94
0x14004d008  call    cs:__imp_GetLastError
0x14004d00e  mov     ebx, eax
0x14004d010  cmp     eax, 12h
0x14004d013  jnz     loc_14004D0AD
0x14004d019  xor     ebx, ebx
0x14004d01b  jmp     loc_14004D1C5
0x14004d020  call    cs:__imp_GetLastError
0x14004d026  mov     ebx, eax
0x14004d028  test    eax, eax
0x14004d02a  jle     short loc_14004D031
0x14004d02c  movzx   ebx, ax
0x14004d02f  or      ebx, edi
0x14004d031  mov     eax, 80004005h
0x14004d036  lea     r13, aCbraex; "CBRAEx"
0x14004d03d  test    ebx, ebx
0x14004d03f  lea     rsi, aCwmswebservice_53; "CWmsWebService::s_ProcessPendingReplace"...
0x14004d046  mov     r14d, 9CBh
0x14004d04c  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d053  cmovns  ebx, eax
0x14004d056  lea     r15, aFsuccess; "fSuccess"
0x14004d05d  mov     [rsp+550h+var_528], ebx; int
0x14004d061  mov     r9, r13; unsigned __int16 *
0x14004d064  mov     r8, rsi; unsigned __int16 *
0x14004d067  mov     [rsp+550h+var_530], r15; unsigned __int16 *
0x14004d06c  mov     edx, r14d; unsigned int
0x14004d06f  mov     rcx, rdi; unsigned __int16 *
0x14004d072  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d077  call    cs:__imp_IsDebuggerPresent
0x14004d07d  test    eax, eax
0x14004d07f  jz      short loc_14004D097
0x14004d081  mov     [rsp+550h+var_518], ebx
0x14004d085  mov     r9d, r14d
0x14004d088  mov     [rsp+550h+var_520], r15
0x14004d08d  mov     qword ptr [rsp+550h+var_528], r13
0x14004d092  jmp     loc_14004D187
0x14004d097  mov     dword ptr [rsp+550h+var_520], ebx
0x14004d09b  mov     r8d, r14d
0x14004d09e  mov     qword ptr [rsp+550h+var_528], r15
0x14004d0a3  mov     [rsp+550h+var_530], r13
0x14004d0a8  jmp     loc_14004D1B3
0x14004d0ad  movzx   ecx, bx
0x14004d0b0  test    ebx, ebx
0x14004d0b2  jle     short loc_14004D0B8
0x14004d0b4  mov     eax, ecx
0x14004d0b6  or      eax, edi
0x14004d0b8  test    eax, eax
0x14004d0ba  jns     short loc_14004D129
0x14004d0bc  test    ebx, ebx
0x14004d0be  jle     short loc_14004D0C4
0x14004d0c0  mov     ebx, ecx
0x14004d0c2  or      ebx, edi
0x14004d0c4  lea     r14, aChra; "CHRA"
0x14004d0cb  mov     [rsp+550h+var_528], ebx; int
0x14004d0cf  lea     rsi, aCwmswebservice_53; "CWmsWebService::s_ProcessPendingReplace"...
0x14004d0d6  mov     r13d, 9D5h
0x14004d0dc  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d0e3  mov     r9, r14; unsigned __int16 *
0x14004d0e6  lea     r15, aHresultFromWin_0; "HRESULT_FROM_WIN32 (dwError)"
0x14004d0ed  mov     r8, rsi; unsigned __int16 *
0x14004d0f0  mov     edx, r13d; unsigned int
0x14004d0f3  mov     [rsp+550h+var_530], r15; unsigned __int16 *
0x14004d0f8  mov     rcx, rdi; unsigned __int16 *
0x14004d0fb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d100  call    cs:__imp_IsDebuggerPresent
0x14004d106  test    eax, eax
0x14004d108  jz      short loc_14004D118
0x14004d10a  mov     [rsp+550h+var_518], ebx
0x14004d10e  mov     r9d, r13d
0x14004d111  mov     [rsp+550h+var_520], r15
0x14004d116  jmp     short loc_14004D182
0x14004d118  mov     dword ptr [rsp+550h+var_520], ebx
0x14004d11c  mov     r8d, r13d
0x14004d11f  mov     qword ptr [rsp+550h+var_528], r15
0x14004d124  jmp     loc_14004D1AE
0x14004d129  mov     ebx, eax
0x14004d12b  jmp     loc_14004D1C5
0x14004d130  lea     r14, aChra; "CHRA"
0x14004d137  mov     [rsp+550h+var_528], ebx; int
0x14004d13b  lea     rsi, aCwmswebservice_53; "CWmsWebService::s_ProcessPendingReplace"...
0x14004d142  mov     r15d, 9BFh
0x14004d148  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d14f  mov     r9, r14; unsigned __int16 *
0x14004d152  lea     r13, aHr; "hr"
0x14004d159  mov     r8, rsi; unsigned __int16 *
0x14004d15c  mov     edx, r15d; unsigned int
0x14004d15f  mov     [rsp+550h+var_530], r13; unsigned __int16 *
0x14004d164  mov     rcx, rdi; unsigned __int16 *
0x14004d167  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d16c  call    cs:__imp_IsDebuggerPresent
0x14004d172  test    eax, eax
0x14004d174  jz      short loc_14004D1A2
0x14004d176  mov     [rsp+550h+var_518], ebx
0x14004d17a  mov     r9d, r15d
0x14004d17d  mov     [rsp+550h+var_520], r13
0x14004d182  mov     qword ptr [rsp+550h+var_528], r14
0x14004d187  mov     r8, rdi
0x14004d18a  mov     [rsp+550h+var_530], rsi
0x14004d18f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004d196  mov     ecx, 2; unsigned __int8
0x14004d19b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004d1a0  jmp     short loc_14004D1C5
0x14004d1a2  mov     dword ptr [rsp+550h+var_520], ebx
0x14004d1a6  mov     r8d, r15d
0x14004d1a9  mov     qword ptr [rsp+550h+var_528], r13
0x14004d1ae  mov     [rsp+550h+var_530], r14
0x14004d1b3  mov     r9, rsi
0x14004d1b6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004d1bd  mov     rdx, rdi
0x14004d1c0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004d1c5  test    r12, r12
0x14004d1c8  jz      short loc_14004D1D3
0x14004d1ca  mov     rcx, r12; hFindFile
0x14004d1cd  call    cs:__imp_FindClose
0x14004d1d3  mov     eax, ebx
0x14004d1d5  mov     rcx, [rbp+450h+var_50]
0x14004d1dc  xor     rcx, rsp; StackCookie
0x14004d1df  call    __security_check_cookie
0x14004d1e4  add     rsp, 518h
0x14004d1eb  pop     r15
0x14004d1ed  pop     r14
0x14004d1ef  pop     r13
0x14004d1f1  pop     r12
0x14004d1f3  pop     rdi
0x14004d1f4  pop     rsi
0x14004d1f5  pop     rbx
0x14004d1f6  pop     rbp
0x14004d1f7  retn
```
