# winreScanForWinReWim(ushort const *,ushort *,unsigned __int64,int *,int *)

- ea: `0x1800393e4`
- end: `0x180039b31`
- name: `?winreScanForWinReWim@@YAKPEBGPEAG_KPEAH3@Z`
- size: `1869`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int64@<r8>, int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18003bfbc`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800393e4`
- `0x18004d3a0`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800398d7`
- `KERNEL32!GetLastError` at `0x1800398d7`
- `KERNEL32!FindFirstFileW` at `0x1800398c8`
- `KERNEL32!FindFirstFileW` at `0x1800398c8`
- `KERNEL32!FindNextFileW` at `0x180039a6b`
- `KERNEL32!FindNextFileW` at `0x180039a6b`
- `KERNEL32!FindClose` at `0x180039af2`
- `KERNEL32!FindClose` at `0x180039af2`

## string_xrefs

- `0x1800395a7`: `failed to append path`
- `0x180039a1a`: `failed to append path`
- `0x180039617`: `failed to copy string`
- `0x180039ac8`: `failed to copy string`
- `0x18003959d`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003961e`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039a03`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039ab1`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x1800398b0`: `failed to create wildcard path`
- `0x180039850`: `Winre.wim found in the temporary staging location at  %s`
- `0x1800397c1`: `Temporary`

## pseudocode

```c
__int64 __fastcall winreScanForWinReWim(const unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, int *a4, int *a5)
{
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // r8
  int v12; // edi
  const wchar_t *v13; // r8
  const unsigned __int16 *v14; // r8
  __int64 v15; // r11
  __int64 v16; // rcx
  __int64 v17; // rdx
  const unsigned __int16 *v18; // r8
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  int v21; // edi
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  WCHAR *cFileName; // rax
  int v26; // edi
  int v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v32; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v33[606]; // [rsp+292h] [rbp+192h] BYREF
  unsigned __int16 v34; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v35[606]; // [rsp+4F2h] [rbp+3F2h] BYREF
  WCHAR FileName; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v37[606]; // [rsp+752h] [rbp+652h] BYREF
  unsigned __int16 v38; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v39[606]; // [rsp+9B2h] [rbp+8B2h] BYREF

  v34 = 0;
  memset_0(v35, 0, 0x25Au);
  FileName = 0;
  memset_0(v37, 0, 0x25Au);
  v32 = 0;
  memset_0(v33, 0, 0x25Au);
  v38 = 0;
  memset_0(v39, 0, 0x25Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || !a2 || !a4 || !a5 )
  {
    v8 = 87;
    UnattendLogW(1, L"invalid parameter");
    return (unsigned int)v8;
  }
  *a5 = 0;
  *a4 = 0;
  v30[0] = 0;
  v8 = StringCchLengthW(a1, 0x7FFFFFFFu, v30);
  if ( v8 >= 0 )
  {
    if ( !v30[0] || (v11 = L"%s\\%s", a1[v30[0] - 1] == 92) )
      v11 = L"%s%s";
    v8 = StringCchPrintfW(&v32, 0x12Eu, v11, a1, L"Recovery\\WindowsRE");
    if ( v8 >= 0 )
    {
      v8 = 0;
      goto LABEL_21;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 15;
      goto LABEL_16;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 14;
LABEL_16:
      WPP_SF_d(v9[2], v10, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v8);
    }
  }
  v8 = (unsigned __int16)v8;
  if ( (_WORD)v8 )
  {
    v28 = 3098;
LABEL_19:
    UnattendLogW(
      2,
      L"winreScanForWinReWim %s (0x%x) in file %S line %d",
      L"failed to append path",
      (unsigned int)v8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v28);
    return (unsigned int)v8;
  }
LABEL_21:
  if ( !Utils::DoesFileExist(&v32, L"Winre.wim") )
  {
    UnattendLogW(0, L"Winre.wim found at %s", &v32);
    v12 = StringCchCopyW(a2, 0x12Eu, &v32);
    if ( v12 < 0 )
    {
      v29 = 3103;
LABEL_24:
      v13 = L"failed to copy string";
LABEL_25:
      UnattendLogW(
        2,
        L"winreScanForWinReWim %s (0x%x) in file %S line %d",
        v13,
        (unsigned int)v12,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        v29);
      return (unsigned __int16)v12;
    }
    *a5 = 1;
    goto LABEL_27;
  }
  v30[0] = 0;
  v8 = StringCchLengthW(a1, 0x7FFFFFFFu, v30);
  if ( v8 >= 0 )
  {
    if ( !v30[0] || (v14 = L"%s\\%s", a1[v30[0] - 1] == 92) )
      v14 = L"%s%s";
    v8 = StringCchPrintfW(&v34, 0x12Eu, v14, a1, L"Recovery");
    if ( v8 >= 0 )
      goto LABEL_42;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (unsigned int)v8);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v8);
  }
  v8 = (unsigned __int16)v8;
  if ( (_WORD)v8 )
  {
    v28 = 3109;
    goto LABEL_19;
  }
LABEL_42:
  v30[0] = 0;
  v8 = StringCchLengthW(&v34, 0x7FFFFFFFu, v30);
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN **)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 2) != 0 )
    {
      v16 = *(_QWORD *)(v15 + 16);
      v17 = 14;
LABEL_53:
      WPP_SF_d(v16, v17, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v8);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  if ( !v30[0] || (v18 = L"%s\\%s", *(_WORD *)&v33[2 * v30[0] + 604] == 92) )
    v18 = L"%s%s";
  v8 = StringCchPrintfW(&v38, 0x12Eu, v18, &v34, L"Temporary");
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v17 = 15;
      goto LABEL_53;
    }
LABEL_54:
    v8 = (unsigned __int16)v8;
    if ( (_WORD)v8 )
    {
      v28 = 3112;
      goto LABEL_19;
    }
    goto LABEL_57;
  }
  v8 = 0;
LABEL_57:
  if ( !Utils::DoesFileExist(&v38, L"Winre.wim") )
  {
    UnattendLogW(0, L"Winre.wim found in the temporary staging location at  %s", &v32);
    v12 = StringCchCopyW(a2, 0x12Eu, &v38);
    if ( v12 < 0 )
    {
      v29 = 3122;
      goto LABEL_24;
    }
LABEL_27:
    *a4 = 1;
    return (unsigned int)v8;
  }
  v12 = StringCchPrintfW(&FileName, 0x12Eu, L"%s\\*", &v34);
  if ( v12 < 0 )
  {
    v29 = 3127;
    v13 = L"failed to create wildcard path";
    goto LABEL_25;
  }
  FirstFileW = FindFirstFileW(&FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 2 )
      UnattendLogW(0, L"%s not found", &FileName);
    else
      UnattendLogW(1, L"FindFirstFileW(%s) failed, last error 0x%x", &FileName, LastError);
    return (unsigned int)v8;
  }
  v21 = 0;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      goto LABEL_86;
    v30[0] = 0;
    v8 = StringCchLengthW(&v34, 0x7FFFFFFFu, v30);
    if ( v8 >= 0 )
    {
      if ( !v30[0] || (v24 = L"%s\\%s", *(_WORD *)&v33[2 * v30[0] + 604] == 92) )
        v24 = L"%s%s";
      cFileName = &FindFileData.cFileName[1];
      if ( FindFileData.cFileName[0] != 92 )
        cFileName = FindFileData.cFileName;
      v8 = StringCchPrintfW(&v32, 0x12Eu, v24, &v34, cFileName);
      if ( v8 >= 0 )
      {
        v8 = 0;
        goto LABEL_85;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v23 = 15;
        goto LABEL_81;
      }
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v23 = 14;
LABEL_81:
        WPP_SF_d(v22[2], v23, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v8);
      }
    }
    v8 = (unsigned __int16)v8;
    if ( (_WORD)v8 )
    {
      UnattendLogW(
        2,
        L"winreScanForWinReWim %s (0x%x) in file %S line %d",
        L"failed to append path",
        (unsigned __int16)v8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        3149);
      goto LABEL_92;
    }
LABEL_85:
    UnattendLogW(0, L"Scanning %s", &v32);
    if ( !Utils::DoesFileExist(&v32, L"Winre.wim") )
      break;
LABEL_86:
    if ( FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( (unsigned int)++v21 < 0x64 )
        continue;
    }
    goto LABEL_92;
  }
  UnattendLogW(0, L"Winre.wim found at %s", &v32);
  v26 = StringCchCopyW(a2, 0x12Eu, &v32);
  if ( v26 >= 0 )
  {
    *a4 = 1;
  }
  else
  {
    UnattendLogW(
      2,
      L"winreScanForWinReWim %s (0x%x) in file %S line %d",
      L"failed to copy string",
      (unsigned int)v26,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      3154);
    v8 = (unsigned __int16)v26;
  }
LABEL_92:
  if ( FirstFileW )
    FindClose(FirstFileW);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800393e4  push    rbp
0x1800393e6  push    rbx
0x1800393e7  push    rsi
0x1800393e8  push    rdi
0x1800393e9  push    r13
0x1800393eb  push    r14
0x1800393ed  push    r15
0x1800393ef  lea     rbp, [rsp-0B20h]
0x1800393f7  sub     rsp, 0C20h
0x1800393fe  mov     rax, cs:__security_cookie
0x180039405  xor     rax, rsp
0x180039408  mov     [rbp+0B50h+var_40], rax
0x18003940f  mov     rsi, [rbp+0B50h+arg_20]
0x180039416  mov     r15, rdx
0x180039419  mov     rdi, rcx
0x18003941c  xor     eax, eax
0x18003941e  mov     ebx, 25Ah
0x180039423  mov     [rbp+0B50h+var_760], ax
0x18003942a  mov     r8d, ebx; Size
0x18003942d  lea     rcx, [rbp+0B50h+var_75E]; void *
0x180039434  xor     edx, edx; Val
0x180039436  mov     r14, r9
0x180039439  call    memset_0
0x18003943e  xor     eax, eax
0x180039440  lea     rcx, [rbp+0B50h+var_4FE]; void *
0x180039447  mov     r8d, ebx; Size
0x18003944a  mov     [rbp+0B50h+FileName], ax
0x180039451  xor     edx, edx; Val
0x180039453  call    memset_0
0x180039458  xor     eax, eax
0x18003945a  lea     rcx, [rbp+0B50h+var_9BE]; void *
0x180039461  mov     r8d, ebx; Size
0x180039464  mov     [rbp+0B50h+var_9C0], ax
0x18003946b  xor     edx, edx; Val
0x18003946d  call    memset_0
0x180039472  xor     eax, eax
0x180039474  lea     rcx, [rbp+0B50h+var_29E]; void *
0x18003947b  mov     r8d, ebx; Size
0x18003947e  mov     [rbp+0B50h+var_2A0], ax
0x180039485  xor     edx, edx; Val
0x180039487  call    memset_0
0x18003948c  xor     edx, edx; Val
0x18003948e  lea     r8d, [rbx-0Ah]; Size
0x180039492  lea     rcx, [rsp+0C50h+FindFileData]; void *
0x180039497  call    memset_0
0x18003949c  test    rdi, rdi
0x18003949f  jz      loc_180039AFA
0x1800394a5  test    r15, r15
0x1800394a8  jz      loc_180039AFA
0x1800394ae  test    r14, r14
0x1800394b1  jz      loc_180039AFA
0x1800394b7  test    rsi, rsi
0x1800394ba  jz      loc_180039AFA
0x1800394c0  mov     dword ptr [rsi], 0
0x1800394c6  lea     r8, [rsp+0C50h+var_C20]; unsigned __int64 *
0x1800394cb  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800394d0  mov     dword ptr [r14], 0
0x1800394d7  mov     rcx, rdi; unsigned __int16 *
0x1800394da  mov     [rsp+0C50h+var_C20], 0
0x1800394e3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800394e8  mov     ebx, eax
0x1800394ea  mov     r13d, 2
0x1800394f0  lea     rax, WPP_GLOBAL_Control
0x1800394f7  test    ebx, ebx
0x1800394f9  jns     short loc_180039517
0x1800394fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180039502  cmp     rcx, rax
0x180039505  jz      loc_18003958E
0x18003950b  test    [rcx+1Ch], r13b
0x18003950f  jz      short loc_18003958E
0x180039511  lea     edx, [r13+0Ch]
0x180039515  jmp     short loc_18003957B
0x180039517  mov     rax, [rsp+0C50h+var_C20]
0x18003951c  test    rax, rax
0x18003951f  jz      short loc_180039530
0x180039521  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180039527  lea     r8, aSS_1; "%s\\%s"
0x18003952e  jnz     short loc_180039537
0x180039530  lea     r8, aSS_2; "%s%s"
0x180039537  lea     rax, aRecoveryWindow+2; "Recovery\\WindowsRE"
0x18003953e  mov     r9, rdi
0x180039541  mov     edx, 12Eh; unsigned __int64
0x180039546  mov     [rsp+0C50h+var_C30], rax
0x18003954b  lea     rcx, [rbp+0B50h+var_9C0]; unsigned __int16 *
0x180039552  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039557  mov     ebx, eax
0x180039559  test    eax, eax
0x18003955b  jns     short loc_1800395C7
0x18003955d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039564  lea     rax, WPP_GLOBAL_Control
0x18003956b  cmp     rcx, rax
0x18003956e  jz      short loc_18003958E
0x180039570  test    [rcx+1Ch], r13b
0x180039574  jz      short loc_18003958E
0x180039576  mov     edx, 0Fh
0x18003957b  mov     rcx, [rcx+10h]
0x18003957f  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180039586  mov     r9d, ebx
0x180039589  call    WPP_SF_d
0x18003958e  movzx   ebx, bx
0x180039591  test    ebx, ebx
0x180039593  jz      short loc_1800395C9
0x180039595  mov     [rsp+0C50h+var_C28], 0C1Ah
0x18003959d  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800395a4  mov     r9d, ebx
0x1800395a7  lea     r8, aFailedToAppend_7; "failed to append path"
0x1800395ae  mov     [rsp+0C50h+var_C30], rax
0x1800395b3  lea     rdx, aWinrescanforwi; "winreScanForWinReWim %s (0x%x) in file "...
0x1800395ba  mov     ecx, r13d
0x1800395bd  call    UnattendLogW
0x1800395c2  jmp     loc_180039B0E
0x1800395c7  xor     ebx, ebx
0x1800395c9  lea     rdx, aWinreWim; "Winre.wim"
0x1800395d0  lea     rcx, [rbp+0B50h+var_9C0]; unsigned __int16 *
0x1800395d7  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x1800395dc  test    eax, eax
0x1800395de  jnz     short loc_180039656
0x1800395e0  lea     r8, [rbp+0B50h+var_9C0]
0x1800395e7  xor     ecx, ecx
0x1800395e9  lea     rdx, aWinreWimFoundA; "Winre.wim found at %s"
0x1800395f0  call    UnattendLogW
0x1800395f5  lea     r8, [rbp+0B50h+var_9C0]; unsigned __int16 *
0x1800395fc  mov     edx, 12Eh; unsigned __int64
0x180039601  mov     rcx, r15; unsigned __int16 *
0x180039604  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039609  mov     edi, eax
0x18003960b  test    eax, eax
0x18003960d  jns     short loc_180039644
0x18003960f  mov     [rsp+0C50h+var_C28], 0C1Fh
0x180039617  lea     r8, aFailedToCopySt; "failed to copy string"
0x18003961e  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039625  mov     r9d, edi
0x180039628  lea     rdx, aWinrescanforwi; "winreScanForWinReWim %s (0x%x) in file "...
0x18003962f  mov     [rsp+0C50h+var_C30], rax
0x180039634  mov     ecx, r13d
0x180039637  call    UnattendLogW
0x18003963c  movzx   ebx, di
0x18003963f  jmp     loc_180039B0E
0x180039644  mov     dword ptr [rsi], 1
0x18003964a  mov     dword ptr [r14], 1
0x180039651  jmp     loc_180039B0E
0x180039656  mov     esi, 7FFFFFFFh
0x18003965b  mov     [rsp+0C50h+var_C20], 0
0x180039664  mov     edx, esi; unsigned __int64
0x180039666  lea     r8, [rsp+0C50h+var_C20]; unsigned __int64 *
0x18003966b  mov     rcx, rdi; unsigned __int16 *
0x18003966e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180039673  mov     ebx, eax
0x180039675  test    eax, eax
0x180039677  jns     short loc_1800396BB
0x180039679  mov     r11, cs:WPP_GLOBAL_Control
0x180039680  lea     rax, WPP_GLOBAL_Control
0x180039687  cmp     r11, rax
0x18003968a  jz      short loc_1800396B1
0x18003968c  test    [r11+1Ch], r13b
0x180039690  jz      short loc_1800396B1
0x180039692  mov     rcx, [r11+10h]
0x180039696  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18003969d  mov     edx, 0Eh
0x1800396a2  mov     r9d, ebx
0x1800396a5  call    WPP_SF_d
0x1800396aa  mov     r11, cs:WPP_GLOBAL_Control
0x1800396b1  mov     edi, 12Eh
0x1800396b6  jmp     loc_18003973B
0x1800396bb  mov     rax, [rsp+0C50h+var_C20]
0x1800396c0  test    rax, rax
0x1800396c3  jz      short loc_1800396D4
0x1800396c5  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800396cb  lea     r8, aSS_1; "%s\\%s"
0x1800396d2  jnz     short loc_1800396DB
0x1800396d4  lea     r8, aSS_2; "%s%s"
0x1800396db  mov     r9, rdi
0x1800396de  lea     rax, aRecovery+2; "Recovery"
0x1800396e5  mov     edi, 12Eh
0x1800396ea  mov     [rsp+0C50h+var_C30], rax
0x1800396ef  mov     edx, edi; unsigned __int64
0x1800396f1  lea     rcx, [rbp+0B50h+var_760]; unsigned __int16 *
0x1800396f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800396fd  mov     ebx, eax
0x1800396ff  test    eax, eax
0x180039701  jns     short loc_18003974F
0x180039703  mov     r11, cs:WPP_GLOBAL_Control
0x18003970a  lea     rax, WPP_GLOBAL_Control
0x180039711  cmp     r11, rax
0x180039714  jz      short loc_18003973B
0x180039716  test    [r11+1Ch], r13b
0x18003971a  jz      short loc_18003973B
0x18003971c  mov     rcx, [r11+10h]
0x180039720  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180039727  mov     edx, 0Fh
0x18003972c  mov     r9d, ebx
0x18003972f  call    WPP_SF_d
0x180039734  mov     r11, cs:WPP_GLOBAL_Control
0x18003973b  movzx   ebx, bx
0x18003973e  test    ebx, ebx
0x180039740  jz      short loc_180039756
0x180039742  mov     [rsp+0C50h+var_C28], 0C25h
0x18003974a  jmp     loc_18003959D
0x18003974f  mov     r11, cs:WPP_GLOBAL_Control
0x180039756  lea     r8, [rsp+0C50h+var_C20]; unsigned __int64 *
0x18003975b  mov     [rsp+0C50h+var_C20], 0
0x180039764  mov     rdx, rsi; unsigned __int64
0x180039767  lea     rcx, [rbp+0B50h+var_760]; unsigned __int16 *
0x18003976e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180039773  mov     ebx, eax
0x180039775  test    eax, eax
0x180039777  jns     short loc_18003979E
0x180039779  lea     rax, WPP_GLOBAL_Control
0x180039780  cmp     r11, rax
0x180039783  jz      loc_18003981A
0x180039789  test    [r11+1Ch], r13b
0x18003978d  jz      loc_18003981A
0x180039793  mov     rcx, [r11+10h]
0x180039797  mov     edx, 0Eh
0x18003979c  jmp     short loc_18003980B
0x18003979e  mov     rax, [rsp+0C50h+var_C20]
0x1800397a3  test    rax, rax
0x1800397a6  jz      short loc_1800397BA
0x1800397a8  cmp     [rbp+rax*2+0B50h+var_762], 5Ch ; '\'
0x1800397b1  lea     r8, aSS_1; "%s\\%s"
0x1800397b8  jnz     short loc_1800397C1
0x1800397ba  lea     r8, aSS_2; "%s%s"
0x1800397c1  lea     rax, aTemporary_0; "Temporary"
0x1800397c8  mov     rdx, rdi; unsigned __int64
0x1800397cb  lea     r9, [rbp+0B50h+var_760]
0x1800397d2  mov     [rsp+0C50h+var_C30], rax
0x1800397d7  lea     rcx, [rbp+0B50h+var_2A0]; unsigned __int16 *
0x1800397de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800397e3  mov     ebx, eax
0x1800397e5  test    eax, eax
0x1800397e7  jns     short loc_18003982E
0x1800397e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397f0  lea     rax, WPP_GLOBAL_Control
0x1800397f7  cmp     rcx, rax
0x1800397fa  jz      short loc_18003981A
0x1800397fc  test    [rcx+1Ch], r13b
0x180039800  jz      short loc_18003981A
0x180039802  mov     rcx, [rcx+10h]
0x180039806  mov     edx, 0Fh
0x18003980b  mov     r9d, ebx
0x18003980e  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180039815  call    WPP_SF_d
0x18003981a  movzx   ebx, bx
0x18003981d  test    ebx, ebx
0x18003981f  jz      short loc_180039830
0x180039821  mov     [rsp+0C50h+var_C28], 0C28h
0x180039829  jmp     loc_18003959D
0x18003982e  xor     ebx, ebx
0x180039830  lea     rdx, aWinreWim; "Winre.wim"
0x180039837  lea     rcx, [rbp+0B50h+var_2A0]; unsigned __int16 *
0x18003983e  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x180039843  test    eax, eax
0x180039845  jnz     short loc_180039885
0x180039847  lea     r8, [rbp+0B50h+var_9C0]
0x18003984e  xor     ecx, ecx
0x180039850  lea     rdx, aWinreWimFoundI; "Winre.wim found in the temporary stagin"...
0x180039857  call    UnattendLogW
0x18003985c  lea     r8, [rbp+0B50h+var_2A0]; unsigned __int16 *
0x180039863  mov     rdx, rdi; unsigned __int64
0x180039866  mov     rcx, r15; unsigned __int16 *
0x180039869  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003986e  mov     edi, eax
0x180039870  test    eax, eax
0x180039872  jns     loc_18003964A
0x180039878  mov     [rsp+0C50h+var_C28], 0C32h
0x180039880  jmp     loc_180039617
0x180039885  lea     r9, [rbp+0B50h+var_760]
0x18003988c  mov     rdx, rdi; unsigned __int64
0x18003988f  lea     r8, aS_0; "%s\\*"
0x180039896  lea     rcx, [rbp+0B50h+FileName]; unsigned __int16 *
0x18003989d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800398a2  mov     edi, eax
0x1800398a4  test    eax, eax
0x1800398a6  jns     short loc_1800398BC
0x1800398a8  mov     [rsp+0C50h+var_C28], 0C37h
0x1800398b0  lea     r8, aFailedToCreate_29; "failed to create wildcard path"
0x1800398b7  jmp     loc_18003961E
0x1800398bc  lea     rdx, [rsp+0C50h+FindFileData]; lpFindFileData
0x1800398c1  lea     rcx, [rbp+0B50h+FileName]; lpFileName
0x1800398c8  call    cs:__imp_FindFirstFileW
0x1800398ce  mov     rsi, rax
0x1800398d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800398d5  jnz     short loc_180039917
0x1800398d7  call    cs:__imp_GetLastError
0x1800398dd  lea     r8, [rbp+0B50h+FileName]
0x1800398e4  mov     ebx, eax
0x1800398e6  cmp     eax, r13d
0x1800398e9  jnz     short loc_1800398FE
0x1800398eb  lea     rdx, aSNotFound; "%s not found"
0x1800398f2  xor     ecx, ecx
0x1800398f4  call    UnattendLogW
0x1800398f9  jmp     loc_180039B0E
0x1800398fe  mov     r9d, eax
0x180039901  lea     rdx, aFindfirstfilew_1; "FindFirstFileW(%s) failed, last error 0"...
0x180039908  mov     ecx, 1
0x18003990d  call    UnattendLogW
0x180039912  jmp     loc_180039B0E
0x180039917  xor     edi, edi
0x180039919  test    byte ptr [rsp+0C50h+FindFileData.dwFileAttributes], 10h
0x18003991e  jz      loc_180039A63
  ... truncated ...
```
