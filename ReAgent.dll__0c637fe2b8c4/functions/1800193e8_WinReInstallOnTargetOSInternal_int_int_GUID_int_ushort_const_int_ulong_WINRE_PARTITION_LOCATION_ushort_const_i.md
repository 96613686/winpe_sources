# WinReInstallOnTargetOSInternal(int,int *,_GUID *,int,ushort const *,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,int *,PartitionNode *)

- ea: `0x1800193e8`
- end: `0x180019a89`
- name: `?WinReInstallOnTargetOSInternal@@YAKHPEAHPEAU_GUID@@HPEBGHKW4_WINRE_PARTITION_LOCATION@@20PEAUPartitionNode@@@Z`
- size: `1697`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019180`
- `0x18001a700`
- `0x18001a7c0`
- `0x18001a8d0`
- `0x18001aa00`
- `0x18001ab30`
- `0x180024800`
- `0x180024ff0`

## callees

- `0x18000196c`
- `0x180001adc`
- `0x180002786`
- `0x1800059fc`
- `0x18000edec`
- `0x18000ee80`
- `0x180011974`
- `0x1800170a4`
- `0x180017248`
- `0x1800174a0`
- `0x180017960`
- `0x180017ec4`
- `0x1800180f8`
- `0x180018870`
- `0x1800193e8`
- `0x180029074`
- `0x180030df0`
- `0x180030fcc`
- `0x1800310a0`
- `0x18003207c`
- `0x1800321a0`
- `0x18003559c`
- `0x18003cf28`
- `0x18003ddb0`
- `0x18003dee8`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`
- `0x18005f010`

## string_xrefs

- `0x1800194e3`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019562`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019922`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019506`: `WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d`
- `0x18001956c`: `WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d`
- `0x180019943`: `WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d`
- `0x180019519`: `--Install on target OS step 1: collect info like partition list, loading reagent.xml, source winre.wim and partition`
- `0x1800195a8`: `failed to get downlevel reagent config`
- `0x180019939`: `failed to get reagent config`
- `0x180019697`: `--Install on target OS step 2: detect and fix if there is any issue for winre settings`
- `0x1800198fe`: `Current WinRE is ready. No need to make any further changes`
- `0x180019703`: `--Install on target OS step 3: check if we can keep winre.wim in the same partition if it is staged.`
- `0x18001977a`: `--Install on target OS step 4: check if we can put winre.wim in other partitions or create one if needed.`
- `0x1800195c8`: `--Install on target OS step 5: set WinRE settings and restore system to a good state when hitting any errors`
- `0x1800198ad`: `WinReInstallOnTargetOSInternal WinRE installation completed successfully.`
- `0x180019a08`: `Not installing for running OS; skipped storing disk info in NVRAM`

## pseudocode

```c
__int64 __fastcall WinReInstallOnTargetOSInternal(
        int a1,
        int *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        _DWORD *a10,
        void *a11)
{
  struct ReAgentConfig *v13; // rdi
  unsigned int PartitionList; // ebx
  __int64 v15; // rdx
  const wchar_t *v16; // r8
  int v17; // esi
  int v18; // ebx
  unsigned __int16 *v19; // rbx
  unsigned int v20; // eax
  unsigned int fixed; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  ReAgentXMLParser *v24; // rcx
  struct ReAgentConfigInfo *ConfigInfo; // rax
  unsigned int IsCurrentOS; // eax
  int v27; // eax
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  struct PartitionNode *v30; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+74h] [rbp-8Ch] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  struct ReAgentConfig *v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+8Ch] [rbp-74h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v38; // [rsp+98h] [rbp-68h]
  ReAgentXMLParser *v39; // [rsp+A0h] [rbp-60h] BYREF
  int *v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v43[1320]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v44; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v45[1320]; // [rsp+5F8h] [rbp+4F8h] BYREF
  __int64 Src; // [rsp+B20h] [rbp+A20h] BYREF
  _BYTE v47[1320]; // [rsp+B28h] [rbp+A28h] BYREF
  int v48; // [rsp+1050h] [rbp+F50h] BYREF
  int v49; // [rsp+1058h] [rbp+F58h] BYREF
  unsigned __int16 v50[304]; // [rsp+1060h] [rbp+F60h] BYREF

  v40 = a2;
  v48 = a1;
  v35 = a4;
  v38 = a5;
  v41 = a9;
  v37 = 0;
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v39 = 0;
  v34 = 0;
  v13 = 0;
  memset_0(v50, 0, 0x25Cu);
  v33 = 0;
  v49 = 0;
  TraceLoggingRegisterEx_EventRegister_2U();
  AsmInstallWinReStart(a5, a4);
  if ( a11 )
    memset_0(a11, 0, 0x530u);
  PartitionList = SetWinReOperationSyncKey();
  if ( PartitionList )
  {
    UnattendLogW(
      2,
      L"WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d",
      L"Failed to set operation sync key",
      PartitionList,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      1010);
    goto LABEL_65;
  }
  v36 = a4 != 0 ? a6 : 0;
  UnattendLogW(
    0,
    L"--Install on target OS step 1: collect info like partition list, loading reagent.xml, source winre.wim and partition");
  PrivateFreePartitionList(0);
  PartitionList = PrivateGetPartitionList(a3);
  if ( PartitionList )
  {
    LODWORD(v30) = 1037;
    v16 = L"failed to get partition list";
LABEL_7:
    UnattendLogW(
      2,
      L"WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d",
      v16,
      PartitionList,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      v30);
    goto LABEL_49;
  }
  LogAllPartitionInfo(v37);
  PartitionList = GetDownlevelReAgentConfig(a3, &v39);
  if ( PartitionList )
  {
    LODWORD(v30) = 1040;
    v16 = L"failed to get downlevel reagent config";
    goto LABEL_7;
  }
  v17 = 1;
LABEL_11:
  v18 = 0;
  while ( v17 )
  {
    UnattendLogW(0, L"First round search");
    if ( v18 )
      goto LABEL_26;
    while ( 1 )
    {
      v31 = 0;
      if ( v13 )
      {
        (**(void (__fastcall ***)(struct ReAgentConfig *, __int64))v13)(v13, 1);
        v34 = 0;
      }
      PartitionList = GetReAgentConfig(a3, v35, &v34);
      if ( PartitionList )
      {
        LODWORD(v30) = 1059;
        UnattendLogW(
          2,
          L"WinReInstallOnTargetOSInternal %s (0x%x) in file %S line %d",
          L"failed to get reagent config",
          PartitionList,
          "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
          v30);
        v13 = v34;
        goto LABEL_49;
      }
      v13 = v34;
      PartitionList = FindWinReSourceImageAndPartition(a3, v34, v38, v50, v29, (struct PartitionNode *)&v42);
      if ( PartitionList )
      {
        LODWORD(v30) = 1061;
        v16 = L"failed to find source winre.wim";
        goto LABEL_7;
      }
      UnattendLogW(0, L"--Install on target OS step 2: detect and fix if there is any issue for winre settings");
      fixed = DetectAndFixWinReIssues(v48, a3, v13, v40, &v33, &v31);
      PartitionList = fixed;
      if ( v33 )
      {
        UnattendLogW(0, L"Current WinRE is ready. No need to make any further changes");
        goto LABEL_49;
      }
      if ( !v31 || !v17 )
        break;
      v17 = 0;
LABEL_26:
      UnattendLogW(0, L"Second round search");
    }
    if ( fixed )
    {
      UnattendLogW(1, L"failed to detect and fix winre issues, error:0x%x", fixed);
      goto LABEL_49;
    }
    UnattendLogW(
      0,
      L"--Install on target OS step 3: check if we can keep winre.wim in the same partition if it is staged.");
    v19 = v38;
    v32 = 0;
    CanKeepWinReOnSamePartitionIfStaged(&v48, a3, v13, (struct PartitionNode *)&v42, v38, &v32, &v31);
    if ( v32 )
    {
      UnattendLogW(0, L"NOTE: Find target partition: source partition will used");
      memcpy_0(&v44, &v42, 0x530u);
      goto LABEL_15;
    }
    if ( v31 && v17 )
    {
      v17 = 0;
      v18 = 1;
      UnattendLogW(0, L"NOTE: WILL RETRY because source partition is not ok because of bitlocker");
    }
    else
    {
      UnattendLogW(
        0,
        L"--Install on target OS step 4: check if we can put winre.wim in other partitions or create one if needed.");
      Src = 0;
      memset_0(v47, 0, sizeof(v47));
      v22 = CanPutWinREOnOtherPartitions(
              a3,
              v13,
              v37,
              (__int64)&v42,
              (__int64)v19,
              v36,
              a7,
              a8,
              v41,
              (__int64)&Src,
              v40,
              &v31,
              &v49);
      PartitionList = v22;
      if ( v22 )
      {
        UnattendLogW(1, L"Can't put WinRE on other partitions, error:0x%x", v22);
        goto LABEL_49;
      }
      if ( !v31 )
      {
        memcpy_0(&v44, &Src, 0x530u);
LABEL_37:
        v17 = 0;
        goto LABEL_11;
      }
      if ( !v17 )
        goto LABEL_37;
      v17 = 0;
      v18 = 1;
    }
  }
  if ( v18 )
    goto LABEL_26;
  v19 = v38;
LABEL_15:
  UnattendLogW(
    0,
    L"--Install on target OS step 5: set WinRE settings and restore system to a good state when hitting any errors");
  v20 = SetWinRESettings(a3, v13, (struct PartitionNode *)&v42, (struct PartitionNode *)&v44, v50, v19);
  PartitionList = v20;
  if ( v20 )
  {
    UnattendLogW(1, L"failed to set WinRE settings, error:0x%x", v20);
  }
  else
  {
    UnattendLogW(0, L"Backup Setting file");
    v23 = winreBackupSettingFile(a3);
    PartitionList = v23;
    if ( v23 )
    {
      UnattendLogW(2, L"failed to backup setting file, error:0x%x", v23);
      PartitionList = 0;
    }
    UnattendLogW(0, L"WinReInstallOnTargetOSInternal WinRE installation completed successfully.");
    if ( a11 && v49 )
      memcpy_0(a11, &v44, 0x530u);
  }
LABEL_49:
  RemoveWinReOperationSyncKey();
  if ( !PartitionList )
  {
    if ( a10 )
    {
      v24 = v39;
      *a10 = 0;
      if ( v24 )
      {
        ConfigInfo = ReAgentXMLParser::GetConfigInfo(v24);
        if ( ConfigInfo )
        {
          if ( *((_DWORD *)ConfigInfo + 1397) )
            *a10 = 1;
        }
      }
    }
    if ( (unsigned int)winreIsEfi() )
    {
      UnattendLogW(0, L"Is UEFI");
      v32 = 0;
      IsCurrentOS = winreIsCurrentOS(a3, &v32);
      if ( IsCurrentOS )
      {
        UnattendLogW(2, L"Failed to check whether it's current OS GUID: 0x%x", IsCurrentOS);
        v27 = 0;
      }
      else
      {
        v27 = v32;
      }
      if ( v27 )
      {
        if ( (unsigned int)winreIsVMMode() )
        {
          UnattendLogW(0, L"Sysprep VM mode; skipped storing disk info in NVRAM");
        }
        else
        {
          UnattendLogW(0, L"Storing disk info in NVRAM");
          winreStoreSystemDiskPathInNVRAM();
          UnattendLogW(0, L"Stored disk info in NVRAM");
        }
      }
      else
      {
        UnattendLogW(0, L"Not installing for running OS; skipped storing disk info in NVRAM");
      }
    }
    else
    {
      UnattendLogW(0, L"Not UEFI; skipped storing disk info in NVRAM");
    }
  }
LABEL_65:
  AsmInstallWinReEnd((struct PartitionNode *)&v44, v15, PartitionList);
  TraceLoggingUnregister_EventUnregister();
  if ( v39 )
    (**(void (__fastcall ***)(ReAgentXMLParser *, __int64))v39)(v39, 1);
  if ( v13 )
    (**(void (__fastcall ***)(struct ReAgentConfig *, __int64))v13)(v13, 1);
  return PartitionList;
}

```

## disassembly

```asm
0x1800193e8  push    rbp
0x1800193ea  push    rbx
0x1800193eb  push    rsi
0x1800193ec  push    rdi
0x1800193ed  push    r12
0x1800193ef  push    r13
0x1800193f1  push    r14
0x1800193f3  push    r15
0x1800193f5  lea     rbp, [rsp-11D8h]
0x1800193fd  mov     eax, 12D8h
0x180019402  call    _alloca_probe
0x180019407  sub     rsp, rax
0x18001940a  mov     rax, cs:__security_cookie
0x180019411  xor     rax, rsp
0x180019414  mov     [rbp+1210h+var_50], rax
0x18001941b  mov     rax, [rbp+1210h+arg_40]
0x180019422  mov     r15, r8
0x180019425  mov     rbx, [rbp+1210h+arg_20]
0x18001942c  xor     r14d, r14d
0x18001942f  mov     r13, [rbp+1210h+arg_48]
0x180019436  mov     edi, 528h
0x18001943b  mov     r12, [rbp+1210h+arg_50]
0x180019442  mov     r8d, edi; Size
0x180019445  mov     [rbp+1210h+var_1268], rdx
0x180019449  mov     esi, r9d
0x18001944c  mov     [rbp+1210h+var_2C0], ecx
0x180019452  xor     edx, edx; Val
0x180019454  lea     rcx, [rbp+1210h+var_D18]; void *
0x18001945b  mov     [rbp+1210h+var_1288], r9d
0x18001945f  mov     [rbp+1210h+var_1278], rbx
0x180019463  mov     [rbp+1210h+var_1260], rax
0x180019467  mov     [rbp+1210h+var_1280], r14
0x18001946b  mov     [rbp+1210h+var_D20], r14
0x180019472  call    memset_0
0x180019477  mov     r8d, edi; Size
0x18001947a  mov     [rbp+1210h+var_1250], r14
0x18001947e  xor     edx, edx; Val
0x180019480  lea     rcx, [rbp+1210h+var_1248]; void *
0x180019484  call    memset_0
0x180019489  xor     edx, edx; Val
0x18001948b  mov     [rbp+1210h+var_1270], r14
0x18001948f  mov     r8d, 25Ch; Size
0x180019495  mov     [rbp+1210h+var_1290], r14
0x180019499  lea     rcx, [rbp+1210h+var_2B0]; void *
0x1800194a0  mov     edi, r14d
0x1800194a3  call    memset_0
0x1800194a8  mov     [rsp+1310h+var_1298], r14d
0x1800194ad  mov     [rbp+1210h+var_2B8], r14d
0x1800194b4  call    TraceLoggingRegisterEx_EventRegister_2U
0x1800194b9  mov     edx, esi; int
0x1800194bb  mov     rcx, rbx; unsigned __int16 *
0x1800194be  call    ?AsmInstallWinReStart@@YAXPEBGH@Z; AsmInstallWinReStart(ushort const *,int)
0x1800194c3  test    r12, r12
0x1800194c6  jz      short loc_1800194D8
0x1800194c8  xor     edx, edx; Val
0x1800194ca  mov     r8d, 530h; Size
0x1800194d0  mov     rcx, r12; void *
0x1800194d3  call    memset_0
0x1800194d8  call    SetWinReOperationSyncKey
0x1800194dd  mov     ebx, eax
0x1800194df  test    eax, eax
0x1800194e1  jz      short loc_180019517
0x1800194e3  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800194ea  mov     dword ptr [rsp+1310h+var_12E8], 3F2h
0x1800194f2  mov     r9d, ebx
0x1800194f5  mov     [rsp+1310h+var_12F0], rax
0x1800194fa  lea     r8, aFailedToSetOpe_0; "Failed to set operation sync key"
0x180019501  mov     ecx, 2
0x180019506  lea     rdx, aWinreinstallon_2; "WinReInstallOnTargetOSInternal %s (0x%x"...
0x18001950d  call    UnattendLogW
0x180019512  jmp     loc_180019A1F
0x180019517  mov     eax, esi
0x180019519  lea     rdx, aInstallOnTarge_1; "--Install on target OS step 1: collect "...
0x180019520  neg     eax
0x180019522  sbb     eax, eax
0x180019524  xor     ecx, ecx
0x180019526  and     eax, [rbp+1210h+arg_28]
0x18001952c  mov     [rbp+1210h+var_1284], eax
0x18001952f  call    UnattendLogW
0x180019534  xor     ecx, ecx; pv
0x180019536  call    PrivateFreePartitionList
0x18001953b  lea     rdx, [rbp+1210h+var_1280]
0x18001953f  mov     rcx, r15; struct _GUID *
0x180019542  call    PrivateGetPartitionList
0x180019547  mov     ebx, eax
0x180019549  mov     r14d, 2
0x18001954f  test    eax, eax
0x180019551  jz      short loc_180019585
0x180019553  mov     dword ptr [rsp+1310h+var_12E8], 40Dh
0x18001955b  lea     r8, aFailedToGetPar; "failed to get partition list"
0x180019562  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180019569  mov     r9d, ebx
0x18001956c  lea     rdx, aWinreinstallon_2; "WinReInstallOnTargetOSInternal %s (0x%x"...
0x180019573  mov     [rsp+1310h+var_12F0], rax
0x180019578  mov     ecx, r14d
0x18001957b  call    UnattendLogW
0x180019580  jmp     loc_180019953
0x180019585  mov     rcx, [rbp+1210h+var_1280]
0x180019589  call    LogAllPartitionInfo
0x18001958e  lea     rdx, [rbp+1210h+var_1270]; struct ReAgentConfig **
0x180019592  mov     rcx, r15; struct _GUID *
0x180019595  call    ?GetDownlevelReAgentConfig@@YAKPEAU_GUID@@PEAPEAVReAgentConfig@@@Z; GetDownlevelReAgentConfig(_GUID *,ReAgentConfig * *)
0x18001959a  mov     ebx, eax
0x18001959c  test    eax, eax
0x18001959e  jz      short loc_1800195B1
0x1800195a0  mov     dword ptr [rsp+1310h+var_12E8], 410h
0x1800195a8  lea     r8, aFailedToGetDow_1; "failed to get downlevel reagent config"
0x1800195af  jmp     short loc_180019562
0x1800195b1  mov     esi, 1
0x1800195b6  xor     ebx, ebx
0x1800195b8  test    esi, esi
0x1800195ba  jnz     short loc_180019613
0x1800195bc  test    ebx, ebx
0x1800195be  jnz     loc_1800196E8
0x1800195c4  mov     rbx, [rbp+1210h+var_1278]
0x1800195c8  lea     rdx, aInstallOnTarge_3; "--Install on target OS step 5: set WinR"...
0x1800195cf  xor     ecx, ecx
0x1800195d1  call    UnattendLogW
0x1800195d6  lea     rax, [rbp+1210h+var_2B0]
0x1800195dd  mov     [rsp+1310h+var_12E8], rbx; unsigned __int16 *
0x1800195e2  lea     r9, [rbp+1210h+var_D20]; struct PartitionNode *
0x1800195e9  mov     [rsp+1310h+var_12F0], rax; unsigned __int16 *
0x1800195ee  lea     r8, [rbp+1210h+var_1250]; struct PartitionNode *
0x1800195f2  mov     rdx, rdi; this
0x1800195f5  mov     rcx, r15; struct _GUID *
0x1800195f8  call    ?SetWinRESettings@@YAKPEAU_GUID@@PEAVReAgentConfig@@PEAUPartitionNode@@2PEBG3@Z; SetWinRESettings(_GUID *,ReAgentConfig *,PartitionNode *,PartitionNode *,ushort const *,ushort const *)
0x1800195fd  mov     ebx, eax
0x1800195ff  test    eax, eax
0x180019601  jz      loc_18001987D
0x180019607  lea     rdx, aFailedToSetWin_2; "failed to set WinRE settings, error:0x%"...
0x18001960e  jmp     loc_1800198EF
0x180019613  lea     rdx, aFirstRoundSear; "First round search"
0x18001961a  xor     ecx, ecx
0x18001961c  call    UnattendLogW
0x180019621  test    ebx, ebx
0x180019623  jnz     loc_1800196E8
0x180019629  mov     [rsp+1310h+var_12A0], 0
0x180019631  test    rdi, rdi
0x180019634  jz      short loc_180019651
0x180019636  mov     rax, [rdi]
0x180019639  mov     edx, 1
0x18001963e  mov     rcx, rdi
0x180019641  mov     rax, [rax]
0x180019644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019649  mov     [rbp+1210h+var_1290], 0
0x180019651  mov     edx, [rbp+1210h+var_1288]; int
0x180019654  lea     r8, [rbp+1210h+var_1290]; struct ReAgentConfig **
0x180019658  mov     rcx, r15; struct _GUID *
0x18001965b  call    ?GetReAgentConfig@@YAKPEAU_GUID@@HPEAPEAVReAgentConfig@@@Z; GetReAgentConfig(_GUID *,int,ReAgentConfig * *)
0x180019660  mov     ebx, eax
0x180019662  test    eax, eax
0x180019664  jnz     loc_180019922
0x18001966a  mov     rdi, [rbp+1210h+var_1290]
0x18001966e  lea     rax, [rbp+1210h+var_1250]
0x180019672  mov     r8, [rbp+1210h+var_1278]; unsigned __int16 *
0x180019676  lea     r9, [rbp+1210h+var_2B0]; unsigned __int16 *
0x18001967d  mov     rdx, rdi; struct ReAgentConfig *
0x180019680  mov     [rsp+1310h+var_12E8], rax; struct PartitionNode *
0x180019685  mov     rcx, r15; struct _GUID *
0x180019688  call    ?FindWinReSourceImageAndPartition@@YAKPEAU_GUID@@PEAVReAgentConfig@@PEBGPEAGKPEAUPartitionNode@@@Z; FindWinReSourceImageAndPartition(_GUID *,ReAgentConfig *,ushort const *,ushort *,ulong,PartitionNode *)
0x18001968d  mov     ebx, eax
0x18001968f  test    eax, eax
0x180019691  jnz     loc_18001990E
0x180019697  lea     rdx, aInstallOnTarge_0; "--Install on target OS step 2: detect a"...
0x18001969e  xor     ecx, ecx
0x1800196a0  call    UnattendLogW
0x1800196a5  mov     r9, [rbp+1210h+var_1268]; int *
0x1800196a9  lea     rax, [rsp+1310h+var_12A0]
0x1800196ae  mov     ecx, [rbp+1210h+var_2C0]; int
0x1800196b4  mov     r8, rdi; struct ReAgentConfig *
0x1800196b7  mov     [rsp+1310h+var_12E8], rax; int *
0x1800196bc  mov     rdx, r15; struct _GUID *
0x1800196bf  lea     rax, [rsp+1310h+var_1298]
0x1800196c4  mov     [rsp+1310h+var_12F0], rax; int *
0x1800196c9  call    ?DetectAndFixWinReIssues@@YAKHPEAU_GUID@@PEAVReAgentConfig@@PEAH22@Z; DetectAndFixWinReIssues(int,_GUID *,ReAgentConfig *,int *,int *,int *)
0x1800196ce  cmp     [rsp+1310h+var_1298], 0
0x1800196d3  mov     ebx, eax
0x1800196d5  jnz     loc_1800198FE
0x1800196db  cmp     [rsp+1310h+var_12A0], 0
0x1800196e0  jz      short loc_1800196FB
0x1800196e2  test    esi, esi
0x1800196e4  jz      short loc_1800196FB
0x1800196e6  xor     esi, esi
0x1800196e8  lea     rdx, aSecondRoundSea; "Second round search"
0x1800196ef  xor     ecx, ecx
0x1800196f1  call    UnattendLogW
0x1800196f6  jmp     loc_180019629
0x1800196fb  test    eax, eax
0x1800196fd  jnz     loc_1800198E8
0x180019703  lea     rdx, aInstallOnTarge_2; "--Install on target OS step 3: check if"...
0x18001970a  xor     ecx, ecx
0x18001970c  call    UnattendLogW
0x180019711  mov     rbx, [rbp+1210h+var_1278]
0x180019715  lea     rax, [rsp+1310h+var_12A0]
0x18001971a  mov     [rsp+1310h+var_12E0], rax; int *
0x18001971f  lea     r9, [rbp+1210h+var_1250]; struct PartitionNode *
0x180019723  lea     rax, [rsp+1310h+var_129C]
0x180019728  mov     [rsp+1310h+var_129C], 0
0x180019730  mov     [rsp+1310h+var_12E8], rax; int *
0x180019735  lea     rcx, [rbp+1210h+var_2C0]; int *
0x18001973c  mov     r8, rdi; struct ReAgentConfig *
0x18001973f  mov     [rsp+1310h+var_12F0], rbx; unsigned __int16 *
0x180019744  mov     rdx, r15; struct _GUID *
0x180019747  call    ?CanKeepWinReOnSamePartitionIfStaged@@YAKPEAHPEAU_GUID@@PEAVReAgentConfig@@PEAUPartitionNode@@PEBG00@Z; CanKeepWinReOnSamePartitionIfStaged(int *,_GUID *,ReAgentConfig *,PartitionNode *,ushort const *,int *,int *)
0x18001974c  cmp     [rsp+1310h+var_129C], 0
0x180019751  jnz     loc_180019854
0x180019757  cmp     [rsp+1310h+var_12A0], 0
0x18001975c  jz      short loc_18001977A
0x18001975e  test    esi, esi
0x180019760  jz      short loc_18001977A
0x180019762  xor     esi, esi
0x180019764  lea     rdx, aNoteWillRetryB_0; "NOTE: WILL RETRY because source partiti"...
0x18001976b  xor     ecx, ecx
0x18001976d  lea     ebx, [rsi+1]
0x180019770  call    UnattendLogW
0x180019775  jmp     loc_1800195B8
0x18001977a  lea     rdx, aInstallOnTarge; "--Install on target OS step 4: check if"...
0x180019781  xor     ecx, ecx
0x180019783  call    UnattendLogW
0x180019788  xor     edx, edx; Val
0x18001978a  mov     [rbp+1210h+Src], 0
0x180019795  mov     r8d, 528h; Size
0x18001979b  lea     rcx, [rbp+1210h+var_7E8]; void *
0x1800197a2  call    memset_0
0x1800197a7  mov     r8, [rbp+1210h+var_1280]
0x1800197ab  lea     rax, [rbp+1210h+var_2B8]
0x1800197b2  mov     [rsp+1310h+var_12B0], rax
0x1800197b7  lea     r9, [rbp+1210h+var_1250]
0x1800197bb  lea     rax, [rsp+1310h+var_12A0]
0x1800197c0  mov     rdx, rdi
0x1800197c3  mov     [rsp+1310h+var_12B8], rax
0x1800197c8  mov     rcx, r15
0x1800197cb  mov     rax, [rbp+1210h+var_1268]
0x1800197cf  mov     [rsp+1310h+var_12C0], rax
0x1800197d4  lea     rax, [rbp+1210h+Src]
0x1800197db  mov     [rsp+1310h+var_12C8], rax
0x1800197e0  mov     rax, [rbp+1210h+var_1260]
0x1800197e4  mov     [rsp+1310h+var_12D0], rax
0x1800197e9  mov     eax, [rbp+1210h+arg_38]
0x1800197ef  mov     [rsp+1310h+var_12D8], eax
0x1800197f3  mov     eax, [rbp+1210h+arg_30]
0x1800197f9  mov     dword ptr [rsp+1310h+var_12E0], eax
0x1800197fd  mov     eax, [rbp+1210h+var_1284]
0x180019800  mov     dword ptr [rsp+1310h+var_12E8], eax
0x180019804  mov     [rsp+1310h+var_12F0], rbx
0x180019809  call    ?CanPutWinREOnOtherPartitions@@YAHPEAU_GUID@@PEAVReAgentConfig@@PEAU_LIST_ENTRY@@PEAUPartitionNode@@PEBGHKW4_WINRE_PARTITION_LOCATION@@43PEAH66@Z; CanPutWinREOnOtherPartitions(_GUID *,ReAgentConfig *,_LIST_ENTRY *,PartitionNode *,ushort const *,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,PartitionNode *,int *,int *,int *)
0x18001980e  mov     ebx, eax
0x180019810  test    eax, eax
0x180019812  jnz     short loc_180019848
0x180019814  cmp     [rsp+1310h+var_12A0], eax
0x180019818  jz      short loc_180019828
0x18001981a  test    esi, esi
0x18001981c  jz      short loc_180019841
0x18001981e  xor     esi, esi
0x180019820  lea     ebx, [rax+1]
0x180019823  jmp     loc_1800195B8
0x180019828  lea     rcx, [rbp+1210h+var_D20]; void *
0x18001982f  mov     r8d, 530h; Size
0x180019835  lea     rdx, [rbp+1210h+Src]; Src
0x18001983c  call    memcpy_0
0x180019841  xor     esi, esi
0x180019843  jmp     loc_1800195B6
0x180019848  lea     rdx, aCanTPutWinreOn; "Can't put WinRE on other partitions, er"...
0x18001984f  jmp     loc_1800198EF
0x180019854  lea     rdx, aNoteFindTarget; "NOTE: Find target partition: source par"...
0x18001985b  xor     ecx, ecx
0x18001985d  call    UnattendLogW
0x180019862  lea     rcx, [rbp+1210h+var_D20]; void *
0x180019869  mov     r8d, 530h; Size
0x18001986f  lea     rdx, [rbp+1210h+var_1250]; Src
0x180019873  call    memcpy_0
0x180019878  jmp     loc_1800195C8
0x18001987d  lea     rdx, aBackupSettingF_1; "Backup Setting file"
0x180019884  xor     ecx, ecx
0x180019886  call    UnattendLogW
0x18001988b  mov     rcx, r15
0x18001988e  call    winreBackupSettingFile
0x180019893  mov     ebx, eax
0x180019895  test    eax, eax
0x180019897  jz      short loc_1800198AD
0x180019899  mov     r8d, eax
0x18001989c  lea     rdx, aFailedToBackup_1; "failed to backup setting file, error:0x"...
0x1800198a3  mov     ecx, r14d
0x1800198a6  call    UnattendLogW
0x1800198ab  xor     ebx, ebx
0x1800198ad  lea     rdx, aWinreinstallon_1; "WinReInstallOnTargetOSInternal WinRE in"...
0x1800198b4  xor     ecx, ecx
0x1800198b6  call    UnattendLogW
0x1800198bb  test    r12, r12
0x1800198be  jz      loc_180019953
0x1800198c4  cmp     [rbp+1210h+var_2B8], 0
0x1800198cb  jz      loc_180019953
0x1800198d1  mov     rcx, r12; void *
0x1800198d4  lea     rdx, [rbp+1210h+var_D20]; Src
0x1800198db  mov     r8d, 530h; Size
0x1800198e1  call    memcpy_0
0x1800198e6  jmp     short loc_180019953
0x1800198e8  lea     rdx, aFailedToDetect_3; "failed to detect and fix winre issues, "...
0x1800198ef  mov     r8d, eax
0x1800198f2  mov     ecx, 1
  ... truncated ...
```
