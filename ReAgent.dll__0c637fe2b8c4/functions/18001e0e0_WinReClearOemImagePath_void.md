# WinReClearOemImagePath(void)

- ea: `0x18001e0e0`
- end: `0x18001e2c1`
- name: `?WinReClearOemImagePath@@YAHXZ`
- size: `481`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x1800109d0`
- `0x1800121b0`
- `0x180014754`
- `0x18001df60`
- `0x18001e0e0`
- `0x180028e30`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001e290`
- `KERNEL32!SetLastError` at `0x18001e290`
- `ole32!CoTaskMemFree` at `0x18001e268`
- `ole32!CoTaskMemFree` at `0x18001e268`

## string_xrefs

- `0x18001e197`: `failed to get config file path`
- `0x18001e1e1`: `failed to init agent config`
- `0x18001e24d`: `ReAgent.xml`
- `0x18001e19e`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001e241`: `failed to update agent config`
- `0x18001e21e`: `failed to set os install location path`
- `0x18001e168`: `Enter WinReClearOemImagePath`
- `0x18001e1ad`: `WinReClearOemImagePath %s (0x%x) in file %S line %d`
- `0x18001e27b`: `Exit WinReClearOemImagePath return value: %d, last error: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 WinReClearOemImagePath(void)
{
  __int64 v0; // r8
  DWORD ConfigFilePathFromWinDir; // edi
  unsigned __int16 *v2; // rbx
  const wchar_t *v3; // r8
  __int64 v5; // [rsp+28h] [rbp-51h]
  struct _GUID v6; // [rsp+38h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v8[3]; // [rsp+50h] [rbp-29h] BYREF
  int v9; // [rsp+68h] [rbp-11h]
  int v10; // [rsp+6Ch] [rbp-Dh]
  __int128 v11; // [rsp+70h] [rbp-9h]
  __int128 v12; // [rsp+80h] [rbp+7h]
  __int64 v13; // [rsp+90h] [rbp+17h]
  int v14; // [rsp+98h] [rbp+1Fh]

  v8[1] = 0;
  v8[2] = 0;
  v9 = 0;
  v10 = 2;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v8[0] = &ReAgentConfig::`vftable';
  v14 = 0;
  pv = 0;
  v6 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReClearOemImagePath");
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(0, 1, v0, &pv);
  v2 = (unsigned __int16 *)pv;
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v5) = 2158;
    v3 = L"failed to get config file path";
LABEL_3:
    UnattendLogW(
      2,
      L"WinReClearOemImagePath %s (0x%x) in file %S line %d",
      v3,
      ConfigFilePathFromWinDir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v5,
      -2,
      *(_QWORD *)&v6.Data1,
      *(_QWORD *)v6.Data4);
    goto LABEL_11;
  }
  ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v8, (unsigned __int16 *)pv, 1);
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v5) = 2161;
    v3 = L"failed to init agent config";
    goto LABEL_3;
  }
  ConfigFilePathFromWinDir = ReAgentConfig::SetOsInstallLocationPath(
                               (ReAgentConfig *)v8,
                               0,
                               &v6,
                               0,
                               (unsigned __int16 *)&cchOriginalDestLength,
                               0);
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v5) = 2174;
    v3 = L"failed to set os install location path";
    goto LABEL_3;
  }
  ConfigFilePathFromWinDir = ReAgentXMLParser::Update((ReAgentXMLParser *)v8);
  if ( ConfigFilePathFromWinDir )
  {
    LODWORD(v5) = 2175;
    v3 = L"failed to update agent config";
    goto LABEL_3;
  }
  winreBackupRecoveryFile(v2, (ReAgentXMLParser *)v8, L"ReAgent.xml");
LABEL_11:
  if ( v2 )
    CoTaskMemFree(v2);
  UnattendLogW(
    0,
    L"Exit WinReClearOemImagePath return value: %d, last error: 0x%x",
    ConfigFilePathFromWinDir == 0,
    ConfigFilePathFromWinDir);
  UnattendFinalizeLog();
  SetLastError(ConfigFilePathFromWinDir);
  v8[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v8);
  return ConfigFilePathFromWinDir == 0;
}

```

## disassembly

```asm
0x18001e0e0  push    rbp
0x18001e0e2  push    rbx
0x18001e0e3  push    rdi
0x18001e0e4  push    r12
0x18001e0e6  push    r14
0x18001e0e8  lea     rbp, [rsp-37h]
0x18001e0ed  sub     rsp, 0B0h
0x18001e0f4  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001e0fc  mov     rax, cs:__security_cookie
0x18001e103  xor     rax, rsp
0x18001e106  mov     [rbp+57h+var_30], rax
0x18001e10a  mov     [rbp+57h+var_78], 0
0x18001e112  mov     [rbp+57h+var_70], 0
0x18001e11a  mov     [rbp+57h+var_68], 0
0x18001e121  mov     r14d, 2
0x18001e127  mov     [rbp+57h+var_64], r14d
0x18001e12b  xorps   xmm0, xmm0
0x18001e12e  movdqa  [rbp+57h+var_60], xmm0
0x18001e133  xorps   xmm1, xmm1
0x18001e136  movdqa  [rbp+57h+var_50], xmm1
0x18001e13b  mov     [rbp+57h+var_40], 0
0x18001e143  lea     r12, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18001e14a  mov     [rbp+57h+var_80], r12
0x18001e14e  mov     [rbp+57h+var_38], 0
0x18001e155  mov     [rbp+57h+pv], 0
0x18001e15d  movups  xmmword ptr [rbp+57h+var_98.Data1], xmm0
0x18001e161  xor     ecx, ecx
0x18001e163  call    UnattendInitializeLogEx2
0x18001e168  lea     rdx, aEnterWinreclea_5; "Enter WinReClearOemImagePath"
0x18001e16f  xor     ecx, ecx
0x18001e171  call    UnattendLogW
0x18001e176  lea     r9, [rbp+57h+pv]
0x18001e17a  lea     edx, [r14-1]
0x18001e17e  xor     ecx, ecx
0x18001e180  call    winreGetConfigFilePathFromWinDir
0x18001e185  mov     edi, eax
0x18001e187  mov     rbx, [rbp+57h+pv]
0x18001e18b  test    eax, eax
0x18001e18d  jz      short loc_18001E1C1
0x18001e18f  mov     dword ptr [rsp+0D0h+var_A8], 86Eh
0x18001e197  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x18001e19e  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001e1a5  mov     r9d, edi
0x18001e1a8  mov     [rsp+0D0h+var_B0], rax
0x18001e1ad  lea     rdx, aWinreclearoemi_0; "WinReClearOemImagePath %s (0x%x) in fil"...
0x18001e1b4  mov     ecx, r14d
0x18001e1b7  call    UnattendLogW
0x18001e1bc  jmp     loc_18001E260
0x18001e1c1  mov     r8d, 1; int
0x18001e1c7  mov     rdx, rbx; unsigned __int16 *
0x18001e1ca  lea     rcx, [rbp+57h+var_80]; this
0x18001e1ce  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18001e1d3  mov     edi, eax
0x18001e1d5  test    eax, eax
0x18001e1d7  jz      short loc_18001E1EA
0x18001e1d9  mov     dword ptr [rsp+0D0h+var_A8], 871h
0x18001e1e1  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18001e1e8  jmp     short loc_18001E19E
0x18001e1ea  mov     dword ptr [rsp+0D0h+var_A8], 0; int
0x18001e1f2  lea     rax, cchOriginalDestLength
0x18001e1f9  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x18001e1fe  xor     r9d, r9d; unsigned int
0x18001e201  lea     r8, [rbp+57h+var_98]; struct _GUID *
0x18001e205  xor     edx, edx; unsigned __int64
0x18001e207  lea     rcx, [rbp+57h+var_80]; this
0x18001e20b  call    ?SetOsInstallLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAGH@Z; ReAgentConfig::SetOsInstallLocationPath(unsigned __int64,_GUID *,ulong,ushort *,int)
0x18001e210  mov     edi, eax
0x18001e212  test    eax, eax
0x18001e214  jz      short loc_18001E22A
0x18001e216  mov     dword ptr [rsp+0D0h+var_A8], 87Eh
0x18001e21e  lea     r8, aFailedToSetOsI; "failed to set os install location path"
0x18001e225  jmp     loc_18001E19E
0x18001e22a  lea     rcx, [rbp+57h+var_80]; this
0x18001e22e  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x18001e233  mov     edi, eax
0x18001e235  test    eax, eax
0x18001e237  jz      short loc_18001E24D
0x18001e239  mov     dword ptr [rsp+0D0h+var_A8], 87Fh
0x18001e241  lea     r8, aFailedToUpdate_7; "failed to update agent config"
0x18001e248  jmp     loc_18001E19E
0x18001e24d  lea     r8, aReagentXml_1; "ReAgent.xml"
0x18001e254  lea     rdx, [rbp+57h+var_80]; this
0x18001e258  mov     rcx, rbx; unsigned __int16 *
0x18001e25b  call    winreBackupRecoveryFile
0x18001e260  test    rbx, rbx
0x18001e263  jz      short loc_18001E26E
0x18001e265  mov     rcx, rbx; pv
0x18001e268  call    cs:__imp_CoTaskMemFree
0x18001e26e  xor     ebx, ebx
0x18001e270  test    edi, edi
0x18001e272  setz    bl
0x18001e275  mov     r9d, edi
0x18001e278  mov     r8d, ebx
0x18001e27b  lea     rdx, aExitWinreclear_4; "Exit WinReClearOemImagePath return valu"...
0x18001e282  xor     ecx, ecx
0x18001e284  call    UnattendLogW
0x18001e289  call    UnattendFinalizeLog
0x18001e28e  mov     ecx, edi; dwErrCode
0x18001e290  call    cs:__imp_SetLastError
0x18001e296  nop
0x18001e297  mov     [rbp+57h+var_80], r12
0x18001e29b  lea     rcx, [rbp+57h+var_80]; this
0x18001e29f  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18001e2a4  mov     eax, ebx
0x18001e2a6  mov     rcx, [rbp+57h+var_30]
0x18001e2aa  xor     rcx, rsp; StackCookie
0x18001e2ad  call    __security_check_cookie
0x18001e2b2  add     rsp, 0B0h
0x18001e2b9  pop     r14
0x18001e2bb  pop     r12
0x18001e2bd  pop     rdi
0x18001e2be  pop     rbx
0x18001e2bf  pop     rbp
0x18001e2c0  retn
```
