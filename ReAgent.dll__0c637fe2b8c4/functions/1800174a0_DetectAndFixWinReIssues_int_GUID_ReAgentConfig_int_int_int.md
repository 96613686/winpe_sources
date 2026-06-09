# DetectAndFixWinReIssues(int,_GUID *,ReAgentConfig *,int *,int *,int *)

- ea: `0x1800174a0`
- end: `0x1800178c7`
- name: `?DetectAndFixWinReIssues@@YAKHPEAU_GUID@@PEAVReAgentConfig@@PEAH22@Z`
- size: `1063`
- prototype: `__int64 __fastcall(int, struct _GUID *, struct ReAgentConfig *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x1800193e8`

## callees

- `0x1800059fc`
- `0x180006fc8`
- `0x18000702c`
- `0x180010010`
- `0x180011974`
- `0x1800145f4`
- `0x180014754`
- `0x1800174a0`
- `0x180018838`
- `0x18001fd7c`
- `0x180034aa4`
- `0x180035300`
- `0x180035e88`
- `0x18003a248`
- `0x18005cee2`
- `0x18005cf30`

## string_xrefs

- `0x18001760f`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x18001752c`: `DetectAndFixWinReIssues (WinRE)WinRE is already installed, setting BCD entry (winre location %s)`
- `0x18001757b`: `DetectAndFixWinReIssues Current Recovery Sequence is already set as the BCD id of WinRE.`
- `0x1800175d6`: `DetectAndFixWinReIssues BCD could not be set, uninstalling WinRE`
- `0x180017603`: `failed to uninstall`
- `0x1800176f0`: `Create Recovery BCD entry issue successfully.`
- `0x180017719`: `Updated winre GUID in reagent xml file and fixed missing Recovery BCD entry issue successfully!!!`
- `0x180017783`: `Failed to set Recovery Sequence for created Recovery BCD entry.`
- `0x18001778c`: `Failed to update winre GUID in Reagent xml file.`
- `0x180017795`: `Failed to create recovery BCD entry, will continue.`
- `0x1800177a5`: `Failed to convert directory name to offset, will continue.`
- `0x1800177c0`: `NOTE: WILL RETRY. We have to uninstall WinRE and retry because WinRE is installed but its BCD entry is not present.`
- `0x1800177e3`: `DetectAndFixWinReIssues Copying Winre.wim from %s to staging location`
- `0x180017836`: `Failed to update config file`
- `0x180017844`: `DetectAndFixWinReIssues Uninstalling corrupt WinRE installation.`
- `0x180017865`: `DetectAndFixWinReIssues WinRE uninstall did not succeed`
- `0x180017890`: `Agent config update failed`
- `0x1800178ae`: `DetectAndFixWinReIssues we should retry because winre installation was changed.`

## pseudocode

```c
__int64 __fastcall DetectAndFixWinReIssues(
        int a1,
        struct _GUID *a2,
        struct ReAgentConfig *a3,
        int *a4,
        int *a5,
        int *a6)
{
  unsigned int RecoveryEntryInBCD; // ebx
  struct ReAgentConfigInfo *ConfigInfo; // r14
  const wchar_t *v11; // r15
  GUID *v12; // rcx
  int WinReGuid; // ecx
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  const wchar_t *v16; // r8
  ReAgentXMLParser *v18; // rcx
  ReAgentXMLParser *v19; // rcx
  int v20; // [rsp+28h] [rbp-D8h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[1328]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[608]; // [rsp+580h] [rbp+480h] BYREF
  wchar_t pszDest[304]; // [rsp+7E0h] [rbp+6E0h] BYREF

  RecoveryEntryInBCD = 0;
  *a5 = 0;
  ConfigInfo = ReAgentXMLParser::GetConfigInfo(a3);
  v11 = (const wchar_t *)((char *)ConfigInfo + 16);
  if ( !*((_DWORD *)ConfigInfo + 1397) && !*v11 )
  {
    UnattendLogW(0, L"DetectAndFixWinReIssues nothing to do because winre is not enabled.");
    return RecoveryEntryInBCD;
  }
  if ( a1 )
    return RecoveryEntryInBCD;
  UnattendLogW(
    0,
    L"DetectAndFixWinReIssues (WinRE)WinRE is already installed, setting BCD entry (winre location %s)",
    v11);
  v12 = a2;
  if ( !a2 )
    v12 = &GUID_CURRENT_BOOT_ENTRY;
  v22 = 0;
  WinReGuid = winreGetWinReGuid(v12, &v22);
  if ( !WinReGuid )
  {
    v14 = v22 - *(_QWORD *)ConfigInfo;
    if ( (_QWORD)v22 == *(_QWORD *)ConfigInfo )
      v14 = *((_QWORD *)&v22 + 1) - *((_QWORD *)ConfigInfo + 1);
    if ( !v14 )
    {
      UnattendLogW(0, L"DetectAndFixWinReIssues Current Recovery Sequence is already set as the BCD id of WinRE.");
LABEL_29:
      *a5 = 1;
      return RecoveryEntryInBCD;
    }
  }
  v15 = L"DetectAndFixWinReIssues Failed to get WinRE GUID.";
  if ( !WinReGuid )
    v15 = L"DetectAndFixWinReIssues Get different WinRE GUID.";
  UnattendLogW(0, v15);
  UnattendLogW(0, L"DetectAndFixWinReIssues Will fix the BCD entry.");
  RecoveryEntryInBCD = winreSetRecoverySequence(ConfigInfo, *((unsigned int *)ConfigInfo + 1556), a2);
  if ( RecoveryEntryInBCD )
  {
    if ( *((_DWORD *)ConfigInfo + 1397) )
    {
      UnattendLogW(0, L"DetectAndFixWinReIssues BCD could not be set, uninstalling WinRE");
      RecoveryEntryInBCD = winreUnInstallInternal(a2, 0, 0);
      if ( RecoveryEntryInBCD )
      {
        v20 = 271;
        v16 = L"failed to uninstall";
LABEL_18:
        UnattendLogW(
          2,
          L"DetectAndFixWinReIssues %s (0x%x) in file %S line %d",
          v16,
          RecoveryEntryInBCD,
          "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
          v20);
        return RecoveryEntryInBCD;
      }
    }
    return RecoveryEntryInBCD;
  }
  if ( a2 )
  {
    RecoveryEntryInBCD = winreGetWinReGuid(a2, &v22);
    if ( RecoveryEntryInBCD == 2 )
    {
      if ( *v11 )
      {
        memset_0(v23, 0, sizeof(v23));
        if ( (unsigned int)WdsGetParentPath(v11, pszDest, 0x12Eu) )
        {
          if ( (unsigned int)WdsGetFileName(v11, v24) )
          {
            RecoveryEntryInBCD = winreConvertDirNameToOffset(pszDest, 0);
            if ( RecoveryEntryInBCD )
            {
              UnattendLogW(2, L"Failed to convert directory name to offset, will continue.");
            }
            else
            {
              RecoveryEntryInBCD = winreCreateRecoveryEntryInBCD((struct PartitionNode *)v23);
              if ( RecoveryEntryInBCD )
              {
                UnattendLogW(2, L"Failed to create recovery BCD entry, will continue.");
              }
              else
              {
                UnattendLogW(0, L"Create Recovery BCD entry issue successfully.");
                *(_OWORD *)*((_QWORD *)a3 + 8) = v22;
                RecoveryEntryInBCD = ReAgentXMLParser::Update(a3);
                if ( RecoveryEntryInBCD )
                {
                  UnattendLogW(2, L"Failed to update winre GUID in Reagent xml file.");
                }
                else
                {
                  UnattendLogW(
                    0,
                    L"Updated winre GUID in reagent xml file and fixed missing Recovery BCD entry issue successfully!!!");
                  RecoveryEntryInBCD = winreSetRecoverySequence(&v22, *((unsigned int *)ConfigInfo + 1556), a2);
                  if ( !RecoveryEntryInBCD )
                  {
                    UnattendLogW(0, L"Recovery Sequence is set.");
                    goto LABEL_29;
                  }
                  UnattendLogW(2, L"Failed to set Recovery Sequence for created Recovery BCD entry.");
                }
              }
            }
          }
        }
      }
      goto LABEL_37;
    }
  }
  else
  {
    RecoveryEntryInBCD = winreGetWinReGuid(&GUID_CURRENT_BOOT_ENTRY, &v22);
  }
  if ( !RecoveryEntryInBCD )
    goto LABEL_29;
LABEL_37:
  UnattendLogW(
    0,
    L"NOTE: WILL RETRY. We have to uninstall WinRE and retry because WinRE is installed but its BCD entry is not present.");
  if ( *((_DWORD *)ConfigInfo + 1397) || !*v11 )
  {
    UnattendLogW(0, L"DetectAndFixWinReIssues Uninstalling corrupt WinRE installation.");
    if ( winreUnInstallInternal(a2, 1, 0) )
    {
      UnattendLogW(0, L"DetectAndFixWinReIssues WinRE uninstall did not succeed");
      ReAgentConfig::SetInstallState(a3, 0);
      RecoveryEntryInBCD = ReAgentXMLParser::Update(v19);
      if ( RecoveryEntryInBCD )
      {
        v20 = 365;
        v16 = L"Agent config update failed";
        goto LABEL_18;
      }
    }
  }
  else
  {
    UnattendLogW(0, L"DetectAndFixWinReIssues Copying Winre.wim from %s to staging location", v11);
    winreCopyWIMBack(a2, ConfigInfo);
    ReAgentConfig::SetWinreLocationPath(a3, 0, &ZeroGuid, 0, 0);
    ReAgentConfig::SetInstallState(a3, 0);
    RecoveryEntryInBCD = ReAgentXMLParser::Update(v18);
    if ( RecoveryEntryInBCD )
    {
      v20 = 354;
      v16 = L"Failed to update config file";
      goto LABEL_18;
    }
  }
  if ( a4 )
    *a4 = 1;
  *a6 = 1;
  UnattendLogW(0, L"DetectAndFixWinReIssues we should retry because winre installation was changed.");
  return RecoveryEntryInBCD;
}

```

## disassembly

```asm
0x1800174a0  mov     [rsp-8+arg_0], rbx
0x1800174a5  push    rbp
0x1800174a6  push    rsi
0x1800174a7  push    rdi
0x1800174a8  push    r12
0x1800174aa  push    r13
0x1800174ac  push    r14
0x1800174ae  push    r15
0x1800174b0  lea     rbp, [rsp-950h]
0x1800174b8  sub     rsp, 0A50h
0x1800174bf  mov     rax, cs:__security_cookie
0x1800174c6  xor     rax, rsp
0x1800174c9  mov     [rbp+980h+var_40], rax
0x1800174d0  mov     rax, [rbp+980h+arg_28]
0x1800174d7  mov     edi, ecx
0x1800174d9  mov     r12, [rbp+980h+arg_20]
0x1800174e0  xor     ebx, ebx
0x1800174e2  mov     rcx, r8; this
0x1800174e5  mov     [rsp+0A80h+var_A50], r9
0x1800174ea  mov     r13, r8
0x1800174ed  mov     [rsp+0A80h+var_A48], rax
0x1800174f2  mov     rsi, rdx
0x1800174f5  mov     [r12], ebx
0x1800174f9  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x1800174fe  mov     r14, rax
0x180017501  lea     r15, [rax+10h]
0x180017505  cmp     [rax+15D4h], ebx
0x18001750b  jnz     short loc_180017521
0x18001750d  xor     eax, eax
0x18001750f  cmp     ax, [r15]
0x180017513  jnz     short loc_180017521
0x180017515  lea     rdx, aDetectandfixwi_5; "DetectAndFixWinReIssues nothing to do b"...
0x18001751c  jmp     loc_1800178BB
0x180017521  test    edi, edi
0x180017523  jnz     loc_180017757
0x180017529  mov     r8, r15
0x18001752c  lea     rdx, aDetectandfixwi; "DetectAndFixWinReIssues (WinRE)WinRE is"...
0x180017533  xor     ecx, ecx
0x180017535  call    UnattendLogW
0x18001753a  lea     rax, GUID_CURRENT_BOOT_ENTRY
0x180017541  xorps   xmm0, xmm0
0x180017544  test    rsi, rsi
0x180017547  lea     rdx, [rsp+0A80h+var_A40]
0x18001754c  mov     rcx, rsi
0x18001754f  cmovz   rcx, rax
0x180017553  movups  [rsp+0A80h+var_A40], xmm0
0x180017558  call    winreGetWinReGuid
0x18001755d  mov     ecx, eax
0x18001755f  test    eax, eax
0x180017561  jnz     short loc_180017587
0x180017563  mov     rax, qword ptr [rsp+0A80h+var_A40]
0x180017568  sub     rax, [r14]
0x18001756b  jnz     short loc_180017576
0x18001756d  mov     rax, qword ptr [rsp+0A80h+var_A40+8]
0x180017572  sub     rax, [r14+8]
0x180017576  test    rax, rax
0x180017579  jnz     short loc_180017587
0x18001757b  lea     rdx, aDetectandfixwi_8; "DetectAndFixWinReIssues Current Recover"...
0x180017582  jmp     loc_180017748
0x180017587  test    ecx, ecx
0x180017589  lea     rax, aDetectandfixwi_1; "DetectAndFixWinReIssues Get different W"...
0x180017590  lea     rdx, aDetectandfixwi_2; "DetectAndFixWinReIssues Failed to get W"...
0x180017597  cmovz   rdx, rax
0x18001759b  xor     ecx, ecx
0x18001759d  call    UnattendLogW
0x1800175a2  lea     rdx, aDetectandfixwi_4; "DetectAndFixWinReIssues Will fix the BC"...
0x1800175a9  xor     ecx, ecx
0x1800175ab  call    UnattendLogW
0x1800175b0  mov     edx, [r14+1850h]
0x1800175b7  mov     r8, rsi
0x1800175ba  mov     rcx, r14
0x1800175bd  call    winreSetRecoverySequence
0x1800175c2  mov     ebx, eax
0x1800175c4  test    eax, eax
0x1800175c6  jz      short loc_18001762F
0x1800175c8  cmp     dword ptr [r14+15D4h], 0
0x1800175d0  jz      loc_180017757
0x1800175d6  lea     rdx, aDetectandfixwi_6; "DetectAndFixWinReIssues BCD could not b"...
0x1800175dd  xor     ecx, ecx
0x1800175df  call    UnattendLogW
0x1800175e4  xor     r8d, r8d; int
0x1800175e7  xor     edx, edx; int
0x1800175e9  mov     rcx, rsi; struct _GUID *
0x1800175ec  call    ?winreUnInstallInternal@@YAKPEAU_GUID@@HH@Z; winreUnInstallInternal(_GUID *,int,int)
0x1800175f1  mov     ebx, eax
0x1800175f3  test    eax, eax
0x1800175f5  jz      loc_180017757
0x1800175fb  mov     [rsp+0A80h+var_A58], 10Fh
0x180017603  lea     r8, aFailedToUninst; "failed to uninstall"
0x18001760a  mov     ecx, 2
0x18001760f  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180017616  mov     r9d, ebx
0x180017619  lea     rdx, aDetectandfixwi_3; "DetectAndFixWinReIssues %s (0x%x) in fi"...
0x180017620  mov     [rsp+0A80h+var_A60], rax
0x180017625  call    UnattendLogW
0x18001762a  jmp     loc_180017757
0x18001762f  lea     rdx, [rsp+0A80h+var_A40]
0x180017634  mov     edi, 2
0x180017639  test    rsi, rsi
0x18001763c  jz      loc_1800177AE
0x180017642  mov     rcx, rsi
0x180017645  call    winreGetWinReGuid
0x18001764a  mov     ebx, eax
0x18001764c  cmp     eax, edi
0x18001764e  jnz     loc_1800177BC
0x180017654  xor     eax, eax
0x180017656  cmp     ax, [r15]
0x18001765a  jz      loc_1800177C0
0x180017660  xor     edx, edx; Val
0x180017662  lea     rcx, [rsp+0A80h+var_A30]; void *
0x180017667  mov     r8d, 530h; Size
0x18001766d  call    memset_0
0x180017672  mov     r8d, 12Eh; cchDest
0x180017678  lea     rdx, [rbp+980h+pszDest]; pszDest
0x18001767f  mov     rcx, r15; pszSrc
0x180017682  call    WdsGetParentPath
0x180017687  test    eax, eax
0x180017689  jz      loc_1800177C0
0x18001768f  lea     rdx, [rbp+980h+var_500]
0x180017696  mov     rcx, r15
0x180017699  call    WdsGetFileName
0x18001769e  test    eax, eax
0x1800176a0  jz      loc_1800177C0
0x1800176a6  xor     r9d, r9d
0x1800176a9  mov     [rsp+0A80h+var_A60], 0; __int64
0x1800176b2  lea     r8, [rsp+0A80h+var_A30]
0x1800176b7  lea     rdx, [rbp+980h+var_500]
0x1800176be  lea     rcx, [rbp+980h+pszDest]; lpszFileName
0x1800176c5  call    winreConvertDirNameToOffset
0x1800176ca  mov     ebx, eax
0x1800176cc  test    eax, eax
0x1800176ce  jnz     loc_1800177A5
0x1800176d4  mov     r8, rsi
0x1800176d7  lea     rdx, [rsp+0A80h+var_A40]
0x1800176dc  lea     rcx, [rsp+0A80h+var_A30]; struct PartitionNode *
0x1800176e1  call    winreCreateRecoveryEntryInBCD
0x1800176e6  mov     ebx, eax
0x1800176e8  test    eax, eax
0x1800176ea  jnz     loc_180017795
0x1800176f0  lea     rdx, aCreateRecovery; "Create Recovery BCD entry issue success"...
0x1800176f7  xor     ecx, ecx
0x1800176f9  call    UnattendLogW
0x1800176fe  mov     rax, [r13+40h]
0x180017702  mov     rcx, r13; this
0x180017705  movups  xmm0, [rsp+0A80h+var_A40]
0x18001770a  movdqu  xmmword ptr [rax], xmm0
0x18001770e  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180017713  mov     ebx, eax
0x180017715  test    eax, eax
0x180017717  jnz     short loc_18001778C
0x180017719  lea     rdx, aUpdatedWinreGu; "Updated winre GUID in reagent xml file "...
0x180017720  xor     ecx, ecx
0x180017722  call    UnattendLogW
0x180017727  mov     edx, [r14+1850h]
0x18001772e  lea     rcx, [rsp+0A80h+var_A40]
0x180017733  mov     r8, rsi
0x180017736  call    winreSetRecoverySequence
0x18001773b  mov     ebx, eax
0x18001773d  test    eax, eax
0x18001773f  jnz     short loc_180017783
0x180017741  lea     rdx, aRecoverySequen; "Recovery Sequence is set."
0x180017748  xor     ecx, ecx
0x18001774a  call    UnattendLogW
0x18001774f  mov     dword ptr [r12], 1
0x180017757  mov     eax, ebx
0x180017759  mov     rcx, [rbp+980h+var_40]
0x180017760  xor     rcx, rsp; StackCookie
0x180017763  call    __security_check_cookie
0x180017768  mov     rbx, [rsp+0A80h+arg_0]
0x180017770  add     rsp, 0A50h
0x180017777  pop     r15
0x180017779  pop     r14
0x18001777b  pop     r13
0x18001777d  pop     r12
0x18001777f  pop     rdi
0x180017780  pop     rsi
0x180017781  pop     rbp
0x180017782  retn
0x180017783  lea     rdx, aFailedToSetRec_0; "Failed to set Recovery Sequence for cre"...
0x18001778a  jmp     short loc_18001779C
0x18001778c  lea     rdx, aFailedToUpdate_9; "Failed to update winre GUID in Reagent "...
0x180017793  jmp     short loc_18001779C
0x180017795  lea     rdx, aFailedToCreate_15; "Failed to create recovery BCD entry, wi"...
0x18001779c  mov     ecx, edi
0x18001779e  call    UnattendLogW
0x1800177a3  jmp     short loc_1800177C0
0x1800177a5  lea     rdx, aFailedToConver_6; "Failed to convert directory name to off"...
0x1800177ac  jmp     short loc_18001779C
0x1800177ae  lea     rcx, GUID_CURRENT_BOOT_ENTRY
0x1800177b5  call    winreGetWinReGuid
0x1800177ba  mov     ebx, eax
0x1800177bc  test    ebx, ebx
0x1800177be  jz      short loc_18001774F
0x1800177c0  lea     rdx, aNoteWillRetryW; "NOTE: WILL RETRY. We have to uninstall "...
0x1800177c7  xor     ecx, ecx
0x1800177c9  call    UnattendLogW
0x1800177ce  cmp     dword ptr [r14+15D4h], 0
0x1800177d6  jnz     short loc_180017844
0x1800177d8  xor     eax, eax
0x1800177da  cmp     ax, [r15]
0x1800177de  jz      short loc_180017844
0x1800177e0  mov     r8, r15
0x1800177e3  lea     rdx, aDetectandfixwi_0; "DetectAndFixWinReIssues Copying Winre.w"...
0x1800177ea  xor     ecx, ecx
0x1800177ec  call    UnattendLogW
0x1800177f1  mov     rdx, r14
0x1800177f4  mov     rcx, rsi
0x1800177f7  call    winreCopyWIMBack
0x1800177fc  xor     r9d, r9d; unsigned int
0x1800177ff  mov     [rsp+0A80h+var_A60], 0; unsigned __int16 *
0x180017808  lea     r8, ZeroGuid; struct _GUID *
0x18001780f  xor     edx, edx; unsigned __int64
0x180017811  mov     rcx, r13; this
0x180017814  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x180017819  xor     edx, edx; int
0x18001781b  mov     rcx, r13; this
0x18001781e  call    ?SetInstallState@ReAgentConfig@@QEAAXH@Z; ReAgentConfig::SetInstallState(int)
0x180017823  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180017828  mov     ebx, eax
0x18001782a  test    eax, eax
0x18001782c  jz      short loc_180017899
0x18001782e  mov     [rsp+0A80h+var_A58], 162h
0x180017836  lea     r8, aFailedToUpdate_6; "Failed to update config file"
0x18001783d  mov     ecx, edi
0x18001783f  jmp     loc_18001760F
0x180017844  lea     rdx, aDetectandfixwi_9; "DetectAndFixWinReIssues Uninstalling co"...
0x18001784b  xor     ecx, ecx
0x18001784d  call    UnattendLogW
0x180017852  xor     r8d, r8d; int
0x180017855  mov     rcx, rsi; struct _GUID *
0x180017858  lea     edx, [r8+1]; int
0x18001785c  call    ?winreUnInstallInternal@@YAKPEAU_GUID@@HH@Z; winreUnInstallInternal(_GUID *,int,int)
0x180017861  test    eax, eax
0x180017863  jz      short loc_180017899
0x180017865  lea     rdx, aDetectandfixwi_7; "DetectAndFixWinReIssues WinRE uninstall"...
0x18001786c  xor     ecx, ecx
0x18001786e  call    UnattendLogW
0x180017873  xor     edx, edx; int
0x180017875  mov     rcx, r13; this
0x180017878  call    ?SetInstallState@ReAgentConfig@@QEAAXH@Z; ReAgentConfig::SetInstallState(int)
0x18001787d  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180017882  mov     ebx, eax
0x180017884  test    eax, eax
0x180017886  jz      short loc_180017899
0x180017888  mov     [rsp+0A80h+var_A58], 16Dh
0x180017890  lea     r8, aAgentConfigUpd; "Agent config update failed"
0x180017897  jmp     short loc_18001783D
0x180017899  mov     rax, [rsp+0A80h+var_A50]
0x18001789e  test    rax, rax
0x1800178a1  jz      short loc_1800178A9
0x1800178a3  mov     dword ptr [rax], 1
0x1800178a9  mov     rax, [rsp+0A80h+var_A48]
0x1800178ae  lea     rdx, aDetectandfixwi_10; "DetectAndFixWinReIssues we should retry"...
0x1800178b5  mov     dword ptr [rax], 1
0x1800178bb  xor     ecx, ecx
0x1800178bd  call    UnattendLogW
0x1800178c2  jmp     loc_180017757
```
