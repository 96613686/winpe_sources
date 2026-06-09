# WinReSetNarratorScheduled

- ea: `0x180026460`
- end: `0x180026662`
- name: `WinReSetNarratorScheduled`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x1800109d0`
- `0x180011974`
- `0x1800121b0`
- `0x180014754`
- `0x180026460`
- `0x180028e30`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002662a`
- `KERNEL32!SetLastError` at `0x18002662a`
- `ole32!CoTaskMemFree` at `0x180026602`
- `ole32!CoTaskMemFree` at `0x180026602`

## string_xrefs

- `0x180026543`: `DisableUpdateEnhancedConfigInfo`
- `0x180026537`: `failed to get config file path`
- `0x180026578`: `failed to init agent config`
- `0x1800265b4`: `ReAgent.xml`
- `0x1800265dc`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800265ab`: `failed to update agent config`
- `0x1800265d5`: `failed to back up config file`
- `0x1800264e5`: `Enter WinReSetNarratorScheduled`
- `0x180026500`: `Parameters: configWinDir: %s, State: %d`
- `0x1800265e6`: `WinReSetNarratorScheduled %s (0x%x) in file %S line %d`
- `0x18002660a`: `Exit WinReSetNarratorScheduled return value: %d, last error: 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WinReSetNarratorScheduled(unsigned int a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // r8
  __int64 v5; // r8
  DWORD ConfigFilePathFromWinDir; // eax
  unsigned __int16 *v7; // rbx
  DWORD v8; // edi
  const wchar_t *v9; // r8
  int v11; // [rsp+28h] [rbp-41h]
  LPVOID pv[2]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v13[3]; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+58h] [rbp-11h]
  int v15; // [rsp+5Ch] [rbp-Dh]
  __int128 v16; // [rsp+60h] [rbp-9h]
  __int128 v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+80h] [rbp+17h]
  int v19; // [rsp+88h] [rbp+1Fh]

  pv[0] = 0;
  v13[1] = 0;
  v16 = 0;
  v17 = 0;
  v15 = 2;
  v13[0] = &ReAgentConfig::`vftable';
  v13[2] = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetNarratorScheduled");
  v4 = a2;
  if ( !a2 )
    v4 = L"NULL";
  UnattendLogW(0, L"Parameters: configWinDir: %s, State: %d", v4, a1);
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a2, 1, v5, pv);
  v7 = (unsigned __int16 *)pv[0];
  v8 = ConfigFilePathFromWinDir;
  if ( ConfigFilePathFromWinDir )
  {
    v11 = 658;
    v9 = L"failed to get config file path";
  }
  else
  {
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v19 = 1;
    v8 = ReAgentConfig::Init((ReAgentConfig *)v13, v7, 1);
    if ( v8 )
    {
      v11 = 661;
      v9 = L"failed to init agent config";
    }
    else
    {
      ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v13);
      *(_DWORD *)(v18 + 7476) = a1;
      v8 = ReAgentXMLParser::Update((ReAgentXMLParser *)v13);
      if ( v8 )
      {
        v11 = 671;
        v9 = L"failed to update agent config";
      }
      else
      {
        v8 = winreBackupRecoveryFile(v7, (ReAgentXMLParser *)v13, L"ReAgent.xml");
        if ( !v8 )
          goto LABEL_12;
        v11 = 675;
        v9 = L"failed to back up config file";
      }
    }
  }
  UnattendLogW(
    2,
    L"WinReSetNarratorScheduled %s (0x%x) in file %S line %d",
    v9,
    v8,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v11);
LABEL_12:
  if ( v7 )
    CoTaskMemFree(v7);
  UnattendLogW(0, L"Exit WinReSetNarratorScheduled return value: %d, last error: 0x%x", v8 == 0, v8);
  UnattendFinalizeLog();
  SetLastError(v8);
  v13[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v13);
  return v8 == 0;
}

```

## disassembly

```asm
0x180026460  mov     [rsp-8+arg_10], rbx
0x180026465  push    rbp
0x180026466  push    rsi
0x180026467  push    rdi
0x180026468  push    r13
0x18002646a  push    r15
0x18002646c  lea     rbp, [rsp-37h]
0x180026471  sub     rsp, 0A0h
0x180026478  mov     rax, cs:__security_cookie
0x18002647f  xor     rax, rsp
0x180026482  mov     [rbp+57h+var_30], rax
0x180026486  mov     esi, ecx
0x180026488  mov     [rbp+57h+pv], 0
0x180026490  xorps   xmm0, xmm0
0x180026493  mov     [rbp+57h+var_78], 0
0x18002649b  xorps   xmm1, xmm1
0x18002649e  movdqa  [rbp+57h+var_60], xmm0
0x1800264a3  mov     r15d, 2
0x1800264a9  movdqa  [rbp+57h+var_50], xmm1
0x1800264ae  lea     r13, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x1800264b5  mov     [rbp+57h+var_64], r15d
0x1800264b9  xor     ecx, ecx
0x1800264bb  mov     [rbp+57h+var_80], r13
0x1800264bf  mov     rbx, rdx
0x1800264c2  mov     [rbp+57h+var_70], 0
0x1800264ca  mov     [rbp+57h+var_68], 0
0x1800264d1  mov     [rbp+57h+var_40], 0
0x1800264d9  mov     [rbp+57h+var_38], 0
0x1800264e0  call    UnattendInitializeLogEx2
0x1800264e5  lea     rdx, aEnterWinresetn; "Enter WinReSetNarratorScheduled"
0x1800264ec  xor     ecx, ecx
0x1800264ee  call    UnattendLogW
0x1800264f3  lea     rax, aNull_0; "NULL"
0x1800264fa  test    rbx, rbx
0x1800264fd  mov     r8, rbx
0x180026500  lea     rdx, aParametersConf; "Parameters: configWinDir: %s, State: %d"
0x180026507  cmovz   r8, rax
0x18002650b  mov     r9d, esi
0x18002650e  xor     ecx, ecx
0x180026510  call    UnattendLogW
0x180026515  lea     r9, [rbp+57h+pv]
0x180026519  mov     rcx, rbx
0x18002651c  lea     edx, [r15-1]
0x180026520  call    winreGetConfigFilePathFromWinDir
0x180026525  mov     rbx, [rbp+57h+pv]
0x180026529  mov     edi, eax
0x18002652b  test    eax, eax
0x18002652d  jz      short loc_180026543
0x18002652f  mov     [rsp+0C0h+var_98], 292h
0x180026537  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x18002653e  jmp     loc_1800265DC
0x180026543  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18002654a  xor     ecx, ecx
0x18002654c  call    UnattendLogW
0x180026551  mov     r8d, 1; int
0x180026557  mov     [rbp+57h+var_38], 1
0x18002655e  mov     rdx, rbx; unsigned __int16 *
0x180026561  lea     rcx, [rbp+57h+var_80]; this
0x180026565  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18002656a  mov     edi, eax
0x18002656c  test    eax, eax
0x18002656e  jz      short loc_180026581
0x180026570  mov     [rsp+0C0h+var_98], 295h
0x180026578  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18002657f  jmp     short loc_1800265DC
0x180026581  lea     rcx, [rbp+57h+var_80]; this
0x180026585  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002658a  mov     rax, [rbp+57h+var_40]
0x18002658e  lea     rcx, [rbp+57h+var_80]; this
0x180026592  mov     [rax+1D34h], esi
0x180026598  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x18002659d  mov     edi, eax
0x18002659f  test    eax, eax
0x1800265a1  jz      short loc_1800265B4
0x1800265a3  mov     [rsp+0C0h+var_98], 29Fh
0x1800265ab  lea     r8, aFailedToUpdate_7; "failed to update agent config"
0x1800265b2  jmp     short loc_1800265DC
0x1800265b4  lea     r8, aReagentXml_1; "ReAgent.xml"
0x1800265bb  mov     rcx, rbx; unsigned __int16 *
0x1800265be  lea     rdx, [rbp+57h+var_80]; this
0x1800265c2  call    winreBackupRecoveryFile
0x1800265c7  mov     edi, eax
0x1800265c9  test    eax, eax
0x1800265cb  jz      short loc_1800265FA
0x1800265cd  mov     [rsp+0C0h+var_98], 2A3h
0x1800265d5  lea     r8, aFailedToBackUp; "failed to back up config file"
0x1800265dc  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800265e3  mov     r9d, edi
0x1800265e6  lea     rdx, aWinresetnarrat_0; "WinReSetNarratorScheduled %s (0x%x) in "...
0x1800265ed  mov     [rsp+0C0h+var_A0], rax
0x1800265f2  mov     ecx, r15d
0x1800265f5  call    UnattendLogW
0x1800265fa  test    rbx, rbx
0x1800265fd  jz      short loc_180026608
0x1800265ff  mov     rcx, rbx; pv
0x180026602  call    cs:__imp_CoTaskMemFree
0x180026608  xor     ebx, ebx
0x18002660a  lea     rdx, aExitWinresetna; "Exit WinReSetNarratorScheduled return v"...
0x180026611  test    edi, edi
0x180026613  mov     r9d, edi
0x180026616  setz    bl
0x180026619  xor     ecx, ecx
0x18002661b  mov     r8d, ebx
0x18002661e  call    UnattendLogW
0x180026623  call    UnattendFinalizeLog
0x180026628  mov     ecx, edi; dwErrCode
0x18002662a  call    cs:__imp_SetLastError
0x180026630  lea     rcx, [rbp+57h+var_80]; this
0x180026634  mov     [rbp+57h+var_80], r13
0x180026638  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002663d  mov     eax, ebx
0x18002663f  mov     rcx, [rbp+57h+var_30]
0x180026643  xor     rcx, rsp; StackCookie
0x180026646  call    __security_check_cookie
0x18002664b  mov     rbx, [rsp+0C0h+arg_10]
0x180026653  add     rsp, 0A0h
0x18002665a  pop     r15
0x18002665c  pop     r13
0x18002665e  pop     rdi
0x18002665f  pop     rsi
0x180026660  pop     rbp
0x180026661  retn
```
