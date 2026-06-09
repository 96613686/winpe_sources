# WinREAgent::WinREServicingManager::ServiceCreatedWinRE(void *,WinREAgent::IWinREServicingProgress *)

- ea: `0x18001d3c0`
- end: `0x18001d6b7`
- name: `?ServiceCreatedWinRE@WinREServicingManager@WinREAgent@@UEAAJPEAXPEAUIWinREServicingProgress@2@@Z`
- size: `759`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, void *, struct WinREAgent::IWinREServicingProgress *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d92c`
- `0x1800158bc`
- `0x18001d3c0`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18001d4eb`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001d630`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001d61c`: `Failed to commit WinRE servicing`
- `0x18001d3e2`: `Enter WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d3f0`: `Schedule WinRE servicing with created WinRE and execute`
- `0x18001d433`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d4a9`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d4f2`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d55b`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d5ee`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d637`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d662`: `WinREAgent::WinREServicingManager::ServiceCreatedWinRE`
- `0x18001d690`: `Exit WinREAgent::WinREServicingManager::ServiceCreatedWinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::WinREServicingManager::ServiceCreatedWinRE(
        WinREAgent::WinREServicingManager *this,
        void *a2,
        struct WinREAgent::IWinREServicingProgress *a3)
{
  char *v6; // rdi
  __int64 v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rbx
  __int64 v11; // rbx
  unsigned int v12; // esi
  __int64 (__fastcall *v13)(char *, __int64 *); // rax
  char v14; // al
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
  PushButtonReset::Logging::Trace(0, L"Schedule WinRE servicing with created WinRE and execute");
  v6 = (char *)this + 24;
  v17 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v17) )
  {
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))((char *)this + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v17,
      (__int64)"WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
    WinREAgent::TelemetrySession::TraceEnterAPI(v7, &v17);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  }
  v8 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *))(*(_QWORD *)this + 96LL))(this);
  if ( (v8 & 0x80000000) != 0 )
  {
    v17 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v6 + 64LL))((char *)this + 24, &v17) )
    {
      v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v17,
        (__int64)"WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v9, &v17, v8);
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v8,
      "WinREAgent::WinREServicingManager::ServiceCreatedWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      565,
      L"Failed to schedule WinRE servicing");
    return v8;
  }
  v8 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 104LL))(
         this,
         a2,
         a3);
  if ( (v8 & 0x80000000) != 0 )
  {
    v17 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v6 + 64LL))((char *)this + 24, &v17) )
    {
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v17,
        (__int64)"WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v11, &v17, v8);
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v8,
      "WinREAgent::WinREServicingManager::ServiceCreatedWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      572,
      L"Failed to stage WinRE servicing");
    return v8;
  }
  v12 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 112LL))(
          this,
          a2,
          a3);
  v13 = *(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v6 + 64LL);
  v17 = 0;
  v14 = v13(v6, &v17);
  if ( (v12 & 0x80000000) == 0 )
  {
    if ( v14 )
    {
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))(v6);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v17,
        (__int64)"WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v16, &v17, v12);
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    }
    PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
  }
  else
  {
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))(v6);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v17,
        (__int64)"WinREAgent::WinREServicingManager::ServiceCreatedWinRE");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v15, &v17, v12);
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v12,
      "WinREAgent::WinREServicingManager::ServiceCreatedWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      579,
      L"Failed to commit WinRE servicing");
  }
  return v12;
}

```

## disassembly

```asm
0x18001d3c0  mov     [rsp-28h+arg_8], rbx
0x18001d3c5  mov     [rsp-28h+arg_10], rsi
0x18001d3ca  push    rbp
0x18001d3cb  push    rdi
0x18001d3cc  push    r12
0x18001d3ce  push    r14
0x18001d3d0  push    r15
0x18001d3d2  mov     rbp, rsp
0x18001d3d5  sub     rsp, 30h
0x18001d3d9  mov     r15, r8
0x18001d3dc  mov     r12, rdx
0x18001d3df  mov     rsi, rcx
0x18001d3e2  lea     rdx, aEnterWinreagen_14; "Enter WinREAgent::WinREServicingManager"...
0x18001d3e9  xor     ecx, ecx
0x18001d3eb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d3f0  lea     rdx, aScheduleWinreS; "Schedule WinRE servicing with created W"...
0x18001d3f7  xor     ecx, ecx
0x18001d3f9  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d3fe  lea     rdi, [rsi+18h]
0x18001d402  mov     [rbp+arg_0], 0
0x18001d40a  mov     rax, [rdi]
0x18001d40d  lea     rdx, [rbp+arg_0]
0x18001d411  mov     rcx, rdi
0x18001d414  mov     rax, [rax+40h]
0x18001d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d41d  test    al, al
0x18001d41f  jz      short loc_18001D45E
0x18001d421  mov     rax, [rdi]
0x18001d424  mov     rcx, rdi
0x18001d427  mov     rax, [rax+18h]
0x18001d42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d430  mov     rbx, rax
0x18001d433  lea     rdx, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d43a  lea     rcx, [rbp+arg_0]
0x18001d43e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d443  nop
0x18001d444  lea     rdx, [rbp+arg_0]
0x18001d448  mov     rcx, rbx
0x18001d44b  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001d450  nop
0x18001d451  mov     rcx, [rbp+arg_0]
0x18001d455  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d459  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d45e  mov     rax, [rsi]
0x18001d461  mov     rcx, rsi
0x18001d464  mov     rax, [rax+60h]
0x18001d468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46d  mov     r14d, eax
0x18001d470  test    eax, eax
0x18001d472  jns     loc_18001D50E
0x18001d478  mov     [rbp+arg_0], 0
0x18001d480  mov     rdx, [rdi]
0x18001d483  mov     rax, [rdx+40h]
0x18001d487  lea     rdx, [rbp+arg_0]
0x18001d48b  mov     rcx, rdi
0x18001d48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d493  test    al, al
0x18001d495  jz      short loc_18001D4D7
0x18001d497  mov     rax, [rdi]
0x18001d49a  mov     rcx, rdi
0x18001d49d  mov     rax, [rax+18h]
0x18001d4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a6  mov     rbx, rax
0x18001d4a9  lea     rdx, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d4b0  lea     rcx, [rbp+arg_0]
0x18001d4b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d4b9  nop
0x18001d4ba  mov     r8d, r14d
0x18001d4bd  lea     rdx, [rbp+arg_0]
0x18001d4c1  mov     rcx, rbx
0x18001d4c4  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d4c9  nop
0x18001d4ca  mov     rcx, [rbp+arg_0]
0x18001d4ce  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d4d2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d4d7  lea     rax, aFailedToSchedu_0; "Failed to schedule WinRE servicing"
0x18001d4de  mov     [rsp+30h+var_8], rax
0x18001d4e3  mov     [rsp+30h+var_10], 235h
0x18001d4eb  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001d4f2  lea     r8, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d4f9  mov     edx, r14d
0x18001d4fc  mov     ecx, 2
0x18001d501  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001d506  mov     eax, r14d
0x18001d509  jmp     loc_18001D6A0
0x18001d50e  mov     rax, [rsi]
0x18001d511  mov     r8, r15
0x18001d514  mov     rdx, r12
0x18001d517  mov     rcx, rsi
0x18001d51a  mov     rax, [rax+68h]
0x18001d51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d523  mov     r14d, eax
0x18001d526  test    eax, eax
0x18001d528  jns     short loc_18001D5A2
0x18001d52a  mov     [rbp+arg_0], 0
0x18001d532  mov     rcx, [rdi]
0x18001d535  mov     rax, [rcx+40h]
0x18001d539  lea     rdx, [rbp+arg_0]
0x18001d53d  mov     rcx, rdi
0x18001d540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d545  test    al, al
0x18001d547  jz      short loc_18001D589
0x18001d549  mov     rax, [rdi]
0x18001d54c  mov     rcx, rdi
0x18001d54f  mov     rax, [rax+18h]
0x18001d553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d558  mov     rbx, rax
0x18001d55b  lea     rdx, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d562  lea     rcx, [rbp+arg_0]
0x18001d566  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d56b  nop
0x18001d56c  mov     r8d, r14d
0x18001d56f  lea     rdx, [rbp+arg_0]
0x18001d573  mov     rcx, rbx
0x18001d576  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d57b  nop
0x18001d57c  mov     rcx, [rbp+arg_0]
0x18001d580  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d584  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d589  lea     rax, aFailedToStageW; "Failed to stage WinRE servicing"
0x18001d590  mov     [rsp+30h+var_8], rax
0x18001d595  mov     [rsp+30h+var_10], 23Ch
0x18001d59d  jmp     loc_18001D4EB
0x18001d5a2  mov     rax, [rsi]
0x18001d5a5  mov     r8, r15
0x18001d5a8  mov     rdx, r12
0x18001d5ab  mov     rcx, rsi
0x18001d5ae  mov     rax, [rax+70h]
0x18001d5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5b7  mov     esi, eax
0x18001d5b9  mov     rcx, [rdi]
0x18001d5bc  mov     rax, [rcx+40h]
0x18001d5c0  mov     [rbp+arg_0], 0
0x18001d5c8  lea     rdx, [rbp+arg_0]
0x18001d5cc  mov     rcx, rdi
0x18001d5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d4  test    esi, esi
0x18001d5d6  jns     short loc_18001D64C
0x18001d5d8  test    al, al
0x18001d5da  jz      short loc_18001D61C
0x18001d5dc  mov     rax, [rdi]
0x18001d5df  mov     rcx, rdi
0x18001d5e2  mov     rax, [rax+18h]
0x18001d5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5eb  mov     rbx, rax
0x18001d5ee  lea     rdx, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d5f5  lea     rcx, [rbp+arg_0]
0x18001d5f9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d5fe  nop
0x18001d5ff  mov     r8d, esi
0x18001d602  lea     rdx, [rbp+arg_0]
0x18001d606  mov     rcx, rbx
0x18001d609  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d60e  nop
0x18001d60f  mov     rcx, [rbp+arg_0]
0x18001d613  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d617  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d61c  lea     rax, aFailedToCommit_1; "Failed to commit WinRE servicing"
0x18001d623  mov     [rsp+30h+var_8], rax
0x18001d628  mov     [rsp+30h+var_10], 243h
0x18001d630  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001d637  lea     r8, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d63e  mov     edx, esi
0x18001d640  mov     ecx, 2
0x18001d645  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001d64a  jmp     short loc_18001D69E
0x18001d64c  test    al, al
0x18001d64e  jz      short loc_18001D690
0x18001d650  mov     rax, [rdi]
0x18001d653  mov     rcx, rdi
0x18001d656  mov     rax, [rax+18h]
0x18001d65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d65f  mov     rbx, rax
0x18001d662  lea     rdx, aWinreagentWinr_7; "WinREAgent::WinREServicingManager::Serv"...
0x18001d669  lea     rcx, [rbp+arg_0]
0x18001d66d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d672  nop
0x18001d673  mov     r8d, esi
0x18001d676  lea     rdx, [rbp+arg_0]
0x18001d67a  mov     rcx, rbx
0x18001d67d  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d682  nop
0x18001d683  mov     rcx, [rbp+arg_0]
0x18001d687  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d68b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d690  lea     rdx, aExitWinreagent_10; "Exit WinREAgent::WinREServicingManager:"...
0x18001d697  xor     ecx, ecx
0x18001d699  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d69e  mov     eax, esi
0x18001d6a0  mov     rbx, [rsp+30h+arg_8]
0x18001d6a5  mov     rsi, [rsp+30h+arg_10]
0x18001d6aa  add     rsp, 30h
0x18001d6ae  pop     r15
0x18001d6b0  pop     r14
0x18001d6b2  pop     r12
0x18001d6b4  pop     rdi
0x18001d6b5  pop     rbp
0x18001d6b6  retn
```
