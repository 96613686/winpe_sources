# winreGetCopiedRecoveryFilePath(ushort const *,ushort * *)

- ea: `0x18000e7a8`
- end: `0x18000eb16`
- name: `?winreGetCopiedRecoveryFilePath@@YAKPEBGPEAPEAG@Z`
- size: `878`
- prototype: `unsigned int __fastcall(wchar_t *String1, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800109f8`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000e7a8`
- `0x18000ed74`
- `0x18000ff68`
- `0x18000ffcc`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e830`
- `msvcrt!_wcsicmp` at `0x18000e830`
- `KERNEL32!GetLastError` at `0x18000e9a9`
- `KERNEL32!GetLastError` at `0x18000ea6f`
- `KERNEL32!GetLastError` at `0x18000e9a9`
- `KERNEL32!GetLastError` at `0x18000ea6f`
- `KERNEL32!CreateFileW` at `0x18000ea60`
- `KERNEL32!CreateFileW` at `0x18000ea60`
- `KERNEL32!CloseHandle` at `0x18000eaab`
- `KERNEL32!CloseHandle` at `0x18000eaab`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000e99f`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000e99f`
- `ADVAPI32!RegQueryValueExW` at `0x18000e8d8`
- `ADVAPI32!RegQueryValueExW` at `0x18000e8d8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e86d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e86d`
- `ADVAPI32!RegCloseKey` at `0x18000ead2`
- `ADVAPI32!RegCloseKey` at `0x18000ead2`
- `ole32!CoTaskMemFree` at `0x18000eaec`
- `ole32!CoTaskMemFree` at `0x18000eaec`

## string_xrefs

- `0x18000e888`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000e957`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000ea00`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000e881`: `failed to open recovery environment key`
- `0x18000e892`: `winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x18000e97a`: `winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x18000ea23`: `winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x18000e8d1`: `ReAgentXmlCopiedToRamdisk`
- `0x18000e905`: `Target registry key not found. Reagent.xml is not copied to ramdisk`
- `0x18000e8ef`: `failed to query registry value whether reagent.xml is copied to ramdisk. Error: 0x%08X`
- `0x18000e91b`: `Get unexpected registry value type %d`
- `0x18000e93c`: `Reagent.xml is not copied to ramdisk`
- `0x18000e96e`: `failed to allocate path`
- `0x18000e9b7`: `failed to get Windows directory`
- `0x18000e9e7`: `Recovery\ReAgentCopied.xml`
- `0x18000ea78`: `failed to open copied recovery file %s. Error: 0x%08X`
- `0x18000e826`: `ReAgent.xml`

## pseudocode

```c
__int64 __fastcall winreGetCopiedRecoveryFilePath(wchar_t *String1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  __int64 v5; // rbx
  const wchar_t *v6; // r8
  unsigned int v7; // eax
  DWORD LastError; // eax
  int v9; // r14d
  HANDLE FileW; // r14
  LPDWORD lpcbData; // [rsp+28h] [rbp-48h]
  LPWSTR lpBuffer; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+54h] [rbp-1Ch] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-18h] BYREF

  v2 = 0;
  lpBuffer = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  UnattendLogW(0, L"Looking for copied recovery file");
  if ( String1 && a2 )
  {
    *a2 = 0;
    if ( !(unsigned int)winreIsWinPE() )
    {
      UnattendLogW(0, L"Copied recovery file can only be used in WinPE");
LABEL_5:
      LODWORD(v5) = 0;
      goto LABEL_32;
    }
    if ( _wcsicmp(String1, L"ReAgent.xml") )
    {
      UnattendLogW(0, L"[%s] isn't supported for copied recovery file", String1);
      goto LABEL_5;
    }
    LODWORD(v5) = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 1u, &hKey);
    if ( (_DWORD)v5 )
    {
      LODWORD(lpcbData) = 560;
      v6 = L"failed to open recovery environment key";
LABEL_10:
      UnattendLogW(
        2,
        L"winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d",
        v6,
        (unsigned int)v5,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        lpcbData);
      goto LABEL_32;
    }
    cbData = 4;
    v7 = RegQueryValueExW(hKey, L"ReAgentXmlCopiedToRamdisk", 0, &Type, Data, &cbData);
    LODWORD(v5) = v7;
    if ( v7 )
    {
      if ( v7 - 2 <= 1 )
      {
        UnattendLogW(0, L"Target registry key not found. Reagent.xml is not copied to ramdisk");
        goto LABEL_5;
      }
      UnattendLogW(1, L"failed to query registry value whether reagent.xml is copied to ramdisk. Error: 0x%08X", v7);
    }
    else if ( Type == 4 )
    {
      if ( *(_DWORD *)Data != 1 )
      {
        UnattendLogW(0, L"Reagent.xml is not copied to ramdisk");
        goto LABEL_5;
      }
      LODWORD(v5) = winreAllocPath(&lpBuffer);
      if ( (_DWORD)v5 )
      {
        LODWORD(lpcbData) = 592;
        UnattendLogW(
          2,
          L"winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d",
          L"failed to allocate path",
          (unsigned int)v5,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          lpcbData);
        v2 = lpBuffer;
      }
      else
      {
        v2 = lpBuffer;
        if ( !GetWindowsDirectoryW(lpBuffer, 0x12Eu) )
        {
          LastError = GetLastError();
          LODWORD(lpcbData) = 598;
          v6 = L"failed to get Windows directory";
          LODWORD(v5) = LastError;
          goto LABEL_10;
        }
        LODWORD(v5) = winreAddTrailingBackslash(v2);
        if ( (_DWORD)v5 )
        {
          LODWORD(lpcbData) = 603;
          v6 = L"failed to add trailing back slash";
          goto LABEL_10;
        }
        v9 = StringCchCatW(v2, 0x12Eu, L"Recovery\\ReAgentCopied.xml");
        if ( v9 >= 0 )
        {
          FileW = CreateFileW(v2, 0x80000000, 7u, 0, 3u, 0, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            v5 = GetLastError();
            UnattendLogW(1, L"failed to open copied recovery file %s. Error: 0x%08X", v2, v5);
          }
          else
          {
            UnattendLogW(0, L" Using copied recovery file at %s on ramdisk", v2);
            *a2 = v2;
            if ( FileW )
              CloseHandle(FileW);
          }
        }
        else
        {
          LODWORD(lpcbData) = 606;
          UnattendLogW(
            2,
            L"winreGetCopiedRecoveryFilePath %s (0x%x) in file %S line %d",
            L"failed to concatenate recovery file name",
            (unsigned int)v9,
            "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
            lpcbData);
          LODWORD(v5) = (unsigned __int16)v9;
        }
      }
    }
    else
    {
      UnattendLogW(1, L"Get unexpected registry value type %d");
      LODWORD(v5) = 1804;
    }
  }
  else
  {
    UnattendLogW(1, L"Invalid parameter");
    LODWORD(v5) = 87;
  }
LABEL_32:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (_DWORD)v5 && v2 )
    CoTaskMemFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e7a8  mov     [rsp-18h+arg_10], rbx
0x18000e7ad  mov     [rsp-18h+arg_18], rdi
0x18000e7b2  push    rbp
0x18000e7b3  push    r14
0x18000e7b5  push    r15
0x18000e7b7  mov     rbp, rsp
0x18000e7ba  sub     rsp, 70h
0x18000e7be  mov     rax, cs:__security_cookie
0x18000e7c5  xor     rax, rsp
0x18000e7c8  mov     [rbp+var_10], rax
0x18000e7cc  xor     edi, edi
0x18000e7ce  mov     r15, rdx
0x18000e7d1  mov     rbx, rcx
0x18000e7d4  mov     [rbp+lpBuffer], rdi
0x18000e7d8  lea     rdx, aLookingForCopi; "Looking for copied recovery file"
0x18000e7df  mov     [rbp+Type], edi
0x18000e7e2  xor     ecx, ecx
0x18000e7e4  mov     [rbp+cbData], edi
0x18000e7e7  mov     [rbp+hKey], rdi
0x18000e7eb  mov     dword ptr [rbp+Data], edi
0x18000e7ee  call    UnattendLogW
0x18000e7f3  test    rbx, rbx
0x18000e7f6  jz      loc_18000EAB3
0x18000e7fc  test    r15, r15
0x18000e7ff  jz      loc_18000EAB3
0x18000e805  mov     [r15], rdi
0x18000e808  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18000e80d  test    eax, eax
0x18000e80f  jnz     short loc_18000E826
0x18000e811  lea     rdx, aCopiedRecovery; "Copied recovery file can only be used i"...
0x18000e818  xor     ecx, ecx
0x18000e81a  call    UnattendLogW
0x18000e81f  xor     ebx, ebx
0x18000e821  jmp     loc_18000EAC9
0x18000e826  lea     rdx, aReagentXml_0; "ReAgent.xml"
0x18000e82d  mov     rcx, rbx; String1
0x18000e830  call    cs:__imp__wcsicmp
0x18000e836  test    eax, eax
0x18000e838  jz      short loc_18000E84D
0x18000e83a  mov     r8, rbx
0x18000e83d  lea     rdx, aSIsnTSupported_0; "[%s] isn't supported for copied recover"...
0x18000e844  xor     ecx, ecx
0x18000e846  call    UnattendLogW
0x18000e84b  jmp     short loc_18000E81F
0x18000e84d  lea     rax, [rbp+hKey]
0x18000e851  mov     r9d, 1; samDesired
0x18000e857  xor     r8d, r8d; ulOptions
0x18000e85a  mov     [rsp+70h+phkResult], rax; phkResult
0x18000e85f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18000e866  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e86d  call    cs:__imp_RegOpenKeyExW
0x18000e873  mov     ebx, eax
0x18000e875  test    eax, eax
0x18000e877  jz      short loc_18000E8AD
0x18000e879  mov     dword ptr [rsp+70h+lpcbData], 230h
0x18000e881  lea     r8, aFailedToOpenRe_1; "failed to open recovery environment key"
0x18000e888  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000e88f  mov     r9d, ebx
0x18000e892  lea     rdx, aWinregetcopied; "winreGetCopiedRecoveryFilePath %s (0x%x"...
0x18000e899  mov     [rsp+70h+phkResult], rax
0x18000e89e  mov     ecx, 2
0x18000e8a3  call    UnattendLogW
0x18000e8a8  jmp     loc_18000EAC9
0x18000e8ad  mov     rcx, [rbp+hKey]; hKey
0x18000e8b1  lea     rax, [rbp+cbData]
0x18000e8b5  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000e8ba  lea     r9, [rbp+Type]; lpType
0x18000e8be  lea     rax, [rbp+Data]
0x18000e8c2  mov     [rbp+cbData], 4
0x18000e8c9  xor     r8d, r8d; lpReserved
0x18000e8cc  mov     [rsp+70h+phkResult], rax; lpData
0x18000e8d1  lea     rdx, aReagentxmlcopi; "ReAgentXmlCopiedToRamdisk"
0x18000e8d8  call    cs:__imp_RegQueryValueExW
0x18000e8de  mov     ebx, eax
0x18000e8e0  test    eax, eax
0x18000e8e2  jz      short loc_18000E911
0x18000e8e4  add     eax, 0FFFFFFFEh
0x18000e8e7  cmp     eax, 1
0x18000e8ea  jbe     short loc_18000E905
0x18000e8ec  mov     r8d, ebx
0x18000e8ef  lea     rdx, aFailedToQueryR; "failed to query registry value whether "...
0x18000e8f6  mov     ecx, 1
0x18000e8fb  call    UnattendLogW
0x18000e900  jmp     loc_18000EAC9
0x18000e905  lea     rdx, aTargetRegistry_0; "Target registry key not found. Reagent."...
0x18000e90c  jmp     loc_18000E818
0x18000e911  mov     r8d, [rbp+Type]
0x18000e915  cmp     r8d, 4
0x18000e919  jz      short loc_18000E936
0x18000e91b  lea     rdx, aGetUnexpectedR_0; "Get unexpected registry value type %d"
0x18000e922  mov     ecx, 1
0x18000e927  call    UnattendLogW
0x18000e92c  mov     ebx, 70Ch
0x18000e931  jmp     loc_18000EAC9
0x18000e936  cmp     dword ptr [rbp+Data], 1
0x18000e93a  jz      short loc_18000E948
0x18000e93c  lea     rdx, aReagentXmlIsNo; "Reagent.xml is not copied to ramdisk"
0x18000e943  jmp     loc_18000E818
0x18000e948  lea     rcx, [rbp+lpBuffer]
0x18000e94c  call    winreAllocPath
0x18000e951  mov     ebx, eax
0x18000e953  test    eax, eax
0x18000e955  jz      short loc_18000E98F
0x18000e957  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000e95e  mov     dword ptr [rsp+70h+lpcbData], 250h
0x18000e966  mov     r9d, ebx
0x18000e969  mov     [rsp+70h+phkResult], rax
0x18000e96e  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18000e975  mov     ecx, 2
0x18000e97a  lea     rdx, aWinregetcopied; "winreGetCopiedRecoveryFilePath %s (0x%x"...
0x18000e981  call    UnattendLogW
0x18000e986  mov     rdi, [rbp+lpBuffer]
0x18000e98a  jmp     loc_18000EAC9
0x18000e98f  mov     rdi, [rbp+lpBuffer]
0x18000e993  mov     r14d, 12Eh
0x18000e999  mov     edx, r14d; uSize
0x18000e99c  mov     rcx, rdi; lpBuffer
0x18000e99f  call    cs:__imp_GetWindowsDirectoryW
0x18000e9a5  test    eax, eax
0x18000e9a7  jnz     short loc_18000E9C5
0x18000e9a9  call    cs:__imp_GetLastError
0x18000e9af  mov     dword ptr [rsp+70h+lpcbData], 256h
0x18000e9b7  lea     r8, aFailedToGetWin; "failed to get Windows directory"
0x18000e9be  mov     ebx, eax
0x18000e9c0  jmp     loc_18000E888
0x18000e9c5  mov     rcx, rdi
0x18000e9c8  call    winreAddTrailingBackslash
0x18000e9cd  mov     ebx, eax
0x18000e9cf  test    eax, eax
0x18000e9d1  jz      short loc_18000E9E7
0x18000e9d3  mov     dword ptr [rsp+70h+lpcbData], 25Bh
0x18000e9db  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18000e9e2  jmp     loc_18000E888
0x18000e9e7  lea     r8, aRecoveryReagen_0; "Recovery\\ReAgentCopied.xml"
0x18000e9ee  mov     rdx, r14; unsigned __int64
0x18000e9f1  mov     rcx, rdi; unsigned __int16 *
0x18000e9f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e9f9  mov     r14d, eax
0x18000e9fc  test    eax, eax
0x18000e9fe  jns     short loc_18000EA38
0x18000ea00  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000ea07  mov     dword ptr [rsp+70h+lpcbData], 25Eh
0x18000ea0f  mov     r9d, r14d
0x18000ea12  mov     [rsp+70h+phkResult], rax
0x18000ea17  lea     r8, aFailedToConcat_6; "failed to concatenate recovery file nam"...
0x18000ea1e  mov     ecx, 2
0x18000ea23  lea     rdx, aWinregetcopied; "winreGetCopiedRecoveryFilePath %s (0x%x"...
0x18000ea2a  call    UnattendLogW
0x18000ea2f  movzx   ebx, r14w
0x18000ea33  jmp     loc_18000EAC9
0x18000ea38  xor     r9d, r9d; lpSecurityAttributes
0x18000ea3b  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18000ea44  mov     dword ptr [rsp+70h+lpcbData], 0; dwFlagsAndAttributes
0x18000ea4c  mov     edx, 80000000h; dwDesiredAccess
0x18000ea51  mov     rcx, rdi; lpFileName
0x18000ea54  mov     dword ptr [rsp+70h+phkResult], 3; dwCreationDisposition
0x18000ea5c  lea     r8d, [r9+7]; dwShareMode
0x18000ea60  call    cs:__imp_CreateFileW
0x18000ea66  mov     r14, rax
0x18000ea69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ea6d  jnz     short loc_18000EA8F
0x18000ea6f  call    cs:__imp_GetLastError
0x18000ea75  mov     r8, rdi
0x18000ea78  lea     rdx, aFailedToOpenCo; "failed to open copied recovery file %s."...
0x18000ea7f  mov     r9d, eax
0x18000ea82  lea     ecx, [r14+2]
0x18000ea86  mov     ebx, eax
0x18000ea88  call    UnattendLogW
0x18000ea8d  jmp     short loc_18000EAC9
0x18000ea8f  mov     r8, rdi
0x18000ea92  lea     rdx, aUsingCopiedRec; " Using copied recovery file at %s on ra"...
0x18000ea99  xor     ecx, ecx
0x18000ea9b  call    UnattendLogW
0x18000eaa0  mov     [r15], rdi
0x18000eaa3  test    r14, r14
0x18000eaa6  jz      short loc_18000EAC9
0x18000eaa8  mov     rcx, r14; hObject
0x18000eaab  call    cs:__imp_CloseHandle
0x18000eab1  jmp     short loc_18000EAC9
0x18000eab3  lea     rdx, aInvalidParamet_6; "Invalid parameter"
0x18000eaba  mov     ecx, 1
0x18000eabf  call    UnattendLogW
0x18000eac4  mov     ebx, 57h ; 'W'
0x18000eac9  mov     rcx, [rbp+hKey]; hKey
0x18000eacd  test    rcx, rcx
0x18000ead0  jz      short loc_18000EAE0
0x18000ead2  call    cs:__imp_RegCloseKey
0x18000ead8  mov     [rbp+hKey], 0
0x18000eae0  test    ebx, ebx
0x18000eae2  jz      short loc_18000EAF2
0x18000eae4  test    rdi, rdi
0x18000eae7  jz      short loc_18000EAF2
0x18000eae9  mov     rcx, rdi; pv
0x18000eaec  call    cs:__imp_CoTaskMemFree
0x18000eaf2  mov     eax, ebx
0x18000eaf4  mov     rcx, [rbp+var_10]
0x18000eaf8  xor     rcx, rsp; StackCookie
0x18000eafb  call    __security_check_cookie
0x18000eb00  lea     r11, [rsp+70h+var_s0]
0x18000eb05  mov     rbx, [r11+30h]
0x18000eb09  mov     rdi, [r11+38h]
0x18000eb0d  mov     rsp, r11
0x18000eb10  pop     r15
0x18000eb12  pop     r14
0x18000eb14  pop     rbp
0x18000eb15  retn
```
