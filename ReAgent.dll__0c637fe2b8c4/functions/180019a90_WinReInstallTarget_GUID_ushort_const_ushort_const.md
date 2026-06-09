# WinReInstallTarget(_GUID *,ushort const *,ushort const *)

- ea: `0x180019a90`
- end: `0x18001a16a`
- name: `?WinReInstallTarget@@YAHPEAU_GUID@@PEBG1@Z`
- size: `1754`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000196c`
- `0x180001adc`
- `0x180002786`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x18000edec`
- `0x18000ee80`
- `0x1800109d0`
- `0x180011344`
- `0x180011974`
- `0x1800121b0`
- `0x1800145f4`
- `0x180014754`
- `0x1800187e0`
- `0x180019a90`
- `0x18001a1ac`
- `0x180028e30`
- `0x180029074`
- `0x180030df0`
- `0x180030f18`
- `0x180031a00`
- `0x180032488`
- `0x180032564`
- `0x180034aa4`
- `0x1800356d4`
- `0x180035e88`
- `0x18003648c`
- `0x18003aac0`
- `0x18003dcbc`
- `0x18003dd24`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019c3c`
- `msvcrt!_wcsicmp` at `0x180019c3c`
- `KERNEL32!SetLastError` at `0x180019ca4`
- `KERNEL32!SetLastError` at `0x180019ca4`
- `ole32!CoTaskMemFree` at `0x180019c77`
- `ole32!CoTaskMemFree` at `0x180019c77`

## string_xrefs

- `0x180019d0e`: `DisableUpdateEnhancedConfigInfo`
- `0x180019dbd`: `failed to init agent config`
- `0x180019c01`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019d4b`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019d91`: `Failed to get config path`
- `0x18001a0ea`: `Failed to update config file`
- `0x180019d44`: `Failed to get config path from os guid`
- `0x180019e03`: `Copying WinRE from %s to staging location on %s`
- `0x180019eaa`: `Failed to create BCD recovery entry %d`
- `0x180019e58`: `winre RenameWimDir failed`
- `0x180019f70`: `Updating reagent.xml`
- `0x180019ff3`: `Set WinRE location path to: %s`
- `0x18001a040`: `Set scheduled operation: WinReNoOperation`
- `0x18001a0ac`: `Set install state to: enabled`
- `0x180019b7a`: `Enter WinReInstallTarget`
- `0x180019b8e`: `Parameters: TargetWimPath: %s, VolumeName: %s`
- `0x180019bb0`: `Target WinRE path is NULL`
- `0x180019c10`: `WinReInstallTarget %s (0x%x) in file %S line %d`
- `0x180019d5a`: `WinReInstallTarget %s (0x%x) in file %S line %d`
- `0x180019ded`: `winre RemoveWimDir from partition failed`
- `0x180019e2e`: `winreCopyWIMFile failed`
- `0x180019ef8`: `Update existing WinRE BCD`
- `0x180019f2f`: `Failed to update Recovery BCD`
- `0x180019fa2`: `ImageLocation path no longer valid, clear ImageLocation value`
- `0x180019fe0`: `failed to clear ImageLocation path`
- `0x180019c83`: `Exit WinReInstallTarget return value: %d, last error: 0x%x`
- `0x18001a0f6`: `ReAgent.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinReInstallTarget(struct _GUID *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // r13d
  unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // rbx
  DWORD PartitionList; // ebx
  const wchar_t *v11; // r8
  const wchar_t *i; // rbx
  __int64 v13; // rdx
  __int64 v15; // r8
  const wchar_t *v16; // r8
  struct ReAgentConfigInfo *ConfigInfo; // rsi
  DWORD RecoveryEntryInBCD; // eax
  int v19; // r12d
  unsigned int v20; // eax
  ReAgentXMLParser *v21; // rcx
  unsigned int v22; // eax
  DWORD v23; // eax
  int v24; // [rsp+30h] [rbp-D8h]
  int v25; // [rsp+30h] [rbp-D8h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v27[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+78h] [rbp-90h]
  __int128 v29; // [rsp+88h] [rbp-80h]
  __int64 v30; // [rsp+98h] [rbp-70h]
  int v31; // [rsp+A0h] [rbp-68h]
  __int128 v32; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v33[32]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v34; // [rsp+D8h] [rbp-30h]
  struct _GUID v35; // [rsp+DCh] [rbp-2Ch] BYREF
  _BYTE v36[608]; // [rsp+348h] [rbp+240h] BYREF
  unsigned __int64 v37; // [rsp+5A8h] [rbp+4A0h]
  unsigned __int16 v38[304]; // [rsp+5E8h] [rbp+4E0h] BYREF

  v6 = 0;
  v32 = 0;
  v7 = 0;
  v26 = 0;
  v27[1] = 0;
  v27[2] = 0;
  v27[3] = 0x200000000LL;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v27[0] = &ReAgentConfig::`vftable';
  v31 = 0;
  memset_0(v33, 0, 0x530u);
  memset_0(v38, 0, 0x25Cu);
  UnattendInitializeLogEx2(0);
  TraceLoggingRegisterEx_EventRegister_2U();
  v8 = a3;
  if ( !a3 )
    v8 = L"NULL";
  v9 = a2;
  if ( !a2 )
    v9 = L"NULL";
  AsmInstallTargetWinREStart(v9, v8);
  UnattendLogW(0, L"Enter WinReInstallTarget");
  UnattendLogW(0, L"Parameters: TargetWimPath: %s, VolumeName: %s", v9, v8);
  LogGuid(L"TargetOSGuid", a1);
  if ( !a2 )
  {
    UnattendLogW(1, L"Target WinRE path is NULL");
LABEL_7:
    PartitionList = 87;
    goto LABEL_18;
  }
  if ( !a3 )
  {
    UnattendLogW(1, L"Volume name is NULL");
    goto LABEL_7;
  }
  PrivateFreePartitionList(0);
  PartitionList = PrivateGetPartitionList(0);
  if ( PartitionList )
  {
    v24 = 2228;
    v11 = L"failed to get partition list";
LABEL_12:
    UnattendLogW(
      2,
      L"WinReInstallTarget %s (0x%x) in file %S line %d",
      v11,
      PartitionList,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      v24);
    goto LABEL_18;
  }
  LogAllPartitionInfo(0);
  for ( i = (const wchar_t *)MEMORY[0]; ; i = *(const wchar_t **)i )
  {
    if ( !i )
    {
      UnattendLogW(1, L"Failed to find the target volume");
      PartitionList = 1168;
      goto LABEL_18;
    }
    if ( !_wcsicmp(a3, i + 26) )
      break;
  }
  memcpy_0(v33, i, 0x530u);
  UnattendLogW(0, L"Find target partition");
  UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
  v31 = 1;
  if ( a1 )
  {
    PartitionList = winreGetConfigFilePathFromOsGuid(a1);
    if ( PartitionList )
    {
      v25 = 2274;
      v16 = L"Failed to get config path from os guid";
LABEL_24:
      UnattendLogW(
        2,
        L"WinReInstallTarget %s (0x%x) in file %S line %d",
        v16,
        PartitionList,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        v25);
      v7 = v26;
      goto LABEL_18;
    }
  }
  else
  {
    PartitionList = winreGetConfigFilePathFromWinDir(0, 0, v15, &v26);
    if ( PartitionList )
    {
      v25 = 2283;
      v16 = L"Failed to get config path";
      goto LABEL_24;
    }
  }
  v7 = v26;
  PartitionList = ReAgentConfig::Init((ReAgentConfig *)v27, v26, 1);
  if ( PartitionList )
  {
    v24 = 2286;
    v11 = L"failed to init agent config";
    goto LABEL_12;
  }
  ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v27);
  PartitionList = winreRemoveWIMDirFromPart(v33);
  if ( PartitionList )
  {
    v24 = 2292;
    v11 = L"winre RemoveWimDir from partition failed";
    goto LABEL_12;
  }
  UnattendLogW(0, L"Copying WinRE from %s to staging location on %s", a2, v36);
  PartitionList = winreCopyWIMFile(a1, (__int64)v33, a2);
  if ( PartitionList )
  {
    v24 = 2298;
    v11 = L"winreCopyWIMFile failed";
    goto LABEL_12;
  }
  PartitionList = winreRenameWIMDir(v33, v38);
  if ( PartitionList )
  {
    v24 = 2304;
    v11 = L"winre RenameWimDir failed";
    goto LABEL_12;
  }
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)ConfigInfo && *(_QWORD *)GUID_NULL.Data4 == *((_QWORD *)ConfigInfo + 1) )
  {
    UnattendLogW(0, L"No existing WinRe BCD. Creating BCD entry");
    RecoveryEntryInBCD = winreCreateRecoveryEntryInBCD((struct PartitionNode *)v33);
    PartitionList = RecoveryEntryInBCD;
    if ( RecoveryEntryInBCD )
    {
      UnattendLogW(0, L"Failed to create BCD recovery entry %d", RecoveryEntryInBCD);
      goto LABEL_18;
    }
    UnattendLogW(0, L"Set new Recovery guid as Recovery sequence of OS");
    PartitionList = winreSetRecoverySequence(&v32, *((unsigned int *)ConfigInfo + 1556), a1);
    if ( PartitionList )
    {
      v24 = 2331;
      v11 = L"failed to set new Recovery GUID as Recovery sequence";
      goto LABEL_12;
    }
    v19 = 1;
  }
  else
  {
    UnattendLogW(0, L"Update existing WinRE BCD");
    LogGuid(L"WinRE GUID", ConfigInfo);
    PartitionList = winreUpdateRecoveryEntryInBCD((struct PartitionNode *)v33);
    if ( PartitionList )
    {
      v24 = 2345;
      v11 = L"Failed to update Recovery BCD";
      goto LABEL_12;
    }
    v19 = 0;
  }
  UnattendLogW(0, L"Register to Recovery BCD");
  v20 = winreRegisterInRecoveryBCD((struct PartitionNode *)v33, a1);
  if ( v20 )
    UnattendLogW(2, L"Failed to register WinRE in recovery BCD, recovery button may be unavailable: 0x%x", v20);
  UnattendLogW(0, L"Updating reagent.xml");
  if ( *((_WORD *)ConfigInfo + 930) )
  {
    UnattendLogW(0, L"Verify ImageLocation");
    if ( !*((_WORD *)ConfigInfo + 628) )
    {
      UnattendLogW(0, L"ImageLocation path no longer valid, clear ImageLocation value");
      PartitionList = ReAgentConfig::SetImageLocationPath(
                        (ReAgentConfig *)v27,
                        0,
                        &ZeroGuid,
                        0,
                        (unsigned __int16 *)&Default);
      if ( PartitionList )
      {
        v24 = 2382;
        v11 = L"failed to clear ImageLocation path";
        goto LABEL_12;
      }
    }
  }
  UnattendLogW(0, L"Set WinRE location path to: %s", v38);
  PartitionList = ReAgentConfig::SetWinreLocationPath((ReAgentConfig *)v27, v37, &v35, v34, v38);
  if ( PartitionList )
  {
    v24 = 2392;
    v11 = L"Failed to set WinRE location";
    goto LABEL_12;
  }
  UnattendLogW(0, L"Set scheduled operation: WinReNoOperation");
  *(_DWORD *)(v30 + 5612) = 4;
  PartitionList = ReAgentXMLParser::CopyPathInfo(
                    v21,
                    (unsigned __int16 *)&qword_1800709D0,
                    (unsigned __int16 *)(v30 + 5616));
  if ( PartitionList )
  {
    v24 = 2397;
    v11 = L"Failed to set operation param";
    goto LABEL_12;
  }
  if ( v19 )
  {
    UnattendLogW(0, L"Set recovery guid");
    *(_OWORD *)v30 = v32;
  }
  UnattendLogW(0, L"Set install state to: enabled");
  *(_DWORD *)(v30 + 5588) = 1;
  *(_DWORD *)(v30 + 5604) = 0;
  PartitionList = ReAgentXMLParser::Update((ReAgentXMLParser *)v27);
  if ( PartitionList )
  {
    v24 = 2408;
    v11 = L"Failed to update config file";
    goto LABEL_12;
  }
  winreBackupRecoveryFile(v7, (ReAgentXMLParser *)v27, L"ReAgent.xml");
  v22 = pBackupRecoveryFile(a1, (struct ReAgentConfig *)v27);
  if ( v22 )
    UnattendLogW(2, L"Failed to backup recovery file: 0x%x", v22);
  UnattendLogW(0, L"Backup Setting file");
  v23 = winreBackupSettingFile(a1);
  PartitionList = v23;
  if ( v23 )
  {
    UnattendLogW(2, L"failed to backup setting file, error:0x%x", v23);
    PartitionList = 0;
  }
  v6 = 1;
LABEL_18:
  PrivateFreePartitionList(0);
  if ( v7 )
    CoTaskMemFree(v7);
  UnattendLogW(0, L"Exit WinReInstallTarget return value: %d, last error: 0x%x", v6, PartitionList);
  UnattendFinalizeLog();
  AsmInstallTragetWinREEnd(PartitionList, v13);
  TraceLoggingUnregister_EventUnregister();
  SetLastError(PartitionList);
  v27[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v27);
  return v6;
}

```

## disassembly

```asm
0x180019a90  mov     rax, rsp
0x180019a93  push    rbp
0x180019a94  push    rsi
0x180019a95  push    rdi
0x180019a96  push    r12
0x180019a98  push    r13
0x180019a9a  push    r14
0x180019a9c  push    r15
0x180019a9e  lea     rbp, [rax-788h]
0x180019aa5  sub     rsp, 850h
0x180019aac  mov     [rsp+880h+var_848], 0FFFFFFFFFFFFFFFEh
0x180019ab5  mov     [rax+20h], rbx
0x180019ab9  mov     rax, cs:__security_cookie
0x180019ac0  xor     rax, rsp
0x180019ac3  mov     [rbp+780h+var_40], rax
0x180019aca  mov     rsi, r8
0x180019acd  mov     r12, rdx
0x180019ad0  mov     r14, rcx
0x180019ad3  xor     ebx, ebx
0x180019ad5  mov     r13d, ebx
0x180019ad8  mov     [rsp+880h+var_850], rbx
0x180019add  xorps   xmm0, xmm0
0x180019ae0  movups  [rbp+780h+var_7E0], xmm0
0x180019ae4  mov     r15d, ebx
0x180019ae7  mov     [rsp+880h+var_840], rbx
0x180019aec  mov     [rsp+880h+var_828], rbx
0x180019af1  mov     qword ptr [rsp+880h+var_820], rbx
0x180019af6  mov     dword ptr [rsp+880h+var_818], ebx
0x180019afa  mov     dword ptr [rsp+880h+var_818+4], 2
0x180019b02  movdqa  xmmword ptr [rsp+880h+var_818+8], xmm0
0x180019b08  xorps   xmm1, xmm1
0x180019b0b  movdqa  [rbp+780h+var_800], xmm1
0x180019b10  mov     [rbp+780h+var_7F0], rbx
0x180019b14  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180019b1b  mov     [rsp+880h+var_830], rax
0x180019b20  mov     [rbp+780h+var_7E8], ebx
0x180019b23  xor     edx, edx; Val
0x180019b25  mov     r8d, 530h; Size
0x180019b2b  lea     rcx, [rbp+780h+var_7D0]; void *
0x180019b2f  call    memset_0
0x180019b34  xor     edx, edx; Val
0x180019b36  mov     r8d, 25Ch; Size
0x180019b3c  lea     rcx, [rbp+780h+var_2A0]; void *
0x180019b43  call    memset_0
0x180019b48  xor     ecx, ecx
0x180019b4a  call    UnattendInitializeLogEx2
0x180019b4f  call    TraceLoggingRegisterEx_EventRegister_2U
0x180019b54  lea     rax, aNull_0; "NULL"
0x180019b5b  mov     rdi, rsi
0x180019b5e  test    rsi, rsi
0x180019b61  cmovz   rdi, rax
0x180019b65  mov     rbx, r12
0x180019b68  test    r12, r12
0x180019b6b  cmovz   rbx, rax
0x180019b6f  mov     rdx, rdi; unsigned __int16 *
0x180019b72  mov     rcx, rbx; unsigned __int16 *
0x180019b75  call    ?AsmInstallTargetWinREStart@@YAXPEBG0@Z; AsmInstallTargetWinREStart(ushort const *,ushort const *)
0x180019b7a  lea     rdx, aEnterWinreinst; "Enter WinReInstallTarget"
0x180019b81  xor     ecx, ecx
0x180019b83  call    UnattendLogW
0x180019b88  mov     r9, rdi
0x180019b8b  mov     r8, rbx
0x180019b8e  lea     rdx, aParametersTarg; "Parameters: TargetWimPath: %s, VolumeNa"...
0x180019b95  xor     ecx, ecx
0x180019b97  call    UnattendLogW
0x180019b9c  mov     rdx, r14
0x180019b9f  lea     rcx, aTargetosguid_0; "TargetOSGuid"
0x180019ba6  call    LogGuid
0x180019bab  test    r12, r12
0x180019bae  jnz     short loc_180019BCB
0x180019bb0  lea     rdx, aTargetWinrePat; "Target WinRE path is NULL"
0x180019bb7  mov     ecx, 1
0x180019bbc  call    UnattendLogW
0x180019bc1  mov     ebx, 57h ; 'W'
0x180019bc6  jmp     loc_180019C68
0x180019bcb  test    rsi, rsi
0x180019bce  jnz     short loc_180019BD9
0x180019bd0  lea     rdx, aVolumeNameIsNu; "Volume name is NULL"
0x180019bd7  jmp     short loc_180019BB7
0x180019bd9  xor     ecx, ecx; pv
0x180019bdb  call    PrivateFreePartitionList
0x180019be0  lea     rdx, [rsp+880h+var_850]
0x180019be5  xor     ecx, ecx; struct _GUID *
0x180019be7  call    PrivateGetPartitionList
0x180019bec  mov     ebx, eax
0x180019bee  test    eax, eax
0x180019bf0  jz      short loc_180019C23
0x180019bf2  mov     dword ptr [rsp+880h+var_858], 8B4h
0x180019bfa  lea     r8, aFailedToGetPar; "failed to get partition list"
0x180019c01  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180019c08  mov     [rsp+880h+var_860], rax
0x180019c0d  mov     r9d, ebx
0x180019c10  lea     rdx, aWinreinstallta_0; "WinReInstallTarget %s (0x%x) in file %S"...
0x180019c17  mov     ecx, 2
0x180019c1c  call    UnattendLogW
0x180019c21  jmp     short loc_180019C68
0x180019c23  mov     rdi, [rsp+880h+var_850]
0x180019c28  mov     rcx, rdi
0x180019c2b  call    LogAllPartitionInfo
0x180019c30  mov     rbx, [rdi]
0x180019c33  jmp     short loc_180019C4D
0x180019c35  lea     rdx, [rbx+34h]; String2
0x180019c39  mov     rcx, rsi; String1
0x180019c3c  call    cs:__imp__wcsicmp
0x180019c42  test    eax, eax
0x180019c44  jz      loc_180019CEE
0x180019c4a  mov     rbx, [rbx]
0x180019c4d  cmp     rbx, rdi
0x180019c50  jnz     short loc_180019C35
0x180019c52  lea     rdx, aFailedToFindTh; "Failed to find the target volume"
0x180019c59  mov     ecx, 1
0x180019c5e  call    UnattendLogW
0x180019c63  mov     ebx, 490h
0x180019c68  xor     ecx, ecx; pv
0x180019c6a  call    PrivateFreePartitionList
0x180019c6f  test    r15, r15
0x180019c72  jz      short loc_180019C7D
0x180019c74  mov     rcx, r15; pv
0x180019c77  call    cs:__imp_CoTaskMemFree
0x180019c7d  mov     r9d, ebx
0x180019c80  mov     r8d, r13d
0x180019c83  lea     rdx, aExitWinreinsta; "Exit WinReInstallTarget return value: %"...
0x180019c8a  xor     ecx, ecx
0x180019c8c  call    UnattendLogW
0x180019c91  call    UnattendFinalizeLog
0x180019c96  mov     ecx, ebx; unsigned int
0x180019c98  call    ?AsmInstallTragetWinREEnd@@YAXK@Z; AsmInstallTragetWinREEnd(ulong)
0x180019c9d  call    TraceLoggingUnregister_EventUnregister
0x180019ca2  mov     ecx, ebx; dwErrCode
0x180019ca4  call    cs:__imp_SetLastError
0x180019caa  nop
0x180019cab  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180019cb2  mov     [rsp+880h+var_830], rax
0x180019cb7  lea     rcx, [rsp+880h+var_830]; this
0x180019cbc  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x180019cc1  mov     eax, r13d
0x180019cc4  mov     rcx, [rbp+780h+var_40]
0x180019ccb  xor     rcx, rsp; StackCookie
0x180019cce  call    __security_check_cookie
0x180019cd3  mov     rbx, [rsp+880h+arg_18]
0x180019cdb  add     rsp, 850h
0x180019ce2  pop     r15
0x180019ce4  pop     r14
0x180019ce6  pop     r13
0x180019ce8  pop     r12
0x180019cea  pop     rdi
0x180019ceb  pop     rsi
0x180019cec  pop     rbp
0x180019ced  retn
0x180019cee  lea     rcx, [rbp+780h+var_7D0]; void *
0x180019cf2  mov     rdx, rbx; Src
0x180019cf5  mov     r8d, 530h; Size
0x180019cfb  call    memcpy_0
0x180019d00  lea     rdx, aFindTargetPart; "Find target partition"
0x180019d07  xor     ecx, ecx
0x180019d09  call    UnattendLogW
0x180019d0e  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x180019d15  xor     ecx, ecx
0x180019d17  call    UnattendLogW
0x180019d1c  mov     edi, 1
0x180019d21  mov     [rbp+780h+var_7E8], edi
0x180019d24  test    r14, r14
0x180019d27  jz      short loc_180019D75
0x180019d29  lea     r8, [rsp+880h+var_840]
0x180019d2e  mov     rcx, r14
0x180019d31  call    winreGetConfigFilePathFromOsGuid
0x180019d36  mov     ebx, eax
0x180019d38  test    eax, eax
0x180019d3a  jz      short loc_180019D9A
0x180019d3c  mov     dword ptr [rsp+880h+var_858], 8E2h
0x180019d44  lea     r8, aFailedToGetCon_2; "Failed to get config path from os guid"
0x180019d4b  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180019d52  mov     r9d, ebx
0x180019d55  mov     [rsp+880h+var_860], rax
0x180019d5a  lea     rdx, aWinreinstallta_0; "WinReInstallTarget %s (0x%x) in file %S"...
0x180019d61  mov     ecx, 2
0x180019d66  call    UnattendLogW
0x180019d6b  mov     r15, [rsp+880h+var_840]
0x180019d70  jmp     loc_180019C68
0x180019d75  lea     r9, [rsp+880h+var_840]
0x180019d7a  xor     edx, edx
0x180019d7c  xor     ecx, ecx
0x180019d7e  call    winreGetConfigFilePathFromWinDir
0x180019d83  mov     ebx, eax
0x180019d85  test    eax, eax
0x180019d87  jz      short loc_180019D9A
0x180019d89  mov     dword ptr [rsp+880h+var_858], 8EBh
0x180019d91  lea     r8, aFailedToGetCon_1; "Failed to get config path"
0x180019d98  jmp     short loc_180019D4B
0x180019d9a  mov     r8d, edi; int
0x180019d9d  mov     r15, [rsp+880h+var_840]
0x180019da2  mov     rdx, r15; unsigned __int16 *
0x180019da5  lea     rcx, [rsp+880h+var_830]; this
0x180019daa  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180019daf  mov     ebx, eax
0x180019db1  test    eax, eax
0x180019db3  jz      short loc_180019DC9
0x180019db5  mov     dword ptr [rsp+880h+var_858], 8EEh
0x180019dbd  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x180019dc4  jmp     loc_180019C01
0x180019dc9  lea     rcx, [rsp+880h+var_830]; this
0x180019dce  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180019dd3  mov     rsi, rax
0x180019dd6  lea     rcx, [rbp+780h+var_7D0]
0x180019dda  call    winreRemoveWIMDirFromPart
0x180019ddf  mov     ebx, eax
0x180019de1  test    eax, eax
0x180019de3  jz      short loc_180019DF9
0x180019de5  mov     dword ptr [rsp+880h+var_858], 8F4h
0x180019ded  lea     r8, aWinreRemovewim; "winre RemoveWimDir from partition faile"...
0x180019df4  jmp     loc_180019C01
0x180019df9  lea     r9, [rbp+780h+var_540]
0x180019e00  mov     r8, r12
0x180019e03  lea     rdx, aCopyingWinreFr; "Copying WinRE from %s to staging locati"...
0x180019e0a  xor     ecx, ecx
0x180019e0c  call    UnattendLogW
0x180019e11  mov     r8, r12
0x180019e14  lea     rdx, [rbp+780h+var_7D0]
0x180019e18  mov     rcx, r14
0x180019e1b  call    winreCopyWIMFile
0x180019e20  mov     ebx, eax
0x180019e22  test    eax, eax
0x180019e24  jz      short loc_180019E3A
0x180019e26  mov     dword ptr [rsp+880h+var_858], 8FAh
0x180019e2e  lea     r8, aWinrecopywimfi_1; "winreCopyWIMFile failed"
0x180019e35  jmp     loc_180019C01
0x180019e3a  lea     rdx, [rbp+780h+var_2A0]
0x180019e41  lea     rcx, [rbp+780h+var_7D0]
0x180019e45  call    winreRenameWIMDir
0x180019e4a  mov     ebx, eax
0x180019e4c  test    eax, eax
0x180019e4e  jz      short loc_180019E64
0x180019e50  mov     dword ptr [rsp+880h+var_858], 900h
0x180019e58  lea     r8, aWinreRenamewim; "winre RenameWimDir failed"
0x180019e5f  jmp     loc_180019C01
0x180019e64  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180019e6b  cmp     rax, [rsi]
0x180019e6e  jnz     loc_180019EF8
0x180019e74  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180019e7b  cmp     rax, [rsi+8]
0x180019e7f  jnz     short loc_180019EF8
0x180019e81  lea     rdx, aNoExistingWinr; "No existing WinRe BCD. Creating BCD ent"...
0x180019e88  xor     ecx, ecx
0x180019e8a  call    UnattendLogW
0x180019e8f  mov     r8, r14
0x180019e92  lea     rdx, [rbp+780h+var_7E0]
0x180019e96  lea     rcx, [rbp+780h+var_7D0]; struct PartitionNode *
0x180019e9a  call    winreCreateRecoveryEntryInBCD
0x180019e9f  mov     ebx, eax
0x180019ea1  xor     ecx, ecx
0x180019ea3  test    eax, eax
0x180019ea5  jz      short loc_180019EBB
0x180019ea7  mov     r8d, eax
0x180019eaa  lea     rdx, aFailedToCreate_22; "Failed to create BCD recovery entry %d"
0x180019eb1  call    UnattendLogW
0x180019eb6  jmp     loc_180019C68
0x180019ebb  lea     rdx, aSetNewRecovery; "Set new Recovery guid as Recovery seque"...
0x180019ec2  call    UnattendLogW
0x180019ec7  mov     r8, r14
0x180019eca  mov     edx, [rsi+1850h]
0x180019ed0  lea     rcx, [rbp+780h+var_7E0]
0x180019ed4  call    winreSetRecoverySequence
0x180019ed9  mov     ebx, eax
0x180019edb  test    eax, eax
0x180019edd  jz      short loc_180019EF3
0x180019edf  mov     dword ptr [rsp+880h+var_858], 91Bh
0x180019ee7  lea     r8, aFailedToSetNew; "failed to set new Recovery GUID as Reco"...
0x180019eee  jmp     loc_180019C01
0x180019ef3  mov     r12d, edi
0x180019ef6  jmp     short loc_180019F3E
0x180019ef8  lea     rdx, aUpdateExisting; "Update existing WinRE BCD"
0x180019eff  xor     ecx, ecx
0x180019f01  call    UnattendLogW
0x180019f06  mov     rdx, rsi
0x180019f09  lea     rcx, aWinreGuid; "WinRE GUID"
0x180019f10  call    LogGuid
0x180019f15  mov     rdx, rsi
0x180019f18  lea     rcx, [rbp+780h+var_7D0]; struct PartitionNode *
0x180019f1c  call    winreUpdateRecoveryEntryInBCD
0x180019f21  mov     ebx, eax
0x180019f23  test    eax, eax
0x180019f25  jz      short loc_180019F3B
0x180019f27  mov     dword ptr [rsp+880h+var_858], 929h
0x180019f2f  lea     r8, aFailedToUpdate_0; "Failed to update Recovery BCD"
0x180019f36  jmp     loc_180019C01
0x180019f3b  xor     r12d, r12d
0x180019f3e  lea     rdx, aRegisterToReco; "Register to Recovery BCD"
0x180019f45  xor     ecx, ecx
0x180019f47  call    UnattendLogW
0x180019f4c  mov     rdx, r14; struct _GUID *
0x180019f4f  lea     rcx, [rbp+780h+var_7D0]; struct PartitionNode *
0x180019f53  call    winreRegisterInRecoveryBCD
0x180019f58  test    eax, eax
0x180019f5a  jz      short loc_180019F70
0x180019f5c  mov     r8d, eax
0x180019f5f  lea     rdx, aFailedToRegist_0; "Failed to register WinRE in recovery BC"...
0x180019f66  mov     ecx, 2
0x180019f6b  call    UnattendLogW
0x180019f70  lea     rdx, aUpdatingReagen; "Updating reagent.xml"
0x180019f77  xor     ecx, ecx
  ... truncated ...
```
