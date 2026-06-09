# WinreUpdateForCopiedConfigFile

- ea: `0x18000f698`
- end: `0x18000f9e9`
- name: `WinreUpdateForCopiedConfigFile`
- size: `849`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014754`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000ed74`
- `0x18000f698`
- `0x18000ff68`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000f7ec`
- `msvcrt!_wcsicmp` at `0x18000f7ec`
- `KERNEL32!CopyFileW` at `0x18000f978`
- `KERNEL32!CopyFileW` at `0x18000f978`
- `KERNEL32!GetLastError` at `0x18000f734`
- `KERNEL32!GetLastError` at `0x18000f982`
- `KERNEL32!GetLastError` at `0x18000f734`
- `KERNEL32!GetLastError` at `0x18000f982`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000f72a`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000f72a`
- `ADVAPI32!RegQueryValueExW` at `0x18000f879`
- `ADVAPI32!RegQueryValueExW` at `0x18000f91f`
- `ADVAPI32!RegQueryValueExW` at `0x18000f879`
- `ADVAPI32!RegQueryValueExW` at `0x18000f91f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f829`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f829`
- `ADVAPI32!RegCloseKey` at `0x18000f9ba`
- `ADVAPI32!RegCloseKey` at `0x18000f9ba`

## string_xrefs

- `0x18000f74b`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000f7ad`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000f83d`: `failed to open recovery environment key`
- `0x18000f872`: `ReAgentXmlCopiedToRamdisk`
- `0x18000f890`: `failed to query registry value whether reagent.xml is copied to ramdisk. Error: 0x%08X`
- `0x18000f8c4`: `Get unexpected registry value type %d`
- `0x18000f73a`: `failed to get Windows directory`
- `0x18000f791`: `Recovery\ReAgentCopied.xml`
- `0x18000f988`: `failed to copy recovery file`
- `0x18000f918`: `SourceReAgentXmlPath`
- `0x18000f755`: `WinreUpdateForCopiedConfigFile %s (0x%x) in file %S line %d`
- `0x18000f7d0`: `WinreUpdateForCopiedConfigFile %s (0x%x) in file %S line %d`
- `0x18000f7fd`: `Current xml [%s] is copied xml file`
- `0x18000f8a4`: `Target registry key not found. Copied xml is not used`
- `0x18000f8e4`: `Copied xml is not used`
- `0x18000f933`: `failed to read source recovery file path from registry`
- `0x18000f99c`: `Get unexpected registry value type/length %d - %d`
- `0x18000f95d`: ` Update the source xml file path [%s] with copied config file [%s]`

## pseudocode

```c
__int64 __fastcall WinreUpdateForCopiedConfigFile(LPCWSTR lpExistingFileName)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  const wchar_t *v4; // r8
  int v5; // esi
  unsigned int v6; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v14[264]; // [rsp+260h] [rbp+160h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(v14, 0, 0x208u);
  Type = 0;
  *(_DWORD *)Data = 1;
  cbData = 0;
  hKey = 0;
  if ( (unsigned int)winreIsWinPE() )
  {
    if ( !lpExistingFileName )
    {
      v2 = 87;
      goto LABEL_31;
    }
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      v4 = L"failed to get Windows directory";
      LODWORD(lpcbData) = 940;
LABEL_6:
      v2 = LastError;
LABEL_7:
      UnattendLogW(
        2,
        L"WinreUpdateForCopiedConfigFile %s (0x%x) in file %S line %d",
        v4,
        v2,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        lpcbData);
      goto LABEL_31;
    }
    v2 = winreAddTrailingBackslash(Buffer);
    if ( v2 )
    {
      LODWORD(lpcbData) = 945;
      v4 = L"failed to add trailing back slash";
      goto LABEL_7;
    }
    v5 = StringCchCatW(Buffer, 0x12Eu, L"Recovery\\ReAgentCopied.xml");
    if ( v5 < 0 )
    {
      UnattendLogW(
        2,
        L"WinreUpdateForCopiedConfigFile %s (0x%x) in file %S line %d",
        L"failed to concatenate recovery file name",
        (unsigned int)v5,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        948);
      v2 = (unsigned __int16)v5;
      goto LABEL_31;
    }
    if ( !_wcsicmp(lpExistingFileName, Buffer) )
    {
      UnattendLogW(0, L"Current xml [%s] is copied xml file", lpExistingFileName);
      v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 1u, &hKey);
      if ( v2 )
      {
        LODWORD(lpcbData) = 966;
        v4 = L"failed to open recovery environment key";
        goto LABEL_7;
      }
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"ReAgentXmlCopiedToRamdisk", 0, &Type, Data, &cbData);
      v2 = v6;
      if ( v6 )
      {
        if ( v6 - 2 > 1 )
        {
          UnattendLogW(1, L"failed to query registry value whether reagent.xml is copied to ramdisk. Error: 0x%08X", v6);
          goto LABEL_31;
        }
        UnattendLogW(0, L"Target registry key not found. Copied xml is not used");
        goto LABEL_19;
      }
      if ( Type == 4 )
      {
        if ( *(_DWORD *)Data != 1 )
        {
          UnattendLogW(0, L"Copied xml is not used");
LABEL_19:
          v2 = 0;
          goto LABEL_31;
        }
        cbData = 604;
        v2 = RegQueryValueExW(hKey, L"SourceReAgentXmlPath", 0, &Type, (LPBYTE)v14, &cbData);
        if ( v2 )
        {
          LODWORD(lpcbData) = 1006;
          v4 = L"failed to read source recovery file path from registry";
          goto LABEL_7;
        }
        if ( Type == 1 && cbData )
        {
          UnattendLogW(
            0,
            L" Update the source xml file path [%s] with copied config file [%s]",
            v14,
            lpExistingFileName);
          if ( !CopyFileW(lpExistingFileName, v14, 0) )
          {
            LastError = GetLastError();
            v4 = L"failed to copy recovery file";
            LODWORD(lpcbData) = 1021;
            goto LABEL_6;
          }
        }
        else
        {
          v2 = 87;
          UnattendLogW(1, L"Get unexpected registry value type/length %d - %d", Type, cbData);
        }
      }
      else
      {
        UnattendLogW(1, L"Get unexpected registry value type %d");
        v2 = 1804;
      }
    }
  }
LABEL_31:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18000f698  mov     [rsp-8+arg_8], rbx
0x18000f69d  mov     [rsp-8+arg_10], rsi
0x18000f6a2  push    rbp
0x18000f6a3  push    rdi
0x18000f6a4  push    r15
0x18000f6a6  lea     rbp, [rsp-380h]
0x18000f6ae  sub     rsp, 480h
0x18000f6b5  mov     rax, cs:__security_cookie
0x18000f6bc  xor     rax, rsp
0x18000f6bf  mov     [rbp+390h+var_20], rax
0x18000f6c6  mov     rdi, rcx
0x18000f6c9  mov     esi, 208h
0x18000f6ce  mov     r8d, esi; Size
0x18000f6d1  lea     rcx, [rsp+490h+Buffer]; void *
0x18000f6d6  xor     edx, edx; Val
0x18000f6d8  xor     ebx, ebx
0x18000f6da  call    memset_0
0x18000f6df  mov     r8d, esi; Size
0x18000f6e2  lea     rcx, [rbp+390h+var_230]; void *
0x18000f6e9  xor     edx, edx; Val
0x18000f6eb  call    memset_0
0x18000f6f0  lea     r15d, [rbx+1]
0x18000f6f4  mov     [rsp+490h+Type], ebx
0x18000f6f8  mov     dword ptr [rsp+490h+Data], r15d
0x18000f6fd  mov     [rsp+490h+cbData], ebx
0x18000f701  mov     [rsp+490h+hKey], rbx
0x18000f706  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18000f70b  test    eax, eax
0x18000f70d  jz      loc_18000F9B0
0x18000f713  test    rdi, rdi
0x18000f716  jnz     short loc_18000F720
0x18000f718  lea     ebx, [rdi+57h]
0x18000f71b  jmp     loc_18000F9B0
0x18000f720  mov     edx, 104h; uSize
0x18000f725  lea     rcx, [rsp+490h+Buffer]; lpBuffer
0x18000f72a  call    cs:__imp_GetWindowsDirectoryW
0x18000f730  test    eax, eax
0x18000f732  jnz     short loc_18000F770
0x18000f734  call    cs:__imp_GetLastError
0x18000f73a  lea     r8, aFailedToGetWin; "failed to get Windows directory"
0x18000f741  mov     dword ptr [rsp+490h+lpcbData], 3ACh
0x18000f749  mov     ebx, eax
0x18000f74b  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000f752  mov     r9d, ebx
0x18000f755  lea     rdx, aWinreupdatefor; "WinreUpdateForCopiedConfigFile %s (0x%x"...
0x18000f75c  mov     [rsp+490h+phkResult], rax
0x18000f761  mov     ecx, 2
0x18000f766  call    UnattendLogW
0x18000f76b  jmp     loc_18000F9B0
0x18000f770  lea     rcx, [rsp+490h+Buffer]
0x18000f775  call    winreAddTrailingBackslash
0x18000f77a  mov     ebx, eax
0x18000f77c  test    eax, eax
0x18000f77e  jz      short loc_18000F791
0x18000f780  mov     dword ptr [rsp+490h+lpcbData], 3B1h
0x18000f788  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18000f78f  jmp     short loc_18000F74B
0x18000f791  lea     r8, aRecoveryReagen_0; "Recovery\\ReAgentCopied.xml"
0x18000f798  mov     edx, 12Eh; unsigned __int64
0x18000f79d  lea     rcx, [rsp+490h+Buffer]; unsigned __int16 *
0x18000f7a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f7a7  mov     esi, eax
0x18000f7a9  test    eax, eax
0x18000f7ab  jns     short loc_18000F7E4
0x18000f7ad  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000f7b4  mov     dword ptr [rsp+490h+lpcbData], 3B4h
0x18000f7bc  mov     r9d, esi
0x18000f7bf  mov     [rsp+490h+phkResult], rax
0x18000f7c4  lea     r8, aFailedToConcat_6; "failed to concatenate recovery file nam"...
0x18000f7cb  mov     ecx, 2
0x18000f7d0  lea     rdx, aWinreupdatefor; "WinreUpdateForCopiedConfigFile %s (0x%x"...
0x18000f7d7  call    UnattendLogW
0x18000f7dc  movzx   ebx, si
0x18000f7df  jmp     loc_18000F9B0
0x18000f7e4  lea     rdx, [rsp+490h+Buffer]; String2
0x18000f7e9  mov     rcx, rdi; String1
0x18000f7ec  call    cs:__imp__wcsicmp
0x18000f7f2  test    eax, eax
0x18000f7f4  jnz     loc_18000F9B0
0x18000f7fa  mov     r8, rdi
0x18000f7fd  lea     rdx, aCurrentXmlSIsC; "Current xml [%s] is copied xml file"
0x18000f804  xor     ecx, ecx
0x18000f806  call    UnattendLogW
0x18000f80b  lea     rax, [rsp+490h+hKey]
0x18000f810  mov     r9d, r15d; samDesired
0x18000f813  xor     r8d, r8d; ulOptions
0x18000f816  mov     [rsp+490h+phkResult], rax; phkResult
0x18000f81b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18000f822  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f829  call    cs:__imp_RegOpenKeyExW
0x18000f82f  mov     ebx, eax
0x18000f831  test    eax, eax
0x18000f833  jz      short loc_18000F849
0x18000f835  mov     dword ptr [rsp+490h+lpcbData], 3C6h
0x18000f83d  lea     r8, aFailedToOpenRe_1; "failed to open recovery environment key"
0x18000f844  jmp     loc_18000F74B
0x18000f849  mov     rcx, [rsp+490h+hKey]; hKey
0x18000f84e  lea     rax, [rsp+490h+cbData]
0x18000f853  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18000f858  lea     r9, [rsp+490h+Type]; lpType
0x18000f85d  lea     rax, [rsp+490h+Data]
0x18000f862  mov     [rsp+490h+cbData], 4
0x18000f86a  xor     r8d, r8d; lpReserved
0x18000f86d  mov     [rsp+490h+phkResult], rax; lpData
0x18000f872  lea     rdx, aReagentxmlcopi; "ReAgentXmlCopiedToRamdisk"
0x18000f879  call    cs:__imp_RegQueryValueExW
0x18000f87f  mov     ebx, eax
0x18000f881  test    eax, eax
0x18000f883  jz      short loc_18000F8B9
0x18000f885  add     eax, 0FFFFFFFEh
0x18000f888  cmp     eax, r15d
0x18000f88b  jbe     short loc_18000F8A4
0x18000f88d  mov     r8d, ebx
0x18000f890  lea     rdx, aFailedToQueryR; "failed to query registry value whether "...
0x18000f897  mov     ecx, r15d
0x18000f89a  call    UnattendLogW
0x18000f89f  jmp     loc_18000F9B0
0x18000f8a4  lea     rdx, aTargetRegistry; "Target registry key not found. Copied x"...
0x18000f8ab  xor     ecx, ecx
0x18000f8ad  call    UnattendLogW
0x18000f8b2  xor     ebx, ebx
0x18000f8b4  jmp     loc_18000F9B0
0x18000f8b9  mov     r8d, [rsp+490h+Type]
0x18000f8be  cmp     r8d, 4
0x18000f8c2  jz      short loc_18000F8DD
0x18000f8c4  lea     rdx, aGetUnexpectedR_0; "Get unexpected registry value type %d"
0x18000f8cb  mov     ecx, r15d
0x18000f8ce  call    UnattendLogW
0x18000f8d3  mov     ebx, 70Ch
0x18000f8d8  jmp     loc_18000F9B0
0x18000f8dd  cmp     dword ptr [rsp+490h+Data], r15d
0x18000f8e2  jz      short loc_18000F8ED
0x18000f8e4  lea     rdx, aCopiedXmlIsNot; "Copied xml is not used"
0x18000f8eb  jmp     short loc_18000F8AB
0x18000f8ed  mov     rcx, [rsp+490h+hKey]; hKey
0x18000f8f2  lea     rax, [rsp+490h+cbData]
0x18000f8f7  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18000f8fc  lea     r9, [rsp+490h+Type]; lpType
0x18000f901  lea     rax, [rbp+390h+var_230]
0x18000f908  mov     [rsp+490h+cbData], 25Ch
0x18000f910  xor     r8d, r8d; lpReserved
0x18000f913  mov     [rsp+490h+phkResult], rax; lpData
0x18000f918  lea     rdx, aSourcereagentx; "SourceReAgentXmlPath"
0x18000f91f  call    cs:__imp_RegQueryValueExW
0x18000f925  mov     ebx, eax
0x18000f927  test    eax, eax
0x18000f929  jz      short loc_18000F93F
0x18000f92b  mov     dword ptr [rsp+490h+lpcbData], 3EEh
0x18000f933  lea     r8, aFailedToReadSo; "failed to read source recovery file pat"...
0x18000f93a  jmp     loc_18000F74B
0x18000f93f  mov     r8d, [rsp+490h+Type]
0x18000f944  mov     r9d, [rsp+490h+cbData]
0x18000f949  cmp     r8d, r15d
0x18000f94c  jnz     short loc_18000F99C
0x18000f94e  test    r9d, r9d
0x18000f951  jz      short loc_18000F99C
0x18000f953  mov     r9, rdi
0x18000f956  lea     r8, [rbp+390h+var_230]
0x18000f95d  lea     rdx, aUpdateTheSourc; " Update the source xml file path [%s] w"...
0x18000f964  xor     ecx, ecx
0x18000f966  call    UnattendLogW
0x18000f96b  xor     r8d, r8d; bFailIfExists
0x18000f96e  lea     rdx, [rbp+390h+var_230]; lpNewFileName
0x18000f975  mov     rcx, rdi; lpExistingFileName
0x18000f978  call    cs:__imp_CopyFileW
0x18000f97e  test    eax, eax
0x18000f980  jnz     short loc_18000F9B0
0x18000f982  call    cs:__imp_GetLastError
0x18000f988  lea     r8, aFailedToCopyRe_3; "failed to copy recovery file"
0x18000f98f  mov     dword ptr [rsp+490h+lpcbData], 3FDh
0x18000f997  jmp     loc_18000F749
0x18000f99c  lea     rdx, aGetUnexpectedR; "Get unexpected registry value type/leng"...
0x18000f9a3  mov     ecx, r15d
0x18000f9a6  mov     ebx, 57h ; 'W'
0x18000f9ab  call    UnattendLogW
0x18000f9b0  mov     rcx, [rsp+490h+hKey]; hKey
0x18000f9b5  test    rcx, rcx
0x18000f9b8  jz      short loc_18000F9C0
0x18000f9ba  call    cs:__imp_RegCloseKey
0x18000f9c0  mov     eax, ebx
0x18000f9c2  mov     rcx, [rbp+390h+var_20]
0x18000f9c9  xor     rcx, rsp; StackCookie
0x18000f9cc  call    __security_check_cookie
0x18000f9d1  lea     r11, [rsp+490h+var_10]
0x18000f9d9  mov     rbx, [r11+28h]
0x18000f9dd  mov     rsi, [r11+30h]
0x18000f9e1  mov     rsp, r11
0x18000f9e4  pop     r15
0x18000f9e6  pop     rdi
0x18000f9e7  pop     rbp
0x18000f9e8  retn
```
