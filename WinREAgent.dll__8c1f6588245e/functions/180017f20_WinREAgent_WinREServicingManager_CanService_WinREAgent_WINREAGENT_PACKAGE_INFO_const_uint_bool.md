# WinREAgent::WinREServicingManager::CanService(WinREAgent::WINREAGENT_PACKAGE_INFO * const,uint,bool *)

- ea: `0x180017f20`
- end: `0x1800183dd`
- name: `?CanService@WinREServicingManager@WinREAgent@@UEAAJQEAUWINREAGENT_PACKAGE_INFO@2@IPEA_N@Z`
- size: `1213`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, struct WinREAgent::WINREAGENT_PACKAGE_INFO *const, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180004bc4`
- `0x180005708`
- `0x180006564`
- `0x180006b20`
- `0x1800086d8`
- `0x18000d92c`
- `0x18000f254`
- `0x1800158bc`
- `0x180017f20`
- `0x18002e06c`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18001805f`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180018237`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x1800183a2`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180017f48`: `Enter WinREAgent::WinREServicingManager::CanService`
- `0x180017f9d`: `WinREAgent::WinREServicingManager::CanService`
- `0x180018014`: `WinREAgent::WinREServicingManager::CanService`
- `0x180018066`: `WinREAgent::WinREServicingManager::CanService`
- `0x1800180f9`: `WinREAgent::WinREServicingManager::CanService`
- `0x180018189`: `WinREAgent::WinREServicingManager::CanService`
- `0x18001823e`: `WinREAgent::WinREServicingManager::CanService`
- `0x1800182da`: `WinREAgent::WinREServicingManager::CanService`
- `0x180018357`: `WinREAgent::WinREServicingManager::CanService`
- `0x1800183a9`: `WinREAgent::WinREServicingManager::CanService`
- `0x180018291`: `CanService`
- `0x180018311`: `Exit WinREAgent::WinREServicingManager::CanService`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::WinREServicingManager::CanService(
        WinREAgent::WinREServicingManager *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        bool *a4)
{
  char *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rbx
  unsigned int i; // ebx
  unsigned int v13; // esi
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  char *v18; // rcx
  __int64 v19; // rbx
  WinREAgent::TelemetrySession *v20; // rax
  struct WinREAgent::TelemetrySession *v21; // rax
  bool CanExecute; // al
  WinREAgent::TelemetrySession *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rbx
  _BYTE v26[512]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+240h] [rbp+140h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::CanService");
  PushButtonReset::Logging::Trace(0, L"Checking servicing of WinRE image using packages");
  v8 = (char *)this + 24;
  v27 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v27) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))(v8);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)"WinREAgent::WinREServicingManager::CanService");
    WinREAgent::TelemetrySession::TraceEnterAPI(v9, &v27);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  }
  if ( *((_BYTE *)this + 64) )
  {
    WinREAgent::Executor::Executor((WinREAgent::Executor *)v26);
    for ( i = 0; i < a3; ++i )
    {
      v13 = WinREAgent::Executor::AddPackage(
              (WinREAgent::Executor *)v26,
              a2[3 * i],
              (__int64)a2[3 * i + 1],
              (__int64)a2[3 * i + 2]);
      if ( (v13 & 0x80000000) != 0 )
      {
        v27 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v27) )
        {
          v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v27,
            (__int64)"WinREAgent::WinREServicingManager::CanService");
          WinREAgent::TelemetrySession::TraceLeaveAPI(v14, &v27, v13);
          ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
        }
        PushButtonReset::Logging::TraceErr(
          2,
          v13,
          "WinREAgent::WinREServicingManager::CanService",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          328,
          L"Failed to add package");
        goto LABEL_30;
      }
    }
    v13 = WinREAgent::Executor::FillPackageInfo((WinREAgent::Executor *)v26);
    v17 = *(_QWORD *)v8;
    v18 = (char *)this + 24;
    if ( (v13 & 0x80000000) == 0 )
    {
      v20 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(v17 + 32))(v18);
      v13 = WinREAgent::Executor::ScheduleExecution((__int64)v26, (_QWORD *)this + 7, v20);
      if ( (v13 & 0x80000000) != 0 )
      {
        if ( v13 != -2147467263 )
        {
          v27 = 0;
          if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v27) )
          {
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v27,
              (__int64)"WinREAgent::WinREServicingManager::CanService");
            WinREAgent::TelemetrySession::TraceLeaveAPI(v25, &v27, v13);
            ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
          }
          PushButtonReset::Logging::TraceErr(
            2,
            v13,
            "WinREAgent::WinREServicingManager::CanService",
            "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
            353,
            L"Failed to schedule execution");
          goto LABEL_30;
        }
        PushButtonReset::Logging::TraceErr(
          1,
          2147500033LL,
          "WinREAgent::WinREServicingManager::CanService",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          346,
          L"Execution scenario is not implemented; servicing not possible");
        v13 = 0;
        CanExecute = 0;
      }
      else
      {
        v21 = (struct WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 32LL))((char *)this + 24);
        CanExecute = WinREAgent::Executor::CanExecute((WinREAgent::Executor *)v26, v21);
      }
      *a4 = CanExecute;
      v27 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v27) )
      {
        v23 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
        WinREAgent::TelemetrySession::TraceDataPoint(v23, L"ServicingInfoGroup", L"CanService", *a4);
      }
      v27 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v27) )
      {
        v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v27,
          (__int64)"WinREAgent::WinREServicingManager::CanService");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v24, &v27, v13);
        ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      }
      PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::CanService");
    }
    else
    {
      v27 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(v17 + 64))(v18, &v27) )
      {
        v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v27,
          (__int64)"WinREAgent::WinREServicingManager::CanService");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v19, &v27, v13);
        ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      }
      PushButtonReset::Logging::TraceErr(
        2,
        v13,
        "WinREAgent::WinREServicingManager::CanService",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        336,
        L"Failed to fill package info");
    }
LABEL_30:
    WinREAgent::Executor::~Executor((WinREAgent::Executor *)v26, v15, v16);
    return v13;
  }
  v27 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v27) )
  {
    v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))(v8);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)"WinREAgent::WinREServicingManager::CanService");
    WinREAgent::TelemetrySession::TraceLeaveAPI(v10, &v27, 2147942421LL);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  }
  PushButtonReset::Logging::TraceErr(
    2,
    2147942421LL,
    "WinREAgent::WinREServicingManager::CanService",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    312,
    L"Must initialize WinREServicingManager first");
  return 2147942421LL;
}

```

## disassembly

```asm
0x180017f20  push    rbp
0x180017f22  push    rbx
0x180017f23  push    rsi
0x180017f24  push    rdi
0x180017f25  push    r12
0x180017f27  push    r13
0x180017f29  push    r14
0x180017f2b  push    r15
0x180017f2d  lea     rbp, [rsp-0F8h]
0x180017f35  sub     rsp, 1F8h
0x180017f3c  mov     r13, r9
0x180017f3f  mov     r12d, r8d
0x180017f42  mov     r15, rdx
0x180017f45  mov     r14, rcx
0x180017f48  lea     rdx, aEnterWinreagen_4; "Enter WinREAgent::WinREServicingManager"...
0x180017f4f  xor     ecx, ecx
0x180017f51  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180017f56  lea     rdx, aCheckingServic; "Checking servicing of WinRE image using"...
0x180017f5d  xor     ecx, ecx
0x180017f5f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180017f64  lea     rdi, [r14+18h]
0x180017f68  xor     esi, esi
0x180017f6a  mov     [rbp+130h+arg_0], rsi
0x180017f71  mov     rax, [rdi]
0x180017f74  lea     rdx, [rbp+130h+arg_0]
0x180017f7b  mov     rcx, rdi
0x180017f7e  mov     rax, [rax+40h]
0x180017f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f87  test    al, al
0x180017f89  jz      short loc_180017FD1
0x180017f8b  mov     rax, [rdi]
0x180017f8e  mov     rcx, rdi
0x180017f91  mov     rax, [rax+18h]
0x180017f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f9a  mov     rbx, rax
0x180017f9d  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x180017fa4  lea     rcx, [rbp+130h+arg_0]
0x180017fab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180017fb0  nop
0x180017fb1  lea     rdx, [rbp+130h+arg_0]
0x180017fb8  mov     rcx, rbx
0x180017fbb  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180017fc0  nop
0x180017fc1  mov     rcx, [rbp+130h+arg_0]
0x180017fc8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017fcc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180017fd1  cmp     [r14+40h], sil
0x180017fd5  jnz     loc_180018084
0x180017fdb  mov     [rbp+130h+arg_0], rsi
0x180017fe2  mov     rax, [rdi]
0x180017fe5  lea     rdx, [rbp+130h+arg_0]
0x180017fec  mov     rcx, rdi
0x180017fef  mov     rax, [rax+40h]
0x180017ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff8  mov     r14d, 80070015h
0x180017ffe  test    al, al
0x180018000  jz      short loc_18001804B
0x180018002  mov     rax, [rdi]
0x180018005  mov     rcx, rdi
0x180018008  mov     rax, [rax+18h]
0x18001800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018011  mov     rbx, rax
0x180018014  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x18001801b  lea     rcx, [rbp+130h+arg_0]
0x180018022  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180018027  nop
0x180018028  mov     r8d, r14d
0x18001802b  lea     rdx, [rbp+130h+arg_0]
0x180018032  mov     rcx, rbx
0x180018035  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001803a  nop
0x18001803b  mov     rcx, [rbp+130h+arg_0]
0x180018042  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018046  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001804b  lea     rcx, aMustInitialize; "Must initialize WinREServicingManager f"...
0x180018052  mov     [rsp+230h+var_208], rcx
0x180018057  mov     [rsp+230h+var_210], 138h
0x18001805f  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180018066  lea     r8, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x18001806d  mov     edx, 80070015h
0x180018072  mov     ecx, 2
0x180018077  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001807c  mov     eax, r14d
0x18001807f  jmp     loc_1800183C9
0x180018084  lea     rcx, [rsp+230h+var_200]; this
0x180018089  call    ??0Executor@WinREAgent@@QEAA@XZ; WinREAgent::Executor::Executor(void)
0x18001808e  nop
0x18001808f  mov     ebx, esi
0x180018091  lea     rcx, [rsp+230h+var_200]; this
0x180018096  cmp     ebx, r12d
0x180018099  jnb     loc_180018149
0x18001809f  mov     eax, ebx
0x1800180a1  lea     rdx, [rax+rax*2]
0x1800180a5  mov     r9, [r15+rdx*8+10h]; unsigned __int64
0x1800180aa  mov     r8, [r15+rdx*8+8]; unsigned __int64
0x1800180af  mov     rdx, [r15+rdx*8]; unsigned __int16 *
0x1800180b3  call    ?AddPackage@Executor@WinREAgent@@QEAAJPEBG_K1@Z; WinREAgent::Executor::AddPackage(ushort const *,unsigned __int64,unsigned __int64)
0x1800180b8  mov     esi, eax
0x1800180ba  test    eax, eax
0x1800180bc  js      short loc_1800180C2
0x1800180be  inc     ebx
0x1800180c0  jmp     short loc_180018091
0x1800180c2  mov     [rbp+130h+arg_0], 0
0x1800180cd  mov     rax, [rdi]
0x1800180d0  lea     rdx, [rbp+130h+arg_0]
0x1800180d7  mov     rcx, rdi
0x1800180da  mov     rax, [rax+40h]
0x1800180de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180e3  test    al, al
0x1800180e5  jz      short loc_180018130
0x1800180e7  mov     rax, [rdi]
0x1800180ea  mov     rcx, rdi
0x1800180ed  mov     rax, [rax+18h]
0x1800180f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180f6  mov     rbx, rax
0x1800180f9  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x180018100  lea     rcx, [rbp+130h+arg_0]
0x180018107  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001810c  nop
0x18001810d  mov     r8d, esi
0x180018110  lea     rdx, [rbp+130h+arg_0]
0x180018117  mov     rcx, rbx
0x18001811a  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001811f  nop
0x180018120  mov     rcx, [rbp+130h+arg_0]
0x180018127  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001812b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018130  lea     rax, aFailedToAddPac_0; "Failed to add package"
0x180018137  mov     [rsp+230h+var_208], rax
0x18001813c  mov     [rsp+230h+var_210], 148h
0x180018144  jmp     loc_1800183A2
0x180018149  call    ?FillPackageInfo@Executor@WinREAgent@@QEAAJXZ; WinREAgent::Executor::FillPackageInfo(void)
0x18001814e  mov     esi, eax
0x180018150  mov     rax, [rdi]
0x180018153  xor     ebx, ebx
0x180018155  mov     rcx, rdi
0x180018158  test    esi, esi
0x18001815a  jns     short loc_1800181D9
0x18001815c  mov     [rbp+130h+arg_0], rbx
0x180018163  lea     rdx, [rbp+130h+arg_0]
0x18001816a  mov     rax, [rax+40h]
0x18001816e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018173  test    al, al
0x180018175  jz      short loc_1800181C0
0x180018177  mov     rax, [rdi]
0x18001817a  mov     rcx, rdi
0x18001817d  mov     rax, [rax+18h]
0x180018181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018186  mov     rbx, rax
0x180018189  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x180018190  lea     rcx, [rbp+130h+arg_0]
0x180018197  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001819c  nop
0x18001819d  mov     r8d, esi
0x1800181a0  lea     rdx, [rbp+130h+arg_0]
0x1800181a7  mov     rcx, rbx
0x1800181aa  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x1800181af  nop
0x1800181b0  mov     rcx, [rbp+130h+arg_0]
0x1800181b7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800181bb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800181c0  lea     rax, aFailedToFillPa; "Failed to fill package info"
0x1800181c7  mov     [rsp+230h+var_208], rax
0x1800181cc  mov     [rsp+230h+var_210], 150h
0x1800181d4  jmp     loc_1800183A2
0x1800181d9  mov     rax, [rax+20h]
0x1800181dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181e2  mov     r8, rax
0x1800181e5  lea     rdx, [r14+38h]
0x1800181e9  lea     rcx, [rsp+230h+var_200]
0x1800181ee  call    ?ScheduleExecution@Executor@WinREAgent@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVTelemetrySession@2@@Z; WinREAgent::Executor::ScheduleExecution(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,WinREAgent::TelemetrySession *)
0x1800181f3  mov     esi, eax
0x1800181f5  test    eax, eax
0x1800181f7  js      short loc_180018217
0x1800181f9  mov     rcx, [rdi]
0x1800181fc  mov     rax, [rcx+20h]
0x180018200  mov     rcx, rdi
0x180018203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018208  mov     rdx, rax; struct WinREAgent::TelemetrySession *
0x18001820b  lea     rcx, [rsp+230h+var_200]; this
0x180018210  call    ?CanExecute@Executor@WinREAgent@@QEBA_NPEAVTelemetrySession@2@@Z; WinREAgent::Executor::CanExecute(WinREAgent::TelemetrySession *)
0x180018215  jmp     short loc_180018258
0x180018217  cmp     esi, 80004001h
0x18001821d  jnz     loc_180018324
0x180018223  lea     rax, aExecutionScena; "Execution scenario is not implemented; "...
0x18001822a  mov     [rsp+230h+var_208], rax
0x18001822f  mov     [rsp+230h+var_210], 15Ah
0x180018237  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001823e  lea     r8, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x180018245  mov     edx, 80004001h
0x18001824a  mov     ecx, 1
0x18001824f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018254  mov     esi, ebx
0x180018256  mov     al, bl
0x180018258  mov     [r13+0], al
0x18001825c  mov     [rbp+130h+arg_0], rbx
0x180018263  mov     rax, [rdi]
0x180018266  lea     rdx, [rbp+130h+arg_0]
0x18001826d  mov     rcx, rdi
0x180018270  mov     rax, [rax+40h]
0x180018274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018279  test    al, al
0x18001827b  jz      short loc_1800182A7
0x18001827d  mov     rax, [rdi]
0x180018280  mov     rcx, rdi
0x180018283  mov     rax, [rax+18h]
0x180018287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001828c  movzx   r9d, byte ptr [r13+0]; unsigned int
0x180018291  lea     r8, aCanservice; "CanService"
0x180018298  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18001829f  mov     rcx, rax; this
0x1800182a2  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x1800182a7  mov     [rbp+130h+arg_0], rbx
0x1800182ae  mov     rax, [rdi]
0x1800182b1  lea     rdx, [rbp+130h+arg_0]
0x1800182b8  mov     rcx, rdi
0x1800182bb  mov     rax, [rax+40h]
0x1800182bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c4  test    al, al
0x1800182c6  jz      short loc_180018311
0x1800182c8  mov     rax, [rdi]
0x1800182cb  mov     rcx, rdi
0x1800182ce  mov     rax, [rax+18h]
0x1800182d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182d7  mov     rbx, rax
0x1800182da  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x1800182e1  lea     rcx, [rbp+130h+arg_0]
0x1800182e8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800182ed  nop
0x1800182ee  mov     r8d, esi
0x1800182f1  lea     rdx, [rbp+130h+arg_0]
0x1800182f8  mov     rcx, rbx
0x1800182fb  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180018300  nop
0x180018301  mov     rcx, [rbp+130h+arg_0]
0x180018308  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001830c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018311  lea     rdx, aExitWinreagent_2; "Exit WinREAgent::WinREServicingManager:"...
0x180018318  xor     ecx, ecx
0x18001831a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001831f  jmp     loc_1800183BD
0x180018324  mov     [rbp+130h+arg_0], rbx
0x18001832b  mov     rax, [rdi]
0x18001832e  lea     rdx, [rbp+130h+arg_0]
0x180018335  mov     rcx, rdi
0x180018338  mov     rax, [rax+40h]
0x18001833c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018341  test    al, al
0x180018343  jz      short loc_18001838E
0x180018345  mov     rax, [rdi]
0x180018348  mov     rcx, rdi
0x18001834b  mov     rax, [rax+18h]
0x18001834f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018354  mov     rbx, rax
0x180018357  lea     rdx, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x18001835e  lea     rcx, [rbp+130h+arg_0]
0x180018365  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001836a  nop
0x18001836b  mov     r8d, esi
0x18001836e  lea     rdx, [rbp+130h+arg_0]
0x180018375  mov     rcx, rbx
0x180018378  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001837d  nop
0x18001837e  mov     rcx, [rbp+130h+arg_0]
0x180018385  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018389  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001838e  lea     rax, aFailedToSchedu; "Failed to schedule execution"
0x180018395  mov     [rsp+230h+var_208], rax
0x18001839a  mov     [rsp+230h+var_210], 161h
0x1800183a2  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800183a9  lea     r8, aWinreagentWinr_16; "WinREAgent::WinREServicingManager::CanS"...
0x1800183b0  mov     edx, esi
0x1800183b2  mov     ecx, 2
0x1800183b7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800183bc  nop
0x1800183bd  lea     rcx, [rsp+230h+var_200]; this
0x1800183c2  call    ??1Executor@WinREAgent@@QEAA@XZ; WinREAgent::Executor::~Executor(void)
0x1800183c7  mov     eax, esi
0x1800183c9  add     rsp, 1F8h
0x1800183d0  pop     r15
0x1800183d2  pop     r14
0x1800183d4  pop     r13
0x1800183d6  pop     r12
0x1800183d8  pop     rdi
0x1800183d9  pop     rsi
0x1800183da  pop     rbx
0x1800183db  pop     rbp
0x1800183dc  retn
```
