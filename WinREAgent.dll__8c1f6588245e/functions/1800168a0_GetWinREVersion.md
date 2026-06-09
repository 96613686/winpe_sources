# GetWinREVersion

- ea: `0x1800168a0`
- end: `0x180016f45`
- name: `GetWinREVersion`
- size: `1701`
- prototype: `__int64 __fastcall(union _FOUR_PART_VERSION *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x1800089d0`
- `0x18000d570`
- `0x18000d640`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18001586c`
- `0x1800158bc`
- `0x180015f00`
- `0x180016440`
- `0x180016490`
- `0x180016638`
- `0x1800168a0`
- `0x18001f194`
- `0x18002da30`
- `0x18002e384`
- `0x18002e448`
- `0x18003717c`
- `0x180037344`
- `0x180050488`
- `0x1800536bc`
- `0x180053afc`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016ab8`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016ab8`
- `KERNEL32!GetLastError` at `0x180016ac2`
- `KERNEL32!GetLastError` at `0x180016b04`
- `KERNEL32!GetLastError` at `0x180016ac2`
- `KERNEL32!GetLastError` at `0x180016b04`
- `DismApi!DismGetImageInfo` at `0x180016dd5`
- `DismApi!DismGetImageInfo` at `0x180016dd5`

## string_xrefs

- `0x180016d63`: `Failed to open DISM session`
- `0x180016ad6`: `Failed to get system Windows directory`
- `0x18001693e`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x18001699e`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016ae4`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016b6b`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016be8`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016c7b`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016d01`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016d71`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016dfe`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016b5d`: `Failed to build log path`
- `0x180016c6d`: `Failed to read WinRE configuration`
- `0x180016cf3`: `Failed to get winre path`
- `0x180016930`: `Failed to create telemetry session`
- `0x180016952`: `WinREAgent::GetWinREVersion`
- `0x1800169a5`: `WinREAgent::GetWinREVersion`
- `0x1800169f6`: `WinREAgent::GetWinREVersion`
- `0x180016a81`: `WinREAgent::GetWinREVersion`
- `0x180016af8`: `WinREAgent::GetWinREVersion`
- `0x180016b72`: `WinREAgent::GetWinREVersion`
- `0x180016bef`: `WinREAgent::GetWinREVersion`
- `0x180016c82`: `WinREAgent::GetWinREVersion`
- `0x180016d08`: `WinREAgent::GetWinREVersion`
- `0x180016d78`: `WinREAgent::GetWinREVersion`
- `0x180016e05`: `WinREAgent::GetWinREVersion`
- `0x180016bc0`: `Enter WinREAgent::GetWinREVersion`
- `0x180016f2b`: `Exit WinREAgent::GetWinREVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetWinREVersion(union _FOUR_PART_VERSION *a1)
{
  struct WinREAgent::TelemetrySession **v2; // rax
  int v3; // eax
  __int64 v4; // rbx
  struct WinREAgent::TelemetrySession *v5; // rax
  int WinREVersionInternal; // edi
  __int64 v7; // rbx
  __int64 v8; // rcx
  signed int LastError; // eax
  signed int v10; // eax
  signed int LogDir; // ebx
  struct PushButtonReset::WindowsRE::Config **v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int16 v18; // cx
  __int64 v19; // rax
  __int16 v20; // cx
  __int64 v21; // rax
  __int16 v22; // cx
  __int64 v23; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v33[3]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  v28[1] = 0;
  v28[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry>::GetImpl'::`2'::impl) )
  {
    v2 = (struct WinREAgent::TelemetrySession **)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 8LL))(v28);
    v3 = WinREAgent::TelemetrySession::Create(0, v2);
    if ( v3 >= 0 )
    {
      if ( !(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 32LL))(v28) )
        PushButtonReset::Logging::TraceErr(
          1,
          2147942414LL,
          "WinREAgent::GetWinREVersion",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
          270,
          L"Failed to allocate telemetry session");
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v3,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        264,
        L"Failed to create telemetry session");
      (*(void (__fastcall **)(_QWORD *, _QWORD))(v28[0] + 48LL))(v28, 0);
    }
    v25 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v28[0] + 64LL))(v28, &v25) )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v25,
        "WinREAgent::GetWinREVersion");
      WinREAgent::TelemetrySession::TraceEnterAPI(v4, &v25);
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    }
    v5 = (struct WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 32LL))(v28);
    WinREVersionInternal = GetWinREVersionInternal(v5, a1);
    v25 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *))(v28[0] + 64LL))(v28, &v25) )
      goto LABEL_34;
    v7 = (*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v25,
      "WinREAgent::GetWinREVersion");
    WinREAgent::TelemetrySession::TraceLeaveAPI(v7, &v25, (unsigned int)WinREVersionInternal);
    v8 = v25;
LABEL_33:
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
LABEL_34:
    LogDir = WinREVersionInternal;
    goto LABEL_35;
  }
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v27,
      L"%c:\\",
      Buffer[0]);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
    LogDir = WinREAgent::WorkDir::GetLogDir(&v27, &v26);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        290,
        L"Failed to build log path");
LABEL_17:
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      goto LABEL_35;
    }
    v24[0] = 0;
    v31[1] = PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &,bool>(
               &v26,
               v24);
    PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::GetWinREVersion");
    if ( !a1 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942487LL,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        298,
        L"Invalid argument");
      v31[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v31);
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      LogDir = -2147024809;
      goto LABEL_35;
    }
    v30[1] = 0;
    v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    v12 = (struct PushButtonReset::WindowsRE::Config **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v30);
    LogDir = PushButtonReset::WindowsRE::OpenConfig(v12);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        304,
        L"Failed to read WinRE configuration");
LABEL_22:
      v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v30);
      v31[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v31);
      goto LABEL_17;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
    v13 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
    LogDir = PushButtonReset::WindowsRE::Config::GetCurrentWimPath(v13, &v25);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        308,
        L"Failed to get winre path");
LABEL_25:
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
      goto LABEL_22;
    }
    v33[1] = 0;
    v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    v14 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v33);
    LogDir = PushButtonReset::DismAutoShutdown::Create(&v26, v14);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        313,
        L"Failed to open DISM session");
      v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v33);
      goto LABEL_25;
    }
    v29[1] = 0;
    v29[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
    v32 = 0;
    v15 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v29);
    v16 = v25;
    WinREVersionInternal = DismGetImageInfo(v25, v15, &v32);
    if ( WinREVersionInternal >= 0 )
    {
      if ( v32 )
      {
        v18 = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 32LL))(v29) + 84);
        v19 = v29[0];
        *((_WORD *)a1 + 3) = v18;
        v20 = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v19 + 32))(v29) + 88);
        v21 = v29[0];
        *((_WORD *)a1 + 2) = v20;
        v22 = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v21 + 32))(v29) + 92);
        v23 = v29[0];
        *((_WORD *)a1 + 1) = v22;
        *(_WORD *)a1 = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v23 + 32))(v29) + 96);
        PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::GetWinREVersion");
        goto LABEL_32;
      }
      WinREVersionInternal = -2147467259;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)WinREVersionInternal,
      "WinREAgent::GetWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
      326,
      L"Failed to get image info");
LABEL_32:
    v29[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
    RAII::CAutoDismDelete<_DismPackageInfo *>::Release(v29);
    v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v33);
    ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
    v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v30);
    v31[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v31);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    v8 = v27;
    goto LABEL_33;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LastError,
    "WinREAgent::GetWinREVersion",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
    282,
    L"Failed to get system Windows directory");
  v10 = GetLastError();
  LogDir = v10;
  if ( v10 > 0 )
    LogDir = (unsigned __int16)v10 | 0x80070000;
LABEL_35:
  v28[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(v28);
  return (unsigned int)LogDir;
}

```

## disassembly

```asm
0x1800168a0  mov     [rsp-8+arg_8], rbx
0x1800168a5  mov     [rsp-8+arg_10], rsi
0x1800168aa  push    rbp
0x1800168ab  push    rdi
0x1800168ac  push    r12
0x1800168ae  push    r13
0x1800168b0  push    r15
0x1800168b2  lea     rbp, [rsp-1D0h]
0x1800168ba  sub     rsp, 2D0h
0x1800168c1  mov     rax, cs:__security_cookie
0x1800168c8  xor     rax, rsp
0x1800168cb  mov     [rbp+1F0h+var_30], rax
0x1800168d2  mov     rsi, rcx
0x1800168d5  xor     edx, edx; Val
0x1800168d7  lea     rcx, [rbp+1F0h+Buffer]; void *
0x1800168db  mov     r8d, 20Ah; Size
0x1800168e1  call    memset_0
0x1800168e6  lea     rax, ??_7?$CAutoPbrDelete@PEAVTelemetrySession@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable'
0x1800168ed  mov     [rsp+2F0h+var_298], 0
0x1800168f6  mov     [rsp+2F0h+var_2A0], rax
0x1800168fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry>::GetImpl(void)'::`2'::impl
0x180016902  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinREVersionTelemetry>::__private_IsEnabled(void)
0x180016907  test    al, al
0x180016909  jz      loc_180016AAF
0x18001690f  mov     rax, [rsp+2F0h+var_2A0]
0x180016914  lea     rcx, [rsp+2F0h+var_2A0]
0x180016919  mov     rax, [rax+8]
0x18001691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016922  mov     rdx, rax; struct WinREAgent::TelemetrySession **
0x180016925  xor     ecx, ecx; char *
0x180016927  call    ?Create@TelemetrySession@WinREAgent@@SAJPEBDPEAPEAV12@@Z; WinREAgent::TelemetrySession::Create(char const *,WinREAgent::TelemetrySession * *)
0x18001692c  test    eax, eax
0x18001692e  jns     short loc_180016975
0x180016930  lea     rcx, aFailedToCreate_35; "Failed to create telemetry session"
0x180016937  mov     edx, eax
0x180016939  mov     [rsp+2F0h+var_2C8], rcx
0x18001693e  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016945  mov     ecx, 1
0x18001694a  mov     [rsp+2F0h+var_2D0], 108h
0x180016952  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016959  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001695e  mov     rax, [rsp+2F0h+var_2A0]
0x180016963  lea     rcx, [rsp+2F0h+var_2A0]
0x180016968  xor     edx, edx
0x18001696a  mov     rax, [rax+30h]
0x18001696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016973  jmp     short loc_1800169BE
0x180016975  mov     rax, [rsp+2F0h+var_2A0]
0x18001697a  lea     rcx, [rsp+2F0h+var_2A0]
0x18001697f  mov     rax, [rax+20h]
0x180016983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016988  test    rax, rax
0x18001698b  jnz     short loc_1800169BE
0x18001698d  lea     rax, aFailedToAlloca_24; "Failed to allocate telemetry session"
0x180016994  mov     edx, 8007000Eh
0x180016999  mov     [rsp+2F0h+var_2C8], rax
0x18001699e  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800169a5  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x1800169ac  mov     [rsp+2F0h+var_2D0], 10Eh
0x1800169b4  mov     ecx, 1
0x1800169b9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800169be  mov     rax, [rsp+2F0h+var_2A0]
0x1800169c3  lea     rdx, [rsp+2F0h+var_2B8]
0x1800169c8  lea     rcx, [rsp+2F0h+var_2A0]
0x1800169cd  mov     [rsp+2F0h+var_2B8], 0
0x1800169d6  mov     rax, [rax+40h]
0x1800169da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169df  test    al, al
0x1800169e1  jz      short loc_180016A25
0x1800169e3  mov     rax, [rsp+2F0h+var_2A0]
0x1800169e8  lea     rcx, [rsp+2F0h+var_2A0]
0x1800169ed  mov     rax, [rax+18h]
0x1800169f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f6  lea     rdx, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x1800169fd  mov     rbx, rax
0x180016a00  lea     rcx, [rsp+2F0h+var_2B8]
0x180016a05  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180016a0a  lea     rdx, [rsp+2F0h+var_2B8]
0x180016a0f  mov     rcx, rbx
0x180016a12  call    ?TraceEnterAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceEnterAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180016a17  mov     rcx, [rsp+2F0h+var_2B8]
0x180016a1c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016a20  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016a25  mov     rax, [rsp+2F0h+var_2A0]
0x180016a2a  lea     rcx, [rsp+2F0h+var_2A0]
0x180016a2f  mov     rax, [rax+20h]
0x180016a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a38  mov     rcx, rax; this
0x180016a3b  mov     rdx, rsi; union _FOUR_PART_VERSION *
0x180016a3e  call    ?GetWinREVersionInternal@@YAJPEAVTelemetrySession@WinREAgent@@PEAT_FOUR_PART_VERSION@@@Z; GetWinREVersionInternal(WinREAgent::TelemetrySession *,_FOUR_PART_VERSION *)
0x180016a43  mov     rcx, [rsp+2F0h+var_2A0]
0x180016a48  lea     rdx, [rsp+2F0h+var_2B8]
0x180016a4d  mov     edi, eax
0x180016a4f  mov     [rsp+2F0h+var_2B8], 0
0x180016a58  mov     rax, [rcx+40h]
0x180016a5c  lea     rcx, [rsp+2F0h+var_2A0]
0x180016a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a66  test    al, al
0x180016a68  jz      loc_180016E82
0x180016a6e  mov     rcx, [rsp+2F0h+var_2A0]
0x180016a73  mov     rax, [rcx+18h]
0x180016a77  lea     rcx, [rsp+2F0h+var_2A0]
0x180016a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a81  lea     rdx, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016a88  mov     rbx, rax
0x180016a8b  lea     rcx, [rsp+2F0h+var_2B8]
0x180016a90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180016a95  mov     r8d, edi
0x180016a98  lea     rdx, [rsp+2F0h+var_2B8]
0x180016a9d  mov     rcx, rbx
0x180016aa0  call    ?TraceLeaveAPI@TelemetrySession@WinREAgent@@QEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceLeaveAPI(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x180016aa5  mov     rcx, [rsp+2F0h+var_2B8]
0x180016aaa  jmp     loc_180016E79
0x180016aaf  mov     edx, 104h; uSize
0x180016ab4  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x180016ab8  call    cs:__imp_GetSystemWindowsDirectoryW
0x180016abe  test    eax, eax
0x180016ac0  jnz     short loc_180016B1E
0x180016ac2  call    cs:__imp_GetLastError
0x180016ac8  mov     edi, 80070000h
0x180016acd  test    eax, eax
0x180016acf  jle     short loc_180016AD6
0x180016ad1  movzx   eax, ax
0x180016ad4  or      eax, edi
0x180016ad6  lea     rcx, aFailedToGetSys_0; "Failed to get system Windows directory"
0x180016add  mov     edx, eax
0x180016adf  mov     [rsp+2F0h+var_2C8], rcx
0x180016ae4  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016aeb  mov     ecx, 2
0x180016af0  mov     [rsp+2F0h+var_2D0], 11Ah
0x180016af8  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016aff  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016b04  call    cs:__imp_GetLastError
0x180016b0a  mov     ebx, eax
0x180016b0c  test    eax, eax
0x180016b0e  jle     loc_180016E84
0x180016b14  movzx   ebx, ax
0x180016b17  or      ebx, edi
0x180016b19  jmp     loc_180016E84
0x180016b1e  lea     rcx, [rsp+2F0h+var_2A8]
0x180016b23  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016b28  movzx   r8d, [rbp+1F0h+Buffer]
0x180016b2d  lea     rdx, aC; "%c:\\"
0x180016b34  lea     rcx, [rsp+2F0h+var_2A8]
0x180016b39  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180016b3e  lea     rcx, [rsp+2F0h+var_2B0]
0x180016b43  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016b48  lea     rdx, [rsp+2F0h+var_2B0]
0x180016b4d  lea     rcx, [rsp+2F0h+var_2A8]
0x180016b52  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180016b57  mov     ebx, eax
0x180016b59  test    eax, eax
0x180016b5b  jns     short loc_180016BAC
0x180016b5d  lea     rax, aFailedToBuildL; "Failed to build log path"
0x180016b64  mov     edx, ebx
0x180016b66  mov     [rsp+2F0h+var_2C8], rax
0x180016b6b  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016b72  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016b79  mov     [rsp+2F0h+var_2D0], 122h
0x180016b81  mov     ecx, 2
0x180016b86  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016b8b  mov     rcx, [rsp+2F0h+var_2B0]
0x180016b90  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016b94  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016b99  mov     rcx, [rsp+2F0h+var_2A8]
0x180016b9e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016ba2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016ba7  jmp     loc_180016E84
0x180016bac  lea     rdx, [rsp+2F0h+var_2C0]
0x180016bb1  mov     [rsp+2F0h+var_2C0], 0
0x180016bb6  lea     rcx, [rsp+2F0h+var_2B0]
0x180016bbb  call    ??$PbrNew@VLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@@YAPEAVLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEA_N@Z; PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &&)
0x180016bc0  lea     rdx, aEnterWinreagen_6; "Enter WinREAgent::GetWinREVersion"
0x180016bc7  mov     [rbp+1F0h+var_268], rax
0x180016bcb  xor     ecx, ecx
0x180016bcd  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180016bd2  test    rsi, rsi
0x180016bd5  jnz     short loc_180016C40
0x180016bd7  lea     rax, aInvalidArgumen; "Invalid argument"
0x180016bde  mov     edx, 80070057h
0x180016be3  mov     [rsp+2F0h+var_2C8], rax
0x180016be8  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016bef  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016bf6  mov     [rsp+2F0h+var_2D0], 12Ah
0x180016bfe  lea     ecx, [rsi+2]
0x180016c01  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016c06  lea     rax, ??_7?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable'
0x180016c0d  lea     rcx, [rbp+1F0h+var_270]
0x180016c11  mov     [rbp+1F0h+var_270], rax
0x180016c15  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180016c1a  mov     rcx, [rsp+2F0h+var_2B0]
0x180016c1f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016c23  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016c28  mov     rcx, [rsp+2F0h+var_2A8]
0x180016c2d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016c31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016c36  mov     ebx, 80070057h
0x180016c3b  jmp     loc_180016E84
0x180016c40  lea     r15, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x180016c47  mov     [rsp+2F0h+var_278], 0
0x180016c50  lea     rcx, [rsp+2F0h+var_280]
0x180016c55  mov     [rsp+2F0h+var_280], r15
0x180016c5a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180016c5f  mov     rcx, rax; struct PushButtonReset::WindowsRE::Config **
0x180016c62  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x180016c67  mov     ebx, eax
0x180016c69  test    eax, eax
0x180016c6b  jns     short loc_180016CC3
0x180016c6d  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x180016c74  mov     edx, ebx
0x180016c76  mov     [rsp+2F0h+var_2C8], rax
0x180016c7b  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016c82  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016c89  mov     [rsp+2F0h+var_2D0], 130h
0x180016c91  mov     ecx, 2
0x180016c96  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016c9b  lea     rcx, [rsp+2F0h+var_280]
0x180016ca0  mov     [rsp+2F0h+var_280], r15
0x180016ca5  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180016caa  lea     rax, ??_7?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable'
0x180016cb1  lea     rcx, [rbp+1F0h+var_270]
0x180016cb5  mov     [rbp+1F0h+var_270], rax
0x180016cb9  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180016cbe  jmp     loc_180016B8B
0x180016cc3  lea     rcx, [rsp+2F0h+var_2B8]
0x180016cc8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016ccd  mov     rax, [rsp+2F0h+var_280]
0x180016cd2  lea     rcx, [rsp+2F0h+var_280]
0x180016cd7  mov     rax, [rax+18h]
0x180016cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce0  lea     rdx, [rsp+2F0h+var_2B8]
0x180016ce5  mov     rcx, rax
0x180016ce8  call    ?GetCurrentWimPath@Config@WindowsRE@PushButtonReset@@QEAAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WindowsRE::Config::GetCurrentWimPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180016ced  mov     ebx, eax
0x180016cef  test    eax, eax
0x180016cf1  jns     short loc_180016D34
0x180016cf3  lea     rax, aFailedToGetWin_0; "Failed to get winre path"
0x180016cfa  mov     edx, ebx
0x180016cfc  mov     [rsp+2F0h+var_2C8], rax
0x180016d01  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016d08  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016d0f  mov     [rsp+2F0h+var_2D0], 134h
0x180016d17  mov     ecx, 2
0x180016d1c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016d21  mov     rcx, [rsp+2F0h+var_2B8]
0x180016d26  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016d2a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016d2f  jmp     loc_180016C9B
0x180016d34  lea     r12, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x180016d3b  mov     [rbp+1F0h+var_250], 0
0x180016d43  lea     rcx, [rbp+1F0h+var_258]
0x180016d47  mov     [rbp+1F0h+var_258], r12
0x180016d4b  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180016d50  mov     rdx, rax
0x180016d53  lea     rcx, [rsp+2F0h+var_2B0]
0x180016d58  call    ?Create@DismAutoShutdown@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::DismAutoShutdown::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DismAutoShutdown * *)
0x180016d5d  mov     ebx, eax
0x180016d5f  test    eax, eax
0x180016d61  jns     short loc_180016DA0
0x180016d63  lea     rax, aFailedToOpenDi_1; "Failed to open DISM session"
0x180016d6a  mov     edx, ebx
0x180016d6c  mov     [rsp+2F0h+var_2C8], rax
0x180016d71  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016d78  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016d7f  mov     [rsp+2F0h+var_2D0], 139h
0x180016d87  mov     ecx, 2
0x180016d8c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016d91  lea     rcx, [rbp+1F0h+var_258]
0x180016d95  mov     [rbp+1F0h+var_258], r12
0x180016d99  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x180016d9e  jmp     short loc_180016D21
0x180016da0  lea     r13, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180016da7  mov     [rsp+2F0h+var_288], 0
0x180016db0  lea     rcx, [rsp+2F0h+var_290]
0x180016db5  mov     [rsp+2F0h+var_290], r13
0x180016dba  mov     [rbp+1F0h+var_260], 0
0x180016dc1  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180016dc6  mov     rbx, [rsp+2F0h+var_2B8]
0x180016dcb  lea     r8, [rbp+1F0h+var_260]
0x180016dcf  mov     rcx, rbx
0x180016dd2  mov     rdx, rax
0x180016dd5  call    cs:__imp_DismGetImageInfo
0x180016ddb  mov     edi, eax
0x180016ddd  test    eax, eax
0x180016ddf  js      short loc_180016DF0
0x180016de1  cmp     [rbp+1F0h+var_260], 0
0x180016de5  jnz     loc_180016EC7
0x180016deb  mov     edi, 80004005h
0x180016df0  lea     rax, aFailedToGetIma_0; "Failed to get image info"
0x180016df7  mov     edx, edi
0x180016df9  mov     [rsp+2F0h+var_2C8], rax
0x180016dfe  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016e05  lea     r8, aWinreagentGetw; "WinREAgent::GetWinREVersion"
0x180016e0c  mov     [rsp+2F0h+var_2D0], 146h
0x180016e14  mov     ecx, 2
0x180016e19  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016e1e  lea     rcx, [rsp+2F0h+var_290]
0x180016e23  mov     [rsp+2F0h+var_290], r13
0x180016e28  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180016e2d  lea     rcx, [rbp+1F0h+var_258]
  ... truncated ...
```
