# WinReGetLogDirPathInternal

- ea: `0x18002bfac`
- end: `0x18002c27a`
- name: `WinReGetLogDirPathInternal`
- size: `718`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18002a570`
- `0x18002b358`
- `0x18002b6f0`
- `0x18002bec4`
- `0x18002bf60`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x180008b94`
- `0x18000c658`
- `0x18000ff68`
- `0x18000ffcc`
- `0x1800109d0`
- `0x180011974`
- `0x1800121b0`
- `0x18002bad4`
- `0x18002bfac`
- `0x18002ca4c`
- `0x1800322a8`
- `0x18005cf30`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c230`
- `ole32!CoTaskMemFree` at `0x18002c242`
- `ole32!CoTaskMemFree` at `0x18002c230`
- `ole32!CoTaskMemFree` at `0x18002c242`

## string_xrefs

- `0x18002c0da`: `failed to init agent config`
- `0x18002c057`: `failed to allocate path`
- `0x18002c092`: `failed to get congig file path`
- `0x18002c12f`: `failed to copy string`
- `0x18002c040`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c099`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c125`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c1f0`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c061`: `WinReGetLogDirPathInternal %s (0x%x) in file %S line %d`
- `0x18002c0a3`: `WinReGetLogDirPathInternal %s (0x%x) in file %S line %d`
- `0x18002c13b`: `WinReGetLogDirPathInternal %s (0x%x) in file %S line %d`
- `0x18002c211`: `WinReGetLogDirPathInternal %s (0x%x) in file %S line %d`
- `0x18002c168`: `failed to open log directory`
- `0x18002c1aa`: `failed to drop file form path`

## pseudocode

```c
__int64 __fastcall WinReGetLogDirPathInternal(WCHAR **a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  WCHAR *v4; // rdi
  int ConfigFilePathFromWinDir; // ebx
  const wchar_t *v6; // r8
  struct ReAgentConfigInfo *ConfigInfo; // rax
  int v8; // esi
  int v10; // [rsp+28h] [rbp-51h]
  int v11; // [rsp+28h] [rbp-51h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-39h] BYREF
  int v15; // [rsp+58h] [rbp-21h]
  int v16; // [rsp+5Ch] [rbp-1Dh]
  __int128 v17; // [rsp+60h] [rbp-19h]
  __int128 v18; // [rsp+70h] [rbp-9h]
  __int64 v19; // [rsp+80h] [rbp+7h]
  int v20; // [rsp+88h] [rbp+Fh]

  lpFileName = 0;
  pv = 0;
  v17 = 0;
  v18 = 0;
  v14[0] = &ReAgentConfig::`vftable';
  v16 = 2;
  v14[1] = 0;
  v14[2] = 0;
  v15 = 0;
  v19 = 0;
  v20 = 0;
  v2 = winreAllocPath(&lpFileName);
  v4 = (WCHAR *)lpFileName;
  ConfigFilePathFromWinDir = v2;
  if ( v2 )
  {
    UnattendLogW(
      2,
      L"WinReGetLogDirPathInternal %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      v2,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      132);
LABEL_27:
    if ( v4 )
      CoTaskMemFree(v4);
    goto LABEL_29;
  }
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(0, 1, v3, &pv);
  if ( ConfigFilePathFromWinDir )
  {
    v10 = 138;
    v6 = L"failed to get congig file path";
LABEL_5:
    UnattendLogW(
      2,
      L"WinReGetLogDirPathInternal %s (0x%x) in file %S line %d",
      v6,
      (unsigned int)ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      v10);
    goto LABEL_24;
  }
  ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v14, (unsigned __int16 *)pv, 1);
  if ( ConfigFilePathFromWinDir )
  {
    v10 = 141;
    v6 = L"failed to init agent config";
    goto LABEL_5;
  }
  ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v14);
  if ( *((_DWORD *)ConfigInfo + 1397) )
  {
    ConfigFilePathFromWinDir = StringCchCopyW(v4, 0x12Eu, (const unsigned __int16 *)ConfigInfo + 8);
    if ( ConfigFilePathFromWinDir < 0 )
    {
      v11 = 169;
      goto LABEL_12;
    }
    ConfigFilePathFromWinDir = winreDropFileFormPath(v4);
    if ( ConfigFilePathFromWinDir )
    {
      v10 = 175;
      v6 = L"failed to drop file form path";
      goto LABEL_5;
    }
  }
  else
  {
    if ( !(unsigned int)winreGetStoredRecoveryDir(v4) )
    {
      ConfigFilePathFromWinDir = StringCchCopyW(v4, 0x12Eu, L"c:\\Recovery");
      if ( ConfigFilePathFromWinDir < 0 )
      {
        v11 = 159;
LABEL_12:
        UnattendLogW(
          2,
          L"WinReGetLogDirPathInternal %s (0x%x) in file %S line %d",
          L"failed to copy string",
          (unsigned int)ConfigFilePathFromWinDir,
          "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
          v11);
        ConfigFilePathFromWinDir = (unsigned __int16)ConfigFilePathFromWinDir;
        goto LABEL_24;
      }
    }
    ConfigFilePathFromWinDir = winreOpenOrCreateDir(v4);
    if ( ConfigFilePathFromWinDir )
    {
      v10 = 162;
      v6 = L"failed to open log directory";
      goto LABEL_5;
    }
  }
  ConfigFilePathFromWinDir = winreAddTrailingBackslash(v4);
  if ( ConfigFilePathFromWinDir )
  {
    v10 = 178;
    v6 = L"failed to add trailing back slash";
    goto LABEL_5;
  }
  v8 = StringCchCatW(v4, 0x12Eu, L"Logs");
  if ( v8 >= 0 )
  {
    *a1 = v4;
  }
  else
  {
    UnattendLogW(
      2,
      L"WinReGetLogDirPathInternal %s (0x%x) in file %S line %d",
      L"failed to concatenate string",
      (unsigned int)v8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      180);
    ConfigFilePathFromWinDir = (unsigned __int16)v8;
  }
LABEL_24:
  if ( pv )
    CoTaskMemFree(pv);
  if ( ConfigFilePathFromWinDir )
    goto LABEL_27;
LABEL_29:
  v14[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v14);
  return (unsigned int)ConfigFilePathFromWinDir;
}

```

## disassembly

```asm
0x18002bfac  push    rbp
0x18002bfae  push    rbx
0x18002bfaf  push    rsi
0x18002bfb0  push    rdi
0x18002bfb1  push    r13
0x18002bfb3  push    r15
0x18002bfb5  lea     rbp, [rsp-2Fh]
0x18002bfba  sub     rsp, 0A8h
0x18002bfc1  mov     rax, cs:__security_cookie
0x18002bfc8  xor     rax, rsp
0x18002bfcb  mov     [rbp+57h+var_40], rax
0x18002bfcf  mov     r15, rcx
0x18002bfd2  mov     [rbp+57h+lpFileName], 0
0x18002bfda  xorps   xmm0, xmm0
0x18002bfdd  mov     [rbp+57h+pv], 0
0x18002bfe5  xorps   xmm1, xmm1
0x18002bfe8  movdqa  [rbp+57h+var_70], xmm0
0x18002bfed  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002bff4  movdqa  [rbp+57h+var_60], xmm1
0x18002bff9  mov     r13d, 2
0x18002bfff  mov     [rbp+57h+var_90], rax
0x18002c003  lea     rcx, [rbp+57h+lpFileName]
0x18002c007  mov     [rbp+57h+var_74], r13d
0x18002c00b  mov     [rbp+57h+var_88], 0
0x18002c013  mov     [rbp+57h+var_80], 0
0x18002c01b  mov     [rbp+57h+var_78], 0
0x18002c022  mov     [rbp+57h+var_50], 0
0x18002c02a  mov     [rbp+57h+var_48], 0
0x18002c031  call    winreAllocPath
0x18002c036  mov     rdi, [rbp+57h+lpFileName]
0x18002c03a  mov     ebx, eax
0x18002c03c  test    eax, eax
0x18002c03e  jz      short loc_18002C072
0x18002c040  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c047  mov     [rsp+0D0h+var_A8], 84h
0x18002c04f  mov     r9d, ebx
0x18002c052  mov     [rsp+0D0h+var_B0], rax
0x18002c057  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002c05e  mov     ecx, r13d
0x18002c061  lea     rdx, aWinregetlogdir_0; "WinReGetLogDirPathInternal %s (0x%x) in"...
0x18002c068  call    UnattendLogW
0x18002c06d  jmp     loc_18002C23A
0x18002c072  mov     esi, 1
0x18002c077  lea     r9, [rbp+57h+pv]
0x18002c07b  mov     edx, esi
0x18002c07d  xor     ecx, ecx
0x18002c07f  call    winreGetConfigFilePathFromWinDir
0x18002c084  mov     ebx, eax
0x18002c086  test    eax, eax
0x18002c088  jz      short loc_18002C0BC
0x18002c08a  mov     [rsp+0D0h+var_A8], 8Ah
0x18002c092  lea     r8, aFailedToGetCon_4; "failed to get congig file path"
0x18002c099  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c0a0  mov     r9d, ebx
0x18002c0a3  lea     rdx, aWinregetlogdir_0; "WinReGetLogDirPathInternal %s (0x%x) in"...
0x18002c0aa  mov     [rsp+0D0h+var_B0], rax
0x18002c0af  mov     ecx, r13d
0x18002c0b2  call    UnattendLogW
0x18002c0b7  jmp     loc_18002C225
0x18002c0bc  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18002c0c0  lea     rcx, [rbp+57h+var_90]; this
0x18002c0c4  mov     r8d, esi; int
0x18002c0c7  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18002c0cc  mov     ebx, eax
0x18002c0ce  test    eax, eax
0x18002c0d0  jz      short loc_18002C0E3
0x18002c0d2  mov     [rsp+0D0h+var_A8], 8Dh
0x18002c0da  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18002c0e1  jmp     short loc_18002C099
0x18002c0e3  lea     rcx, [rbp+57h+var_90]; this
0x18002c0e7  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002c0ec  mov     rcx, rdi; unsigned __int16 *
0x18002c0ef  cmp     dword ptr [rax+15D4h], 0
0x18002c0f6  jnz     short loc_18002C174
0x18002c0f8  call    ?winreGetStoredRecoveryDir@@YAHPEAG@Z; winreGetStoredRecoveryDir(ushort *)
0x18002c0fd  mov     esi, 12Eh
0x18002c102  test    eax, eax
0x18002c104  jnz     short loc_18002C152
0x18002c106  lea     r8, aCRecovery; "c:\\Recovery"
0x18002c10d  mov     edx, esi; unsigned __int64
0x18002c10f  mov     rcx, rdi; unsigned __int16 *
0x18002c112  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c117  mov     ebx, eax
0x18002c119  test    eax, eax
0x18002c11b  jns     short loc_18002C152
0x18002c11d  mov     [rsp+0D0h+var_A8], 9Fh
0x18002c125  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c12c  mov     r9d, ebx
0x18002c12f  lea     r8, aFailedToCopySt; "failed to copy string"
0x18002c136  mov     [rsp+0D0h+var_B0], rax
0x18002c13b  lea     rdx, aWinregetlogdir_0; "WinReGetLogDirPathInternal %s (0x%x) in"...
0x18002c142  mov     ecx, r13d
0x18002c145  call    UnattendLogW
0x18002c14a  movzx   ebx, bx
0x18002c14d  jmp     loc_18002C225
0x18002c152  mov     rcx, rdi; lpFileName
0x18002c155  call    winreOpenOrCreateDir
0x18002c15a  mov     ebx, eax
0x18002c15c  test    eax, eax
0x18002c15e  jz      short loc_18002C1B6
0x18002c160  mov     [rsp+0D0h+var_A8], 0A2h
0x18002c168  lea     r8, aFailedToOpenLo_0; "failed to open log directory"
0x18002c16f  jmp     loc_18002C099
0x18002c174  mov     esi, 12Eh
0x18002c179  lea     r8, [rax+10h]; unsigned __int16 *
0x18002c17d  mov     edx, esi; unsigned __int64
0x18002c17f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c184  mov     ebx, eax
0x18002c186  test    eax, eax
0x18002c188  jns     short loc_18002C194
0x18002c18a  mov     [rsp+0D0h+var_A8], 0A9h
0x18002c192  jmp     short loc_18002C125
0x18002c194  mov     rcx, rdi
0x18002c197  call    winreDropFileFormPath
0x18002c19c  mov     ebx, eax
0x18002c19e  test    eax, eax
0x18002c1a0  jz      short loc_18002C1B6
0x18002c1a2  mov     [rsp+0D0h+var_A8], 0AFh
0x18002c1aa  lea     r8, aFailedToDropFi_0; "failed to drop file form path"
0x18002c1b1  jmp     loc_18002C099
0x18002c1b6  mov     rcx, rdi
0x18002c1b9  call    winreAddTrailingBackslash
0x18002c1be  mov     ebx, eax
0x18002c1c0  test    eax, eax
0x18002c1c2  jz      short loc_18002C1D8
0x18002c1c4  mov     [rsp+0D0h+var_A8], 0B2h
0x18002c1cc  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18002c1d3  jmp     loc_18002C099
0x18002c1d8  lea     r8, aLogs; "Logs"
0x18002c1df  mov     rdx, rsi; unsigned __int64
0x18002c1e2  mov     rcx, rdi; unsigned __int16 *
0x18002c1e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c1ea  mov     esi, eax
0x18002c1ec  test    eax, eax
0x18002c1ee  jns     short loc_18002C222
0x18002c1f0  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c1f7  mov     [rsp+0D0h+var_A8], 0B4h
0x18002c1ff  mov     r9d, esi
0x18002c202  mov     [rsp+0D0h+var_B0], rax
0x18002c207  lea     r8, aFailedToConcat; "failed to concatenate string"
0x18002c20e  mov     ecx, r13d
0x18002c211  lea     rdx, aWinregetlogdir_0; "WinReGetLogDirPathInternal %s (0x%x) in"...
0x18002c218  call    UnattendLogW
0x18002c21d  movzx   ebx, si
0x18002c220  jmp     short loc_18002C225
0x18002c222  mov     [r15], rdi
0x18002c225  cmp     [rbp+57h+pv], 0
0x18002c22a  jz      short loc_18002C236
0x18002c22c  mov     rcx, [rbp+57h+pv]; pv
0x18002c230  call    cs:__imp_CoTaskMemFree
0x18002c236  test    ebx, ebx
0x18002c238  jz      short loc_18002C248
0x18002c23a  test    rdi, rdi
0x18002c23d  jz      short loc_18002C248
0x18002c23f  mov     rcx, rdi; pv
0x18002c242  call    cs:__imp_CoTaskMemFree
0x18002c248  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002c24f  lea     rcx, [rbp+57h+var_90]; this
0x18002c253  mov     [rbp+57h+var_90], rax
0x18002c257  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002c25c  mov     eax, ebx
0x18002c25e  mov     rcx, [rbp+57h+var_40]
0x18002c262  xor     rcx, rsp; StackCookie
0x18002c265  call    __security_check_cookie
0x18002c26a  add     rsp, 0A8h
0x18002c271  pop     r15
0x18002c273  pop     r13
0x18002c275  pop     rdi
0x18002c276  pop     rsi
0x18002c277  pop     rbx
0x18002c278  pop     rbp
0x18002c279  retn
```
