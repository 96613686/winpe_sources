# WinREAgent::WinREServicingManager::Service(WinREAgent::WINREAGENT_PACKAGE_INFO * const,uint,ushort const * * const,uint,void *,WinREAgent::IWinREServicingProgress *)

- ea: `0x18001d0c0`
- end: `0x18001d3b1`
- name: `?Service@WinREServicingManager@WinREAgent@@UEAAJQEAUWINREAGENT_PACKAGE_INFO@2@IQEAPEBGIPEAXPEAUIWinREServicingProgress@2@@Z`
- size: `753`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, struct WinREAgent::WINREAGENT_PACKAGE_INFO *const, unsigned int, const unsigned __int16 **const, unsigned int, void *, struct WinREAgent::IWinREServicingProgress *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d92c`
- `0x1800158bc`
- `0x18001d0c0`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18001d1fd`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001d0e5`: `Enter WinREAgent::WinREServicingManager::Service`
- `0x18001d136`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d1bb`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d204`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d26a`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d2ff`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d35c`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d32d`: `Failed to commit WinRE servicing`
- `0x18001d38a`: `Exit WinREAgent::WinREServicingManager::Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::WinREServicingManager::Service(
        WinREAgent::WinREServicingManager *this,
        struct WinREAgent::WINREAGENT_PACKAGE_INFO *const a2,
        unsigned int a3,
        const unsigned __int16 **const a4,
        unsigned int a5,
        void *a6,
        struct WinREAgent::IWinREServicingProgress *a7)
{
  char *v11; // rdi
  __int64 v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(char *, __int64 *); // rax
  char v17; // al
  __int64 v18; // rbx
  __int64 v19; // rbx
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::Service");
  PushButtonReset::Logging::Trace(0, L"Schedule WinRE servicing and execute");
  v11 = (char *)this + 24;
  v21 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v21) )
  {
    v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 24LL))((char *)this + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v21,
      (__int64)"WinREAgent::WinREServicingManager::Service");
    WinREAgent::TelemetrySession::TraceEnterAPI(v12, &v21);
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
  }
  v13 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, struct WinREAgent::WINREAGENT_PACKAGE_INFO *const, _QWORD, const unsigned __int16 **const, unsigned int))(*(_QWORD *)this + 80LL))(
          this,
          a2,
          a3,
          a4,
          a5);
  if ( (v13 & 0x80000000) == 0 )
  {
    v13 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 104LL))(
            this,
            a6,
            a7);
    if ( (v13 & 0x80000000) == 0 )
    {
      v13 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 112LL))(
              this,
              a6,
              a7);
      v16 = *(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v11 + 64LL);
      v21 = 0;
      v17 = v16((char *)this + 24, &v21);
      if ( (v13 & 0x80000000) == 0 )
      {
        if ( v17 )
        {
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 24LL))((char *)this + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v21,
            (__int64)"WinREAgent::WinREServicingManager::Service");
          WinREAgent::TelemetrySession::TraceLeaveAPI(v19, &v21, v13);
          ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
        }
        PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::Service");
      }
      else
      {
        if ( v17 )
        {
          v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 24LL))((char *)this + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v21,
            (__int64)"WinREAgent::WinREServicingManager::Service");
          WinREAgent::TelemetrySession::TraceLeaveAPI(v18, &v21, v13);
          ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
        }
        PushButtonReset::Logging::TraceErr(
          2,
          v13,
          "WinREAgent::WinREServicingManager::Service",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          543,
          L"Failed to commit WinRE servicing");
      }
    }
    else
    {
      v21 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v11 + 64LL))((char *)this + 24, &v21) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 24LL))((char *)this + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v21,
          (__int64)"WinREAgent::WinREServicingManager::Service");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v15, &v21, v13);
        ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      }
      PushButtonReset::Logging::TraceErr(
        2,
        v13,
        "WinREAgent::WinREServicingManager::Service",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        536,
        L"Failed to stage WinRE servicing");
    }
  }
  else
  {
    v21 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v11 + 64LL))((char *)this + 24, &v21) )
    {
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v21,
        (__int64)"WinREAgent::WinREServicingManager::Service");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v14, &v21, v13);
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v13,
      "WinREAgent::WinREServicingManager::Service",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      529,
      L"Failed to schedule WinRE servicing");
  }
  return v13;
}

```

## disassembly

```asm
0x18001d0c0  mov     [rsp-28h+arg_8], rbx
0x18001d0c5  mov     [rsp-28h+arg_10], rsi
0x18001d0ca  push    rbp
0x18001d0cb  push    rdi
0x18001d0cc  push    r12
0x18001d0ce  push    r14
0x18001d0d0  push    r15
0x18001d0d2  mov     rbp, rsp
0x18001d0d5  sub     rsp, 30h
0x18001d0d9  mov     rsi, r9
0x18001d0dc  mov     r15d, r8d
0x18001d0df  mov     r12, rdx
0x18001d0e2  mov     r14, rcx
0x18001d0e5  lea     rdx, aEnterWinreagen_3; "Enter WinREAgent::WinREServicingManager"...
0x18001d0ec  xor     ecx, ecx
0x18001d0ee  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d0f3  lea     rdx, aScheduleWinreS_0; "Schedule WinRE servicing and execute"
0x18001d0fa  xor     ecx, ecx
0x18001d0fc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d101  lea     rdi, [r14+18h]
0x18001d105  mov     [rbp+arg_0], 0
0x18001d10d  mov     rax, [rdi]
0x18001d110  lea     rdx, [rbp+arg_0]
0x18001d114  mov     rcx, rdi
0x18001d117  mov     rax, [rax+40h]
0x18001d11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d120  test    al, al
0x18001d122  jz      short loc_18001D161
0x18001d124  mov     rax, [rdi]
0x18001d127  mov     rcx, rdi
0x18001d12a  mov     rax, [rax+18h]
0x18001d12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d133  mov     rbx, rax
0x18001d136  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d13d  lea     rcx, [rbp+arg_0]
0x18001d141  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d146  nop
0x18001d147  lea     rdx, [rbp+arg_0]
0x18001d14b  mov     rcx, rbx
0x18001d14e  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001d153  nop
0x18001d154  mov     rcx, [rbp+arg_0]
0x18001d158  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d15c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d161  mov     rax, [r14]
0x18001d164  mov     ecx, [rbp+arg_20]
0x18001d167  mov     [rsp+30h+var_10], ecx
0x18001d16b  mov     r9, rsi
0x18001d16e  mov     r8d, r15d
0x18001d171  mov     rdx, r12
0x18001d174  mov     rcx, r14
0x18001d177  mov     rax, [rax+50h]
0x18001d17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d180  mov     esi, eax
0x18001d182  test    eax, eax
0x18001d184  jns     loc_18001D21C
0x18001d18a  mov     [rbp+arg_0], 0
0x18001d192  mov     rdx, [rdi]
0x18001d195  mov     rax, [rdx+40h]
0x18001d199  lea     rdx, [rbp+arg_0]
0x18001d19d  mov     rcx, rdi
0x18001d1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a5  test    al, al
0x18001d1a7  jz      short loc_18001D1E9
0x18001d1a9  mov     rax, [rdi]
0x18001d1ac  mov     rcx, rdi
0x18001d1af  mov     rax, [rax+18h]
0x18001d1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b8  mov     rbx, rax
0x18001d1bb  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d1c2  lea     rcx, [rbp+arg_0]
0x18001d1c6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d1cb  nop
0x18001d1cc  mov     r8d, esi
0x18001d1cf  lea     rdx, [rbp+arg_0]
0x18001d1d3  mov     rcx, rbx
0x18001d1d6  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d1db  nop
0x18001d1dc  mov     rcx, [rbp+arg_0]
0x18001d1e0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d1e4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d1e9  lea     rax, aFailedToSchedu_0; "Failed to schedule WinRE servicing"
0x18001d1f0  mov     [rsp+30h+var_8], rax
0x18001d1f5  mov     [rsp+30h+var_10], 211h
0x18001d1fd  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001d204  lea     r8, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d20b  mov     edx, esi
0x18001d20d  mov     ecx, 2
0x18001d212  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001d217  jmp     loc_18001D398
0x18001d21c  mov     rax, [r14]
0x18001d21f  mov     r8, [rbp+arg_30]
0x18001d223  mov     rdx, [rbp+arg_28]
0x18001d227  mov     rcx, r14
0x18001d22a  mov     rax, [rax+68h]
0x18001d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d233  mov     esi, eax
0x18001d235  test    eax, eax
0x18001d237  jns     short loc_18001D2B1
0x18001d239  mov     [rbp+arg_0], 0
0x18001d241  mov     rcx, [rdi]
0x18001d244  mov     rax, [rcx+40h]
0x18001d248  lea     rdx, [rbp+arg_0]
0x18001d24c  mov     rcx, rdi
0x18001d24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d254  test    al, al
0x18001d256  jz      short loc_18001D298
0x18001d258  mov     rax, [rdi]
0x18001d25b  mov     rcx, rdi
0x18001d25e  mov     rax, [rax+18h]
0x18001d262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d267  mov     rbx, rax
0x18001d26a  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d271  lea     rcx, [rbp+arg_0]
0x18001d275  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d27a  nop
0x18001d27b  mov     r8d, esi
0x18001d27e  lea     rdx, [rbp+arg_0]
0x18001d282  mov     rcx, rbx
0x18001d285  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d28a  nop
0x18001d28b  mov     rcx, [rbp+arg_0]
0x18001d28f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d293  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d298  lea     rax, aFailedToStageW; "Failed to stage WinRE servicing"
0x18001d29f  mov     [rsp+30h+var_8], rax
0x18001d2a4  mov     [rsp+30h+var_10], 218h
0x18001d2ac  jmp     loc_18001D1FD
0x18001d2b1  mov     rax, [r14]
0x18001d2b4  mov     r8, [rbp+arg_30]
0x18001d2b8  mov     rdx, [rbp+arg_28]
0x18001d2bc  mov     rcx, r14
0x18001d2bf  mov     rax, [rax+70h]
0x18001d2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2c8  mov     esi, eax
0x18001d2ca  mov     rcx, [rdi]
0x18001d2cd  mov     rax, [rcx+40h]
0x18001d2d1  mov     [rbp+arg_0], 0
0x18001d2d9  lea     rdx, [rbp+arg_0]
0x18001d2dd  mov     rcx, rdi
0x18001d2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2e5  test    esi, esi
0x18001d2e7  jns     short loc_18001D346
0x18001d2e9  test    al, al
0x18001d2eb  jz      short loc_18001D32D
0x18001d2ed  mov     rax, [rdi]
0x18001d2f0  mov     rcx, rdi
0x18001d2f3  mov     rax, [rax+18h]
0x18001d2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2fc  mov     rbx, rax
0x18001d2ff  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d306  lea     rcx, [rbp+arg_0]
0x18001d30a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d30f  nop
0x18001d310  mov     r8d, esi
0x18001d313  lea     rdx, [rbp+arg_0]
0x18001d317  mov     rcx, rbx
0x18001d31a  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d31f  nop
0x18001d320  mov     rcx, [rbp+arg_0]
0x18001d324  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d328  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d32d  lea     rax, aFailedToCommit_1; "Failed to commit WinRE servicing"
0x18001d334  mov     [rsp+30h+var_8], rax
0x18001d339  mov     [rsp+30h+var_10], 21Fh
0x18001d341  jmp     loc_18001D1FD
0x18001d346  test    al, al
0x18001d348  jz      short loc_18001D38A
0x18001d34a  mov     rax, [rdi]
0x18001d34d  mov     rcx, rdi
0x18001d350  mov     rax, [rax+18h]
0x18001d354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d359  mov     rbx, rax
0x18001d35c  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d363  lea     rcx, [rbp+arg_0]
0x18001d367  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d36c  nop
0x18001d36d  mov     r8d, esi
0x18001d370  lea     rdx, [rbp+arg_0]
0x18001d374  mov     rcx, rbx
0x18001d377  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d37c  nop
0x18001d37d  mov     rcx, [rbp+arg_0]
0x18001d381  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d385  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d38a  lea     rdx, aExitWinreagent_11; "Exit WinREAgent::WinREServicingManager:"...
0x18001d391  xor     ecx, ecx
0x18001d393  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d398  mov     eax, esi
0x18001d39a  mov     rbx, [rsp+30h+arg_8]
0x18001d39f  mov     rsi, [rsp+30h+arg_10]
0x18001d3a4  add     rsp, 30h
0x18001d3a8  pop     r15
0x18001d3aa  pop     r14
0x18001d3ac  pop     r12
0x18001d3ae  pop     rdi
0x18001d3af  pop     rbp
0x18001d3b0  retn
```
