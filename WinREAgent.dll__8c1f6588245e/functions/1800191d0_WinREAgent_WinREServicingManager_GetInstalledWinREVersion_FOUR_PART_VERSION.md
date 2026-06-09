# WinREAgent::WinREServicingManager::GetInstalledWinREVersion(_FOUR_PART_VERSION *)

- ea: `0x1800191d0`
- end: `0x18001971e`
- name: `?GetInstalledWinREVersion@WinREServicingManager@WinREAgent@@UEAAJPEAT_FOUR_PART_VERSION@@@Z`
- size: `1358`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, union _FOUR_PART_VERSION *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180005cc0`
- `0x18000d570`
- `0x18000d640`
- `0x18000d92c`
- `0x1800158bc`
- `0x1800191d0`
- `0x18001b1c0`
- `0x18001e51c`
- `0x18002e384`
- `0x18002e448`
- `0x18002f378`
- `0x18003717c`
- `0x180037344`
- `0x180050390`
- `0x18006f010`

## import_xrefs

- `DismApi!DismGetImageInfo` at `0x180019515`
- `DismApi!DismGetImageInfo` at `0x180019515`

## string_xrefs

- `0x1800193fb`: `Failed to create execution context`
- `0x180019486`: `Failed to open DISM session`
- `0x1800191ed`: `Enter WinREAgent::WinREServicingManager::GetInstalledWinREVersion`
- `0x180019219`: `WinREAgent::WinREServicingManager::GetInstalledWinREVersion`
- `0x1800192df`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001940f`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001949a`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001959b`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001970a`: `Exit WinREAgent::WinREServicingManager::GetInstalledWinREVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::WinREServicingManager::GetInstalledWinREVersion(
        WinREAgent::WinREServicingManager *this,
        union _FOUR_PART_VERSION *a2)
{
  char *v4; // rsi
  __int64 v5; // rbx
  char v6; // al
  unsigned int ExecutionContext; // edi
  __int64 v8; // rbx
  char v9; // al
  __int64 v10; // rbx
  __int64 *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // ebx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  WinREAgent::TelemetrySession *v21; // rax
  __int64 v22; // rbx
  _QWORD v23[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-10h] BYREF
  int v26; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+50h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
  v4 = (char *)this + 24;
  v27 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v27) )
  {
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))((char *)this + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
    WinREAgent::TelemetrySession::TraceEnterAPI(v5, &v27);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  }
  if ( !*((_BYTE *)this + 64) )
  {
    v27 = 0;
    v6 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))((char *)this + 24, &v27);
    ExecutionContext = -2147024875;
    if ( v6 )
    {
      v8 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v27,
        (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v8, &v27, 2147942421LL);
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942421LL,
      "WinREAgent::WinREServicingManager::GetInstalledWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      144,
      L"Must initialize WinREServicingManager first");
    return ExecutionContext;
  }
  if ( !a2 )
  {
    v27 = 0;
    v9 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))((char *)this + 24, &v27);
    ExecutionContext = -2147024809;
    if ( v9 )
    {
      v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v27,
        (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v10, &v27, 2147942487LL);
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREServicingManager::GetInstalledWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      150,
      L"Invalid argument");
    return ExecutionContext;
  }
  v23[1] = 0;
  v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  v11 = (__int64 *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v23);
  ExecutionContext = WinREAgent::CreateExecutionContext((__int64 *)this + 7, 0, v11);
  if ( (ExecutionContext & 0x80000000) != 0 )
  {
    v27 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v27) )
    {
      v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v27,
        (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v12, &v27, ExecutionContext);
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      ExecutionContext,
      "WinREAgent::WinREServicingManager::GetInstalledWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      160,
      L"Failed to create execution context");
    goto LABEL_25;
  }
  v25[1] = 0;
  v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
  v13 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v25);
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(v23[0] + 24LL))(v23) + 184;
  v15 = (*(__int64 (__fastcall **)(_QWORD *))(v23[0] + 24LL))(v23);
  v16 = PushButtonReset::DismAutoShutdown::Create(v15 + 216, v14, v13);
  if ( v16 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v16,
      "WinREAgent::WinREServicingManager::GetInstalledWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      165,
      L"Failed to open DISM session");
    v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v25);
    v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(v23);
    return (unsigned int)v16;
  }
  v24[1] = 0;
  v24[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
  v26 = 0;
  v18 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v24);
  v19 = (*(__int64 (__fastcall **)(_QWORD *))(v23[0] + 24LL))(v23);
  ExecutionContext = DismGetImageInfo(*(_QWORD *)(v19 + 120), v18, &v26);
  if ( (ExecutionContext & 0x80000000) == 0 )
  {
    if ( v26 )
    {
      *((_WORD *)a2 + 3) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 32LL))(v24) + 84);
      *((_WORD *)a2 + 2) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 32LL))(v24) + 88);
      *((_WORD *)a2 + 1) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 32LL))(v24) + 92);
      *(_WORD *)a2 = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 32LL))(v24) + 96);
      v27 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v27) )
      {
        v21 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
        WinREAgent::TelemetrySession::TraceWinREVersion(
          v21,
          *((unsigned __int16 *)a2 + 3),
          *((unsigned __int16 *)a2 + 2),
          *((unsigned __int16 *)a2 + 1),
          *(unsigned __int16 *)a2);
      }
      v27 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v27) )
      {
        v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v27,
          (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v22, &v27, ExecutionContext);
        ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      }
      PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
      goto LABEL_24;
    }
    ExecutionContext = -2147467259;
  }
  v27 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v27) )
  {
    v20 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)"WinREAgent::WinREServicingManager::GetInstalledWinREVersion");
    WinREAgent::TelemetrySession::TraceLeaveAPI(v20, &v27, ExecutionContext);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  }
  PushButtonReset::Logging::TraceErr(
    2,
    ExecutionContext,
    "WinREAgent::WinREServicingManager::GetInstalledWinREVersion",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    179,
    L"Failed to get image info");
LABEL_24:
  v24[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
  RAII::CAutoDismDelete<_DismPackageInfo *>::Release(v24);
  v25[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v25);
LABEL_25:
  v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(v23);
  return ExecutionContext;
}

```

## disassembly

```asm
0x1800191d0  mov     [rsp-38h+arg_8], rbx
0x1800191d5  push    rbp
0x1800191d6  push    rsi
0x1800191d7  push    rdi
0x1800191d8  push    r12
0x1800191da  push    r13
0x1800191dc  push    r14
0x1800191de  push    r15
0x1800191e0  mov     rbp, rsp
0x1800191e3  sub     rsp, 60h
0x1800191e7  mov     r14, rdx
0x1800191ea  mov     rdi, rcx
0x1800191ed  lea     rdx, aEnterWinreagen_5; "Enter WinREAgent::WinREServicingManager"...
0x1800191f4  xor     ecx, ecx
0x1800191f6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800191fb  lea     rsi, [rdi+18h]
0x1800191ff  xor     r15d, r15d
0x180019202  mov     [rbp+arg_10], r15
0x180019206  mov     rax, [rsi]
0x180019209  lea     rdx, [rbp+arg_10]
0x18001920d  mov     rcx, rsi
0x180019210  mov     rax, [rax+40h]
0x180019214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019219  lea     r12, aWinreagentWinr_11; "WinREAgent::WinREServicingManager::GetI"...
0x180019220  test    al, al
0x180019222  jz      short loc_18001925D
0x180019224  mov     rax, [rsi]
0x180019227  mov     rcx, rsi
0x18001922a  mov     rax, [rax+18h]
0x18001922e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019233  mov     rbx, rax
0x180019236  mov     rdx, r12
0x180019239  lea     rcx, [rbp+arg_10]
0x18001923d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180019242  nop
0x180019243  lea     rdx, [rbp+arg_10]
0x180019247  mov     rcx, rbx
0x18001924a  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001924f  nop
0x180019250  mov     rcx, [rbp+arg_10]
0x180019254  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019258  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001925d  cmp     [rdi+40h], r15b
0x180019261  jnz     loc_1800192F5
0x180019267  mov     [rbp+arg_10], r15
0x18001926b  mov     rax, [rsi]
0x18001926e  lea     rdx, [rbp+arg_10]
0x180019272  mov     rcx, rsi
0x180019275  mov     rax, [rax+40h]
0x180019279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001927e  mov     edi, 80070015h
0x180019283  test    al, al
0x180019285  jz      short loc_1800192C3
0x180019287  mov     rax, [rsi]
0x18001928a  mov     rcx, rsi
0x18001928d  mov     rax, [rax+18h]
0x180019291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019296  mov     rbx, rax
0x180019299  mov     rdx, r12
0x18001929c  lea     rcx, [rbp+arg_10]
0x1800192a0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800192a5  nop
0x1800192a6  mov     r8d, edi
0x1800192a9  lea     rdx, [rbp+arg_10]
0x1800192ad  mov     rcx, rbx
0x1800192b0  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x1800192b5  nop
0x1800192b6  mov     rcx, [rbp+arg_10]
0x1800192ba  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800192be  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800192c3  lea     rcx, aMustInitialize; "Must initialize WinREServicingManager f"...
0x1800192ca  mov     [rsp+60h+var_38], rcx
0x1800192cf  mov     [rsp+60h+var_40], 90h
0x1800192d7  mov     edx, 80070015h
0x1800192dc  mov     r8, r12
0x1800192df  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800192e6  mov     ecx, 2
0x1800192eb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800192f0  jmp     loc_1800195E9
0x1800192f5  test    r14, r14
0x1800192f8  jnz     short loc_180019374
0x1800192fa  mov     [rbp+arg_10], r15
0x1800192fe  mov     rax, [rsi]
0x180019301  lea     rdx, [rbp+arg_10]
0x180019305  mov     rcx, rsi
0x180019308  mov     rax, [rax+40h]
0x18001930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019311  mov     edi, 80070057h
0x180019316  test    al, al
0x180019318  jz      short loc_180019356
0x18001931a  mov     rax, [rsi]
0x18001931d  mov     rcx, rsi
0x180019320  mov     rax, [rax+18h]
0x180019324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019329  mov     rbx, rax
0x18001932c  mov     rdx, r12
0x18001932f  lea     rcx, [rbp+arg_10]
0x180019333  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180019338  nop
0x180019339  mov     r8d, edi
0x18001933c  lea     rdx, [rbp+arg_10]
0x180019340  mov     rcx, rbx
0x180019343  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180019348  nop
0x180019349  mov     rcx, [rbp+arg_10]
0x18001934d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019351  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019356  lea     rcx, aInvalidArgumen; "Invalid argument"
0x18001935d  mov     [rsp+60h+var_38], rcx
0x180019362  mov     [rsp+60h+var_40], 96h
0x18001936a  mov     edx, 80070057h
0x18001936f  jmp     loc_1800192DC
0x180019374  mov     [rbp+var_28], r15
0x180019378  lea     r13, ??_7?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable'
0x18001937f  mov     [rbp+var_30], r13
0x180019383  lea     rcx, [rbp+var_30]
0x180019387  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18001938c  mov     r8, rax
0x18001938f  lea     rcx, [rdi+38h]
0x180019393  xor     edx, edx
0x180019395  call    ?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z; WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)
0x18001939a  mov     edi, eax
0x18001939c  test    eax, eax
0x18001939e  jns     loc_18001942A
0x1800193a4  mov     [rbp+arg_10], r15
0x1800193a8  mov     rcx, [rsi]
0x1800193ab  mov     rax, [rcx+40h]
0x1800193af  lea     rdx, [rbp+arg_10]
0x1800193b3  mov     rcx, rsi
0x1800193b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193bb  test    al, al
0x1800193bd  jz      short loc_1800193FB
0x1800193bf  mov     rax, [rsi]
0x1800193c2  mov     rcx, rsi
0x1800193c5  mov     rax, [rax+18h]
0x1800193c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ce  mov     rbx, rax
0x1800193d1  mov     rdx, r12
0x1800193d4  lea     rcx, [rbp+arg_10]
0x1800193d8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800193dd  nop
0x1800193de  mov     r8d, edi
0x1800193e1  lea     rdx, [rbp+arg_10]
0x1800193e5  mov     rcx, rbx
0x1800193e8  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x1800193ed  nop
0x1800193ee  mov     rcx, [rbp+arg_10]
0x1800193f2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800193f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800193fb  lea     rax, aFailedToCreate_6; "Failed to create execution context"
0x180019402  mov     [rsp+60h+var_38], rax
0x180019407  mov     [rsp+60h+var_40], 0A0h
0x18001940f  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019416  mov     r8, r12
0x180019419  mov     edx, edi
0x18001941b  mov     ecx, 2
0x180019420  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019425  jmp     loc_1800195DC
0x18001942a  mov     [rbp+var_8], r15
0x18001942e  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x180019435  mov     [rbp+var_10], rax
0x180019439  lea     rcx, [rbp+var_10]
0x18001943d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180019442  mov     rdi, rax
0x180019445  mov     rcx, [rbp+var_30]
0x180019449  mov     rax, [rcx+18h]
0x18001944d  lea     rcx, [rbp+var_30]
0x180019451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019456  lea     rbx, [rax+0B8h]
0x18001945d  mov     rcx, [rbp+var_30]
0x180019461  mov     rax, [rcx+18h]
0x180019465  lea     rcx, [rbp+var_30]
0x180019469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946e  lea     rcx, [rax+0D8h]
0x180019475  mov     r8, rdi
0x180019478  mov     rdx, rbx
0x18001947b  call    ?Create@DismAutoShutdown@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAPEAV12@@Z; PushButtonReset::DismAutoShutdown::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DismAutoShutdown * *)
0x180019480  mov     ebx, eax
0x180019482  test    eax, eax
0x180019484  jns     short loc_1800194DA
0x180019486  lea     rax, aFailedToOpenDi_1; "Failed to open DISM session"
0x18001948d  mov     [rsp+60h+var_38], rax
0x180019492  mov     [rsp+60h+var_40], 0A5h
0x18001949a  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800194a1  mov     r8, r12
0x1800194a4  mov     edx, ebx
0x1800194a6  mov     ecx, 2
0x1800194ab  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800194b0  nop
0x1800194b1  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x1800194b8  mov     [rbp+var_10], rax
0x1800194bc  lea     rcx, [rbp+var_10]
0x1800194c0  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x1800194c5  nop
0x1800194c6  mov     [rbp+var_30], r13
0x1800194ca  lea     rcx, [rbp+var_30]
0x1800194ce  call    ?Release@?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(void)
0x1800194d3  mov     eax, ebx
0x1800194d5  jmp     loc_1800195EB
0x1800194da  mov     [rbp+var_18], r15
0x1800194de  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x1800194e5  mov     [rbp+var_20], rax
0x1800194e9  mov     [rbp+arg_0], r15d
0x1800194ed  lea     rcx, [rbp+var_20]
0x1800194f1  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800194f6  mov     rbx, rax
0x1800194f9  mov     rcx, [rbp+var_30]
0x1800194fd  mov     rax, [rcx+18h]
0x180019501  lea     rcx, [rbp+var_30]
0x180019505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001950a  lea     r8, [rbp+arg_0]
0x18001950e  mov     rdx, rbx
0x180019511  mov     rcx, [rax+78h]
0x180019515  call    cs:__imp_DismGetImageInfo
0x18001951b  mov     edi, eax
0x18001951d  test    eax, eax
0x18001951f  js      short loc_180019530
0x180019521  cmp     [rbp+arg_0], r15d
0x180019525  jnz     loc_180019603
0x18001952b  mov     edi, 80004005h
0x180019530  mov     [rbp+arg_10], r15
0x180019534  mov     rax, [rsi]
0x180019537  lea     rdx, [rbp+arg_10]
0x18001953b  mov     rcx, rsi
0x18001953e  mov     rax, [rax+40h]
0x180019542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019547  test    al, al
0x180019549  jz      short loc_180019587
0x18001954b  mov     rax, [rsi]
0x18001954e  mov     rcx, rsi
0x180019551  mov     rax, [rax+18h]
0x180019555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001955a  mov     rbx, rax
0x18001955d  mov     rdx, r12
0x180019560  lea     rcx, [rbp+arg_10]
0x180019564  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180019569  nop
0x18001956a  mov     r8d, edi
0x18001956d  lea     rdx, [rbp+arg_10]
0x180019571  mov     rcx, rbx
0x180019574  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180019579  nop
0x18001957a  mov     rcx, [rbp+arg_10]
0x18001957e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019582  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019587  lea     rax, aFailedToGetIma_0; "Failed to get image info"
0x18001958e  mov     [rsp+60h+var_38], rax
0x180019593  mov     [rsp+60h+var_40], 0B3h
0x18001959b  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800195a2  mov     r8, r12
0x1800195a5  mov     edx, edi
0x1800195a7  mov     ecx, 2
0x1800195ac  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800195b1  nop
0x1800195b2  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x1800195b9  mov     [rbp+var_20], rax
0x1800195bd  lea     rcx, [rbp+var_20]
0x1800195c1  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x1800195c6  nop
0x1800195c7  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x1800195ce  mov     [rbp+var_10], rax
0x1800195d2  lea     rcx, [rbp+var_10]
0x1800195d6  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x1800195db  nop
0x1800195dc  mov     [rbp+var_30], r13
0x1800195e0  lea     rcx, [rbp+var_30]
0x1800195e4  call    ?Release@?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(void)
0x1800195e9  mov     eax, edi
0x1800195eb  mov     rbx, [rsp+60h+arg_8]
0x1800195f3  add     rsp, 60h
0x1800195f7  pop     r15
0x1800195f9  pop     r14
0x1800195fb  pop     r13
0x1800195fd  pop     r12
0x1800195ff  pop     rdi
0x180019600  pop     rsi
0x180019601  pop     rbp
0x180019602  retn
0x180019603  mov     rax, [rbp+var_20]
0x180019607  lea     rcx, [rbp+var_20]
0x18001960b  mov     rax, [rax+20h]
0x18001960f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019614  movzx   ecx, word ptr [rax+54h]
0x180019618  mov     [r14+6], cx
0x18001961d  mov     rax, [rbp+var_20]
0x180019621  lea     rcx, [rbp+var_20]
0x180019625  mov     rax, [rax+20h]
0x180019629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001962e  movzx   ecx, word ptr [rax+58h]
0x180019632  mov     [r14+4], cx
0x180019637  mov     rax, [rbp+var_20]
0x18001963b  lea     rcx, [rbp+var_20]
0x18001963f  mov     rax, [rax+20h]
0x180019643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019648  movzx   ecx, word ptr [rax+5Ch]
0x18001964c  mov     [r14+2], cx
0x180019651  mov     rax, [rbp+var_20]
0x180019655  lea     rcx, [rbp+var_20]
0x180019659  mov     rax, [rax+20h]
0x18001965d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
