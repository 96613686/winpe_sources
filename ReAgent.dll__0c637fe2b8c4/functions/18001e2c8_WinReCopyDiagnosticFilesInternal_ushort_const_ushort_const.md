# WinReCopyDiagnosticFilesInternal(ushort const *,ushort const *)

- ea: `0x18001e2c8`
- end: `0x18001e4bf`
- name: `?WinReCopyDiagnosticFilesInternal@@YAKPEBG0@Z`
- size: `503`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180021df0`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800109d0`
- `0x18001e2c8`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001e412`
- `KERNEL32!CopyFileW` at `0x18001e412`
- `KERNEL32!GetLastError` at `0x18001e41c`
- `KERNEL32!GetLastError` at `0x18001e41c`
- `ole32!CoTaskMemFree` at `0x18001e496`
- `ole32!CoTaskMemFree` at `0x18001e496`

## string_xrefs

- `0x18001e32f`: `failed to get config file path`
- `0x18001e3a9`: `ReAgent.xml`
- `0x18001e469`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001e473`: `WinReCopyDiagnosticFilesInternal %s (0x%x) in file %S line %d`
- `0x18001e462`: `failed to construct config file target path`
- `0x18001e427`: `WinReCopyDiagnosticFilesInternal`
- `0x18001e432`: `%hs: Failed to copy [%s] => [%s]: 0x%0x`

## pseudocode

```c
__int64 __fastcall WinReCopyDiagnosticFilesInternal(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // r8
  signed int ConfigFilePathFromWinDir; // ebx
  const wchar_t *v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  int v11; // [rsp+28h] [rbp-290h]
  unsigned __int64 v12; // [rsp+30h] [rbp-288h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-280h] BYREF
  WCHAR NewFileName; // [rsp+40h] [rbp-278h] BYREF
  _BYTE v15[606]; // [rsp+42h] [rbp-276h] BYREF

  lpExistingFileName = 0;
  NewFileName = 0;
  memset_0(v15, 0, 0x25Au);
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a1, 1, v4, &lpExistingFileName);
  if ( ConfigFilePathFromWinDir )
  {
    v11 = 6777;
    v6 = L"failed to get config file path";
LABEL_22:
    UnattendLogW(
      2,
      L"WinReCopyDiagnosticFilesInternal %s (0x%x) in file %S line %d",
      v6,
      (unsigned int)ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v11);
    goto LABEL_23;
  }
  v12 = 0;
  if ( !a2 )
  {
    ConfigFilePathFromWinDir = 87;
    goto LABEL_21;
  }
  ConfigFilePathFromWinDir = StringCchLengthW(a2, 0x7FFFFFFFu, &v12);
  if ( ConfigFilePathFromWinDir >= 0 )
  {
    if ( !v12 || (v9 = L"%s\\%s", a2[v12 - 1] == 92) )
      v9 = L"%s%s";
    ConfigFilePathFromWinDir = StringCchPrintfW(&NewFileName, 0x12Eu, v9, a2, L"ReAgent.xml");
    if ( ConfigFilePathFromWinDir >= 0 )
      goto LABEL_17;
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
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)ConfigFilePathFromWinDir);
    }
  }
  ConfigFilePathFromWinDir = (unsigned __int16)ConfigFilePathFromWinDir;
  if ( (_WORD)ConfigFilePathFromWinDir )
  {
LABEL_21:
    v11 = 6783;
    v6 = L"failed to construct config file target path";
    goto LABEL_22;
  }
LABEL_17:
  if ( CopyFileW(lpExistingFileName, &NewFileName, 0) )
  {
    ConfigFilePathFromWinDir = 0;
  }
  else
  {
    ConfigFilePathFromWinDir = GetLastError();
    UnattendLogW(
      2,
      L"%hs: Failed to copy [%s] => [%s]: 0x%0x",
      "WinReCopyDiagnosticFilesInternal",
      lpExistingFileName,
      &NewFileName,
      ConfigFilePathFromWinDir);
  }
LABEL_23:
  if ( lpExistingFileName )
    CoTaskMemFree((LPVOID)lpExistingFileName);
  return (unsigned int)ConfigFilePathFromWinDir;
}

```

## disassembly

```asm
0x18001e2c8  mov     [rsp+arg_10], rbx
0x18001e2cd  push    rsi
0x18001e2ce  sub     rsp, 2B0h
0x18001e2d5  mov     rax, cs:__security_cookie
0x18001e2dc  xor     rax, rsp
0x18001e2df  mov     [rsp+2B8h+var_18], rax
0x18001e2e7  mov     rsi, rdx
0x18001e2ea  mov     [rsp+2B8h+lpExistingFileName], 0
0x18001e2f3  mov     rbx, rcx
0x18001e2f6  xor     eax, eax
0x18001e2f8  xor     edx, edx; Val
0x18001e2fa  mov     [rsp+2B8h+NewFileName], ax
0x18001e2ff  lea     rcx, [rsp+2B8h+var_276]; void *
0x18001e304  mov     r8d, 25Ah; Size
0x18001e30a  call    memset_0
0x18001e30f  lea     r9, [rsp+2B8h+lpExistingFileName]
0x18001e314  mov     edx, 1
0x18001e319  mov     rcx, rbx
0x18001e31c  call    winreGetConfigFilePathFromWinDir
0x18001e321  mov     ebx, eax
0x18001e323  test    eax, eax
0x18001e325  jz      short loc_18001E33B
0x18001e327  mov     [rsp+2B8h+var_290], 1A79h
0x18001e32f  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x18001e336  jmp     loc_18001E469
0x18001e33b  mov     [rsp+2B8h+var_288], 0
0x18001e344  test    rsi, rsi
0x18001e347  jz      loc_18001E455
0x18001e34d  lea     r8, [rsp+2B8h+var_288]; unsigned __int64 *
0x18001e352  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001e357  mov     rcx, rsi; unsigned __int16 *
0x18001e35a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e35f  mov     ebx, eax
0x18001e361  test    eax, eax
0x18001e363  jns     short loc_18001E389
0x18001e365  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e36c  lea     rax, WPP_GLOBAL_Control
0x18001e373  cmp     rcx, rax
0x18001e376  jz      loc_18001E3FE
0x18001e37c  test    byte ptr [rcx+1Ch], 2
0x18001e380  jz      short loc_18001E3FE
0x18001e382  mov     edx, 0Eh
0x18001e387  jmp     short loc_18001E3EB
0x18001e389  mov     rax, [rsp+2B8h+var_288]
0x18001e38e  test    rax, rax
0x18001e391  jz      short loc_18001E3A2
0x18001e393  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x18001e399  lea     r8, aSS_1; "%s\\%s"
0x18001e3a0  jnz     short loc_18001E3A9
0x18001e3a2  lea     r8, aSS_2; "%s%s"
0x18001e3a9  lea     rax, aReagentXml_1; "ReAgent.xml"
0x18001e3b0  mov     r9, rsi
0x18001e3b3  mov     edx, 12Eh; unsigned __int64
0x18001e3b8  mov     [rsp+2B8h+var_298], rax
0x18001e3bd  lea     rcx, [rsp+2B8h+NewFileName]; unsigned __int16 *
0x18001e3c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e3c7  mov     ebx, eax
0x18001e3c9  test    eax, eax
0x18001e3cb  jns     short loc_18001E405
0x18001e3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3d4  lea     rax, WPP_GLOBAL_Control
0x18001e3db  cmp     rcx, rax
0x18001e3de  jz      short loc_18001E3FE
0x18001e3e0  test    byte ptr [rcx+1Ch], 2
0x18001e3e4  jz      short loc_18001E3FE
0x18001e3e6  mov     edx, 0Fh
0x18001e3eb  mov     rcx, [rcx+10h]
0x18001e3ef  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18001e3f6  mov     r9d, ebx
0x18001e3f9  call    WPP_SF_d
0x18001e3fe  movzx   ebx, bx
0x18001e401  test    ebx, ebx
0x18001e403  jnz     short loc_18001E45A
0x18001e405  mov     rcx, [rsp+2B8h+lpExistingFileName]; lpExistingFileName
0x18001e40a  lea     rdx, [rsp+2B8h+NewFileName]; lpNewFileName
0x18001e40f  xor     r8d, r8d; bFailIfExists
0x18001e412  call    cs:__imp_CopyFileW
0x18001e418  test    eax, eax
0x18001e41a  jnz     short loc_18001E451
0x18001e41c  call    cs:__imp_GetLastError
0x18001e422  mov     r9, [rsp+2B8h+lpExistingFileName]
0x18001e427  lea     r8, aWinrecopydiagn_1; "WinReCopyDiagnosticFilesInternal"
0x18001e42e  mov     [rsp+2B8h+var_290], eax
0x18001e432  lea     rdx, aHsFailedToCopy; "%hs: Failed to copy [%s] => [%s]: 0x%0x"
0x18001e439  mov     ebx, eax
0x18001e43b  mov     ecx, 2
0x18001e440  lea     rax, [rsp+2B8h+NewFileName]
0x18001e445  mov     [rsp+2B8h+var_298], rax
0x18001e44a  call    UnattendLogW
0x18001e44f  jmp     short loc_18001E489
0x18001e451  xor     ebx, ebx
0x18001e453  jmp     short loc_18001E489
0x18001e455  mov     ebx, 57h ; 'W'
0x18001e45a  mov     [rsp+2B8h+var_290], 1A7Fh
0x18001e462  lea     r8, aFailedToConstr; "failed to construct config file target "...
0x18001e469  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001e470  mov     r9d, ebx
0x18001e473  lea     rdx, aWinrecopydiagn_0; "WinReCopyDiagnosticFilesInternal %s (0x"...
0x18001e47a  mov     [rsp+2B8h+var_298], rax
0x18001e47f  mov     ecx, 2
0x18001e484  call    UnattendLogW
0x18001e489  cmp     [rsp+2B8h+lpExistingFileName], 0
0x18001e48f  jz      short loc_18001E49C
0x18001e491  mov     rcx, [rsp+2B8h+lpExistingFileName]; pv
0x18001e496  call    cs:__imp_CoTaskMemFree
0x18001e49c  mov     eax, ebx
0x18001e49e  mov     rcx, [rsp+2B8h+var_18]
0x18001e4a6  xor     rcx, rsp; StackCookie
0x18001e4a9  call    __security_check_cookie
0x18001e4ae  mov     rbx, [rsp+2B8h+arg_10]
0x18001e4b6  add     rsp, 2B0h
0x18001e4bd  pop     rsi
0x18001e4be  retn
```
