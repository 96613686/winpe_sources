# WinReSetSettings

- ea: `0x180027cc0`
- end: `0x1800281af`
- name: `WinReSetSettings`
- size: `1263`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000196c`
- `0x180001adc`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x1800124e0`
- `0x18001c5e0`
- `0x18001f6fc`
- `0x180027cc0`
- `0x18003e4dc`
- `0x18003e588`
- `0x18003e5cc`
- `0x18003e784`
- `0x18003e864`
- `0x18003eb38`
- `0x18003ebc4`
- `0x180047024`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180027d85`
- `KERNEL32!GetLastError` at `0x180027d85`
- `KERNEL32!SetLastError` at `0x18002817d`
- `KERNEL32!SetLastError` at `0x18002817d`
- `KERNEL32!GetFileAttributesW` at `0x180027d7a`
- `KERNEL32!GetFileAttributesW` at `0x180027d7a`

## string_xrefs

- `0x180027de0`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180027e29`: `Failed to create settings object. Error: 0x%x`
- `0x180027d4d`: `Parameters: xml file: %s`
- `0x180027d60`: `Invalid parameter. xml file path is null`
- `0x180027daf`: `Invalid file path. %s is a directory`
- `0x180027df7`: `Failed to initialize xml parser`

## pseudocode

```c
__int64 __fastcall WinReSetSettings(unsigned __int16 *a1)
{
  unsigned int v1; // r13d
  struct SrSettings::ISrSettings *v2; // r14
  __int64 LastError; // rbx
  DWORD FileAttributesW; // eax
  struct SrSettings::ISrSettings **v6; // rdx
  __int64 v7; // rsi
  int SrSettings; // eax
  unsigned __int16 v9; // r14
  int v10; // r15d
  const unsigned __int16 *v11; // r15
  const unsigned __int16 *v12; // r8
  int v13; // r12d
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // r8
  int v18; // eax
  int v19; // r15d
  int v20; // esi
  struct SrSettings::ISrSettings *v22; // [rsp+30h] [rbp-59h] BYREF
  void **v23; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-49h] BYREF
  int v25; // [rsp+58h] [rbp-31h]
  __int128 v26; // [rsp+60h] [rbp-29h]
  __int128 v27; // [rsp+70h] [rbp-19h]
  __int128 v28; // [rsp+80h] [rbp-9h]

  v1 = 0;
  v23 = &ReAgentLogcallback::`vftable';
  v24[1] = 0;
  v24[0] = &SettingXmlParser::`vftable';
  v2 = 0;
  v24[2] = 0;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  TraceLoggingRegisterEx_EventRegister_2U();
  AsmWinREWinReSetSettingsStart();
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetSettings");
  UnattendLogW(0, L"Parameters: xml file: %s", a1);
  if ( !a1 )
  {
    LODWORD(LastError) = 87;
    UnattendLogW(1, L"Invalid parameter. xml file path is null");
    goto LABEL_56;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    UnattendLogW(1, L"Failed to get file attributes. Error: 0x%x", LastError);
    goto LABEL_56;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    LODWORD(LastError) = 87;
    UnattendLogW(1, L"Invalid file path. %s is a directory", a1);
    goto LABEL_56;
  }
  LODWORD(LastError) = SettingXmlParser::Init((SettingXmlParser *)v24, a1, 1);
  if ( (_DWORD)LastError )
  {
    UnattendLogW(
      2,
      L"WinReSetSettings %s (0x%x) in file %S line %d",
      L"Failed to initialize xml parser",
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      8573);
    goto LABEL_56;
  }
  v7 = v28;
  SrSettings = SrSettings::CreateSrSettings((SrSettings *)&v22, v6);
  v9 = SrSettings;
  if ( SrSettings < 0 )
  {
    UnattendLogW(1, L"Failed to create settings object. Error: 0x%x", (unsigned int)SrSettings);
    LODWORD(LastError) = v9;
    v2 = v22;
    goto LABEL_56;
  }
  v2 = v22;
  v10 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, void ***, _QWORD, _QWORD))(*(_QWORD *)v22 + 8LL))(
          v22,
          &v23,
          0,
          0);
  if ( v10 < 0 )
  {
    UnattendLogW(1, L"Failed to initialize settings object. Error: 0x%x", (unsigned int)v10);
LABEL_13:
    LODWORD(LastError) = (unsigned __int16)v10;
    goto LABEL_56;
  }
  AsmWinREClearRecoverySettings(L"All");
  v10 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *))(*(_QWORD *)v2 + 88LL))(v2);
  if ( v10 < 0 )
  {
    UnattendLogW(1, L"Failed to clear existing settings. Error: 0x%x", (unsigned int)v10);
    goto LABEL_13;
  }
  if ( (*(_BYTE *)(v7 + 1228) & 1) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, __int64, __int64, _QWORD))(*(_QWORD *)v2 + 120LL))(
            v2,
            v7,
            v7 + 604,
            0);
    if ( v10 < 0 )
    {
      UnattendLogW(1, L"Failed to store wifi credential. Error: 0x%x", (unsigned int)v10);
      goto LABEL_13;
    }
    AsmWinRESetRecoverySettings(L"WiFiCredential", &cchOriginalDestLength, 0);
  }
  v11 = L"on";
  if ( (*(_BYTE *)(v7 + 1228) & 0x20) != 0 )
  {
    v12 = L"on";
    if ( !*(_DWORD *)(v7 + 1220) )
      v12 = L"off";
    v13 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v2 + 56LL))(
            v2,
            L"CloudRemediation",
            v12,
            0);
    if ( v13 < 0 )
    {
      UnattendLogW(1, L"Failed to set cloud remediation setting. Error: 0x%x", (unsigned int)v13);
LABEL_25:
      LODWORD(LastError) = (unsigned __int16)v13;
      goto LABEL_56;
    }
    v14 = L"on";
    if ( !*(_DWORD *)(v7 + 1220) )
      v14 = L"off";
    AsmWinRESetRecoverySettings(L"CloudRemediation", v14, 0);
  }
  if ( (*(_BYTE *)(v7 + 1228) & 2) != 0 )
  {
    v15 = L"on";
    if ( !*(_DWORD *)(v7 + 1216) )
      v15 = L"off";
    v13 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v2 + 56LL))(
            v2,
            L"AutoRemediation",
            v15,
            0);
    if ( v13 < 0 )
    {
      UnattendLogW(1, L"Failed to set auto remediation setting. Error: 0x%x", (unsigned int)v13);
      goto LABEL_25;
    }
    v16 = L"on";
    if ( !*(_DWORD *)(v7 + 1216) )
      v16 = L"off";
    AsmWinRESetRecoverySettings(L"AutoRemediation", v16, 0);
  }
  if ( (*(_BYTE *)(v7 + 1228) & 4) != 0 )
  {
    v17 = L"on";
    if ( !*(_DWORD *)(v7 + 1224) )
      v17 = L"off";
    v13 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v2 + 56LL))(
            v2,
            L"HeadlessMode",
            v17,
            0);
    if ( v13 < 0 )
    {
      UnattendLogW(1, L"Failed to set headless setting. Error: 0x%x", (unsigned int)v13);
      goto LABEL_25;
    }
    if ( !*(_DWORD *)(v7 + 1224) )
      v11 = L"off";
    AsmWinRESetRecoverySettings(L"HeadlessMode", v11, 0);
  }
  if ( (*(_BYTE *)(v7 + 1228) & 8) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v2 + 48LL))(
            v2,
            L"TotalWaitTime",
            *(unsigned int *)(v7 + 1208),
            0);
    if ( v10 < 0 )
    {
      UnattendLogW(1, L"Failed to set total timeout. Error: 0x%x", (unsigned int)v10);
      goto LABEL_13;
    }
    AsmWinRESetRecoverySettings(L"TotalWaitTime", *(_DWORD *)(v7 + 1208), 0);
  }
  if ( (*(_BYTE *)(v7 + 1228) & 0x10) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v2 + 48LL))(
            v2,
            L"WaitInterval",
            *(unsigned int *)(v7 + 1212),
            0);
    if ( v10 < 0 )
    {
      UnattendLogW(1, L"Failed to set wait interval. Error: 0x%x", (unsigned int)v10);
      goto LABEL_13;
    }
    AsmWinRESetRecoverySettings(L"WaitInterval", *(_DWORD *)(v7 + 1212), 0);
  }
  UnattendLogW(0, L"Backup setting file");
  AsmWinREBackupSettingFileStart();
  v18 = winreBackupSetting(v2);
  v19 = (unsigned __int16)v18;
  v20 = v18;
  AsmWinREBackupSettingFileEnd(&cchOriginalDestLength, v18 >= 0, (unsigned __int16)v18);
  if ( v20 >= 0 )
  {
    v1 = 1;
  }
  else
  {
    UnattendLogW(1, L"Failed to backup setting file. Error: 0x%x", (unsigned int)v20);
    LODWORD(LastError) = v19;
  }
LABEL_56:
  if ( v2 )
    (*(void (__fastcall **)(struct SrSettings::ISrSettings *))(*(_QWORD *)v2 + 168LL))(v2);
  AsmWinREWinReSetSettingsEnd(v1, LastError);
  TraceLoggingUnregister_EventUnregister();
  UnattendLogW(0, L"Exit WinReSetSettings return value: %d, last error: 0x%x", v1, (unsigned int)LastError);
  UnattendFinalizeLog();
  SetLastError(LastError);
  SettingXmlParser::~SettingXmlParser((SettingXmlParser *)v24);
  return v1;
}

```

## disassembly

```asm
0x180027cc0  push    rbp
0x180027cc2  push    rbx
0x180027cc3  push    rsi
0x180027cc4  push    rdi
0x180027cc5  push    r12
0x180027cc7  push    r13
0x180027cc9  push    r14
0x180027ccb  push    r15
0x180027ccd  lea     rbp, [rsp-1Fh]
0x180027cd2  sub     rsp, 0A8h
0x180027cd9  mov     rax, cs:__security_cookie
0x180027ce0  xor     rax, rsp
0x180027ce3  mov     [rbp+57h+var_50], rax
0x180027ce7  xor     r13d, r13d
0x180027cea  lea     rax, ??_7ReAgentLogcallback@@6B@; const ReAgentLogcallback::`vftable'
0x180027cf1  xorps   xmm0, xmm0
0x180027cf4  mov     [rbp+57h+var_A8], rax
0x180027cf8  lea     rax, ??_7SettingXmlParser@@6B@; const SettingXmlParser::`vftable'
0x180027cff  mov     [rbp+57h+var_98], r13
0x180027d03  xorps   xmm1, xmm1
0x180027d06  mov     [rbp+57h+var_A0], rax
0x180027d0a  xor     r14d, r14d
0x180027d0d  mov     [rbp+57h+var_90], r13
0x180027d11  mov     rsi, rcx
0x180027d14  mov     [rbp+57h+var_B0], r14
0x180027d18  mov     [rbp+57h+var_88], r13d
0x180027d1c  movdqa  [rbp+57h+var_80], xmm0
0x180027d21  movdqa  [rbp+57h+var_70], xmm1
0x180027d26  movdqa  [rbp+57h+var_60], xmm0
0x180027d2b  call    TraceLoggingRegisterEx_EventRegister_2U
0x180027d30  call    ?AsmWinREWinReSetSettingsStart@@YAXXZ; AsmWinREWinReSetSettingsStart(void)
0x180027d35  xor     ecx, ecx
0x180027d37  call    UnattendInitializeLogEx2
0x180027d3c  lea     rdx, aEnterWinresets_0; "Enter WinReSetSettings"
0x180027d43  xor     ecx, ecx
0x180027d45  call    UnattendLogW
0x180027d4a  mov     r8, rsi
0x180027d4d  lea     rdx, aParametersXmlF; "Parameters: xml file: %s"
0x180027d54  xor     ecx, ecx
0x180027d56  call    UnattendLogW
0x180027d5b  test    rsi, rsi
0x180027d5e  jnz     short loc_180027D77
0x180027d60  lea     rdx, aInvalidParamet_4; "Invalid parameter. xml file path is nul"...
0x180027d67  lea     ecx, [rsi+1]
0x180027d6a  lea     ebx, [rsi+57h]
0x180027d6d  call    UnattendLogW
0x180027d72  jmp     loc_18002813C
0x180027d77  mov     rcx, rsi; lpFileName
0x180027d7a  call    cs:__imp_GetFileAttributesW
0x180027d80  cmp     eax, 0FFFFFFFFh
0x180027d83  jnz     short loc_180027DA6
0x180027d85  call    cs:__imp_GetLastError
0x180027d8b  lea     rdx, aFailedToGetFil_0; "Failed to get file attributes. Error: 0"...
0x180027d92  mov     ecx, 1
0x180027d97  mov     r8d, eax
0x180027d9a  mov     ebx, eax
0x180027d9c  call    UnattendLogW
0x180027da1  jmp     loc_18002813C
0x180027da6  test    al, 10h
0x180027da8  jz      short loc_180027DC6
0x180027daa  mov     ebx, 57h ; 'W'
0x180027daf  lea     rdx, aInvalidFilePat; "Invalid file path. %s is a directory"
0x180027db6  mov     r8, rsi
0x180027db9  lea     ecx, [rbx-56h]
0x180027dbc  call    UnattendLogW
0x180027dc1  jmp     loc_18002813C
0x180027dc6  mov     edi, 1
0x180027dcb  lea     rcx, [rbp+57h+var_A0]; this
0x180027dcf  mov     r8d, edi; int
0x180027dd2  mov     rdx, rsi; unsigned __int16 *
0x180027dd5  call    ?Init@SettingXmlParser@@UEAAKPEBGH@Z; SettingXmlParser::Init(ushort const *,int)
0x180027dda  mov     ebx, eax
0x180027ddc  test    eax, eax
0x180027dde  jz      short loc_180027E12
0x180027de0  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180027de7  mov     [rsp+0E0h+var_B8], 217Dh
0x180027def  mov     r9d, ebx
0x180027df2  mov     [rsp+0E0h+var_C0], rax
0x180027df7  lea     r8, aFailedToInitia_5; "Failed to initialize xml parser"
0x180027dfe  lea     rdx, aWinresetsettin_3; "WinReSetSettings %s (0x%x) in file %S l"...
0x180027e05  lea     ecx, [rdi+1]
0x180027e08  call    UnattendLogW
0x180027e0d  jmp     loc_18002813C
0x180027e12  mov     rsi, qword ptr [rbp+57h+var_60]
0x180027e16  lea     rcx, [rbp+57h+var_B0]; this
0x180027e1a  call    ?CreateSrSettings@SrSettings@@YAJPEAPEAUISrSettings@1@@Z; SrSettings::CreateSrSettings(SrSettings::ISrSettings * *)
0x180027e1f  mov     r14d, eax
0x180027e22  test    eax, eax
0x180027e24  jns     short loc_180027E44
0x180027e26  mov     r8d, eax
0x180027e29  lea     rdx, aFailedToCreate_9; "Failed to create settings object. Error"...
0x180027e30  mov     ecx, edi
0x180027e32  call    UnattendLogW
0x180027e37  movzx   ebx, r14w
0x180027e3b  mov     r14, [rbp+57h+var_B0]
0x180027e3f  jmp     loc_18002813C
0x180027e44  mov     r14, [rbp+57h+var_B0]
0x180027e48  lea     rdx, [rbp+57h+var_A8]
0x180027e4c  xor     r9d, r9d
0x180027e4f  xor     r8d, r8d
0x180027e52  mov     rcx, r14
0x180027e55  mov     rax, [r14]
0x180027e58  mov     rax, [rax+8]
0x180027e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e61  mov     r15d, eax
0x180027e64  test    eax, eax
0x180027e66  jns     short loc_180027E82
0x180027e68  lea     rdx, aFailedToInitia; "Failed to initialize settings object. E"...
0x180027e6f  mov     r8d, r15d
0x180027e72  mov     ecx, edi
0x180027e74  call    UnattendLogW
0x180027e79  movzx   ebx, r15w
0x180027e7d  jmp     loc_18002813C
0x180027e82  lea     rcx, aAll; "All"
0x180027e89  call    ?AsmWinREClearRecoverySettings@@YAXPEBG@Z; AsmWinREClearRecoverySettings(ushort const *)
0x180027e8e  mov     rax, [r14]
0x180027e91  mov     rcx, r14
0x180027e94  mov     rax, [rax+58h]
0x180027e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e9d  mov     r15d, eax
0x180027ea0  test    eax, eax
0x180027ea2  jns     short loc_180027EAD
0x180027ea4  lea     rdx, aFailedToClearE_0; "Failed to clear existing settings. Erro"...
0x180027eab  jmp     short loc_180027E6F
0x180027ead  test    [rsi+4CCh], dil
0x180027eb4  jz      short loc_180027EF8
0x180027eb6  mov     rax, [r14]
0x180027eb9  lea     r8, [rsi+25Ch]
0x180027ec0  xor     r9d, r9d
0x180027ec3  mov     rdx, rsi
0x180027ec6  mov     rcx, r14
0x180027ec9  mov     rax, [rax+78h]
0x180027ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ed2  mov     r15d, eax
0x180027ed5  test    eax, eax
0x180027ed7  jns     short loc_180027EE2
0x180027ed9  lea     rdx, aFailedToStoreW; "Failed to store wifi credential. Error:"...
0x180027ee0  jmp     short loc_180027E6F
0x180027ee2  xor     r8d, r8d; bool
0x180027ee5  lea     rdx, cchOriginalDestLength; unsigned __int16 *
0x180027eec  lea     rcx, aWificredential; "WiFiCredential"
0x180027ef3  call    ?AsmWinRESetRecoverySettings@@YAXPEBG0_N@Z; AsmWinRESetRecoverySettings(ushort const *,ushort const *,bool)
0x180027ef8  test    byte ptr [rsi+4CCh], 20h
0x180027eff  lea     r12, aOff_0; "off"
0x180027f06  lea     r15, aOn_0; "on"
0x180027f0d  jz      short loc_180027F7B
0x180027f0f  mov     rax, [r14]
0x180027f12  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x180027f19  cmp     [rsi+4C4h], r13d
0x180027f20  mov     r8, r15
0x180027f23  mov     rcx, r14
0x180027f26  cmovz   r8, r12
0x180027f2a  xor     r9d, r9d
0x180027f2d  mov     rax, [rax+38h]
0x180027f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f36  mov     r12d, eax
0x180027f39  test    eax, eax
0x180027f3b  jns     short loc_180027F57
0x180027f3d  lea     rdx, aFailedToSetClo; "Failed to set cloud remediation setting"...
0x180027f44  mov     r8d, r12d
0x180027f47  mov     ecx, edi
0x180027f49  call    UnattendLogW
0x180027f4e  movzx   ebx, r12w
0x180027f52  jmp     loc_18002813C
0x180027f57  cmp     [rsi+4C4h], r13d
0x180027f5e  lea     r12, aOff_0; "off"
0x180027f65  mov     rdx, r15
0x180027f68  lea     rcx, aCloudremediati_0; "CloudRemediation"
0x180027f6f  cmovz   rdx, r12; unsigned __int16 *
0x180027f73  xor     r8d, r8d; bool
0x180027f76  call    ?AsmWinRESetRecoverySettings@@YAXPEBG0_N@Z; AsmWinRESetRecoverySettings(ushort const *,ushort const *,bool)
0x180027f7b  test    byte ptr [rsi+4CCh], 2
0x180027f82  jz      short loc_180027FDF
0x180027f84  mov     rax, [r14]
0x180027f87  lea     rdx, aAutoremediatio; "AutoRemediation"
0x180027f8e  cmp     [rsi+4C0h], r13d
0x180027f95  mov     r8, r15
0x180027f98  mov     rcx, r14
0x180027f9b  cmovz   r8, r12
0x180027f9f  xor     r9d, r9d
0x180027fa2  mov     rax, [rax+38h]
0x180027fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fab  mov     r12d, eax
0x180027fae  test    eax, eax
0x180027fb0  jns     short loc_180027FBB
0x180027fb2  lea     rdx, aFailedToSetAut; "Failed to set auto remediation setting."...
0x180027fb9  jmp     short loc_180027F44
0x180027fbb  cmp     [rsi+4C0h], r13d
0x180027fc2  lea     r12, aOff_0; "off"
0x180027fc9  mov     rdx, r15
0x180027fcc  lea     rcx, aAutoremediatio; "AutoRemediation"
0x180027fd3  cmovz   rdx, r12; unsigned __int16 *
0x180027fd7  xor     r8d, r8d; bool
0x180027fda  call    ?AsmWinRESetRecoverySettings@@YAXPEBG0_N@Z; AsmWinRESetRecoverySettings(ushort const *,ushort const *,bool)
0x180027fdf  test    byte ptr [rsi+4CCh], 4
0x180027fe6  jz      short loc_180028046
0x180027fe8  mov     rax, [r14]
0x180027feb  lea     rdx, aHeadlessmode; "HeadlessMode"
0x180027ff2  cmp     [rsi+4C8h], r13d
0x180027ff9  mov     r8, r15
0x180027ffc  mov     rcx, r14
0x180027fff  cmovz   r8, r12
0x180028003  xor     r9d, r9d
0x180028006  mov     rax, [rax+38h]
0x18002800a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002800f  mov     r12d, eax
0x180028012  test    eax, eax
0x180028014  jns     short loc_180028022
0x180028016  lea     rdx, aFailedToSetHea; "Failed to set headless setting. Error: "...
0x18002801d  jmp     loc_180027F44
0x180028022  cmp     [rsi+4C8h], r13d
0x180028029  lea     rax, aOff_0; "off"
0x180028030  lea     rcx, aHeadlessmode; "HeadlessMode"
0x180028037  cmovz   r15, rax
0x18002803b  xor     r8d, r8d; bool
0x18002803e  mov     rdx, r15; unsigned __int16 *
0x180028041  call    ?AsmWinRESetRecoverySettings@@YAXPEBG0_N@Z; AsmWinRESetRecoverySettings(ushort const *,ushort const *,bool)
0x180028046  test    byte ptr [rsi+4CCh], 8
0x18002804d  jz      short loc_180028097
0x18002804f  mov     rax, [r14]
0x180028052  lea     rdx, aTotalwaittime_0; "TotalWaitTime"
0x180028059  mov     r8d, [rsi+4B8h]
0x180028060  xor     r9d, r9d
0x180028063  mov     rcx, r14
0x180028066  mov     rax, [rax+30h]
0x18002806a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002806f  mov     r15d, eax
0x180028072  test    eax, eax
0x180028074  jns     short loc_180028082
0x180028076  lea     rdx, aFailedToSetTot; "Failed to set total timeout. Error: 0x%"...
0x18002807d  jmp     loc_180027E6F
0x180028082  mov     edx, [rsi+4B8h]; unsigned int
0x180028088  lea     rcx, aTotalwaittime_0; "TotalWaitTime"
0x18002808f  xor     r8d, r8d; bool
0x180028092  call    ?AsmWinRESetRecoverySettings@@YAXPEBGK_N@Z; AsmWinRESetRecoverySettings(ushort const *,ulong,bool)
0x180028097  test    byte ptr [rsi+4CCh], 10h
0x18002809e  jz      short loc_1800280E8
0x1800280a0  mov     rax, [r14]
0x1800280a3  lea     rdx, aWaitinterval; "WaitInterval"
0x1800280aa  mov     r8d, [rsi+4BCh]
0x1800280b1  xor     r9d, r9d
0x1800280b4  mov     rcx, r14
0x1800280b7  mov     rax, [rax+30h]
0x1800280bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280c0  mov     r15d, eax
0x1800280c3  test    eax, eax
0x1800280c5  jns     short loc_1800280D3
0x1800280c7  lea     rdx, aFailedToSetWai; "Failed to set wait interval. Error: 0x%"...
0x1800280ce  jmp     loc_180027E6F
0x1800280d3  mov     edx, [rsi+4BCh]; unsigned int
0x1800280d9  lea     rcx, aWaitinterval; "WaitInterval"
0x1800280e0  xor     r8d, r8d; bool
0x1800280e3  call    ?AsmWinRESetRecoverySettings@@YAXPEBGK_N@Z; AsmWinRESetRecoverySettings(ushort const *,ulong,bool)
0x1800280e8  lea     rdx, aBackupSettingF_3; "Backup setting file"
0x1800280ef  xor     ecx, ecx
0x1800280f1  call    UnattendLogW
0x1800280f6  call    ?AsmWinREBackupSettingFileStart@@YAXXZ; AsmWinREBackupSettingFileStart(void)
0x1800280fb  mov     rcx, r14; struct SrSettings::ISrSettings *
0x1800280fe  call    ?winreBackupSetting@@YAJPEAUISrSettings@SrSettings@@@Z; winreBackupSetting(SrSettings::ISrSettings *)
0x180028103  mov     edx, eax
0x180028105  movzx   r15d, ax
0x180028109  not     edx
0x18002810b  lea     rcx, cchOriginalDestLength; unsigned __int16 *
0x180028112  shr     edx, 1Fh; int
0x180028115  mov     r8d, r15d; unsigned int
0x180028118  mov     esi, eax
0x18002811a  call    ?AsmWinREBackupSettingFileEnd@@YAXPEBGHK@Z; AsmWinREBackupSettingFileEnd(ushort const *,int,ulong)
0x18002811f  test    esi, esi
0x180028121  jns     short loc_180028139
0x180028123  mov     r8d, esi
0x180028126  lea     rdx, aFailedToBackup_2; "Failed to backup setting file. Error: 0"...
0x18002812d  mov     ecx, edi
0x18002812f  call    UnattendLogW
0x180028134  mov     ebx, r15d
0x180028137  jmp     short loc_18002813C
0x180028139  mov     r13d, edi
0x18002813c  test    r14, r14
0x18002813f  jz      short loc_180028153
0x180028141  mov     rax, [r14]
0x180028144  mov     rcx, r14
0x180028147  mov     rax, [rax+0A8h]
0x18002814e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028153  mov     edx, ebx; unsigned int
0x180028155  mov     ecx, r13d; int
0x180028158  call    ?AsmWinREWinReSetSettingsEnd@@YAXHK@Z; AsmWinREWinReSetSettingsEnd(int,ulong)
0x18002815d  call    TraceLoggingUnregister_EventUnregister
0x180028162  mov     r9d, ebx
0x180028165  lea     rdx, aExitWinresetse_0; "Exit WinReSetSettings return value: %d,"...
0x18002816c  mov     r8d, r13d
0x18002816f  xor     ecx, ecx
0x180028171  call    UnattendLogW
0x180028176  call    UnattendFinalizeLog
0x18002817b  mov     ecx, ebx; dwErrCode
0x18002817d  call    cs:__imp_SetLastError
0x180028183  lea     rcx, [rbp+57h+var_A0]; this
0x180028187  call    ??1SettingXmlParser@@UEAA@XZ; SettingXmlParser::~SettingXmlParser(void)
0x18002818c  mov     eax, r13d
0x18002818f  mov     rcx, [rbp+57h+var_50]
0x180028193  xor     rcx, rsp; StackCookie
0x180028196  call    __security_check_cookie
  ... truncated ...
```
