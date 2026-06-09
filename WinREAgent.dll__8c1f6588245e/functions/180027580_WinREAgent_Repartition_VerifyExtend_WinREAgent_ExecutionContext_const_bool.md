# WinREAgent::Repartition::VerifyExtend(WinREAgent::ExecutionContext const *,bool &)

- ea: `0x180027580`
- end: `0x180027a58`
- name: `?VerifyExtend@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@AEA_N@Z`
- size: `1240`
- prototype: `__int64 __fastcall(WinREAgent::Repartition *__hidden this, const struct WinREAgent::ExecutionContext *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027a60`

## callees

- `0x180004af8`
- `0x180004dd8`
- `0x180005974`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180013e74`
- `0x180027580`
- `0x18002dee0`
- `0x18002e1f8`
- `0x180033394`
- `0x1800346cc`
- `0x18003717c`
- `0x180037344`
- `0x18003bbf4`
- `0x180047d1c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180027655`: `IsCleanupAllowedInCommit`
- `0x18002761b`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800276a5`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002770d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027775`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027622`: `WinREAgent::Repartition::VerifyExtend`
- `0x1800276ac`: `WinREAgent::Repartition::VerifyExtend`
- `0x180027714`: `WinREAgent::Repartition::VerifyExtend`
- `0x18002777c`: `WinREAgent::Repartition::VerifyExtend`
- `0x180027861`: `ScheduledShrinkSize`
- `0x1800278b1`: `Repartition: Additional extendable space besides used by repartition: [%llu]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::Repartition::VerifyExtend(
        WinREAgent::Repartition *this,
        const struct WinREAgent::ExecutionContext *a2,
        bool *a3)
{
  WinREAgent::TelemetrySession *v6; // rsi
  char IsEnabled; // al
  char *v8; // rdx
  int Info; // ebx
  const unsigned __int16 *v10; // r9
  __int64 v11; // rax
  PushButtonReset::Partition *v12; // rax
  unsigned __int64 *v13; // r8
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // r15
  unsigned __int64 v18; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-91h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-89h] BYREF
  bool v21; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v23[48]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v24; // [rsp+90h] [rbp-39h]

  PushButtonReset::Logging::Trace(0, L"Repartition: Verify scenario to extend WinRE partition");
  v6 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  v21 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v22);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl);
  v8 = (char *)this + 240;
  if ( !IsEnabled )
    v8 = 0;
  Info = WinREAgent::WinREIsWinRECleanupAllowed((_QWORD *)a2 + 15, (__int64)v8, &v21, &v22);
  if ( Info >= 0 )
  {
    if ( v6 )
    {
      v10 = L"True";
      if ( !v21 )
        v10 = L"False";
      WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"IsCleanupAllowedInCommit", v10);
      if ( *((_DWORD *)v22 - 4) )
        WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"UnknownContentOnWinREPartition", v22);
    }
    if ( !v21 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942450LL,
        "WinREAgent::Repartition::VerifyExtend",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        150,
        L"Cleanup WinRE partition is not allowed by policy");
      Info = -2147024846;
      goto LABEL_35;
    }
    v20[1] = 0;
    v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    v11 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v20);
    Info = PushButtonReset::Partition::FindByFilePath((char *)a2 + 120, v11);
    if ( Info >= 0 )
    {
      PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v23);
      v12 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v20[0] + 24LL))(v20);
      Info = PushButtonReset::Partition::GetInfo(v12, (struct PushButtonReset::PartitionInfo *)v23);
      if ( Info >= 0 )
      {
        v18 = 0;
        v19 = 0;
        Info = WinREAgent::WinREOSResizeBound((WinREAgent *)&v18, &v19, v13);
        if ( Info >= 0 )
        {
          v14 = v18;
          PushButtonReset::Logging::Trace(0, L"Repartition: Reclaimable space on OS partition:   [%llu]", v18);
          v15 = v19;
          PushButtonReset::Logging::Trace(0, L"Repartition: Extendable space after OS partition: [%llu]", v19);
          PushButtonReset::Logging::Trace(0, L"Repartition: Existing WinRE partition size:       [%llu]", v24);
          PushButtonReset::Logging::Trace(
            0,
            L"Repartition: Target size for WinRE partition:     [%llu]",
            *((_QWORD *)this + 22));
          if ( v6 )
          {
            WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSReclaimableSpace", v14);
            WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSExtendableSpace", v15);
            WinREAgent::TelemetrySession::TraceDataPoint(
              v6,
              L"ExecutionInfoGroup",
              L"ScheduledShrinkSize",
              *((_QWORD *)this + 26));
          }
          if ( v15 + v24 < *((_QWORD *)this + 22) )
          {
            PushButtonReset::Logging::Trace(0, L"Repartition: Confirm needed size for shrink");
            *((_QWORD *)this + 26) = ((*((_QWORD *)this + 22) - v24 - v15 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL) + 0x100000;
            PushButtonReset::Logging::Trace(0, L"Repartition: Need to shrink [%llu] space to extend WinRE partition");
          }
          else
          {
            PushButtonReset::Logging::Trace(
              0,
              L"Repartition: Extendable space is enough for repartition. No need to shrink OS");
            *((_QWORD *)this + 26) = 0;
            v16 = v15 + v24 - *((_QWORD *)this + 22);
            PushButtonReset::Logging::Trace(
              0,
              L"Repartition: Additional extendable space besides used by repartition: [%llu]",
              v16);
            if ( v6 )
              WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSExtraExtendableSpace", v16);
            if ( v16 > 0x6400000 )
            {
              PushButtonReset::Logging::Trace(0, L"Repartition: Significant extendable space left");
              PushButtonReset::Logging::Trace(
                0,
                L"Repartition: There is a concern to use those space as it's unknown what they are used for");
              *a3 = 0;
              PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v23);
              v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
              RAII::CAutoPbrHeapFree<unsigned short *>::Release(v20);
              Info = 0;
              goto LABEL_35;
            }
            PushButtonReset::Logging::Trace(0, L"Repartition: Absorb the additoinal space into new WinRE partition");
            *((_QWORD *)this + 22) = v15 + v24;
            PushButtonReset::Logging::Trace(0, L"Repartition: Adjusted target size for WinRE partition: [%llu]");
          }
          if ( v6 )
            WinREAgent::TelemetrySession::TraceDataPoint(
              v6,
              L"ExecutionInfoGroup",
              L"FinalShrinkSize",
              *((_QWORD *)this + 26));
          if ( v14 < *((_QWORD *)this + 26) )
          {
            PushButtonReset::Logging::Trace(0, L"Repartition Not Enough space to shrink");
            *a3 = 0;
            PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v23);
            v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
            RAII::CAutoPbrHeapFree<unsigned short *>::Release(v20);
            Info = 0;
            goto LABEL_35;
          }
          *a3 = 1;
          PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v23);
          v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
LABEL_34:
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v20);
          goto LABEL_35;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "WinREAgent::Repartition::VerifyExtend",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          167,
          L"Failed to get resize bound of OS partition");
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Info,
          "WinREAgent::Repartition::VerifyExtend",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          161,
          L"Failed to get WinRE partition info");
      }
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v23);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Repartition::VerifyExtend",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        156,
        L"Failed to get partition for WinRE");
    }
    v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
    goto LABEL_34;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Info,
    "WinREAgent::Repartition::VerifyExtend",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    132,
    L"Failed to check whether cleanup WinRE partition is allowed");
LABEL_35:
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
  return (unsigned int)Info;
}

```

## disassembly

```asm
0x180027580  mov     [rsp-8+arg_18], rbx
0x180027585  push    rbp
0x180027586  push    rsi
0x180027587  push    rdi
0x180027588  push    r12
0x18002758a  push    r13
0x18002758c  push    r14
0x18002758e  push    r15
0x180027590  lea     rbp, [rsp-27h]
0x180027595  sub     rsp, 0F0h
0x18002759c  mov     rax, cs:__security_cookie
0x1800275a3  xor     rax, rsp
0x1800275a6  mov     [rbp+57h+var_40], rax
0x1800275aa  mov     r12, r8
0x1800275ad  mov     r14, rdx
0x1800275b0  mov     rdi, rcx
0x1800275b3  lea     rdx, aRepartitionVer; "Repartition: Verify scenario to extend "...
0x1800275ba  xor     ecx, ecx
0x1800275bc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800275c1  mov     rsi, [rdi+70h]
0x1800275c5  xor     r15d, r15d
0x1800275c8  mov     [rbp+57h+var_D0], r15b
0x1800275cc  lea     rcx, [rbp+57h+var_C8]
0x1800275d0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800275d5  nop
0x1800275d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl(void)'::`2'::impl
0x1800275dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled(void)
0x1800275e2  test    al, al
0x1800275e4  lea     rdx, [rdi+0F0h]
0x1800275eb  jnz     short loc_1800275F0
0x1800275ed  mov     edx, r15d
0x1800275f0  lea     r9, [rbp+57h+var_C8]
0x1800275f4  lea     r8, [rbp+57h+var_D0]
0x1800275f8  lea     rcx, [r14+78h]
0x1800275fc  call    ?WinREIsWinRECleanupAllowed@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@PEA_NPEAV23@@Z; WinREAgent::WinREIsWinRECleanupAllowed(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180027601  mov     ebx, eax
0x180027603  test    eax, eax
0x180027605  jns     short loc_18002763A
0x180027607  lea     rax, aFailedToCheckW_7; "Failed to check whether cleanup WinRE p"...
0x18002760e  mov     [rsp+120h+var_F8], rax
0x180027613  mov     [rsp+120h+var_100], 84h
0x18002761b  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027622  lea     r8, aWinreagentRepa_9; "WinREAgent::Repartition::VerifyExtend"
0x180027629  mov     edx, ebx
0x18002762b  mov     ecx, 2
0x180027630  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027635  jmp     loc_180027A22
0x18002763a  test    rsi, rsi
0x18002763d  jz      short loc_18002768B
0x18002763f  lea     r9, aTrue_0; "True"
0x180027646  lea     rax, aFalse_1; "False"
0x18002764d  cmp     [rbp+57h+var_D0], r15b
0x180027651  cmovz   r9, rax; unsigned __int16 *
0x180027655  lea     r8, aIscleanupallow_0; "IsCleanupAllowedInCommit"
0x18002765c  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027663  mov     rcx, rsi; this
0x180027666  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18002766b  mov     r9, [rbp+57h+var_C8]; unsigned __int16 *
0x18002766f  cmp     [r9-10h], r15d
0x180027673  jz      short loc_18002768B
0x180027675  lea     r8, aUnknowncontent_0; "UnknownContentOnWinREPartition"
0x18002767c  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027683  mov     rcx, rsi; this
0x180027686  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18002768b  cmp     [rbp+57h+var_D0], r15b
0x18002768f  jnz     short loc_1800276CC
0x180027691  lea     rax, aCleanupWinrePa_0; "Cleanup WinRE partition is not allowed "...
0x180027698  mov     [rsp+120h+var_F8], rax
0x18002769d  mov     [rsp+120h+var_100], 96h
0x1800276a5  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800276ac  lea     r8, aWinreagentRepa_9; "WinREAgent::Repartition::VerifyExtend"
0x1800276b3  mov     edx, 80070032h
0x1800276b8  mov     ecx, 2
0x1800276bd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800276c2  mov     ebx, 80070032h
0x1800276c7  jmp     loc_180027A22
0x1800276cc  mov     [rsp+120h+var_D8], r15
0x1800276d1  lea     r13, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x1800276d8  mov     [rsp+120h+var_E0], r13
0x1800276dd  lea     rcx, [rsp+120h+var_E0]
0x1800276e2  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800276e7  mov     rdx, rax
0x1800276ea  lea     rcx, [r14+78h]
0x1800276ee  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x1800276f3  mov     ebx, eax
0x1800276f5  test    eax, eax
0x1800276f7  jns     short loc_180027732
0x1800276f9  lea     rax, aFailedToGetPar_0; "Failed to get partition for WinRE"
0x180027700  mov     [rsp+120h+var_F8], rax
0x180027705  mov     [rsp+120h+var_100], 9Ch
0x18002770d  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027714  lea     r8, aWinreagentRepa_9; "WinREAgent::Repartition::VerifyExtend"
0x18002771b  mov     edx, ebx
0x18002771d  mov     ecx, 2
0x180027722  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027727  nop
0x180027728  mov     [rsp+120h+var_E0], r13
0x18002772d  jmp     loc_180027A17
0x180027732  lea     rcx, [rbp+57h+var_C0]; this
0x180027736  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18002773b  nop
0x18002773c  mov     rax, [rsp+120h+var_E0]
0x180027741  lea     rcx, [rsp+120h+var_E0]
0x180027746  mov     rax, [rax+18h]
0x18002774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002774f  lea     rdx, [rbp+57h+var_C0]; struct PushButtonReset::PartitionInfo *
0x180027753  mov     rcx, rax; this
0x180027756  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18002775b  mov     ebx, eax
0x18002775d  test    eax, eax
0x18002775f  jns     short loc_18002779B
0x180027761  lea     rax, aFailedToGetWin_4; "Failed to get WinRE partition info"
0x180027768  mov     [rsp+120h+var_F8], rax
0x18002776d  mov     [rsp+120h+var_100], 0A1h
0x180027775  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002777c  lea     r8, aWinreagentRepa_9; "WinREAgent::Repartition::VerifyExtend"
0x180027783  mov     edx, ebx
0x180027785  mov     ecx, 2
0x18002778a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002778f  nop
0x180027790  lea     rcx, [rbp+57h+var_C0]; this
0x180027794  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180027799  jmp     short loc_180027728
0x18002779b  mov     [rsp+120h+var_F0], r15
0x1800277a0  mov     [rsp+120h+var_E8], r15
0x1800277a5  lea     rdx, [rsp+120h+var_E8]; unsigned __int64 *
0x1800277aa  lea     rcx, [rsp+120h+var_F0]; this
0x1800277af  call    ?WinREOSResizeBound@WinREAgent@@YAJPEA_K0@Z; WinREAgent::WinREOSResizeBound(unsigned __int64 *,unsigned __int64 *)
0x1800277b4  mov     ebx, eax
0x1800277b6  test    eax, eax
0x1800277b8  jns     short loc_1800277D0
0x1800277ba  lea     rax, aFailedToGetRes; "Failed to get resize bound of OS partit"...
0x1800277c1  mov     [rsp+120h+var_F8], rax
0x1800277c6  mov     [rsp+120h+var_100], 0A7h
0x1800277ce  jmp     short loc_180027775
0x1800277d0  mov     r13, [rsp+120h+var_F0]
0x1800277d5  mov     r8, r13
0x1800277d8  lea     rdx, aRepartitionRec; "Repartition: Reclaimable space on OS pa"...
0x1800277df  xor     ecx, ecx
0x1800277e1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800277e6  mov     r14, [rsp+120h+var_E8]
0x1800277eb  mov     r8, r14
0x1800277ee  lea     rdx, aRepartitionExt; "Repartition: Extendable space after OS "...
0x1800277f5  xor     ecx, ecx
0x1800277f7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800277fc  mov     r8, [rbp+57h+var_90]
0x180027800  lea     rdx, aRepartitionExi; "Repartition: Existing WinRE partition s"...
0x180027807  xor     ecx, ecx
0x180027809  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002780e  mov     r8, [rdi+0B0h]
0x180027815  lea     rdx, aRepartitionTar; "Repartition: Target size for WinRE part"...
0x18002781c  xor     ecx, ecx
0x18002781e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027823  test    rsi, rsi
0x180027826  jz      short loc_180027877
0x180027828  mov     r9, r13; unsigned __int64
0x18002782b  lea     r8, aOsreclaimables; "OSReclaimableSpace"
0x180027832  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027839  mov     rcx, rsi; this
0x18002783c  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180027841  mov     r9, r14; unsigned __int64
0x180027844  lea     r8, aOsextendablesp; "OSExtendableSpace"
0x18002784b  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027852  mov     rcx, rsi; this
0x180027855  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x18002785a  mov     r9, [rdi+0D0h]; unsigned __int64
0x180027861  lea     r8, aScheduledshrin; "ScheduledShrinkSize"
0x180027868  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x18002786f  mov     rcx, rsi; this
0x180027872  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180027877  mov     rcx, [rbp+57h+var_90]
0x18002787b  add     rcx, r14
0x18002787e  cmp     rcx, [rdi+0B0h]
0x180027885  jb      loc_180027954
0x18002788b  lea     rdx, aRepartitionExt_1; "Repartition: Extendable space is enough"...
0x180027892  xor     ecx, ecx
0x180027894  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027899  mov     [rdi+0D0h], r15
0x1800278a0  mov     r15, [rbp+57h+var_90]
0x1800278a4  sub     r15, [rdi+0B0h]
0x1800278ab  add     r15, r14
0x1800278ae  mov     r8, r15
0x1800278b1  lea     rdx, aRepartitionAdd_0; "Repartition: Additional extendable spac"...
0x1800278b8  xor     ecx, ecx
0x1800278ba  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800278bf  test    rsi, rsi
0x1800278c2  jz      short loc_1800278DD
0x1800278c4  mov     r9, r15; unsigned __int64
0x1800278c7  lea     r8, aOsextraextenda; "OSExtraExtendableSpace"
0x1800278ce  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x1800278d5  mov     rcx, rsi; this
0x1800278d8  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x1800278dd  xor     ecx, ecx
0x1800278df  cmp     r15, 6400000h
0x1800278e6  jbe     short loc_18002792E
0x1800278e8  lea     rdx, aRepartitionSig; "Repartition: Significant extendable spa"...
0x1800278ef  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800278f4  lea     rdx, aRepartitionThe; "Repartition: There is a concern to use "...
0x1800278fb  xor     ecx, ecx
0x1800278fd  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027902  mov     byte ptr [r12], 0
0x180027907  lea     rcx, [rbp+57h+var_C0]; this
0x18002790b  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180027910  nop
0x180027911  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180027918  mov     [rsp+120h+var_E0], rax
0x18002791d  lea     rcx, [rsp+120h+var_E0]
0x180027922  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180027927  xor     ebx, ebx
0x180027929  jmp     loc_180027A22
0x18002792e  lea     rdx, aRepartitionAbs; "Repartition: Absorb the additoinal spac"...
0x180027935  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002793a  mov     r8, [rbp+57h+var_90]
0x18002793e  add     r8, r14
0x180027941  mov     [rdi+0B0h], r8
0x180027948  lea     rdx, aRepartitionAdj; "Repartition: Adjusted target size for W"...
0x18002794f  xor     r15d, r15d
0x180027952  jmp     short loc_180027993
0x180027954  lea     rdx, aRepartitionCon; "Repartition: Confirm needed size for sh"...
0x18002795b  xor     ecx, ecx
0x18002795d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027962  mov     r8, [rdi+0B0h]
0x180027969  sub     r8, [rbp+57h+var_90]
0x18002796d  sub     r8, r14
0x180027970  add     r8, 0FFFFFh
0x180027977  and     r8, 0FFFFFFFFFFF00000h
0x18002797e  add     r8, 100000h
0x180027985  mov     [rdi+0D0h], r8
0x18002798c  lea     rdx, aRepartitionNee; "Repartition: Need to shrink [%llu] spac"...
0x180027993  xor     ecx, ecx
0x180027995  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002799a  test    rsi, rsi
0x18002799d  jz      short loc_1800279BC
0x18002799f  mov     r9, [rdi+0D0h]; unsigned __int64
0x1800279a6  lea     r8, aFinalshrinksiz; "FinalShrinkSize"
0x1800279ad  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x1800279b4  mov     rcx, rsi; this
0x1800279b7  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x1800279bc  cmp     r13, [rdi+0D0h]
0x1800279c3  jnb     short loc_1800279FC
0x1800279c5  lea     rdx, aRepartitionNot; "Repartition Not Enough space to shrink"
0x1800279cc  xor     ecx, ecx
0x1800279ce  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800279d3  mov     [r12], r15b
0x1800279d7  lea     rcx, [rbp+57h+var_C0]; this
0x1800279db  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x1800279e0  nop
0x1800279e1  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x1800279e8  mov     [rsp+120h+var_E0], rax
0x1800279ed  lea     rcx, [rsp+120h+var_E0]
0x1800279f2  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800279f7  mov     ebx, r15d
0x1800279fa  jmp     short loc_180027A22
0x1800279fc  mov     byte ptr [r12], 1
0x180027a01  lea     rcx, [rbp+57h+var_C0]; this
0x180027a05  call    ??1PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::~PartitionInfo(void)
0x180027a0a  nop
0x180027a0b  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180027a12  mov     [rsp+120h+var_E0], rax
0x180027a17  lea     rcx, [rsp+120h+var_E0]
0x180027a1c  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180027a21  nop
0x180027a22  mov     rcx, [rbp+57h+var_C8]
0x180027a26  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027a2a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027a2f  mov     eax, ebx
0x180027a31  mov     rcx, [rbp+57h+var_40]
0x180027a35  xor     rcx, rsp; StackCookie
0x180027a38  call    __security_check_cookie
0x180027a3d  mov     rbx, [rsp+120h+arg_18]
0x180027a45  add     rsp, 0F0h
0x180027a4c  pop     r15
0x180027a4e  pop     r14
0x180027a50  pop     r13
0x180027a52  pop     r12
0x180027a54  pop     rdi
0x180027a55  pop     rsi
0x180027a56  pop     rbp
0x180027a57  retn
```
