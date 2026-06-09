# WinREAgent::Repartition::VerifyCreateNew(WinREAgent::ExecutionContext const *,bool &)

- ea: `0x180027204`
- end: `0x180027579`
- name: `?VerifyCreateNew@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@AEA_N@Z`
- size: `885`
- prototype: `__int64 __fastcall(WinREAgent::Repartition *__hidden this, const struct WinREAgent::ExecutionContext *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180027a60`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180027204`
- `0x18002dee0`
- `0x18002e1f8`
- `0x180033394`
- `0x1800346cc`
- `0x18003717c`
- `0x180037344`
- `0x18006c690`

## string_xrefs

- `0x1800272bb`: `IsCleanupAllowedInCommit`
- `0x180027282`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002730b`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027362`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800273ff`: `ScheduledShrinkSize`
- `0x180027444`: `Repartition: Additional extendable space besides used by repartition: [%llu]`
- `0x180027232`: `Repartition: Verify scenario to create new WinRE partition`
- `0x180027289`: `WinREAgent::Repartition::VerifyCreateNew`
- `0x180027312`: `WinREAgent::Repartition::VerifyCreateNew`
- `0x180027369`: `WinREAgent::Repartition::VerifyCreateNew`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::Repartition::VerifyCreateNew(
        WinREAgent::Repartition *this,
        const struct WinREAgent::ExecutionContext *a2,
        bool *a3)
{
  WinREAgent::TelemetrySession *v6; // rdi
  int v7; // ebx
  unsigned __int64 *v8; // r8
  const unsigned __int16 *v9; // r9
  int v10; // r14d
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rbx
  unsigned __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  bool v18; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-18h] BYREF

  PushButtonReset::Logging::Trace(0, L"Repartition: Verify scenario to create new WinRE partition");
  v6 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  v18 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v19);
  v7 = WinREAgent::WinREIsWinRECleanupAllowed((_QWORD *)a2 + 15, 0, &v18, &v19);
  if ( v7 >= 0 )
  {
    if ( v6 )
    {
      v9 = L"True";
      if ( !v18 )
        v9 = L"False";
      WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ServicingInfoGroup", L"IsCleanupAllowedInCommit", v9);
      if ( *((_DWORD *)v19 - 4) )
        WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ServicingInfoGroup", L"UnknownContentOnWinREPartition", v19);
    }
    if ( v18 )
    {
      v16 = 0;
      v17 = 0;
      v10 = WinREAgent::WinREOSResizeBound((WinREAgent *)&v16, &v17, v8);
      if ( v10 >= 0 )
      {
        v11 = v16;
        PushButtonReset::Logging::Trace(0, L"Repartition: Reclaimable space on OS partition:   [%llu]", v16);
        v12 = v17;
        PushButtonReset::Logging::Trace(0, L"Repartition: Extendable space after OS partition: [%llu]", v17);
        PushButtonReset::Logging::Trace(
          0,
          L"Repartition: Target size for WinRE partition:     [%llu]",
          *((_QWORD *)this + 22));
        if ( v6 )
        {
          WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSReclaimableSpace", v11);
          WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSExtendableSpace", v12);
          WinREAgent::TelemetrySession::TraceDataPoint(
            v6,
            L"ExecutionInfoGroup",
            L"ScheduledShrinkSize",
            *((_QWORD *)this + 26));
        }
        if ( v12 < *((_QWORD *)this + 22) )
        {
          PushButtonReset::Logging::Trace(0, L"Repartition: Confirm needed size for shrink");
          v14 = (*((_QWORD *)this + 22) - v12 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
          *((_QWORD *)this + 26) = v14;
          PushButtonReset::Logging::Trace(0, L"Repartition: Need to shrink [%llu] space to extend WinRE partition", v14);
        }
        else
        {
          PushButtonReset::Logging::Trace(
            0,
            L"Repartition: Extendable space is enough for repartition. No need to shrink OS");
          *((_QWORD *)this + 26) = 0;
          v13 = v12 - *((_QWORD *)this + 22);
          PushButtonReset::Logging::Trace(
            0,
            L"Repartition: Additional extendable space besides used by repartition: [%llu]",
            v13);
          if ( v6 )
            WinREAgent::TelemetrySession::TraceDataPoint(v6, L"ExecutionInfoGroup", L"OSExtraExtendableSpace", v13);
          if ( v13 > 0x6400000 )
          {
            PushButtonReset::Logging::Trace(0, L"Repartition: Significant extendable space left");
            PushButtonReset::Logging::Trace(
              0,
              L"Repartition: There is a concern to use those space as it's unknown what they are used for");
            *a3 = 0;
            v7 = 0;
            goto LABEL_27;
          }
          PushButtonReset::Logging::Trace(0, L"Repartition: Absorb the additoinal space into new WinRE partition");
          *((_QWORD *)this + 22) = v12;
          PushButtonReset::Logging::Trace(0, L"Repartition: Adjusted target size for WinRE partition: [%llu]", v12);
        }
        if ( v6 )
          WinREAgent::TelemetrySession::TraceDataPoint(
            v6,
            L"ExecutionInfoGroup",
            L"FinalShrinkSize",
            *((_QWORD *)this + 26));
        if ( v11 < *((_QWORD *)this + 26) )
        {
          PushButtonReset::Logging::Trace(0, L"Repartition Not Enough space to shrink");
          *a3 = 0;
          v7 = 0;
          goto LABEL_27;
        }
        *a3 = 1;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v10,
          "WinREAgent::Repartition::VerifyCreateNew",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          275,
          L"Failed to get resize bound of OS partition");
      }
      v7 = v10;
      goto LABEL_27;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942450LL,
      "WinREAgent::Repartition::VerifyCreateNew",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      268,
      L"Cleanup WinRE partition is not allowed by policy");
    v7 = -2147024846;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "WinREAgent::Repartition::VerifyCreateNew",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      250,
      L"Failed to check whether cleanup WinRE partition is allowed");
  }
LABEL_27:
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180027204  mov     [rsp-38h+arg_18], rbx
0x180027209  push    rbp
0x18002720a  push    rsi
0x18002720b  push    rdi
0x18002720c  push    r12
0x18002720e  push    r13
0x180027210  push    r14
0x180027212  push    r15
0x180027214  mov     rbp, rsp
0x180027217  sub     rsp, 60h
0x18002721b  mov     rax, cs:__security_cookie
0x180027222  xor     rax, rsp
0x180027225  mov     [rbp+var_10], rax
0x180027229  mov     r12, r8
0x18002722c  mov     rbx, rdx
0x18002722f  mov     rsi, rcx
0x180027232  lea     rdx, aRepartitionVer_0; "Repartition: Verify scenario to create "...
0x180027239  xor     ecx, ecx
0x18002723b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027240  mov     rdi, [rsi+70h]
0x180027244  xor     r15d, r15d
0x180027247  mov     [rbp+var_20], r15b
0x18002724b  lea     rcx, [rbp+var_18]
0x18002724f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180027254  nop
0x180027255  lea     rcx, [rbx+78h]
0x180027259  lea     r9, [rbp+var_18]
0x18002725d  lea     r8, [rbp+var_20]
0x180027261  xor     edx, edx
0x180027263  call    ?WinREIsWinRECleanupAllowed@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@PEA_NPEAV23@@Z; WinREAgent::WinREIsWinRECleanupAllowed(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180027268  mov     ebx, eax
0x18002726a  test    eax, eax
0x18002726c  jns     short loc_1800272A0
0x18002726e  lea     rax, aFailedToCheckW_7; "Failed to check whether cleanup WinRE p"...
0x180027275  mov     [rsp+60h+var_38], rax
0x18002727a  mov     [rsp+60h+var_40], 0FAh
0x180027282  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027289  lea     r8, aWinreagentRepa_3; "WinREAgent::Repartition::VerifyCreateNe"...
0x180027290  mov     edx, ebx
0x180027292  lea     ecx, [r15+2]
0x180027296  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002729b  jmp     loc_180027546
0x1800272a0  test    rdi, rdi
0x1800272a3  jz      short loc_1800272F1
0x1800272a5  lea     r9, aTrue_0; "True"
0x1800272ac  lea     rax, aFalse_1; "False"
0x1800272b3  cmp     [rbp+var_20], r15b
0x1800272b7  cmovz   r9, rax; unsigned __int16 *
0x1800272bb  lea     r8, aIscleanupallow_0; "IsCleanupAllowedInCommit"
0x1800272c2  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800272c9  mov     rcx, rdi; this
0x1800272cc  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x1800272d1  mov     r9, [rbp+var_18]; unsigned __int16 *
0x1800272d5  cmp     [r9-10h], r15d
0x1800272d9  jz      short loc_1800272F1
0x1800272db  lea     r8, aUnknowncontent_0; "UnknownContentOnWinREPartition"
0x1800272e2  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800272e9  mov     rcx, rdi; this
0x1800272ec  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x1800272f1  cmp     [rbp+var_20], r15b
0x1800272f5  jnz     short loc_180027332
0x1800272f7  lea     rax, aCleanupWinrePa_0; "Cleanup WinRE partition is not allowed "...
0x1800272fe  mov     [rsp+60h+var_38], rax
0x180027303  mov     [rsp+60h+var_40], 10Ch
0x18002730b  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027312  lea     r8, aWinreagentRepa_3; "WinREAgent::Repartition::VerifyCreateNe"...
0x180027319  mov     edx, 80070032h
0x18002731e  mov     ecx, 2
0x180027323  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027328  mov     ebx, 80070032h
0x18002732d  jmp     loc_180027546
0x180027332  mov     [rbp+var_30], r15
0x180027336  mov     [rbp+var_28], r15
0x18002733a  lea     rdx, [rbp+var_28]; unsigned __int64 *
0x18002733e  lea     rcx, [rbp+var_30]; this
0x180027342  call    ?WinREOSResizeBound@WinREAgent@@YAJPEA_K0@Z; WinREAgent::WinREOSResizeBound(unsigned __int64 *,unsigned __int64 *)
0x180027347  mov     r14d, eax
0x18002734a  test    eax, eax
0x18002734c  jns     short loc_180027382
0x18002734e  lea     rax, aFailedToGetRes; "Failed to get resize bound of OS partit"...
0x180027355  mov     [rsp+60h+var_38], rax
0x18002735a  mov     [rsp+60h+var_40], 113h
0x180027362  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027369  lea     r8, aWinreagentRepa_3; "WinREAgent::Repartition::VerifyCreateNe"...
0x180027370  mov     edx, r14d
0x180027373  mov     ecx, 2
0x180027378  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002737d  jmp     loc_180027543
0x180027382  mov     r13, [rbp+var_30]
0x180027386  mov     r8, r13
0x180027389  lea     rdx, aRepartitionRec; "Repartition: Reclaimable space on OS pa"...
0x180027390  xor     ecx, ecx
0x180027392  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027397  mov     rbx, [rbp+var_28]
0x18002739b  mov     r8, rbx
0x18002739e  lea     rdx, aRepartitionExt; "Repartition: Extendable space after OS "...
0x1800273a5  xor     ecx, ecx
0x1800273a7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800273ac  mov     r8, [rsi+0B0h]
0x1800273b3  lea     rdx, aRepartitionTar; "Repartition: Target size for WinRE part"...
0x1800273ba  xor     ecx, ecx
0x1800273bc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800273c1  test    rdi, rdi
0x1800273c4  jz      short loc_180027415
0x1800273c6  mov     r9, r13; unsigned __int64
0x1800273c9  lea     r8, aOsreclaimables; "OSReclaimableSpace"
0x1800273d0  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x1800273d7  mov     rcx, rdi; this
0x1800273da  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x1800273df  mov     r9, rbx; unsigned __int64
0x1800273e2  lea     r8, aOsextendablesp; "OSExtendableSpace"
0x1800273e9  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x1800273f0  mov     rcx, rdi; this
0x1800273f3  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x1800273f8  mov     r9, [rsi+0D0h]; unsigned __int64
0x1800273ff  lea     r8, aScheduledshrin; "ScheduledShrinkSize"
0x180027406  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x18002740d  mov     rcx, rdi; this
0x180027410  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180027415  xor     ecx, ecx
0x180027417  cmp     rbx, [rsi+0B0h]
0x18002741e  jb      loc_1800274C0
0x180027424  lea     rdx, aRepartitionExt_1; "Repartition: Extendable space is enough"...
0x18002742b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027430  mov     [rsi+0D0h], r15
0x180027437  mov     r15, rbx
0x18002743a  sub     r15, [rsi+0B0h]
0x180027441  mov     r8, r15
0x180027444  lea     rdx, aRepartitionAdd_0; "Repartition: Additional extendable spac"...
0x18002744b  xor     ecx, ecx
0x18002744d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027452  test    rdi, rdi
0x180027455  jz      short loc_180027470
0x180027457  mov     r9, r15; unsigned __int64
0x18002745a  lea     r8, aOsextraextenda; "OSExtraExtendableSpace"
0x180027461  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027468  mov     rcx, rdi; this
0x18002746b  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180027470  xor     ecx, ecx
0x180027472  cmp     r15, 6400000h
0x180027479  jbe     short loc_1800274A1
0x18002747b  lea     rdx, aRepartitionSig; "Repartition: Significant extendable spa"...
0x180027482  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027487  lea     rdx, aRepartitionThe; "Repartition: There is a concern to use "...
0x18002748e  xor     ecx, ecx
0x180027490  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027495  mov     byte ptr [r12], 0
0x18002749a  xor     ebx, ebx
0x18002749c  jmp     loc_180027546
0x1800274a1  lea     rdx, aRepartitionAbs; "Repartition: Absorb the additoinal spac"...
0x1800274a8  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800274ad  mov     [rsi+0B0h], rbx
0x1800274b4  lea     rdx, aRepartitionAdj; "Repartition: Adjusted target size for W"...
0x1800274bb  xor     r15d, r15d
0x1800274be  jmp     short loc_1800274F2
0x1800274c0  lea     rdx, aRepartitionCon; "Repartition: Confirm needed size for sh"...
0x1800274c7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800274cc  mov     rax, [rsi+0B0h]
0x1800274d3  sub     rax, rbx
0x1800274d6  lea     rbx, [rax+0FFFFFh]
0x1800274dd  and     rbx, 0FFFFFFFFFFF00000h
0x1800274e4  mov     [rsi+0D0h], rbx
0x1800274eb  lea     rdx, aRepartitionNee; "Repartition: Need to shrink [%llu] spac"...
0x1800274f2  mov     r8, rbx
0x1800274f5  xor     ecx, ecx
0x1800274f7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800274fc  test    rdi, rdi
0x1800274ff  jz      short loc_18002751E
0x180027501  mov     r9, [rsi+0D0h]; unsigned __int64
0x180027508  lea     r8, aFinalshrinksiz; "FinalShrinkSize"
0x18002750f  lea     rdx, aExecutioninfog; "ExecutionInfoGroup"
0x180027516  mov     rcx, rdi; this
0x180027519  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x18002751e  cmp     r13, [rsi+0D0h]
0x180027525  jnb     short loc_18002753E
0x180027527  lea     rdx, aRepartitionNot; "Repartition Not Enough space to shrink"
0x18002752e  xor     ecx, ecx
0x180027530  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027535  mov     [r12], r15b
0x180027539  mov     ebx, r15d
0x18002753c  jmp     short loc_180027546
0x18002753e  mov     byte ptr [r12], 1
0x180027543  mov     ebx, r14d
0x180027546  mov     rcx, [rbp+var_18]
0x18002754a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002754e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027553  mov     eax, ebx
0x180027555  mov     rcx, [rbp+var_10]
0x180027559  xor     rcx, rsp; StackCookie
0x18002755c  call    __security_check_cookie
0x180027561  mov     rbx, [rsp+60h+arg_18]
0x180027569  add     rsp, 60h
0x18002756d  pop     r15
0x18002756f  pop     r14
0x180027571  pop     r13
0x180027573  pop     r12
0x180027575  pop     rdi
0x180027576  pop     rsi
0x180027577  pop     rbp
0x180027578  retn
```
