# CoreInstall(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *)

- ea: `0x180004880`
- end: `0x180005213`
- name: `?CoreInstall@@YAJPEBG00KK0@Z`
- size: `2451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, ULONG, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `30`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180005ea0`
- `0x18000b8f0`
- `0x18000bdb0`
- `0x18000f7b0`

## callees

- `0x1800022bc`
- `0x1800040e0`
- `0x180004700`
- `0x180004754`
- `0x180004880`
- `0x180005584`
- `0x180005f80`
- `0x18000616c`
- `0x180006d24`
- `0x180007454`
- `0x1800080c8`
- `0x1800080f0`
- `0x180008644`
- `0x180008a6c`
- `0x180009004`
- `0x180009928`
- `0x18000a0c0`
- `0x18000a24c`
- `0x18000a61c`
- `0x18000c574`
- `0x18000dbec`
- `0x18000de30`
- `0x18000e060`
- `0x180010350`
- `0x180017728`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!ExitWindowsEx` at `0x1800051b8`
- `USER32!ExitWindowsEx` at `0x1800051b8`
- `KERNEL32!GetLastError` at `0x180004f5c`
- `KERNEL32!GetLastError` at `0x180004f5c`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000506e`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000506e`
- `KERNEL32!DeleteFileW` at `0x18000515a`
- `KERNEL32!DeleteFileW` at `0x18000515a`
- `ADVAPI32!RegCreateKeyExW` at `0x1800050d5`
- `ADVAPI32!RegCreateKeyExW` at `0x1800050d5`
- `ADVAPI32!RegCloseKey` at `0x180004c90`
- `ADVAPI32!RegCloseKey` at `0x180005113`
- `ADVAPI32!RegCloseKey` at `0x180004c90`
- `ADVAPI32!RegCloseKey` at `0x180005113`
- `ADVAPI32!RegOpenKeyExW` at `0x180004bd7`
- `ADVAPI32!RegOpenKeyExW` at `0x180004bd7`
- `ADVAPI32!RegEnumValueW` at `0x180004c23`
- `ADVAPI32!RegEnumValueW` at `0x180004c7a`
- `ADVAPI32!RegEnumValueW` at `0x180004c23`
- `ADVAPI32!RegEnumValueW` at `0x180004c7a`
- `ADVAPI32!RegSetValueExW` at `0x180005108`
- `ADVAPI32!RegSetValueExW` at `0x180005108`

## string_xrefs

- `0x180004ade`: `ComponentName`
- `0x1800048f5`: `CoreInstall: InfFile=%1 `
- `0x180004951`: `InstallSection=%1\n`
- `0x180004e1d`: `CoreInstall: SfpInstallCatalog returned=%1!lu!\n`
- `0x180004e37`: `GenInstall: Sec=%1\n`
- `0x180004e59`: `GenInstall return: Sec=%1 hr=0x%2!x!\n`
- `0x1800051df`: `CoreInstall: End InfFile=%1 hr=0x%2!x!\n`
- `0x180004f8e`: `RunPostSetupCommands`
- `0x180004a3f`: `RunPreSetupCommands`

## pseudocode

```c
__int64 __fastcall CoreInstall(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        ULONG a5,
        const unsigned __int16 *a6)
{
  unsigned __int16 *v6; // r12
  unsigned int v10; // r14d
  __int64 v11; // rdi
  __int16 v12; // bx
  WCHAR *v13; // rdi
  int v14; // edi
  WCHAR *p_ValueName; // r15
  DWORD v16; // r12d
  int v17; // ebx
  WCHAR *v18; // rbx
  int v19; // edi
  int v20; // ebx
  const unsigned __int16 *v21; // r8
  int v22; // eax
  int v23; // r8d
  signed int LastError; // eax
  int v25; // eax
  unsigned int v26; // eax
  int v27; // r12d
  ULONG dwFlags; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v34; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v36; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v37; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v38; // [rsp+80h] [rbp-80h]
  unsigned __int16 v39[4]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Section[256]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszPathOut[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszMore[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR ValueName; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v44[1022]; // [rsp+6B2h] [rbp+5B2h] BYREF
  unsigned __int16 v45[256]; // [rsp+AB0h] [rbp+9B0h] BYREF

  v6 = a3;
  v37 = a3;
  v38 = a6;
  hKey = 0;
  v36 = 0;
  ValueName = 0;
  memset_0(v44, 0, sizeof(v44));
  AdvWriteToLog(L"CoreInstall: InfFile=%1 ", a1);
  StringCchCopyW(v39, 4u, L"I");
  v10 = a5;
  LODWORD(v11) = CommonInstallInit(a1, a2, Section, 0x100u, v6, 1, a5);
  if ( (int)v11 < 0 )
    goto LABEL_107;
  AdvWriteToLog(L"InstallSection=%1\r\n", Section);
  if ( GetTranslatedInt(a1, Section, L"CheckAdminRights", 0) && ctx && !IsNTAdmin(0, 0) )
  {
    v12 = word_1800257D2;
    word_1800257D2 |= 2u;
    LODWORD(v11) = -2147467260;
    MsgBox2Param(hWnd, 0x48Eu, 0, 0, 0x10u, 0);
    word_1800257D2 = v12;
    goto LABEL_107;
  }
  v34 = a5 & 1;
  if ( (a5 & 1) != 0 && (a5 & 0x10) == 0 )
  {
    v36 = pszTitleString;
    if ( (unsigned int)BeginPrompt(a1, Section, v45) == 2 )
    {
      LODWORD(v11) = -2147023673;
LABEL_108:
      pszTitleString = v36;
      goto LABEL_109;
    }
  }
  v32 = 0;
  if ( (a5 & 0x200) == 0 )
    v32 = InternalNeedRebootInit(ctx);
  LODWORD(v11) = RunCommandsSections(a1, Section, L"RunPreSetupCommands", v6, 0, 0);
  if ( (int)v11 < 0 )
    goto LABEL_107;
  LODWORD(v11) = SetLDIDs(a1, Section, a4, 0);
  if ( (int)v11 < 0 )
    goto LABEL_107;
  LODWORD(v11) = RunPatchingCommands(a1, Section, v6);
  if ( (int)v11 < 0 )
    goto LABEL_107;
  if ( (a5 & 0x10) == 0 )
    RemoveBackupBaseOnVer(a1, Section);
  memset_0(&ValueName, 0, 0x400u);
  if ( (a5 & 0x40) != 0 )
  {
    pszMore[0] = 0;
    GetTranslatedString(a1, Section, L"ComponentName", pszMore, 0x104u, 0);
    if ( pszMore[0] )
    {
      phkResult = 0;
      StringCchCopyW(pszPathOut, 0x104u, L"Software\\Microsoft\\Advanced INF Setup");
      v13 = pszMore;
      if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
      {
        do
          ++v13;
        while ( *v13 == 92 );
      }
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v13, dwFlags);
      PathIsUnc2(L"Catalogs");
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, L"Catalogs", dwFlagsa);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &phkResult) )
      {
        cchValueName = 511;
        v14 = 0;
        p_ValueName = &ValueName;
        v16 = 0;
        if ( !RegEnumValueW(phkResult, 0, &ValueName, &cchValueName, 0, 0, 0, 0) )
        {
          do
          {
            ++v16;
            v14 += (cchValueName >> 1) + 1;
            p_ValueName += ((unsigned __int64)cchValueName >> 1) + 1;
            cchValueName = 511 - v14;
          }
          while ( !RegEnumValueW(phkResult, v16, p_ValueName, &cchValueName, 0, 0, 0, 0) );
          v10 = a5;
        }
        RegCloseKey(phkResult);
        v6 = (unsigned __int16 *)v37;
      }
    }
  }
  if ( ValueName || (GetTranslatedString(a1, Section, L"CatalogName", &ValueName, 0x200u, 0), ValueName) )
    ValueName = 0;
  if ( (v10 & 8) != 0 || (a5 & 0x10) != 0 )
  {
    if ( (a5 & 0x10) != 0 )
      RegisterOCXs(a1, Section, 0, 0, v10);
    LODWORD(v11) = SaveRestoreInfo(a1, Section, v6, v10);
    if ( (int)v11 < 0 )
      goto LABEL_107;
    if ( (a5 & 0x10) != 0 )
    {
      v17 = InternalNeedReboot(v32, ctx);
      RegisterOCXs(a1, Section, v17, 1, v10);
      if ( v17 )
        LODWORD(v11) = 3010;
      DelDirs(a1, Section);
      goto LABEL_107;
    }
  }
  if ( ctx != 1 )
    RegisterOCXs(a1, Section, 0, 0, v10);
  if ( ValueName )
  {
    StringCchCopyW(pszPathOut, 0x104u, v6);
    v18 = &ValueName;
    if ( !(unsigned int)PathIsUnc2(&ValueName) && !IsExtendedLengthDosDevicePath(&ValueName) && ValueName == 92 )
    {
      do
        ++v18;
      while ( *v18 == 92 );
    }
    PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v18, dwFlags);
    AdvWriteToLog(L"CoreInstall: SfpInstallCatalog returned=%1!lu!\r\n", 120);
    LODWORD(v11) = -2147024776;
    goto LABEL_107;
  }
  AdvWriteToLog(L"GenInstall: Sec=%1\r\n", Section);
  v11 = (unsigned int)GenInstall(a1, Section, v6);
  AdvWriteToLog(L"GenInstall return: Sec=%1 hr=0x%2!x!\r\n", Section, v11);
  if ( (int)v11 < 0 )
    goto LABEL_107;
  v19 = InternalNeedReboot(v32, ctx);
  v20 = v19;
  cchValueName = v10 & 4;
  if ( (v10 & 4) == 0 )
    goto LABEL_64;
  if ( v38 && *v38 )
  {
    v21 = v38;
LABEL_55:
    StringCchCopyW(v39, 4u, v21);
    goto LABEL_56;
  }
  if ( (int)GetTranslatedString(a1, Section, L"SmartReboot", v39, 4u, 0) < 0 )
  {
    v21 = L"I";
    goto LABEL_55;
  }
LABEL_56:
  switch ( v39[0] )
  {
    case 0u:
      StringCchCopyW(v39, 4u, L"I");
      break;
    case 0x41u:
      goto LABEL_62;
    case 0x4Eu:
LABEL_61:
      v20 = 0;
      break;
    case 0x61u:
LABEL_62:
      v22 = 1;
      v20 = 1;
      goto LABEL_65;
    case 0x6Eu:
      goto LABEL_61;
  }
LABEL_64:
  v22 = 1;
LABEL_65:
  if ( ctx != 1 )
  {
    if ( v20 || (v23 = 0, v19) )
      v23 = 1;
    if ( !(unsigned int)RegisterOCXs(a1, Section, v23, 1, v10) )
    {
      LastError = GetLastError();
      LODWORD(v11) = LastError;
      if ( LastError > 0 )
        LODWORD(v11) = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_107;
    }
    v22 = 1;
  }
  if ( !v20 && !v19 )
    v22 = 0;
  LODWORD(v11) = RunCommandsSections(a1, Section, L"RunPostSetupCommands", v6, v10, v22);
  if ( (int)v11 >= 0 )
  {
    v25 = ProcessPerUserSec(a1, Section);
    LODWORD(v11) = v25;
    if ( v25 >= 0 )
    {
      if ( (v10 & 0x400) != 0 || v25 == 3010 )
        v26 = 0;
      else
        v26 = v32;
      v27 = InternalNeedReboot(v26, ctx);
      if ( GetTranslatedInt(a1, Section, L"Reboot", 0) )
      {
        v27 = 1;
      }
      else if ( !v27 )
      {
LABEL_86:
        if ( ((v39[0] - 73) & 0xFFDF) == 0 )
          v20 = v27;
        if ( ctx != 1 && (unsigned int)NeedToRunGrpconv() )
        {
          if ( (v10 & 2) == 0 || v20 || v27 )
          {
            if ( !RegCreateKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
                    0,
                    0,
                    0,
                    0x20006u,
                    0,
                    &hKey,
                    0) )
            {
              RegSetValueExW(hKey, L"GrpConv", 0, 1u, L"grpconv.exe -o", 0x1Eu);
              RegCloseKey(hKey);
            }
          }
          else
          {
            GetWindowsDirectoryW(pszPathOut, 0x104u);
            LaunchAndWait(L"grpconv.exe -o", pszPathOut, 0, 0x7530u, word_1800257D2 & 1);
          }
        }
        DelDirs(a1, Section);
        if ( v34 )
          EndPrompt(a1, Section);
        if ( (GetTranslatedInt(a1, Section, L"Cleanup", 0) & 1) != 0 )
          DeleteFileW(a1);
        if ( v20
          && cchValueName
          && (((v39[1] - 83) & 0xFFDF) == 0 || (unsigned int)MsgBox2Param(hWnd, 0x3ECu, 0, 0, 0x40u, 4u) == 6) )
        {
          if ( ctx )
            MyNTReboot();
          else
            ExitWindowsEx(2u, 0);
        }
        goto LABEL_107;
      }
      LODWORD(v11) = 3010;
      goto LABEL_86;
    }
  }
LABEL_107:
  if ( (v10 & 1) != 0 )
    goto LABEL_108;
LABEL_109:
  CommonInstallCleanup();
  AdvWriteToLog(L"CoreInstall: End InfFile=%1 hr=0x%2!x!\r\n", a1, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004880  push    rbp
0x180004882  push    rbx
0x180004883  push    rsi
0x180004884  push    rdi
0x180004885  push    r12
0x180004887  push    r13
0x180004889  push    r14
0x18000488b  push    r15
0x18000488d  lea     rbp, [rsp-0BC8h]
0x180004895  sub     rsp, 0CC8h
0x18000489c  mov     rax, cs:__security_cookie
0x1800048a3  xor     rax, rsp
0x1800048a6  mov     [rbp+0C00h+var_50], rax
0x1800048ad  mov     rax, [rbp+0C00h+arg_28]
0x1800048b4  xor     r13d, r13d
0x1800048b7  mov     r12, r8
0x1800048ba  mov     [rsp+0D00h+var_C88], r8
0x1800048bf  mov     rbx, rdx
0x1800048c2  mov     [rbp+0C00h+var_C80], rax
0x1800048c6  mov     rsi, rcx
0x1800048c9  mov     [rsp+0D00h+hKey], r13
0x1800048ce  xor     edx, edx; Val
0x1800048d0  mov     [rsp+0D00h+var_C90], r13
0x1800048d5  mov     r8d, 3FEh; Size
0x1800048db  mov     [rbp+0C00h+ValueName], r13w
0x1800048e3  lea     rcx, [rbp+0C00h+var_64E]; void *
0x1800048ea  mov     r15d, r9d
0x1800048ed  call    memset_0
0x1800048f2  mov     rdx, rsi
0x1800048f5  lea     rcx, aCoreinstallInf; "CoreInstall: InfFile=%1 "
0x1800048fc  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180004901  lea     r8, aI; "I"
0x180004908  lea     edx, [r13+4]; unsigned __int64
0x18000490c  lea     rcx, [rbp+0C00h+var_C78]; unsigned __int16 *
0x180004910  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004915  mov     r14d, [rbp+0C00h+arg_20]
0x18000491c  lea     r8, [rbp+0C00h+Section]; unsigned __int16 *
0x180004920  mov     dword ptr [rsp+0D00h+lpData], r14d; unsigned int
0x180004925  mov     r9d, 100h; unsigned int
0x18000492b  mov     dword ptr [rsp+0D00h+lpType], 1; int
0x180004933  mov     rdx, rbx; unsigned __int16 *
0x180004936  mov     rcx, rsi; unsigned __int16 *
0x180004939  mov     qword ptr [rsp+0D00h+dwFlags], r12; unsigned __int16 *
0x18000493e  call    ?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z; CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)
0x180004943  mov     edi, eax
0x180004945  test    eax, eax
0x180004947  js      loc_1800051C5
0x18000494d  lea     rdx, [rbp+0C00h+Section]
0x180004951  lea     rcx, aInstallsection; "InstallSection=%1\r\n"
0x180004958  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000495d  xor     r9d, r9d; nDefault
0x180004960  lea     r8, aCheckadminrigh; "CheckAdminRights"
0x180004967  lea     rdx, [rbp+0C00h+Section]; Section
0x18000496b  mov     rcx, rsi; unsigned __int16 *
0x18000496e  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x180004973  test    eax, eax
0x180004975  jz      short loc_1800049D8
0x180004977  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r13w; ADVCONTEXTW ctx
0x18000497f  jz      short loc_1800049D8
0x180004981  xor     edx, edx; lpdwReserved
0x180004983  xor     ecx, ecx; dwReserved
0x180004985  call    IsNTAdmin
0x18000498a  test    eax, eax
0x18000498c  jnz     short loc_1800049D8
0x18000498e  movzx   ebx, cs:word_1800257D2
0x180004995  xor     r9d, r9d; unsigned __int16 *
0x180004998  mov     rcx, cs:hWnd; hWnd
0x18000499f  movzx   eax, bx
0x1800049a2  or      ax, 2
0x1800049a6  mov     dword ptr [rsp+0D00h+lpType], r13d; unsigned int
0x1800049ab  xor     r8d, r8d; unsigned __int16 *
0x1800049ae  mov     cs:word_1800257D2, ax
0x1800049b5  mov     edx, 48Eh; uID
0x1800049ba  mov     [rsp+0D00h+dwFlags], 10h; unsigned int
0x1800049c2  mov     edi, 80004004h
0x1800049c7  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800049cc  mov     cs:word_1800257D2, bx
0x1800049d3  jmp     loc_1800051C5
0x1800049d8  mov     eax, r14d
0x1800049db  mov     r13d, 2
0x1800049e1  and     eax, 1
0x1800049e4  mov     [rsp+0D00h+var_CA0], eax
0x1800049e8  jz      short loc_180004A1E
0x1800049ea  test    r14b, 10h
0x1800049ee  jnz     short loc_180004A1E
0x1800049f0  mov     rax, cs:pszTitleString
0x1800049f7  lea     r8, [rbp+0C00h+var_250]; unsigned __int16 *
0x1800049fe  lea     rdx, [rbp+0C00h+Section]; unsigned __int16 *
0x180004a02  mov     [rsp+0D00h+var_C90], rax
0x180004a07  mov     rcx, rsi; unsigned __int16 *
0x180004a0a  call    ?BeginPrompt@@YAHPEBG0PEAGK@Z; BeginPrompt(ushort const *,ushort const *,ushort *,ulong)
0x180004a0f  cmp     eax, r13d
0x180004a12  jnz     short loc_180004A1E
0x180004a14  mov     edi, 800704C7h
0x180004a19  jmp     loc_1800051CB
0x180004a1e  xor     ebx, ebx
0x180004a20  mov     [rsp+0D00h+var_CAC], ebx
0x180004a24  bt      r14d, 9
0x180004a29  jb      short loc_180004A3B
0x180004a2b  movzx   ecx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x180004a32  call    ?InternalNeedRebootInit@@YAKG@Z; InternalNeedRebootInit(ushort)
0x180004a37  mov     [rsp+0D00h+var_CAC], eax
0x180004a3b  mov     dword ptr [rsp+0D00h+lpType], ebx; int
0x180004a3f  lea     r8, aRunpresetupcom; "RunPreSetupCommands"
0x180004a46  mov     r9, r12; unsigned __int16 *
0x180004a49  mov     [rsp+0D00h+dwFlags], ebx; unsigned int
0x180004a4d  lea     rdx, [rbp+0C00h+Section]; unsigned __int16 *
0x180004a51  mov     rcx, rsi; lpFileName
0x180004a54  call    ?RunCommandsSections@@YAJPEBG000KH@Z; RunCommandsSections(ushort const *,ushort const *,ushort const *,ushort const *,ulong,int)
0x180004a59  mov     edi, eax
0x180004a5b  test    eax, eax
0x180004a5d  js      loc_1800051C5
0x180004a63  xor     r9d, r9d; unsigned __int16 *
0x180004a66  lea     rdx, [rbp+0C00h+Section]; unsigned __int16 *
0x180004a6a  mov     r8d, r15d; unsigned int
0x180004a6d  mov     rcx, rsi; unsigned __int16 *
0x180004a70  call    ?SetLDIDs@@YAJPEBG0K0@Z; SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)
0x180004a75  xor     r15d, r15d
0x180004a78  mov     edi, eax
0x180004a7a  test    eax, eax
0x180004a7c  js      loc_1800051C5
0x180004a82  mov     r8, r12; lpWideCharStr
0x180004a85  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004a89  mov     rcx, rsi; unsigned __int16 *
0x180004a8c  call    ?RunPatchingCommands@@YAJPEBG00@Z; RunPatchingCommands(ushort const *,ushort const *,ushort const *)
0x180004a91  mov     edi, eax
0x180004a93  test    eax, eax
0x180004a95  js      loc_1800051C5
0x180004a9b  mov     ebx, r14d
0x180004a9e  and     ebx, 10h
0x180004aa1  jnz     short loc_180004AAF
0x180004aa3  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004aa7  mov     rcx, rsi; unsigned __int16 *
0x180004aaa  call    ?RemoveBackupBaseOnVer@@YAHPEBG0@Z; RemoveBackupBaseOnVer(ushort const *,ushort const *)
0x180004aaf  xor     edx, edx; Val
0x180004ab1  lea     rcx, [rbp+0C00h+ValueName]; void *
0x180004ab8  mov     r8d, 400h; Size
0x180004abe  call    memset_0
0x180004ac3  mov     edi, 104h
0x180004ac8  test    r14b, 40h
0x180004acc  jz      loc_180004C9E
0x180004ad2  mov     [rsp+0D00h+lpType], r15; unsigned int *
0x180004ad7  lea     r9, [rbp+0C00h+pszMore]; unsigned __int16 *
0x180004ade  lea     r8, KeyName; "ComponentName"
0x180004ae5  mov     [rsp+0D00h+dwFlags], edi; unsigned int
0x180004ae9  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004aed  mov     [rbp+0C00h+pszMore], r15w
0x180004af5  mov     rcx, rsi; unsigned __int16 *
0x180004af8  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180004afd  cmp     [rbp+0C00h+pszMore], r15w
0x180004b05  jz      loc_180004C9E
0x180004b0b  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x180004b12  mov     [rsp+0D00h+phkResult], r15
0x180004b17  mov     edx, edi; unsigned __int64
0x180004b19  lea     rcx, [rbp+0C00h+pszPathOut]; unsigned __int16 *
0x180004b20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b25  lea     r8, IsBackslash
0x180004b2c  xor     edx, edx
0x180004b2e  lea     rcx, [rbp+0C00h+pszMore]; unsigned __int16 *
0x180004b35  lea     rdi, [rbp+0C00h+pszMore]
0x180004b3c  call    PathIsUnc2
0x180004b41  test    eax, eax
0x180004b43  jnz     short loc_180004B68
0x180004b45  lea     rcx, [rbp+0C00h+pszMore]; unsigned __int16 *
0x180004b4c  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180004b51  test    al, al
0x180004b53  jnz     short loc_180004B68
0x180004b55  cmp     [rbp+0C00h+pszMore], 5Ch ; '\'
0x180004b5d  jnz     short loc_180004B68
0x180004b5f  add     rdi, r13
0x180004b62  cmp     word ptr [rdi], 5Ch ; '\'
0x180004b66  jz      short loc_180004B5F
0x180004b68  mov     r9, rdi; pszMore
0x180004b6b  lea     r8, [rbp+0C00h+pszPathOut]; pszPathIn
0x180004b72  mov     edi, 104h
0x180004b77  lea     rcx, [rbp+0C00h+pszPathOut]; pszPathOut
0x180004b7e  mov     edx, edi; cchPathOut
0x180004b80  call    PathCchCombineEx
0x180004b85  lea     r8, IsBackslash
0x180004b8c  xor     edx, edx
0x180004b8e  lea     rcx, aCatalogs; "Catalogs"
0x180004b95  call    PathIsUnc2
0x180004b9a  lea     r9, aCatalogs; "Catalogs"
0x180004ba1  mov     edx, edi; cchPathOut
0x180004ba3  lea     r8, [rbp+0C00h+pszPathOut]; pszPathIn
0x180004baa  lea     rcx, [rbp+0C00h+pszPathOut]; pszPathOut
0x180004bb1  call    PathCchCombineEx
0x180004bb6  lea     rax, [rsp+0D00h+phkResult]
0x180004bbb  mov     r9d, 20019h; samDesired
0x180004bc1  xor     r8d, r8d; ulOptions
0x180004bc4  mov     qword ptr [rsp+0D00h+dwFlags], rax; phkResult
0x180004bc9  lea     rdx, [rbp+0C00h+pszPathOut]; lpSubKey
0x180004bd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004bd7  call    cs:__imp_RegOpenKeyExW
0x180004bdd  test    eax, eax
0x180004bdf  jnz     loc_180004C9E
0x180004be5  mov     rcx, [rsp+0D00h+phkResult]; hKey
0x180004bea  lea     r9, [rsp+0D00h+cchValueName]; lpcchValueName
0x180004bef  xor     eax, eax
0x180004bf1  mov     [rsp+0D00h+cchValueName], 1FFh
0x180004bf9  mov     [rsp+0D00h+lpcbData], rax; lpcbData
0x180004bfe  lea     r8, [rbp+0C00h+ValueName]; lpValueName
0x180004c05  mov     [rsp+0D00h+lpData], rax; lpData
0x180004c0a  mov     edi, r15d
0x180004c0d  mov     [rsp+0D00h+lpType], rax; lpType
0x180004c12  lea     r15, [rbp+0C00h+ValueName]
0x180004c19  xor     edx, edx; dwIndex
0x180004c1b  mov     qword ptr [rsp+0D00h+dwFlags], rax; lpReserved
0x180004c20  mov     r12d, eax
0x180004c23  call    cs:__imp_RegEnumValueW
0x180004c29  test    eax, eax
0x180004c2b  jnz     short loc_180004C8B
0x180004c2d  xor     r14d, r14d
0x180004c30  mov     eax, [rsp+0D00h+cchValueName]
0x180004c34  lea     r9, [rsp+0D00h+cchValueName]; lpcchValueName
0x180004c39  mov     rcx, [rsp+0D00h+phkResult]; hKey
0x180004c3e  inc     r12d
0x180004c41  shr     eax, 1
0x180004c43  mov     edx, r12d; dwIndex
0x180004c46  inc     eax
0x180004c48  mov     [rsp+0D00h+lpcbData], r14; lpcbData
0x180004c4d  add     edi, eax
0x180004c4f  mov     [rsp+0D00h+lpData], r14; lpData
0x180004c54  mov     eax, [rsp+0D00h+cchValueName]
0x180004c58  shr     rax, 1
0x180004c5b  mov     [rsp+0D00h+lpType], r14; lpType
0x180004c60  mov     qword ptr [rsp+0D00h+dwFlags], r14; lpReserved
0x180004c65  lea     r15, [r15+rax*2]
0x180004c69  mov     eax, 1FFh
0x180004c6e  sub     eax, edi
0x180004c70  add     r15, r13
0x180004c73  mov     r8, r15; lpValueName
0x180004c76  mov     [rsp+0D00h+cchValueName], eax
0x180004c7a  call    cs:__imp_RegEnumValueW
0x180004c80  test    eax, eax
0x180004c82  jz      short loc_180004C30
0x180004c84  mov     r14d, [rbp+0C00h+arg_20]
0x180004c8b  mov     rcx, [rsp+0D00h+phkResult]; hKey
0x180004c90  call    cs:__imp_RegCloseKey
0x180004c96  mov     r12, [rsp+0D00h+var_C88]
0x180004c9b  xor     r15d, r15d
0x180004c9e  cmp     [rbp+0C00h+ValueName], r15w
0x180004ca6  jnz     short loc_180004CD9
0x180004ca8  mov     [rsp+0D00h+lpType], r15; unsigned int *
0x180004cad  lea     r9, [rbp+0C00h+ValueName]; unsigned __int16 *
0x180004cb4  lea     r8, aCatalogname; "CatalogName"
0x180004cbb  mov     [rsp+0D00h+dwFlags], 200h; unsigned int
0x180004cc3  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004cc7  mov     rcx, rsi; unsigned __int16 *
0x180004cca  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180004ccf  cmp     [rbp+0C00h+ValueName], r15w
0x180004cd7  jz      short loc_180004CE1
0x180004cd9  mov     [rbp+0C00h+ValueName], r15w
0x180004ce1  test    r14b, 8
0x180004ce5  jnz     short loc_180004CEF
0x180004ce7  test    ebx, ebx
0x180004ce9  jz      loc_180004D73
0x180004cef  test    ebx, ebx
0x180004cf1  jz      short loc_180004D0A
0x180004cf3  xor     r9d, r9d; int
0x180004cf6  mov     [rsp+0D00h+dwFlags], r14d; unsigned int
0x180004cfb  xor     r8d, r8d; int
0x180004cfe  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004d02  mov     rcx, rsi; unsigned __int16 *
0x180004d05  call    ?RegisterOCXs@@YAHPEBG0HHK@Z; RegisterOCXs(ushort const *,ushort const *,int,int,ulong)
0x180004d0a  mov     r9d, r14d; unsigned int
0x180004d0d  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004d11  mov     r8, r12; SourceRootPath
0x180004d14  mov     rcx, rsi; unsigned __int16 *
0x180004d17  call    ?SaveRestoreInfo@@YAJPEBG00K@Z; SaveRestoreInfo(ushort const *,ushort const *,ushort const *,ulong)
0x180004d1c  mov     edi, eax
0x180004d1e  test    eax, eax
0x180004d20  js      loc_1800051C5
0x180004d26  test    ebx, ebx
0x180004d28  jz      short loc_180004D73
0x180004d2a  movzx   edx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x180004d31  mov     ecx, [rsp+0D00h+var_CAC]; unsigned int
0x180004d35  call    ?InternalNeedReboot@@YAHKG@Z; InternalNeedReboot(ulong,ushort)
0x180004d3a  mov     r9d, 1; int
0x180004d40  mov     [rsp+0D00h+dwFlags], r14d; unsigned int
0x180004d45  mov     r8d, eax; int
0x180004d48  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004d4c  mov     rcx, rsi; unsigned __int16 *
0x180004d4f  mov     ebx, eax
0x180004d51  call    ?RegisterOCXs@@YAHPEBG0HHK@Z; RegisterOCXs(ushort const *,ushort const *,int,int,ulong)
0x180004d56  test    ebx, ebx
0x180004d58  lea     rdx, [rbp+0C00h+Section]; unsigned __int16 *
0x180004d5c  mov     r15d, 0BC2h
0x180004d62  mov     rcx, rsi; lpFileName
0x180004d65  cmovnz  edi, r15d
0x180004d69  call    ?DelDirs@@YAXPEBG0@Z; DelDirs(ushort const *,ushort const *)
0x180004d6e  jmp     loc_1800051C5
0x180004d73  mov     eax, 1
0x180004d78  cmp     cs:?ctx@@3UADVCONTEXTW@@A, ax; ADVCONTEXTW ctx
0x180004d7f  jz      short loc_180004D98
0x180004d81  xor     r9d, r9d; int
0x180004d84  mov     [rsp+0D00h+dwFlags], r14d; unsigned int
0x180004d89  xor     r8d, r8d; int
0x180004d8c  lea     rdx, [rbp+0C00h+Section]; lpAppName
0x180004d90  mov     rcx, rsi; unsigned __int16 *
  ... truncated ...
```
