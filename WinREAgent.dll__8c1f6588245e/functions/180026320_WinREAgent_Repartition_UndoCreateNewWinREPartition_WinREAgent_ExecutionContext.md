# WinREAgent::Repartition::UndoCreateNewWinREPartition(WinREAgent::ExecutionContext *)

- ea: `0x180026320`
- end: `0x180026ad7`
- name: `?UndoCreateNewWinREPartition@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `1975`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x1800089d0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180026260`
- `0x180026320`
- `0x180027fdc`
- `0x180030608`
- `0x1800307e0`
- `0x180032480`
- `0x180032ee0`
- `0x18003717c`
- `0x180037344`
- `0x18003d700`
- `0x1800444b4`
- `0x180047d1c`
- `0x18004e5a4`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002637d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800264a7`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026507`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026590`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002697c`: `Failed to save WinRE partition volume name into Rollback info`
- `0x180026715`: `Failed to create WinRE partition`
- `0x1800269a7`: `Repartition: Save repartition has completed`
- `0x1800263a2`: `RepartitionCompleted`
- `0x1800269ce`: `RepartitionCompleted`
- `0x180026369`: `Cannot execute undo without rollback object`
- `0x18002634f`: `Repartition::UndoCreateNewWinREPartition Start`
- `0x180026384`: `WinREAgent::Repartition::UndoCreateNewWinREPartition`
- `0x1800264ae`: `WinREAgent::Repartition::UndoCreateNewWinREPartition`
- `0x18002650e`: `WinREAgent::Repartition::UndoCreateNewWinREPartition`
- `0x180026597`: `WinREAgent::Repartition::UndoCreateNewWinREPartition`
- `0x1800263fb`: `Repartition: Repartition was completed, skip undo`
- `0x180026493`: `Failed to read target WinRE partition offset from Rollback info`
- `0x1800265a2`: `Repartition: Find new WinRE partition, use it for rollback`
- `0x180026618`: `Repartition: Failed to find new WinRE partition, assume not created`
- `0x1800266ac`: `Failed to read target WinRE partition size from Rollback info`
- `0x1800266dc`: `Repartition: Create WinRE partition with target partition size [%llu]`
- `0x18002673b`: `Repartition: Continue rollback to create old WinRE partition`
- `0x180026a54`: `Repartition::UndoCreateNewWinREPartition Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall WinREAgent::Repartition::UndoCreateNewWinREPartition(struct WinREAgent::ExecutionContext *a1)
{
  __int64 v2; // rbx
  char HasKey; // bl
  __int64 v5; // rbx
  int Key; // ebx
  WinREAgent *v7; // rax
  struct PushButtonReset::Disk **v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  struct PushButtonReset::Partition **v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  PushButtonReset::Partition *v14; // rax
  int Info; // eax
  __int64 v16; // rbx
  struct PushButtonReset::Partition **v17; // rax
  int v18; // eax
  PushButtonReset::Partition *v19; // rbx
  PushButtonReset::Partition *v20; // rax
  unsigned __int64 v21; // rbx
  __int64 v22; // rdi
  int v23; // edi
  __int64 v24; // rdi
  int v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v32[3]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v33[10]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+C4h] [rbp-3Ch]
  __int64 v37; // [rsp+D0h] [rbp-30h]

  PushButtonReset::Logging::Trace(0, L"Repartition::UndoCreateNewWinREPartition Start");
  v2 = *((_QWORD *)a1 + 56);
  if ( !v2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::Repartition::UndoCreateNewWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      1073,
      L"Cannot execute undo without rollback object");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v26,
    (__int64)L"RepartitionCompleted");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v27,
    (__int64)L"RepartitionInfo");
  HasKey = WinREAgent::RollbackHelper::HasKey(v2, &v27, &v26);
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  if ( HasKey )
  {
    PushButtonReset::Logging::Trace(0, L"Repartition: Repartition was completed, skip undo");
    return 0;
  }
  v31[1] = 0;
  v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v28 = 0;
  v5 = *((_QWORD *)a1 + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v26,
    (__int64)L"TargetWinREPartitionOffset");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v27,
    (__int64)L"RepartitionInfo");
  Key = WinREAgent::RollbackHelper::GetKey(v5, &v27, &v26, &v28);
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  if ( Key >= 0 )
  {
    v32[1] = 0;
    v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    v7 = (WinREAgent *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v32);
    Key = WinREAgent::WinREGetOSDisk(v7, v8);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::Repartition::UndoCreateNewWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        1098,
        L"Failed to get Disk for OS");
      v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
LABEL_34:
      RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v32);
      goto LABEL_35;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
    v10 = v28;
    PushButtonReset::Logging::Trace(
      0,
      L"Repartition: Search for new WinRE partition on OS Disk [%u] and offset [%llu]",
      *(unsigned int *)(v9 + 16),
      v28);
    v11 = (struct PushButtonReset::Partition **)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 8LL))(v31);
    v12 = (*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
    v13 = PushButtonReset::Partition::FindByOffset(*(_DWORD *)(v12 + 16), v10, v11);
    if ( v13 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v13,
        "WinREAgent::Repartition::UndoCreateNewWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        1111,
        L"Repartition: Failed to find new WinRE partition, assume not created");
      v27 = 0;
      v16 = *((_QWORD *)a1 + 56);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v26,
        (__int64)L"TargetWinREPartitionSize");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)L"RepartitionInfo");
      Key = WinREAgent::RollbackHelper::GetKey(v16, &v28, &v26, &v27);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      if ( Key < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Key,
          "WinREAgent::Repartition::UndoCreateNewWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          1118,
          L"Failed to read target WinRE partition size from Rollback info");
        goto LABEL_33;
      }
      PushButtonReset::Logging::Trace(0, L"Repartition: Create WinRE partition with target partition size [%llu]", v27);
      v17 = (struct PushButtonReset::Partition **)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 8LL))(v31);
      v18 = WinRECreateRecoveryPartition(v10, v27, v17);
      if ( v18 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v18,
          "WinREAgent::Repartition::UndoCreateNewWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          1129,
          L"Failed to create WinRE partition");
        PushButtonReset::Logging::Trace(0, L"Repartition: Continue rollback to create old WinRE partition");
        Key = 0;
        goto LABEL_33;
      }
    }
    else
    {
      PushButtonReset::Logging::Trace(0, L"Repartition: Find new WinRE partition, use it for rollback");
    }
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v33);
    v14 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
    Info = PushButtonReset::Partition::GetInfo(v14, (struct PushButtonReset::PartitionInfo *)v33);
    Key = Info;
    if ( Info >= 0 )
    {
      if ( v36 )
        goto LABEL_24;
      PushButtonReset::Logging::Trace(0, L"Repartition: New WinRE partition is raw, format it");
      v19 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)&pszFormat);
      Key = PushButtonReset::Partition::Format(v19);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      if ( Key < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Key,
          "WinREAgent::Repartition::UndoCreateNewWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          1144,
          L"Failed to format the recovery partition");
        goto LABEL_14;
      }
      v20 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
      Info = PushButtonReset::Partition::GetInfo(v20, (struct PushButtonReset::PartitionInfo *)v33);
      Key = Info;
      if ( Info >= 0 )
      {
LABEL_24:
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition info");
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition offset: [%llu]", v34);
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Size: [%llu]", v35);
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Available space: [%llu]", v37);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v27);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v26,
          L"\\\\?\\GLOBALROOT\\device\\harddisk%u\\partition%u\\",
          v33[0],
          v33[1]);
        Key = PushButtonReset::Path::GetVolume(&v26, &v27);
        if ( Key >= 0 )
        {
          v21 = v27;
          PushButtonReset::Logging::Trace(0, L"WinRE partition volume name: [%s]", v27);
          PushButtonReset::Logging::Trace(0, L"Repartition: Save new WinRE partition volume name: [%s]", v21);
          v22 = *((_QWORD *)a1 + 56);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v29,
            (__int64)L"WinREPartitionVolumeName");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v28,
            (__int64)L"RepartitionInfo");
          v23 = WinREAgent::RollbackHelper::WriteToConfig(v22, &v28, &v29, &v27);
          ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
          if ( v23 >= 0 )
          {
            PushButtonReset::Logging::Trace(0, L"Repartition: Save repartition has completed");
            v24 = *((_QWORD *)a1 + 56);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v30,
              (__int64)L"Yes");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v28,
              (__int64)L"RepartitionCompleted");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v29,
              (__int64)L"RepartitionInfo");
            v23 = WinREAgent::RollbackHelper::WriteToConfig(v24, &v29, &v28, &v30);
            ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
            if ( v23 >= 0 )
              PushButtonReset::Logging::Trace(0, L"Repartition::UndoCreateNewWinREPartition Completed");
            else
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v23,
                "WinREAgent::Repartition::UndoCreateNewWinREPartition",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
                1180,
                L"Failed to save repartition has cmpleted");
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v23,
              "WinREAgent::Repartition::UndoCreateNewWinREPartition",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
              1173,
              L"Failed to save WinRE partition volume name into Rollback info");
          }
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
          PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v33);
          Key = v23;
          goto LABEL_33;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Key,
          "WinREAgent::Repartition::UndoCreateNewWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          1163,
          L"Failed to get volume name");
        ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
        goto LABEL_14;
      }
      v25 = 1147;
    }
    else
    {
      v25 = 1138;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::Repartition::UndoCreateNewWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      v25,
      L"Failed to get WinRE partition info");
LABEL_14:
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v33);
LABEL_33:
    v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    goto LABEL_34;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Key,
    "WinREAgent::Repartition::UndoCreateNewWinREPartition",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    1093,
    L"Failed to read target WinRE partition offset from Rollback info");
LABEL_35:
  v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v31);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180026320  mov     [rsp-8+arg_8], rbx
0x180026325  mov     [rsp-8+arg_10], rsi
0x18002632a  push    rbp
0x18002632b  push    rdi
0x18002632c  push    r13
0x18002632e  push    r14
0x180026330  push    r15
0x180026332  lea     rbp, [rsp-10h]
0x180026337  sub     rsp, 110h
0x18002633e  mov     rax, cs:__security_cookie
0x180026345  xor     rax, rsp
0x180026348  mov     [rbp+30h+var_30], rax
0x18002634c  mov     r15, rcx
0x18002634f  lea     rdx, aRepartitionUnd_5; "Repartition::UndoCreateNewWinREPartitio"...
0x180026356  xor     ecx, ecx
0x180026358  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002635d  mov     rbx, [r15+1C0h]
0x180026364  test    rbx, rbx
0x180026367  jnz     short loc_1800263A2
0x180026369  lea     rax, aCannotExecuteU; "Cannot execute undo without rollback ob"...
0x180026370  mov     [rsp+130h+var_108], rax
0x180026375  mov     [rsp+130h+var_110], 431h
0x18002637d  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026384  lea     r8, aWinreagentRepa_0; "WinREAgent::Repartition::UndoCreateNewW"...
0x18002638b  mov     edx, 80070057h
0x180026390  lea     ecx, [rbx+2]
0x180026393  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026398  mov     eax, 80070057h
0x18002639d  jmp     loc_180026AAF
0x1800263a2  lea     rdx, aRepartitioncom; "RepartitionCompleted"
0x1800263a9  lea     rcx, [rsp+130h+var_100]
0x1800263ae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800263b3  nop
0x1800263b4  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x1800263bb  lea     rcx, [rsp+130h+var_F8]
0x1800263c0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800263c5  nop
0x1800263c6  lea     r8, [rsp+130h+var_100]
0x1800263cb  lea     rdx, [rsp+130h+var_F8]
0x1800263d0  mov     rcx, rbx
0x1800263d3  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800263d8  mov     bl, al
0x1800263da  mov     rcx, [rsp+130h+var_F8]
0x1800263df  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800263e3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800263e8  nop
0x1800263e9  mov     rcx, [rsp+130h+var_100]
0x1800263ee  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800263f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800263f7  test    bl, bl
0x1800263f9  jz      short loc_180026410
0x1800263fb  lea     rdx, aRepartitionRep_0; "Repartition: Repartition was completed,"...
0x180026402  xor     ecx, ecx
0x180026404  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026409  xor     eax, eax
0x18002640b  jmp     loc_180026AAF
0x180026410  mov     [rsp+130h+var_D0], 0
0x180026419  lea     r13, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180026420  mov     [rsp+130h+var_D8], r13
0x180026425  mov     [rsp+130h+var_F0], 0
0x18002642e  mov     rbx, [r15+1C0h]
0x180026435  lea     rdx, aTargetwinrepar_0; "TargetWinREPartitionOffset"
0x18002643c  lea     rcx, [rsp+130h+var_100]
0x180026441  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026446  nop
0x180026447  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x18002644e  lea     rcx, [rsp+130h+var_F8]
0x180026453  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026458  nop
0x180026459  lea     r9, [rsp+130h+var_F0]
0x18002645e  lea     r8, [rsp+130h+var_100]
0x180026463  lea     rdx, [rsp+130h+var_F8]
0x180026468  mov     rcx, rbx
0x18002646b  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_K@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180026470  mov     ebx, eax
0x180026472  mov     rcx, [rsp+130h+var_F8]
0x180026477  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002647b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026480  nop
0x180026481  mov     rcx, [rsp+130h+var_100]
0x180026486  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002648a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002648f  test    ebx, ebx
0x180026491  jns     short loc_1800264C6
0x180026493  lea     rax, aFailedToReadTa; "Failed to read target WinRE partition o"...
0x18002649a  mov     [rsp+130h+var_108], rax
0x18002649f  mov     [rsp+130h+var_110], 445h
0x1800264a7  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800264ae  lea     r8, aWinreagentRepa_0; "WinREAgent::Repartition::UndoCreateNewW"...
0x1800264b5  mov     edx, ebx
0x1800264b7  mov     ecx, 2
0x1800264bc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800264c1  jmp     loc_180026A9E
0x1800264c6  mov     [rsp+130h+var_C0], 0
0x1800264cf  lea     rdi, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x1800264d6  mov     [rsp+130h+var_C8], rdi
0x1800264db  lea     rcx, [rsp+130h+var_C8]
0x1800264e0  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800264e5  mov     rcx, rax; this
0x1800264e8  call    ?WinREGetOSDisk@WinREAgent@@YAJPEAPEAVDisk@PushButtonReset@@@Z; WinREAgent::WinREGetOSDisk(PushButtonReset::Disk * *)
0x1800264ed  mov     ebx, eax
0x1800264ef  test    eax, eax
0x1800264f1  jns     short loc_18002652C
0x1800264f3  lea     rax, aFailedToGetDis_0; "Failed to get Disk for OS"
0x1800264fa  mov     [rsp+130h+var_108], rax
0x1800264ff  mov     [rsp+130h+var_110], 44Ah
0x180026507  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002650e  lea     r8, aWinreagentRepa_0; "WinREAgent::Repartition::UndoCreateNewW"...
0x180026515  mov     edx, ebx
0x180026517  mov     ecx, 2
0x18002651c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026521  nop
0x180026522  mov     [rsp+130h+var_C8], rdi
0x180026527  jmp     loc_180026A93
0x18002652c  mov     rax, [rsp+130h+var_C8]
0x180026531  lea     rcx, [rsp+130h+var_C8]
0x180026536  mov     rax, [rax+18h]
0x18002653a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002653f  mov     rdi, [rsp+130h+var_F0]
0x180026544  mov     r9, rdi
0x180026547  mov     r8d, [rax+10h]
0x18002654b  lea     rdx, aRepartitionSea_0; "Repartition: Search for new WinRE parti"...
0x180026552  xor     ecx, ecx
0x180026554  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026559  mov     rax, [rsp+130h+var_D8]
0x18002655e  lea     rcx, [rsp+130h+var_D8]
0x180026563  mov     rax, [rax+8]
0x180026567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002656c  mov     rbx, rax
0x18002656f  mov     rcx, [rsp+130h+var_C8]
0x180026574  mov     rax, [rcx+18h]
0x180026578  lea     rcx, [rsp+130h+var_C8]
0x18002657d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026582  mov     r8, rbx; struct PushButtonReset::Partition **
0x180026585  mov     rdx, rdi; unsigned __int64
0x180026588  mov     ecx, [rax+10h]; unsigned int
0x18002658b  call    ?FindByOffset@Partition@PushButtonReset@@SAJK_KPEAPEAV12@@Z; PushButtonReset::Partition::FindByOffset(ulong,unsigned __int64,PushButtonReset::Partition * *)
0x180026590  lea     rsi, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026597  lea     r14, aWinreagentRepa_0; "WinREAgent::Repartition::UndoCreateNewW"...
0x18002659e  test    eax, eax
0x1800265a0  js      short loc_180026618
0x1800265a2  lea     rdx, aRepartitionFin_0; "Repartition: Find new WinRE partition, "...
0x1800265a9  xor     ecx, ecx
0x1800265ab  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800265b0  lea     rcx, [rbp+30h+var_B0]; this
0x1800265b4  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x1800265b9  nop
0x1800265ba  mov     rax, [rsp+130h+var_D8]
0x1800265bf  lea     rcx, [rsp+130h+var_D8]
0x1800265c4  mov     rax, [rax+18h]
0x1800265c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265cd  lea     rdx, [rbp+30h+var_B0]; struct PushButtonReset::PartitionInfo *
0x1800265d1  mov     rcx, rax; this
0x1800265d4  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x1800265d9  mov     ebx, eax
0x1800265db  test    eax, eax
0x1800265dd  jns     loc_180026750
0x1800265e3  lea     rcx, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x1800265ea  mov     [rsp+130h+var_108], rcx
0x1800265ef  mov     [rsp+130h+var_110], 472h
0x1800265f7  mov     edx, eax
0x1800265f9  mov     r8, r14
0x1800265fc  mov     r9, rsi
0x1800265ff  mov     ecx, 2
0x180026604  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026609  nop
0x18002660a  lea     rcx, [rbp+30h+var_B0]; this
0x18002660e  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180026613  jmp     loc_180026A87
0x180026618  lea     rcx, aRepartitionFai_0; "Repartition: Failed to find new WinRE p"...
0x18002661f  mov     [rsp+130h+var_108], rcx
0x180026624  mov     [rsp+130h+var_110], 457h
0x18002662c  mov     r9, rsi
0x18002662f  mov     r8, r14
0x180026632  mov     edx, eax
0x180026634  mov     ecx, 1
0x180026639  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002663e  mov     [rsp+130h+var_F8], 0
0x180026647  mov     rbx, [r15+1C0h]
0x18002664e  lea     rdx, aTargetwinrepar; "TargetWinREPartitionSize"
0x180026655  lea     rcx, [rsp+130h+var_100]
0x18002665a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002665f  nop
0x180026660  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180026667  lea     rcx, [rsp+130h+var_F0]
0x18002666c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026671  nop
0x180026672  lea     r9, [rsp+130h+var_F8]
0x180026677  lea     r8, [rsp+130h+var_100]
0x18002667c  lea     rdx, [rsp+130h+var_F0]
0x180026681  mov     rcx, rbx
0x180026684  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_K@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180026689  mov     ebx, eax
0x18002668b  mov     rcx, [rsp+130h+var_F0]
0x180026690  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026694  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026699  nop
0x18002669a  mov     rcx, [rsp+130h+var_100]
0x18002669f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800266a3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800266a8  test    ebx, ebx
0x1800266aa  jns     short loc_1800266D7
0x1800266ac  lea     rax, aFailedToReadTa_0; "Failed to read target WinRE partition s"...
0x1800266b3  mov     [rsp+130h+var_108], rax
0x1800266b8  mov     [rsp+130h+var_110], 45Eh
0x1800266c0  mov     r9, rsi
0x1800266c3  mov     r8, r14
0x1800266c6  mov     edx, ebx
0x1800266c8  mov     ecx, 2
0x1800266cd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800266d2  jmp     loc_180026A87
0x1800266d7  mov     r8, [rsp+130h+var_F8]
0x1800266dc  lea     rdx, aRepartitionCre_0; "Repartition: Create WinRE partition wit"...
0x1800266e3  xor     ecx, ecx
0x1800266e5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800266ea  mov     rax, [rsp+130h+var_D8]
0x1800266ef  lea     rcx, [rsp+130h+var_D8]
0x1800266f4  mov     rax, [rax+8]
0x1800266f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266fd  mov     r8, rax; struct PushButtonReset::Partition **
0x180026700  mov     rdx, [rsp+130h+var_F8]; unsigned __int64
0x180026705  mov     rcx, rdi; unsigned __int64
0x180026708  call    ?WinRECreateRecoveryPartition@@YAJ_K0PEAPEAVPartition@PushButtonReset@@@Z; WinRECreateRecoveryPartition(unsigned __int64,unsigned __int64,PushButtonReset::Partition * *)
0x18002670d  test    eax, eax
0x18002670f  jns     loc_1800265B0
0x180026715  lea     rcx, aFailedToCreate_9; "Failed to create WinRE partition"
0x18002671c  mov     [rsp+130h+var_108], rcx
0x180026721  mov     [rsp+130h+var_110], 469h
0x180026729  mov     r9, rsi
0x18002672c  mov     r8, r14
0x18002672f  mov     edx, eax
0x180026731  mov     ecx, 2
0x180026736  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002673b  lea     rdx, aRepartitionCon_0; "Repartition: Continue rollback to creat"...
0x180026742  xor     ecx, ecx
0x180026744  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026749  xor     ebx, ebx
0x18002674b  jmp     loc_180026A87
0x180026750  cmp     [rbp+30h+var_6C], 0
0x180026754  jnz     loc_18002681F
0x18002675a  lea     rdx, aRepartitionNew; "Repartition: New WinRE partition is raw"...
0x180026761  xor     ecx, ecx
0x180026763  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026768  mov     rax, [rsp+130h+var_D8]
0x18002676d  lea     rcx, [rsp+130h+var_D8]
0x180026772  mov     rax, [rax+18h]
0x180026776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002677b  mov     rbx, rax
0x18002677e  lea     rdx, pszFormat
0x180026785  lea     rcx, [rsp+130h+var_F0]
0x18002678a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002678f  nop
0x180026790  mov     byte ptr [rsp+130h+var_108], 0
0x180026795  mov     [rsp+130h+var_110], 0
0x18002679d  mov     r9b, 1
0x1800267a0  lea     r8, [rsp+130h+var_F0]
0x1800267a5  mov     edx, 1
0x1800267aa  mov     rcx, rbx; this
0x1800267ad  call    ?Format@Partition@PushButtonReset@@QEAAJW4FilesystemType@2@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NK2@Z; PushButtonReset::Partition::Format(PushButtonReset::FilesystemType,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ulong,bool)
0x1800267b2  mov     ebx, eax
0x1800267b4  mov     rcx, [rsp+130h+var_F0]
0x1800267b9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800267bd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800267c2  test    ebx, ebx
0x1800267c4  jns     short loc_1800267E1
0x1800267c6  lea     rax, aFailedToFormat; "Failed to format the recovery partition"
0x1800267cd  mov     [rsp+130h+var_108], rax
0x1800267d2  mov     [rsp+130h+var_110], 478h
0x1800267da  mov     edx, ebx
0x1800267dc  jmp     loc_1800265F9
0x1800267e1  mov     rax, [rsp+130h+var_D8]
0x1800267e6  lea     rcx, [rsp+130h+var_D8]
0x1800267eb  mov     rax, [rax+18h]
0x1800267ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267f4  lea     rdx, [rbp+30h+var_B0]; struct PushButtonReset::PartitionInfo *
0x1800267f8  mov     rcx, rax; this
0x1800267fb  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x180026800  mov     ebx, eax
0x180026802  test    eax, eax
0x180026804  jns     short loc_18002681F
0x180026806  lea     rcx, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x18002680d  mov     [rsp+130h+var_108], rcx
0x180026812  mov     [rsp+130h+var_110], 47Bh
0x18002681a  jmp     loc_1800265F7
0x18002681f  lea     rdx, aRepartitionWin_2; "Repartition: WinRE partition info"
0x180026826  xor     ecx, ecx
0x180026828  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002682d  mov     r8, [rbp+30h+var_88]
0x180026831  lea     rdx, aRepartitionWin; "Repartition: WinRE partition offset: [%"...
0x180026838  xor     ecx, ecx
0x18002683a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002683f  mov     r8, [rbp+30h+var_80]
0x180026843  lea     rdx, aRepartitionWin_5; "Repartition: WinRE partition Size: [%ll"...
0x18002684a  xor     ecx, ecx
0x18002684c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026851  mov     r8, [rbp+30h+var_60]
0x180026855  lea     rdx, aRepartitionWin_0; "Repartition: WinRE partition Available "...
0x18002685c  xor     ecx, ecx
0x18002685e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026863  lea     rcx, [rsp+130h+var_F8]
  ... truncated ...
```
