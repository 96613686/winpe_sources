# ExecuteCabW

- ea: `0x18000f7b0`
- end: `0x18000ff2b`
- name: `ExecuteCabW`
- size: `1915`
- prototype: `HRESULT __stdcall(HWND hwnd, CABINFOW *pCab, LPVOID pReserved)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002ad4`
- `0x18000f660`
- `0x1800104c0`

## callees

- `0x1800022bc`
- `0x180003ce0`
- `0x180003e20`
- `0x180004880`
- `0x1800067dc`
- `0x180007454`
- `0x1800082f0`
- `0x18000c574`
- `0x18000cc80`
- `0x18000f32c`
- `0x18000f7b0`
- `0x180012110`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18000fa1b`
- `KERNEL32!GetTempFileNameW` at `0x18000fa1b`
- `KERNEL32!DeleteFileW` at `0x18000f90e`
- `KERNEL32!DeleteFileW` at `0x18000f99c`
- `KERNEL32!DeleteFileW` at `0x18000fa2c`
- `KERNEL32!DeleteFileW` at `0x18000f90e`
- `KERNEL32!DeleteFileW` at `0x18000f99c`
- `KERNEL32!DeleteFileW` at `0x18000fa2c`
- `KERNEL32!CopyFileW` at `0x18000fa46`
- `KERNEL32!CopyFileW` at `0x18000fa46`
- `ADVAPI32!RegCreateKeyExW` at `0x18000fe99`
- `ADVAPI32!RegCreateKeyExW` at `0x18000fe99`
- `ADVAPI32!RegCloseKey` at `0x18000fd38`
- `ADVAPI32!RegCloseKey` at `0x18000fd48`
- `ADVAPI32!RegCloseKey` at `0x18000fee8`
- `ADVAPI32!RegCloseKey` at `0x18000fd38`
- `ADVAPI32!RegCloseKey` at `0x18000fd48`
- `ADVAPI32!RegCloseKey` at `0x18000fee8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fce0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fd0d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fce0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fd0d`
- `ADVAPI32!RegSetValueExW` at `0x18000fedd`
- `ADVAPI32!RegSetValueExW` at `0x18000fedd`
- `SHLWAPI!StrRChrW` at `0x18000f9e9`
- `SHLWAPI!StrRChrW` at `0x18000f9e9`

## string_xrefs

- `0x18000fad3`: `ComponentName`
- `0x18000fa60`: `InfFile Rename: %1 becomes %2\n`
- `0x18000fbd1`: `PreRollBack`
- `0x18000fec9`: `InstallCabFile`

## pseudocode

```c
HRESULT __stdcall ExecuteCabW(HWND hwnd, CABINFOW *pCab, LPVOID pReserved)
{
  HRESULT FilesW; // r15d
  HRESULT v6; // ebx
  const unsigned __int16 **p_pszInf; // r14
  LPWSTR pszInf; // rdx
  int v9; // r13d
  int v10; // esi
  __int64 v11; // r8
  DWORD dwFlags; // eax
  const WCHAR *v13; // rcx
  const WCHAR *v14; // r10
  WCHAR *v15; // rdi
  PWSTR v16; // rbx
  WCHAR v17; // si
  size_t *pszSection; // r8
  DWORD v19; // eax
  DWORD v20; // ecx
  DWORD v21; // eax
  int v22; // eax
  WCHAR *v23; // rsi
  WCHAR *v24; // rsi
  const BYTE *pszCab; // rcx
  __int64 v26; // rax
  ULONG lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+54h] [rbp-ACh]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR v34[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszPathIn[264]; // [rsp+490h] [rbp+390h] BYREF
  size_t TempFileName[66]; // [rsp+6A0h] [rbp+5A0h] BYREF
  WCHAR pszMore[264]; // [rsp+8B0h] [rbp+7B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+AC0h] [rbp+9C0h] BYREF

  FilesW = 0;
  dwDisposition = 0;
  phkResult = 0;
  memset_0(pszPathIn, 0, 0x208u);
  AdvWriteToLog(L"ExecuteCab:");
  if ( (unsigned int)SaveGlobalContext() )
  {
    if ( !pCab )
      return -2147024809;
    p_pszInf = (const unsigned __int16 **)&pCab->pszInf;
    pszInf = pCab->pszInf;
    if ( !pszInf || !*pszInf )
      return -2147024809;
    v30 = 0;
    v9 = 0;
    v32 = 0;
    v10 = 0;
    AdvWriteToLog(L"Inf = %1\r\n");
    hWnd = hwnd;
    dwFlags = pCab->dwFlags;
    if ( (dwFlags & 0x100) != 0 )
    {
      dwFlags |= 0x40u;
      pCab->dwFlags = dwFlags;
    }
    if ( pCab->pszCab && *pCab->pszCab )
    {
      if ( !IsFullPath(*p_pszInf) )
      {
        FilesW = ExtractFilesW(v14, pCab->szSrcPath, 0, v13, 0, 0);
        if ( FilesW >= 0 )
          v9 = 1;
      }
    }
    else if ( (dwFlags & 0x40) != 0 )
    {
      pCab->dwFlags = dwFlags | 0x100;
    }
    if ( !(unsigned int)GetFullInfNameAndSrcDir((unsigned __int16 *)*p_pszInf, FileName, v11, pCab->szSrcPath) )
    {
      v6 = -2147024809;
      goto LABEL_17;
    }
    if ( (pCab->dwFlags & 0x40) != 0 && !v9 )
    {
      v16 = StrRChrW(FileName, 0, 0x5Cu);
      if ( v16 )
      {
        v17 = *v16;
        *v16 = 0;
        if ( GetTempFileNameW(FileName, L"INF", 0, (LPWSTR)TempFileName) )
        {
          DeleteFileW((LPCWSTR)TempFileName);
          *v16 = v17;
          if ( CopyFileW(FileName, (LPCWSTR)TempFileName, 0) )
          {
            AdvWriteToLog(L"InfFile Rename: %1 becomes %2\r\n", FileName, TempFileName);
            v32 = 1;
            StringCchCopyW(FileName, 0x104u, TempFileName);
          }
          v10 = 0;
        }
        else
        {
          v10 = v30;
        }
      }
    }
    pszSection = (size_t *)pCab->pszSection;
    if ( pszSection )
      StringCchCopyW(pszPathIn, 0x104u, pszSection);
    GetInfInstallSectionName(FileName, pszPathIn, 0x104u);
    if ( (int)GetTranslatedString(FileName, pszPathIn, L"ComponentName", v34, 0x104u, 0) < 0 && v34[0] )
      v34[0] = 0;
    if ( pCab->pszCab )
    {
      if ( *pCab->pszCab )
      {
        pszMore[0] = 0;
        GetTranslatedString(FileName, pszPathIn, L"CatalogName", pszMore, 0x104u, 0);
        if ( pszMore[0] )
        {
          if ( ExtractFilesW(pCab->pszCab, pCab->szSrcPath, 0, pszMore, 0, 0) >= 0 )
            v10 = 1;
          v30 = v10;
        }
      }
    }
    v19 = pCab->dwFlags;
    v20 = ~(unsigned __int8)(v19 >> 2) & 2 | 1;
    dwDisposition = v20;
    if ( (v19 & 4) != 0 )
      word_1800257D2 = 1;
    v21 = pCab->dwFlags;
    if ( (v21 & 0x80u) != 0 || (v21 & 0x40) != 0 )
    {
      hKey = 0;
      if ( (v21 & 0x40) != 0 )
      {
        pszPathOut[0] = 0;
        if ( (int)GetTranslatedString(FileName, pszPathIn, L"PreRollBack", pszPathOut, 0x104u, 0) >= 0 )
        {
          if ( pszPathOut[0] )
          {
            v22 = CoreInstall(FileName, pszPathOut, pCab->szSrcPath, 0, dwDisposition, 0);
            FilesW = v22;
            if ( v22 < 0 )
            {
              v6 = v22;
LABEL_17:
              if ( v9 || v32 )
                DeleteFileW(FileName);
              if ( v30 )
              {
                StringCchCopyW(pszPathOut, 0x104u, (size_t *)pCab->szSrcPath);
                v15 = pszMore;
                if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
                {
                  do
                    ++v15;
                  while ( *v15 == 92 );
                }
                PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v15, lpReserved);
                DeleteFileW(pszPathOut);
              }
              RestoreGlobalContext();
              goto LABEL_27;
            }
          }
        }
      }
      v6 = -2147418113;
      if ( !v34[0] )
        goto LABEL_17;
      StringCchCopyW((unsigned __int16 *)TempFileName, 0x104u, (size_t *)L"Software\\Microsoft\\Advanced INF Setup");
      v23 = v34;
      if ( !(unsigned int)PathIsUnc2(v34) && !IsExtendedLengthDosDevicePath(v34) && v34[0] == 92 )
      {
        do
          ++v23;
        while ( *v23 == 92 );
      }
      PathCchCombineEx((PWSTR)TempFileName, 0x104u, (PCWSTR)TempFileName, v23, lpReserved);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)TempFileName, 0, 0x2001Fu, &phkResult) )
      {
        RegOpenKeyExW(HKEY_CURRENT_USER, (LPCWSTR)TempFileName, 0, 0x20019u, &hKey);
        v6 = (unsigned int)VerifyBackupInfo(phkResult, hKey) == 0 ? 0x80004005 : 0;
      }
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v6 < 0 )
        goto LABEL_17;
      v21 = pCab->dwFlags;
      if ( v21 == 128 )
        goto LABEL_17;
      v20 = dwDisposition;
    }
    dwDisposition = ((v21 & 0x360 | 0x10) >> 2) | v20;
    v6 = CoreInstall(FileName, pszPathIn, pCab->szSrcPath, 0, dwDisposition, qword_180032318);
    if ( v6 >= 0 && pCab->pszCab && *pCab->pszCab && (pCab->dwFlags & 0x20) != 0 )
    {
      if ( FilesW != 3010 )
        FilesW = v6;
      v6 = FilesW;
      if ( v34[0] )
      {
        StringCchCopyW(pszPathIn, 0x104u, (size_t *)L"Software\\Microsoft\\Advanced INF Setup");
        v24 = v34;
        if ( !(unsigned int)PathIsUnc2(v34) && !IsExtendedLengthDosDevicePath(v34) && v34[0] == 92 )
        {
          do
            ++v24;
          while ( *v24 == 92 );
        }
        PathCchCombineEx(pszPathIn, 0x104u, pszPathIn, v24, lpReserved);
        if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathIn, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition) )
        {
          pszCab = (const BYTE *)pCab->pszCab;
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)&pszCab[2 * v26] );
          RegSetValueExW(phkResult, L"InstallCabFile", 0, 1u, pszCab, 2 * v26 + 2);
          RegCloseKey(phkResult);
        }
      }
    }
    goto LABEL_17;
  }
  v6 = -2147024882;
  p_pszInf = (const unsigned __int16 **)&pCab->pszInf;
LABEL_27:
  if ( *p_pszInf )
    AdvWriteToLog(L"ExecuteCab: End hr=0x%1!x! Inf=%2\r\n", (unsigned int)v6);
  else
    AdvWriteToLog(L"ExecuteCab: End hr=0x%1!x!\r\n", (unsigned int)v6);
  return v6;
}

```

## disassembly

```asm
0x18000f7b0  push    rbp
0x18000f7b2  push    rbx
0x18000f7b3  push    rsi
0x18000f7b4  push    rdi
0x18000f7b5  push    r12
0x18000f7b7  push    r13
0x18000f7b9  push    r14
0x18000f7bb  push    r15
0x18000f7bd  lea     rbp, [rsp-0BE8h]
0x18000f7c5  sub     rsp, 0CE8h
0x18000f7cc  mov     rax, cs:__security_cookie
0x18000f7d3  xor     rax, rsp
0x18000f7d6  mov     [rbp+0C20h+var_50], rax
0x18000f7dd  mov     rdi, rdx
0x18000f7e0  mov     rbx, rcx
0x18000f7e3  xor     r15d, r15d
0x18000f7e6  lea     rcx, [rbp+0C20h+pszPathIn]; void *
0x18000f7ed  xor     edx, edx; Val
0x18000f7ef  mov     [rsp+0D20h+dwDisposition], r15d
0x18000f7f4  mov     r8d, 208h; Size
0x18000f7fa  mov     [rsp+0D20h+phkResult], r15
0x18000f7ff  call    memset_0
0x18000f804  lea     rcx, aExecutecab_0; "ExecuteCab:"
0x18000f80b  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000f810  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x18000f815  test    eax, eax
0x18000f817  jnz     short loc_18000F827
0x18000f819  mov     ebx, 8007000Eh
0x18000f81e  lea     r14, [rdi+8]
0x18000f822  jmp     loc_18000F9A7
0x18000f827  test    rdi, rdi
0x18000f82a  jz      loc_18000FF03
0x18000f830  lea     r14, [rdi+8]
0x18000f834  mov     rdx, [r14]
0x18000f837  test    rdx, rdx
0x18000f83a  jz      loc_18000FF03
0x18000f840  cmp     [rdx], r15w
0x18000f844  jz      loc_18000FF03
0x18000f84a  lea     rcx, aInf1; "Inf = %1\r\n"
0x18000f851  mov     [rsp+0D20h+var_CCC], r15d
0x18000f856  mov     r13d, r15d
0x18000f859  mov     [rsp+0D20h+var_CC0], r15d
0x18000f85e  mov     esi, r15d
0x18000f861  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000f866  mov     ecx, 100h
0x18000f86b  mov     cs:hWnd, rbx
0x18000f872  mov     eax, [rdi+220h]
0x18000f878  test    ecx, eax
0x18000f87a  jz      short loc_18000F885
0x18000f87c  or      eax, 40h
0x18000f87f  mov     [rdi+220h], eax
0x18000f885  mov     r10, [rdi]
0x18000f888  xor     ebx, ebx
0x18000f88a  test    r10, r10
0x18000f88d  jz      short loc_18000F8C9
0x18000f88f  cmp     [r10], bx
0x18000f893  jz      short loc_18000F8C9
0x18000f895  mov     rcx, [r14]; unsigned __int16 *
0x18000f898  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000f89d  test    eax, eax
0x18000f89f  jnz     short loc_18000F8D5
0x18000f8a1  mov     r9, rcx; pszFileList
0x18000f8a4  mov     [rsp+0D20h+dwReserved], ebx; dwReserved
0x18000f8a8  mov     rcx, r10; pszCabName
0x18000f8ab  mov     [rsp+0D20h+lpReserved], rbx; lpReserved
0x18000f8b0  lea     rdx, [rdi+18h]; pszExpandDir
0x18000f8b4  xor     r8d, r8d; dwFlags
0x18000f8b7  call    ExtractFilesW
0x18000f8bc  mov     r15d, eax
0x18000f8bf  test    eax, eax
0x18000f8c1  js      short loc_18000F8D5
0x18000f8c3  lea     r13d, [rbx+1]
0x18000f8c7  jmp     short loc_18000F8D5
0x18000f8c9  test    al, 40h
0x18000f8cb  jz      short loc_18000F8D5
0x18000f8cd  or      eax, ecx
0x18000f8cf  mov     [rdi+220h], eax
0x18000f8d5  mov     rcx, [r14]; unsigned __int16 *
0x18000f8d8  lea     r12, [rdi+18h]
0x18000f8dc  mov     r9, r12; unsigned __int16 *
0x18000f8df  lea     rdx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000f8e6  call    ?GetFullInfNameAndSrcDir@@YAHPEBGPEAGK1K@Z; GetFullInfNameAndSrcDir(ushort const *,ushort *,ulong,ushort *,ulong)
0x18000f8eb  test    eax, eax
0x18000f8ed  jnz     loc_18000F9C6
0x18000f8f3  mov     ebx, 80070057h
0x18000f8f8  xor     r15d, r15d
0x18000f8fb  test    r13d, r13d
0x18000f8fe  jnz     short loc_18000F907
0x18000f900  cmp     [rsp+0D20h+var_CC0], r15d
0x18000f905  jz      short loc_18000F914
0x18000f907  lea     rcx, [rbp+0C20h+FileName]; lpFileName
0x18000f90e  call    cs:__imp_DeleteFileW
0x18000f914  cmp     [rsp+0D20h+var_CCC], r15d
0x18000f919  jz      loc_18000F9A2
0x18000f91f  mov     r8, r12; unsigned __int16 *
0x18000f922  lea     rcx, [rbp+0C20h+pszPathOut]; unsigned __int16 *
0x18000f929  mov     edx, 104h; unsigned __int64
0x18000f92e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f933  lea     r8, IsBackslash
0x18000f93a  xor     edx, edx
0x18000f93c  lea     rcx, [rbp+0C20h+pszMore]; unsigned __int16 *
0x18000f943  lea     rdi, [rbp+0C20h+pszMore]
0x18000f94a  call    PathIsUnc2
0x18000f94f  test    eax, eax
0x18000f951  jnz     short loc_18000F97A
0x18000f953  lea     rcx, [rbp+0C20h+pszMore]; unsigned __int16 *
0x18000f95a  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000f95f  test    al, al
0x18000f961  jnz     short loc_18000F97A
0x18000f963  mov     eax, 5Ch ; '\'
0x18000f968  cmp     [rbp+0C20h+pszMore], ax
0x18000f96f  jnz     short loc_18000F97A
0x18000f971  add     rdi, 2
0x18000f975  cmp     [rdi], ax
0x18000f978  jz      short loc_18000F971
0x18000f97a  mov     r9, rdi; pszMore
0x18000f97d  lea     r8, [rbp+0C20h+pszPathOut]; pszPathIn
0x18000f984  mov     edx, 104h; cchPathOut
0x18000f989  lea     rcx, [rbp+0C20h+pszPathOut]; pszPathOut
0x18000f990  call    PathCchCombineEx
0x18000f995  lea     rcx, [rbp+0C20h+pszPathOut]; lpFileName
0x18000f99c  call    cs:__imp_DeleteFileW
0x18000f9a2  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000f9a7  mov     r8, [r14]
0x18000f9aa  mov     edx, ebx
0x18000f9ac  test    r8, r8
0x18000f9af  jz      loc_18000FEF3
0x18000f9b5  lea     rcx, aExecutecabEndH; "ExecuteCab: End hr=0x%1!x! Inf=%2\r\n"
0x18000f9bc  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000f9c1  jmp     loc_18000FEFF
0x18000f9c6  test    byte ptr [rdi+220h], 40h
0x18000f9cd  jz      loc_18000FA96
0x18000f9d3  test    r13d, r13d
0x18000f9d6  jnz     loc_18000FA96
0x18000f9dc  xor     edx, edx; pszEnd
0x18000f9de  lea     r8d, [r13+5Ch]; wMatch
0x18000f9e2  lea     rcx, [rbp+0C20h+FileName]; pszStart
0x18000f9e9  call    cs:__imp_StrRChrW
0x18000f9ef  mov     rbx, rax
0x18000f9f2  xor     eax, eax
0x18000f9f4  test    rbx, rbx
0x18000f9f7  jz      loc_18000FA94
0x18000f9fd  movzx   esi, word ptr [rbx]
0x18000fa00  lea     r9, [rbp+0C20h+TempFileName]; lpTempFileName
0x18000fa07  xor     r8d, r8d; uUnique
0x18000fa0a  mov     [rbx], ax
0x18000fa0d  lea     rdx, aInf; "INF"
0x18000fa14  lea     rcx, [rbp+0C20h+FileName]; lpPathName
0x18000fa1b  call    cs:__imp_GetTempFileNameW
0x18000fa21  test    eax, eax
0x18000fa23  jz      short loc_18000FA90
0x18000fa25  lea     rcx, [rbp+0C20h+TempFileName]; lpFileName
0x18000fa2c  call    cs:__imp_DeleteFileW
0x18000fa32  xor     r8d, r8d; bFailIfExists
0x18000fa35  mov     [rbx], si
0x18000fa38  lea     rdx, [rbp+0C20h+TempFileName]; lpNewFileName
0x18000fa3f  lea     rcx, [rbp+0C20h+FileName]; lpExistingFileName
0x18000fa46  call    cs:__imp_CopyFileW
0x18000fa4c  xor     ebx, ebx
0x18000fa4e  test    eax, eax
0x18000fa50  jz      short loc_18000FA8C
0x18000fa52  lea     r8, [rbp+0C20h+TempFileName]
0x18000fa59  lea     rdx, [rbp+0C20h+FileName]
0x18000fa60  lea     rcx, aInffileRename1; "InfFile Rename: %1 becomes %2\r\n"
0x18000fa67  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000fa6c  lea     r8, [rbp+0C20h+TempFileName]; unsigned __int16 *
0x18000fa73  mov     [rsp+0D20h+var_CC0], 1
0x18000fa7b  mov     edx, 104h; unsigned __int64
0x18000fa80  lea     rcx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000fa87  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa8c  mov     esi, ebx
0x18000fa8e  jmp     short loc_18000FA96
0x18000fa90  mov     esi, [rsp+0D20h+var_CCC]
0x18000fa94  xor     ebx, ebx
0x18000fa96  mov     r8, [rdi+10h]; unsigned __int16 *
0x18000fa9a  test    r8, r8
0x18000fa9d  jz      short loc_18000FAB0
0x18000fa9f  mov     edx, 104h; unsigned __int64
0x18000faa4  lea     rcx, [rbp+0C20h+pszPathIn]; unsigned __int16 *
0x18000faab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fab0  mov     r8d, 104h; unsigned int
0x18000fab6  lea     rdx, [rbp+0C20h+pszPathIn]; unsigned __int16 *
0x18000fabd  lea     rcx, [rbp+0C20h+FileName]; lpFileName
0x18000fac4  call    ?GetInfInstallSectionName@@YAKPEBGPEAGK@Z; GetInfInstallSectionName(ushort const *,ushort *,ulong)
0x18000fac9  lea     r9, [rsp+0D20h+var_CB0]; unsigned __int16 *
0x18000face  mov     qword ptr [rsp+0D20h+dwReserved], rbx; unsigned int *
0x18000fad3  lea     r8, KeyName; "ComponentName"
0x18000fada  mov     dword ptr [rsp+0D20h+lpReserved], 104h; unsigned int
0x18000fae2  lea     rdx, [rbp+0C20h+pszPathIn]; lpAppName
0x18000fae9  lea     rcx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000faf0  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000faf5  test    eax, eax
0x18000faf7  jns     short loc_18000FB05
0x18000faf9  cmp     [rsp+0D20h+var_CB0], bx
0x18000fafe  jz      short loc_18000FB05
0x18000fb00  mov     [rsp+0D20h+var_CB0], bx
0x18000fb05  mov     rax, [rdi]
0x18000fb08  test    rax, rax
0x18000fb0b  jz      short loc_18000FB7C
0x18000fb0d  cmp     [rax], bx
0x18000fb10  jz      short loc_18000FB7C
0x18000fb12  mov     qword ptr [rsp+0D20h+dwReserved], rbx; unsigned int *
0x18000fb17  lea     r9, [rbp+0C20h+pszMore]; unsigned __int16 *
0x18000fb1e  lea     r8, aCatalogname; "CatalogName"
0x18000fb25  mov     dword ptr [rsp+0D20h+lpReserved], 104h; unsigned int
0x18000fb2d  lea     rdx, [rbp+0C20h+pszPathIn]; lpAppName
0x18000fb34  mov     [rbp+0C20h+pszMore], bx
0x18000fb3b  lea     rcx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000fb42  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000fb47  cmp     [rbp+0C20h+pszMore], bx
0x18000fb4e  jz      short loc_18000FB7C
0x18000fb50  mov     rcx, [rdi]; pszCabName
0x18000fb53  lea     r9, [rbp+0C20h+pszMore]; pszFileList
0x18000fb5a  mov     [rsp+0D20h+dwReserved], ebx; dwReserved
0x18000fb5e  xor     r8d, r8d; dwFlags
0x18000fb61  mov     rdx, r12; pszExpandDir
0x18000fb64  mov     [rsp+0D20h+lpReserved], rbx; dwFlags
0x18000fb69  call    ExtractFilesW
0x18000fb6e  test    eax, eax
0x18000fb70  mov     eax, 1
0x18000fb75  cmovns  esi, eax
0x18000fb78  mov     [rsp+0D20h+var_CCC], esi
0x18000fb7c  mov     eax, [rdi+220h]
0x18000fb82  mov     esi, 1
0x18000fb87  mov     ecx, eax
0x18000fb89  shr     ecx, 2
0x18000fb8c  not     ecx
0x18000fb8e  and     ecx, 2
0x18000fb91  or      ecx, esi
0x18000fb93  mov     [rsp+0D20h+dwDisposition], ecx
0x18000fb97  test    al, 4
0x18000fb99  jz      short loc_18000FBA2
0x18000fb9b  mov     cs:word_1800257D2, si
0x18000fba2  mov     eax, [rdi+220h]
0x18000fba8  mov     edx, eax
0x18000fbaa  and     edx, 40h
0x18000fbad  test    al, al
0x18000fbaf  js      short loc_18000FBBC
0x18000fbb1  test    edx, edx
0x18000fbb3  jnz     short loc_18000FBBC
0x18000fbb5  xor     esi, esi
0x18000fbb7  jmp     loc_18000FD6B
0x18000fbbc  mov     [rsp+0D20h+hKey], rbx
0x18000fbc1  test    edx, edx
0x18000fbc3  jz      short loc_18000FC3B
0x18000fbc5  mov     qword ptr [rsp+0D20h+dwReserved], rbx; unsigned int *
0x18000fbca  lea     r9, [rbp+0C20h+pszPathOut]; unsigned __int16 *
0x18000fbd1  lea     r8, aPrerollback; "PreRollBack"
0x18000fbd8  mov     dword ptr [rsp+0D20h+lpReserved], 104h; unsigned int
0x18000fbe0  lea     rdx, [rbp+0C20h+pszPathIn]; lpAppName
0x18000fbe7  mov     [rbp+0C20h+pszPathOut], bx
0x18000fbee  lea     rcx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000fbf5  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000fbfa  test    eax, eax
0x18000fbfc  js      short loc_18000FC3B
0x18000fbfe  cmp     [rbp+0C20h+pszPathOut], bx
0x18000fc05  jz      short loc_18000FC3B
0x18000fc07  mov     eax, [rsp+0D20h+dwDisposition]
0x18000fc0b  lea     rdx, [rbp+0C20h+pszPathOut]; unsigned __int16 *
0x18000fc12  mov     qword ptr [rsp+0D20h+dwReserved], rbx; unsigned __int16 *
0x18000fc17  lea     rcx, [rbp+0C20h+FileName]; unsigned __int16 *
0x18000fc1e  xor     r9d, r9d; unsigned int
0x18000fc21  mov     dword ptr [rsp+0D20h+lpReserved], eax; ULONG
0x18000fc25  mov     r8, r12; unsigned __int16 *
0x18000fc28  call    ?CoreInstall@@YAJPEBG00KK0@Z; CoreInstall(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *)
0x18000fc2d  mov     r15d, eax
0x18000fc30  test    eax, eax
0x18000fc32  jns     short loc_18000FC3B
0x18000fc34  mov     ebx, eax
0x18000fc36  jmp     loc_18000F8F8
0x18000fc3b  xor     eax, eax
0x18000fc3d  mov     ebx, 8000FFFFh
0x18000fc42  cmp     [rsp+0D20h+var_CB0], ax
0x18000fc47  jz      loc_18000F8F8
0x18000fc4d  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000fc54  mov     edx, 104h; unsigned __int64
0x18000fc59  lea     rcx, [rbp+0C20h+TempFileName]; unsigned __int16 *
0x18000fc60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fc65  lea     r8, IsBackslash
0x18000fc6c  xor     edx, edx
0x18000fc6e  lea     rcx, [rsp+0D20h+var_CB0]; unsigned __int16 *
0x18000fc73  lea     rsi, [rsp+0D20h+var_CB0]
0x18000fc78  call    PathIsUnc2
0x18000fc7d  test    eax, eax
0x18000fc7f  jnz     short loc_18000FCA4
0x18000fc81  lea     rcx, [rsp+0D20h+var_CB0]; unsigned __int16 *
0x18000fc86  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000fc8b  test    al, al
0x18000fc8d  jnz     short loc_18000FCA4
0x18000fc8f  mov     eax, 5Ch ; '\'
0x18000fc94  cmp     [rsp+0D20h+var_CB0], ax
0x18000fc99  jnz     short loc_18000FCA4
0x18000fc9b  add     rsi, 2
0x18000fc9f  cmp     [rsi], ax
0x18000fca2  jz      short loc_18000FC9B
0x18000fca4  mov     r9, rsi; pszMore
0x18000fca7  lea     r8, [rbp+0C20h+TempFileName]; pszPathIn
0x18000fcae  mov     edx, 104h; cchPathOut
0x18000fcb3  lea     rcx, [rbp+0C20h+TempFileName]; pszPathOut
0x18000fcba  call    PathCchCombineEx
  ... truncated ...
```
