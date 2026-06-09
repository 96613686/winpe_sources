# WinREGetWinREPartition(WinREAgent::ExecutionContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180028220`
- end: `0x180028899`
- name: `?WinREGetWinREPartition@@YAJPEAVExecutionContext@WinREAgent@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1657`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180026ae0`

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
- `0x180026260`
- `0x180027fdc`
- `0x180028220`
- `0x1800304dc`
- `0x180030608`
- `0x1800307e0`
- `0x180032ee0`
- `0x18003717c`
- `0x180037344`
- `0x18003d700`
- `0x180047d1c`
- `0x18004e5a4`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002826b`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180028386`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180028437`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800284a5`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002858f`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800285cc`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180028668`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002877d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800286d3`: `Failed to create WinRE partition`
- `0x1800282a3`: `RepartitionCompleted`
- `0x180028303`: `Repartition: Repartition was completed, use new WinRE partition for rollback`
- `0x180028372`: `Failed to read WinRE partition volume name from Rollback info`
- `0x180028423`: `Failed to read original WinRE partition offset from Rollback info`
- `0x18002853c`: `Repartition: Find original WinRE partition, use it for rollback`
- `0x1800285b8`: `Repartition: Failed to find original WinRE partition, assume deleted`
- `0x180028654`: `Failed to read original WinRE partition size from Rollback info`
- `0x18002869a`: `Repartition: Create WinRE partition with original partition size [%llu]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WinREGetWinREPartition(__int64 a1, _QWORD *a2)
{
  __int64 v5; // rbx
  __int64 v6; // rbx
  int Volume; // edi
  ATL::CStringData *v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rbx
  int Key; // ebx
  WinREAgent *v12; // rax
  struct PushButtonReset::Disk **v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  struct PushButtonReset::Partition **v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  PushButtonReset::Partition *v19; // rax
  __int64 v20; // rbx
  struct PushButtonReset::Partition **v21; // rax
  ATL::CStringData *v22; // rsi
  int *v23; // r14
  __int64 v24; // rbx
  unsigned __int64 v25; // [rsp+30h] [rbp-99h] BYREF
  __int64 v26; // [rsp+38h] [rbp-91h] BYREF
  __int64 v27; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v31[10]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v32; // [rsp+98h] [rbp-31h]
  __int64 v33; // [rsp+A0h] [rbp-29h]
  __int64 v34; // [rsp+C0h] [rbp-9h]

  if ( !a2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREGetWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      846,
      L"res cannot be null");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
  v5 = *(_QWORD *)(a1 + 448);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v27,
    (__int64)L"RepartitionCompleted");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v25,
    (__int64)L"RepartitionInfo");
  LOBYTE(v5) = WinREAgent::RollbackHelper::HasKey(v5, &v25, &v27);
  ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  if ( !(_BYTE)v5 )
  {
    v28 = 0;
    v10 = *(_QWORD *)(a1 + 448);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v25,
      (__int64)L"OriginalWinREPartitionOffset");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"RepartitionInfo");
    Key = WinREAgent::RollbackHelper::GetKey(v10, &v27, &v25, &v28);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREGetWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        868,
        L"Failed to read original WinRE partition offset from Rollback info");
LABEL_10:
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      return (unsigned int)Key;
    }
    v29[1] = 0;
    v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    v12 = (WinREAgent *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v29);
    Key = WinREAgent::WinREGetOSDisk(v12, v13);
    if ( Key < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREGetWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        873,
        L"Failed to get Disk for OS");
LABEL_13:
      v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v29);
      goto LABEL_10;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 24LL))(v29);
    v15 = v28;
    PushButtonReset::Logging::Trace(
      0,
      L"Repartition: Search for original WinRE partition on OS Disk [%u] and offset [%llu]",
      *(unsigned int *)(v14 + 16),
      v28);
    v30[1] = 0;
    v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    v16 = (struct PushButtonReset::Partition **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v30);
    v17 = (*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 24LL))(v29);
    v18 = PushButtonReset::Partition::FindByOffset(*(_DWORD *)(v17 + 16), v15, v16);
    if ( v18 >= 0 )
    {
      PushButtonReset::Logging::Trace(0, L"Repartition: Find original WinRE partition, use it for rollback");
LABEL_16:
      PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v31);
      v19 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
      Key = PushButtonReset::Partition::GetInfo(v19, (struct PushButtonReset::PartitionInfo *)v31);
      if ( Key >= 0 )
      {
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition info");
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition offset: [%llu]", v32);
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Size: [%llu]", v33);
        PushButtonReset::Logging::Trace(0, L"Repartition: WinRE partition Available space: [%llu]", v34);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v25,
          L"\\\\?\\GLOBALROOT\\device\\harddisk%u\\partition%u\\",
          v31[0],
          v31[1]);
        Volume = PushButtonReset::Path::GetVolume(&v25, &v26);
        if ( Volume < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Volume,
            "WinREGetWinREPartition",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            920,
            L"Failed to get volume name");
          ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
          PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v31);
          v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v30);
          v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v29);
          goto LABEL_6;
        }
        v9 = v26;
        PushButtonReset::Logging::Trace(0, L"WinRE partition volume name: [%s]", v26);
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
        PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v31);
        v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v30);
        v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v29);
LABEL_26:
        v22 = (ATL::CStringData *)(v9 - 24);
        v23 = (int *)(*a2 - 24LL);
        if ( (int *)(v9 - 24) != v23 )
        {
          if ( v23[4] >= 0 && *(_QWORD *)v22 == *(_QWORD *)v23 )
          {
            v24 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v9 - 24);
            ATL::CStringData::Release((ATL::CStringData *)v23);
            *a2 = v24 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v9, *(unsigned int *)(v9 - 16));
          }
        }
        v8 = v22;
        goto LABEL_32;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREGetWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        907,
        L"Failed to get WinRE partition info");
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v31);
      goto LABEL_20;
    }
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v18,
      "WinREGetWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      888,
      L"Repartition: Failed to find original WinRE partition, assume deleted");
    v25 = 0;
    v20 = *(_QWORD *)(a1 + 448);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"OriginalWinREPartitionSize");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v28,
      (__int64)L"RepartitionInfo");
    Key = WinREAgent::RollbackHelper::GetKey(v20, &v28, &v27, &v25);
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    if ( Key >= 0 )
    {
      PushButtonReset::Logging::Trace(
        0,
        L"Repartition: Create WinRE partition with original partition size [%llu]",
        v25);
      v21 = (struct PushButtonReset::Partition **)(*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 8LL))(v30);
      Key = WinRECreateRecoveryPartition(v15, v25, v21);
      if ( Key >= 0 )
        goto LABEL_16;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREGetWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        901,
        L"Failed to create WinRE partition");
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREGetWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        895,
        L"Failed to read original WinRE partition size from Rollback info");
    }
LABEL_20:
    v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v30);
    goto LABEL_13;
  }
  PushButtonReset::Logging::Trace(0, L"Repartition: Repartition was completed, use new WinRE partition for rollback");
  v6 = *(_QWORD *)(a1 + 448);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v25,
    (__int64)L"WinREPartitionVolumeName");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v27,
    (__int64)L"RepartitionInfo");
  Volume = WinREAgent::RollbackHelper::GetKey(v6, &v27, &v25, &v26);
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
  if ( Volume >= 0 )
  {
    v9 = v26;
    goto LABEL_26;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Volume,
    "WinREGetWinREPartition",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    859,
    L"Failed to read WinRE partition volume name from Rollback info");
LABEL_6:
  v8 = (ATL::CStringData *)(v26 - 24);
LABEL_32:
  ATL::CStringData::Release(v8);
  return (unsigned int)Volume;
}

```

## disassembly

```asm
0x180028220  mov     [rsp-8+arg_10], rbx
0x180028225  mov     [rsp-8+arg_18], rsi
0x18002822a  push    rbp
0x18002822b  push    rdi
0x18002822c  push    r13
0x18002822e  push    r14
0x180028230  push    r15
0x180028232  lea     rbp, [rsp-37h]
0x180028237  sub     rsp, 100h
0x18002823e  mov     rax, cs:__security_cookie
0x180028245  xor     rax, rsp
0x180028248  mov     [rbp+57h+var_30], rax
0x18002824c  mov     r15, rdx
0x18002824f  mov     rdi, rcx
0x180028252  test    rdx, rdx
0x180028255  jnz     short loc_180028291
0x180028257  lea     rax, aResCannotBeNul; "res cannot be null"
0x18002825e  mov     [rsp+120h+var_F8], rax
0x180028263  mov     [rsp+120h+var_100], 34Eh
0x18002826b  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180028272  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x180028279  mov     edx, 80070057h
0x18002827e  lea     ecx, [r15+2]
0x180028282  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180028287  mov     eax, 80070057h
0x18002828c  jmp     loc_180028871
0x180028291  lea     rcx, [rsp+120h+var_E8]
0x180028296  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002829b  nop
0x18002829c  mov     rbx, [rdi+1C0h]
0x1800282a3  lea     rdx, aRepartitioncom; "RepartitionCompleted"
0x1800282aa  lea     rcx, [rsp+120h+var_E0]
0x1800282af  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800282b4  nop
0x1800282b5  lea     rsi, aRepartitioninf; "RepartitionInfo"
0x1800282bc  mov     rdx, rsi
0x1800282bf  lea     rcx, [rsp+120h+var_F0]
0x1800282c4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800282c9  nop
0x1800282ca  lea     r8, [rsp+120h+var_E0]
0x1800282cf  lea     rdx, [rsp+120h+var_F0]
0x1800282d4  mov     rcx, rbx
0x1800282d7  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800282dc  mov     bl, al
0x1800282de  mov     rcx, [rsp+120h+var_F0]
0x1800282e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800282e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800282ec  nop
0x1800282ed  mov     rcx, [rsp+120h+var_E0]
0x1800282f2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800282f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800282fb  test    bl, bl
0x1800282fd  jz      loc_1800283B9
0x180028303  lea     rdx, aRepartitionRep_1; "Repartition: Repartition was completed,"...
0x18002830a  xor     ecx, ecx
0x18002830c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180028311  mov     rbx, [rdi+1C0h]
0x180028318  lea     rdx, aWinrepartition_0; "WinREPartitionVolumeName"
0x18002831f  lea     rcx, [rsp+120h+var_F0]
0x180028324  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180028329  nop
0x18002832a  mov     rdx, rsi
0x18002832d  lea     rcx, [rsp+120h+var_E0]
0x180028332  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180028337  nop
0x180028338  lea     r9, [rsp+120h+var_E8]
0x18002833d  lea     r8, [rsp+120h+var_F0]
0x180028342  lea     rdx, [rsp+120h+var_E0]
0x180028347  mov     rcx, rbx
0x18002834a  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002834f  mov     edi, eax
0x180028351  mov     rcx, [rsp+120h+var_E0]
0x180028356  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002835a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002835f  nop
0x180028360  mov     rcx, [rsp+120h+var_F0]
0x180028365  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180028369  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002836e  test    edi, edi
0x180028370  jns     short loc_1800283AF
0x180028372  lea     rax, aFailedToReadWi; "Failed to read WinRE partition volume n"...
0x180028379  mov     [rsp+120h+var_F8], rax
0x18002837e  mov     [rsp+120h+var_100], 35Bh
0x180028386  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002838d  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x180028394  mov     edx, edi
0x180028396  mov     ecx, 2
0x18002839b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800283a0  nop
0x1800283a1  mov     rcx, [rsp+120h+var_E8]
0x1800283a6  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800283aa  jmp     loc_18002886A
0x1800283af  mov     rbx, [rsp+120h+var_E8]
0x1800283b4  jmp     loc_18002881C
0x1800283b9  mov     [rsp+120h+var_D8], 0
0x1800283c2  mov     rbx, [rdi+1C0h]
0x1800283c9  lea     rdx, aOriginalwinrep_0; "OriginalWinREPartitionOffset"
0x1800283d0  lea     rcx, [rsp+120h+var_F0]
0x1800283d5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800283da  nop
0x1800283db  mov     rdx, rsi
0x1800283de  lea     rcx, [rsp+120h+var_E0]
0x1800283e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800283e8  nop
0x1800283e9  lea     r9, [rsp+120h+var_D8]
0x1800283ee  lea     r8, [rsp+120h+var_F0]
0x1800283f3  lea     rdx, [rsp+120h+var_E0]
0x1800283f8  mov     rcx, rbx
0x1800283fb  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_K@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180028400  mov     ebx, eax
0x180028402  mov     rcx, [rsp+120h+var_E0]
0x180028407  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002840b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028410  nop
0x180028411  mov     rcx, [rsp+120h+var_F0]
0x180028416  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002841a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002841f  test    ebx, ebx
0x180028421  jns     short loc_180028467
0x180028423  lea     rax, aFailedToReadOr; "Failed to read original WinRE partition"...
0x18002842a  mov     [rsp+120h+var_F8], rax
0x18002842f  mov     [rsp+120h+var_100], 364h
0x180028437  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002843e  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x180028445  mov     edx, ebx
0x180028447  mov     ecx, 2
0x18002844c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180028451  nop
0x180028452  mov     rcx, [rsp+120h+var_E8]
0x180028457  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002845b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028460  mov     eax, ebx
0x180028462  jmp     loc_180028871
0x180028467  mov     [rbp+57h+var_C8], 0
0x18002846f  lea     r14, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x180028476  mov     [rbp+57h+var_D0], r14
0x18002847a  lea     rcx, [rbp+57h+var_D0]
0x18002847e  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180028483  mov     rcx, rax; this
0x180028486  call    ?WinREGetOSDisk@WinREAgent@@YAJPEAPEAVDisk@PushButtonReset@@@Z; WinREAgent::WinREGetOSDisk(PushButtonReset::Disk * *)
0x18002848b  mov     ebx, eax
0x18002848d  test    eax, eax
0x18002848f  jns     short loc_1800284CF
0x180028491  lea     rax, aFailedToGetDis_0; "Failed to get Disk for OS"
0x180028498  mov     [rsp+120h+var_F8], rax
0x18002849d  mov     [rsp+120h+var_100], 369h
0x1800284a5  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800284ac  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x1800284b3  mov     edx, ebx
0x1800284b5  mov     ecx, 2
0x1800284ba  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800284bf  nop
0x1800284c0  mov     [rbp+57h+var_D0], r14
0x1800284c4  lea     rcx, [rbp+57h+var_D0]
0x1800284c8  call    ?Release@?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(void)
0x1800284cd  jmp     short loc_180028452
0x1800284cf  mov     rax, [rbp+57h+var_D0]
0x1800284d3  lea     rcx, [rbp+57h+var_D0]
0x1800284d7  mov     rax, [rax+18h]
0x1800284db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284e0  mov     rsi, [rsp+120h+var_D8]
0x1800284e5  mov     r9, rsi
0x1800284e8  mov     r8d, [rax+10h]
0x1800284ec  lea     rdx, aRepartitionSea; "Repartition: Search for original WinRE "...
0x1800284f3  xor     ecx, ecx
0x1800284f5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800284fa  mov     [rbp+57h+var_B8], 0
0x180028502  lea     r13, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180028509  mov     [rbp+57h+var_C0], r13
0x18002850d  lea     rcx, [rbp+57h+var_C0]
0x180028511  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180028516  mov     rbx, rax
0x180028519  mov     rcx, [rbp+57h+var_D0]
0x18002851d  mov     rax, [rcx+18h]
0x180028521  lea     rcx, [rbp+57h+var_D0]
0x180028525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852a  mov     r8, rbx; struct PushButtonReset::Partition **
0x18002852d  mov     rdx, rsi; unsigned __int64
0x180028530  mov     ecx, [rax+10h]; unsigned int
0x180028533  call    ?FindByOffset@Partition@PushButtonReset@@SAJK_KPEAPEAV12@@Z; PushButtonReset::Partition::FindByOffset(ulong,unsigned __int64,PushButtonReset::Partition * *)
0x180028538  test    eax, eax
0x18002853a  js      short loc_1800285B8
0x18002853c  lea     rdx, aRepartitionFin; "Repartition: Find original WinRE partit"...
0x180028543  xor     ecx, ecx
0x180028545  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002854a  lea     rcx, [rbp+57h+var_B0]; this
0x18002854e  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180028553  nop
0x180028554  mov     rax, [rbp+57h+var_C0]
0x180028558  lea     rcx, [rbp+57h+var_C0]
0x18002855c  mov     rax, [rax+18h]
0x180028560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028565  lea     rdx, [rbp+57h+var_B0]; struct PushButtonReset::PartitionInfo *
0x180028569  mov     rcx, rax; this
0x18002856c  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x180028571  mov     ebx, eax
0x180028573  test    eax, eax
0x180028575  jns     loc_1800286EC
0x18002857b  lea     rax, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x180028582  mov     [rsp+120h+var_F8], rax
0x180028587  mov     [rsp+120h+var_100], 38Bh
0x18002858f  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180028596  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x18002859d  mov     edx, ebx
0x18002859f  mov     ecx, 2
0x1800285a4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800285a9  nop
0x1800285aa  lea     rcx, [rbp+57h+var_B0]; this
0x1800285ae  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x1800285b3  jmp     loc_180028683
0x1800285b8  lea     rcx, aRepartitionFai; "Repartition: Failed to find original Wi"...
0x1800285bf  mov     [rsp+120h+var_F8], rcx
0x1800285c4  mov     [rsp+120h+var_100], 378h
0x1800285cc  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800285d3  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x1800285da  mov     edx, eax
0x1800285dc  mov     ecx, 1
0x1800285e1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800285e6  mov     [rsp+120h+var_F0], 0
0x1800285ef  mov     rbx, [rdi+1C0h]
0x1800285f6  lea     rdx, aOriginalwinrep; "OriginalWinREPartitionSize"
0x1800285fd  lea     rcx, [rsp+120h+var_E0]
0x180028602  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180028607  nop
0x180028608  lea     rdx, aRepartitioninf; "RepartitionInfo"
0x18002860f  lea     rcx, [rsp+120h+var_D8]
0x180028614  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180028619  nop
0x18002861a  lea     r9, [rsp+120h+var_F0]
0x18002861f  lea     r8, [rsp+120h+var_E0]
0x180028624  lea     rdx, [rsp+120h+var_D8]
0x180028629  mov     rcx, rbx
0x18002862c  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_K@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180028631  mov     ebx, eax
0x180028633  mov     rcx, [rsp+120h+var_D8]
0x180028638  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002863c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028641  nop
0x180028642  mov     rcx, [rsp+120h+var_E0]
0x180028647  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002864b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028650  test    ebx, ebx
0x180028652  jns     short loc_180028695
0x180028654  lea     rax, aFailedToReadOr_0; "Failed to read original WinRE partition"...
0x18002865b  mov     [rsp+120h+var_F8], rax
0x180028660  mov     [rsp+120h+var_100], 37Fh
0x180028668  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002866f  lea     r8, aWinregetwinrep; "WinREGetWinREPartition"
0x180028676  mov     edx, ebx
0x180028678  mov     ecx, 2
0x18002867d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180028682  nop
0x180028683  mov     [rbp+57h+var_C0], r13
0x180028687  lea     rcx, [rbp+57h+var_C0]
0x18002868b  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180028690  jmp     loc_1800284C0
0x180028695  mov     r8, [rsp+120h+var_F0]
0x18002869a  lea     rdx, aRepartitionCre; "Repartition: Create WinRE partition wit"...
0x1800286a1  xor     ecx, ecx
0x1800286a3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800286a8  mov     rax, [rbp+57h+var_C0]
0x1800286ac  lea     rcx, [rbp+57h+var_C0]
0x1800286b0  mov     rax, [rax+8]
0x1800286b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286b9  mov     r8, rax; struct PushButtonReset::Partition **
0x1800286bc  mov     rdx, [rsp+120h+var_F0]; unsigned __int64
0x1800286c1  mov     rcx, rsi; unsigned __int64
0x1800286c4  call    ?WinRECreateRecoveryPartition@@YAJ_K0PEAPEAVPartition@PushButtonReset@@@Z; WinRECreateRecoveryPartition(unsigned __int64,unsigned __int64,PushButtonReset::Partition * *)
0x1800286c9  mov     ebx, eax
0x1800286cb  test    eax, eax
0x1800286cd  jns     loc_18002854A
0x1800286d3  lea     rax, aFailedToCreate_9; "Failed to create WinRE partition"
0x1800286da  mov     [rsp+120h+var_F8], rax
0x1800286df  mov     [rsp+120h+var_100], 385h
0x1800286e7  jmp     loc_180028668
0x1800286ec  lea     rdx, aRepartitionWin_2; "Repartition: WinRE partition info"
0x1800286f3  xor     ecx, ecx
0x1800286f5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800286fa  mov     r8, [rbp+57h+var_88]
0x1800286fe  lea     rdx, aRepartitionWin; "Repartition: WinRE partition offset: [%"...
0x180028705  xor     ecx, ecx
0x180028707  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002870c  mov     r8, [rbp+57h+var_80]
0x180028710  lea     rdx, aRepartitionWin_5; "Repartition: WinRE partition Size: [%ll"...
0x180028717  xor     ecx, ecx
0x180028719  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002871e  mov     r8, [rbp+57h+var_60]
0x180028722  lea     rdx, aRepartitionWin_0; "Repartition: WinRE partition Available "...
0x180028729  xor     ecx, ecx
0x18002872b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180028730  lea     rcx, [rsp+120h+var_F0]
0x180028735  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002873a  nop
0x18002873b  mov     r9d, [rbp+57h+var_AC]
0x18002873f  mov     r8d, [rbp+57h+var_B0]
0x180028743  lea     rdx, aGlobalrootDevi_0; "\\\\?\\GLOBALROOT\\device\\harddisk%u\\"...
0x18002874a  lea     rcx, [rsp+120h+var_F0]
0x18002874f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180028754  lea     rdx, [rsp+120h+var_E8]
0x180028759  lea     rcx, [rsp+120h+var_F0]
  ... truncated ...
```
