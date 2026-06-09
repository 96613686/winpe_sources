# winreGetRecoveryFilePath

- ea: `0x1800109f8`
- end: `0x180010e71`
- name: `winreGetRecoveryFilePath`
- size: `1145`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800109d0`
- `0x180018870`
- `0x18001a1ac`
- `0x1800224f0`
- `0x180026158`
- `0x180041de4`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000c6f0`
- `0x18000e3b8`
- `0x18000e7a8`
- `0x18000ed74`
- `0x18000ff68`
- `0x18000ffcc`
- `0x1800103f4`
- `0x18001051c`
- `0x1800109f8`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180010ba6`
- `ADVAPI32!RegQueryValueExW` at `0x180010ce0`
- `ADVAPI32!RegQueryValueExW` at `0x180010ba6`
- `ADVAPI32!RegQueryValueExW` at `0x180010ce0`
- `ADVAPI32!RegOpenKeyExW` at `0x180010af2`
- `ADVAPI32!RegOpenKeyExW` at `0x180010af2`
- `ADVAPI32!RegCloseKey` at `0x180010c75`
- `ADVAPI32!RegCloseKey` at `0x180010c75`
- `ole32!CoTaskMemFree` at `0x180010c8f`
- `ole32!CoTaskMemFree` at `0x180010c8f`

## string_xrefs

- `0x180010aa9`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010b46`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010c0e`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010e3a`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010b06`: `failed to open recovery environment key`
- `0x180010aa2`: `failed to allocate path`
- `0x180010ab3`: `winreGetRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x180010b50`: `winreGetRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x180010c18`: `winreGetRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x180010e5d`: `winreGetRecoveryFilePath %s (0x%x) in file %S line %d`
- `0x180010b3f`: `failed to get copied recovery file path`
- `0x180010b9f`: `SourceWimPath`
- `0x180010c4c`: `failed to copy recovery file to ramdisk`
- `0x180010cf4`: `failed to read target OS reg value`
- `0x180010d2d`: `system32\`
- `0x180010d4d`: `failed to concatenate string system32`
- `0x180010d79`: `faile to concatenate recovery root directory`
- `0x180010da8`: `failed to find main os config directory`
- `0x180010dfd`: `%s\system32\%s`

## pseudocode

```c
__int64 __fastcall winreGetRecoveryFilePath(__int64 a1, int a2, int a3, wchar_t *a4, unsigned __int16 **a5)
{
  int CopiedRecoveryFilePath; // ebx
  const wchar_t *v10; // r8
  unsigned __int16 *v11; // rdi
  const wchar_t *v12; // r8
  const wchar_t *v13; // r8
  __int64 v15; // r9
  int v16; // esi
  LPDWORD lpcbData; // [rsp+28h] [rbp-28h]
  int lpcbDataa; // [rsp+28h] [rbp-28h]
  LPBYTE lpData; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+44h] [rbp-Ch] BYREF

  lpData = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( a1 )
  {
    CopiedRecoveryFilePath = winreAllocPath(&lpData);
    if ( CopiedRecoveryFilePath )
    {
      lpcbDataa = 872;
      goto LABEL_9;
    }
    v15 = a1;
    v11 = (unsigned __int16 *)lpData;
    if ( StringCchPrintfW((unsigned __int16 *)lpData, 0x12Eu, L"%s\\system32\\%s", v15, L"Recovery") < 0 )
    {
      CopiedRecoveryFilePath = -1073741811;
      goto LABEL_31;
    }
  }
  else
  {
    if ( (unsigned int)winreIsWinPE() && !ReAgentError )
      ReAgentError = 9;
    if ( a2 && (unsigned int)winreIsWinPE() )
    {
      CopiedRecoveryFilePath = winreAllocPath(&lpData);
      if ( CopiedRecoveryFilePath )
      {
        lpcbDataa = 785;
LABEL_9:
        v10 = L"failed to allocate path";
LABEL_10:
        UnattendLogW(
          2,
          L"winreGetRecoveryFilePath %s (0x%x) in file %S line %d",
          v10,
          (unsigned int)CopiedRecoveryFilePath,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          lpcbDataa);
        v11 = (unsigned __int16 *)lpData;
        goto LABEL_31;
      }
      CopiedRecoveryFilePath = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Microsoft\\RecoveryEnvironment",
                                 0,
                                 1u,
                                 &hKey);
      if ( CopiedRecoveryFilePath )
      {
        lpcbDataa = 789;
        v10 = L"failed to open recovery environment key";
        goto LABEL_10;
      }
      v11 = (unsigned __int16 *)lpData;
      cbData = 604;
      if ( a3 )
      {
        CopiedRecoveryFilePath = winreGetCopiedRecoveryFilePath(a4, a5);
        if ( CopiedRecoveryFilePath )
        {
          LODWORD(lpcbData) = 796;
          v12 = L"failed to get copied recovery file path";
LABEL_16:
          UnattendLogW(
            2,
            L"winreGetRecoveryFilePath %s (0x%x) in file %S line %d",
            v12,
            (unsigned int)CopiedRecoveryFilePath,
            "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
            lpcbData);
          goto LABEL_31;
        }
        if ( *a5 )
        {
          UnattendLogW(0, L" Using recovery file at %s");
          goto LABEL_31;
        }
        if ( !RegQueryValueExW(hKey, L"SourceWimPath", 0, &Type, (LPBYTE)v11, &cbData)
          && (unsigned int)winreDoesFileExist(v11, a4) )
        {
          CopiedRecoveryFilePath = winreAddTrailingBackslash(v11);
          if ( CopiedRecoveryFilePath )
          {
            LODWORD(lpcbData) = 821;
LABEL_23:
            v12 = L"failed to add trailing back slash";
            goto LABEL_16;
          }
          CopiedRecoveryFilePath = StringCchCatW(v11, 0x12Eu, a4);
          if ( CopiedRecoveryFilePath < 0 )
          {
            LODWORD(lpcbData) = 824;
            v13 = L"failed to concatenate recovery file name";
LABEL_26:
            UnattendLogW(
              2,
              L"winreGetRecoveryFilePath %s (0x%x) in file %S line %d",
              v13,
              (unsigned int)CopiedRecoveryFilePath,
              "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
              lpcbData);
            CopiedRecoveryFilePath = (unsigned __int16)CopiedRecoveryFilePath;
            goto LABEL_31;
          }
          CopiedRecoveryFilePath = winreCopyConfigFileToRamdisk(v11, a4);
          if ( CopiedRecoveryFilePath )
          {
            LODWORD(lpcbData) = 830;
            v12 = L"failed to copy recovery file to ramdisk";
            goto LABEL_16;
          }
          UnattendLogW(0, L" Using recovery file at %s", v11);
          goto LABEL_30;
        }
      }
      cbData = 604;
      CopiedRecoveryFilePath = RegQueryValueExW(hKey, L"TargetOS", 0, &Type, (LPBYTE)v11, &cbData);
      if ( CopiedRecoveryFilePath )
      {
        LODWORD(lpcbData) = 841;
        v12 = L"failed to read target OS reg value";
        goto LABEL_16;
      }
      if ( Type != 1 || !cbData )
      {
        CopiedRecoveryFilePath = 87;
        goto LABEL_31;
      }
      CopiedRecoveryFilePath = winreAddTrailingBackslash(v11);
      if ( CopiedRecoveryFilePath )
      {
        LODWORD(lpcbData) = 849;
        goto LABEL_23;
      }
      CopiedRecoveryFilePath = StringCchCatW(v11, 0x12Eu, L"system32\\");
      if ( CopiedRecoveryFilePath < 0 )
      {
        LODWORD(lpcbData) = 852;
        v13 = L"failed to concatenate string system32";
        goto LABEL_26;
      }
      CopiedRecoveryFilePath = StringCchCatW(v11, 0x12Eu, L"Recovery");
      if ( CopiedRecoveryFilePath < 0 )
      {
        LODWORD(lpcbData) = 855;
        v13 = L"faile to concatenate recovery root directory";
        goto LABEL_26;
      }
    }
    else
    {
      CopiedRecoveryFilePath = winreFindMainOsConfigDir(0);
      if ( CopiedRecoveryFilePath )
      {
        lpcbDataa = 863;
        v10 = L"failed to find main os config directory";
        goto LABEL_10;
      }
      v11 = (unsigned __int16 *)lpData;
    }
  }
  CopiedRecoveryFilePath = winreAddTrailingBackslash(v11);
  if ( CopiedRecoveryFilePath )
  {
    LODWORD(lpcbData) = 885;
    goto LABEL_23;
  }
  v16 = StringCchCatW(v11, 0x12Eu, a4);
  if ( v16 >= 0 )
  {
LABEL_30:
    *a5 = v11;
    goto LABEL_31;
  }
  LODWORD(lpcbData) = 889;
  UnattendLogW(
    2,
    L"winreGetRecoveryFilePath %s (0x%x) in file %S line %d",
    L"failed to concatenate recovery file name",
    (unsigned int)v16,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
    lpcbData);
  CopiedRecoveryFilePath = (unsigned __int16)v16;
LABEL_31:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( CopiedRecoveryFilePath && v11 )
    CoTaskMemFree(v11);
  return (unsigned int)CopiedRecoveryFilePath;
}

```

## disassembly

```asm
0x1800109f8  mov     [rsp-28h+arg_8], rbx
0x1800109fd  mov     [rsp-28h+arg_10], rsi
0x180010a02  push    rbp
0x180010a03  push    rdi
0x180010a04  push    r13
0x180010a06  push    r14
0x180010a08  push    r15
0x180010a0a  mov     rbp, rsp
0x180010a0d  sub     rsp, 50h
0x180010a11  mov     rax, cs:__security_cookie
0x180010a18  xor     rax, rsp
0x180010a1b  mov     [rbp+var_8], rax
0x180010a1f  mov     r14, [rbp+arg_20]
0x180010a23  mov     rsi, r9
0x180010a26  mov     [rbp+lpData], 0
0x180010a2e  mov     r15d, r8d
0x180010a31  mov     [rbp+hKey], 0
0x180010a39  mov     ebx, edx
0x180010a3b  mov     [rbp+Type], 0
0x180010a42  mov     rdi, rcx
0x180010a45  mov     [rbp+cbData], 0
0x180010a4c  mov     r13d, 12Eh
0x180010a52  test    rcx, rcx
0x180010a55  jnz     loc_180010DD3
0x180010a5b  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x180010a60  test    eax, eax
0x180010a62  jz      short loc_180010A76
0x180010a64  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, edi; _ReAgentErrorCodes ReAgentError
0x180010a6a  jnz     short loc_180010A76
0x180010a6c  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 9; _ReAgentErrorCodes ReAgentError
0x180010a76  test    ebx, ebx
0x180010a78  jz      loc_180010D8F
0x180010a7e  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x180010a83  test    eax, eax
0x180010a85  jz      loc_180010D8F
0x180010a8b  lea     rcx, [rbp+lpData]
0x180010a8f  call    winreAllocPath
0x180010a94  mov     ebx, eax
0x180010a96  test    eax, eax
0x180010a98  jz      short loc_180010AD2
0x180010a9a  mov     dword ptr [rsp+50h+lpcbData], 311h
0x180010aa2  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180010aa9  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010ab0  mov     r9d, ebx
0x180010ab3  lea     rdx, aWinregetrecove_1; "winreGetRecoveryFilePath %s (0x%x) in f"...
0x180010aba  mov     [rsp+50h+phkResult], rax
0x180010abf  mov     ecx, 2
0x180010ac4  call    UnattendLogW
0x180010ac9  mov     rdi, [rbp+lpData]
0x180010acd  jmp     loc_180010C6C
0x180010ad2  lea     rax, [rbp+hKey]
0x180010ad6  mov     r9d, 1; samDesired
0x180010adc  xor     r8d, r8d; ulOptions
0x180010adf  mov     [rsp+50h+phkResult], rax; phkResult
0x180010ae4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x180010aeb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010af2  call    cs:__imp_RegOpenKeyExW
0x180010af8  mov     ebx, eax
0x180010afa  test    eax, eax
0x180010afc  jz      short loc_180010B0F
0x180010afe  mov     dword ptr [rsp+50h+lpcbData], 315h
0x180010b06  lea     r8, aFailedToOpenRe_1; "failed to open recovery environment key"
0x180010b0d  jmp     short loc_180010AA9
0x180010b0f  mov     rdi, [rbp+lpData]
0x180010b13  mov     r13d, 25Ch
0x180010b19  mov     [rbp+cbData], r13d
0x180010b1d  test    r15d, r15d
0x180010b20  jz      loc_180010CBC
0x180010b26  mov     rdx, r14; unsigned __int16 **
0x180010b29  mov     rcx, rsi; String1
0x180010b2c  call    ?winreGetCopiedRecoveryFilePath@@YAKPEBGPEAPEAG@Z; winreGetCopiedRecoveryFilePath(ushort const *,ushort * *)
0x180010b31  mov     ebx, eax
0x180010b33  test    eax, eax
0x180010b35  jz      short loc_180010B6B
0x180010b37  mov     dword ptr [rsp+50h+lpcbData], 31Ch
0x180010b3f  lea     r8, aFailedToGetCop; "failed to get copied recovery file path"
0x180010b46  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010b4d  mov     r9d, ebx
0x180010b50  lea     rdx, aWinregetrecove_1; "winreGetRecoveryFilePath %s (0x%x) in f"...
0x180010b57  mov     [rsp+50h+phkResult], rax
0x180010b5c  mov     ecx, 2
0x180010b61  call    UnattendLogW
0x180010b66  jmp     loc_180010C6C
0x180010b6b  mov     r8, [r14]
0x180010b6e  test    r8, r8
0x180010b71  jz      short loc_180010B86
0x180010b73  lea     rdx, aUsingRecoveryF; " Using recovery file at %s"
0x180010b7a  xor     ecx, ecx
0x180010b7c  call    UnattendLogW
0x180010b81  jmp     loc_180010C6C
0x180010b86  mov     rcx, [rbp+hKey]; hKey
0x180010b8a  lea     rax, [rbp+cbData]
0x180010b8e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180010b93  lea     r9, [rbp+Type]; lpType
0x180010b97  xor     r8d, r8d; lpReserved
0x180010b9a  mov     [rsp+50h+phkResult], rdi; lpData
0x180010b9f  lea     rdx, aSourcewimpath; "SourceWimPath"
0x180010ba6  call    cs:__imp_RegQueryValueExW
0x180010bac  test    eax, eax
0x180010bae  jnz     loc_180010CBC
0x180010bb4  mov     rdx, rsi; unsigned __int16 *
0x180010bb7  mov     rcx, rdi; unsigned __int16 *
0x180010bba  call    winreDoesFileExist
0x180010bbf  test    eax, eax
0x180010bc1  jz      loc_180010CBC
0x180010bc7  mov     rcx, rdi
0x180010bca  call    winreAddTrailingBackslash
0x180010bcf  mov     ebx, eax
0x180010bd1  test    eax, eax
0x180010bd3  jz      short loc_180010BE9
0x180010bd5  mov     dword ptr [rsp+50h+lpcbData], 335h
0x180010bdd  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180010be4  jmp     loc_180010B46
0x180010be9  mov     r8, rsi; unsigned __int16 *
0x180010bec  mov     edx, 12Eh; unsigned __int64
0x180010bf1  mov     rcx, rdi; unsigned __int16 *
0x180010bf4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010bf9  mov     ebx, eax
0x180010bfb  test    eax, eax
0x180010bfd  jns     short loc_180010C33
0x180010bff  mov     dword ptr [rsp+50h+lpcbData], 338h
0x180010c07  lea     r8, aFailedToConcat_6; "failed to concatenate recovery file nam"...
0x180010c0e  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010c15  mov     r9d, ebx
0x180010c18  lea     rdx, aWinregetrecove_1; "winreGetRecoveryFilePath %s (0x%x) in f"...
0x180010c1f  mov     [rsp+50h+phkResult], rax
0x180010c24  mov     ecx, 2
0x180010c29  call    UnattendLogW
0x180010c2e  movzx   ebx, bx
0x180010c31  jmp     short loc_180010C6C
0x180010c33  mov     rdx, rsi; String1
0x180010c36  mov     rcx, rdi; unsigned __int16 *
0x180010c39  call    ?winreCopyConfigFileToRamdisk@@YAKPEBG0@Z; winreCopyConfigFileToRamdisk(ushort const *,ushort const *)
0x180010c3e  mov     ebx, eax
0x180010c40  test    eax, eax
0x180010c42  jz      short loc_180010C58
0x180010c44  mov     dword ptr [rsp+50h+lpcbData], 33Eh
0x180010c4c  lea     r8, aFailedToCopyRe_1; "failed to copy recovery file to ramdisk"
0x180010c53  jmp     loc_180010B46
0x180010c58  mov     r8, rdi
0x180010c5b  lea     rdx, aUsingRecoveryF; " Using recovery file at %s"
0x180010c62  xor     ecx, ecx
0x180010c64  call    UnattendLogW
0x180010c69  mov     [r14], rdi
0x180010c6c  mov     rcx, [rbp+hKey]; hKey
0x180010c70  test    rcx, rcx
0x180010c73  jz      short loc_180010C83
0x180010c75  call    cs:__imp_RegCloseKey
0x180010c7b  mov     [rbp+hKey], 0
0x180010c83  test    ebx, ebx
0x180010c85  jz      short loc_180010C95
0x180010c87  test    rdi, rdi
0x180010c8a  jz      short loc_180010C95
0x180010c8c  mov     rcx, rdi; pv
0x180010c8f  call    cs:__imp_CoTaskMemFree
0x180010c95  mov     eax, ebx
0x180010c97  mov     rcx, [rbp+var_8]
0x180010c9b  xor     rcx, rsp; StackCookie
0x180010c9e  call    __security_check_cookie
0x180010ca3  lea     r11, [rsp+50h+var_s0]
0x180010ca8  mov     rbx, [r11+38h]
0x180010cac  mov     rsi, [r11+40h]
0x180010cb0  mov     rsp, r11
0x180010cb3  pop     r15
0x180010cb5  pop     r14
0x180010cb7  pop     r13
0x180010cb9  pop     rdi
0x180010cba  pop     rbp
0x180010cbb  retn
0x180010cbc  mov     rcx, [rbp+hKey]; hKey
0x180010cc0  lea     rax, [rbp+cbData]
0x180010cc4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180010cc9  lea     r9, [rbp+Type]; lpType
0x180010ccd  xor     r8d, r8d; lpReserved
0x180010cd0  mov     [rsp+50h+phkResult], rdi; lpData
0x180010cd5  lea     rdx, aTargetos; "TargetOS"
0x180010cdc  mov     [rbp+cbData], r13d
0x180010ce0  call    cs:__imp_RegQueryValueExW
0x180010ce6  mov     ebx, eax
0x180010ce8  test    eax, eax
0x180010cea  jz      short loc_180010D00
0x180010cec  mov     dword ptr [rsp+50h+lpcbData], 349h
0x180010cf4  lea     r8, aFailedToReadTa; "failed to read target OS reg value"
0x180010cfb  jmp     loc_180010B46
0x180010d00  cmp     [rbp+Type], 1
0x180010d04  jnz     short loc_180010D85
0x180010d06  cmp     [rbp+cbData], 0
0x180010d0a  jz      short loc_180010D85
0x180010d0c  mov     rcx, rdi
0x180010d0f  call    winreAddTrailingBackslash
0x180010d14  mov     ebx, eax
0x180010d16  test    eax, eax
0x180010d18  jz      short loc_180010D27
0x180010d1a  mov     dword ptr [rsp+50h+lpcbData], 351h
0x180010d22  jmp     loc_180010BDD
0x180010d27  mov     r13d, 12Eh
0x180010d2d  lea     r8, aSystem32_0; "system32\\"
0x180010d34  mov     edx, r13d; unsigned __int64
0x180010d37  mov     rcx, rdi; unsigned __int16 *
0x180010d3a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010d3f  mov     ebx, eax
0x180010d41  test    eax, eax
0x180010d43  jns     short loc_180010D59
0x180010d45  mov     dword ptr [rsp+50h+lpcbData], 354h
0x180010d4d  lea     r8, aFailedToConcat_1; "failed to concatenate string system32"
0x180010d54  jmp     loc_180010C0E
0x180010d59  lea     r8, AppName; "Recovery"
0x180010d60  mov     rdx, r13; unsigned __int64
0x180010d63  mov     rcx, rdi; unsigned __int16 *
0x180010d66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010d6b  mov     ebx, eax
0x180010d6d  test    eax, eax
0x180010d6f  jns     short loc_180010DB8
0x180010d71  mov     dword ptr [rsp+50h+lpcbData], 357h
0x180010d79  lea     r8, aFaileToConcate; "faile to concatenate recovery root dire"...
0x180010d80  jmp     loc_180010C0E
0x180010d85  mov     ebx, 57h ; 'W'
0x180010d8a  jmp     loc_180010C6C
0x180010d8f  lea     rdx, [rbp+lpData]
0x180010d93  xor     ecx, ecx
0x180010d95  call    winreFindMainOsConfigDir
0x180010d9a  mov     ebx, eax
0x180010d9c  test    eax, eax
0x180010d9e  jz      short loc_180010DB4
0x180010da0  mov     dword ptr [rsp+50h+lpcbData], 35Fh
0x180010da8  lea     r8, aFailedToFindMa; "failed to find main os config directory"
0x180010daf  jmp     loc_180010AA9
0x180010db4  mov     rdi, [rbp+lpData]
0x180010db8  mov     rcx, rdi
0x180010dbb  call    winreAddTrailingBackslash
0x180010dc0  mov     ebx, eax
0x180010dc2  test    eax, eax
0x180010dc4  jz      short loc_180010E22
0x180010dc6  mov     dword ptr [rsp+50h+lpcbData], 375h
0x180010dce  jmp     loc_180010BDD
0x180010dd3  lea     rcx, [rbp+lpData]
0x180010dd7  call    winreAllocPath
0x180010ddc  mov     ebx, eax
0x180010dde  test    eax, eax
0x180010de0  jz      short loc_180010DEF
0x180010de2  mov     dword ptr [rsp+50h+lpcbData], 368h
0x180010dea  jmp     loc_180010AA2
0x180010def  mov     r9, rdi
0x180010df2  lea     rax, AppName; "Recovery"
0x180010df9  mov     rdi, [rbp+lpData]
0x180010dfd  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x180010e04  mov     rcx, rdi; unsigned __int16 *
0x180010e07  mov     [rsp+50h+phkResult], rax
0x180010e0c  mov     rdx, r13; unsigned __int64
0x180010e0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e14  test    eax, eax
0x180010e16  jns     short loc_180010DB8
0x180010e18  mov     ebx, 0C000000Dh
0x180010e1d  jmp     loc_180010C6C
0x180010e22  mov     r8, rsi; unsigned __int16 *
0x180010e25  mov     rdx, r13; unsigned __int64
0x180010e28  mov     rcx, rdi; unsigned __int16 *
0x180010e2b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010e30  mov     esi, eax
0x180010e32  test    eax, eax
0x180010e34  jns     loc_180010C69
0x180010e3a  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010e41  mov     dword ptr [rsp+50h+lpcbData], 379h
0x180010e49  mov     r9d, esi
0x180010e4c  mov     [rsp+50h+phkResult], rax
0x180010e51  lea     r8, aFailedToConcat_6; "failed to concatenate recovery file nam"...
0x180010e58  mov     ecx, 2
0x180010e5d  lea     rdx, aWinregetrecove_1; "winreGetRecoveryFilePath %s (0x%x) in f"...
0x180010e64  call    UnattendLogW
0x180010e69  movzx   ebx, si
0x180010e6c  jmp     loc_180010C6C
```
