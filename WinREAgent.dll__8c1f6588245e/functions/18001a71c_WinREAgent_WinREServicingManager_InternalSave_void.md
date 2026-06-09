# WinREAgent::WinREServicingManager::InternalSave(void)

- ea: `0x18001a71c`
- end: `0x18001aea9`
- name: `?InternalSave@WinREServicingManager@WinREAgent@@AEAAJXZ`
- size: `1933`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18001da20`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x18000d800`
- `0x18000d92c`
- `0x18000e9c0`
- `0x1800158bc`
- `0x18001a71c`
- `0x18001b1e0`
- `0x18001f358`
- `0x18002dcf0`
- `0x18002e448`
- `0x18002ed10`
- `0x18003717c`
- `0x180037344`
- `0x180050e24`
- `0x180050fe8`
- `0x180052400`
- `0x1800528ac`
- `0x18005338c`
- `0x1800533dc`
- `0x180053554`
- `0x18006f010`

## string_xrefs

- `0x18001ad95`: `Failed to get suspend file path`
- `0x18001a7be`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a803`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a88d`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a919`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001abd4`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001ad2f`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001ada9`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001ae06`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a77c`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001a7c5`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001a80a`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001a894`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001a920`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001abdb`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001ad36`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001adb0`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001ae0d`: `WinREAgent::WinREServicingManager::InternalSave`
- `0x18001a879`: `Failed to create empty document`
- `0x18001aa83`: `Scheduled`
- `0x18001aab6`: `Failed to save Scheduled State`
- `0x18001abc0`: `Failed to create Executor node`
- `0x18001adf2`: `Failed to write document to [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinREAgent::WinREServicingManager::InternalSave(WinREAgent::WinREServicingManager *this)
{
  __int64 v2; // rbx
  char *v4; // r15
  __int64 v5; // rbx
  int Root; // ebx
  PushButtonReset::SerializeDocument *v7; // rbx
  struct PushButtonReset::SerializeNode **v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rdi
  char v13; // bl
  __int64 v14; // r8
  __int64 v15; // rdi
  char v16; // bl
  __int64 v17; // r8
  PushButtonReset::XmlNode **v18; // rdi
  _QWORD *v19; // rbx
  struct PushButtonReset::SerializeNode *v20; // rbx
  struct WinREAgent::Executor *v21; // rax
  char *v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  int v26; // esi
  __int64 v27; // rbx
  ATL::CStringData *v28; // rcx
  WinREAgent::TelemetrySession *v29; // rax
  _QWORD v30[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v32[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v33; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v34; // [rsp+A8h] [rbp+38h] BYREF

  if ( !*((_BYTE *)this + 64) )
  {
    v33 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v33) )
    {
      v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 24LL))((char *)this + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v33,
        (__int64)"WinREAgent::WinREServicingManager::InternalSave");
      WinREAgent::TelemetrySession::TraceLeaveAPI(v2, &v33, 2147942421LL);
      ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    }
    PushButtonReset::Logging::TraceErr(
      2,
      2147942421LL,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1039,
      L"Must initialize WinREServicingManager first");
    return 2147942421LL;
  }
  v4 = (char *)this + 56;
  if ( !*(_DWORD *)(*((_QWORD *)this + 7) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942450LL,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1047,
      L"Can't suspend the session because the target root is not known");
    return 2147942450LL;
  }
  v31[1] = 0;
  v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
  v5 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v31);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"ResetSession");
  Root = PushButtonReset::SerializeDocument::Create(&v33, v5);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1053,
      L"Failed to create empty document");
LABEL_9:
    v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
LABEL_10:
    RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v31);
    return (unsigned int)Root;
  }
  v30[1] = 0;
  v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  v7 = (PushButtonReset::SerializeDocument *)(*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
  v8 = (struct PushButtonReset::SerializeNode **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v30);
  Root = PushButtonReset::SerializeDocument::GetRoot(v7, v8);
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1057,
      L"Failed to get root node");
LABEL_13:
    v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v30);
    goto LABEL_9;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"MajorVersion");
  Root = PushButtonReset::SerializeNode::SetProperty(v9, &v33, 1);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1060,
      L"Failed to save MajorVersion");
    goto LABEL_13;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"MinorVersion");
  Root = PushButtonReset::SerializeNode::SetProperty(v10, &v33, 4);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1063,
      L"Failed to save MinorVersion");
    goto LABEL_13;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"TargetRoot");
  Root = PushButtonReset::SerializeNode::SetProperty(v11, &v33, v4);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1066,
      L"Failed to save Target Root");
    goto LABEL_13;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
  v13 = *((_BYTE *)this + 65);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"Scheduled");
  LOBYTE(v14) = v13;
  Root = PushButtonReset::SerializeNode::SetProperty(v12, &v33, v14);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1069,
      L"Failed to save Scheduled State");
    goto LABEL_13;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
  v16 = *((_BYTE *)this + 66);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v33,
    (__int64)L"Staged");
  LOBYTE(v17) = v16;
  Root = PushButtonReset::SerializeNode::SetProperty(v15, &v33, v17);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1072,
      L"Failed to save Staged State");
    goto LABEL_13;
  }
  v33 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 5) + 64LL))((char *)this + 40, &v33) )
  {
    v32[1] = 0;
    v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    v18 = (PushButtonReset::XmlNode **)(*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
    v19 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 8LL))(v32);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v33,
      (__int64)L"Executor");
    Root = PushButtonReset::SerializeNode::AddChild(v18, &v33, v19);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    if ( Root < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Root,
        "WinREAgent::WinREServicingManager::InternalSave",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1078,
        L"Failed to create Executor node");
LABEL_27:
      v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v32);
LABEL_28:
      v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v30);
      v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
      goto LABEL_10;
    }
    v20 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 32LL))(v32);
    v21 = (struct WinREAgent::Executor *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 32LL))((char *)this + 40);
    Root = WinREAgent::Executor::Save(v21, v20);
    if ( Root < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Root,
        "WinREAgent::WinREServicingManager::InternalSave",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1081,
        L"Failed to save Executor");
      goto LABEL_27;
    }
    v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v32);
  }
  v22 = (char *)this + 24;
  v33 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 3) + 64LL))((char *)this + 24, &v33) )
  {
    v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 24LL))((char *)this + 24);
    WinREAgent::TelemetrySession::GetCVString(v23, &v33);
    if ( !*(_DWORD *)(v33 - 16) )
      PushButtonReset::Logging::Trace(1, L"Telemetry has empty correlationvector");
    v24 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v34,
      (__int64)L"CVString");
    Root = PushButtonReset::SerializeNode::SetProperty(v24, &v34, &v33);
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
    if ( Root < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Root,
        "WinREAgent::WinREServicingManager::InternalSave",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1096,
        L"Failed to save correlationvector");
LABEL_37:
      ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
      goto LABEL_28;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"WinREServicingManager doesn't have telemetry, skip it");
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v33);
  Root = WinREAgent::WorkDir::GetSuspendFile(v4, &v33);
  if ( Root < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1106,
      L"Failed to get suspend file path");
    goto LABEL_37;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD *))(v31[0] + 24LL))(v31);
  v26 = PushButtonReset::SerializeDocument::Save(v25, &v33);
  if ( v26 >= 0 )
  {
    v34 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v22 + 64LL))(v22, &v34) )
    {
      v29 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 24LL))(v22);
      WinREAgent::TelemetrySession::TraceSessionSaved(v29);
    }
    v28 = (ATL::CStringData *)(v33 - 24);
  }
  else
  {
    v27 = v33;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v26,
      "WinREAgent::WinREServicingManager::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1110,
      L"Failed to write document to [%s]",
      v33);
    v28 = (ATL::CStringData *)(v27 - 24);
  }
  ATL::CStringData::Release(v28);
  v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v30);
  v31[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v31);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18001a71c  mov     [rsp-28h+arg_10], rbx
0x18001a721  mov     [rsp-28h+arg_18], rsi
0x18001a726  push    rbp
0x18001a727  push    rdi
0x18001a728  push    r13
0x18001a72a  push    r14
0x18001a72c  push    r15
0x18001a72e  mov     rbp, rsp
0x18001a731  sub     rsp, 70h
0x18001a735  mov     rsi, rcx
0x18001a738  cmp     byte ptr [rcx+40h], 0
0x18001a73c  jnz     loc_18001A7E2
0x18001a742  mov     [rbp+arg_0], 0
0x18001a74a  mov     rax, [rcx+18h]
0x18001a74e  lea     rdx, [rbp+arg_0]
0x18001a752  add     rcx, 18h
0x18001a756  mov     rax, [rax+40h]
0x18001a75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a75f  mov     edi, 80070015h
0x18001a764  test    al, al
0x18001a766  jz      short loc_18001A7AA
0x18001a768  mov     rax, [rsi+18h]
0x18001a76c  lea     rcx, [rsi+18h]
0x18001a770  mov     rax, [rax+18h]
0x18001a774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a779  mov     rbx, rax
0x18001a77c  lea     rdx, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001a783  lea     rcx, [rbp+arg_0]
0x18001a787  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x18001a78c  nop
0x18001a78d  mov     r8d, edi
0x18001a790  lea     rdx, [rbp+arg_0]
0x18001a794  mov     rcx, rbx
0x18001a797  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18001a79c  nop
0x18001a79d  mov     rcx, [rbp+arg_0]
0x18001a7a1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a7a5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a7aa  lea     rcx, aMustInitialize; "Must initialize WinREServicingManager f"...
0x18001a7b1  mov     [rsp+70h+var_48], rcx
0x18001a7b6  mov     [rsp+70h+var_50], 40Fh
0x18001a7be  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001a7c5  lea     r8, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001a7cc  mov     edx, 80070015h
0x18001a7d1  mov     ecx, 2
0x18001a7d6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001a7db  mov     eax, edi
0x18001a7dd  jmp     loc_18001AE90
0x18001a7e2  lea     r15, [rcx+38h]
0x18001a7e6  mov     rax, [r15]
0x18001a7e9  cmp     dword ptr [rax-10h], 0
0x18001a7ed  jnz     short loc_18001A82A
0x18001a7ef  lea     rax, aCanTSuspendThe; "Can't suspend the session because the t"...
0x18001a7f6  mov     [rsp+70h+var_48], rax
0x18001a7fb  mov     [rsp+70h+var_50], 417h
0x18001a803  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001a80a  lea     r8, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001a811  mov     edx, 80070032h
0x18001a816  mov     ecx, 2
0x18001a81b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001a820  mov     eax, 80070032h
0x18001a825  jmp     loc_18001AE90
0x18001a82a  mov     [rbp+var_18], 0
0x18001a832  lea     r14, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x18001a839  mov     [rbp+var_20], r14
0x18001a83d  lea     rcx, [rbp+var_20]
0x18001a841  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18001a846  mov     rbx, rax
0x18001a849  lea     rdx, aResetsession; "ResetSession"
0x18001a850  lea     rcx, [rbp+arg_0]
0x18001a854  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001a859  nop
0x18001a85a  mov     rdx, rbx
0x18001a85d  lea     rcx, [rbp+arg_0]
0x18001a861  call    ?Create@SerializeDocument@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeDocument::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeDocument * *)
0x18001a866  mov     ebx, eax
0x18001a868  mov     rcx, [rbp+arg_0]
0x18001a86c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a870  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a875  test    ebx, ebx
0x18001a877  jns     short loc_18001A8BC
0x18001a879  lea     rax, aFailedToCreate_40; "Failed to create empty document"
0x18001a880  mov     [rsp+70h+var_48], rax
0x18001a885  mov     [rsp+70h+var_50], 41Dh
0x18001a88d  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001a894  lea     r8, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001a89b  mov     edx, ebx
0x18001a89d  mov     ecx, 2
0x18001a8a2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001a8a7  nop
0x18001a8a8  mov     [rbp+var_20], r14
0x18001a8ac  lea     rcx, [rbp+var_20]
0x18001a8b0  call    ?Release@?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(void)
0x18001a8b5  mov     eax, ebx
0x18001a8b7  jmp     loc_18001AE90
0x18001a8bc  mov     [rbp+var_28], 0
0x18001a8c4  lea     r13, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x18001a8cb  mov     [rbp+var_30], r13
0x18001a8cf  mov     rax, [rbp+var_20]
0x18001a8d3  lea     rcx, [rbp+var_20]
0x18001a8d7  mov     rax, [rax+18h]
0x18001a8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8e0  mov     rbx, rax
0x18001a8e3  mov     rcx, [rbp+var_30]
0x18001a8e7  mov     rax, [rcx+8]
0x18001a8eb  lea     rcx, [rbp+var_30]
0x18001a8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f4  mov     rdx, rax; struct PushButtonReset::SerializeNode **
0x18001a8f7  mov     rcx, rbx; this
0x18001a8fa  call    ?GetRoot@SerializeDocument@PushButtonReset@@QEAAJPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeDocument::GetRoot(PushButtonReset::SerializeNode * *)
0x18001a8ff  mov     ebx, eax
0x18001a901  test    eax, eax
0x18001a903  jns     short loc_18001A946
0x18001a905  lea     rax, aFailedToGetRoo_1; "Failed to get root node"
0x18001a90c  mov     [rsp+70h+var_48], rax
0x18001a911  mov     [rsp+70h+var_50], 421h
0x18001a919  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001a920  lea     r8, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001a927  mov     edx, ebx
0x18001a929  mov     ecx, 2
0x18001a92e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001a933  nop
0x18001a934  mov     [rbp+var_30], r13
0x18001a938  lea     rcx, [rbp+var_30]
0x18001a93c  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18001a941  jmp     loc_18001A8A8
0x18001a946  mov     rax, [rbp+var_30]
0x18001a94a  lea     rcx, [rbp+var_30]
0x18001a94e  mov     rax, [rax+18h]
0x18001a952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a957  mov     rbx, rax
0x18001a95a  lea     rdx, aMajorversion; "MajorVersion"
0x18001a961  lea     rcx, [rbp+arg_0]
0x18001a965  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001a96a  nop
0x18001a96b  mov     r8d, 1
0x18001a971  lea     rdx, [rbp+arg_0]
0x18001a975  mov     rcx, rbx
0x18001a978  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong)
0x18001a97d  mov     ebx, eax
0x18001a97f  mov     rcx, [rbp+arg_0]
0x18001a983  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a987  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a98c  test    ebx, ebx
0x18001a98e  jns     short loc_18001A9A9
0x18001a990  lea     rax, aFailedToSaveMa; "Failed to save MajorVersion"
0x18001a997  mov     [rsp+70h+var_48], rax
0x18001a99c  mov     [rsp+70h+var_50], 424h
0x18001a9a4  jmp     loc_18001A919
0x18001a9a9  mov     rax, [rbp+var_30]
0x18001a9ad  lea     rcx, [rbp+var_30]
0x18001a9b1  mov     rax, [rax+18h]
0x18001a9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ba  mov     rbx, rax
0x18001a9bd  lea     rdx, aMinorversion; "MinorVersion"
0x18001a9c4  lea     rcx, [rbp+arg_0]
0x18001a9c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001a9cd  nop
0x18001a9ce  mov     r8d, 4
0x18001a9d4  lea     rdx, [rbp+arg_0]
0x18001a9d8  mov     rcx, rbx
0x18001a9db  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong)
0x18001a9e0  mov     ebx, eax
0x18001a9e2  mov     rcx, [rbp+arg_0]
0x18001a9e6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a9ea  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a9ef  test    ebx, ebx
0x18001a9f1  jns     short loc_18001AA0C
0x18001a9f3  lea     rax, aFailedToSaveMi; "Failed to save MinorVersion"
0x18001a9fa  mov     [rsp+70h+var_48], rax
0x18001a9ff  mov     [rsp+70h+var_50], 427h
0x18001aa07  jmp     loc_18001A919
0x18001aa0c  mov     rax, [rbp+var_30]
0x18001aa10  lea     rcx, [rbp+var_30]
0x18001aa14  mov     rax, [rax+18h]
0x18001aa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa1d  mov     rbx, rax
0x18001aa20  lea     rdx, aTargetroot; "TargetRoot"
0x18001aa27  lea     rcx, [rbp+arg_0]
0x18001aa2b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001aa30  nop
0x18001aa31  mov     r8, r15
0x18001aa34  lea     rdx, [rbp+arg_0]
0x18001aa38  mov     rcx, rbx
0x18001aa3b  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001aa40  mov     ebx, eax
0x18001aa42  mov     rcx, [rbp+arg_0]
0x18001aa46  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001aa4a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aa4f  test    ebx, ebx
0x18001aa51  jns     short loc_18001AA6C
0x18001aa53  lea     rax, aFailedToSaveTa_1; "Failed to save Target Root"
0x18001aa5a  mov     [rsp+70h+var_48], rax
0x18001aa5f  mov     [rsp+70h+var_50], 42Ah
0x18001aa67  jmp     loc_18001A919
0x18001aa6c  mov     rax, [rbp+var_30]
0x18001aa70  lea     rcx, [rbp+var_30]
0x18001aa74  mov     rax, [rax+18h]
0x18001aa78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa7d  mov     rdi, rax
0x18001aa80  mov     bl, [rsi+41h]
0x18001aa83  lea     rdx, aScheduled; "Scheduled"
0x18001aa8a  lea     rcx, [rbp+arg_0]
0x18001aa8e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001aa93  nop
0x18001aa94  mov     r8b, bl
0x18001aa97  lea     rdx, [rbp+arg_0]
0x18001aa9b  mov     rcx, rdi
0x18001aa9e  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x18001aaa3  mov     ebx, eax
0x18001aaa5  mov     rcx, [rbp+arg_0]
0x18001aaa9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001aaad  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aab2  test    ebx, ebx
0x18001aab4  jns     short loc_18001AACF
0x18001aab6  lea     rax, aFailedToSaveSc_0; "Failed to save Scheduled State"
0x18001aabd  mov     [rsp+70h+var_48], rax
0x18001aac2  mov     [rsp+70h+var_50], 42Dh
0x18001aaca  jmp     loc_18001A919
0x18001aacf  mov     rax, [rbp+var_30]
0x18001aad3  lea     rcx, [rbp+var_30]
0x18001aad7  mov     rax, [rax+18h]
0x18001aadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aae0  mov     rdi, rax
0x18001aae3  mov     bl, [rsi+42h]
0x18001aae6  lea     rdx, aStaged; "Staged"
0x18001aaed  lea     rcx, [rbp+arg_0]
0x18001aaf1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001aaf6  nop
0x18001aaf7  mov     r8b, bl
0x18001aafa  lea     rdx, [rbp+arg_0]
0x18001aafe  mov     rcx, rdi
0x18001ab01  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x18001ab06  mov     ebx, eax
0x18001ab08  mov     rcx, [rbp+arg_0]
0x18001ab0c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ab10  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ab15  test    ebx, ebx
0x18001ab17  jns     short loc_18001AB32
0x18001ab19  lea     rax, aFailedToSaveSt_0; "Failed to save Staged State"
0x18001ab20  mov     [rsp+70h+var_48], rax
0x18001ab25  mov     [rsp+70h+var_50], 430h
0x18001ab2d  jmp     loc_18001A919
0x18001ab32  lea     r14, [rsi+28h]
0x18001ab36  mov     [rbp+arg_0], 0
0x18001ab3e  mov     rax, [r14]
0x18001ab41  lea     rdx, [rbp+arg_0]
0x18001ab45  mov     rcx, r14
0x18001ab48  mov     rax, [rax+40h]
0x18001ab4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab51  test    al, al
0x18001ab53  jz      loc_18001AC75
0x18001ab59  mov     [rbp+var_8], 0
0x18001ab61  mov     [rbp+var_10], r13
0x18001ab65  mov     rax, [rbp+var_30]
0x18001ab69  lea     rcx, [rbp+var_30]
0x18001ab6d  mov     rax, [rax+18h]
0x18001ab71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab76  mov     rdi, rax
0x18001ab79  mov     rcx, [rbp+var_10]
0x18001ab7d  mov     rax, [rcx+8]
0x18001ab81  lea     rcx, [rbp+var_10]
0x18001ab85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab8a  mov     rbx, rax
0x18001ab8d  lea     rdx, aExecutor; "Executor"
0x18001ab94  lea     rcx, [rbp+arg_0]
0x18001ab98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001ab9d  nop
0x18001ab9e  mov     r8, rbx
0x18001aba1  lea     rdx, [rbp+arg_0]
0x18001aba5  mov     rcx, rdi
0x18001aba8  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18001abad  mov     ebx, eax
0x18001abaf  mov     rcx, [rbp+arg_0]
0x18001abb3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001abb7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001abbc  test    ebx, ebx
0x18001abbe  jns     short loc_18001AC1B
0x18001abc0  lea     rax, aFailedToCreate_5; "Failed to create Executor node"
0x18001abc7  mov     [rsp+70h+var_48], rax
0x18001abcc  mov     [rsp+70h+var_50], 436h
0x18001abd4  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001abdb  lea     r8, aWinreagentWinr_3; "WinREAgent::WinREServicingManager::Inte"...
0x18001abe2  mov     edx, ebx
0x18001abe4  mov     ecx, 2
0x18001abe9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001abee  nop
0x18001abef  mov     [rbp+var_10], r13
0x18001abf3  lea     rcx, [rbp+var_10]
0x18001abf7  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18001abfc  nop
0x18001abfd  mov     [rbp+var_30], r13
0x18001ac01  lea     rcx, [rbp+var_30]
0x18001ac05  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18001ac0a  nop
0x18001ac0b  lea     rax, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x18001ac12  mov     [rbp+var_20], rax
0x18001ac16  jmp     loc_18001A8AC
0x18001ac1b  mov     rax, [rbp+var_10]
0x18001ac1f  lea     rcx, [rbp+var_10]
  ... truncated ...
```
