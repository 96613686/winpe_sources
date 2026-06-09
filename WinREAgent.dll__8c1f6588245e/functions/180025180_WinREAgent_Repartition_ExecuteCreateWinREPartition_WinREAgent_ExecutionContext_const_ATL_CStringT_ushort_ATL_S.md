# WinREAgent::Repartition::ExecuteCreateWinREPartition(WinREAgent::ExecutionContext const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180025180`
- end: `0x1800258b0`
- name: `?ExecuteCreateWinREPartition@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1840`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025ef0`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x1800074b8`
- `0x1800089d0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180011ef4`
- `0x180025180`
- `0x180027fdc`
- `0x18002e06c`
- `0x18002e1f8`
- `0x18003207c`
- `0x180032480`
- `0x180032504`
- `0x180033238`
- `0x18003717c`
- `0x180037344`
- `0x180047d1c`
- `0x18004e5a4`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x1800251cc`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002523a`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800254d7`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025545`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800255c3`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025699`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025685`: `Failed to save WinRE partition volume name into Rollback info`
- `0x1800251d3`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x180025241`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x1800254de`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x18002554c`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x1800255ca`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x1800256a0`: `WinREAgent::Repartition::ExecuteCreateWinREPartition`
- `0x1800251fd`: `Repartition: Create WinRE partition with size [%llu]`
- `0x1800252a2`: `Create recovery partition at offset [%llu]`
- `0x18002533d`: `Failed to save target WinRE partition size into Rollback info`
- `0x1800253ca`: `Failed to save target WinRE partition offset into Rollback info`
- `0x1800254a0`: `CreateWinREPartitionSucceed`
- `0x180025499`: `CreateWinREPartitionFaield`
- `0x1800254c3`: `Failed to create WinRE partition`
- `0x1800256bd`: `Repartition: Save repartition has completed`
- `0x1800256e4`: `RepartitionCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WinREAgent::Repartition::ExecuteCreateWinREPartition(__int64 a1, __int64 a2, _QWORD *a3)
{
  WinREAgent::TelemetrySession *v7; // r14
  struct PushButtonReset::PartitionInfo *v8; // rdx
  signed int Info; // ebx
  __int64 v10; // rdi
  unsigned __int64 v11; // r12
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rbx
  struct PushButtonReset::Partition **v15; // rax
  const unsigned __int16 *v16; // r8
  PushButtonReset::Partition *v17; // rax
  int Volume; // edi
  ATL::CStringData *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // rdi
  ATL::CStringData *v23; // r14
  int *v24; // rsi
  __int64 v25; // rbx
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[40]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  _QWORD v34[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v35[10]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]
  __int64 v38; // [rsp+140h] [rbp+40h]

  if ( !a3 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::Repartition::ExecuteCreateWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      561,
      L"volumeName cannot be null");
    return 2147942487LL;
  }
  v7 = *(WinREAgent::TelemetrySession **)(a1 + 112);
  PushButtonReset::Logging::Trace(0, L"Repartition: Create WinRE partition with size [%llu]", *(_QWORD *)(a1 + 176));
  PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v31);
  Info = WinREAgent::WinREGetOSPartitionInfo((WinREAgent *)v31, v8);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::Repartition::ExecuteCreateWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      570,
      L"Failed to get OS partition info");
LABEL_5:
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v31);
    return (unsigned int)Info;
  }
  v10 = v32;
  PushButtonReset::Logging::Trace(0, L"OS partition offset: [%llu]", v32);
  PushButtonReset::Logging::Trace(0, L"OS partition size: [%llu]", v33);
  v11 = (v33 + v10 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
  PushButtonReset::Logging::Trace(0, L"Create recovery partition at offset [%llu]", v11);
  if ( *(_QWORD *)(a2 + 448) )
  {
    PushButtonReset::Logging::Trace(0, L"Repartition: Save target WinRE partition size: [%llu]", *(_QWORD *)(a1 + 176));
    v12 = *(_QWORD *)(a2 + 448);
    v13 = *(_QWORD *)(a1 + 176);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v26,
      (__int64)L"TargetWinREPartitionSize");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"RepartitionInfo");
    Info = WinREAgent::RollbackHelper::WriteToConfig(v12, &v27, &v26, v13);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteCreateWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        592,
        L"Failed to save target WinRE partition size into Rollback info");
      goto LABEL_5;
    }
    PushButtonReset::Logging::Trace(0, L"Repartition: Save target WinRE partition offset: [%llu]", v11);
    v14 = *(_QWORD *)(a2 + 448);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v26,
      (__int64)L"TargetWinREPartitionOffset");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"RepartitionInfo");
    Info = WinREAgent::RollbackHelper::WriteToConfig(v14, &v27, &v26, v11);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteCreateWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        598,
        L"Failed to save target WinRE partition offset into Rollback info");
      goto LABEL_5;
    }
    PushButtonReset::Logging::Trace(0, L"Repartition: Add checkpoint [%u]", 8);
    Info = WinREAgent::RollbackHelper::SetCheckpoint(*(_QWORD *)(a2 + 448), 8);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteCreateWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        602,
        L"Failed to set checkpoint for Repartition");
      goto LABEL_5;
    }
  }
  if ( v7 )
  {
    WinREAgent::TelemetrySession::TraceDataPoint(v7, L"ExecutionInfoGroup", L"NewPartitionSize", *(_QWORD *)(a1 + 176));
    WinREAgent::TelemetrySession::TraceDataPoint(v7, L"ExecutionInfoGroup", L"NewPartitionOffset", v11);
  }
  v34[1] = 0;
  v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v15 = (struct PushButtonReset::Partition **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v34);
  Info = WinRECreateRecoveryPartition(v11, *(_QWORD *)(a1 + 176), v15);
  if ( v7 )
  {
    v16 = L"CreateWinREPartitionSucceed";
    if ( Info < 0 )
      v16 = L"CreateWinREPartitionFaield";
    WinREAgent::TelemetrySession::TraceDataPoint(v7, L"ExecutionInfoGroup", v16, Info);
  }
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::Repartition::ExecuteCreateWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      624,
      L"Failed to create WinRE partition");
LABEL_21:
    v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v34);
    goto LABEL_5;
  }
  PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v35);
  v17 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v34[0] + 24LL))(v34);
  Info = PushButtonReset::Partition::GetInfo(v17, (struct PushButtonReset::PartitionInfo *)v35);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::Repartition::ExecuteCreateWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      629,
      L"Failed to get WinRE partition info");
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v35);
    goto LABEL_21;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v27);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v26,
    L"\\\\?\\GLOBALROOT\\device\\harddisk%u\\partition%u\\",
    v35[0],
    v35[1]);
  Volume = PushButtonReset::Path::GetVolume(&v26, &v27);
  if ( Volume >= 0 )
  {
    v20 = v27;
    PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition volume name: [%s]", v27);
    if ( *(_QWORD *)(a2 + 448) )
    {
      PushButtonReset::Logging::Trace(0, L"Repartition: Save new WinRE partition volume name: [%s]", v20);
      v21 = *(_QWORD *)(a2 + 448);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v29,
        (__int64)L"WinREPartitionVolumeName");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)L"RepartitionInfo");
      Volume = WinREAgent::RollbackHelper::WriteToConfig(v21, &v28, &v29, &v27);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      if ( Volume < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::Repartition::ExecuteCreateWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          650,
          L"Failed to save WinRE partition volume name into Rollback info");
LABEL_29:
        v19 = (ATL::CStringData *)(v20 - 24);
        goto LABEL_41;
      }
      PushButtonReset::Logging::Trace(0, L"Repartition: Save repartition has completed");
      v22 = *(_QWORD *)(a2 + 448);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)v30,
        (__int64)L"Yes");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)L"RepartitionCompleted");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v29,
        (__int64)L"RepartitionInfo");
      Volume = WinREAgent::RollbackHelper::WriteToConfig(v22, &v29, &v28, v30);
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v30[0] - 24LL));
      if ( Volume < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::Repartition::ExecuteCreateWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          657,
          L"Failed to save repartition has cmpleted");
        goto LABEL_29;
      }
    }
    PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition info");
    PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition offset: [%llu]", v36);
    PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Size: [%llu]", v37);
    PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Available space: [%llu]", v38);
    if ( !*(_QWORD *)(a2 + 448)
      || (PushButtonReset::Logging::Trace(0, L"Repartition: Add checkpoint [%u]", 9),
          Volume = WinREAgent::RollbackHelper::SetCheckpoint(*(_QWORD *)(a2 + 448), 9),
          Volume >= 0) )
    {
      v23 = (ATL::CStringData *)(v20 - 24);
      v24 = (int *)(*a3 - 24LL);
      if ( (int *)(v20 - 24) != v24 )
      {
        if ( v24[4] >= 0 && *(_QWORD *)v23 == *(_QWORD *)v24 )
        {
          v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v20 - 24);
          ATL::CStringData::Release((ATL::CStringData *)v24);
          *a3 = v25 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v20, *(unsigned int *)(v20 - 16));
        }
      }
      v19 = v23;
      goto LABEL_41;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Volume,
      "WinREAgent::Repartition::ExecuteCreateWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      671,
      L"Failed to set checkpoint for Repartition");
    goto LABEL_29;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Volume,
    "WinREAgent::Repartition::ExecuteCreateWinREPartition",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    638,
    L"Failed to get volume name");
  v19 = (ATL::CStringData *)(v27 - 24);
LABEL_41:
  ATL::CStringData::Release(v19);
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v35);
  v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v34);
  PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v31);
  return (unsigned int)Volume;
}

```

## disassembly

```asm
0x180025180  mov     [rsp-8+arg_18], rbx
0x180025185  push    rbp
0x180025186  push    rsi
0x180025187  push    rdi
0x180025188  push    r12
0x18002518a  push    r13
0x18002518c  push    r14
0x18002518e  push    r15
0x180025190  lea     rbp, [rsp-80h]
0x180025195  sub     rsp, 180h
0x18002519c  mov     rax, cs:__security_cookie
0x1800251a3  xor     rax, rsp
0x1800251a6  mov     [rbp+0B0h+var_40], rax
0x1800251aa  mov     r13, r8
0x1800251ad  mov     rsi, rdx
0x1800251b0  mov     r15, rcx
0x1800251b3  test    r8, r8
0x1800251b6  jnz     short loc_1800251F2
0x1800251b8  lea     rax, aVolumenameCann; "volumeName cannot be null"
0x1800251bf  mov     [rsp+1B0h+var_188], rax
0x1800251c4  mov     [rsp+1B0h+var_190], 231h
0x1800251cc  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800251d3  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x1800251da  mov     edx, 80070057h
0x1800251df  lea     ecx, [r13+2]
0x1800251e3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800251e8  mov     eax, 80070057h
0x1800251ed  jmp     loc_180025889
0x1800251f2  mov     r14, [rcx+70h]
0x1800251f6  mov     r8, [rcx+0B0h]
0x1800251fd  lea     rdx, aRepartitionCre_1; "Repartition: Create WinRE partition wit"...
0x180025204  xor     ecx, ecx
0x180025206  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002520b  lea     rcx, [rsp+1B0h+var_150]; this
0x180025210  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180025215  nop
0x180025216  lea     rcx, [rsp+1B0h+var_150]; this
0x18002521b  call    ?WinREGetOSPartitionInfo@WinREAgent@@YAJPEAUPartitionInfo@PushButtonReset@@@Z; WinREAgent::WinREGetOSPartitionInfo(PushButtonReset::PartitionInfo *)
0x180025220  mov     ebx, eax
0x180025222  test    eax, eax
0x180025224  jns     short loc_180025266
0x180025226  lea     rax, aFailedToGetOsP; "Failed to get OS partition info"
0x18002522d  mov     [rsp+1B0h+var_188], rax
0x180025232  mov     [rsp+1B0h+var_190], 23Ah
0x18002523a  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180025241  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x180025248  mov     edx, ebx
0x18002524a  mov     ecx, 2
0x18002524f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180025254  nop
0x180025255  lea     rcx, [rsp+1B0h+var_150]; this
0x18002525a  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x18002525f  mov     eax, ebx
0x180025261  jmp     loc_180025889
0x180025266  mov     rdi, [rbp+0B0h+var_128]
0x18002526a  mov     r8, rdi
0x18002526d  lea     rdx, aOsPartitionOff; "OS partition offset: [%llu]"
0x180025274  xor     ecx, ecx
0x180025276  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002527b  mov     r8, [rbp+0B0h+var_120]
0x18002527f  lea     rdx, aOsPartitionSiz; "OS partition size: [%llu]"
0x180025286  xor     ecx, ecx
0x180025288  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002528d  lea     r12, [rdi+0FFFFFh]
0x180025294  add     r12, [rbp+0B0h+var_120]
0x180025298  and     r12, 0FFFFFFFFFFF00000h
0x18002529f  mov     r8, r12
0x1800252a2  lea     rdx, aCreateRecovery; "Create recovery partition at offset [%l"...
0x1800252a9  xor     ecx, ecx
0x1800252ab  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800252b0  cmp     qword ptr [rsi+1C0h], 0
0x1800252b8  jz      loc_180025426
0x1800252be  mov     r8, [r15+0B0h]
0x1800252c5  lea     rdx, aRepartitionSav_2; "Repartition: Save target WinRE partitio"...
0x1800252cc  xor     ecx, ecx
0x1800252ce  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800252d3  mov     rdi, [rsi+1C0h]
0x1800252da  mov     rbx, [r15+0B0h]
0x1800252e1  lea     rdx, aTargetwinrepar; "TargetWinREPartitionSize"
0x1800252e8  lea     rcx, [rsp+1B0h+var_180]
0x1800252ed  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800252f2  nop
0x1800252f3  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x1800252fa  lea     rcx, [rsp+1B0h+var_178]
0x1800252ff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025304  nop
0x180025305  mov     r9, rbx
0x180025308  lea     r8, [rsp+1B0h+var_180]
0x18002530d  lea     rdx, [rsp+1B0h+var_178]
0x180025312  mov     rcx, rdi
0x180025315  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0_K@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x18002531a  mov     ebx, eax
0x18002531c  mov     rcx, [rsp+1B0h+var_178]
0x180025321  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025325  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002532a  nop
0x18002532b  mov     rcx, [rsp+1B0h+var_180]
0x180025330  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025334  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025339  test    ebx, ebx
0x18002533b  jns     short loc_180025356
0x18002533d  lea     rax, aFailedToSaveTa_0; "Failed to save target WinRE partition s"...
0x180025344  mov     [rsp+1B0h+var_188], rax
0x180025349  mov     [rsp+1B0h+var_190], 250h
0x180025351  jmp     loc_18002523A
0x180025356  mov     r8, r12
0x180025359  lea     rdx, aRepartitionSav_0; "Repartition: Save target WinRE partitio"...
0x180025360  xor     ecx, ecx
0x180025362  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025367  mov     rbx, [rsi+1C0h]
0x18002536e  lea     rdx, aTargetwinrepar_0; "TargetWinREPartitionOffset"
0x180025375  lea     rcx, [rsp+1B0h+var_180]
0x18002537a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002537f  nop
0x180025380  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180025387  lea     rcx, [rsp+1B0h+var_178]
0x18002538c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025391  nop
0x180025392  mov     r9, r12
0x180025395  lea     r8, [rsp+1B0h+var_180]
0x18002539a  lea     rdx, [rsp+1B0h+var_178]
0x18002539f  mov     rcx, rbx
0x1800253a2  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0_K@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x1800253a7  mov     ebx, eax
0x1800253a9  mov     rcx, [rsp+1B0h+var_178]
0x1800253ae  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800253b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800253b7  nop
0x1800253b8  mov     rcx, [rsp+1B0h+var_180]
0x1800253bd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800253c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800253c6  test    ebx, ebx
0x1800253c8  jns     short loc_1800253E3
0x1800253ca  lea     rax, aFailedToSaveTa; "Failed to save target WinRE partition o"...
0x1800253d1  mov     [rsp+1B0h+var_188], rax
0x1800253d6  mov     [rsp+1B0h+var_190], 256h
0x1800253de  jmp     loc_18002523A
0x1800253e3  mov     ebx, 8
0x1800253e8  mov     r8d, ebx
0x1800253eb  lea     rdx, aRepartitionAdd; "Repartition: Add checkpoint [%u]"
0x1800253f2  xor     ecx, ecx
0x1800253f4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800253f9  mov     edx, ebx
0x1800253fb  mov     rcx, [rsi+1C0h]
0x180025402  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x180025407  mov     ebx, eax
0x180025409  test    eax, eax
0x18002540b  jns     short loc_180025426
0x18002540d  lea     rax, aFailedToSetChe_4; "Failed to set checkpoint for Repartitio"...
0x180025414  mov     [rsp+1B0h+var_188], rax
0x180025419  mov     [rsp+1B0h+var_190], 25Ah
0x180025421  jmp     loc_18002523A
0x180025426  test    r14, r14
0x180025429  jz      short loc_180025461
0x18002542b  mov     r9, [r15+0B0h]; unsigned __int64
0x180025432  lea     r8, aNewpartitionsi; "NewPartitionSize"
0x180025439  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180025440  mov     rcx, r14; this
0x180025443  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180025448  mov     r9, r12; unsigned __int64
0x18002544b  lea     r8, aNewpartitionof; "NewPartitionOffset"
0x180025452  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180025459  mov     rcx, r14; this
0x18002545c  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180025461  mov     [rbp+0B0h+var_C8], 0
0x180025469  lea     rdi, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180025470  mov     [rbp+0B0h+var_D0], rdi
0x180025474  lea     rcx, [rbp+0B0h+var_D0]
0x180025478  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002547d  mov     r8, rax; struct PushButtonReset::Partition **
0x180025480  mov     rdx, [r15+0B0h]; unsigned __int64
0x180025487  mov     rcx, r12; unsigned __int64
0x18002548a  call    ?WinRECreateRecoveryPartition@@YAJ_K0PEAPEAVPartition@PushButtonReset@@@Z; WinRECreateRecoveryPartition(unsigned __int64,unsigned __int64,PushButtonReset::Partition * *)
0x18002548f  mov     ebx, eax
0x180025491  xor     r15d, r15d
0x180025494  test    r14, r14
0x180025497  jz      short loc_1800254BF
0x180025499  lea     rax, aCreatewinrepar_0; "CreateWinREPartitionFaield"
0x1800254a0  lea     r8, aCreatewinrepar; "CreateWinREPartitionSucceed"
0x1800254a7  test    ebx, ebx
0x1800254a9  cmovs   r8, rax; unsigned __int16 *
0x1800254ad  mov     r9d, ebx; unsigned int
0x1800254b0  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x1800254b7  mov     rcx, r14; this
0x1800254ba  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x1800254bf  test    ebx, ebx
0x1800254c1  jns     short loc_180025504
0x1800254c3  lea     rax, aFailedToCreate_9; "Failed to create WinRE partition"
0x1800254ca  mov     [rsp+1B0h+var_188], rax
0x1800254cf  mov     [rsp+1B0h+var_190], 270h
0x1800254d7  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800254de  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x1800254e5  mov     edx, ebx
0x1800254e7  mov     ecx, 2
0x1800254ec  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800254f1  nop
0x1800254f2  mov     [rbp+0B0h+var_D0], rdi
0x1800254f6  lea     rcx, [rbp+0B0h+var_D0]
0x1800254fa  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800254ff  jmp     loc_180025255
0x180025504  lea     rcx, [rbp+0B0h+var_C0]; this
0x180025508  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18002550d  nop
0x18002550e  mov     rax, [rbp+0B0h+var_D0]
0x180025512  lea     rcx, [rbp+0B0h+var_D0]
0x180025516  mov     rax, [rax+18h]
0x18002551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002551f  lea     rdx, [rbp+0B0h+var_C0]; struct PushButtonReset::PartitionInfo *
0x180025523  mov     rcx, rax; this
0x180025526  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18002552b  mov     ebx, eax
0x18002552d  test    eax, eax
0x18002552f  jns     short loc_18002556B
0x180025531  lea     rax, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x180025538  mov     [rsp+1B0h+var_188], rax
0x18002553d  mov     [rsp+1B0h+var_190], 275h
0x180025545  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002554c  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x180025553  mov     edx, ebx
0x180025555  mov     ecx, 2
0x18002555a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002555f  nop
0x180025560  lea     rcx, [rbp+0B0h+var_C0]; this
0x180025564  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180025569  jmp     short loc_1800254F2
0x18002556b  lea     rcx, [rsp+1B0h+var_180]
0x180025570  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025575  nop
0x180025576  lea     rcx, [rsp+1B0h+var_178]
0x18002557b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025580  nop
0x180025581  mov     r9d, [rbp+0B0h+var_BC]
0x180025585  mov     r8d, [rbp+0B0h+var_C0]
0x180025589  lea     rdx, aGlobalrootDevi_0; "\\\\?\\GLOBALROOT\\device\\harddisk%u\\"...
0x180025590  lea     rcx, [rsp+1B0h+var_180]
0x180025595  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002559a  lea     rdx, [rsp+1B0h+var_178]
0x18002559f  lea     rcx, [rsp+1B0h+var_180]
0x1800255a4  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800255a9  mov     edi, eax
0x1800255ab  test    eax, eax
0x1800255ad  jns     short loc_1800255EC
0x1800255af  lea     rax, aFailedToGetVol_3; "Failed to get volume name"
0x1800255b6  mov     [rsp+1B0h+var_188], rax
0x1800255bb  mov     [rsp+1B0h+var_190], 27Eh
0x1800255c3  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800255ca  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x1800255d1  mov     edx, edi
0x1800255d3  mov     ecx, 2
0x1800255d8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800255dd  nop
0x1800255de  mov     rcx, [rsp+1B0h+var_178]
0x1800255e3  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800255e7  jmp     loc_180025849
0x1800255ec  mov     rbx, [rsp+1B0h+var_178]
0x1800255f1  mov     r8, rbx
0x1800255f4  lea     rdx, aRepartitionWin_3; "Repartition: WinRE partition volume nam"...
0x1800255fb  xor     ecx, ecx
0x1800255fd  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025602  cmp     [rsi+1C0h], r15
0x180025609  jz      loc_18002576A
0x18002560f  mov     r8, rbx
0x180025612  lea     rdx, aRepartitionSav_4; "Repartition: Save new WinRE partition v"...
0x180025619  xor     ecx, ecx
0x18002561b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025620  mov     rdi, [rsi+1C0h]
0x180025627  lea     rdx, aWinrepartition_0; "WinREPartitionVolumeName"
0x18002562e  lea     rcx, [rsp+1B0h+var_168]
0x180025633  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025638  nop
0x180025639  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180025640  lea     rcx, [rsp+1B0h+var_170]
0x180025645  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002564a  nop
0x18002564b  lea     r9, [rsp+1B0h+var_178]
0x180025650  lea     r8, [rsp+1B0h+var_168]
0x180025655  lea     rdx, [rsp+1B0h+var_170]
0x18002565a  mov     rcx, rdi
0x18002565d  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180025662  mov     edi, eax
0x180025664  mov     rcx, [rsp+1B0h+var_170]
0x180025669  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002566d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025672  nop
0x180025673  mov     rcx, [rsp+1B0h+var_168]
0x180025678  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002567c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025681  test    edi, edi
0x180025683  jns     short loc_1800256BD
0x180025685  lea     rax, aFailedToSaveWi; "Failed to save WinRE partition volume n"...
0x18002568c  mov     [rsp+1B0h+var_188], rax
0x180025691  mov     [rsp+1B0h+var_190], 28Ah
0x180025699  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800256a0  lea     r8, aWinreagentRepa_6; "WinREAgent::Repartition::ExecuteCreateW"...
0x1800256a7  mov     edx, edi
0x1800256a9  mov     ecx, 2
0x1800256ae  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800256b3  nop
0x1800256b4  lea     rcx, [rbx-18h]
0x1800256b8  jmp     loc_180025849
  ... truncated ...
```
