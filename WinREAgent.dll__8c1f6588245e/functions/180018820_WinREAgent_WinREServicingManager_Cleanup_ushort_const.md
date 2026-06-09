# WinREAgent::WinREServicingManager::Cleanup(ushort const *)

- ea: `0x180018820`
- end: `0x180018e87`
- name: `?Cleanup@WinREServicingManager@WinREAgent@@UEAAJPEBG@Z`
- size: `1639`
- prototype: `int(WinREAgent::WinREServicingManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x180006de8`
- `0x18000d92c`
- `0x1800158bc`
- `0x180018820`
- `0x18001b1c0`
- `0x18001e51c`
- `0x18001f228`
- `0x18001f358`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004c2b0`
- `0x18004c418`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x18004d7a0`
- `0x18006f010`

## string_xrefs

- `0x180018b72`: `Failed to create execution context`
- `0x180018d59`: `Failed to get WinREAgent root directory`
- `0x180018c5e`: `update.wim`
- `0x180018a49`: `Failed to get suspend file path`
- `0x180018c06`: `Failed to construct WinRE parent directory path`
- `0x180018c93`: `Failed to build path for updated wim new location`
- `0x18001892f`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180018a5d`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180018a91`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180018838`: `Enter WinREAgent::WinREServicingManager::Cleanup`
- `0x180018865`: `WinREAgent::WinREServicingManager::Cleanup`
- `0x180018d9f`: `Cleanup WinREAgent root directory`
- `0x180018dbc`: `Failed to cleanup WinREAgent root directory`
- `0x180018e68`: `Exit WinREAgent::WinREServicingManager::Cleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::WinREServicingManager::Cleanup(
        WinREAgent::WinREServicingManager *this,
        const unsigned __int16 *a2)
{
  char *v4; // rdi
  __int64 v5; // rbx
  char v6; // al
  unsigned int ExecutionContext; // esi
  __int64 v8; // rbx
  WinREAgent::Executor *v9; // rbx
  struct WinREAgent::TelemetrySession *v10; // rax
  __int64 v11; // rbx
  char *v12; // r15
  int SuspendFile; // ebx
  int v15; // eax
  __int64 *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  const WCHAR *v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v23[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+58h] BYREF

  PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::Cleanup");
  v4 = (char *)this + 24;
  v24 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v24) )
  {
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))((char *)this + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v24,
      (__int64)"WinREAgent::WinREServicingManager::Cleanup");
    WinREAgent::TelemetrySession::TraceEnterAPI(v5, &v24);
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  }
  v24 = 0;
  if ( !*((_BYTE *)this + 64) )
  {
    v6 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))((char *)this + 24, &v24);
    ExecutionContext = -2147024875;
    if ( v6 )
    {
      v8 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v24,
        (__int64)"WinREAgent::WinREServicingManager::Cleanup");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v8, &v24, 2147942421LL);
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942421LL,
      "WinREAgent::WinREServicingManager::Cleanup",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      925,
      L"Must initialize WinREServicingManager first");
    return ExecutionContext;
  }
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 5) + 64LL))((char *)this + 40, &v24) )
  {
    PushButtonReset::Logging::Trace(0, L"Let Executor cleanup state");
    v9 = (WinREAgent::Executor *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 24LL))((char *)this + 40);
    v10 = (struct WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 32LL))((char *)this + 24);
    ExecutionContext = WinREAgent::Executor::Cleanup(v9, a2, v10);
    if ( (ExecutionContext & 0x80000000) != 0 )
    {
      v24 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v24) )
      {
        v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v24,
          (__int64)"WinREAgent::WinREServicingManager::Cleanup");
        WinREAgent::TelemetrySession::TraceLeaveAPI(v11, &v24, ExecutionContext);
        ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
      }
      PushButtonReset::Logging::TraceErr(
        2,
        ExecutionContext,
        "WinREAgent::WinREServicingManager::Cleanup",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        935,
        L"Executor failed to cleanup state");
      return ExecutionContext;
    }
LABEL_40:
    v24 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v24) )
    {
      v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v24,
        (__int64)"WinREAgent::WinREServicingManager::Cleanup");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v21, &v24, ExecutionContext);
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    }
    PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::Cleanup");
    return ExecutionContext;
  }
  PushButtonReset::Logging::Trace(0, L"No Executor found, do some basic cleanup");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v24);
  v12 = (char *)this + 56;
  SuspendFile = WinREAgent::WorkDir::GetSuspendFile((char *)this + 56, &v24);
  if ( SuspendFile < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)SuspendFile,
      "WinREAgent::WinREServicingManager::Cleanup",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      945,
      L"Failed to get suspend file path");
LABEL_15:
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    return (unsigned int)SuspendFile;
  }
  if ( (unsigned __int8)PushButtonReset::File::Exists(&v24) )
  {
    PushButtonReset::Logging::Trace(0, L"Cleanup suspend file");
    v15 = PushButtonReset::File::Delete(&v24);
    if ( v15 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v15,
        "WinREAgent::WinREServicingManager::Cleanup",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        953,
        L"Failed to cleanup suspend file");
  }
  v23[1] = 0;
  v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  v16 = (__int64 *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v23);
  ExecutionContext = WinREAgent::CreateExecutionContext((__int64 *)this + 7, 0, v16);
  if ( (ExecutionContext & 0x80000000) != 0 )
  {
    v25 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, &v25) )
    {
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 24LL))(v4);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v25,
        (__int64)"WinREAgent::WinREServicingManager::Cleanup");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v17, &v25, ExecutionContext);
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      ExecutionContext,
      "WinREAgent::WinREServicingManager::Cleanup",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      963,
      L"Failed to create execution context");
    goto LABEL_23;
  }
  if ( *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v23[0] + 24LL))(v23) + 120) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
    v18 = (*(__int64 (__fastcall **)(_QWORD *))(v23[0] + 24LL))(v23);
    SuspendFile = PushButtonReset::Path::GetDirectory(v18 + 120, &v26);
    if ( SuspendFile < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)SuspendFile,
        "WinREAgent::WinREServicingManager::Cleanup",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        974,
        L"Failed to construct WinRE parent directory path");
LABEL_27:
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(v23);
      goto LABEL_15;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v22,
      (__int64)L"update.wim");
    SuspendFile = PushButtonReset::Path::Combine(&v26, &v22, &v25);
    ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
    if ( SuspendFile < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)SuspendFile,
        "WinREAgent::WinREServicingManager::Cleanup",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        978,
        L"Failed to build path for updated wim new location");
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
      goto LABEL_27;
    }
    if ( (unsigned __int8)PushButtonReset::File::Exists(&v25) )
    {
      PushButtonReset::Logging::Trace(0, L"Cleanup existing new WinRE on Recovery partition");
      v19 = PushButtonReset::File::Delete(&v25);
      if ( v19 < 0 )
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v19,
          "WinREAgent::WinREServicingManager::Cleanup",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          990,
          L"Failed to cleanup existing new WinRE");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
  ExecutionContext = WinREAgent::WorkDir::GetRootDir((__int64)v12, (__int64)&v25);
  if ( (ExecutionContext & 0x80000000) == 0 )
  {
    if ( (unsigned __int8)PushButtonReset::Directory::Exists(&v25) )
    {
      PushButtonReset::Logging::Trace(0, L"Cleanup WinREAgent root directory");
      ExecutionContext = PushButtonReset::Directory::Delete(&v25, v20);
      if ( (ExecutionContext & 0x80000000) != 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          ExecutionContext,
          "WinREAgent::WinREServicingManager::Cleanup",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1006,
          L"Failed to cleanup WinREAgent root directory");
        ExecutionContext = 0;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(v23);
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    goto LABEL_40;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    ExecutionContext,
    "WinREAgent::WinREServicingManager::Cleanup",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    998,
    L"Failed to get WinREAgent root directory");
  ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
LABEL_23:
  v23[0] = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(v23);
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  return ExecutionContext;
}

```

## disassembly

```asm
0x180018820  push    rbp
0x180018822  push    rbx
0x180018823  push    rsi
0x180018824  push    rdi
0x180018825  push    r13
0x180018827  push    r14
0x180018829  push    r15
0x18001882b  mov     rbp, rsp
0x18001882e  sub     rsp, 50h
0x180018832  mov     r14, rdx
0x180018835  mov     rsi, rcx
0x180018838  lea     rdx, aEnterWinreagen_10; "Enter WinREAgent::WinREServicingManager"...
0x18001883f  xor     ecx, ecx
0x180018841  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180018846  lea     rdi, [rsi+18h]
0x18001884a  mov     [rbp+arg_0], 0
0x180018852  mov     rax, [rdi]
0x180018855  lea     rdx, [rbp+arg_0]
0x180018859  mov     rcx, rdi
0x18001885c  mov     rax, [rax+40h]
0x180018860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018865  lea     r13, aWinreagentWinr_22; "WinREAgent::WinREServicingManager::Clea"...
0x18001886c  test    al, al
0x18001886e  jz      short loc_1800188A9
0x180018870  mov     rax, [rdi]
0x180018873  mov     rcx, rdi
0x180018876  mov     rax, [rax+18h]
0x18001887a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001887f  mov     rbx, rax
0x180018882  mov     rdx, r13
0x180018885  lea     rcx, [rbp+arg_0]
0x180018889  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001888e  nop
0x18001888f  lea     rdx, [rbp+arg_0]
0x180018893  mov     rcx, rbx
0x180018896  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001889b  nop
0x18001889c  mov     rcx, [rbp+arg_0]
0x1800188a0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800188a4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800188a9  mov     [rbp+arg_0], 0
0x1800188b1  lea     rdx, [rbp+arg_0]
0x1800188b5  cmp     byte ptr [rsi+40h], 0
0x1800188b9  jnz     loc_180018945
0x1800188bf  mov     rax, [rdi]
0x1800188c2  mov     rcx, rdi
0x1800188c5  mov     rax, [rax+40h]
0x1800188c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ce  mov     esi, 80070015h
0x1800188d3  test    al, al
0x1800188d5  jz      short loc_180018913
0x1800188d7  mov     rax, [rdi]
0x1800188da  mov     rcx, rdi
0x1800188dd  mov     rax, [rax+18h]
0x1800188e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e6  mov     rbx, rax
0x1800188e9  mov     rdx, r13
0x1800188ec  lea     rcx, [rbp+arg_0]
0x1800188f0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800188f5  nop
0x1800188f6  mov     r8d, esi
0x1800188f9  lea     rdx, [rbp+arg_0]
0x1800188fd  mov     rcx, rbx
0x180018900  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180018905  nop
0x180018906  mov     rcx, [rbp+arg_0]
0x18001890a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001890e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018913  lea     rcx, aMustInitialize; "Must initialize WinREServicingManager f"...
0x18001891a  mov     [rsp+50h+var_28], rcx
0x18001891f  mov     [rsp+50h+var_30], 39Dh
0x180018927  mov     edx, 80070015h
0x18001892c  mov     r8, r13
0x18001892f  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180018936  mov     ecx, 2
0x18001893b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018940  jmp     loc_180018E76
0x180018945  lea     rbx, [rsi+28h]
0x180018949  mov     rax, [rbx]
0x18001894c  mov     rcx, rbx
0x18001894f  mov     rax, [rax+40h]
0x180018953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018958  xor     ecx, ecx
0x18001895a  test    al, al
0x18001895c  jz      loc_180018A1D
0x180018962  lea     rdx, aLetExecutorCle; "Let Executor cleanup state"
0x180018969  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001896e  mov     rax, [rbx]
0x180018971  mov     rcx, rbx
0x180018974  mov     rax, [rax+18h]
0x180018978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001897d  mov     rbx, rax
0x180018980  mov     rcx, [rdi]
0x180018983  mov     rax, [rcx+20h]
0x180018987  mov     rcx, rdi
0x18001898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001898f  mov     r8, rax; struct WinREAgent::TelemetrySession *
0x180018992  mov     rdx, r14; unsigned __int16 *
0x180018995  mov     rcx, rbx; this
0x180018998  call    ?Cleanup@Executor@WinREAgent@@QEAAJPEBGPEAVTelemetrySession@2@@Z; WinREAgent::Executor::Cleanup(ushort const *,WinREAgent::TelemetrySession *)
0x18001899d  mov     esi, eax
0x18001899f  test    eax, eax
0x1800189a1  jns     loc_180018E0D
0x1800189a7  mov     [rbp+arg_0], 0
0x1800189af  mov     rcx, [rdi]
0x1800189b2  mov     rax, [rcx+40h]
0x1800189b6  lea     rdx, [rbp+arg_0]
0x1800189ba  mov     rcx, rdi
0x1800189bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c2  test    al, al
0x1800189c4  jz      short loc_180018A02
0x1800189c6  mov     rax, [rdi]
0x1800189c9  mov     rcx, rdi
0x1800189cc  mov     rax, [rax+18h]
0x1800189d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189d5  mov     rbx, rax
0x1800189d8  mov     rdx, r13
0x1800189db  lea     rcx, [rbp+arg_0]
0x1800189df  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800189e4  nop
0x1800189e5  mov     r8d, esi
0x1800189e8  lea     rdx, [rbp+arg_0]
0x1800189ec  mov     rcx, rbx
0x1800189ef  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x1800189f4  nop
0x1800189f5  mov     rcx, [rbp+arg_0]
0x1800189f9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800189fd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018a02  lea     rax, aExecutorFailed; "Executor failed to cleanup state"
0x180018a09  mov     [rsp+50h+var_28], rax
0x180018a0e  mov     [rsp+50h+var_30], 3A7h
0x180018a16  mov     edx, esi
0x180018a18  jmp     loc_18001892C
0x180018a1d  lea     rdx, aNoExecutorFoun_0; "No Executor found, do some basic cleanu"...
0x180018a24  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180018a29  lea     rcx, [rbp+arg_0]
0x180018a2d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018a32  nop
0x180018a33  lea     r15, [rsi+38h]
0x180018a37  lea     rdx, [rbp+arg_0]
0x180018a3b  mov     rcx, r15
0x180018a3e  call    ?GetSuspendFile@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetSuspendFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180018a43  mov     ebx, eax
0x180018a45  test    eax, eax
0x180018a47  jns     short loc_180018A88
0x180018a49  lea     rax, aFailedToGetSus; "Failed to get suspend file path"
0x180018a50  mov     [rsp+50h+var_28], rax
0x180018a55  mov     [rsp+50h+var_30], 3B1h
0x180018a5d  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180018a64  mov     r8, r13
0x180018a67  mov     edx, ebx
0x180018a69  mov     ecx, 2
0x180018a6e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018a73  nop
0x180018a74  mov     rcx, [rbp+arg_0]
0x180018a78  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018a7c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018a81  mov     eax, ebx
0x180018a83  jmp     loc_180018E78
0x180018a88  lea     rcx, [rbp+arg_0]
0x180018a8c  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180018a91  lea     r14, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180018a98  test    al, al
0x180018a9a  jz      short loc_180018ADD
0x180018a9c  lea     rdx, aCleanupSuspend; "Cleanup suspend file"
0x180018aa3  xor     ecx, ecx
0x180018aa5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180018aaa  lea     rcx, [rbp+arg_0]
0x180018aae  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180018ab3  test    eax, eax
0x180018ab5  jns     short loc_180018ADD
0x180018ab7  lea     rcx, aFailedToCleanu_1; "Failed to cleanup suspend file"
0x180018abe  mov     [rsp+50h+var_28], rcx
0x180018ac3  mov     [rsp+50h+var_30], 3B9h
0x180018acb  mov     r9, r14
0x180018ace  mov     r8, r13
0x180018ad1  mov     edx, eax
0x180018ad3  mov     ecx, 1
0x180018ad8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018add  mov     [rbp+var_10], 0
0x180018ae5  lea     rbx, ??_7?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable'
0x180018aec  mov     [rbp+var_18], rbx
0x180018af0  lea     rcx, [rbp+var_18]
0x180018af4  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180018af9  mov     r8, rax
0x180018afc  xor     edx, edx
0x180018afe  mov     rcx, r15
0x180018b01  call    ?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z; WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)
0x180018b06  mov     esi, eax
0x180018b08  test    eax, eax
0x180018b0a  jns     loc_180018BB9
0x180018b10  mov     [rbp+arg_10], 0
0x180018b18  mov     rcx, [rdi]
0x180018b1b  mov     rax, [rcx+40h]
0x180018b1f  lea     rdx, [rbp+arg_10]
0x180018b23  mov     rcx, rdi
0x180018b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b2b  test    al, al
0x180018b2d  jz      short loc_180018B72
0x180018b2f  mov     rax, [rdi]
0x180018b32  mov     rcx, rdi
0x180018b35  mov     rax, [rax+18h]
0x180018b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b3e  mov     rbx, rax
0x180018b41  mov     rdx, r13
0x180018b44  lea     rcx, [rbp+arg_10]
0x180018b48  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180018b4d  nop
0x180018b4e  mov     r8d, esi
0x180018b51  lea     rdx, [rbp+arg_10]
0x180018b55  mov     rcx, rbx
0x180018b58  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180018b5d  nop
0x180018b5e  mov     rcx, [rbp+arg_10]
0x180018b62  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018b66  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018b6b  lea     rbx, ??_7?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable'
0x180018b72  lea     rax, aFailedToCreate_6; "Failed to create execution context"
0x180018b79  mov     [rsp+50h+var_28], rax
0x180018b7e  mov     [rsp+50h+var_30], 3C3h
0x180018b86  mov     r9, r14
0x180018b89  mov     r8, r13
0x180018b8c  mov     edx, esi
0x180018b8e  mov     ecx, 2
0x180018b93  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018b98  nop
0x180018b99  mov     [rbp+var_18], rbx
0x180018b9d  lea     rcx, [rbp+var_18]
0x180018ba1  call    ?Release@?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(void)
0x180018ba6  nop
0x180018ba7  mov     rcx, [rbp+arg_0]
0x180018bab  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018baf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018bb4  jmp     loc_180018E76
0x180018bb9  mov     rax, [rbp+var_18]
0x180018bbd  lea     rcx, [rbp+var_18]
0x180018bc1  mov     rax, [rax+18h]
0x180018bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bca  mov     rcx, [rax+78h]
0x180018bce  cmp     dword ptr [rcx-10h], 0
0x180018bd2  jz      loc_180018D3D
0x180018bd8  lea     rcx, [rbp+arg_18]
0x180018bdc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018be1  nop
0x180018be2  mov     rax, [rbp+var_18]
0x180018be6  lea     rcx, [rbp+var_18]
0x180018bea  mov     rax, [rax+18h]
0x180018bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bf3  lea     rcx, [rax+78h]
0x180018bf7  lea     rdx, [rbp+arg_18]
0x180018bfb  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180018c00  mov     ebx, eax
0x180018c02  test    eax, eax
0x180018c04  jns     short loc_180018C54
0x180018c06  lea     rax, aFailedToConstr_1; "Failed to construct WinRE parent direct"...
0x180018c0d  mov     [rsp+50h+var_28], rax
0x180018c12  mov     [rsp+50h+var_30], 3CEh
0x180018c1a  mov     r9, r14
0x180018c1d  mov     r8, r13
0x180018c20  mov     edx, ebx
0x180018c22  mov     ecx, 2
0x180018c27  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018c2c  nop
0x180018c2d  mov     rcx, [rbp+arg_18]
0x180018c31  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018c35  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018c3a  nop
0x180018c3b  lea     rax, ??_7?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable'
0x180018c42  mov     [rbp+var_18], rax
0x180018c46  lea     rcx, [rbp+var_18]
0x180018c4a  call    ?Release@?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(void)
0x180018c4f  jmp     loc_180018A74
0x180018c54  lea     rcx, [rbp+arg_10]
0x180018c58  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018c5d  nop
0x180018c5e  lea     rdx, aUpdateWim; "update.wim"
0x180018c65  lea     rcx, [rbp+var_20]
0x180018c69  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180018c6e  nop
0x180018c6f  lea     r8, [rbp+arg_10]
0x180018c73  lea     rdx, [rbp+var_20]
0x180018c77  lea     rcx, [rbp+arg_18]
0x180018c7b  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180018c80  mov     ebx, eax
0x180018c82  mov     rcx, [rbp+var_20]
0x180018c86  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018c8a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018c8f  test    ebx, ebx
0x180018c91  jns     short loc_180018CCC
0x180018c93  lea     rax, aFailedToBuildP; "Failed to build path for updated wim ne"...
0x180018c9a  mov     [rsp+50h+var_28], rax
0x180018c9f  mov     [rsp+50h+var_30], 3D2h
0x180018ca7  mov     r9, r14
0x180018caa  mov     r8, r13
0x180018cad  mov     edx, ebx
0x180018caf  mov     ecx, 2
0x180018cb4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180018cb9  nop
0x180018cba  mov     rcx, [rbp+arg_10]
0x180018cbe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
  ... truncated ...
```
