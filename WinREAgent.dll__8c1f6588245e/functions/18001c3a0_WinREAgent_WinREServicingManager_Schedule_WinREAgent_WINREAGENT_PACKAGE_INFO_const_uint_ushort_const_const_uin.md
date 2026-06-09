# WinREAgent::WinREServicingManager::Schedule(WinREAgent::WINREAGENT_PACKAGE_INFO * const,uint,ushort const * * const,uint)

- ea: `0x18001c3a0`
- end: `0x18001c95e`
- name: `?Schedule@WinREServicingManager@WinREAgent@@UEAAJQEAUWINREAGENT_PACKAGE_INFO@2@IQEAPEBGI@Z`
- size: `1470`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, struct WinREAgent::WINREAGENT_PACKAGE_INFO *const, unsigned int, const unsigned __int16 **const, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003eb0`
- `0x180006500`
- `0x180006564`
- `0x180006b20`
- `0x1800086d8`
- `0x18000d690`
- `0x18000d92c`
- `0x18000f254`
- `0x1800158bc`
- `0x18001c3a0`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18001c66f`: `Source path [%u]: [%s] added `
- `0x18001c4c5`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001c7c5`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001c889`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001c3c0`: `Enter WinREAgent::WinREServicingManager::Schedule`
- `0x18001c40f`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c477`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c4be`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c517`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c5eb`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c6d3`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c783`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c7cc`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c847`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c890`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c8fa`: `WinREAgent::WinREServicingManager::Schedule`
- `0x18001c545`: `Cannot execute this API because Schedule() was already called`
- `0x18001c928`: `Exit WinREAgent::WinREServicingManager::Schedule`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinREAgent::WinREServicingManager::Schedule(
        WinREAgent::WinREServicingManager *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        const unsigned __int16 **const a4,
        unsigned int a5)
{
  char *v9; // rdi
  __int64 v10; // rbx
  char v11; // al
  unsigned int v12; // r14d
  __int64 v13; // rbx
  char v15; // al
  __int64 v16; // rbx
  void **v17; // rax
  unsigned int i; // ebx
  WinREAgent::Executor *v19; // rax
  unsigned int v20; // esi
  __int64 v21; // rbx
  __int64 v22; // rax
  unsigned int v23; // esi
  unsigned int v24; // r15d
  _QWORD *v25; // r13
  WinREAgent::Executor *v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rbx
  WinREAgent::TelemetrySession *v29; // rax
  __int64 v30; // rbx
  WinREAgent::Executor *v31; // rbx
  struct WinREAgent::TelemetrySession *v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rbx
  void **v36; // [rsp+30h] [rbp-18h] BYREF
  __int64 v37; // [rsp+38h] [rbp-10h]
  __int64 v38; // [rsp+90h] [rbp+48h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::Schedule");
  PushButtonReset::Logging::Trace(0, L"Servicing of WinRE image using packages");
  v9 = (char *)this + 24;
  v38 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v38) )
  {
    v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))(v9);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)"WinREAgent::WinREServicingManager::Schedule");
    WinREAgent::TelemetrySession::TraceEnterAPI(v10, &v38);
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  }
  if ( !*((_BYTE *)this + 64) )
  {
    v38 = 0;
    v11 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38);
    v12 = -2147024875;
    if ( v11 )
    {
      v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))(v9);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v38,
        (__int64)"WinREAgent::WinREServicingManager::Schedule");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v13, &v38, 2147942421LL);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942421LL,
      "WinREAgent::WinREServicingManager::Schedule",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      659,
      L"Must initialize WinREServicingManager first");
    return v12;
  }
  if ( *((_BYTE *)this + 65) )
  {
    v38 = 0;
    v15 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38);
    v12 = -2147024811;
    if ( v15 )
    {
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))(v9);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v38,
        (__int64)"WinREAgent::WinREServicingManager::Schedule");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v16, &v38, 2147942485LL);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942485LL,
      "WinREAgent::WinREServicingManager::Schedule",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      666,
      L"Cannot execute this API because Schedule() was already called");
    return v12;
  }
  v37 = PbrNew<WinREAgent::Executor,>();
  v17 = &RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable';
  v36 = &RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable';
  for ( i = 0; i < a3; ++i )
  {
    v19 = (WinREAgent::Executor *)((__int64 (__fastcall *)(void ***))v17[3])(&v36);
    v20 = WinREAgent::Executor::AddPackage(v19, a2[3 * i], (__int64)a2[3 * i + 1], (__int64)a2[3 * i + 2]);
    if ( (v20 & 0x80000000) != 0 )
    {
      v38 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38) )
      {
        v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))((char *)this + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v38,
          (__int64)"WinREAgent::WinREServicingManager::Schedule");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v21, &v38, v20);
        ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      }
      PushButtonReset::Logging::TraceErr(
        2,
        v20,
        "WinREAgent::WinREServicingManager::Schedule",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        682,
        L"Failed to add package");
      goto LABEL_39;
    }
    v17 = v36;
  }
  if ( a4 )
  {
    v22 = ((__int64 (__fastcall *)(void ***))v17[3])(&v36);
    v23 = 0;
    v24 = a5;
    if ( a5 )
    {
      v25 = (_QWORD *)(v22 + 216);
      do
      {
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
          v25,
          (__int64)a4[v23]);
        PushButtonReset::Logging::Trace(0, L"Source path [%u]: [%s] added ", v23, a4[v23]);
        ++v23;
      }
      while ( v23 < v24 );
    }
    v17 = v36;
  }
  v26 = (WinREAgent::Executor *)((__int64 (__fastcall *)(void ***))v17[3])(&v36);
  v20 = WinREAgent::Executor::FillPackageInfo(v26);
  if ( (v20 & 0x80000000) == 0 )
  {
    v28 = ((__int64 (__fastcall *)(void ***))v36[3])(&v36);
    v29 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 32LL))((char *)this + 24);
    v20 = WinREAgent::Executor::ScheduleExecution(v28, (_QWORD *)this + 7, v29);
    if ( (v20 & 0x80000000) == 0 )
    {
      v31 = (WinREAgent::Executor *)((__int64 (__fastcall *)(void ***))v36[3])(&v36);
      v32 = (struct WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 32LL))((char *)this + 24);
      if ( WinREAgent::Executor::CanExecute(v31, v32) )
      {
        v34 = v37;
        v37 = 0;
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 5) + 48LL))((char *)this + 40, v34);
        *((_BYTE *)this + 65) = 1;
        v38 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38) )
        {
          v35 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))((char *)this + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v38,
            (__int64)"WinREAgent::WinREServicingManager::Schedule");
          WinREAgent::TelemetrySession::TraceLeaveAPI(v35, &v38, v20);
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
        }
        PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::Schedule");
      }
      else
      {
        v38 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38) )
        {
          v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))((char *)this + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v38,
            (__int64)"WinREAgent::WinREServicingManager::Schedule");
          WinREAgent::TelemetrySession::TraceLeaveAPI(v33, &v38, v20);
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
        }
        PushButtonReset::Logging::TraceErr(
          2,
          2147500037LL,
          "WinREAgent::WinREServicingManager::Schedule",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          713,
          L"Could not execute WinRE servicing operations");
        v20 = -2147467259;
      }
    }
    else
    {
      v38 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38) )
      {
        v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))((char *)this + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v38,
          (__int64)"WinREAgent::WinREServicingManager::Schedule");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v30, &v38, v20);
        ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      }
      PushButtonReset::Logging::TraceErr(
        2,
        v20,
        "WinREAgent::WinREServicingManager::Schedule",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        707,
        L"Failed to schedule execution");
    }
  }
  else
  {
    v38 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v9 + 64LL))((char *)this + 24, &v38) )
    {
      v27 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v38,
        (__int64)"WinREAgent::WinREServicingManager::Schedule");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v27, &v38, v20);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      v20,
      "WinREAgent::WinREServicingManager::Schedule",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      700,
      L"Failed to fill package info");
  }
LABEL_39:
  v36 = &RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::Executor *>::Release(&v36);
  return v20;
}

```

## disassembly

```asm
0x18001c3a0  push    rbp
0x18001c3a2  push    rbx
0x18001c3a3  push    rsi
0x18001c3a4  push    rdi
0x18001c3a5  push    r12
0x18001c3a7  push    r13
0x18001c3a9  push    r14
0x18001c3ab  push    r15
0x18001c3ad  mov     rbp, rsp
0x18001c3b0  sub     rsp, 48h
0x18001c3b4  mov     r12, r9
0x18001c3b7  mov     r15d, r8d
0x18001c3ba  mov     r13, rdx
0x18001c3bd  mov     r14, rcx
0x18001c3c0  lea     rdx, aEnterWinreagen; "Enter WinREAgent::WinREServicingManager"...
0x18001c3c7  xor     ecx, ecx
0x18001c3c9  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001c3ce  lea     rdx, aServicingOfWin; "Servicing of WinRE image using packages"
0x18001c3d5  xor     ecx, ecx
0x18001c3d7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001c3dc  lea     rdi, [r14+18h]
0x18001c3e0  xor     esi, esi
0x18001c3e2  mov     [rbp+arg_0], rsi
0x18001c3e6  mov     rax, [rdi]
0x18001c3e9  lea     rdx, [rbp+arg_0]
0x18001c3ed  mov     rcx, rdi
0x18001c3f0  mov     rax, [rax+40h]
0x18001c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f9  test    al, al
0x18001c3fb  jz      short loc_18001C43A
0x18001c3fd  mov     rax, [rdi]
0x18001c400  mov     rcx, rdi
0x18001c403  mov     rax, [rax+18h]
0x18001c407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c40c  mov     rbx, rax
0x18001c40f  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c416  lea     rcx, [rbp+arg_0]
0x18001c41a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c41f  nop
0x18001c420  lea     rdx, [rbp+arg_0]
0x18001c424  mov     rcx, rbx
0x18001c427  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001c42c  nop
0x18001c42d  mov     rcx, [rbp+arg_0]
0x18001c431  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c435  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c43a  cmp     [r14+40h], sil
0x18001c43e  jnz     loc_18001C4DE
0x18001c444  mov     [rbp+arg_0], rsi
0x18001c448  mov     rax, [rdi]
0x18001c44b  lea     rdx, [rbp+arg_0]
0x18001c44f  mov     rcx, rdi
0x18001c452  mov     rax, [rax+40h]
0x18001c456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c45b  mov     r14d, 80070015h
0x18001c461  test    al, al
0x18001c463  jz      short loc_18001C4A5
0x18001c465  mov     rax, [rdi]
0x18001c468  mov     rcx, rdi
0x18001c46b  mov     rax, [rax+18h]
0x18001c46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c474  mov     rbx, rax
0x18001c477  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c47e  lea     rcx, [rbp+arg_0]
0x18001c482  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c487  nop
0x18001c488  mov     r8d, r14d
0x18001c48b  lea     rdx, [rbp+arg_0]
0x18001c48f  mov     rcx, rbx
0x18001c492  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001c497  nop
0x18001c498  mov     rcx, [rbp+arg_0]
0x18001c49c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c4a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c4a5  lea     rcx, aMustInitialize; "Must initialize WinREServicingManager f"...
0x18001c4ac  mov     [rsp+48h+var_20], rcx
0x18001c4b1  mov     [rsp+48h+var_28], 293h
0x18001c4b9  mov     edx, 80070015h
0x18001c4be  lea     r8, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c4c5  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001c4cc  mov     ecx, 2
0x18001c4d1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001c4d6  mov     eax, r14d
0x18001c4d9  jmp     loc_18001C94D
0x18001c4de  cmp     [r14+41h], sil
0x18001c4e2  jz      short loc_18001C563
0x18001c4e4  mov     [rbp+arg_0], rsi
0x18001c4e8  mov     rax, [rdi]
0x18001c4eb  lea     rdx, [rbp+arg_0]
0x18001c4ef  mov     rcx, rdi
0x18001c4f2  mov     rax, [rax+40h]
0x18001c4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4fb  mov     r14d, 80070055h
0x18001c501  test    al, al
0x18001c503  jz      short loc_18001C545
0x18001c505  mov     rax, [rdi]
0x18001c508  mov     rcx, rdi
0x18001c50b  mov     rax, [rax+18h]
0x18001c50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c514  mov     rbx, rax
0x18001c517  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c51e  lea     rcx, [rbp+arg_0]
0x18001c522  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c527  nop
0x18001c528  mov     r8d, r14d
0x18001c52b  lea     rdx, [rbp+arg_0]
0x18001c52f  mov     rcx, rbx
0x18001c532  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001c537  nop
0x18001c538  mov     rcx, [rbp+arg_0]
0x18001c53c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c540  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c545  lea     rcx, aCannotExecuteT; "Cannot execute this API because Schedul"...
0x18001c54c  mov     [rsp+48h+var_20], rcx
0x18001c551  mov     [rsp+48h+var_28], 29Ah
0x18001c559  mov     edx, 80070055h
0x18001c55e  jmp     loc_18001C4BE
0x18001c563  call    ??$PbrNew@VExecutor@WinREAgent@@$$V@@YAPEAVExecutor@WinREAgent@@XZ; PbrNew<WinREAgent::Executor,>(void)
0x18001c568  mov     [rbp+var_10], rax
0x18001c56c  lea     rax, ??_7?$CAutoPbrDelete@PEAVExecutor@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable'
0x18001c573  mov     [rbp+var_18], rax
0x18001c577  mov     ebx, esi
0x18001c579  cmp     ebx, r15d
0x18001c57c  jnb     loc_18001C632
0x18001c582  lea     rcx, [rbp+var_18]
0x18001c586  mov     rax, [rax+18h]
0x18001c58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c58f  mov     ecx, ebx
0x18001c591  lea     rdx, [rcx+rcx*2]
0x18001c595  mov     r9, [r13+rdx*8+10h]; unsigned __int64
0x18001c59a  mov     r8, [r13+rdx*8+8]; unsigned __int64
0x18001c59f  mov     rdx, [r13+rdx*8+0]; unsigned __int16 *
0x18001c5a4  mov     rcx, rax; this
0x18001c5a7  call    ?AddPackage@Executor@WinREAgent@@QEAAJPEBG_K1@Z; WinREAgent::Executor::AddPackage(ushort const *,unsigned __int64,unsigned __int64)
0x18001c5ac  mov     esi, eax
0x18001c5ae  test    eax, eax
0x18001c5b0  js      short loc_18001C5BA
0x18001c5b2  inc     ebx
0x18001c5b4  mov     rax, [rbp+var_18]
0x18001c5b8  jmp     short loc_18001C579
0x18001c5ba  mov     [rbp+arg_0], 0
0x18001c5c2  mov     rax, [rdi]
0x18001c5c5  lea     rdx, [rbp+arg_0]
0x18001c5c9  mov     rcx, rdi
0x18001c5cc  mov     rax, [rax+40h]
0x18001c5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5d5  test    al, al
0x18001c5d7  jz      short loc_18001C619
0x18001c5d9  mov     rax, [rdi]
0x18001c5dc  mov     rcx, rdi
0x18001c5df  mov     rax, [rax+18h]
0x18001c5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5e8  mov     rbx, rax
0x18001c5eb  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c5f2  lea     rcx, [rbp+arg_0]
0x18001c5f6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c5fb  nop
0x18001c5fc  mov     r8d, esi
0x18001c5ff  lea     rdx, [rbp+arg_0]
0x18001c603  mov     rcx, rbx
0x18001c606  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001c60b  nop
0x18001c60c  mov     rcx, [rbp+arg_0]
0x18001c610  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c614  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c619  lea     rax, aFailedToAddPac_0; "Failed to add package"
0x18001c620  mov     [rsp+48h+var_20], rax
0x18001c625  mov     [rsp+48h+var_28], 2AAh
0x18001c62d  jmp     loc_18001C7C5
0x18001c632  xor     r13d, r13d
0x18001c635  test    r12, r12
0x18001c638  jz      short loc_18001C68B
0x18001c63a  lea     rcx, [rbp+var_18]
0x18001c63e  mov     rax, [rax+18h]
0x18001c642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c647  mov     esi, r13d
0x18001c64a  mov     r15d, [rbp+arg_20]
0x18001c64e  test    r15d, r15d
0x18001c651  jz      short loc_18001C687
0x18001c653  lea     r13, [rax+0D8h]
0x18001c65a  mov     ebx, esi
0x18001c65c  mov     rdx, [r12+rbx*8]
0x18001c660  mov     rcx, r13
0x18001c663  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18001c668  mov     r9, [r12+rbx*8]
0x18001c66c  mov     r8d, esi
0x18001c66f  lea     rdx, aSourcePathUSAd; "Source path [%u]: [%s] added "
0x18001c676  xor     ecx, ecx
0x18001c678  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001c67d  inc     esi
0x18001c67f  cmp     esi, r15d
0x18001c682  jb      short loc_18001C65A
0x18001c684  xor     r13d, r13d
0x18001c687  mov     rax, [rbp+var_18]
0x18001c68b  lea     rcx, [rbp+var_18]
0x18001c68f  mov     rax, [rax+18h]
0x18001c693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c698  mov     rcx, rax; this
0x18001c69b  call    ?FillPackageInfo@Executor@WinREAgent@@QEAAJXZ; WinREAgent::Executor::FillPackageInfo(void)
0x18001c6a0  mov     esi, eax
0x18001c6a2  test    eax, eax
0x18001c6a4  jns     short loc_18001C71A
0x18001c6a6  mov     [rbp+arg_0], r13
0x18001c6aa  mov     rcx, [rdi]
0x18001c6ad  mov     rax, [rcx+40h]
0x18001c6b1  lea     rdx, [rbp+arg_0]
0x18001c6b5  mov     rcx, rdi
0x18001c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6bd  test    al, al
0x18001c6bf  jz      short loc_18001C701
0x18001c6c1  mov     rax, [rdi]
0x18001c6c4  mov     rcx, rdi
0x18001c6c7  mov     rax, [rax+18h]
0x18001c6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6d0  mov     rbx, rax
0x18001c6d3  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c6da  lea     rcx, [rbp+arg_0]
0x18001c6de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c6e3  nop
0x18001c6e4  mov     r8d, esi
0x18001c6e7  lea     rdx, [rbp+arg_0]
0x18001c6eb  mov     rcx, rbx
0x18001c6ee  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001c6f3  nop
0x18001c6f4  mov     rcx, [rbp+arg_0]
0x18001c6f8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c6fc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c701  lea     rax, aFailedToFillPa; "Failed to fill package info"
0x18001c708  mov     [rsp+48h+var_20], rax
0x18001c70d  mov     [rsp+48h+var_28], 2BCh
0x18001c715  jmp     loc_18001C7C5
0x18001c71a  mov     rax, [rbp+var_18]
0x18001c71e  lea     rcx, [rbp+var_18]
0x18001c722  mov     rax, [rax+18h]
0x18001c726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c72b  mov     rbx, rax
0x18001c72e  mov     rcx, [rdi]
0x18001c731  mov     rax, [rcx+20h]
0x18001c735  mov     rcx, rdi
0x18001c738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c73d  lea     rdx, [r14+38h]
0x18001c741  mov     r8, rax
0x18001c744  mov     rcx, rbx
0x18001c747  call    ?ScheduleExecution@Executor@WinREAgent@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVTelemetrySession@2@@Z; WinREAgent::Executor::ScheduleExecution(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,WinREAgent::TelemetrySession *)
0x18001c74c  mov     esi, eax
0x18001c74e  test    eax, eax
0x18001c750  jns     loc_18001C7E4
0x18001c756  mov     [rbp+arg_0], r13
0x18001c75a  mov     rcx, [rdi]
0x18001c75d  mov     rax, [rcx+40h]
0x18001c761  lea     rdx, [rbp+arg_0]
0x18001c765  mov     rcx, rdi
0x18001c768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c76d  test    al, al
0x18001c76f  jz      short loc_18001C7B1
0x18001c771  mov     rax, [rdi]
0x18001c774  mov     rcx, rdi
0x18001c777  mov     rax, [rax+18h]
0x18001c77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c780  mov     rbx, rax
0x18001c783  lea     rdx, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c78a  lea     rcx, [rbp+arg_0]
0x18001c78e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001c793  nop
0x18001c794  mov     r8d, esi
0x18001c797  lea     rdx, [rbp+arg_0]
0x18001c79b  mov     rcx, rbx
0x18001c79e  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001c7a3  nop
0x18001c7a4  mov     rcx, [rbp+arg_0]
0x18001c7a8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c7ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c7b1  lea     rax, aFailedToSchedu; "Failed to schedule execution"
0x18001c7b8  mov     [rsp+48h+var_20], rax
0x18001c7bd  mov     [rsp+48h+var_28], 2C3h
0x18001c7c5  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001c7cc  lea     r8, aWinreagentWinr_24; "WinREAgent::WinREServicingManager::Sche"...
0x18001c7d3  mov     edx, esi
0x18001c7d5  mov     ecx, 2
0x18001c7da  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001c7df  jmp     loc_18001C937
0x18001c7e4  mov     rax, [rbp+var_18]
0x18001c7e8  lea     rcx, [rbp+var_18]
0x18001c7ec  mov     rax, [rax+18h]
0x18001c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f5  mov     rbx, rax
0x18001c7f8  mov     rcx, [rdi]
0x18001c7fb  mov     rax, [rcx+20h]
0x18001c7ff  mov     rcx, rdi
0x18001c802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c807  mov     rdx, rax; struct WinREAgent::TelemetrySession *
0x18001c80a  mov     rcx, rbx; this
0x18001c80d  call    ?CanExecute@Executor@WinREAgent@@QEBA_NPEAVTelemetrySession@2@@Z; WinREAgent::Executor::CanExecute(WinREAgent::TelemetrySession *)
0x18001c812  test    al, al
0x18001c814  jnz     loc_18001C8B0
0x18001c81a  mov     [rbp+arg_0], r13
0x18001c81e  mov     rax, [rdi]
0x18001c821  lea     rdx, [rbp+arg_0]
0x18001c825  mov     rcx, rdi
0x18001c828  mov     rax, [rax+40h]
  ... truncated ...
```
