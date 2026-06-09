# WinREAgent::Repartition::UndoShrink(WinREAgent::ExecutionContext *)

- ea: `0x180026ddc`
- end: `0x1800271fd`
- name: `?UndoShrink@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `1057`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x1800049a4`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180026ddc`
- `0x180030608`
- `0x1800307e0`
- `0x18003308c`
- `0x18003717c`
- `0x180037344`
- `0x180039514`
- `0x180047d1c`
- `0x180049b4c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180026e2d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026f4e`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026fab`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800270a4`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027155`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026e52`: `RepartitionCompleted`
- `0x180026e19`: `Cannot execute undo without rollback object`
- `0x180026e34`: `WinREAgent::Repartition::UndoShrink`
- `0x180026f55`: `WinREAgent::Repartition::UndoShrink`
- `0x180026fb2`: `WinREAgent::Repartition::UndoShrink`
- `0x1800270ab`: `WinREAgent::Repartition::UndoShrink`
- `0x18002715c`: `WinREAgent::Repartition::UndoShrink`
- `0x180026eab`: `Repartition::UndoShrink Repartition has completed, keep the status`
- `0x180026eb9`: `Repartition::UndoShrink Completed`
- `0x18002704b`: `Repartition::UndoShrink Completed`
- `0x1800271bc`: `Repartition::UndoShrink Completed`
- `0x180026f3a`: `Failed to get original OS partition size from Rollback info`
- `0x1800270f8`: `Current partition size is already at upper bound. No need to resize`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::Repartition::UndoShrink(struct WinREAgent::ExecutionContext *a1)
{
  __int64 v2; // rbx
  char HasKey; // bl
  __int64 v5; // rbx
  int Key; // ebx
  WinREAgent *v7; // rax
  struct PushButtonReset::Partition **v8; // rdx
  PushButtonReset::Partition *v9; // rax
  unsigned __int64 v10; // rbx
  PushButtonReset::Partition *v11; // rax
  int v12; // edi
  unsigned __int64 v13; // rdi
  PushButtonReset::Partition *v14; // rax
  PushButtonReset::Partition *v15; // rax
  __int64 v16; // [rsp+30h] [rbp-89h] BYREF
  __int64 v17; // [rsp+38h] [rbp-81h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v20[48]; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp-29h]

  PushButtonReset::Logging::Trace(0, L"Repartition::UndoShrink Start");
  v2 = *((_QWORD *)a1 + 56);
  if ( !v2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::Repartition::UndoShrink",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      763,
      L"Cannot execute undo without rollback object");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"RepartitionCompleted");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"RepartitionInfo");
  HasKey = WinREAgent::RollbackHelper::HasKey(v2, &v16, &v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  if ( HasKey )
  {
    PushButtonReset::Logging::Trace(0, L"Repartition::UndoShrink Repartition has completed, keep the status");
    PushButtonReset::Logging::Trace(0, L"Repartition::UndoShrink Completed");
    return 0;
  }
  v18 = 0;
  v5 = *((_QWORD *)a1 + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"OriginalOSPartitionSize");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"RepartitionInfo");
  Key = WinREAgent::RollbackHelper::GetKey(v5, &v17, &v16, &v18);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  if ( Key >= 0 )
  {
    v19[1] = 0;
    v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    v7 = (WinREAgent *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v19);
    Key = WinREAgent::WinREGetOSPartition(v7, v8);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::Repartition::UndoShrink",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        784,
        L"Failed to get partition for OS");
LABEL_27:
      v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
      return (unsigned int)Key;
    }
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v20);
    v9 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
    Key = PushButtonReset::Partition::GetInfo(v9, (struct PushButtonReset::PartitionInfo *)v20);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::Repartition::UndoShrink",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        789,
        L"Failed to get partition info for OS");
LABEL_26:
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v20);
      goto LABEL_27;
    }
    v10 = v18;
    PushButtonReset::Logging::Trace(0, L"Original OS partition size [%llu]", v18);
    PushButtonReset::Logging::Trace(0, L"Current OS partition size: [%llu]", v21);
    if ( v21 >= v10 )
    {
      PushButtonReset::Logging::Trace(0, L"OS partition is larger than original size, no need to undo");
      PushButtonReset::Logging::Trace(0, L"Repartition::UndoShrink Completed");
      Key = 1;
      goto LABEL_26;
    }
    v18 = 0;
    v11 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
    v12 = PushButtonReset::Partition::ComputeResizeBounds(v11, 0, &v18);
    if ( v12 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v12,
        "WinREAgent::Repartition::UndoShrink",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        806,
        L"Failed to get max resize bound for OS partition");
      Key = v12;
      goto LABEL_26;
    }
    v13 = v18;
    PushButtonReset::Logging::Trace(0, L"Max resize bound for OS partition: [%llu]", v18);
    if ( v13 <= v10 )
    {
      Key = 1;
      PushButtonReset::Logging::Trace(
        1,
        L"Original partition size is larger than max resize bound, can only resize to upper bound");
      if ( v13 == v21 )
      {
        PushButtonReset::Logging::Trace(0, L"Current partition size is already at upper bound. No need to resize");
        goto LABEL_25;
      }
      v10 = v13;
    }
    PushButtonReset::Logging::Trace(0, L"Resize OS partition to [%llu]", v10);
    v14 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
    Key = PushButtonReset::Partition::Resize(v14, v10);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::Repartition::UndoShrink",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        828,
        L"Failed to resize OS partition");
      goto LABEL_26;
    }
    v15 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
    Key = PushButtonReset::Partition::GetInfo(v15, (struct PushButtonReset::PartitionInfo *)v20);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::Repartition::UndoShrink",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        831,
        L"Failed to get partition info for OS");
      goto LABEL_26;
    }
    PushButtonReset::Logging::Trace(0, L"Final OS partition size: [%llu]", v21);
LABEL_25:
    PushButtonReset::Logging::Trace(0, L"Repartition::UndoShrink Completed");
    goto LABEL_26;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Key,
    "WinREAgent::Repartition::UndoShrink",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    779,
    L"Failed to get original OS partition size from Rollback info");
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180026ddc  push    rbp
0x180026dde  push    rbx
0x180026ddf  push    rdi
0x180026de0  push    r14
0x180026de2  lea     rbp, [rsp-3Fh]
0x180026de7  sub     rsp, 0F8h
0x180026dee  mov     rax, cs:__security_cookie
0x180026df5  xor     rax, rsp
0x180026df8  mov     [rbp+57h+var_30], rax
0x180026dfc  mov     rdi, rcx
0x180026dff  lea     rdx, aRepartitionUnd_3; "Repartition::UndoShrink Start"
0x180026e06  xor     ecx, ecx
0x180026e08  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026e0d  mov     rbx, [rdi+1C0h]
0x180026e14  test    rbx, rbx
0x180026e17  jnz     short loc_180026E52
0x180026e19  lea     rax, aCannotExecuteU; "Cannot execute undo without rollback ob"...
0x180026e20  mov     [rsp+110h+var_E8], rax
0x180026e25  mov     [rsp+110h+var_F0], 2FBh
0x180026e2d  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026e34  lea     r8, aWinreagentRepa_5; "WinREAgent::Repartition::UndoShrink"
0x180026e3b  mov     edx, 80070057h
0x180026e40  lea     ecx, [rbx+2]
0x180026e43  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026e48  mov     eax, 80070057h
0x180026e4d  jmp     loc_1800271E4
0x180026e52  lea     rdx, aRepartitioncom; "RepartitionCompleted"
0x180026e59  lea     rcx, [rsp+110h+var_D8]
0x180026e5e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026e63  nop
0x180026e64  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180026e6b  lea     rcx, [rsp+110h+var_E0]
0x180026e70  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026e75  nop
0x180026e76  lea     r8, [rsp+110h+var_D8]
0x180026e7b  lea     rdx, [rsp+110h+var_E0]
0x180026e80  mov     rcx, rbx
0x180026e83  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180026e88  mov     bl, al
0x180026e8a  mov     rcx, [rsp+110h+var_E0]
0x180026e8f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026e93  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026e98  nop
0x180026e99  mov     rcx, [rsp+110h+var_D8]
0x180026e9e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026ea2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026ea7  test    bl, bl
0x180026ea9  jz      short loc_180026ECE
0x180026eab  lea     rdx, aRepartitionUnd; "Repartition::UndoShrink Repartition has"...
0x180026eb2  xor     ecx, ecx
0x180026eb4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026eb9  lea     rdx, aRepartitionUnd_1; "Repartition::UndoShrink Completed"
0x180026ec0  xor     ecx, ecx
0x180026ec2  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026ec7  xor     eax, eax
0x180026ec9  jmp     loc_1800271E4
0x180026ece  mov     [rbp+57h+var_D0], 0
0x180026ed6  mov     rbx, [rdi+1C0h]
0x180026edd  lea     rdx, aOriginalospart; "OriginalOSPartitionSize"
0x180026ee4  lea     rcx, [rsp+110h+var_E0]
0x180026ee9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026eee  nop
0x180026eef  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180026ef6  lea     rcx, [rsp+110h+var_D8]
0x180026efb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026f00  nop
0x180026f01  lea     r9, [rbp+57h+var_D0]
0x180026f05  lea     r8, [rsp+110h+var_E0]
0x180026f0a  lea     rdx, [rsp+110h+var_D8]
0x180026f0f  mov     rcx, rbx
0x180026f12  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_K@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180026f17  mov     ebx, eax
0x180026f19  mov     rcx, [rsp+110h+var_D8]
0x180026f1e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026f22  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026f27  nop
0x180026f28  mov     rcx, [rsp+110h+var_E0]
0x180026f2d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026f31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026f36  test    ebx, ebx
0x180026f38  jns     short loc_180026F6D
0x180026f3a  lea     rax, aFailedToGetOri; "Failed to get original OS partition siz"...
0x180026f41  mov     [rsp+110h+var_E8], rax
0x180026f46  mov     [rsp+110h+var_F0], 30Bh
0x180026f4e  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026f55  lea     r8, aWinreagentRepa_5; "WinREAgent::Repartition::UndoShrink"
0x180026f5c  mov     edx, ebx
0x180026f5e  mov     ecx, 2
0x180026f63  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026f68  jmp     loc_1800271E2
0x180026f6d  mov     [rbp+57h+var_C0], 0
0x180026f75  lea     r14, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180026f7c  mov     [rbp+57h+var_C8], r14
0x180026f80  lea     rcx, [rbp+57h+var_C8]
0x180026f84  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180026f89  mov     rcx, rax; this
0x180026f8c  call    ?WinREGetOSPartition@WinREAgent@@YAJPEAPEAVPartition@PushButtonReset@@@Z; WinREAgent::WinREGetOSPartition(PushButtonReset::Partition * *)
0x180026f91  mov     ebx, eax
0x180026f93  test    eax, eax
0x180026f95  jns     short loc_180026FCA
0x180026f97  lea     rax, aFailedToGetPar_6; "Failed to get partition for OS"
0x180026f9e  mov     [rsp+110h+var_E8], rax
0x180026fa3  mov     [rsp+110h+var_F0], 310h
0x180026fab  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026fb2  lea     r8, aWinreagentRepa_5; "WinREAgent::Repartition::UndoShrink"
0x180026fb9  mov     edx, ebx
0x180026fbb  mov     ecx, 2
0x180026fc0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026fc5  jmp     loc_1800271D5
0x180026fca  lea     rcx, [rbp+57h+var_B0]; this
0x180026fce  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180026fd3  nop
0x180026fd4  mov     rax, [rbp+57h+var_C8]
0x180026fd8  lea     rcx, [rbp+57h+var_C8]
0x180026fdc  mov     rax, [rax+18h]
0x180026fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fe5  lea     rdx, [rbp+57h+var_B0]; struct PushButtonReset::PartitionInfo *
0x180026fe9  mov     rcx, rax; this
0x180026fec  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x180026ff1  mov     ebx, eax
0x180026ff3  test    eax, eax
0x180026ff5  jns     short loc_180027010
0x180026ff7  lea     rax, aFailedToGetPar_10; "Failed to get partition info for OS"
0x180026ffe  mov     [rsp+110h+var_E8], rax
0x180027003  mov     [rsp+110h+var_F0], 315h
0x18002700b  jmp     loc_180027155
0x180027010  mov     rbx, [rbp+57h+var_D0]
0x180027014  mov     r8, rbx
0x180027017  lea     rdx, aOriginalOsPart; "Original OS partition size [%llu]"
0x18002701e  xor     ecx, ecx
0x180027020  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027025  mov     r8, [rbp+57h+var_80]
0x180027029  lea     rdx, aCurrentOsParti; "Current OS partition size: [%llu]"
0x180027030  xor     ecx, ecx
0x180027032  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027037  cmp     [rbp+57h+var_80], rbx
0x18002703b  jb      short loc_180027063
0x18002703d  lea     rdx, aOsPartitionIsL; "OS partition is larger than original si"...
0x180027044  xor     ecx, ecx
0x180027046  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002704b  lea     rdx, aRepartitionUnd_1; "Repartition::UndoShrink Completed"
0x180027052  xor     ecx, ecx
0x180027054  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027059  mov     ebx, 1
0x18002705e  jmp     loc_1800271CB
0x180027063  mov     [rbp+57h+var_D0], 0
0x18002706b  mov     rax, [rbp+57h+var_C8]
0x18002706f  lea     rcx, [rbp+57h+var_C8]
0x180027073  mov     rax, [rax+18h]
0x180027077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002707c  lea     r8, [rbp+57h+var_D0]; unsigned __int64 *
0x180027080  xor     edx, edx; unsigned __int64 *
0x180027082  mov     rcx, rax; this
0x180027085  call    ?ComputeResizeBounds@Partition@PushButtonReset@@QEAAJPEA_K0@Z; PushButtonReset::Partition::ComputeResizeBounds(unsigned __int64 *,unsigned __int64 *)
0x18002708a  mov     edi, eax
0x18002708c  test    eax, eax
0x18002708e  jns     short loc_1800270C5
0x180027090  lea     rax, aFailedToGetMax; "Failed to get max resize bound for OS p"...
0x180027097  mov     [rsp+110h+var_E8], rax
0x18002709c  mov     [rsp+110h+var_F0], 326h
0x1800270a4  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800270ab  lea     r8, aWinreagentRepa_5; "WinREAgent::Repartition::UndoShrink"
0x1800270b2  mov     edx, edi
0x1800270b4  mov     ecx, 2
0x1800270b9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800270be  mov     ebx, edi
0x1800270c0  jmp     loc_1800271CB
0x1800270c5  mov     rdi, [rbp+57h+var_D0]
0x1800270c9  mov     r8, rdi
0x1800270cc  lea     rdx, aMaxResizeBound; "Max resize bound for OS partition: [%ll"...
0x1800270d3  xor     ecx, ecx
0x1800270d5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800270da  cmp     rdi, rbx
0x1800270dd  ja      short loc_18002710E
0x1800270df  lea     rdx, aOriginalPartit; "Original partition size is larger than "...
0x1800270e6  mov     ebx, 1
0x1800270eb  mov     ecx, ebx
0x1800270ed  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800270f2  cmp     rdi, [rbp+57h+var_80]
0x1800270f6  jnz     short loc_18002710B
0x1800270f8  lea     rdx, aCurrentPartiti; "Current partition size is already at up"...
0x1800270ff  xor     ecx, ecx
0x180027101  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027106  jmp     loc_1800271BC
0x18002710b  mov     rbx, rdi
0x18002710e  mov     r8, rbx
0x180027111  lea     rdx, aResizeOsPartit; "Resize OS partition to [%llu]"
0x180027118  xor     ecx, ecx
0x18002711a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002711f  mov     rax, [rbp+57h+var_C8]
0x180027123  lea     rcx, [rbp+57h+var_C8]
0x180027127  mov     rax, [rax+18h]
0x18002712b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027130  mov     rdx, rbx; unsigned __int64
0x180027133  mov     rcx, rax; this
0x180027136  call    ?Resize@Partition@PushButtonReset@@QEAAJ_K@Z; PushButtonReset::Partition::Resize(unsigned __int64)
0x18002713b  mov     ebx, eax
0x18002713d  test    eax, eax
0x18002713f  jns     short loc_180027171
0x180027141  lea     rax, aFailedToResize; "Failed to resize OS partition"
0x180027148  mov     [rsp+110h+var_E8], rax
0x18002714d  mov     [rsp+110h+var_F0], 33Ch
0x180027155  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002715c  lea     r8, aWinreagentRepa_5; "WinREAgent::Repartition::UndoShrink"
0x180027163  mov     edx, ebx
0x180027165  mov     ecx, 2
0x18002716a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002716f  jmp     short loc_1800271CB
0x180027171  mov     rax, [rbp+57h+var_C8]
0x180027175  lea     rcx, [rbp+57h+var_C8]
0x180027179  mov     rax, [rax+18h]
0x18002717d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027182  lea     rdx, [rbp+57h+var_B0]; struct PushButtonReset::PartitionInfo *
0x180027186  mov     rcx, rax; this
0x180027189  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18002718e  mov     ebx, eax
0x180027190  test    eax, eax
0x180027192  jns     short loc_1800271AA
0x180027194  lea     rax, aFailedToGetPar_10; "Failed to get partition info for OS"
0x18002719b  mov     [rsp+110h+var_E8], rax
0x1800271a0  mov     [rsp+110h+var_F0], 33Fh
0x1800271a8  jmp     short loc_180027155
0x1800271aa  mov     r8, [rbp+57h+var_80]
0x1800271ae  lea     rdx, aFinalOsPartiti; "Final OS partition size: [%llu]"
0x1800271b5  xor     ecx, ecx
0x1800271b7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800271bc  lea     rdx, aRepartitionUnd_1; "Repartition::UndoShrink Completed"
0x1800271c3  xor     ecx, ecx
0x1800271c5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800271ca  nop
0x1800271cb  lea     rcx, [rbp+57h+var_B0]; this
0x1800271cf  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x1800271d4  nop
0x1800271d5  mov     [rbp+57h+var_C8], r14
0x1800271d9  lea     rcx, [rbp+57h+var_C8]
0x1800271dd  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800271e2  mov     eax, ebx
0x1800271e4  mov     rcx, [rbp+57h+var_30]
0x1800271e8  xor     rcx, rsp; StackCookie
0x1800271eb  call    __security_check_cookie
0x1800271f0  add     rsp, 0F8h
0x1800271f7  pop     r14
0x1800271f9  pop     rdi
0x1800271fa  pop     rbx
0x1800271fb  pop     rbp
0x1800271fc  retn
```
