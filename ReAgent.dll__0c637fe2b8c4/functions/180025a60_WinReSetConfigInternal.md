# WinReSetConfigInternal

- ea: `0x180025a60`
- end: `0x1800260b1`
- name: `WinReSetConfigInternal`
- size: `1617`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800259d0`
- `0x180041de4`

## callees

- `0x1800059fc`
- `0x180008b94`
- `0x18000edec`
- `0x18000ffcc`
- `0x180010010`
- `0x1800103f4`
- `0x1800109d0`
- `0x180011344`
- `0x180011974`
- `0x1800121b0`
- `0x180014754`
- `0x1800187e0`
- `0x18001defc`
- `0x18001df60`
- `0x18001e4c8`
- `0x180025a60`
- `0x180028e30`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180025ccb`
- `KERNEL32!SetLastError` at `0x180025ccb`
- `ole32!CoTaskMemFree` at `0x180025cad`
- `ole32!CoTaskMemFree` at `0x180025cbb`
- `ole32!CoTaskMemFree` at `0x180025cad`
- `ole32!CoTaskMemFree` at `0x180025cbb`

## string_xrefs

- `0x180025ba6`: `failed to get config file path`
- `0x180025c03`: `failed to init agent config`
- `0x180025b53`: `failed to allocate path`
- `0x180026096`: `ReAgent.xml`
- `0x180025b3c`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180025b8f`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180025bec`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180025d9d`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002608a`: `failed to update agent config`
- `0x180025b5d`: `WinReSetConfigInternal %s (0x%x) in file %S line %d`
- `0x180025bb0`: `WinReSetConfigInternal %s (0x%x) in file %S line %d`
- `0x180025c0d`: `WinReSetConfigInternal %s (0x%x) in file %S line %d`
- `0x180025da7`: `WinReSetConfigInternal %s (0x%x) in file %S line %d`
- `0x180025d96`: `failed to set image location path`
- `0x180025e1a`: `install.wim`
- `0x180025edd`: `install.wim`
- `0x180025e37`: `failed to convert install.wim path to offset`
- `0x180025ea0`: `failed to set os install location path`
- `0x180025f36`: `failed to set custom image location path`
- `0x180025ffa`: `failed to convert winre.wim path to offset`
- `0x180026064`: `failed to set downlevel winre location path`

## pseudocode

```c
_BOOL8 __fastcall WinReSetConfigInternal(__int64 a1, const WCHAR *a2)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // rsi
  DWORD ConfigFilePathFromWinDir; // edi
  __int64 v7; // r8
  DWORD v8; // eax
  const wchar_t *v10; // r8
  struct _GUID v11; // xmm0
  ReAgentXMLParser *v12; // rcx
  __int64 v13; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+60h] [rbp-A0h]
  struct _GUID v17; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v18; // [rsp+530h] [rbp+430h]
  LPVOID pv[2]; // [rsp+570h] [rbp+470h] BYREF
  _QWORD v20[3]; // [rsp+580h] [rbp+480h] BYREF
  int v21; // [rsp+598h] [rbp+498h]
  int v22; // [rsp+59Ch] [rbp+49Ch]
  __int128 v23; // [rsp+5A0h] [rbp+4A0h]
  __int128 v24; // [rsp+5B0h] [rbp+4B0h]
  ReAgentXMLParser *v25; // [rsp+5C0h] [rbp+4C0h]
  int v26; // [rsp+5C8h] [rbp+4C8h]

  v20[1] = 0;
  v20[2] = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v22 = 2;
  v25 = 0;
  v20[0] = &ReAgentConfig::`vftable';
  v26 = 0;
  v4 = 0;
  pv[0] = 0;
  v5 = 0;
  v14[0] = 0;
  memset_0(v15, 0, 0x530u);
  if ( !a1 || *(_QWORD *)a1 != 2448 )
  {
LABEL_18:
    ConfigFilePathFromWinDir = 87;
    goto LABEL_19;
  }
  PrivateFreePartitionList(0);
  ConfigFilePathFromWinDir = winreAllocPath(v14);
  if ( ConfigFilePathFromWinDir )
  {
    UnattendLogW(
      2,
      L"WinReSetConfigInternal %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      958);
    v5 = v14[0];
    goto LABEL_21;
  }
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a2, 1, v7, pv);
  if ( ConfigFilePathFromWinDir )
  {
    UnattendLogW(
      2,
      L"WinReSetConfigInternal %s (0x%x) in file %S line %d",
      L"failed to get config file path",
      ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      967);
    v4 = (unsigned __int16 *)pv[0];
LABEL_7:
    v5 = v14[0];
    goto LABEL_19;
  }
  v4 = (unsigned __int16 *)pv[0];
  ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v20, (unsigned __int16 *)pv[0], 1);
  if ( ConfigFilePathFromWinDir )
  {
    UnattendLogW(
      2,
      L"WinReSetConfigInternal %s (0x%x) in file %S line %d",
      L"failed to init agent config",
      ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      970);
    goto LABEL_7;
  }
  v5 = v14[0];
  if ( *(_WORD *)(a1 + 8) )
  {
    if ( *((_DWORD *)ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v20) + 1397) )
    {
      if ( !ReAgentError )
        ReAgentError = 15;
      ConfigFilePathFromWinDir = 183;
      goto LABEL_19;
    }
    LODWORD(v14[0]) = 0;
    v8 = winreConvertDirNameToOffset((LPCWSTR)(a1 + 8), (__int64)L"Winre.wim", v15, v14, (__int64)v5);
    ConfigFilePathFromWinDir = v8;
    if ( LODWORD(v14[0]) )
    {
      if ( !ReAgentError )
        ReAgentError = 31;
      goto LABEL_18;
    }
    if ( v8 == 3 )
    {
      if ( !ReAgentError )
        ReAgentError = 13;
      goto LABEL_19;
    }
    if ( !(unsigned int)winreDoesFileExist((unsigned __int16 *)(a1 + 8), L"Winre.wim") )
    {
      ConfigFilePathFromWinDir = 2;
      if ( !ReAgentError )
        ReAgentError = 29;
      goto LABEL_19;
    }
    ConfigFilePathFromWinDir = ReAgentConfig::SetImageLocationPath((ReAgentConfig *)v20, v18, &v17, v16, v5);
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(v13) = 1028;
      v10 = L"failed to set image location path";
LABEL_32:
      UnattendLogW(
        2,
        L"WinReSetConfigInternal %s (0x%x) in file %S line %d",
        v10,
        ConfigFilePathFromWinDir,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v13);
      goto LABEL_19;
    }
    *((_DWORD *)v25 + 1556) = *(_DWORD *)(a1 + 1828);
  }
  if ( *(_WORD *)(a1 + 612) )
  {
    if ( (unsigned int)WinReIsWimBootEnabledInternal(a2) )
    {
LABEL_36:
      ReAgentError = 37;
      ConfigFilePathFromWinDir = 5;
      goto LABEL_19;
    }
    LODWORD(v14[0]) = 0;
    ConfigFilePathFromWinDir = winreConvertDirNameToOffset(
                                 (LPCWSTR)(a1 + 612),
                                 (__int64)L"install.wim",
                                 v15,
                                 v14,
                                 (__int64)v5);
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(v13) = 1055;
LABEL_39:
      v10 = L"failed to convert install.wim path to offset";
      goto LABEL_32;
    }
    if ( LODWORD(v14[0]) )
    {
      if ( !ReAgentError )
        ReAgentError = 30;
      goto LABEL_18;
    }
    ConfigFilePathFromWinDir = ReAgentConfig::SetOsInstallLocationPath(
                                 (ReAgentConfig *)v20,
                                 v18,
                                 &v17,
                                 v16,
                                 v5,
                                 *(_DWORD *)(a1 + 1832));
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(v13) = 1070;
      v10 = L"failed to set os install location path";
      goto LABEL_32;
    }
  }
  if ( !*(_WORD *)(a1 + 1216) )
    goto LABEL_70;
  if ( (unsigned int)WinReIsWimBootEnabledInternal(a2) )
    goto LABEL_36;
  ConfigFilePathFromWinDir = winreConvertDirNameToOffset(
                               (LPCWSTR)(a1 + 1216),
                               (__int64)L"install.wim",
                               v15,
                               0,
                               (__int64)v5);
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v13) = 1093;
    goto LABEL_39;
  }
  ConfigFilePathFromWinDir = ReAgentConfig::SetCustomImageLocationPath(
                               (ReAgentConfig *)v20,
                               v18,
                               &v17,
                               v16,
                               v5,
                               *(_DWORD *)(a1 + 1836));
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v13) = 1099;
LABEL_51:
    v10 = L"failed to set custom image location path";
    goto LABEL_32;
  }
  if ( !*(_WORD *)(a1 + 1216) )
  {
LABEL_70:
    if ( !*(_DWORD *)(a1 + 1836) )
    {
      ConfigFilePathFromWinDir = ReAgentConfig::SetCustomImageLocationPath(
                                   (ReAgentConfig *)v20,
                                   0,
                                   &ZeroGuid,
                                   0,
                                   (unsigned __int16 *)&Default,
                                   0);
      if ( ConfigFilePathFromWinDir )
      {
        LODWORD(v13) = 1104;
        goto LABEL_51;
      }
    }
  }
  if ( *(_DWORD *)(a1 + 1820) )
    *((_DWORD *)v25 + 1400) = *(_DWORD *)(a1 + 1824);
  if ( *((_DWORD *)v25 + 1397) )
    *((_DWORD *)v25 + 1557) = *(_DWORD *)(a1 + 1840);
  if ( *(_WORD *)(a1 + 1844) )
  {
    ConfigFilePathFromWinDir = winreConvertDirNameToOffset(
                                 (LPCWSTR)(a1 + 1844),
                                 (__int64)L"winre.wim",
                                 v15,
                                 0,
                                 (__int64)v5);
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(v13) = 1122;
      v10 = L"failed to convert winre.wim path to offset";
      goto LABEL_32;
    }
    v11 = v17;
    *((_QWORD *)v25 + 933) = v18;
    v12 = v25;
    *((_DWORD *)v25 + 1860) = v16;
    *(struct _GUID *)((char *)v25 + 7444) = v11;
    ConfigFilePathFromWinDir = ReAgentXMLParser::CopyPathInfo(v12, v5, (unsigned __int16 *)v25 + 3418);
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(v13) = 1127;
      v10 = L"failed to set downlevel winre location path";
      goto LABEL_32;
    }
  }
  ConfigFilePathFromWinDir = ReAgentXMLParser::Update((ReAgentXMLParser *)v20);
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v13) = 1138;
    v10 = L"failed to update agent config";
    goto LABEL_32;
  }
  winreBackupRecoveryFile(v4, (ReAgentXMLParser *)v20, L"ReAgent.xml");
LABEL_19:
  if ( v4 )
    CoTaskMemFree(v4);
LABEL_21:
  if ( v5 )
    CoTaskMemFree(v5);
  SetLastError(ConfigFilePathFromWinDir);
  v20[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v20);
  return ConfigFilePathFromWinDir == 0;
}

```

## disassembly

```asm
0x180025a60  mov     [rsp-8+arg_10], rbx
0x180025a65  push    rbp
0x180025a66  push    rsi
0x180025a67  push    rdi
0x180025a68  push    r12
0x180025a6a  push    r13
0x180025a6c  push    r14
0x180025a6e  push    r15
0x180025a70  lea     rbp, [rsp-4E0h]
0x180025a78  sub     rsp, 5E0h
0x180025a7f  mov     rax, cs:__security_cookie
0x180025a86  xor     rax, rsp
0x180025a89  mov     [rbp+510h+var_40], rax
0x180025a90  xor     r13d, r13d
0x180025a93  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180025a9a  mov     r12, rdx
0x180025a9d  mov     [rbp+510h+var_88], r13
0x180025aa4  mov     rbx, rcx
0x180025aa7  mov     [rbp+510h+var_80], r13
0x180025aae  xorps   xmm0, xmm0
0x180025ab1  mov     [rbp+510h+var_78], r13d
0x180025ab8  xorps   xmm1, xmm1
0x180025abb  movdqa  [rbp+510h+var_70], xmm0
0x180025ac3  lea     r14d, [r13+2]
0x180025ac7  movdqa  [rbp+510h+var_60], xmm1
0x180025acf  xor     edx, edx; Val
0x180025ad1  mov     [rbp+510h+var_74], r14d
0x180025ad8  mov     r8d, 530h; Size
0x180025ade  mov     [rbp+510h+var_50], r13
0x180025ae5  lea     rcx, [rsp+610h+var_5D0]; void *
0x180025aea  mov     [rbp+510h+var_90], rax
0x180025af1  mov     [rbp+510h+var_48], r13d
0x180025af8  mov     r15d, r13d
0x180025afb  mov     [rbp+510h+pv], r13
0x180025b02  mov     esi, r13d
0x180025b05  mov     [rsp+610h+var_5E0], r13
0x180025b0a  call    memset_0
0x180025b0f  test    rbx, rbx
0x180025b12  jz      loc_180025CA0
0x180025b18  cmp     qword ptr [rbx], 990h
0x180025b1f  jnz     loc_180025CA0
0x180025b25  xor     ecx, ecx; pv
0x180025b27  call    PrivateFreePartitionList
0x180025b2c  lea     rcx, [rsp+610h+var_5E0]
0x180025b31  call    winreAllocPath
0x180025b36  mov     edi, eax
0x180025b38  test    eax, eax
0x180025b3a  jz      short loc_180025B73
0x180025b3c  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025b43  mov     dword ptr [rsp+610h+var_5E8], 3BEh
0x180025b4b  mov     r9d, edi
0x180025b4e  mov     [rsp+610h+var_5F0], rax
0x180025b53  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180025b5a  mov     ecx, r14d
0x180025b5d  lea     rdx, aWinresetconfig_0; "WinReSetConfigInternal %s (0x%x) in fil"...
0x180025b64  call    UnattendLogW
0x180025b69  mov     rsi, [rsp+610h+var_5E0]
0x180025b6e  jmp     loc_180025CB3
0x180025b73  mov     esi, 1
0x180025b78  lea     r9, [rbp+510h+pv]
0x180025b7f  mov     edx, esi
0x180025b81  mov     rcx, r12
0x180025b84  call    winreGetConfigFilePathFromWinDir
0x180025b89  mov     edi, eax
0x180025b8b  test    eax, eax
0x180025b8d  jz      short loc_180025BCD
0x180025b8f  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025b96  mov     dword ptr [rsp+610h+var_5E8], 3C7h
0x180025b9e  mov     r9d, edi
0x180025ba1  mov     [rsp+610h+var_5F0], rax
0x180025ba6  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x180025bad  mov     ecx, r14d
0x180025bb0  lea     rdx, aWinresetconfig_0; "WinReSetConfigInternal %s (0x%x) in fil"...
0x180025bb7  call    UnattendLogW
0x180025bbc  mov     r15, [rbp+510h+pv]
0x180025bc3  mov     rsi, [rsp+610h+var_5E0]
0x180025bc8  jmp     loc_180025CA5
0x180025bcd  mov     r15, [rbp+510h+pv]
0x180025bd4  lea     rcx, [rbp+510h+var_90]; this
0x180025bdb  mov     rdx, r15; unsigned __int16 *
0x180025bde  mov     r8d, esi; int
0x180025be1  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180025be6  mov     edi, eax
0x180025be8  test    eax, eax
0x180025bea  jz      short loc_180025C1B
0x180025bec  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025bf3  mov     dword ptr [rsp+610h+var_5E8], 3CAh
0x180025bfb  mov     r9d, edi
0x180025bfe  mov     [rsp+610h+var_5F0], rax
0x180025c03  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x180025c0a  mov     ecx, r14d
0x180025c0d  lea     rdx, aWinresetconfig_0; "WinReSetConfigInternal %s (0x%x) in fil"...
0x180025c14  call    UnattendLogW
0x180025c19  jmp     short loc_180025BC3
0x180025c1b  mov     rsi, [rsp+610h+var_5E0]
0x180025c20  lea     r14, [rbx+8]
0x180025c24  cmp     [r14], r13w
0x180025c28  jz      loc_180025DD5
0x180025c2e  lea     rcx, [rbp+510h+var_90]; this
0x180025c35  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180025c3a  cmp     [rax+15D4h], r13d
0x180025c41  jz      short loc_180025C5D
0x180025c43  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x180025c4a  jnz     short loc_180025C56
0x180025c4c  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0Fh; _ReAgentErrorCodes ReAgentError
0x180025c56  mov     edi, 0B7h
0x180025c5b  jmp     short loc_180025CA5
0x180025c5d  lea     r9, [rsp+610h+var_5E0]
0x180025c62  mov     dword ptr [rsp+610h+var_5E0], r13d
0x180025c67  lea     r8, [rsp+610h+var_5D0]
0x180025c6c  mov     [rsp+610h+var_5F0], rsi; __int64
0x180025c71  lea     rdx, aWinreWim; "Winre.wim"
0x180025c78  mov     rcx, r14; lpszFileName
0x180025c7b  call    winreConvertDirNameToOffset
0x180025c80  mov     edi, eax
0x180025c82  cmp     dword ptr [rsp+610h+var_5E0], r13d
0x180025c87  jz      loc_180025D17
0x180025c8d  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x180025c94  jnz     short loc_180025CA0
0x180025c96  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Fh; _ReAgentErrorCodes ReAgentError
0x180025ca0  mov     edi, 57h ; 'W'
0x180025ca5  test    r15, r15
0x180025ca8  jz      short loc_180025CB3
0x180025caa  mov     rcx, r15; pv
0x180025cad  call    cs:__imp_CoTaskMemFree
0x180025cb3  test    rsi, rsi
0x180025cb6  jz      short loc_180025CC1
0x180025cb8  mov     rcx, rsi; pv
0x180025cbb  call    cs:__imp_CoTaskMemFree
0x180025cc1  test    edi, edi
0x180025cc3  mov     ebx, r13d
0x180025cc6  mov     ecx, edi; dwErrCode
0x180025cc8  setz    bl
0x180025ccb  call    cs:__imp_SetLastError
0x180025cd1  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180025cd8  lea     rcx, [rbp+510h+var_90]; this
0x180025cdf  mov     [rbp+510h+var_90], rax
0x180025ce6  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x180025ceb  mov     eax, ebx
0x180025ced  mov     rcx, [rbp+510h+var_40]
0x180025cf4  xor     rcx, rsp; StackCookie
0x180025cf7  call    __security_check_cookie
0x180025cfc  mov     rbx, [rsp+610h+arg_10]
0x180025d04  add     rsp, 5E0h
0x180025d0b  pop     r15
0x180025d0d  pop     r14
0x180025d0f  pop     r13
0x180025d11  pop     r12
0x180025d13  pop     rdi
0x180025d14  pop     rsi
0x180025d15  pop     rbp
0x180025d16  retn
0x180025d17  cmp     eax, 3
0x180025d1a  jnz     short loc_180025D34
0x180025d1c  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x180025d23  jnz     short loc_180025CA5
0x180025d25  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0Dh; _ReAgentErrorCodes ReAgentError
0x180025d2f  jmp     loc_180025CA5
0x180025d34  lea     rdx, aWinreWim; "Winre.wim"
0x180025d3b  mov     rcx, r14; unsigned __int16 *
0x180025d3e  call    winreDoesFileExist
0x180025d43  test    eax, eax
0x180025d45  jnz     short loc_180025D66
0x180025d47  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x180025d4e  lea     edi, [rax+2]
0x180025d51  jnz     loc_180025CA5
0x180025d57  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Dh; _ReAgentErrorCodes ReAgentError
0x180025d61  jmp     loc_180025CA5
0x180025d66  mov     r9d, [rsp+610h+var_5B0]; unsigned int
0x180025d6b  lea     r8, [rsp+610h+var_5AC]; struct _GUID *
0x180025d70  mov     rdx, [rbp+510h+var_E0]; unsigned __int64
0x180025d77  lea     rcx, [rbp+510h+var_90]; this
0x180025d7e  mov     [rsp+610h+var_5F0], rsi; unsigned __int16 *
0x180025d83  call    ?SetImageLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetImageLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x180025d88  mov     edi, eax
0x180025d8a  test    eax, eax
0x180025d8c  jz      short loc_180025DC2
0x180025d8e  mov     dword ptr [rsp+610h+var_5E8], 404h
0x180025d96  lea     r8, aFailedToSetIma; "failed to set image location path"
0x180025d9d  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025da4  mov     r9d, edi
0x180025da7  lea     rdx, aWinresetconfig_0; "WinReSetConfigInternal %s (0x%x) in fil"...
0x180025dae  mov     [rsp+610h+var_5F0], rax
0x180025db3  mov     ecx, 2
0x180025db8  call    UnattendLogW
0x180025dbd  jmp     loc_180025CA5
0x180025dc2  mov     rax, [rbp+510h+var_50]
0x180025dc9  mov     ecx, [rbx+724h]
0x180025dcf  mov     [rax+1850h], ecx
0x180025dd5  lea     rdi, [rbx+264h]
0x180025ddc  cmp     [rdi], r13w
0x180025de0  jz      loc_180025EAC
0x180025de6  mov     rcx, r12; lpFileName
0x180025de9  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x180025dee  test    eax, eax
0x180025df0  jz      short loc_180025E06
0x180025df2  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 25h ; '%'; _ReAgentErrorCodes ReAgentError
0x180025dfc  mov     edi, 5
0x180025e01  jmp     loc_180025CA5
0x180025e06  lea     r9, [rsp+610h+var_5E0]
0x180025e0b  mov     dword ptr [rsp+610h+var_5E0], r13d
0x180025e10  lea     r8, [rsp+610h+var_5D0]
0x180025e15  mov     [rsp+610h+var_5F0], rsi; __int64
0x180025e1a  lea     rdx, aInstallWim; "install.wim"
0x180025e21  mov     rcx, rdi; lpszFileName
0x180025e24  call    winreConvertDirNameToOffset
0x180025e29  mov     edi, eax
0x180025e2b  test    eax, eax
0x180025e2d  jz      short loc_180025E43
0x180025e2f  mov     dword ptr [rsp+610h+var_5E8], 41Fh
0x180025e37  lea     r8, aFailedToConver_8; "failed to convert install.wim path to o"...
0x180025e3e  jmp     loc_180025D9D
0x180025e43  cmp     dword ptr [rsp+610h+var_5E0], r13d
0x180025e48  jz      short loc_180025E66
0x180025e4a  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x180025e51  jnz     loc_180025CA0
0x180025e57  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Eh; _ReAgentErrorCodes ReAgentError
0x180025e61  jmp     loc_180025CA0
0x180025e66  mov     eax, [rbx+728h]
0x180025e6c  lea     r8, [rsp+610h+var_5AC]; struct _GUID *
0x180025e71  mov     r9d, [rsp+610h+var_5B0]; unsigned int
0x180025e76  lea     rcx, [rbp+510h+var_90]; this
0x180025e7d  mov     rdx, [rbp+510h+var_E0]; unsigned __int64
0x180025e84  mov     dword ptr [rsp+610h+var_5E8], eax; int
0x180025e88  mov     [rsp+610h+var_5F0], rsi; unsigned __int16 *
0x180025e8d  call    ?SetOsInstallLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAGH@Z; ReAgentConfig::SetOsInstallLocationPath(unsigned __int64,_GUID *,ulong,ushort *,int)
0x180025e92  mov     edi, eax
0x180025e94  test    eax, eax
0x180025e96  jz      short loc_180025EAC
0x180025e98  mov     dword ptr [rsp+610h+var_5E8], 42Eh
0x180025ea0  lea     r8, aFailedToSetOsI; "failed to set os install location path"
0x180025ea7  jmp     loc_180025D9D
0x180025eac  lea     r14, [rbx+4C0h]
0x180025eb3  cmp     [r14], r13w
0x180025eb7  jz      loc_180025F48
0x180025ebd  mov     rcx, r12; lpFileName
0x180025ec0  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x180025ec5  test    eax, eax
0x180025ec7  jnz     loc_180025DF2
0x180025ecd  xor     r9d, r9d
0x180025ed0  mov     [rsp+610h+var_5F0], rsi; __int64
0x180025ed5  lea     r8, [rsp+610h+var_5D0]
0x180025eda  mov     rcx, r14; lpszFileName
0x180025edd  lea     rdx, aInstallWim; "install.wim"
0x180025ee4  call    winreConvertDirNameToOffset
0x180025ee9  mov     edi, eax
0x180025eeb  test    eax, eax
0x180025eed  jz      short loc_180025EFC
0x180025eef  mov     dword ptr [rsp+610h+var_5E8], 445h
0x180025ef7  jmp     loc_180025E37
0x180025efc  mov     eax, [rbx+72Ch]
0x180025f02  lea     r8, [rsp+610h+var_5AC]; struct _GUID *
0x180025f07  mov     r9d, [rsp+610h+var_5B0]; unsigned int
0x180025f0c  lea     rcx, [rbp+510h+var_90]; this
0x180025f13  mov     rdx, [rbp+510h+var_E0]; unsigned __int64
0x180025f1a  mov     dword ptr [rsp+610h+var_5E8], eax; int
0x180025f1e  mov     [rsp+610h+var_5F0], rsi; unsigned __int16 *
0x180025f23  call    ?SetCustomImageLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAGH@Z; ReAgentConfig::SetCustomImageLocationPath(unsigned __int64,_GUID *,ulong,ushort *,int)
0x180025f28  mov     edi, eax
0x180025f2a  test    eax, eax
0x180025f2c  jz      short loc_180025F42
0x180025f2e  mov     dword ptr [rsp+610h+var_5E8], 44Bh
0x180025f36  lea     r8, aFailedToSetCus; "failed to set custom image location pat"...
0x180025f3d  jmp     loc_180025D9D
0x180025f42  cmp     [r14], r13w
0x180025f46  jnz     short loc_180025F8A
0x180025f48  cmp     [rbx+72Ch], r13d
0x180025f4f  jnz     short loc_180025F8A
0x180025f51  lea     rax, Default
0x180025f58  mov     dword ptr [rsp+610h+var_5E8], r13d; int
0x180025f5d  xor     r9d, r9d; unsigned int
0x180025f60  mov     [rsp+610h+var_5F0], rax; unsigned __int16 *
0x180025f65  lea     r8, ZeroGuid; struct _GUID *
0x180025f6c  xor     edx, edx; unsigned __int64
0x180025f6e  lea     rcx, [rbp+510h+var_90]; this
0x180025f75  call    ?SetCustomImageLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAGH@Z; ReAgentConfig::SetCustomImageLocationPath(unsigned __int64,_GUID *,ulong,ushort *,int)
0x180025f7a  mov     edi, eax
0x180025f7c  test    eax, eax
0x180025f7e  jz      short loc_180025F8A
0x180025f80  mov     dword ptr [rsp+610h+var_5E8], 450h
0x180025f88  jmp     short loc_180025F36
0x180025f8a  cmp     [rbx+71Ch], r13d
0x180025f91  jz      short loc_180025FA6
0x180025f93  mov     rax, [rbp+510h+var_50]
0x180025f9a  mov     ecx, [rbx+720h]
0x180025fa0  mov     [rax+15E0h], ecx
0x180025fa6  mov     rcx, [rbp+510h+var_50]
0x180025fad  cmp     [rcx+15D4h], r13d
0x180025fb4  jz      short loc_180025FC2
0x180025fb6  mov     eax, [rbx+730h]
0x180025fbc  mov     [rcx+1854h], eax
0x180025fc2  lea     rcx, [rbx+734h]; lpszFileName
0x180025fc9  cmp     [rcx], r13w
0x180025fcd  jz      loc_180026070
0x180025fd3  xor     r9d, r9d
0x180025fd6  mov     [rsp+610h+var_5F0], rsi; __int64
0x180025fdb  lea     r8, [rsp+610h+var_5D0]
0x180025fe0  lea     rdx, aWinreWim_1; "winre.wim"
0x180025fe7  call    winreConvertDirNameToOffset
0x180025fec  mov     edi, eax
  ... truncated ...
```
