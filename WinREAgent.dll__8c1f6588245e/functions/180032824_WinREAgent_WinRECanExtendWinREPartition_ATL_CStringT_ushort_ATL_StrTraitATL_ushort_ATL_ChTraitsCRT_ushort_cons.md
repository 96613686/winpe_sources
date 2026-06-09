# WinREAgent::WinRECanExtendWinREPartition(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)

- ea: `0x180032824`
- end: `0x180032ed8`
- name: `?WinRECanExtendWinREPartition@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@Z`
- size: `1716`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x18000febc`
- `0x180027a60`

## callees

- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x18000d6f0`
- `0x180026260`
- `0x1800327d0`
- `0x180032824`
- `0x180033238`
- `0x18003717c`
- `0x180037344`
- `0x18003bbf4`
- `0x18003bdd8`
- `0x180046d84`
- `0x180047d1c`
- `0x180048b68`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180032876`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x1800328e8`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x18003294d`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x1800329bb`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032af4`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032b76`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032d16`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032d53`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x18003287d`: `WinREAgent::WinRECanExtendWinREPartition`
- `0x18003289d`: `WinREAgent::WinRECanExtendWinREPartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinREAgent::WinRECanExtendWinREPartition(__int64 a1, _BYTE *a2)
{
  char v4; // r13
  struct PushButtonReset::PartitionInfo *v6; // rdx
  int Info; // ebx
  __int64 v8; // rax
  PushButtonReset::Partition *v9; // rax
  unsigned int v10; // ebx
  struct PushButtonReset::Disk **v11; // rax
  PushButtonReset::Disk *v12; // rbx
  struct PushButtonReset::PartitionList **v13; // rax
  unsigned int v14; // r15d
  unsigned int v15; // r14d
  unsigned int i; // esi
  PushButtonReset::PartitionList *v17; // rbx
  struct PushButtonReset::Partition **v18; // rax
  PushButtonReset::Partition *v19; // rax
  unsigned __int64 v20; // rax
  char v21; // [rsp+40h] [rbp-C0h]
  unsigned int v22[10]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+80h] [rbp-80h]
  _QWORD v25[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v27[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v28[2]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v29[10]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v30; // [rsp+138h] [rbp+38h]
  __int64 v31; // [rsp+140h] [rbp+40h]
  _BYTE v32[4]; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v33; // [rsp+194h] [rbp+94h]
  unsigned __int64 v34; // [rsp+1B8h] [rbp+B8h]
  __int64 v35; // [rsp+1C0h] [rbp+C0h]

  v4 = 0;
  if ( !a2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      281,
      L"res cannot be null");
    return 2147942487LL;
  }
  PushButtonReset::Logging::Trace(
    0,
    L"%hs: Check whether can extend WinRE partition",
    "WinREAgent::WinRECanExtendWinREPartition");
  *a2 = 0;
  PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v22);
  Info = WinREAgent::WinREGetOSPartitionInfo((WinREAgent *)v22, v6);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      289,
      L"Failed to get OS partition info");
LABEL_5:
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v22);
    return (unsigned int)Info;
  }
  v27[1] = 0;
  v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v8 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v27);
  Info = PushButtonReset::Partition::FindByFilePath(a1, v8);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      294,
      L"Failed to get partition for WinRE");
LABEL_8:
    v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v27);
    goto LABEL_5;
  }
  PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v29);
  v9 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v27[0] + 24LL))(v27);
  Info = PushButtonReset::Partition::GetInfo(v9, (struct PushButtonReset::PartitionInfo *)v29);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      299,
      L"Failed to get WinRE partition info");
LABEL_40:
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v29);
    goto LABEL_8;
  }
  v10 = v22[0];
  PushButtonReset::Logging::Trace(0, L"OS is on disk [%u], WinRE is on disk [%u]", v22[0], v29[0]);
  if ( v10 != v29[0] )
  {
    PushButtonReset::Logging::Trace(
      0,
      L"%hs: OS and WinRE partition are not on same disk, cannot extend WinRE partition",
      "WinREAgent::WinRECanExtendWinREPartition");
    Info = 0;
    goto LABEL_40;
  }
  PushButtonReset::Logging::Trace(0, L"OS partition info");
  PushButtonReset::Logging::Trace(0, L"  Disk index: [%u]", v10);
  PushButtonReset::Logging::Trace(0, L"  Partition index: [%u]", v22[1]);
  PushButtonReset::Logging::Trace(0, L"  Partition offset: [%llu]", v23);
  PushButtonReset::Logging::Trace(0, L"  Partition size: [%llu]", v24);
  PushButtonReset::Logging::Trace(0, L"  WinRE partitoin info");
  PushButtonReset::Logging::Trace(0, L"Disk index: [%u]", v29[0]);
  PushButtonReset::Logging::Trace(0, L"  Partition index: [%u]", v29[1]);
  PushButtonReset::Logging::Trace(0, L"  Partition offset: [%llu]", v30);
  PushButtonReset::Logging::Trace(0, L"  Partition size: [%llu]", v31);
  v26[1] = 0;
  v26[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
  v11 = (struct PushButtonReset::Disk **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v26);
  Info = PushButtonReset::Disk::FindByIndex(v10, v11);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      333,
      L"Failed to get disk for OS");
    goto LABEL_15;
  }
  v25[1] = 0;
  v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable';
  v12 = (PushButtonReset::Disk *)(*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 24LL))(v26);
  v13 = (struct PushButtonReset::PartitionList **)(*(__int64 (__fastcall **)(_QWORD *))(v25[0] + 8LL))(v25);
  Info = PushButtonReset::Disk::GetAllPartitions(v12, v13);
  if ( Info < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Info,
      "WinREAgent::WinRECanExtendWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      337,
      L"Failed to get all partitions of the OS disk");
    v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::Release(v25);
LABEL_15:
    v26[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
LABEL_16:
    RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v26);
    goto LABEL_40;
  }
  v14 = 0;
  v15 = 0;
  v21 = 0;
  PushButtonReset::Logging::Trace(0, L"Get all partitions on OS disk");
  for ( i = 0; (unsigned __int64)i < *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v25[0] + 24LL))(v25) + 8); ++i )
  {
    v28[1] = 0;
    v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    v17 = (PushButtonReset::PartitionList *)(*(__int64 (__fastcall **)(_QWORD *))(v25[0] + 24LL))(v25);
    v18 = (struct PushButtonReset::Partition **)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 8LL))(v28);
    Info = PushButtonReset::PartitionList::GetPartition(v17, i, v18);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::WinRECanExtendWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
        349,
        L"Failed to get partition [%u] from OS disk",
        i);
LABEL_34:
      v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v28);
LABEL_35:
      v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::Release(v25);
      v26[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
      goto LABEL_16;
    }
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v32);
    v19 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
    Info = PushButtonReset::Partition::GetInfo(v19, (struct PushButtonReset::PartitionInfo *)v32);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::WinRECanExtendWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
        353,
        L"Failed to get partition info");
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v32);
      goto LABEL_34;
    }
    PushButtonReset::Logging::Trace(0, L"  [%u] Partition index [%u], offset [%llu], size[%llu]", i, v33, v34, v35);
    v20 = v34;
    if ( v34 >= v23 )
    {
      if ( v34 == v23 )
      {
        PushButtonReset::Logging::Trace(0, L"Find OS partition");
        v21 = 1;
        v20 = v34;
      }
    }
    else
    {
      ++v14;
    }
    if ( v20 >= v30 )
    {
      if ( v20 == v30 )
      {
        PushButtonReset::Logging::Trace(0, L"Find WinRE partition");
        v4 = 1;
      }
    }
    else
    {
      ++v15;
    }
    PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v32);
    v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v28);
  }
  if ( v21 && v4 )
  {
    PushButtonReset::Logging::Trace(0, L"Real OS partition index: [%u]", v14);
    PushButtonReset::Logging::Trace(0, L"Real WinRE partition index: [%u]", v15);
    if ( v14 + 1 == v15 )
    {
      *a2 = 1;
      PushButtonReset::Logging::Trace(0, L"%hs: Can extend WinRE partition", "WinREAgent::WinRECanExtendWinREPartition");
      goto LABEL_35;
    }
    PushButtonReset::Logging::Trace(
      0,
      L"%hs: WinRE partition is not right after OS partition, cannot extend WinRE partition",
      "WinREAgent::WinRECanExtendWinREPartition");
    v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::Release(v25);
    v26[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v26);
    Info = 0;
    goto LABEL_40;
  }
  PushButtonReset::Logging::Trace(2, L"Cannot find OS or WinRE partition in the partition list");
  v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::Release(v25);
  v26[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v26);
  PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v29);
  v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v27);
  PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v22);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180032824  mov     [rsp-8+arg_10], rbx
0x180032829  push    rbp
0x18003282a  push    rsi
0x18003282b  push    rdi
0x18003282c  push    r12
0x18003282e  push    r13
0x180032830  push    r14
0x180032832  push    r15
0x180032834  lea     rbp, [rsp-120h]
0x18003283c  sub     rsp, 220h
0x180032843  mov     rax, cs:__security_cookie
0x18003284a  xor     rax, rsp
0x18003284d  mov     [rbp+150h+var_40], rax
0x180032854  mov     r12, rdx
0x180032857  mov     rsi, rcx
0x18003285a  xor     r13d, r13d
0x18003285d  test    rdx, rdx
0x180032860  jnz     short loc_18003289D
0x180032862  lea     rax, aResCannotBeNul; "res cannot be null"
0x180032869  mov     [rsp+250h+var_228], rax
0x18003286e  mov     dword ptr [rsp+250h+var_230], 119h
0x180032876  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003287d  lea     r8, aWinreagentWinr_20; "WinREAgent::WinRECanExtendWinREPartitio"...
0x180032884  mov     edx, 80070057h
0x180032889  lea     ecx, [r12+2]
0x18003288e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032893  mov     eax, 80070057h
0x180032898  jmp     loc_180032EAE
0x18003289d  lea     rdi, aWinreagentWinr_20; "WinREAgent::WinRECanExtendWinREPartitio"...
0x1800328a4  mov     r8, rdi
0x1800328a7  lea     rdx, aHsCheckWhether; "%hs: Check whether can extend WinRE par"...
0x1800328ae  xor     ecx, ecx
0x1800328b0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800328b5  mov     [r12], r13b
0x1800328b9  lea     rcx, [rsp+250h+var_200]; this
0x1800328be  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x1800328c3  nop
0x1800328c4  lea     rcx, [rsp+250h+var_200]; this
0x1800328c9  call    ?WinREGetOSPartitionInfo@WinREAgent@@YAJPEAUPartitionInfo@PushButtonReset@@@Z; WinREAgent::WinREGetOSPartitionInfo(PushButtonReset::PartitionInfo *)
0x1800328ce  mov     ebx, eax
0x1800328d0  test    eax, eax
0x1800328d2  jns     short loc_180032910
0x1800328d4  lea     rax, aFailedToGetOsP; "Failed to get OS partition info"
0x1800328db  mov     [rsp+250h+var_228], rax
0x1800328e0  mov     dword ptr [rsp+250h+var_230], 121h
0x1800328e8  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800328ef  mov     r8, rdi
0x1800328f2  mov     edx, ebx
0x1800328f4  mov     ecx, 2
0x1800328f9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800328fe  nop
0x1800328ff  lea     rcx, [rsp+250h+var_200]; this
0x180032904  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180032909  mov     eax, ebx
0x18003290b  jmp     loc_180032EAE
0x180032910  mov     [rbp+150h+var_158], r13
0x180032914  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x18003291b  mov     [rbp+150h+var_160], rax
0x18003291f  lea     rcx, [rbp+150h+var_160]
0x180032923  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180032928  mov     rdx, rax
0x18003292b  mov     rcx, rsi
0x18003292e  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x180032933  mov     ebx, eax
0x180032935  test    eax, eax
0x180032937  jns     short loc_18003297A
0x180032939  lea     rax, aFailedToGetPar_0; "Failed to get partition for WinRE"
0x180032940  mov     [rsp+250h+var_228], rax
0x180032945  mov     dword ptr [rsp+250h+var_230], 126h
0x18003294d  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032954  mov     r8, rdi
0x180032957  mov     edx, ebx
0x180032959  mov     ecx, 2
0x18003295e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032963  nop
0x180032964  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x18003296b  mov     [rbp+150h+var_160], rax
0x18003296f  lea     rcx, [rbp+150h+var_160]
0x180032973  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180032978  jmp     short loc_1800328FF
0x18003297a  lea     rcx, [rbp+150h+var_140]; this
0x18003297e  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180032983  nop
0x180032984  mov     rax, [rbp+150h+var_160]
0x180032988  lea     rcx, [rbp+150h+var_160]
0x18003298c  mov     rax, [rax+18h]
0x180032990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032995  lea     rdx, [rbp+150h+var_140]; struct PushButtonReset::PartitionInfo *
0x180032999  mov     rcx, rax; this
0x18003299c  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x1800329a1  mov     ebx, eax
0x1800329a3  test    eax, eax
0x1800329a5  jns     short loc_1800329D6
0x1800329a7  lea     rax, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x1800329ae  mov     [rsp+250h+var_228], rax
0x1800329b3  mov     dword ptr [rsp+250h+var_230], 12Bh
0x1800329bb  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800329c2  mov     r8, rdi
0x1800329c5  mov     edx, ebx
0x1800329c7  mov     ecx, 2
0x1800329cc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800329d1  jmp     loc_180032E20
0x1800329d6  mov     r9d, [rbp+150h+var_140]
0x1800329da  mov     ebx, [rsp+250h+var_200]
0x1800329de  mov     r8d, ebx
0x1800329e1  lea     rdx, aOsIsOnDiskUWin; "OS is on disk [%u], WinRE is on disk [%"...
0x1800329e8  xor     ecx, ecx
0x1800329ea  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800329ef  xor     ecx, ecx
0x1800329f1  cmp     ebx, [rbp+150h+var_140]
0x1800329f4  jz      short loc_180032A0D
0x1800329f6  mov     r8, rdi
0x1800329f9  lea     rdx, aHsOsAndWinrePa; "%hs: OS and WinRE partition are not on "...
0x180032a00  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a05  mov     ebx, r13d
0x180032a08  jmp     loc_180032E20
0x180032a0d  lea     rdx, aOsPartitionInf; "OS partition info"
0x180032a14  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a19  mov     r8d, ebx
0x180032a1c  lea     rdx, aDiskIndexU_0; "  Disk index: [%u]"
0x180032a23  xor     ecx, ecx
0x180032a25  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a2a  mov     r8d, [rsp+250h+var_1FC]
0x180032a2f  lea     rdx, aPartitionIndex_0; "  Partition index: [%u]"
0x180032a36  xor     ecx, ecx
0x180032a38  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a3d  mov     r8, [rsp+250h+var_1D8]
0x180032a42  lea     rdx, aPartitionOffse; "  Partition offset: [%llu]"
0x180032a49  xor     ecx, ecx
0x180032a4b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a50  mov     r8, [rbp+150h+var_1D0]
0x180032a54  lea     rdx, aPartitionSizeL_0; "  Partition size: [%llu]"
0x180032a5b  xor     ecx, ecx
0x180032a5d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a62  lea     rdx, aWinrePartitoin; "  WinRE partitoin info"
0x180032a69  xor     ecx, ecx
0x180032a6b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a70  mov     r8d, [rbp+150h+var_140]
0x180032a74  lea     rdx, aDiskIndexU_1; "Disk index: [%u]"
0x180032a7b  xor     ecx, ecx
0x180032a7d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a82  mov     r8d, [rbp+150h+var_13C]
0x180032a86  lea     rdx, aPartitionIndex_0; "  Partition index: [%u]"
0x180032a8d  xor     ecx, ecx
0x180032a8f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032a94  mov     r8, [rbp+150h+var_118]
0x180032a98  lea     rdx, aPartitionOffse; "  Partition offset: [%llu]"
0x180032a9f  xor     ecx, ecx
0x180032aa1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032aa6  mov     r8, [rbp+150h+var_110]
0x180032aaa  lea     rdx, aPartitionSizeL_0; "  Partition size: [%llu]"
0x180032ab1  xor     ecx, ecx
0x180032ab3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032ab8  mov     [rbp+150h+var_168], r13
0x180032abc  lea     r14, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x180032ac3  mov     [rbp+150h+var_170], r14
0x180032ac7  lea     rcx, [rbp+150h+var_170]
0x180032acb  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180032ad0  mov     rdx, rax; struct PushButtonReset::Disk **
0x180032ad3  mov     ecx, ebx; unsigned int
0x180032ad5  call    ?FindByIndex@Disk@PushButtonReset@@SAJKPEAPEAV12@@Z; PushButtonReset::Disk::FindByIndex(ulong,PushButtonReset::Disk * *)
0x180032ada  mov     ebx, eax
0x180032adc  test    eax, eax
0x180032ade  jns     short loc_180032B1D
0x180032ae0  lea     rax, aFailedToGetDis_1; "Failed to get disk for OS"
0x180032ae7  mov     [rsp+250h+var_228], rax
0x180032aec  mov     dword ptr [rsp+250h+var_230], 14Dh
0x180032af4  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032afb  mov     r8, rdi
0x180032afe  mov     edx, ebx
0x180032b00  mov     ecx, 2
0x180032b05  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032b0a  nop
0x180032b0b  mov     [rbp+150h+var_170], r14
0x180032b0f  lea     rcx, [rbp+150h+var_170]
0x180032b13  call    ?Release@?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(void)
0x180032b18  jmp     loc_180032E20
0x180032b1d  mov     [rbp+150h+var_178], r13
0x180032b21  lea     rsi, ??_7?$CAutoPbrDelete@PEAVPartitionList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::`vftable'
0x180032b28  mov     [rbp+150h+var_180], rsi
0x180032b2c  mov     rax, [rbp+150h+var_170]
0x180032b30  lea     rcx, [rbp+150h+var_170]
0x180032b34  mov     rax, [rax+18h]
0x180032b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b3d  mov     rbx, rax
0x180032b40  mov     rcx, [rbp+150h+var_180]
0x180032b44  mov     rax, [rcx+8]
0x180032b48  lea     rcx, [rbp+150h+var_180]
0x180032b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b51  mov     rdx, rax; struct PushButtonReset::PartitionList **
0x180032b54  mov     rcx, rbx; this
0x180032b57  call    ?GetAllPartitions@Disk@PushButtonReset@@QEAAJPEAPEAVPartitionList@2@@Z; PushButtonReset::Disk::GetAllPartitions(PushButtonReset::PartitionList * *)
0x180032b5c  mov     ebx, eax
0x180032b5e  test    eax, eax
0x180032b60  jns     short loc_180032B9F
0x180032b62  lea     rax, aFailedToGetAll; "Failed to get all partitions of the OS "...
0x180032b69  mov     [rsp+250h+var_228], rax
0x180032b6e  mov     dword ptr [rsp+250h+var_230], 151h
0x180032b76  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032b7d  mov     r8, rdi
0x180032b80  mov     edx, ebx
0x180032b82  mov     ecx, 2
0x180032b87  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032b8c  nop
0x180032b8d  mov     [rbp+150h+var_180], rsi
0x180032b91  lea     rcx, [rbp+150h+var_180]
0x180032b95  call    ?Release@?$CAutoPbrDelete@PEAVPartitionList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::PartitionList *>::Release(void)
0x180032b9a  jmp     loc_180032B0B
0x180032b9f  mov     r15d, r13d
0x180032ba2  mov     r14d, r13d
0x180032ba5  mov     [rsp+250h+var_210], r13b
0x180032baa  lea     rdx, aGetAllPartitio; "Get all partitions on OS disk"
0x180032bb1  xor     ecx, ecx
0x180032bb3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032bb8  xor     esi, esi
0x180032bba  mov     rax, [rbp+150h+var_180]
0x180032bbe  lea     rcx, [rbp+150h+var_180]
0x180032bc2  mov     rax, [rax+18h]
0x180032bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bcb  mov     ecx, esi
0x180032bcd  cmp     rcx, [rax+8]
0x180032bd1  jnb     loc_180032DA4
0x180032bd7  mov     [rbp+150h+var_148], 0
0x180032bdf  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180032be6  mov     [rbp+150h+var_150], rax
0x180032bea  mov     rax, [rbp+150h+var_180]
0x180032bee  lea     rcx, [rbp+150h+var_180]
0x180032bf2  mov     rax, [rax+18h]
0x180032bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bfb  mov     rbx, rax
0x180032bfe  mov     rcx, [rbp+150h+var_150]
0x180032c02  mov     rax, [rcx+8]
0x180032c06  lea     rcx, [rbp+150h+var_150]
0x180032c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c0f  mov     r8, rax; struct PushButtonReset::Partition **
0x180032c12  mov     edx, esi; unsigned __int64
0x180032c14  mov     rcx, rbx; this
0x180032c17  call    ?GetPartition@PartitionList@PushButtonReset@@QEAAJ_KPEAPEAVPartition@2@@Z; PushButtonReset::PartitionList::GetPartition(unsigned __int64,PushButtonReset::Partition * *)
0x180032c1c  mov     ebx, eax
0x180032c1e  test    eax, eax
0x180032c20  js      loc_180032D3B
0x180032c26  lea     rcx, [rbp+150h+var_C0]; this
0x180032c2d  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x180032c32  nop
0x180032c33  mov     rax, [rbp+150h+var_150]
0x180032c37  lea     rcx, [rbp+150h+var_150]
0x180032c3b  mov     rax, [rax+18h]
0x180032c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c44  lea     rdx, [rbp+150h+var_C0]; struct PushButtonReset::PartitionInfo *
0x180032c4b  mov     rcx, rax; this
0x180032c4e  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x180032c53  mov     ebx, eax
0x180032c55  test    eax, eax
0x180032c57  js      loc_180032D02
0x180032c5d  mov     rax, [rbp+150h+var_90]
0x180032c64  mov     [rsp+250h+var_228], rax
0x180032c69  mov     rax, [rbp+150h+var_98]
0x180032c70  mov     [rsp+250h+var_230], rax
0x180032c75  mov     r9d, [rbp+150h+var_BC]
0x180032c7c  mov     r8d, esi
0x180032c7f  lea     rdx, aUPartitionInde; "  [%u] Partition index [%u], offset [%l"...
0x180032c86  xor     ecx, ecx
0x180032c88  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032c8d  mov     rax, [rbp+150h+var_98]
0x180032c94  cmp     rax, [rsp+250h+var_1D8]
0x180032c99  jnb     short loc_180032CA0
0x180032c9b  inc     r15d
0x180032c9e  jmp     short loc_180032CBC
0x180032ca0  jnz     short loc_180032CBC
0x180032ca2  lea     rdx, aFindOsPartitio; "Find OS partition"
0x180032ca9  xor     ecx, ecx
0x180032cab  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032cb0  mov     [rsp+250h+var_210], 1
0x180032cb5  mov     rax, [rbp+150h+var_98]
0x180032cbc  cmp     rax, [rbp+150h+var_118]
0x180032cc0  jnb     short loc_180032CC7
0x180032cc2  inc     r14d
0x180032cc5  jmp     short loc_180032CDA
0x180032cc7  jnz     short loc_180032CDA
0x180032cc9  lea     rdx, aFindWinreParti; "Find WinRE partition"
0x180032cd0  xor     ecx, ecx
0x180032cd2  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180032cd7  mov     r13b, 1
0x180032cda  lea     rcx, [rbp+150h+var_C0]; this
0x180032ce1  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180032ce6  nop
0x180032ce7  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180032cee  mov     [rbp+150h+var_150], rax
0x180032cf2  lea     rcx, [rbp+150h+var_150]
0x180032cf6  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180032cfb  inc     esi
0x180032cfd  jmp     loc_180032BBA
0x180032d02  lea     rax, aFailedToGetPar; "Failed to get partition info"
0x180032d09  mov     [rsp+250h+var_228], rax
0x180032d0e  mov     dword ptr [rsp+250h+var_230], 161h
0x180032d16  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032d1d  mov     r8, rdi
0x180032d20  mov     edx, ebx
0x180032d22  mov     ecx, 2
0x180032d27  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
  ... truncated ...
```
