# winreCopyWIMBackFromVolume(ushort const *,ReAgentConfigInfo *,int *)

- ea: `0x180038120`
- end: `0x1800385b0`
- name: `?winreCopyWIMBackFromVolume@@YAKPEBGPEAUReAgentConfigInfo@@PEAH@Z`
- size: `1168`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct ReAgentConfigInfo *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003a778`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000fe58`
- `0x18000ff68`
- `0x18001051c`
- `0x1800322a8`
- `0x180038120`
- `0x18003bea8`
- `0x18004d52c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800384c2`
- `KERNEL32!GetLastError` at `0x1800384c2`
- `KERNEL32!RemoveDirectoryW` at `0x180038524`
- `KERNEL32!RemoveDirectoryW` at `0x180038524`
- `KERNEL32!MoveFileExW` at `0x1800384b8`
- `KERNEL32!MoveFileExW` at `0x1800384b8`
- `KERNEL32!DeleteFileW` at `0x180038517`
- `KERNEL32!DeleteFileW` at `0x180038517`
- `ole32!CoTaskMemFree` at `0x180038532`
- `ole32!CoTaskMemFree` at `0x180038532`

## string_xrefs

- `0x18003830b`: `failed to find main os config directory`
- `0x18003848e`: `failed to add winre.wim to directory path`
- `0x18003842a`: `failed to open directory`
- `0x1800384d0`: `failed to move file`
- `0x1800382f7`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180038364`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x1800383a9`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180038543`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x1800381b5`: ` invalid parameter: TempFilesFound can't be NULL`
- `0x180038245`: `Recovery\Temporary`
- `0x180038557`: `failed to append recovery\temporary path`
- `0x180038315`: `winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d`
- `0x180038373`: `winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d`
- `0x1800383b8`: `winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d`
- `0x180038561`: `winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d`
- `0x1800382be`: ` Path %s not found`
- `0x18003835d`: `failed to copy src directory`
- `0x1800383ec`: `failed to copy image location path`
- `0x180038506`: `failed to delete boot.sdi`
- `0x180038573`: `winreCopyWIMBackFromVolume failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCopyWIMBackFromVolume(const unsigned __int16 *a1, struct ReAgentConfigInfo *a2, int *a3)
{
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  unsigned int MainOsConfigDir; // eax
  WCHAR *v11; // rdi
  const wchar_t *v12; // r8
  DWORD Dir; // eax
  const wchar_t *v14; // r8
  int v16; // [rsp+28h] [rbp-D8h]
  int v17; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ExistingFileName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[606]; // [rsp+42h] [rbp-BEh] BYREF
  WCHAR PathName; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v22[606]; // [rsp+2A2h] [rbp+1A2h] BYREF
  WCHAR NewFileName; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v24[606]; // [rsp+502h] [rbp+402h] BYREF

  ExistingFileName = 0;
  memset_0(v20, 0, 0x25Au);
  NewFileName = 0;
  memset_0(v24, 0, 0x25Au);
  PathName = 0;
  memset_0(v22, 0, 0x25Au);
  if ( !a3 )
  {
    v6 = 87;
    UnattendLogW(1, L" invalid parameter: TempFilesFound can't be NULL");
LABEL_51:
    UnattendLogW(1, L"winreCopyWIMBackFromVolume failed: 0x%x", (unsigned int)v6);
    return (unsigned int)v6;
  }
  *a3 = 0;
  v18 = 0;
  if ( !a1 )
  {
    v6 = 87;
    goto LABEL_50;
  }
  v6 = StringCchLengthW(a1, 0x7FFFFFFFu, &v18);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 14;
LABEL_15:
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v6);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( !v18 || (v9 = L"%s\\%s", a1[v18 - 1] == 92) )
    v9 = L"%s%s";
  v6 = StringCchPrintfW(&PathName, 0x12Eu, v9, a1, L"Recovery\\Temporary");
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
      goto LABEL_15;
    }
LABEL_16:
    v6 = (unsigned __int16)v6;
    if ( !(_WORD)v6 )
      goto LABEL_17;
LABEL_50:
    UnattendLogW(
      2,
      L"winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d",
      L"failed to append recovery\\temporary path",
      (unsigned int)v6,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      2181);
    goto LABEL_51;
  }
LABEL_17:
  if ( Utils::DoesPathExist(&PathName) )
  {
    UnattendLogW(0, L" Path %s not found", &PathName);
    return 0;
  }
  *a3 = 1;
  if ( *((_WORD *)a2 + 628) )
  {
    v11 = (WCHAR *)((char *)a2 + 1256);
  }
  else
  {
    MainOsConfigDir = winreFindMainOsConfigDir(0);
    v6 = MainOsConfigDir;
    if ( MainOsConfigDir )
    {
      UnattendLogW(
        2,
        L"winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d",
        L"failed to find main os config directory",
        MainOsConfigDir,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        2200);
      goto LABEL_47;
    }
    v11 = 0;
  }
  v6 = StringCchCopyW(&ExistingFileName, 0x12Eu, &PathName);
  if ( v6 < 0 )
  {
    v16 = 2214;
    v12 = L"failed to copy src directory";
LABEL_26:
    UnattendLogW(
      2,
      L"winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d",
      v12,
      (unsigned int)v6,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v16);
    v6 = (unsigned __int16)v6;
    goto LABEL_47;
  }
  Dir = winreAddTrailingBackslash(&ExistingFileName);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2216;
LABEL_29:
    v14 = L"failed to add trailing back slash";
LABEL_30:
    UnattendLogW(
      2,
      L"winreCopyWIMBackFromVolume %s (0x%x) in file %S line %d",
      v14,
      Dir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v17);
    goto LABEL_47;
  }
  v6 = StringCchCopyW(&NewFileName, 0x12Eu, (const unsigned __int16 *)a2 + 628);
  if ( v6 < 0 )
  {
    v16 = 2220;
    v12 = L"failed to copy image location path";
    goto LABEL_26;
  }
  Dir = winreAddTrailingBackslash(&NewFileName);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2222;
    goto LABEL_29;
  }
  Dir = winreOpenOrCreateDir(v11);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2229;
    v14 = L"failed to open directory";
    goto LABEL_30;
  }
  Dir = winreGetSourceFile(0, &PathName, L"Winre.wim", &ExistingFileName);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2238;
    v14 = L"failed to get source file";
    goto LABEL_30;
  }
  Dir = winreAddFileToDirPath(v11, L"Winre.wim", &NewFileName);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2242;
    v14 = L"failed to add winre.wim to directory path";
    goto LABEL_30;
  }
  if ( !Utils::DoesPathExist(&ExistingFileName) && !MoveFileExW(&ExistingFileName, &NewFileName, 3u) )
  {
    Dir = GetLastError();
    v17 = 2248;
    v14 = L"failed to move file";
    v6 = Dir;
    goto LABEL_30;
  }
  Dir = winreGetSourceFile(0, &PathName, L"boot.sdi", &ExistingFileName);
  v6 = Dir;
  if ( Dir )
  {
    v17 = 2257;
    v14 = L"failed to delete boot.sdi";
    goto LABEL_30;
  }
  DeleteFileW(&ExistingFileName);
  RemoveDirectoryW(&PathName);
LABEL_47:
  if ( v6 )
    goto LABEL_51;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180038120  mov     [rsp-8+arg_18], rbx
0x180038125  push    rbp
0x180038126  push    rsi
0x180038127  push    rdi
0x180038128  push    r12
0x18003812a  push    r13
0x18003812c  push    r14
0x18003812e  push    r15
0x180038130  lea     rbp, [rsp-670h]
0x180038138  sub     rsp, 770h
0x18003813f  mov     rax, cs:__security_cookie
0x180038146  xor     rax, rsp
0x180038149  mov     [rbp+6A0h+var_40], rax
0x180038150  mov     rsi, r8
0x180038153  mov     r15, rdx
0x180038156  mov     rdi, rcx
0x180038159  xor     eax, eax
0x18003815b  mov     ebx, 25Ah
0x180038160  mov     [rsp+7A0h+ExistingFileName], ax
0x180038165  xor     r14d, r14d
0x180038168  lea     rcx, [rsp+7A0h+var_75E]; void *
0x18003816d  mov     r8d, ebx; Size
0x180038170  mov     [rsp+7A0h+pv], r14
0x180038175  xor     edx, edx; Val
0x180038177  call    memset_0
0x18003817c  xor     eax, eax
0x18003817e  lea     rcx, [rbp+6A0h+var_29E]; void *
0x180038185  mov     r8d, ebx; Size
0x180038188  mov     [rbp+6A0h+NewFileName], ax
0x18003818f  xor     edx, edx; Val
0x180038191  call    memset_0
0x180038196  xor     eax, eax
0x180038198  lea     rcx, [rbp+6A0h+var_4FE]; void *
0x18003819f  mov     r8d, ebx; Size
0x1800381a2  mov     [rbp+6A0h+PathName], ax
0x1800381a9  xor     edx, edx; Val
0x1800381ab  call    memset_0
0x1800381b0  test    rsi, rsi
0x1800381b3  jnz     short loc_1800381CC
0x1800381b5  lea     rdx, aInvalidParamet_2; " invalid parameter: TempFilesFound can'"...
0x1800381bc  lea     ecx, [rsi+1]
0x1800381bf  lea     ebx, [rsi+57h]
0x1800381c2  call    UnattendLogW
0x1800381c7  jmp     loc_180038570
0x1800381cc  mov     [rsi], r14d
0x1800381cf  mov     r12d, 2
0x1800381d5  mov     [rsp+7A0h+var_768], r14
0x1800381da  test    rdi, rdi
0x1800381dd  jz      loc_18003853E
0x1800381e3  lea     r8, [rsp+7A0h+var_768]; unsigned __int64 *
0x1800381e8  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800381ed  mov     rcx, rdi; unsigned __int16 *
0x1800381f0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800381f5  mov     ebx, eax
0x1800381f7  mov     r13d, 12Eh
0x1800381fd  test    eax, eax
0x1800381ff  jns     short loc_180038225
0x180038201  mov     rcx, cs:WPP_GLOBAL_Control
0x180038208  lea     rax, WPP_GLOBAL_Control
0x18003820f  cmp     rcx, rax
0x180038212  jz      loc_18003829A
0x180038218  test    [rcx+1Ch], r12b
0x18003821c  jz      short loc_18003829A
0x18003821e  lea     edx, [r12+0Ch]
0x180038223  jmp     short loc_180038287
0x180038225  mov     rax, [rsp+7A0h+var_768]
0x18003822a  test    rax, rax
0x18003822d  jz      short loc_18003823E
0x18003822f  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180038235  lea     r8, aSS_1; "%s\\%s"
0x18003823c  jnz     short loc_180038245
0x18003823e  lea     r8, aSS_2; "%s%s"
0x180038245  lea     rax, aRecoveryTempor; "Recovery\\Temporary"
0x18003824c  mov     r9, rdi
0x18003824f  mov     rdx, r13; unsigned __int64
0x180038252  mov     [rsp+7A0h+var_780], rax
0x180038257  lea     rcx, [rbp+6A0h+PathName]; unsigned __int16 *
0x18003825e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038263  mov     ebx, eax
0x180038265  test    eax, eax
0x180038267  jns     short loc_1800382A5
0x180038269  mov     rcx, cs:WPP_GLOBAL_Control
0x180038270  lea     rax, WPP_GLOBAL_Control
0x180038277  cmp     rcx, rax
0x18003827a  jz      short loc_18003829A
0x18003827c  test    [rcx+1Ch], r12b
0x180038280  jz      short loc_18003829A
0x180038282  mov     edx, 0Fh
0x180038287  mov     rcx, [rcx+10h]
0x18003828b  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180038292  mov     r9d, ebx
0x180038295  call    WPP_SF_d
0x18003829a  movzx   ebx, bx
0x18003829d  test    ebx, ebx
0x18003829f  jnz     loc_180038543
0x1800382a5  lea     rcx, [rbp+6A0h+PathName]; unsigned __int16 *
0x1800382ac  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x1800382b1  test    eax, eax
0x1800382b3  jz      short loc_1800382D1
0x1800382b5  lea     r8, [rbp+6A0h+PathName]
0x1800382bc  xor     ecx, ecx
0x1800382be  lea     rdx, aPathSNotFound; " Path %s not found"
0x1800382c5  call    UnattendLogW
0x1800382ca  xor     ebx, ebx
0x1800382cc  jmp     loc_180038584
0x1800382d1  mov     dword ptr [rsi], 1
0x1800382d7  xor     eax, eax
0x1800382d9  lea     rsi, [r15+4E8h]
0x1800382e0  cmp     ax, [rsi]
0x1800382e3  jnz     short loc_180038338
0x1800382e5  lea     rdx, [rsp+7A0h+pv]
0x1800382ea  xor     ecx, ecx
0x1800382ec  call    winreFindMainOsConfigDir
0x1800382f1  mov     ebx, eax
0x1800382f3  test    eax, eax
0x1800382f5  jz      short loc_18003832E
0x1800382f7  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800382fe  mov     [rsp+7A0h+var_778], 898h
0x180038306  mov     [rsp+7A0h+var_780], rcx
0x18003830b  lea     r8, aFailedToFindMa; "failed to find main os config directory"
0x180038312  mov     ecx, r12d
0x180038315  lea     rdx, aWinrecopywimba_1; "winreCopyWIMBackFromVolume %s (0x%x) in"...
0x18003831c  mov     r9d, eax
0x18003831f  call    UnattendLogW
0x180038324  mov     r14, [rsp+7A0h+pv]
0x180038329  jmp     loc_18003852A
0x18003832e  mov     r14, [rsp+7A0h+pv]
0x180038333  mov     rdi, r14
0x180038336  jmp     short loc_18003833B
0x180038338  mov     rdi, rsi
0x18003833b  lea     r8, [rbp+6A0h+PathName]; unsigned __int16 *
0x180038342  mov     rdx, r13; unsigned __int64
0x180038345  lea     rcx, [rsp+7A0h+ExistingFileName]; unsigned __int16 *
0x18003834a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003834f  mov     ebx, eax
0x180038351  test    eax, eax
0x180038353  jns     short loc_18003838A
0x180038355  mov     [rsp+7A0h+var_778], 8A6h
0x18003835d  lea     r8, aFailedToCopySr; "failed to copy src directory"
0x180038364  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003836b  mov     r9d, ebx
0x18003836e  mov     [rsp+7A0h+var_780], rcx
0x180038373  lea     rdx, aWinrecopywimba_1; "winreCopyWIMBackFromVolume %s (0x%x) in"...
0x18003837a  mov     ecx, r12d
0x18003837d  call    UnattendLogW
0x180038382  movzx   ebx, bx
0x180038385  jmp     loc_18003852A
0x18003838a  lea     rcx, [rsp+7A0h+ExistingFileName]
0x18003838f  call    winreAddTrailingBackslash
0x180038394  mov     ebx, eax
0x180038396  test    eax, eax
0x180038398  jz      short loc_1800383CC
0x18003839a  mov     [rsp+7A0h+var_778], 8A8h
0x1800383a2  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x1800383a9  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800383b0  mov     r9d, eax
0x1800383b3  mov     [rsp+7A0h+var_780], rcx
0x1800383b8  lea     rdx, aWinrecopywimba_1; "winreCopyWIMBackFromVolume %s (0x%x) in"...
0x1800383bf  mov     ecx, r12d
0x1800383c2  call    UnattendLogW
0x1800383c7  jmp     loc_18003852A
0x1800383cc  mov     r8, rsi; unsigned __int16 *
0x1800383cf  lea     rcx, [rbp+6A0h+NewFileName]; unsigned __int16 *
0x1800383d6  mov     rdx, r13; unsigned __int64
0x1800383d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800383de  mov     ebx, eax
0x1800383e0  test    eax, eax
0x1800383e2  jns     short loc_1800383F8
0x1800383e4  mov     [rsp+7A0h+var_778], 8ACh
0x1800383ec  lea     r8, aFailedToCopyIm; "failed to copy image location path"
0x1800383f3  jmp     loc_180038364
0x1800383f8  lea     rcx, [rbp+6A0h+NewFileName]
0x1800383ff  call    winreAddTrailingBackslash
0x180038404  mov     ebx, eax
0x180038406  test    eax, eax
0x180038408  jz      short loc_180038414
0x18003840a  mov     [rsp+7A0h+var_778], 8AEh
0x180038412  jmp     short loc_1800383A2
0x180038414  mov     rcx, rdi; lpFileName
0x180038417  call    winreOpenOrCreateDir
0x18003841c  mov     ebx, eax
0x18003841e  test    eax, eax
0x180038420  jz      short loc_180038436
0x180038422  mov     [rsp+7A0h+var_778], 8B5h
0x18003842a  lea     r8, aFailedToOpenDi; "failed to open directory"
0x180038431  jmp     loc_1800383A9
0x180038436  lea     r9, [rsp+7A0h+ExistingFileName]
0x18003843b  xor     ecx, ecx
0x18003843d  lea     r8, aWinreWim; "Winre.wim"
0x180038444  lea     rdx, [rbp+6A0h+PathName]
0x18003844b  call    winreGetSourceFile
0x180038450  mov     ebx, eax
0x180038452  test    eax, eax
0x180038454  jz      short loc_18003846A
0x180038456  mov     [rsp+7A0h+var_778], 8BEh
0x18003845e  lea     r8, aFailedToGetSou_2; "failed to get source file"
0x180038465  jmp     loc_1800383A9
0x18003846a  lea     r8, [rbp+6A0h+NewFileName]; unsigned __int16 *
0x180038471  mov     rcx, rdi; unsigned __int16 *
0x180038474  lea     rdx, aWinreWim; "Winre.wim"
0x18003847b  call    winreAddFileToDirPath
0x180038480  mov     ebx, eax
0x180038482  test    eax, eax
0x180038484  jz      short loc_18003849A
0x180038486  mov     [rsp+7A0h+var_778], 8C2h
0x18003848e  lea     r8, aFailedToAddWin_0; "failed to add winre.wim to directory pa"...
0x180038495  jmp     loc_1800383A9
0x18003849a  lea     rcx, [rsp+7A0h+ExistingFileName]; unsigned __int16 *
0x18003849f  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x1800384a4  test    eax, eax
0x1800384a6  jnz     short loc_1800384DE
0x1800384a8  lea     r8d, [rax+3]; dwFlags
0x1800384ac  lea     rdx, [rbp+6A0h+NewFileName]; lpNewFileName
0x1800384b3  lea     rcx, [rsp+7A0h+ExistingFileName]; lpExistingFileName
0x1800384b8  call    cs:__imp_MoveFileExW
0x1800384be  test    eax, eax
0x1800384c0  jnz     short loc_1800384DE
0x1800384c2  call    cs:__imp_GetLastError
0x1800384c8  mov     [rsp+7A0h+var_778], 8C8h
0x1800384d0  lea     r8, aFailedToMoveFi; "failed to move file"
0x1800384d7  mov     ebx, eax
0x1800384d9  jmp     loc_1800383A9
0x1800384de  lea     r9, [rsp+7A0h+ExistingFileName]
0x1800384e3  xor     ecx, ecx
0x1800384e5  lea     r8, aBootSdi; "boot.sdi"
0x1800384ec  lea     rdx, [rbp+6A0h+PathName]
0x1800384f3  call    winreGetSourceFile
0x1800384f8  mov     ebx, eax
0x1800384fa  test    eax, eax
0x1800384fc  jz      short loc_180038512
0x1800384fe  mov     [rsp+7A0h+var_778], 8D1h
0x180038506  lea     r8, aFailedToDelete_5; "failed to delete boot.sdi"
0x18003850d  jmp     loc_1800383A9
0x180038512  lea     rcx, [rsp+7A0h+ExistingFileName]; lpFileName
0x180038517  call    cs:__imp_DeleteFileW
0x18003851d  lea     rcx, [rbp+6A0h+PathName]; lpPathName
0x180038524  call    cs:__imp_RemoveDirectoryW
0x18003852a  test    r14, r14
0x18003852d  jz      short loc_180038538
0x18003852f  mov     rcx, r14; pv
0x180038532  call    cs:__imp_CoTaskMemFree
0x180038538  test    ebx, ebx
0x18003853a  jz      short loc_180038584
0x18003853c  jmp     short loc_180038570
0x18003853e  mov     ebx, 57h ; 'W'
0x180038543  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003854a  mov     [rsp+7A0h+var_778], 885h
0x180038552  mov     [rsp+7A0h+var_780], rcx
0x180038557  lea     r8, aFailedToAppend_9; "failed to append recovery\\temporary pa"...
0x18003855e  mov     ecx, r12d
0x180038561  lea     rdx, aWinrecopywimba_1; "winreCopyWIMBackFromVolume %s (0x%x) in"...
0x180038568  mov     r9d, ebx
0x18003856b  call    UnattendLogW
0x180038570  mov     r8d, ebx
0x180038573  lea     rdx, aWinrecopywimba_4; "winreCopyWIMBackFromVolume failed: 0x%x"
0x18003857a  mov     ecx, 1
0x18003857f  call    UnattendLogW
0x180038584  mov     eax, ebx
0x180038586  mov     rcx, [rbp+6A0h+var_40]
0x18003858d  xor     rcx, rsp; StackCookie
0x180038590  call    __security_check_cookie
0x180038595  mov     rbx, [rsp+7A0h+arg_18]
0x18003859d  add     rsp, 770h
0x1800385a4  pop     r15
0x1800385a6  pop     r14
0x1800385a8  pop     r13
0x1800385aa  pop     r12
0x1800385ac  pop     rdi
0x1800385ad  pop     rsi
0x1800385ae  pop     rbp
0x1800385af  retn
```
