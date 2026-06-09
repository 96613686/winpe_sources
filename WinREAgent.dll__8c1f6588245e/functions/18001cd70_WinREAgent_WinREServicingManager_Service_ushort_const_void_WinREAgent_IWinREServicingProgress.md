# WinREAgent::WinREServicingManager::Service(ushort const *,void *,WinREAgent::IWinREServicingProgress *)

- ea: `0x18001cd70`
- end: `0x18001d06d`
- name: `?Service@WinREServicingManager@WinREAgent@@UEAAJPEBGPEAXPEAUIWinREServicingProgress@2@@Z`
- size: `765`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, const unsigned __int16 *, void *, struct WinREAgent::IWinREServicingProgress *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d92c`
- `0x1800158bc`
- `0x18001cd70`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18001cea1`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001cfe6`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001cd95`: `Enter WinREAgent::WinREServicingManager::Service`
- `0x18001cde6`: `WinREAgent::WinREServicingManager::Service`
- `0x18001ce5f`: `WinREAgent::WinREServicingManager::Service`
- `0x18001cea8`: `WinREAgent::WinREServicingManager::Service`
- `0x18001cf11`: `WinREAgent::WinREServicingManager::Service`
- `0x18001cfa4`: `WinREAgent::WinREServicingManager::Service`
- `0x18001cfed`: `WinREAgent::WinREServicingManager::Service`
- `0x18001d018`: `WinREAgent::WinREServicingManager::Service`
- `0x18001cfd2`: `Failed to commit WinRE servicing`
- `0x18001d046`: `Exit WinREAgent::WinREServicingManager::Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::WinREServicingManager::Service(
        WinREAgent::WinREServicingManager *this,
        const unsigned __int16 *a2,
        void *a3,
        struct WinREAgent::IWinREServicingProgress *a4)
{
  char *v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // r14d
  __int64 v11; // rbx
  __int64 v13; // rbx
  unsigned int v14; // esi
  __int64 (__fastcall *v15)(char *, __int64 *); // rax
  char v16; // al
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // [rsp+60h] [rbp+30h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::Service");
  PushButtonReset::Logging::Trace(0, L"Schedule WinRE servicing and execute");
  v8 = (char *)this + 24;
  v19 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v19) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v19,
      (__int64)"WinREAgent::WinREServicingManager::Service");
    WinREAgent::TelemetrySession::TraceEnterAPI(v9, &v19);
    ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  }
  v10 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, const unsigned __int16 *))(*(_QWORD *)this + 72LL))(
          this,
          a2);
  if ( (v10 & 0x80000000) != 0 )
  {
    v19 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v19) )
    {
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v19,
        (__int64)"WinREAgent::WinREServicingManager::Service");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v11, &v19, v10);
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v10,
      "WinREAgent::WinREServicingManager::Service",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      479,
      L"Failed to schedule WinRE servicing");
    return v10;
  }
  v10 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 104LL))(
          this,
          a3,
          a4);
  if ( (v10 & 0x80000000) != 0 )
  {
    v19 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL))((char *)this + 24, &v19) )
    {
      v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v19,
        (__int64)"WinREAgent::WinREServicingManager::Service");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v13, &v19, v10);
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v10,
      "WinREAgent::WinREServicingManager::Service",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      486,
      L"Failed to stage WinRE servicing");
    return v10;
  }
  v14 = (*(__int64 (__fastcall **)(WinREAgent::WinREServicingManager *, void *, struct WinREAgent::IWinREServicingProgress *))(*(_QWORD *)this + 112LL))(
          this,
          a3,
          a4);
  v15 = *(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v8 + 64LL);
  v19 = 0;
  v16 = v15(v8, &v19);
  if ( (v14 & 0x80000000) == 0 )
  {
    if ( v16 )
    {
      v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))(v8);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v19,
        (__int64)"WinREAgent::WinREServicingManager::Service");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v18, &v19, v14);
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
    }
    PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::Service");
  }
  else
  {
    if ( v16 )
    {
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 24LL))(v8);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v19,
        (__int64)"WinREAgent::WinREServicingManager::Service");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v17, &v19, v14);
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v14,
      "WinREAgent::WinREServicingManager::Service",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      493,
      L"Failed to commit WinRE servicing");
  }
  return v14;
}

```

## disassembly

```asm
0x18001cd70  mov     [rsp-28h+arg_8], rbx
0x18001cd75  mov     [rsp-28h+arg_10], rsi
0x18001cd7a  push    rbp
0x18001cd7b  push    rdi
0x18001cd7c  push    r12
0x18001cd7e  push    r14
0x18001cd80  push    r15
0x18001cd82  mov     rbp, rsp
0x18001cd85  sub     rsp, 30h
0x18001cd89  mov     r15, r9
0x18001cd8c  mov     r12, r8
0x18001cd8f  mov     r14, rdx
0x18001cd92  mov     rsi, rcx
0x18001cd95  lea     rdx, aEnterWinreagen_3; "Enter WinREAgent::WinREServicingManager"...
0x18001cd9c  xor     ecx, ecx
0x18001cd9e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001cda3  lea     rdx, aScheduleWinreS_0; "Schedule WinRE servicing and execute"
0x18001cdaa  xor     ecx, ecx
0x18001cdac  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001cdb1  lea     rdi, [rsi+18h]
0x18001cdb5  mov     [rbp+arg_0], 0
0x18001cdbd  mov     rax, [rdi]
0x18001cdc0  lea     rdx, [rbp+arg_0]
0x18001cdc4  mov     rcx, rdi
0x18001cdc7  mov     rax, [rax+40h]
0x18001cdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd0  test    al, al
0x18001cdd2  jz      short loc_18001CE11
0x18001cdd4  mov     rax, [rdi]
0x18001cdd7  mov     rcx, rdi
0x18001cdda  mov     rax, [rax+18h]
0x18001cdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cde3  mov     rbx, rax
0x18001cde6  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001cded  lea     rcx, [rbp+arg_0]
0x18001cdf1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001cdf6  nop
0x18001cdf7  lea     rdx, [rbp+arg_0]
0x18001cdfb  mov     rcx, rbx
0x18001cdfe  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001ce03  nop
0x18001ce04  mov     rcx, [rbp+arg_0]
0x18001ce08  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ce0c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ce11  mov     rax, [rsi]
0x18001ce14  mov     rdx, r14
0x18001ce17  mov     rcx, rsi
0x18001ce1a  mov     rax, [rax+48h]
0x18001ce1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce23  mov     r14d, eax
0x18001ce26  test    eax, eax
0x18001ce28  jns     loc_18001CEC4
0x18001ce2e  mov     [rbp+arg_0], 0
0x18001ce36  mov     rdx, [rdi]
0x18001ce39  mov     rax, [rdx+40h]
0x18001ce3d  lea     rdx, [rbp+arg_0]
0x18001ce41  mov     rcx, rdi
0x18001ce44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce49  test    al, al
0x18001ce4b  jz      short loc_18001CE8D
0x18001ce4d  mov     rax, [rdi]
0x18001ce50  mov     rcx, rdi
0x18001ce53  mov     rax, [rax+18h]
0x18001ce57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce5c  mov     rbx, rax
0x18001ce5f  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001ce66  lea     rcx, [rbp+arg_0]
0x18001ce6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001ce6f  nop
0x18001ce70  mov     r8d, r14d
0x18001ce73  lea     rdx, [rbp+arg_0]
0x18001ce77  mov     rcx, rbx
0x18001ce7a  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001ce7f  nop
0x18001ce80  mov     rcx, [rbp+arg_0]
0x18001ce84  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ce88  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ce8d  lea     rax, aFailedToSchedu_0; "Failed to schedule WinRE servicing"
0x18001ce94  mov     [rsp+30h+var_8], rax
0x18001ce99  mov     [rsp+30h+var_10], 1DFh
0x18001cea1  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001cea8  lea     r8, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001ceaf  mov     edx, r14d
0x18001ceb2  mov     ecx, 2
0x18001ceb7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001cebc  mov     eax, r14d
0x18001cebf  jmp     loc_18001D056
0x18001cec4  mov     rax, [rsi]
0x18001cec7  mov     r8, r15
0x18001ceca  mov     rdx, r12
0x18001cecd  mov     rcx, rsi
0x18001ced0  mov     rax, [rax+68h]
0x18001ced4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced9  mov     r14d, eax
0x18001cedc  test    eax, eax
0x18001cede  jns     short loc_18001CF58
0x18001cee0  mov     [rbp+arg_0], 0
0x18001cee8  mov     rcx, [rdi]
0x18001ceeb  mov     rax, [rcx+40h]
0x18001ceef  lea     rdx, [rbp+arg_0]
0x18001cef3  mov     rcx, rdi
0x18001cef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cefb  test    al, al
0x18001cefd  jz      short loc_18001CF3F
0x18001ceff  mov     rax, [rdi]
0x18001cf02  mov     rcx, rdi
0x18001cf05  mov     rax, [rax+18h]
0x18001cf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0e  mov     rbx, rax
0x18001cf11  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001cf18  lea     rcx, [rbp+arg_0]
0x18001cf1c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001cf21  nop
0x18001cf22  mov     r8d, r14d
0x18001cf25  lea     rdx, [rbp+arg_0]
0x18001cf29  mov     rcx, rbx
0x18001cf2c  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001cf31  nop
0x18001cf32  mov     rcx, [rbp+arg_0]
0x18001cf36  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001cf3a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001cf3f  lea     rax, aFailedToStageW; "Failed to stage WinRE servicing"
0x18001cf46  mov     [rsp+30h+var_8], rax
0x18001cf4b  mov     [rsp+30h+var_10], 1E6h
0x18001cf53  jmp     loc_18001CEA1
0x18001cf58  mov     rax, [rsi]
0x18001cf5b  mov     r8, r15
0x18001cf5e  mov     rdx, r12
0x18001cf61  mov     rcx, rsi
0x18001cf64  mov     rax, [rax+70h]
0x18001cf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf6d  mov     esi, eax
0x18001cf6f  mov     rcx, [rdi]
0x18001cf72  mov     rax, [rcx+40h]
0x18001cf76  mov     [rbp+arg_0], 0
0x18001cf7e  lea     rdx, [rbp+arg_0]
0x18001cf82  mov     rcx, rdi
0x18001cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf8a  test    esi, esi
0x18001cf8c  jns     short loc_18001D002
0x18001cf8e  test    al, al
0x18001cf90  jz      short loc_18001CFD2
0x18001cf92  mov     rax, [rdi]
0x18001cf95  mov     rcx, rdi
0x18001cf98  mov     rax, [rax+18h]
0x18001cf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfa1  mov     rbx, rax
0x18001cfa4  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001cfab  lea     rcx, [rbp+arg_0]
0x18001cfaf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001cfb4  nop
0x18001cfb5  mov     r8d, esi
0x18001cfb8  lea     rdx, [rbp+arg_0]
0x18001cfbc  mov     rcx, rbx
0x18001cfbf  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001cfc4  nop
0x18001cfc5  mov     rcx, [rbp+arg_0]
0x18001cfc9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001cfcd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001cfd2  lea     rax, aFailedToCommit_1; "Failed to commit WinRE servicing"
0x18001cfd9  mov     [rsp+30h+var_8], rax
0x18001cfde  mov     [rsp+30h+var_10], 1EDh
0x18001cfe6  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001cfed  lea     r8, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001cff4  mov     edx, esi
0x18001cff6  mov     ecx, 2
0x18001cffb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001d000  jmp     short loc_18001D054
0x18001d002  test    al, al
0x18001d004  jz      short loc_18001D046
0x18001d006  mov     rax, [rdi]
0x18001d009  mov     rcx, rdi
0x18001d00c  mov     rax, [rax+18h]
0x18001d010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d015  mov     rbx, rax
0x18001d018  lea     rdx, aWinreagentWinr_12; "WinREAgent::WinREServicingManager::Serv"...
0x18001d01f  lea     rcx, [rbp+arg_0]
0x18001d023  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001d028  nop
0x18001d029  mov     r8d, esi
0x18001d02c  lea     rdx, [rbp+arg_0]
0x18001d030  mov     rcx, rbx
0x18001d033  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001d038  nop
0x18001d039  mov     rcx, [rbp+arg_0]
0x18001d03d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d041  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d046  lea     rdx, aExitWinreagent_11; "Exit WinREAgent::WinREServicingManager:"...
0x18001d04d  xor     ecx, ecx
0x18001d04f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001d054  mov     eax, esi
0x18001d056  mov     rbx, [rsp+30h+arg_8]
0x18001d05b  mov     rsi, [rsp+30h+arg_10]
0x18001d060  add     rsp, 30h
0x18001d064  pop     r15
0x18001d066  pop     r14
0x18001d068  pop     r12
0x18001d06a  pop     rdi
0x18001d06b  pop     rbp
0x18001d06c  retn
```
