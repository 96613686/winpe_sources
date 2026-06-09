# WinREAgent::Repartition::ExecuteDeleteWinREPartition(WinREAgent::ExecutionContext const *)

- ea: `0x1800258b8`
- end: `0x180025c6c`
- name: `?ExecuteDeleteWinREPartition@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@@Z`
- size: `948`
- prototype: `__int64 __fastcall(WinREAgent::Repartition *__hidden this, const struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180025ef0`

## callees

- `0x1800049a4`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x1800258b8`
- `0x180026260`
- `0x18002e06c`
- `0x18003207c`
- `0x180032504`
- `0x18003717c`
- `0x180037344`
- `0x18003b4dc`
- `0x18003bbf4`
- `0x1800478bc`
- `0x180047d1c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180025935`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025995`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025a11`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025c07`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002593c`: `WinREAgent::Repartition::ExecuteDeleteWinREPartition`
- `0x18002599c`: `WinREAgent::Repartition::ExecuteDeleteWinREPartition`
- `0x180025a18`: `WinREAgent::Repartition::ExecuteDeleteWinREPartition`
- `0x180025c0e`: `WinREAgent::Repartition::ExecuteDeleteWinREPartition`
- `0x180025ab4`: `Failed to save WinRE partition volume name into Rollback info`
- `0x180025b43`: `Failed to save WinRE partition volume name into Rollback info`
- `0x180025bc9`: `DeleteWinREPartitionSucceed`
- `0x180025bc2`: `DeleteWinREPartitionFailed`
- `0x180025bf3`: `Failed to delete partition [%u] from disk`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinREAgent::Repartition::ExecuteDeleteWinREPartition(
        WinREAgent::Repartition *this,
        const struct WinREAgent::ExecutionContext *a2)
{
  WinREAgent::TelemetrySession *v3; // rsi
  __int64 v4; // rax
  signed int Info; // ebx
  PushButtonReset::Partition *v6; // rax
  PushButtonReset::Partition *v7; // rbx
  struct PushButtonReset::Disk **v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rbx
  PushButtonReset::Disk *v11; // rax
  const unsigned __int16 *v12; // r8
  unsigned int v14; // [rsp+30h] [rbp-99h]
  __int64 v15; // [rsp+40h] [rbp-89h] BYREF
  __int64 v16; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v19[4]; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v20; // [rsp+74h] [rbp-55h]
  __int64 v21; // [rsp+98h] [rbp-31h]
  __int64 v22; // [rsp+A0h] [rbp-29h]

  v3 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  PushButtonReset::Logging::Trace(0, L"Repartition: Extend WinRE partition, deleting the existing WinRE partition");
  v17[1] = 0;
  v17[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v4 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v17);
  Info = PushButtonReset::Partition::FindByFilePath((char *)a2 + 120, v4);
  if ( Info >= 0 )
  {
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v19);
    v6 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v17[0] + 24LL))(v17);
    Info = PushButtonReset::Partition::GetInfo(v6, (struct PushButtonReset::PartitionInfo *)v19);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        513,
        L"Failed to get info of WinRE partition");
LABEL_22:
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v19);
      goto LABEL_23;
    }
    v18[1] = 0;
    v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    v7 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v17[0] + 24LL))(v17);
    v8 = (struct PushButtonReset::Disk **)(*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 8LL))(v18);
    Info = PushButtonReset::Partition::GetDisk(v7, v8);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        518,
        L"Failed to get the disk of WinRE");
      goto LABEL_21;
    }
    if ( *((_QWORD *)a2 + 56) )
    {
      PushButtonReset::Logging::Trace(0, L"Repartition: Save current WinRE partition offset: [%llu]", v21);
      v9 = *((_QWORD *)a2 + 56);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v16,
        (__int64)L"OriginalWinREPartitionOffset");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v15,
        (__int64)L"RepartitionInfo");
      Info = WinREAgent::RollbackHelper::WriteToConfig(v9, &v15, &v16, v21);
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
      if ( Info < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          531,
          L"Failed to save WinRE partition volume name into Rollback info");
LABEL_21:
        v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v18);
        goto LABEL_22;
      }
      PushButtonReset::Logging::Trace(0, L"Repartition: Save current WinRE partition size: [%llu]", v22);
      v10 = *((_QWORD *)a2 + 56);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v15,
        (__int64)L"OriginalWinREPartitionSize");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v16,
        (__int64)L"RepartitionInfo");
      Info = WinREAgent::RollbackHelper::WriteToConfig(v10, &v16, &v15, v22);
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      if ( Info < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          537,
          L"Failed to save WinRE partition volume name into Rollback info");
        goto LABEL_21;
      }
      PushButtonReset::Logging::Trace(0, L"Repartition: Add checkpoint [%u]", 7);
      Info = WinREAgent::RollbackHelper::SetCheckpoint(*((_QWORD **)a2 + 56), 7);
      if ( Info < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          541,
          L"Failed to set checkpoint for Repartition");
        goto LABEL_21;
      }
    }
    v11 = (PushButtonReset::Disk *)(*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
    Info = PushButtonReset::Disk::DeletePartition(v11, v20);
    if ( v3 )
    {
      v12 = L"DeleteWinREPartitionSucceed";
      if ( Info < 0 )
        v12 = L"DeleteWinREPartitionFailed";
      WinREAgent::TelemetrySession::TraceDataPoint(v3, L"ExecutionInfoGroup", v12, Info);
    }
    if ( Info < 0 )
    {
      v14 = v20;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        552,
        L"Failed to delete partition [%u] from disk",
        v14);
    }
    goto LABEL_21;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Info,
    "WinREAgent::Repartition::ExecuteDeleteWinREPartition",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    508,
    L"Failed to get partition for WinRE");
LABEL_23:
  v17[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v17);
  return (unsigned int)Info;
}

```

## disassembly

```asm
0x1800258b8  mov     [rsp-8+arg_10], rbx
0x1800258bd  push    rbp
0x1800258be  push    rsi
0x1800258bf  push    rdi
0x1800258c0  push    r12
0x1800258c2  push    r15
0x1800258c4  lea     rbp, [rsp-37h]
0x1800258c9  sub     rsp, 100h
0x1800258d0  mov     rax, cs:__security_cookie
0x1800258d7  xor     rax, rsp
0x1800258da  mov     [rbp+57h+var_30], rax
0x1800258de  mov     rdi, rdx
0x1800258e1  mov     rsi, [rcx+70h]
0x1800258e5  lea     rdx, aRepartitionExt_0; "Repartition: Extend WinRE partition, de"...
0x1800258ec  xor     ecx, ecx
0x1800258ee  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800258f3  mov     [rbp+57h+var_C8], 0
0x1800258fb  lea     r15, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180025902  mov     [rbp+57h+var_D0], r15
0x180025906  lea     rcx, [rbp+57h+var_D0]
0x18002590a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002590f  lea     rcx, [rdi+78h]
0x180025913  mov     rdx, rax
0x180025916  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x18002591b  mov     ebx, eax
0x18002591d  test    eax, eax
0x18002591f  jns     short loc_180025954
0x180025921  lea     rax, aFailedToGetPar_0; "Failed to get partition for WinRE"
0x180025928  mov     [rsp+120h+var_F8], rax
0x18002592d  mov     [rsp+120h+var_100], 1FCh
0x180025935  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002593c  lea     r8, aWinreagentRepa; "WinREAgent::Repartition::ExecuteDeleteW"...
0x180025943  mov     edx, ebx
0x180025945  mov     ecx, 2
0x18002594a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002594f  jmp     loc_180025C3A
0x180025954  lea     rcx, [rbp+57h+var_B0]; this
0x180025958  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18002595d  nop
0x18002595e  mov     rax, [rbp+57h+var_D0]
0x180025962  lea     rcx, [rbp+57h+var_D0]
0x180025966  mov     rax, [rax+18h]
0x18002596a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002596f  lea     rdx, [rbp+57h+var_B0]; struct PushButtonReset::PartitionInfo *
0x180025973  mov     rcx, rax; this
0x180025976  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18002597b  mov     ebx, eax
0x18002597d  test    eax, eax
0x18002597f  jns     short loc_1800259B4
0x180025981  lea     rax, aFailedToGetInf; "Failed to get info of WinRE partition"
0x180025988  mov     [rsp+120h+var_F8], rax
0x18002598d  mov     [rsp+120h+var_100], 201h
0x180025995  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002599c  lea     r8, aWinreagentRepa; "WinREAgent::Repartition::ExecuteDeleteW"...
0x1800259a3  mov     edx, ebx
0x1800259a5  mov     ecx, 2
0x1800259aa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800259af  jmp     loc_180025C30
0x1800259b4  mov     [rbp+57h+var_B8], 0
0x1800259bc  lea     r12, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x1800259c3  mov     [rbp+57h+var_C0], r12
0x1800259c7  mov     rax, [rbp+57h+var_D0]
0x1800259cb  lea     rcx, [rbp+57h+var_D0]
0x1800259cf  mov     rax, [rax+18h]
0x1800259d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259d8  mov     rbx, rax
0x1800259db  mov     rcx, [rbp+57h+var_C0]
0x1800259df  mov     rax, [rcx+8]
0x1800259e3  lea     rcx, [rbp+57h+var_C0]
0x1800259e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259ec  mov     rdx, rax; struct PushButtonReset::Disk **
0x1800259ef  mov     rcx, rbx; this
0x1800259f2  call    ?GetDisk@Partition@PushButtonReset@@QEAAJPEAPEAVDisk@2@@Z; PushButtonReset::Partition::GetDisk(PushButtonReset::Disk * *)
0x1800259f7  mov     ebx, eax
0x1800259f9  test    eax, eax
0x1800259fb  jns     short loc_180025A30
0x1800259fd  lea     rax, aFailedToGetThe_2; "Failed to get the disk of WinRE"
0x180025a04  mov     [rsp+120h+var_F8], rax
0x180025a09  mov     [rsp+120h+var_100], 206h
0x180025a11  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180025a18  lea     r8, aWinreagentRepa; "WinREAgent::Repartition::ExecuteDeleteW"...
0x180025a1f  mov     edx, ebx
0x180025a21  mov     ecx, 2
0x180025a26  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180025a2b  jmp     loc_180025C22
0x180025a30  cmp     qword ptr [rdi+1C0h], 0
0x180025a38  jz      loc_180025B9F
0x180025a3e  mov     r8, [rbp+57h+var_88]
0x180025a42  lea     rdx, aRepartitionSav; "Repartition: Save current WinRE partiti"...
0x180025a49  xor     ecx, ecx
0x180025a4b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025a50  mov     rbx, [rdi+1C0h]
0x180025a57  lea     rdx, aOriginalwinrep_0; "OriginalWinREPartitionOffset"
0x180025a5e  lea     rcx, [rsp+120h+var_D8]
0x180025a63  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025a68  nop
0x180025a69  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180025a70  lea     rcx, [rsp+120h+var_E0]
0x180025a75  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025a7a  nop
0x180025a7b  mov     r9, [rbp+57h+var_88]
0x180025a7f  lea     r8, [rsp+120h+var_D8]
0x180025a84  lea     rdx, [rsp+120h+var_E0]
0x180025a89  mov     rcx, rbx
0x180025a8c  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0_K@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x180025a91  mov     ebx, eax
0x180025a93  mov     rcx, [rsp+120h+var_E0]
0x180025a98  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025a9c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025aa1  nop
0x180025aa2  mov     rcx, [rsp+120h+var_D8]
0x180025aa7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025aab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025ab0  test    ebx, ebx
0x180025ab2  jns     short loc_180025ACD
0x180025ab4  lea     rcx, aFailedToSaveWi; "Failed to save WinRE partition volume n"...
0x180025abb  mov     [rsp+120h+var_F8], rcx
0x180025ac0  mov     [rsp+120h+var_100], 213h
0x180025ac8  jmp     loc_180025A11
0x180025acd  mov     r8, [rbp+57h+var_80]
0x180025ad1  lea     rdx, aRepartitionSav_3; "Repartition: Save current WinRE partiti"...
0x180025ad8  xor     ecx, ecx
0x180025ada  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025adf  mov     rbx, [rdi+1C0h]
0x180025ae6  lea     rdx, aOriginalwinrep; "OriginalWinREPartitionSize"
0x180025aed  lea     rcx, [rsp+120h+var_E0]
0x180025af2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025af7  nop
0x180025af8  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x180025aff  lea     rcx, [rsp+120h+var_D8]
0x180025b04  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025b09  nop
0x180025b0a  mov     r9, [rbp+57h+var_80]
0x180025b0e  lea     r8, [rsp+120h+var_E0]
0x180025b13  lea     rdx, [rsp+120h+var_D8]
0x180025b18  mov     rcx, rbx
0x180025b1b  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0_K@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x180025b20  mov     ebx, eax
0x180025b22  mov     rcx, [rsp+120h+var_D8]
0x180025b27  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025b2b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025b30  nop
0x180025b31  mov     rcx, [rsp+120h+var_E0]
0x180025b36  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180025b3a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025b3f  test    ebx, ebx
0x180025b41  jns     short loc_180025B5C
0x180025b43  lea     rcx, aFailedToSaveWi; "Failed to save WinRE partition volume n"...
0x180025b4a  mov     [rsp+120h+var_F8], rcx
0x180025b4f  mov     [rsp+120h+var_100], 219h
0x180025b57  jmp     loc_180025A11
0x180025b5c  mov     ebx, 7
0x180025b61  mov     r8d, ebx
0x180025b64  lea     rdx, aRepartitionAdd; "Repartition: Add checkpoint [%u]"
0x180025b6b  xor     ecx, ecx
0x180025b6d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025b72  mov     edx, ebx
0x180025b74  mov     rcx, [rdi+1C0h]
0x180025b7b  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x180025b80  mov     ebx, eax
0x180025b82  test    eax, eax
0x180025b84  jns     short loc_180025B9F
0x180025b86  lea     rax, aFailedToSetChe_4; "Failed to set checkpoint for Repartitio"...
0x180025b8d  mov     [rsp+120h+var_F8], rax
0x180025b92  mov     [rsp+120h+var_100], 21Dh
0x180025b9a  jmp     loc_180025A11
0x180025b9f  mov     rax, [rbp+57h+var_C0]
0x180025ba3  lea     rcx, [rbp+57h+var_C0]
0x180025ba7  mov     rax, [rax+18h]
0x180025bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bb0  mov     edx, [rbp+57h+var_AC]; unsigned int
0x180025bb3  mov     rcx, rax; this
0x180025bb6  call    ?DeletePartition@Disk@PushButtonReset@@QEAAJK@Z; PushButtonReset::Disk::DeletePartition(ulong)
0x180025bbb  mov     ebx, eax
0x180025bbd  test    rsi, rsi
0x180025bc0  jz      short loc_180025BE8
0x180025bc2  lea     rax, aDeletewinrepar; "DeleteWinREPartitionFailed"
0x180025bc9  lea     r8, aDeletewinrepar_0; "DeleteWinREPartitionSucceed"
0x180025bd0  test    ebx, ebx
0x180025bd2  cmovs   r8, rax; unsigned __int16 *
0x180025bd6  mov     r9d, ebx; unsigned int
0x180025bd9  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180025be0  mov     rcx, rsi; this
0x180025be3  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x180025be8  test    ebx, ebx
0x180025bea  jns     short loc_180025C22
0x180025bec  mov     eax, [rbp+57h+var_AC]
0x180025bef  mov     [rsp+120h+var_F0], eax
0x180025bf3  lea     rax, aFailedToDelete_5; "Failed to delete partition [%u] from di"...
0x180025bfa  mov     [rsp+120h+var_F8], rax
0x180025bff  mov     [rsp+120h+var_100], 228h
0x180025c07  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180025c0e  lea     r8, aWinreagentRepa; "WinREAgent::Repartition::ExecuteDeleteW"...
0x180025c15  mov     edx, ebx
0x180025c17  mov     ecx, 2
0x180025c1c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180025c21  nop
0x180025c22  mov     [rbp+57h+var_C0], r12
0x180025c26  lea     rcx, [rbp+57h+var_C0]
0x180025c2a  call    ?Release@?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(void)
0x180025c2f  nop
0x180025c30  lea     rcx, [rbp+57h+var_B0]; this
0x180025c34  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180025c39  nop
0x180025c3a  mov     [rbp+57h+var_D0], r15
0x180025c3e  lea     rcx, [rbp+57h+var_D0]
0x180025c42  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180025c47  mov     eax, ebx
0x180025c49  mov     rcx, [rbp+57h+var_30]
0x180025c4d  xor     rcx, rsp; StackCookie
0x180025c50  call    __security_check_cookie
0x180025c55  mov     rbx, [rsp+120h+arg_10]
0x180025c5d  add     rsp, 100h
0x180025c64  pop     r15
0x180025c66  pop     r12
0x180025c68  pop     rdi
0x180025c69  pop     rsi
0x180025c6a  pop     rbp
0x180025c6b  retn
```
