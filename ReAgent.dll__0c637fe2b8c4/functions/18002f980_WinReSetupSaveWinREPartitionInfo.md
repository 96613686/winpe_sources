# WinReSetupSaveWinREPartitionInfo

- ea: `0x18002f980`
- end: `0x18002fc0e`
- name: `WinReSetupSaveWinREPartitionInfo`
- size: `654`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x180011974`
- `0x1800121b0`
- `0x18002f980`
- `0x180030f18`
- `0x180031a00`
- `0x180031e10`
- `0x180037eb4`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002fb8c`
- `KERNEL32!GetLastError` at `0x18002fb8c`
- `KERNEL32!SetLastError` at `0x18002fa22`
- `KERNEL32!SetLastError` at `0x18002fa22`
- `KERNEL32!GetFileAttributesW` at `0x18002fa30`
- `KERNEL32!GetFileAttributesW` at `0x18002fa30`
- `ole32!CoTaskMemFree` at `0x18002fbd1`
- `ole32!CoTaskMemFree` at `0x18002fbd1`

## string_xrefs

- `0x18002fa7a`: `DisableUpdateEnhancedConfigInfo`
- `0x18002fb02`: `failed to init agent config`
- `0x18002fab5`: `Failed to get config path from os guid`
- `0x18002faa1`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002faee`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002fa3e`: `Undo Directory [%s] does not exist.`
- `0x18002fb33`: `There is no WinRE installed for target OS`

## pseudocode

```c
__int64 __fastcall WinReSetupSaveWinREPartitionInfo(__int64 a1, const WCHAR *a2)
{
  unsigned int v2; // esi
  DWORD v5; // ecx
  unsigned int ConfigFilePathFromOsGuid; // eax
  unsigned int v7; // eax
  struct ReAgentConfigInfo *ConfigInfo; // rax
  struct ReAgentConfigInfo *v9; // rax
  DWORD LastError; // eax
  const wchar_t *v11; // r8
  _QWORD v13[3]; // [rsp+40h] [rbp-39h] BYREF
  int v14; // [rsp+58h] [rbp-21h]
  int v15; // [rsp+5Ch] [rbp-1Dh]
  __int128 v16; // [rsp+60h] [rbp-19h]
  __int128 v17; // [rsp+70h] [rbp-9h]
  __int64 v18; // [rsp+80h] [rbp+7h]
  int v19; // [rsp+88h] [rbp+Fh]
  GUID v20; // [rsp+90h] [rbp+17h] BYREF

  v2 = 0;
  v15 = 2;
  v13[1] = 0;
  v16 = 0;
  v13[2] = 0;
  v14 = 0;
  v17 = 0;
  v20 = GUID_NULL;
  v18 = 0;
  v13[0] = &ReAgentConfig::`vftable';
  v19 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupSaveWinREPartitionInfo");
  LogGuid(L"TargetOSBCDGuid: ", a1);
  if ( !a2 )
  {
    v5 = 160;
LABEL_3:
    SetLastError(v5);
    goto LABEL_17;
  }
  if ( GetFileAttributesW(a2) == -1 )
  {
    UnattendLogW(1, L"Undo Directory [%s] does not exist.", a2);
    v5 = 1168;
    goto LABEL_3;
  }
  if ( (unsigned int)winreGetOSGuidOrDefault(a1, &v20) )
  {
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v19 = 1;
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(&v20);
    if ( ConfigFilePathFromOsGuid )
    {
      UnattendLogW(
        2,
        L"WinReSetupSaveWinREPartitionInfo %s (0x%x) in file %S line %d",
        L"Failed to get config path from os guid",
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
        1449);
    }
    else
    {
      v7 = ReAgentConfig::Init((ReAgentConfig *)v13, 0, 1);
      if ( v7 )
      {
        UnattendLogW(
          2,
          L"WinReSetupSaveWinREPartitionInfo %s (0x%x) in file %S line %d",
          L"failed to init agent config",
          v7,
          "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
          1452);
      }
      else
      {
        if ( !*((_DWORD *)ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v13) + 1397) )
        {
          UnattendLogW(1, L"There is no WinRE installed for target OS");
          v5 = 50;
          goto LABEL_3;
        }
        ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v13);
        UnattendLogW(0, L"Current WinRE partition offset: %llu", *((_QWORD *)ConfigInfo + 156));
        v9 = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v13);
        if ( (unsigned int)SaveNewOffsetToBackup(a2, *((_QWORD *)v9 + 156), L"Current WinRE partition offset") )
        {
          v2 = 1;
        }
        else
        {
          LastError = GetLastError();
          UnattendLogW(1, L"Failed to save current WinRE partition offset. Err: 0x%08x", LastError);
        }
      }
    }
  }
  else
  {
    UnattendLogW(1, L"failed to get OS guid or default");
  }
LABEL_17:
  v11 = L"TRUE";
  if ( !v2 )
    v11 = L"FALSE";
  UnattendLogW(0, L" (WinRE)WinReSetupSaveWinREPartitionInfo() returning %s", v11);
  UnattendFinalizeLog();
  v13[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v13);
  return v2;
}

```

## disassembly

```asm
0x18002f980  mov     [rsp-8+arg_10], rbx
0x18002f985  push    rbp
0x18002f986  push    rsi
0x18002f987  push    rdi
0x18002f988  push    r13
0x18002f98a  push    r14
0x18002f98c  lea     rbp, [rsp-37h]
0x18002f991  sub     rsp, 0B0h
0x18002f998  mov     rax, cs:__security_cookie
0x18002f99f  xor     rax, rsp
0x18002f9a2  mov     [rbp+57h+var_30], rax
0x18002f9a6  xor     esi, esi
0x18002f9a8  mov     [rbp+57h+var_74], 2
0x18002f9af  xorps   xmm0, xmm0
0x18002f9b2  mov     [rbp+57h+var_88], rsi
0x18002f9b6  movdqa  [rbp+57h+var_70], xmm0
0x18002f9bb  lea     r13, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002f9c2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002f9c9  mov     rbx, rcx
0x18002f9cc  mov     [rbp+57h+var_80], rsi
0x18002f9d0  xorps   xmm1, xmm1
0x18002f9d3  mov     [rbp+57h+var_78], esi
0x18002f9d6  xor     edi, edi
0x18002f9d8  movdqa  [rbp+57h+var_60], xmm1
0x18002f9dd  xor     ecx, ecx
0x18002f9df  mov     [rbp+57h+var_A0], rdi
0x18002f9e3  movdqu  [rbp+57h+var_40], xmm0
0x18002f9e8  mov     r14, rdx
0x18002f9eb  mov     [rbp+57h+var_50], rsi
0x18002f9ef  mov     [rbp+57h+var_90], r13
0x18002f9f3  mov     [rbp+57h+var_48], esi
0x18002f9f6  call    UnattendInitializeLogEx2
0x18002f9fb  lea     rdx, aEnterWinresetu_8; "Enter WinReSetupSaveWinREPartitionInfo"
0x18002fa02  xor     ecx, ecx
0x18002fa04  call    UnattendLogW
0x18002fa09  mov     rdx, rbx
0x18002fa0c  lea     rcx, aTargetosbcdgui; "TargetOSBCDGuid: "
0x18002fa13  call    LogGuid
0x18002fa18  test    r14, r14
0x18002fa1b  jnz     short loc_18002FA2D
0x18002fa1d  mov     ecx, 0A0h; dwErrCode
0x18002fa22  call    cs:__imp_SetLastError
0x18002fa28  jmp     loc_18002FBA7
0x18002fa2d  mov     rcx, r14; lpFileName
0x18002fa30  call    cs:__imp_GetFileAttributesW
0x18002fa36  cmp     eax, 0FFFFFFFFh
0x18002fa39  jnz     short loc_18002FA56
0x18002fa3b  mov     r8, r14
0x18002fa3e  lea     rdx, aUndoDirectoryS; "Undo Directory [%s] does not exist."
0x18002fa45  mov     ecx, 1
0x18002fa4a  call    UnattendLogW
0x18002fa4f  mov     ecx, 490h
0x18002fa54  jmp     short loc_18002FA22
0x18002fa56  lea     rdx, [rbp+57h+var_40]
0x18002fa5a  mov     rcx, rbx
0x18002fa5d  call    winreGetOSGuidOrDefault
0x18002fa62  test    eax, eax
0x18002fa64  jnz     short loc_18002FA7A
0x18002fa66  lea     rdx, aFailedToGetOsG; "failed to get OS guid or default"
0x18002fa6d  lea     ecx, [rax+1]
0x18002fa70  call    UnattendLogW
0x18002fa75  jmp     loc_18002FBA7
0x18002fa7a  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18002fa81  xor     ecx, ecx
0x18002fa83  call    UnattendLogW
0x18002fa88  mov     ebx, 1
0x18002fa8d  lea     r8, [rbp+57h+var_A0]
0x18002fa91  lea     rcx, [rbp+57h+var_40]
0x18002fa95  mov     [rbp+57h+var_48], ebx
0x18002fa98  call    winreGetConfigFilePathFromOsGuid
0x18002fa9d  test    eax, eax
0x18002fa9f  jz      short loc_18002FAD7
0x18002faa1  lea     rdx, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002faa8  mov     [rsp+0D0h+var_A8], 5A9h
0x18002fab0  mov     [rsp+0D0h+var_B0], rdx
0x18002fab5  lea     r8, aFailedToGetCon_2; "Failed to get config path from os guid"
0x18002fabc  lea     rdx, aWinresetupsave_0; "WinReSetupSaveWinREPartitionInfo %s (0x"...
0x18002fac3  mov     r9d, eax
0x18002fac6  lea     ecx, [rbx+1]
0x18002fac9  call    UnattendLogW
0x18002face  mov     rdi, [rbp+57h+var_A0]
0x18002fad2  jmp     loc_18002FBA7
0x18002fad7  mov     rdi, [rbp+57h+var_A0]
0x18002fadb  lea     rcx, [rbp+57h+var_90]; this
0x18002fadf  mov     rdx, rdi; unsigned __int16 *
0x18002fae2  mov     r8d, ebx; int
0x18002fae5  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18002faea  test    eax, eax
0x18002faec  jz      short loc_18002FB22
0x18002faee  lea     rdx, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002faf5  mov     [rsp+0D0h+var_A8], 5ACh
0x18002fafd  mov     [rsp+0D0h+var_B0], rdx
0x18002fb02  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18002fb09  lea     rdx, aWinresetupsave_0; "WinReSetupSaveWinREPartitionInfo %s (0x"...
0x18002fb10  mov     r9d, eax
0x18002fb13  mov     ecx, 2
0x18002fb18  call    UnattendLogW
0x18002fb1d  jmp     loc_18002FBA7
0x18002fb22  lea     rcx, [rbp+57h+var_90]; this
0x18002fb26  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002fb2b  cmp     [rax+15D4h], esi
0x18002fb31  jnz     short loc_18002FB4B
0x18002fb33  lea     rdx, aThereIsNoWinre; "There is no WinRE installed for target "...
0x18002fb3a  mov     ecx, ebx
0x18002fb3c  call    UnattendLogW
0x18002fb41  mov     ecx, 32h ; '2'
0x18002fb46  jmp     loc_18002FA22
0x18002fb4b  lea     rcx, [rbp+57h+var_90]; this
0x18002fb4f  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002fb54  lea     rdx, aCurrentWinrePa; "Current WinRE partition offset: %llu"
0x18002fb5b  xor     ecx, ecx
0x18002fb5d  mov     r8, [rax+4E0h]
0x18002fb64  call    UnattendLogW
0x18002fb69  lea     rcx, [rbp+57h+var_90]; this
0x18002fb6d  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002fb72  lea     r8, aCurrentWinrePa_0; "Current WinRE partition offset"
0x18002fb79  mov     rcx, r14; lpFileName
0x18002fb7c  mov     rdx, [rax+4E0h]; unsigned __int64
0x18002fb83  call    ?SaveNewOffsetToBackup@@YAHPEBG_K0@Z; SaveNewOffsetToBackup(ushort const *,unsigned __int64,ushort const *)
0x18002fb88  test    eax, eax
0x18002fb8a  jnz     short loc_18002FBA5
0x18002fb8c  call    cs:__imp_GetLastError
0x18002fb92  lea     rdx, aFailedToSaveCu; "Failed to save current WinRE partition "...
0x18002fb99  mov     ecx, ebx
0x18002fb9b  mov     r8d, eax
0x18002fb9e  call    UnattendLogW
0x18002fba3  jmp     short loc_18002FBA7
0x18002fba5  mov     esi, ebx
0x18002fba7  lea     rax, aFalse_0; "FALSE"
0x18002fbae  test    esi, esi
0x18002fbb0  lea     r8, aTrue_0; "TRUE"
0x18002fbb7  cmovz   r8, rax
0x18002fbbb  lea     rdx, aWinreWinresetu_1; " (WinRE)WinReSetupSaveWinREPartitionInf"...
0x18002fbc2  xor     ecx, ecx
0x18002fbc4  call    UnattendLogW
0x18002fbc9  test    rdi, rdi
0x18002fbcc  jz      short loc_18002FBD7
0x18002fbce  mov     rcx, rdi; pv
0x18002fbd1  call    cs:__imp_CoTaskMemFree
0x18002fbd7  call    UnattendFinalizeLog
0x18002fbdc  lea     rcx, [rbp+57h+var_90]; this
0x18002fbe0  mov     [rbp+57h+var_90], r13
0x18002fbe4  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002fbe9  mov     eax, esi
0x18002fbeb  mov     rcx, [rbp+57h+var_30]
0x18002fbef  xor     rcx, rsp; StackCookie
0x18002fbf2  call    __security_check_cookie
0x18002fbf7  mov     rbx, [rsp+0D0h+arg_10]
0x18002fbff  add     rsp, 0B0h
0x18002fc06  pop     r14
0x18002fc08  pop     r13
0x18002fc0a  pop     rdi
0x18002fc0b  pop     rsi
0x18002fc0c  pop     rbp
0x18002fc0d  retn
```
