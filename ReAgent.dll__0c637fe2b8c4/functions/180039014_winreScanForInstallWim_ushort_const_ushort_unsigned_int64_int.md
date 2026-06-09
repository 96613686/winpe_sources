# winreScanForInstallWim(ushort const *,ushort *,unsigned __int64,int *)

- ea: `0x180039014`
- end: `0x1800393dd`
- name: `?winreScanForInstallWim@@YAKPEBGPEAG_KPEAH@Z`
- size: `969`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003bfbc`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180039014`
- `0x18004d3a0`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003912f`
- `KERNEL32!GetLastError` at `0x18003912f`
- `KERNEL32!FindFirstFileW` at `0x180039120`
- `KERNEL32!FindFirstFileW` at `0x180039120`
- `KERNEL32!FindNextFileW` at `0x180039318`
- `KERNEL32!FindNextFileW` at `0x180039318`
- `KERNEL32!FindClose` at `0x180039395`
- `KERNEL32!FindClose` at `0x180039395`

## string_xrefs

- `0x18003928a`: `install.wim`
- `0x180039268`: `failed to append path`
- `0x180039366`: `failed to copy string`
- `0x1800392a1`: `install.swm`
- `0x1800392b8`: `install.esd`
- `0x1800390dd`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039254`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039352`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x1800390f1`: `failed to create wildcard path`
- `0x1800390fd`: `winreScanForInstallWim %s (0x%x) in file %S line %d`
- `0x180039274`: `winreScanForInstallWim %s (0x%x) in file %S line %d`
- `0x180039372`: `winreScanForInstallWim %s (0x%x) in file %S line %d`
- `0x1800392d8`: `install.wim or install.swm or install.esd found at %s`
- `0x1800392e4`: `ResetConfig.xml`
- `0x18003932e`: `ResetConfig.xml found at %s`
- `0x180039304`: `ResetConfig.xml not found at %s, ignoring install.wim`

## pseudocode

```c
__int64 __fastcall winreScanForInstallWim(const unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  int v11; // edi
  int v12; // eax
  void *v13; // r11
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  const unsigned __int16 *v17; // r8
  WCHAR *cFileName; // rax
  int v19; // eax
  unsigned __int16 v20; // di
  unsigned __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v24; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v25[606]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR FileName; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v27[606]; // [rsp+4F2h] [rbp+3F2h] BYREF

  FileName = 0;
  memset_0(v27, 0, 0x25Au);
  v24 = 0;
  memset_0(v25, 0, 0x25Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || !a2 || !a4 )
  {
    v8 = 87;
    UnattendLogW(1, L"invalid parameter");
    return v8;
  }
  *a4 = 0;
  v7 = StringCchPrintfW(&FileName, 0x12Eu, L"%s\\*", a1);
  LOWORD(v8) = v7;
  if ( v7 < 0 )
  {
    UnattendLogW(
      2,
      L"winreScanForInstallWim %s (0x%x) in file %S line %d",
      L"failed to create wildcard path",
      (unsigned int)v7,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      3013);
    return (unsigned __int16)v8;
  }
  FirstFileW = FindFirstFileW(&FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 2 )
      UnattendLogW(0, L"%s not found", &FileName);
    else
      UnattendLogW(1, L"FindFirstFileW(%s) failed, last error 0X%X", &FileName, LastError);
    return v8;
  }
  v8 = 0;
  v11 = 0;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      goto LABEL_34;
    v22 = 0;
    v12 = StringCchLengthW(a1, 0x7FFFFFFFu, &v22);
    LOWORD(v8) = v12;
    if ( v12 >= 0 )
    {
      if ( !v22 || (v17 = L"%s\\%s", a1[v22 - 1] == 92) )
        v17 = L"%s%s";
      cFileName = &FindFileData.cFileName[1];
      if ( FindFileData.cFileName[0] != 92 )
        cFileName = FindFileData.cFileName;
      v8 = StringCchPrintfW(&v24, 0x12Eu, v17, a1, cFileName);
      if ( (v8 & 0x80000000) == 0 )
      {
        v8 = 0;
        goto LABEL_29;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 15;
        v16 = v8;
        goto LABEL_25;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != v13 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 14;
        v16 = (unsigned int)v12;
LABEL_25:
        WPP_SF_d(v14[2], v15, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, v16);
      }
    }
    v8 = (unsigned __int16)v8;
    if ( (_WORD)v8 )
    {
      UnattendLogW(
        2,
        L"winreScanForInstallWim %s (0x%x) in file %S line %d",
        L"failed to append path",
        (unsigned __int16)v8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        3035);
      goto LABEL_40;
    }
LABEL_29:
    if ( Utils::DoesFileExist(&v24, L"install.wim")
      && Utils::DoesFileExist(&v24, L"install.swm")
      && Utils::DoesFileExist(&v24, L"install.esd") )
    {
      goto LABEL_34;
    }
    UnattendLogW(0, L"install.wim or install.swm or install.esd found at %s", &v24);
    if ( !Utils::DoesFileExist(&v24, L"ResetConfig.xml") )
      break;
    UnattendLogW(0, L"ResetConfig.xml not found at %s, ignoring install.wim", &v24);
LABEL_34:
    if ( FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( (unsigned int)++v11 < 0x64 )
        continue;
    }
    goto LABEL_40;
  }
  UnattendLogW(0, L"ResetConfig.xml found at %s", &v24);
  v19 = StringCchCopyW(a2, 0x12Eu, &v24);
  v20 = v19;
  if ( v19 >= 0 )
  {
    *a4 = 1;
  }
  else
  {
    UnattendLogW(
      2,
      L"winreScanForInstallWim %s (0x%x) in file %S line %d",
      L"failed to copy string",
      (unsigned int)v19,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      3044);
    v8 = v20;
  }
LABEL_40:
  if ( FirstFileW )
    FindClose(FirstFileW);
  return v8;
}

```

## disassembly

```asm
0x180039014  mov     [rsp-8+arg_10], rbx
0x180039019  push    rbp
0x18003901a  push    rsi
0x18003901b  push    rdi
0x18003901c  push    r12
0x18003901e  push    r13
0x180039020  push    r14
0x180039022  push    r15
0x180039024  lea     rbp, [rsp-660h]
0x18003902c  sub     rsp, 760h
0x180039033  mov     rax, cs:__security_cookie
0x18003903a  xor     rax, rsp
0x18003903d  mov     [rbp+690h+var_40], rax
0x180039044  mov     r12, rdx
0x180039047  mov     r15, rcx
0x18003904a  xor     eax, eax
0x18003904c  lea     rcx, [rbp+690h+var_29E]; void *
0x180039053  mov     ebx, 25Ah
0x180039058  mov     [rbp+690h+FileName], ax
0x18003905f  mov     r8d, ebx; Size
0x180039062  xor     edx, edx; Val
0x180039064  mov     r14, r9
0x180039067  call    memset_0
0x18003906c  xor     eax, eax
0x18003906e  lea     rcx, [rbp+690h+var_4FE]; void *
0x180039075  mov     r8d, ebx; Size
0x180039078  mov     [rbp+690h+var_500], ax
0x18003907f  xor     edx, edx; Val
0x180039081  call    memset_0
0x180039086  xor     edx, edx; Val
0x180039088  lea     r8d, [rbx-0Ah]; Size
0x18003908c  lea     rcx, [rsp+790h+FindFileData]; void *
0x180039091  call    memset_0
0x180039096  test    r15, r15
0x180039099  jz      loc_18003939D
0x18003909f  test    r12, r12
0x1800390a2  jz      loc_18003939D
0x1800390a8  test    r14, r14
0x1800390ab  jz      loc_18003939D
0x1800390b1  mov     r13d, 12Eh
0x1800390b7  mov     dword ptr [r14], 0
0x1800390be  mov     edx, r13d; unsigned __int64
0x1800390c1  lea     r8, aS_0; "%s\\*"
0x1800390c8  mov     r9, r15
0x1800390cb  lea     rcx, [rbp+690h+FileName]; unsigned __int16 *
0x1800390d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800390d7  mov     ebx, eax
0x1800390d9  test    eax, eax
0x1800390db  jns     short loc_180039114
0x1800390dd  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800390e4  mov     [rsp+790h+var_768], 0BC5h
0x1800390ec  mov     [rsp+790h+var_770], rcx
0x1800390f1  lea     r8, aFailedToCreate_29; "failed to create wildcard path"
0x1800390f8  mov     ecx, 2
0x1800390fd  lea     rdx, aWinrescanforin; "winreScanForInstallWim %s (0x%x) in fil"...
0x180039104  mov     r9d, eax
0x180039107  call    UnattendLogW
0x18003910c  movzx   ebx, bx
0x18003910f  jmp     loc_1800393B1
0x180039114  lea     rdx, [rsp+790h+FindFileData]; lpFindFileData
0x180039119  lea     rcx, [rbp+690h+FileName]; lpFileName
0x180039120  call    cs:__imp_FindFirstFileW
0x180039126  mov     rsi, rax
0x180039129  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003912d  jnz     short loc_18003916F
0x18003912f  call    cs:__imp_GetLastError
0x180039135  lea     r8, [rbp+690h+FileName]
0x18003913c  mov     ebx, eax
0x18003913e  cmp     eax, 2
0x180039141  jnz     short loc_180039156
0x180039143  lea     rdx, aSNotFound; "%s not found"
0x18003914a  xor     ecx, ecx
0x18003914c  call    UnattendLogW
0x180039151  jmp     loc_1800393B1
0x180039156  mov     r9d, eax
0x180039159  lea     rdx, aFindfirstfilew; "FindFirstFileW(%s) failed, last error 0"...
0x180039160  mov     ecx, 1
0x180039165  call    UnattendLogW
0x18003916a  jmp     loc_1800393B1
0x18003916f  xor     ebx, ebx
0x180039171  xor     edi, edi
0x180039173  test    byte ptr [rsp+790h+FindFileData.dwFileAttributes], 10h
0x180039178  lea     r11, WPP_GLOBAL_Control
0x18003917f  jz      loc_180039310
0x180039185  lea     r8, [rsp+790h+var_760]; unsigned __int64 *
0x18003918a  mov     [rsp+790h+var_760], 0
0x180039193  mov     edx, 7FFFFFFFh; unsigned __int64
0x180039198  mov     rcx, r15; unsigned __int16 *
0x18003919b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800391a0  mov     ebx, eax
0x1800391a2  test    eax, eax
0x1800391a4  jns     short loc_1800391CA
0x1800391a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391ad  cmp     rcx, r11
0x1800391b0  jz      loc_18003924D
0x1800391b6  test    byte ptr [rcx+1Ch], 2
0x1800391ba  jz      loc_18003924D
0x1800391c0  mov     edx, 0Eh
0x1800391c5  mov     r9d, eax
0x1800391c8  jmp     short loc_18003923D
0x1800391ca  mov     rax, [rsp+790h+var_760]
0x1800391cf  test    rax, rax
0x1800391d2  jz      short loc_1800391E4
0x1800391d4  cmp     word ptr [r15+rax*2-2], 5Ch ; '\'
0x1800391db  lea     r8, aSS_1; "%s\\%s"
0x1800391e2  jnz     short loc_1800391EB
0x1800391e4  lea     r8, aSS_2; "%s%s"
0x1800391eb  cmp     [rsp+790h+FindFileData.cFileName], 5Ch ; '\'
0x1800391f1  lea     rcx, [rsp+790h+FindFileData.cFileName]
0x1800391f6  lea     rax, [rsp+790h+FindFileData.cFileName+2]
0x1800391fb  mov     r9, r15
0x1800391fe  cmovnz  rax, rcx
0x180039202  mov     rdx, r13; unsigned __int64
0x180039205  lea     rcx, [rbp+690h+var_500]; unsigned __int16 *
0x18003920c  mov     [rsp+790h+var_770], rax
0x180039211  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039216  mov     ebx, eax
0x180039218  test    eax, eax
0x18003921a  jns     short loc_180039288
0x18003921c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039223  lea     rax, WPP_GLOBAL_Control
0x18003922a  cmp     rcx, rax
0x18003922d  jz      short loc_18003924D
0x18003922f  test    byte ptr [rcx+1Ch], 2
0x180039233  jz      short loc_18003924D
0x180039235  mov     edx, 0Fh
0x18003923a  mov     r9d, ebx
0x18003923d  mov     rcx, [rcx+10h]
0x180039241  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180039248  call    WPP_SF_d
0x18003924d  movzx   ebx, bx
0x180039250  test    ebx, ebx
0x180039252  jz      short loc_18003928A
0x180039254  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003925b  mov     [rsp+790h+var_768], 0BDBh
0x180039263  mov     [rsp+790h+var_770], rcx
0x180039268  lea     r8, aFailedToAppend_7; "failed to append path"
0x18003926f  mov     ecx, 2
0x180039274  lea     rdx, aWinrescanforin; "winreScanForInstallWim %s (0x%x) in fil"...
0x18003927b  mov     r9d, ebx
0x18003927e  call    UnattendLogW
0x180039283  jmp     loc_18003938D
0x180039288  xor     ebx, ebx
0x18003928a  lea     rdx, aInstallWim; "install.wim"
0x180039291  lea     rcx, [rbp+690h+var_500]; unsigned __int16 *
0x180039298  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x18003929d  test    eax, eax
0x18003929f  jz      short loc_1800392CF
0x1800392a1  lea     rdx, aInstallSwm; "install.swm"
0x1800392a8  lea     rcx, [rbp+690h+var_500]; unsigned __int16 *
0x1800392af  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x1800392b4  test    eax, eax
0x1800392b6  jz      short loc_1800392CF
0x1800392b8  lea     rdx, aInstallEsd; "install.esd"
0x1800392bf  lea     rcx, [rbp+690h+var_500]; unsigned __int16 *
0x1800392c6  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x1800392cb  test    eax, eax
0x1800392cd  jnz     short loc_180039310
0x1800392cf  lea     r8, [rbp+690h+var_500]
0x1800392d6  xor     ecx, ecx
0x1800392d8  lea     rdx, aInstallWimOrIn; "install.wim or install.swm or install.e"...
0x1800392df  call    UnattendLogW
0x1800392e4  lea     rdx, aResetconfigXml_3; "ResetConfig.xml"
0x1800392eb  lea     rcx, [rbp+690h+var_500]; unsigned __int16 *
0x1800392f2  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x1800392f7  xor     ecx, ecx
0x1800392f9  lea     r8, [rbp+690h+var_500]
0x180039300  test    eax, eax
0x180039302  jz      short loc_18003932E
0x180039304  lea     rdx, aResetconfigXml; "ResetConfig.xml not found at %s, ignori"...
0x18003930b  call    UnattendLogW
0x180039310  lea     rdx, [rsp+790h+FindFileData]; lpFindFileData
0x180039315  mov     rcx, rsi; hFindFile
0x180039318  call    cs:__imp_FindNextFileW
0x18003931e  test    eax, eax
0x180039320  jz      short loc_18003938D
0x180039322  inc     edi
0x180039324  cmp     edi, 64h ; 'd'
0x180039327  jnb     short loc_18003938D
0x180039329  jmp     loc_180039173
0x18003932e  lea     rdx, aResetconfigXml_2; "ResetConfig.xml found at %s"
0x180039335  call    UnattendLogW
0x18003933a  lea     r8, [rbp+690h+var_500]; unsigned __int16 *
0x180039341  mov     rdx, r13; unsigned __int64
0x180039344  mov     rcx, r12; unsigned __int16 *
0x180039347  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003934c  mov     edi, eax
0x18003934e  test    eax, eax
0x180039350  jns     short loc_180039386
0x180039352  lea     rcx, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039359  mov     [rsp+790h+var_768], 0BE4h
0x180039361  mov     [rsp+790h+var_770], rcx
0x180039366  lea     r8, aFailedToCopySt; "failed to copy string"
0x18003936d  mov     ecx, 2
0x180039372  lea     rdx, aWinrescanforin; "winreScanForInstallWim %s (0x%x) in fil"...
0x180039379  mov     r9d, eax
0x18003937c  call    UnattendLogW
0x180039381  movzx   ebx, di
0x180039384  jmp     short loc_18003938D
0x180039386  mov     dword ptr [r14], 1
0x18003938d  test    rsi, rsi
0x180039390  jz      short loc_1800393B1
0x180039392  mov     rcx, rsi; hFindFile
0x180039395  call    cs:__imp_FindClose
0x18003939b  jmp     short loc_1800393B1
0x18003939d  mov     ebx, 57h ; 'W'
0x1800393a2  lea     rdx, aInvalidParamet_5; "invalid parameter"
0x1800393a9  lea     ecx, [rbx-56h]
0x1800393ac  call    UnattendLogW
0x1800393b1  mov     eax, ebx
0x1800393b3  mov     rcx, [rbp+690h+var_40]
0x1800393ba  xor     rcx, rsp; StackCookie
0x1800393bd  call    __security_check_cookie
0x1800393c2  mov     rbx, [rsp+790h+arg_10]
0x1800393ca  add     rsp, 760h
0x1800393d1  pop     r15
0x1800393d3  pop     r14
0x1800393d5  pop     r13
0x1800393d7  pop     r12
0x1800393d9  pop     rdi
0x1800393da  pop     rsi
0x1800393db  pop     rbp
0x1800393dc  retn
```
