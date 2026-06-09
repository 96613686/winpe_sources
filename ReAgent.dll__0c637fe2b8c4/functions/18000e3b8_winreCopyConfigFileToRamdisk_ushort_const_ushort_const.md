# winreCopyConfigFileToRamdisk(ushort const *,ushort const *)

- ea: `0x18000e3b8`
- end: `0x18000e79f`
- name: `?winreCopyConfigFileToRamdisk@@YAKPEBG0@Z`
- size: `999`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, wchar_t *String1)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800109f8`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c658`
- `0x18000e3b8`
- `0x18000ed74`
- `0x18000ff68`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e457`
- `msvcrt!_wcsicmp` at `0x18000e457`
- `KERNEL32!CopyFileW` at `0x18000e5f7`
- `KERNEL32!CopyFileW` at `0x18000e5f7`
- `KERNEL32!GetLastError` at `0x18000e488`
- `KERNEL32!GetLastError` at `0x18000e55e`
- `KERNEL32!GetLastError` at `0x18000e601`
- `KERNEL32!GetLastError` at `0x18000e488`
- `KERNEL32!GetLastError` at `0x18000e55e`
- `KERNEL32!GetLastError` at `0x18000e601`
- `KERNEL32!CreateDirectoryW` at `0x18000e554`
- `KERNEL32!CreateDirectoryW` at `0x18000e554`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000e47e`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000e47e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e63c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e63c`
- `ADVAPI32!RegSetValueExW` at `0x18000e68f`
- `ADVAPI32!RegSetValueExW` at `0x18000e6d3`
- `ADVAPI32!RegSetValueExW` at `0x18000e68f`
- `ADVAPI32!RegSetValueExW` at `0x18000e6d3`
- `ADVAPI32!RegCloseKey` at `0x18000e770`
- `ADVAPI32!RegCloseKey` at `0x18000e770`

## string_xrefs

- `0x18000e49f`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000e512`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000e709`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000e650`: `failed to open recovery environment key`
- `0x18000e6bf`: `ReAgentXmlCopiedToRamdisk`
- `0x18000e48e`: `failed to get Windows directory`
- `0x18000e409`: `Copying recovery file to ramdisk`
- `0x18000e464`: `[%s] isn't supported for copying recovery file to ramdisk`
- `0x18000e4a9`: `winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d`
- `0x18000e51c`: `winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d`
- `0x18000e72c`: `winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d`
- `0x18000e50b`: `failed to concatenate recovery directory`
- `0x18000e541`: ` Copy recovery file to %s`
- `0x18000e575`: `failed to create recovery directory %s. Error: 0x%08X`
- `0x18000e5a8`: `ReAgentCopied.xml`
- `0x18000e5de`: ` Copying recovery file from %s to %s`
- `0x18000e607`: `failed to copy recovery file`
- `0x18000e67a`: `SourceReAgentXmlPath`
- `0x18000e6a3`: `failed to write copied recovery file source path to registry`
- `0x18000e6e7`: `failed to write copied recovery file flag to registry`
- `0x18000e720`: `failed to copy copied recovery file path`
- `0x18000e44d`: `ReAgent.xml`

## pseudocode

```c
__int64 __fastcall winreCopyConfigFileToRamdisk(WCHAR *a1, wchar_t *String1)
{
  LSTATUS v4; // ebx
  DWORD LastError; // eax
  const wchar_t *v6; // r8
  const wchar_t *v7; // r8
  DWORD v8; // eax
  __int64 v9; // rax
  int v10; // esi
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(Buffer, 0, 0x208u);
  *(_DWORD *)Data = 1;
  hKey = 0;
  UnattendLogW(0, L"Copying recovery file to ramdisk");
  if ( !(unsigned int)winreIsWinPE() )
  {
    UnattendLogW(0, L"Copied recovery file can only be used in WinPE");
LABEL_3:
    v4 = 0;
    goto LABEL_39;
  }
  if ( a1 && String1 )
  {
    if ( _wcsicmp(String1, L"ReAgent.xml") )
    {
      UnattendLogW(0, L"[%s] isn't supported for copying recovery file to ramdisk", String1);
      goto LABEL_3;
    }
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      v6 = L"failed to get Windows directory";
      LODWORD(cbData) = 686;
LABEL_10:
      v4 = LastError;
LABEL_11:
      UnattendLogW(
        2,
        L"winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d",
        v6,
        (unsigned int)v4,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        cbData);
      goto LABEL_39;
    }
    v4 = winreAddTrailingBackslash(Buffer);
    if ( v4 )
    {
      LODWORD(cbData) = 691;
LABEL_14:
      v6 = L"failed to add trailing back slash";
      goto LABEL_11;
    }
    v4 = StringCchCatW(Buffer, 0x12Eu, L"Recovery");
    if ( v4 < 0 )
    {
      cbDataa = 694;
      v7 = L"failed to concatenate recovery directory";
LABEL_17:
      UnattendLogW(
        2,
        L"winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d",
        v7,
        (unsigned int)v4,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        cbDataa);
      v4 = (unsigned __int16)v4;
      goto LABEL_39;
    }
    UnattendLogW(0, L" Copy recovery file to %s", Buffer);
    if ( CreateDirectoryW(Buffer, 0) || (v8 = GetLastError(), v4 = v8, v8 == 183) )
    {
      v4 = winreAddTrailingBackslash(Buffer);
      if ( v4 )
      {
        LODWORD(cbData) = 717;
        goto LABEL_14;
      }
      v4 = StringCchCatW(Buffer, 0x12Eu, L"ReAgentCopied.xml");
      if ( v4 < 0 )
      {
        cbDataa = 720;
        v7 = L"failed to concatenate recovery file name";
        goto LABEL_17;
      }
      UnattendLogW(0, L" Copying recovery file from %s to %s", a1, Buffer);
      if ( !CopyFileW(a1, Buffer, 0) )
      {
        LastError = GetLastError();
        v6 = L"failed to copy recovery file";
        LODWORD(cbData) = 724;
        goto LABEL_10;
      }
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 2u, &hKey);
      if ( v4 )
      {
        LODWORD(cbData) = 731;
        v6 = L"failed to open recovery environment key";
        goto LABEL_11;
      }
      v9 = -1;
      do
        ++v9;
      while ( a1[v9] );
      v4 = RegSetValueExW(hKey, L"SourceReAgentXmlPath", 0, 1u, (const BYTE *)a1, 2 * v9 + 2);
      if ( v4 )
      {
        LODWORD(cbData) = 734;
        v6 = L"failed to write copied recovery file source path to registry";
        goto LABEL_11;
      }
      v4 = RegSetValueExW(hKey, L"ReAgentXmlCopiedToRamdisk", 0, 4u, Data, 4u);
      if ( v4 )
      {
        LODWORD(cbData) = 738;
        v6 = L"failed to write copied recovery file flag to registry";
        goto LABEL_11;
      }
      v10 = StringCchCopyW(a1, 0x12Eu, Buffer);
      if ( v10 >= 0 )
      {
        UnattendLogW(0, L" Using copied recovery file at %s on ramdisk", a1);
      }
      else
      {
        LODWORD(cbData) = 744;
        UnattendLogW(
          2,
          L"winreCopyConfigFileToRamdisk %s (0x%x) in file %S line %d",
          L"failed to copy copied recovery file path",
          (unsigned int)v10,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          cbData);
        v4 = (unsigned __int16)v10;
      }
    }
    else
    {
      UnattendLogW(1, L"failed to create recovery directory %s. Error: 0x%08X", Buffer, v8);
    }
  }
  else
  {
    UnattendLogW(1, L"Invalid parameter");
    v4 = 87;
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e3b8  mov     [rsp-8+arg_10], rbx
0x18000e3bd  mov     [rsp-8+arg_18], rsi
0x18000e3c2  push    rbp
0x18000e3c3  push    rdi
0x18000e3c4  push    r14
0x18000e3c6  lea     rbp, [rsp-160h]
0x18000e3ce  sub     rsp, 260h
0x18000e3d5  mov     rax, cs:__security_cookie
0x18000e3dc  xor     rax, rsp
0x18000e3df  mov     [rbp+170h+var_20], rax
0x18000e3e6  mov     rbx, rdx
0x18000e3e9  mov     rdi, rcx
0x18000e3ec  xor     edx, edx; Val
0x18000e3ee  lea     rcx, [rsp+270h+Buffer]; void *
0x18000e3f3  mov     r8d, 208h; Size
0x18000e3f9  call    memset_0
0x18000e3fe  xor     r14d, r14d
0x18000e401  mov     dword ptr [rsp+270h+Data], 1
0x18000e409  lea     rdx, aCopyingRecover; "Copying recovery file to ramdisk"
0x18000e410  mov     [rsp+270h+hKey], r14
0x18000e415  xor     ecx, ecx
0x18000e417  call    UnattendLogW
0x18000e41c  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18000e421  test    eax, eax
0x18000e423  jnz     short loc_18000E43B
0x18000e425  lea     rdx, aCopiedRecovery; "Copied recovery file can only be used i"...
0x18000e42c  xor     ecx, ecx
0x18000e42e  call    UnattendLogW
0x18000e433  mov     ebx, r14d
0x18000e436  jmp     loc_18000E766
0x18000e43b  test    rdi, rdi
0x18000e43e  jz      loc_18000E750
0x18000e444  test    rbx, rbx
0x18000e447  jz      loc_18000E750
0x18000e44d  lea     rdx, aReagentXml_0; "ReAgent.xml"
0x18000e454  mov     rcx, rbx; String1
0x18000e457  call    cs:__imp__wcsicmp
0x18000e45d  test    eax, eax
0x18000e45f  jz      short loc_18000E474
0x18000e461  mov     r8, rbx
0x18000e464  lea     rdx, aSIsnTSupported; "[%s] isn't supported for copying recove"...
0x18000e46b  xor     ecx, ecx
0x18000e46d  call    UnattendLogW
0x18000e472  jmp     short loc_18000E433
0x18000e474  mov     edx, 104h; uSize
0x18000e479  lea     rcx, [rsp+270h+Buffer]; lpBuffer
0x18000e47e  call    cs:__imp_GetWindowsDirectoryW
0x18000e484  test    eax, eax
0x18000e486  jnz     short loc_18000E4C4
0x18000e488  call    cs:__imp_GetLastError
0x18000e48e  lea     r8, aFailedToGetWin; "failed to get Windows directory"
0x18000e495  mov     dword ptr [rsp+270h+cbData], 2AEh
0x18000e49d  mov     ebx, eax
0x18000e49f  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000e4a6  mov     r9d, ebx
0x18000e4a9  lea     rdx, aWinrecopyconfi; "winreCopyConfigFileToRamdisk %s (0x%x) "...
0x18000e4b0  mov     [rsp+270h+phkResult], rax
0x18000e4b5  mov     ecx, 2
0x18000e4ba  call    UnattendLogW
0x18000e4bf  jmp     loc_18000E766
0x18000e4c4  lea     rcx, [rsp+270h+Buffer]
0x18000e4c9  call    winreAddTrailingBackslash
0x18000e4ce  mov     ebx, eax
0x18000e4d0  test    eax, eax
0x18000e4d2  jz      short loc_18000E4E5
0x18000e4d4  mov     dword ptr [rsp+270h+cbData], 2B3h
0x18000e4dc  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18000e4e3  jmp     short loc_18000E49F
0x18000e4e5  mov     esi, 12Eh
0x18000e4ea  lea     r8, AppName; "Recovery"
0x18000e4f1  mov     edx, esi; unsigned __int64
0x18000e4f3  lea     rcx, [rsp+270h+Buffer]; unsigned __int16 *
0x18000e4f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e4fd  mov     ebx, eax
0x18000e4ff  test    eax, eax
0x18000e501  jns     short loc_18000E53A
0x18000e503  mov     dword ptr [rsp+270h+cbData], 2B6h
0x18000e50b  lea     r8, aFailedToConcat_7; "failed to concatenate recovery director"...
0x18000e512  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000e519  mov     r9d, ebx
0x18000e51c  lea     rdx, aWinrecopyconfi; "winreCopyConfigFileToRamdisk %s (0x%x) "...
0x18000e523  mov     [rsp+270h+phkResult], rax
0x18000e528  mov     ecx, 2
0x18000e52d  call    UnattendLogW
0x18000e532  movzx   ebx, bx
0x18000e535  jmp     loc_18000E766
0x18000e53a  lea     r8, [rsp+270h+Buffer]
0x18000e53f  xor     ecx, ecx
0x18000e541  lea     rdx, aCopyRecoveryFi; " Copy recovery file to %s"
0x18000e548  call    UnattendLogW
0x18000e54d  xor     edx, edx; lpSecurityAttributes
0x18000e54f  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x18000e554  call    cs:__imp_CreateDirectoryW
0x18000e55a  test    eax, eax
0x18000e55c  jnz     short loc_18000E58B
0x18000e55e  call    cs:__imp_GetLastError
0x18000e564  mov     ebx, eax
0x18000e566  cmp     eax, 0B7h
0x18000e56b  jz      short loc_18000E58B
0x18000e56d  mov     r9d, eax
0x18000e570  lea     r8, [rsp+270h+Buffer]
0x18000e575  lea     rdx, aFailedToCreate_16; "failed to create recovery directory %s."...
0x18000e57c  mov     ecx, 1
0x18000e581  call    UnattendLogW
0x18000e586  jmp     loc_18000E766
0x18000e58b  lea     rcx, [rsp+270h+Buffer]
0x18000e590  call    winreAddTrailingBackslash
0x18000e595  mov     ebx, eax
0x18000e597  test    eax, eax
0x18000e599  jz      short loc_18000E5A8
0x18000e59b  mov     dword ptr [rsp+270h+cbData], 2CDh
0x18000e5a3  jmp     loc_18000E4DC
0x18000e5a8  lea     r8, aReagentcopiedX; "ReAgentCopied.xml"
0x18000e5af  mov     rdx, rsi; unsigned __int64
0x18000e5b2  lea     rcx, [rsp+270h+Buffer]; unsigned __int16 *
0x18000e5b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e5bc  mov     ebx, eax
0x18000e5be  test    eax, eax
0x18000e5c0  jns     short loc_18000E5D6
0x18000e5c2  mov     dword ptr [rsp+270h+cbData], 2D0h
0x18000e5ca  lea     r8, aFailedToConcat_6; "failed to concatenate recovery file nam"...
0x18000e5d1  jmp     loc_18000E512
0x18000e5d6  lea     r9, [rsp+270h+Buffer]
0x18000e5db  mov     r8, rdi
0x18000e5de  lea     rdx, aCopyingRecover_0; " Copying recovery file from %s to %s"
0x18000e5e5  xor     ecx, ecx
0x18000e5e7  call    UnattendLogW
0x18000e5ec  xor     r8d, r8d; bFailIfExists
0x18000e5ef  lea     rdx, [rsp+270h+Buffer]; lpNewFileName
0x18000e5f4  mov     rcx, rdi; lpExistingFileName
0x18000e5f7  call    cs:__imp_CopyFileW
0x18000e5fd  test    eax, eax
0x18000e5ff  jnz     short loc_18000E61B
0x18000e601  call    cs:__imp_GetLastError
0x18000e607  lea     r8, aFailedToCopyRe_3; "failed to copy recovery file"
0x18000e60e  mov     dword ptr [rsp+270h+cbData], 2D4h
0x18000e616  jmp     loc_18000E49D
0x18000e61b  lea     rax, [rsp+270h+hKey]
0x18000e620  mov     r9d, 2; samDesired
0x18000e626  xor     r8d, r8d; ulOptions
0x18000e629  mov     [rsp+270h+phkResult], rax; phkResult
0x18000e62e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18000e635  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e63c  call    cs:__imp_RegOpenKeyExW
0x18000e642  mov     ebx, eax
0x18000e644  test    eax, eax
0x18000e646  jz      short loc_18000E65C
0x18000e648  mov     dword ptr [rsp+270h+cbData], 2DBh
0x18000e650  lea     r8, aFailedToOpenRe_1; "failed to open recovery environment key"
0x18000e657  jmp     loc_18000E49F
0x18000e65c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e660  inc     rax
0x18000e663  cmp     [rdi+rax*2], r14w
0x18000e668  jnz     short loc_18000E660
0x18000e66a  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e66f  lea     eax, ds:2[rax*2]
0x18000e676  mov     dword ptr [rsp+270h+cbData], eax; cbData
0x18000e67a  lea     rdx, aSourcereagentx; "SourceReAgentXmlPath"
0x18000e681  mov     r9d, 1; dwType
0x18000e687  mov     [rsp+270h+phkResult], rdi; lpData
0x18000e68c  xor     r8d, r8d; Reserved
0x18000e68f  call    cs:__imp_RegSetValueExW
0x18000e695  mov     ebx, eax
0x18000e697  test    eax, eax
0x18000e699  jz      short loc_18000E6AF
0x18000e69b  mov     dword ptr [rsp+270h+cbData], 2DEh
0x18000e6a3  lea     r8, aFailedToWriteC_1; "failed to write copied recovery file so"...
0x18000e6aa  jmp     loc_18000E49F
0x18000e6af  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e6b4  lea     rax, [rsp+270h+Data]
0x18000e6b9  mov     r9d, 4; dwType
0x18000e6bf  lea     rdx, aReagentxmlcopi; "ReAgentXmlCopiedToRamdisk"
0x18000e6c6  mov     dword ptr [rsp+270h+cbData], r9d; cbData
0x18000e6cb  xor     r8d, r8d; Reserved
0x18000e6ce  mov     [rsp+270h+phkResult], rax; lpData
0x18000e6d3  call    cs:__imp_RegSetValueExW
0x18000e6d9  mov     ebx, eax
0x18000e6db  test    eax, eax
0x18000e6dd  jz      short loc_18000E6F3
0x18000e6df  mov     dword ptr [rsp+270h+cbData], 2E2h
0x18000e6e7  lea     r8, aFailedToWriteC_0; "failed to write copied recovery file fl"...
0x18000e6ee  jmp     loc_18000E49F
0x18000e6f3  lea     r8, [rsp+270h+Buffer]; unsigned __int16 *
0x18000e6f8  mov     rdx, rsi; unsigned __int64
0x18000e6fb  mov     rcx, rdi; unsigned __int16 *
0x18000e6fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e703  mov     esi, eax
0x18000e705  test    eax, eax
0x18000e707  jns     short loc_18000E73D
0x18000e709  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000e710  mov     dword ptr [rsp+270h+cbData], 2E8h
0x18000e718  mov     r9d, esi
0x18000e71b  mov     [rsp+270h+phkResult], rax
0x18000e720  lea     r8, aFailedToCopyCo; "failed to copy copied recovery file pat"...
0x18000e727  mov     ecx, 2
0x18000e72c  lea     rdx, aWinrecopyconfi; "winreCopyConfigFileToRamdisk %s (0x%x) "...
0x18000e733  call    UnattendLogW
0x18000e738  movzx   ebx, si
0x18000e73b  jmp     short loc_18000E766
0x18000e73d  mov     r8, rdi
0x18000e740  lea     rdx, aUsingCopiedRec; " Using copied recovery file at %s on ra"...
0x18000e747  xor     ecx, ecx
0x18000e749  call    UnattendLogW
0x18000e74e  jmp     short loc_18000E766
0x18000e750  lea     rdx, aInvalidParamet_6; "Invalid parameter"
0x18000e757  mov     ecx, 1
0x18000e75c  call    UnattendLogW
0x18000e761  mov     ebx, 57h ; 'W'
0x18000e766  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e76b  test    rcx, rcx
0x18000e76e  jz      short loc_18000E776
0x18000e770  call    cs:__imp_RegCloseKey
0x18000e776  mov     eax, ebx
0x18000e778  mov     rcx, [rbp+170h+var_20]
0x18000e77f  xor     rcx, rsp; StackCookie
0x18000e782  call    __security_check_cookie
0x18000e787  lea     r11, [rsp+270h+var_10]
0x18000e78f  mov     rbx, [r11+30h]
0x18000e793  mov     rsi, [r11+38h]
0x18000e797  mov     rsp, r11
0x18000e79a  pop     r14
0x18000e79c  pop     rdi
0x18000e79d  pop     rbp
0x18000e79e  retn
```
