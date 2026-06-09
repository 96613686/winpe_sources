# PushButtonReset::SerializeNode::SetPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180052fd0`
- end: `0x180053386`
- name: `?SetPath@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x180036ba0`

## callees

- `0x180004af8`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18002476c`
- `0x180037344`
- `0x18003bbf4`
- `0x180047d1c`
- `0x18004e7f8`
- `0x180052f14`
- `0x180052fd0`
- `0x18005338c`
- `0x180053554`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180053048`: `Failed to write path set flag`
- `0x18005322c`: `Failed to write path set flag`
- `0x180053063`: `PushButtonReset::SerializeNode::SetPath`
- `0x1800530cd`: `PushButtonReset::SerializeNode::SetPath`
- `0x180053192`: `PushButtonReset::SerializeNode::SetPath`
- `0x1800531f3`: `PushButtonReset::SerializeNode::SetPath`
- `0x180053247`: `PushButtonReset::SerializeNode::SetPath`
- `0x180053309`: `PushButtonReset::SerializeNode::SetPath`
- `0x1800531d8`: `Failed to get volume-relative path for [%s]`
- `0x1800532bf`: `Failed to write partition information`
- `0x1800532ee`: `Failed to write volume-relative path`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PushButtonReset::SerializeNode::SetPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  int Info; // esi
  PushButtonReset::Partition *v10; // rax
  __int64 v11; // r8
  int v12; // edi
  int v13; // [rsp+30h] [rbp-99h]
  int v14; // [rsp+38h] [rbp-91h]
  __int64 v15; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v16[2]; // [rsp+48h] [rbp-81h] BYREF
  __int64 v17; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v19[10]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v20; // [rsp+98h] [rbp-31h]

  ATL::operator+(&v15, a2, L"Set");
  ATL::operator+(&v17, a2, L"Path");
  if ( *(_DWORD *)(*a3 - 16LL) )
  {
    v16[1] = 0;
    v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    v7 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v16);
    Info = PushButtonReset::Partition::FindByFilePath(a3, v7);
    if ( Info >= 0 )
    {
      PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v19);
      v10 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
      Info = PushButtonReset::Partition::GetInfo(v10, (struct PushButtonReset::PartitionInfo *)v19);
      if ( Info >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v18);
        Info = PushButtonReset::Path::GetVolumeRelPath(a3, v18);
        if ( Info >= 0 )
        {
          LOBYTE(v11) = 1;
          v12 = PushButtonReset::SerializeNode::SetProperty(a1, &v15, v11);
          if ( v12 >= 0 )
          {
            v12 = PushButtonReset::SerializeNode::SetPartition(a1, a2, v19[0], v20);
            if ( v12 >= 0 )
            {
              v6 = PushButtonReset::SerializeNode::SetProperty(a1, &v17, v18);
              if ( v6 < 0 )
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)v6,
                  "PushButtonReset::SerializeNode::SetPath",
                  "base\\reset\\util\\src\\serialize.cpp",
                  861,
                  L"Failed to write volume-relative path");
              ATL::CStringData::Release((ATL::CStringData *)(v18[0] - 24LL));
              PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v19);
              v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
              RAII::CAutoPbrHeapFree<unsigned short *>::Release(v16);
              goto LABEL_20;
            }
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v12,
              "PushButtonReset::SerializeNode::SetPath",
              "base\\reset\\util\\src\\serialize.cpp",
              858,
              L"Failed to write partition information");
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v12,
              "PushButtonReset::SerializeNode::SetPath",
              "base\\reset\\util\\src\\serialize.cpp",
              855,
              L"Failed to write path set flag");
          }
          ATL::CStringData::Release((ATL::CStringData *)(v18[0] - 24LL));
          PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v19);
          v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v16);
          ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
          return (unsigned int)v12;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "PushButtonReset::SerializeNode::SetPath",
          "base\\reset\\util\\src\\serialize.cpp",
          852,
          L"Failed to get volume-relative path for [%s]",
          *a3);
        ATL::CStringData::Release((ATL::CStringData *)(v18[0] - 24LL));
      }
      else
      {
        v14 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16) + 104);
        v13 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16) + 16);
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "PushButtonReset::SerializeNode::SetPath",
          "base\\reset\\util\\src\\serialize.cpp",
          847,
          L"Failed to get info for disk [%u] partition [%u]",
          v13,
          v14);
      }
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v19);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "PushButtonReset::SerializeNode::SetPath",
        "base\\reset\\util\\src\\serialize.cpp",
        841,
        L"Failed to look up host partition for [%s]",
        *a3);
    }
    v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v16);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    return (unsigned int)Info;
  }
  v6 = PushButtonReset::SerializeNode::SetProperty(a1, &v15, 0);
  if ( v6 < 0 )
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v6,
      "PushButtonReset::SerializeNode::SetPath",
      "base\\reset\\util\\src\\serialize.cpp",
      834,
      L"Failed to write path set flag");
LABEL_20:
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180052fd0  mov     [rsp-8+arg_18], rbx
0x180052fd5  push    rbp
0x180052fd6  push    rsi
0x180052fd7  push    rdi
0x180052fd8  push    r14
0x180052fda  push    r15
0x180052fdc  lea     rbp, [rsp-37h]
0x180052fe1  sub     rsp, 100h
0x180052fe8  mov     rax, cs:__security_cookie
0x180052fef  xor     rax, rsp
0x180052ff2  mov     [rbp+57h+var_30], rax
0x180052ff6  mov     rdi, r8
0x180052ff9  mov     r14, rdx
0x180052ffc  mov     rbx, rcx
0x180052fff  lea     r8, aSet; "Set"
0x180053006  lea     rcx, [rsp+120h+var_E0]
0x18005300b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180053010  nop
0x180053011  lea     r8, aPath; "Path"
0x180053018  mov     rdx, r14
0x18005301b  lea     rcx, [rbp+57h+var_C8]
0x18005301f  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180053024  nop
0x180053025  mov     rax, [rdi]
0x180053028  cmp     dword ptr [rax-10h], 0
0x18005302c  jnz     short loc_18005307B
0x18005302e  xor     r8d, r8d
0x180053031  lea     rdx, [rsp+120h+var_E0]
0x180053036  mov     rcx, rbx
0x180053039  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x18005303e  mov     ebx, eax
0x180053040  test    eax, eax
0x180053042  jns     loc_180053345
0x180053048  lea     rax, aFailedToWriteP_1; "Failed to write path set flag"
0x18005304f  mov     [rsp+120h+var_F8], rax
0x180053054  mov     [rsp+120h+var_100], 342h
0x18005305c  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180053063  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x18005306a  mov     edx, ebx
0x18005306c  mov     ecx, 2
0x180053071  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053076  jmp     loc_180053345
0x18005307b  mov     [rbp+57h+var_D0], 0
0x180053083  lea     r15, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x18005308a  mov     [rsp+120h+var_D8], r15
0x18005308f  lea     rcx, [rsp+120h+var_D8]
0x180053094  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180053099  mov     rdx, rax
0x18005309c  mov     rcx, rdi
0x18005309f  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x1800530a4  mov     esi, eax
0x1800530a6  test    eax, eax
0x1800530a8  jns     short loc_180053114
0x1800530aa  mov     rcx, [rdi]
0x1800530ad  mov     [rsp+120h+var_F0], rcx
0x1800530b2  lea     rax, aFailedToLookUp_8; "Failed to look up host partition for [%"...
0x1800530b9  mov     [rsp+120h+var_F8], rax
0x1800530be  mov     [rsp+120h+var_100], 349h
0x1800530c6  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x1800530cd  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x1800530d4  mov     edx, esi
0x1800530d6  mov     ecx, 2
0x1800530db  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800530e0  nop
0x1800530e1  mov     [rsp+120h+var_D8], r15
0x1800530e6  lea     rcx, [rsp+120h+var_D8]
0x1800530eb  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800530f0  nop
0x1800530f1  mov     rcx, [rbp+57h+var_C8]
0x1800530f5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800530f9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800530fe  nop
0x1800530ff  mov     rcx, [rsp+120h+var_E0]
0x180053104  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180053108  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005310d  mov     eax, esi
0x18005310f  jmp     loc_180053363
0x180053114  lea     rcx, [rbp+57h+var_B0]; this
0x180053118  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18005311d  nop
0x18005311e  mov     rax, [rsp+120h+var_D8]
0x180053123  lea     rcx, [rsp+120h+var_D8]
0x180053128  mov     rax, [rax+18h]
0x18005312c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053131  lea     rdx, [rbp+57h+var_B0]; struct PushButtonReset::PartitionInfo *
0x180053135  mov     rcx, rax; this
0x180053138  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18005313d  mov     esi, eax
0x18005313f  test    eax, eax
0x180053141  jns     short loc_1800531B4
0x180053143  mov     rcx, [rsp+120h+var_D8]
0x180053148  mov     rax, [rcx+18h]
0x18005314c  lea     rcx, [rsp+120h+var_D8]
0x180053151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053156  mov     ebx, [rax+68h]
0x180053159  mov     rcx, [rsp+120h+var_D8]
0x18005315e  mov     rax, [rcx+18h]
0x180053162  lea     rcx, [rsp+120h+var_D8]
0x180053167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005316c  mov     [rsp+120h+var_E8], ebx
0x180053170  mov     eax, [rax+10h]
0x180053173  mov     dword ptr [rsp+120h+var_F0], eax
0x180053177  lea     rax, aFailedToGetInf_5; "Failed to get info for disk [%u] partit"...
0x18005317e  mov     [rsp+120h+var_F8], rax
0x180053183  mov     [rsp+120h+var_100], 34Fh
0x18005318b  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180053192  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x180053199  mov     edx, esi
0x18005319b  mov     ecx, 2
0x1800531a0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800531a5  nop
0x1800531a6  lea     rcx, [rbp+57h+var_B0]; this
0x1800531aa  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x1800531af  jmp     loc_1800530E1
0x1800531b4  lea     rcx, [rbp+57h+var_C0]
0x1800531b8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800531bd  nop
0x1800531be  lea     rdx, [rbp+57h+var_C0]
0x1800531c2  mov     rcx, rdi
0x1800531c5  call    ?GetVolumeRelPath@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolumeRelPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800531ca  mov     esi, eax
0x1800531cc  test    eax, eax
0x1800531ce  jns     short loc_180053216
0x1800531d0  mov     rcx, [rdi]
0x1800531d3  mov     [rsp+120h+var_F0], rcx
0x1800531d8  lea     rax, aFailedToGetVol_4; "Failed to get volume-relative path for "...
0x1800531df  mov     [rsp+120h+var_F8], rax
0x1800531e4  mov     [rsp+120h+var_100], 354h
0x1800531ec  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x1800531f3  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x1800531fa  mov     edx, esi
0x1800531fc  mov     ecx, 2
0x180053201  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053206  nop
0x180053207  mov     rcx, [rbp+57h+var_C0]
0x18005320b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005320f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053214  jmp     short loc_1800531A6
0x180053216  mov     r8b, 1
0x180053219  lea     rdx, [rsp+120h+var_E0]
0x18005321e  mov     rcx, rbx
0x180053221  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x180053226  mov     edi, eax
0x180053228  test    eax, eax
0x18005322a  jns     short loc_1800532A6
0x18005322c  lea     rax, aFailedToWriteP_1; "Failed to write path set flag"
0x180053233  mov     [rsp+120h+var_F8], rax
0x180053238  mov     [rsp+120h+var_100], 357h
0x180053240  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180053247  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x18005324e  mov     edx, edi
0x180053250  mov     ecx, 2
0x180053255  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005325a  nop
0x18005325b  mov     rcx, [rbp+57h+var_C0]
0x18005325f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180053263  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053268  nop
0x180053269  lea     rcx, [rbp+57h+var_B0]; this
0x18005326d  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180053272  nop
0x180053273  mov     [rsp+120h+var_D8], r15
0x180053278  lea     rcx, [rsp+120h+var_D8]
0x18005327d  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180053282  nop
0x180053283  mov     rcx, [rbp+57h+var_C8]
0x180053287  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005328b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053290  nop
0x180053291  mov     rcx, [rsp+120h+var_E0]
0x180053296  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005329a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005329f  mov     eax, edi
0x1800532a1  jmp     loc_180053363
0x1800532a6  mov     r9, [rbp+57h+var_88]
0x1800532aa  mov     r8d, [rbp+57h+var_B0]
0x1800532ae  mov     rdx, r14
0x1800532b1  mov     rcx, rbx
0x1800532b4  call    ?SetPartition@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K_K@Z; PushButtonReset::SerializeNode::SetPartition(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,unsigned __int64)
0x1800532b9  mov     edi, eax
0x1800532bb  test    eax, eax
0x1800532bd  jns     short loc_1800532D8
0x1800532bf  lea     rax, aFailedToWriteP_4; "Failed to write partition information"
0x1800532c6  mov     [rsp+120h+var_F8], rax
0x1800532cb  mov     [rsp+120h+var_100], 35Ah
0x1800532d3  jmp     loc_180053240
0x1800532d8  lea     r8, [rbp+57h+var_C0]
0x1800532dc  lea     rdx, [rbp+57h+var_C8]
0x1800532e0  mov     rcx, rbx
0x1800532e3  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800532e8  mov     ebx, eax
0x1800532ea  test    eax, eax
0x1800532ec  jns     short loc_18005331D
0x1800532ee  lea     rax, aFailedToWriteV_0; "Failed to write volume-relative path"
0x1800532f5  mov     [rsp+120h+var_F8], rax
0x1800532fa  mov     [rsp+120h+var_100], 35Dh
0x180053302  lea     r9, aBaseResetUtilS_9; "base\\reset\\util\\src\\serialize.cpp"
0x180053309  lea     r8, aPushbuttonrese_40; "PushButtonReset::SerializeNode::SetPath"
0x180053310  mov     edx, ebx
0x180053312  mov     ecx, 2
0x180053317  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005331c  nop
0x18005331d  mov     rcx, [rbp+57h+var_C0]
0x180053321  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180053325  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005332a  nop
0x18005332b  lea     rcx, [rbp+57h+var_B0]; this
0x18005332f  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180053334  nop
0x180053335  mov     [rsp+120h+var_D8], r15
0x18005333a  lea     rcx, [rsp+120h+var_D8]
0x18005333f  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180053344  nop
0x180053345  mov     rcx, [rbp+57h+var_C8]
0x180053349  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005334d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053352  nop
0x180053353  mov     rcx, [rsp+120h+var_E0]
0x180053358  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005335c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053361  mov     eax, ebx
0x180053363  mov     rcx, [rbp+57h+var_30]
0x180053367  xor     rcx, rsp; StackCookie
0x18005336a  call    __security_check_cookie
0x18005336f  mov     rbx, [rsp+120h+arg_18]
0x180053377  add     rsp, 100h
0x18005337e  pop     r15
0x180053380  pop     r14
0x180053382  pop     rdi
0x180053383  pop     rsi
0x180053384  pop     rbp
0x180053385  retn
```
