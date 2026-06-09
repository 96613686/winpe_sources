# winreRestoreBackupXMLFromVolume(ushort const *,int *)

- ea: `0x18003875c`
- end: `0x18003900e`
- name: `?winreRestoreBackupXMLFromVolume@@YAKPEBGPEAH@Z`
- size: `2226`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003cbe8`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18003875c`
- `0x18004d3a0`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180038b51`
- `KERNEL32!CopyFileW` at `0x180038f4b`
- `KERNEL32!CopyFileW` at `0x180038b51`
- `KERNEL32!CopyFileW` at `0x180038f4b`
- `KERNEL32!GetLastError` at `0x180038b5b`
- `KERNEL32!GetLastError` at `0x180038cdd`
- `KERNEL32!GetLastError` at `0x180038f55`
- `KERNEL32!GetLastError` at `0x180038fc9`
- `KERNEL32!GetLastError` at `0x180038b5b`
- `KERNEL32!GetLastError` at `0x180038cdd`
- `KERNEL32!GetLastError` at `0x180038f55`
- `KERNEL32!GetLastError` at `0x180038fc9`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180038867`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180038867`
- `KERNEL32!FindFirstFileW` at `0x180038cce`
- `KERNEL32!FindFirstFileW` at `0x180038cce`
- `KERNEL32!FindNextFileW` at `0x180038e47`
- `KERNEL32!FindNextFileW` at `0x180038e47`
- `KERNEL32!FindClose` at `0x180038fa6`
- `KERNEL32!FindClose` at `0x180038fa6`

## string_xrefs

- `0x180038e06`: `failed to append path`
- `0x180038fbb`: `failed to append path`
- `0x180038964`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180038c8d`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180038dfc`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180038fd2`: `GetSystemWindowsDirectoryW failed 0x%x`
- `0x1800388f3`: `System32\Recovery\ReAgent.xml`
- `0x18003895d`: `failed to append reagent.xml`
- `0x18003896e`: `winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d`
- `0x180038cae`: `winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d`
- `0x180038e12`: `winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d`
- `0x180038a69`: `Backup xml found at %s`
- `0x180038e63`: `Backup xml found at %s`
- `0x180038b78`: `Copy file from %s to %s failed, 0x%x`
- `0x180038f72`: `Copy file from %s to %s failed, 0x%x`
- `0x180038b99`: `Backup xml copied to %s`
- `0x180038f8e`: `Backup xml copied to %s`
- `0x180038ca4`: `failed to create wildcard path`
- `0x180038a45`: `ReAgent.xml`
- `0x180038ad3`: `ReAgent.xml`
- `0x180038e28`: `ReAgent.xml`
- `0x180038ecd`: `ReAgent.xml`

## pseudocode

```c
__int64 __fastcall winreRestoreBackupXMLFromVolume(const unsigned __int16 *a1, int *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const unsigned __int16 *v6; // rsi
  _QWORD *v7; // r11
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  const wchar_t *v10; // r8
  int v11; // eax
  __int64 v12; // r11
  __int64 v13; // rcx
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  const unsigned __int16 *v22; // r8
  int v23; // edi
  HANDLE FirstFileW; // rdi
  DWORD v25; // eax
  int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  const unsigned __int16 *v29; // r8
  WCHAR *cAlternateFileName; // rax
  int v31; // eax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  DWORD LastError; // eax
  __int64 v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v39[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v41; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v42[606]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR NewFileName; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v44[606]; // [rsp+4F2h] [rbp+3F2h] BYREF
  WCHAR ExistingFileName; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v46[606]; // [rsp+752h] [rbp+652h] BYREF
  unsigned __int16 v47; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v48[606]; // [rsp+9B2h] [rbp+8B2h] BYREF
  WCHAR Buffer; // [rsp+C10h] [rbp+B10h] BYREF
  _BYTE v50[606]; // [rsp+C12h] [rbp+B12h] BYREF
  WCHAR FileName; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v52[606]; // [rsp+E72h] [rbp+D72h] BYREF

  v47 = 0;
  memset_0(v48, 0, 0x25Au);
  FileName = 0;
  memset_0(v52, 0, 0x25Au);
  v41 = 0;
  memset_0(v42, 0, 0x25Au);
  ExistingFileName = 0;
  memset_0(v46, 0, 0x25Au);
  NewFileName = 0;
  memset_0(v44, 0, 0x25Au);
  Buffer = 0;
  memset_0(v50, 0, 0x25Au);
  if ( !a2 )
    return 87;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( GetSystemWindowsDirectoryW(&Buffer, 0x12Eu) - 1 > 0x12D )
  {
    v4 = 0;
    LastError = GetLastError();
    UnattendLogW(1, L"GetSystemWindowsDirectoryW failed 0x%x", LastError);
    return v4;
  }
  v39[0] = 0;
  v5 = StringCchLengthW(&Buffer, 0x7FFFFFFFu, v39);
  LOWORD(v4) = v5;
  v6 = L"%s\\%s";
  if ( v5 >= 0 )
  {
    if ( !v39[0] || (v9 = L"%s\\%s", *(_WORD *)&v48[2 * v39[0] + 604] == 92) )
      v9 = L"%s%s";
    v5 = StringCchPrintfW(&NewFileName, 0x12Eu, v9, &Buffer, L"System32\\Recovery\\ReAgent.xml");
    LOWORD(v4) = v5;
    if ( v5 >= 0 )
      goto LABEL_19;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
      goto LABEL_15;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 14;
LABEL_15:
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v5);
    }
  }
  v4 = (unsigned __int16)v4;
  if ( (_WORD)v4 )
  {
    v37 = 1931;
    v10 = L"failed to append reagent.xml";
LABEL_18:
    UnattendLogW(
      2,
      L"winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d",
      v10,
      v4,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v37);
    return v4;
  }
LABEL_19:
  v39[0] = 0;
  if ( !a1 )
  {
    v4 = 87;
    goto LABEL_116;
  }
  v11 = StringCchLengthW(a1, 0x7FFFFFFFu, v39);
  LOWORD(v4) = v11;
  if ( v11 < 0 )
  {
    if ( (_UNKNOWN **)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 2) != 0 )
    {
      v13 = *(_QWORD *)(v12 + 16);
      v14 = 14;
LABEL_31:
      WPP_SF_d(v13, v14, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v11);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( !v39[0] || (v15 = L"%s\\%s", a1[v39[0] - 1] == 92) )
    v15 = L"%s%s";
  v11 = StringCchPrintfW(&v41, 0x12Eu, v15, a1, L"Recovery\\WindowsRE");
  LOWORD(v4) = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v14 = 15;
      goto LABEL_31;
    }
LABEL_32:
    v4 = (unsigned __int16)v4;
    if ( !(_WORD)v4 )
      goto LABEL_33;
LABEL_116:
    v37 = 1933;
    goto LABEL_117;
  }
LABEL_33:
  if ( !Utils::DoesFileExist(&v41, L"ReAgent.xml") )
  {
    UnattendLogW(0, L"Backup xml found at %s", &v41);
    v39[0] = 0;
    v16 = StringCchLengthW(&v41, 0x7FFFFFFFu, v39);
    LOWORD(v4) = v16;
    if ( v16 >= 0 )
    {
      if ( !v39[0] || FindFileData.cAlternateFileName[v39[0] + 13] == 92 )
        v6 = L"%s%s";
      v16 = StringCchPrintfW(&ExistingFileName, 0x12Eu, v6, &v41, L"ReAgent.xml");
      LOWORD(v4) = v16;
      if ( v16 >= 0 )
      {
        v4 = 0;
        goto LABEL_49;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = 15;
        goto LABEL_45;
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = 14;
LABEL_45:
        WPP_SF_d(v17[2], v18, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v16);
      }
    }
    v4 = (unsigned __int16)v4;
    if ( (_WORD)v4 )
    {
      v37 = 1939;
LABEL_117:
      v10 = L"failed to append path";
      goto LABEL_18;
    }
LABEL_49:
    if ( CopyFileW(&ExistingFileName, &NewFileName, 0) )
    {
      *a2 = 1;
      v4 = 0;
      UnattendLogW(0, L"Backup xml copied to %s", &NewFileName);
    }
    else
    {
      LODWORD(v36) = GetLastError();
      UnattendLogW(1, L"Copy file from %s to %s failed, 0x%x", &ExistingFileName, &NewFileName, v36);
    }
    return v4;
  }
  v39[0] = 0;
  v19 = StringCchLengthW(a1, 0x7FFFFFFFu, v39);
  LOWORD(v4) = v19;
  if ( v19 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = 14;
LABEL_63:
      WPP_SF_d(v20[2], v21, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v19);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  if ( !v39[0] || (v22 = L"%s\\%s", a1[v39[0] - 1] == 92) )
    v22 = L"%s%s";
  v19 = StringCchPrintfW(&v47, 0x12Eu, v22, a1, L"Recovery");
  LOWORD(v4) = v19;
  if ( v19 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = 15;
      goto LABEL_63;
    }
LABEL_64:
    v4 = (unsigned __int16)v4;
    if ( (_WORD)v4 )
    {
      v37 = 1953;
      goto LABEL_117;
    }
    goto LABEL_67;
  }
  v4 = 0;
LABEL_67:
  v23 = StringCchPrintfW(&FileName, 0x12Eu, L"%s\\*", &v47);
  if ( v23 < 0 )
  {
    UnattendLogW(
      2,
      L"winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d",
      L"failed to create wildcard path",
      (unsigned int)v23,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      1955);
    return (unsigned __int16)v23;
  }
  FirstFileW = FindFirstFileW(&FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v25 = GetLastError();
    v4 = v25;
    if ( v25 == 2 )
      UnattendLogW(0, L"%s not found", &FileName);
    else
      UnattendLogW(1, L"FindFirstFileW(%s) failed, last error 0x%x", &FileName, v25);
    return v4;
  }
  while ( (FindFileData.dwFileAttributes & 0x10) == 0 )
  {
LABEL_93:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_113;
  }
  v39[0] = 0;
  v26 = StringCchLengthW(&v47, 0x7FFFFFFFu, v39);
  LOWORD(v4) = v26;
  if ( v26 >= 0 )
  {
    if ( !v39[0] || (v29 = L"%s\\%s", *(_WORD *)&v46[2 * v39[0] + 604] == 92) )
      v29 = L"%s%s";
    cAlternateFileName = &FindFileData.cAlternateFileName[1];
    if ( FindFileData.cAlternateFileName[0] != 92 )
      cAlternateFileName = FindFileData.cAlternateFileName;
    v26 = StringCchPrintfW(&v41, 0x12Eu, v29, &v47, cAlternateFileName);
    LOWORD(v4) = v26;
    if ( v26 >= 0 )
    {
      v4 = 0;
      goto LABEL_92;
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v28 = 15;
      goto LABEL_87;
    }
  }
  else
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v28 = 14;
LABEL_87:
      WPP_SF_d(v27[2], v28, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v26);
    }
  }
  v4 = (unsigned __int16)v4;
  if ( (_WORD)v4 )
  {
    v38 = 1975;
LABEL_90:
    UnattendLogW(
      2,
      L"winreRestoreBackupXMLFromVolume %s (0x%x) in file %S line %d",
      L"failed to append path",
      v4,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v38);
    goto LABEL_113;
  }
LABEL_92:
  if ( Utils::DoesFileExist(&v41, L"ReAgent.xml") )
    goto LABEL_93;
  UnattendLogW(0, L"Backup xml found at %s", &v41);
  v39[0] = 0;
  v31 = StringCchLengthW(&v41, 0x7FFFFFFFu, v39);
  LOWORD(v4) = v31;
  if ( v31 < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v33 = 14;
      goto LABEL_106;
    }
    goto LABEL_107;
  }
  if ( !v39[0] || FindFileData.cAlternateFileName[v39[0] + 13] == 92 )
    v6 = L"%s%s";
  v31 = StringCchPrintfW(&ExistingFileName, 0x12Eu, v6, &v41, L"ReAgent.xml");
  LOWORD(v4) = v31;
  if ( v31 >= 0 )
  {
    v4 = 0;
  }
  else
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v33 = 15;
LABEL_106:
      WPP_SF_d(v32[2], v33, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v31);
    }
LABEL_107:
    v4 = (unsigned __int16)v4;
    if ( (_WORD)v4 )
    {
      v38 = 1981;
      goto LABEL_90;
    }
  }
  if ( CopyFileW(&ExistingFileName, &NewFileName, 0) )
  {
    *a2 = 1;
    UnattendLogW(0, L"Backup xml copied to %s", &NewFileName);
    v4 = 0;
  }
  else
  {
    LODWORD(v36) = GetLastError();
    UnattendLogW(1, L"Copy file from %s to %s failed, 0x%x", &ExistingFileName, &NewFileName, v36);
  }
LABEL_113:
  if ( FirstFileW )
    FindClose(FirstFileW);
  return v4;
}

```

## disassembly

```asm
0x18003875c  mov     [rsp-8+arg_10], rbx
0x180038761  mov     [rsp-8+arg_18], rsi
0x180038766  push    rbp
0x180038767  push    rdi
0x180038768  push    r12
0x18003876a  push    r13
0x18003876c  push    r14
0x18003876e  lea     rbp, [rsp-0FE0h]
0x180038776  mov     eax, 10E0h
0x18003877b  call    _alloca_probe
0x180038780  sub     rsp, rax
0x180038783  mov     rax, cs:__security_cookie
0x18003878a  xor     rax, rsp
0x18003878d  mov     [rbp+1000h+var_30], rax
0x180038794  mov     r14, rdx
0x180038797  mov     rdi, rcx
0x18003879a  xor     eax, eax
0x18003879c  lea     rcx, [rbp+1000h+var_74E]; void *
0x1800387a3  mov     ebx, 25Ah
0x1800387a8  mov     [rbp+1000h+var_750], ax
0x1800387af  mov     r8d, ebx; Size
0x1800387b2  xor     edx, edx; Val
0x1800387b4  call    memset_0
0x1800387b9  xor     eax, eax
0x1800387bb  lea     rcx, [rbp+1000h+var_28E]; void *
0x1800387c2  mov     r8d, ebx; Size
0x1800387c5  mov     [rbp+1000h+FileName], ax
0x1800387cc  xor     edx, edx; Val
0x1800387ce  call    memset_0
0x1800387d3  xor     eax, eax
0x1800387d5  lea     rcx, [rbp+1000h+var_E6E]; void *
0x1800387dc  mov     r8d, ebx; Size
0x1800387df  mov     [rbp+1000h+var_E70], ax
0x1800387e6  xor     edx, edx; Val
0x1800387e8  call    memset_0
0x1800387ed  xor     eax, eax
0x1800387ef  lea     rcx, [rbp+1000h+var_9AE]; void *
0x1800387f6  mov     r8d, ebx; Size
0x1800387f9  mov     [rbp+1000h+ExistingFileName], ax
0x180038800  xor     edx, edx; Val
0x180038802  call    memset_0
0x180038807  xor     eax, eax
0x180038809  lea     rcx, [rbp+1000h+var_C0E]; void *
0x180038810  mov     r8d, ebx; Size
0x180038813  mov     [rbp+1000h+NewFileName], ax
0x18003881a  xor     edx, edx; Val
0x18003881c  call    memset_0
0x180038821  xor     eax, eax
0x180038823  lea     rcx, [rbp+1000h+var_4EE]; void *
0x18003882a  mov     r8d, ebx; Size
0x18003882d  mov     [rbp+1000h+Buffer], ax
0x180038834  xor     edx, edx; Val
0x180038836  call    memset_0
0x18003883b  test    r14, r14
0x18003883e  jnz     short loc_180038849
0x180038840  lea     ebx, [r14+57h]
0x180038844  jmp     loc_180038FE1
0x180038849  xor     edx, edx; Val
0x18003884b  lea     rcx, [rsp+1100h+FindFileData]; void *
0x180038850  mov     r8d, 250h; Size
0x180038856  call    memset_0
0x18003885b  mov     edx, 12Eh; uSize
0x180038860  lea     rcx, [rbp+1000h+Buffer]; lpBuffer
0x180038867  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003886d  dec     eax
0x18003886f  cmp     eax, 12Dh
0x180038874  ja      loc_180038FC7
0x18003887a  lea     r8, [rsp+1100h+var_10D0]; unsigned __int64 *
0x18003887f  mov     [rsp+1100h+var_10D0], 0
0x180038888  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003888d  lea     rcx, [rbp+1000h+Buffer]; unsigned __int16 *
0x180038894  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038899  lea     r13, WPP_GLOBAL_Control
0x1800388a0  mov     ebx, eax
0x1800388a2  lea     rsi, aSS_1; "%s\\%s"
0x1800388a9  mov     r12d, 2
0x1800388af  test    eax, eax
0x1800388b1  jns     short loc_1800388D4
0x1800388b3  mov     r11, cs:WPP_GLOBAL_Control
0x1800388ba  cmp     r11, r13
0x1800388bd  jz      loc_18003894E
0x1800388c3  test    [r11+1Ch], r12b
0x1800388c7  jz      loc_18003894E
0x1800388cd  lea     edx, [r12+0Ch]
0x1800388d2  jmp     short loc_180038934
0x1800388d4  mov     rax, [rsp+1100h+var_10D0]
0x1800388d9  test    rax, rax
0x1800388dc  jz      short loc_1800388EC
0x1800388de  cmp     [rbp+rax*2+1000h+var_4F2], 5Ch ; '\'
0x1800388e7  mov     r8, rsi
0x1800388ea  jnz     short loc_1800388F3
0x1800388ec  lea     r8, aSS_2; "%s%s"
0x1800388f3  lea     rax, aSystem32Recove_2; "System32\\Recovery\\ReAgent.xml"
0x1800388fa  mov     edx, 12Eh; unsigned __int64
0x1800388ff  lea     r9, [rbp+1000h+Buffer]
0x180038906  mov     [rsp+1100h+var_10E0], rax
0x18003890b  lea     rcx, [rbp+1000h+NewFileName]; unsigned __int16 *
0x180038912  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038917  mov     ebx, eax
0x180038919  test    eax, eax
0x18003891b  jns     short loc_180038987
0x18003891d  mov     r11, cs:WPP_GLOBAL_Control
0x180038924  cmp     r11, r13
0x180038927  jz      short loc_18003894E
0x180038929  test    [r11+1Ch], r12b
0x18003892d  jz      short loc_18003894E
0x18003892f  mov     edx, 0Fh
0x180038934  mov     rcx, [r11+10h]
0x180038938  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18003893f  mov     r9d, eax
0x180038942  call    WPP_SF_d
0x180038947  mov     r11, cs:WPP_GLOBAL_Control
0x18003894e  movzx   ebx, bx
0x180038951  test    ebx, ebx
0x180038953  jz      short loc_18003898E
0x180038955  mov     [rsp+1100h+var_10D8], 78Bh
0x18003895d  lea     r8, aFailedToAppend_18; "failed to append reagent.xml"
0x180038964  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003896b  mov     r9d, ebx
0x18003896e  lea     rdx, aWinrerestoreba; "winreRestoreBackupXMLFromVolume %s (0x%"...
0x180038975  mov     [rsp+1100h+var_10E0], rax
0x18003897a  mov     ecx, r12d
0x18003897d  call    UnattendLogW
0x180038982  jmp     loc_180038FE1
0x180038987  mov     r11, cs:WPP_GLOBAL_Control
0x18003898e  mov     [rsp+1100h+var_10D0], 0
0x180038997  test    rdi, rdi
0x18003899a  jz      loc_180038FAE
0x1800389a0  lea     r8, [rsp+1100h+var_10D0]; unsigned __int64 *
0x1800389a5  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800389aa  mov     rcx, rdi; unsigned __int16 *
0x1800389ad  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800389b2  mov     ebx, eax
0x1800389b4  test    eax, eax
0x1800389b6  jns     short loc_1800389CE
0x1800389b8  cmp     r11, r13
0x1800389bb  jz      short loc_180038A3A
0x1800389bd  test    [r11+1Ch], r12b
0x1800389c1  jz      short loc_180038A3A
0x1800389c3  mov     rcx, [r11+10h]
0x1800389c7  mov     edx, 0Eh
0x1800389cc  jmp     short loc_180038A2B
0x1800389ce  mov     rax, [rsp+1100h+var_10D0]
0x1800389d3  test    rax, rax
0x1800389d6  jz      short loc_1800389E3
0x1800389d8  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800389de  mov     r8, rsi
0x1800389e1  jnz     short loc_1800389EA
0x1800389e3  lea     r8, aSS_2; "%s%s"
0x1800389ea  lea     rax, aRecoveryWindow+2; "Recovery\\WindowsRE"
0x1800389f1  mov     r9, rdi
0x1800389f4  mov     edx, 12Eh; unsigned __int64
0x1800389f9  mov     [rsp+1100h+var_10E0], rax
0x1800389fe  lea     rcx, [rbp+1000h+var_E70]; unsigned __int16 *
0x180038a05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038a0a  mov     ebx, eax
0x180038a0c  test    eax, eax
0x180038a0e  jns     short loc_180038A45
0x180038a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a17  cmp     rcx, r13
0x180038a1a  jz      short loc_180038A3A
0x180038a1c  test    [rcx+1Ch], r12b
0x180038a20  jz      short loc_180038A3A
0x180038a22  mov     rcx, [rcx+10h]
0x180038a26  mov     edx, 0Fh
0x180038a2b  mov     r9d, eax
0x180038a2e  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180038a35  call    WPP_SF_d
0x180038a3a  movzx   ebx, bx
0x180038a3d  test    ebx, ebx
0x180038a3f  jnz     loc_180038FB3
0x180038a45  lea     rdx, aReagentXml_2; "ReAgent.xml"
0x180038a4c  lea     rcx, [rbp+1000h+var_E70]; unsigned __int16 *
0x180038a53  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x180038a58  test    eax, eax
0x180038a5a  jnz     loc_180038BAC
0x180038a60  lea     r8, [rbp+1000h+var_E70]
0x180038a67  xor     ecx, ecx
0x180038a69  lea     rdx, aBackupXmlFound; "Backup xml found at %s"
0x180038a70  call    UnattendLogW
0x180038a75  lea     r8, [rsp+1100h+var_10D0]; unsigned __int64 *
0x180038a7a  mov     [rsp+1100h+var_10D0], 0
0x180038a83  mov     edx, 7FFFFFFFh; unsigned __int64
0x180038a88  lea     rcx, [rbp+1000h+var_E70]; unsigned __int16 *
0x180038a8f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038a94  mov     ebx, eax
0x180038a96  test    eax, eax
0x180038a98  jns     short loc_180038AB7
0x180038a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038aa1  cmp     rcx, r13
0x180038aa4  jz      loc_180038B2A
0x180038aaa  test    [rcx+1Ch], r12b
0x180038aae  jz      short loc_180038B2A
0x180038ab0  mov     edx, 0Eh
0x180038ab5  jmp     short loc_180038B17
0x180038ab7  mov     rax, [rsp+1100h+var_10D0]
0x180038abc  test    rax, rax
0x180038abf  jz      short loc_180038ACC
0x180038ac1  cmp     [rbp+rax*2+1000h+FindFileData.cAlternateFileName+1Ah], 5Ch ; '\'
0x180038aca  jnz     short loc_180038AD3
0x180038acc  lea     rsi, aSS_2; "%s%s"
0x180038ad3  lea     rax, aReagentXml_2; "ReAgent.xml"
0x180038ada  mov     r8, rsi; unsigned __int16 *
0x180038add  lea     r9, [rbp+1000h+var_E70]
0x180038ae4  mov     [rsp+1100h+var_10E0], rax
0x180038ae9  mov     edx, 12Eh; unsigned __int64
0x180038aee  lea     rcx, [rbp+1000h+ExistingFileName]; unsigned __int16 *
0x180038af5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038afa  mov     ebx, eax
0x180038afc  test    eax, eax
0x180038afe  jns     short loc_180038B3E
0x180038b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b07  cmp     rcx, r13
0x180038b0a  jz      short loc_180038B2A
0x180038b0c  test    [rcx+1Ch], r12b
0x180038b10  jz      short loc_180038B2A
0x180038b12  mov     edx, 0Fh
0x180038b17  mov     rcx, [rcx+10h]
0x180038b1b  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180038b22  mov     r9d, eax
0x180038b25  call    WPP_SF_d
0x180038b2a  movzx   ebx, bx
0x180038b2d  test    ebx, ebx
0x180038b2f  jz      short loc_180038B40
0x180038b31  mov     [rsp+1100h+var_10D8], 793h
0x180038b39  jmp     loc_180038FBB
0x180038b3e  xor     ebx, ebx
0x180038b40  xor     r8d, r8d; bFailIfExists
0x180038b43  lea     rdx, [rbp+1000h+NewFileName]; lpNewFileName
0x180038b4a  lea     rcx, [rbp+1000h+ExistingFileName]; lpExistingFileName
0x180038b51  call    cs:__imp_CopyFileW
0x180038b57  test    eax, eax
0x180038b59  jnz     short loc_180038B89
0x180038b5b  call    cs:__imp_GetLastError
0x180038b61  lea     r9, [rbp+1000h+NewFileName]
0x180038b68  mov     ecx, 1
0x180038b6d  lea     r8, [rbp+1000h+ExistingFileName]
0x180038b74  mov     dword ptr [rsp+1100h+var_10E0], eax
0x180038b78  lea     rdx, aCopyFileFromST; "Copy file from %s to %s failed, 0x%x"
0x180038b7f  call    UnattendLogW
0x180038b84  jmp     loc_180038FE1
0x180038b89  mov     dword ptr [r14], 1
0x180038b90  lea     r8, [rbp+1000h+NewFileName]
0x180038b97  xor     ebx, ebx
0x180038b99  lea     rdx, aBackupXmlCopie; "Backup xml copied to %s"
0x180038ba0  xor     ecx, ecx
0x180038ba2  call    UnattendLogW
0x180038ba7  jmp     loc_180038FE1
0x180038bac  lea     r8, [rsp+1100h+var_10D0]; unsigned __int64 *
0x180038bb1  mov     [rsp+1100h+var_10D0], 0
0x180038bba  mov     edx, 7FFFFFFFh; unsigned __int64
0x180038bbf  mov     rcx, rdi; unsigned __int16 *
0x180038bc2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038bc7  mov     ebx, eax
0x180038bc9  test    eax, eax
0x180038bcb  jns     short loc_180038BE6
0x180038bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180038bd4  cmp     rcx, r13
0x180038bd7  jz      short loc_180038C52
0x180038bd9  test    [rcx+1Ch], r12b
0x180038bdd  jz      short loc_180038C52
0x180038bdf  mov     edx, 0Eh
0x180038be4  jmp     short loc_180038C3F
0x180038be6  mov     rax, [rsp+1100h+var_10D0]
0x180038beb  test    rax, rax
0x180038bee  jz      short loc_180038BFB
0x180038bf0  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180038bf6  mov     r8, rsi
0x180038bf9  jnz     short loc_180038C02
0x180038bfb  lea     r8, aSS_2; "%s%s"
0x180038c02  lea     rax, aRecovery+2; "Recovery"
0x180038c09  mov     r9, rdi
0x180038c0c  mov     edx, 12Eh; unsigned __int64
0x180038c11  mov     [rsp+1100h+var_10E0], rax
0x180038c16  lea     rcx, [rbp+1000h+var_750]; unsigned __int16 *
0x180038c1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038c22  mov     ebx, eax
0x180038c24  test    eax, eax
0x180038c26  jns     short loc_180038C66
0x180038c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c2f  cmp     rcx, r13
0x180038c32  jz      short loc_180038C52
0x180038c34  test    [rcx+1Ch], r12b
0x180038c38  jz      short loc_180038C52
0x180038c3a  mov     edx, 0Fh
0x180038c3f  mov     rcx, [rcx+10h]
0x180038c43  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180038c4a  mov     r9d, eax
0x180038c4d  call    WPP_SF_d
0x180038c52  movzx   ebx, bx
0x180038c55  test    ebx, ebx
0x180038c57  jz      short loc_180038C68
0x180038c59  mov     [rsp+1100h+var_10D8], 7A1h
0x180038c61  jmp     loc_180038FBB
0x180038c66  xor     ebx, ebx
0x180038c68  lea     r9, [rbp+1000h+var_750]
0x180038c6f  mov     edx, 12Eh; unsigned __int64
0x180038c74  lea     r8, aS_0; "%s\\*"
0x180038c7b  lea     rcx, [rbp+1000h+FileName]; unsigned __int16 *
0x180038c82  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
  ... truncated ...
```
