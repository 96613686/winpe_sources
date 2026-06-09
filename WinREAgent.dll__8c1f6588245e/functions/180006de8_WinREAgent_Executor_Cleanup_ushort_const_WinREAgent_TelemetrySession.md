# WinREAgent::Executor::Cleanup(ushort const *,WinREAgent::TelemetrySession *)

- ea: `0x180006de8`
- end: `0x1800074b1`
- name: `?Cleanup@Executor@WinREAgent@@QEAAJPEBGPEAVTelemetrySession@2@@Z`
- size: `1737`
- prototype: `int(WinREAgent::Executor *__hidden this, const unsigned __int16 *, struct WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018820`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180006de8`
- `0x18000b948`
- `0x18000d92c`
- `0x18001ed24`
- `0x18001f228`
- `0x18001f358`
- `0x18002dee0`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004aabc`
- `0x18004c2b0`
- `0x18004c418`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x18004d7a0`
- `0x18006f010`

## string_xrefs

- `0x180006eab`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006eea`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000737b`: `Failed to get WinREAgent root directory`
- `0x180007270`: `update.wim`
- `0x180006e21`: `External backup directory [%s]`
- `0x180006e97`: `Failed to get suspend file path`
- `0x180006eb2`: `WinREAgent::Executor::Cleanup`
- `0x180006ef1`: `WinREAgent::Executor::Cleanup`
- `0x180006f81`: `Move backup of WinRE to [%s]`
- `0x180006ffb`: `Failed to move [%s] to [%s]`
- `0x180007031`: `Backup directory [%s] doesn't exist`
- `0x180007065`: `Cleanup Backup directory`
- `0x1800070a6`: `Failed to cleanup Backup directory`
- `0x1800070ec`: `Cleanup Updated wim`
- `0x18000712d`: `Failed to cleanup updated wim`
- `0x180007173`: `Cleanup Scratch directory`
- `0x180007213`: `Failed to construct WinRE parent directory path`
- `0x1800072a5`: `Failed to build path for updated wim new location`
- `0x1800073ca`: `Cleanup WinREAgent work directory [%s]`
- `0x1800073fa`: `Failed to cleanup work directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::Executor::Cleanup(
        WinREAgent::Executor *this,
        const unsigned __int16 *a2,
        struct WinREAgent::TelemetrySession *a3)
{
  const wchar_t *v6; // r8
  unsigned int SuspendFile; // esi
  ATL::CStringData *v8; // rcx
  ATL::CStringData *v9; // rcx
  int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // esi
  _QWORD *v14; // rcx
  const WCHAR *v15; // rdx
  int v16; // eax
  unsigned int v17; // esi
  _QWORD *v18; // rcx
  int v19; // eax
  unsigned int v20; // esi
  _QWORD *v21; // rcx
  int v22; // eax
  unsigned int v23; // esi
  int Directory; // ebx
  int v26; // eax
  unsigned int v27; // esi
  LPCWSTR v28; // rbx
  const WCHAR *v29; // rdx
  int v30; // eax
  LPCWSTR v31; // rbx
  unsigned __int16 *v32; // rbx
  __int64 v33; // [rsp+40h] [rbp-18h] BYREF
  __int64 v34; // [rsp+48h] [rbp-10h]
  unsigned __int16 *v35; // [rsp+A0h] [rbp+48h] BYREF
  LPCWSTR v36; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v38; // [rsp+B8h] [rbp+60h] BYREF

  PushButtonReset::Logging::Trace(0, L"Start cleanup of execution");
  v6 = L"NULL";
  if ( a2 )
    v6 = a2;
  PushButtonReset::Logging::Trace(0, L"External backup directory [%s]", v6);
  if ( a3 )
    WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"CleanupStart");
  (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 52) + 48LL))((char *)this + 416, 0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v35);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v37);
  v34 = (__int64)this + 368;
  SuspendFile = WinREAgent::WorkDir::GetSuspendFile((char *)this + 368, &v37);
  if ( (SuspendFile & 0x80000000) == 0 )
  {
    if ( (unsigned __int8)PushButtonReset::File::Exists(&v37)
      && (PushButtonReset::Logging::Trace(0, L"Cleanup suspend file"),
          v10 = PushButtonReset::File::Delete(&v37),
          SuspendFile = v10,
          v10 < 0) )
    {
      v11 = v37;
      LogCleanupFailure(&v35, v37, (unsigned int)v10);
      PushButtonReset::Logging::TraceErr(
        1,
        SuspendFile,
        "WinREAgent::Executor::Cleanup",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        2073,
        L"Failed to cleanup suspend file");
      SuspendFile = 0;
    }
    else
    {
      v11 = v37;
    }
    v12 = *((_QWORD *)this + 51);
    if ( v12 )
    {
      *(_QWORD *)(v12 + 448) = 0;
      if ( a2 )
      {
        PushButtonReset::Logging::Trace(0, L"Move backup of WinRE to [%s]", a2);
        if ( (unsigned __int8)PushButtonReset::Directory::Exists(*((_QWORD *)this + 51) + 248LL) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v36,
            (__int64)a2);
          v13 = PushButtonReset::Directory::Copy((LPCWSTR *)(*((_QWORD *)this + 51) + 248LL), &v36, 0, 1);
          ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
          if ( v13 < 0 )
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v13,
              "WinREAgent::Executor::Cleanup",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2096,
              L"Failed to move [%s] to [%s]",
              *(_QWORD *)(*((_QWORD *)this + 51) + 248LL),
              a2);
        }
        else
        {
          PushButtonReset::Logging::Trace(
            1,
            L"Backup directory [%s] doesn't exist",
            *(_QWORD *)(*((_QWORD *)this + 51) + 248LL));
        }
      }
      v14 = (_QWORD *)(*((_QWORD *)this + 51) + 248LL);
      if ( *(_DWORD *)(*v14 - 16LL) )
      {
        if ( (unsigned __int8)PushButtonReset::Directory::Exists(v14) )
        {
          PushButtonReset::Logging::Trace(0, L"Cleanup Backup directory");
          v16 = PushButtonReset::Directory::Delete((__int64 *)(*((_QWORD *)this + 51) + 248LL), v15);
          v17 = v16;
          if ( v16 < 0 )
          {
            LogCleanupFailure(&v35, *(_QWORD *)(*((_QWORD *)this + 51) + 248LL), (unsigned int)v16);
            PushButtonReset::Logging::TraceErr(
              1,
              v17,
              "WinREAgent::Executor::Cleanup",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2116,
              L"Failed to cleanup Backup directory");
          }
        }
      }
      v18 = (_QWORD *)(*((_QWORD *)this + 51) + 280LL);
      if ( *(_DWORD *)(*v18 - 16LL) )
      {
        if ( (unsigned __int8)PushButtonReset::File::Exists(v18) )
        {
          PushButtonReset::Logging::Trace(0, L"Cleanup Updated wim");
          v19 = PushButtonReset::File::Delete(*((_QWORD *)this + 51) + 280LL);
          v20 = v19;
          if ( v19 < 0 )
          {
            LogCleanupFailure(&v35, *(_QWORD *)(*((_QWORD *)this + 51) + 280LL), (unsigned int)v19);
            PushButtonReset::Logging::TraceErr(
              1,
              v20,
              "WinREAgent::Executor::Cleanup",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2130,
              L"Failed to cleanup updated wim");
          }
        }
      }
      v21 = (_QWORD *)(*((_QWORD *)this + 51) + 184LL);
      if ( *(_DWORD *)(*v21 - 16LL) )
      {
        if ( (unsigned __int8)PushButtonReset::Directory::Exists(v21) )
        {
          PushButtonReset::Logging::Trace(0, L"Cleanup Scratch directory");
          v22 = WinREAgent::WorkDir::CleanupScratchDir((__int64 *)(*((_QWORD *)this + 51) + 184LL));
          v23 = v22;
          if ( v22 < 0 )
          {
            LogCleanupFailure(&v35, *(_QWORD *)(*((_QWORD *)this + 51) + 184LL), (unsigned int)v22);
            PushButtonReset::Logging::TraceErr(
              1,
              v23,
              "WinREAgent::Executor::Cleanup",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2144,
              L"Failed to cleanup scratch dir");
          }
        }
      }
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 51) + 120LL) - 16LL) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
        Directory = PushButtonReset::Path::GetDirectory(*((_QWORD *)this + 51) + 120LL, &v38);
        if ( Directory < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Directory,
            "WinREAgent::Executor::Cleanup",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2154,
            L"Failed to construct WinRE parent directory path");
LABEL_33:
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
          return (unsigned int)Directory;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v36);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v33,
          (__int64)L"update.wim");
        Directory = PushButtonReset::Path::Combine(&v38, &v33, &v36);
        ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
        if ( Directory < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Directory,
            "WinREAgent::Executor::Cleanup",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2158,
            L"Failed to build path for updated wim new location");
          ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
          goto LABEL_33;
        }
        if ( (unsigned __int8)PushButtonReset::File::Exists(&v36)
          && (PushButtonReset::Logging::Trace(0, L"Cleanup existing new WinRE on Recovery partition"),
              v26 = PushButtonReset::File::Delete(&v36),
              v27 = v26,
              v26 < 0) )
        {
          v28 = v36;
          LogCleanupFailure(&v35, v36, (unsigned int)v26);
          PushButtonReset::Logging::TraceErr(
            1,
            v27,
            "WinREAgent::Executor::Cleanup",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2171,
            L"Failed to cleanup existing new WinRE");
        }
        else
        {
          v28 = v36;
        }
        ATL::CStringData::Release((ATL::CStringData *)(v28 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v36);
      SuspendFile = WinREAgent::WorkDir::GetRootDir(v34, (__int64)&v36);
      if ( (SuspendFile & 0x80000000) != 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          SuspendFile,
          "WinREAgent::Executor::Cleanup",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2180,
          L"Failed to get WinREAgent root directory");
        ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
        v8 = (ATL::CStringData *)(v11 - 24);
        goto LABEL_7;
      }
      if ( (unsigned __int8)PushButtonReset::Directory::Exists(&v36)
        && (PushButtonReset::Logging::Trace(0, L"Cleanup WinREAgent work directory [%s]", v36),
            v30 = PushButtonReset::Directory::Delete((__int64 *)&v36, v29),
            SuspendFile = v30,
            v30 < 0) )
      {
        v31 = v36;
        LogCleanupFailure(&v35, v36, (unsigned int)v30);
        PushButtonReset::Logging::TraceErr(
          1,
          SuspendFile,
          "WinREAgent::Executor::Cleanup",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2189,
          L"Failed to cleanup work directory");
        SuspendFile = 0;
      }
      else
      {
        v31 = v36;
      }
      ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
    }
    else
    {
      PushButtonReset::Logging::Trace(0, L"No execution context for cleanup");
    }
    v32 = v35;
    if ( a3 )
    {
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"CleanupEnd");
      if ( *((_DWORD *)v32 - 4) )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"CleanupError", v32);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
    v9 = (ATL::CStringData *)(v32 - 12);
    goto LABEL_53;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    SuspendFile,
    "WinREAgent::Executor::Cleanup",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    2064,
    L"Failed to get suspend file path");
  v8 = (ATL::CStringData *)(v37 - 24);
LABEL_7:
  ATL::CStringData::Release(v8);
  v9 = (ATL::CStringData *)(v35 - 12);
LABEL_53:
  ATL::CStringData::Release(v9);
  return SuspendFile;
}

```

## disassembly

```asm
0x180006de8  push    rbp
0x180006dea  push    rbx
0x180006deb  push    rsi
0x180006dec  push    rdi
0x180006ded  push    r12
0x180006def  push    r13
0x180006df1  push    r14
0x180006df3  push    r15
0x180006df5  mov     rbp, rsp
0x180006df8  sub     rsp, 58h
0x180006dfc  mov     r13, r8
0x180006dff  mov     r12, rdx
0x180006e02  mov     rbx, rcx
0x180006e05  lea     rdx, aStartCleanupOf; "Start cleanup of execution"
0x180006e0c  xor     ecx, ecx
0x180006e0e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006e13  lea     r8, aNull_0; "NULL"
0x180006e1a  test    r12, r12
0x180006e1d  cmovnz  r8, r12
0x180006e21  lea     rdx, aExternalBackup; "External backup directory [%s]"
0x180006e28  xor     ecx, ecx
0x180006e2a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006e2f  test    r13, r13
0x180006e32  jz      short loc_180006E51
0x180006e34  lea     r9, aCleanupstart; "CleanupStart"
0x180006e3b  lea     r8, aPhase; "Phase"
0x180006e42  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180006e49  mov     rcx, r13; this
0x180006e4c  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x180006e51  lea     rcx, [rbx+1A0h]
0x180006e58  mov     rax, [rcx]
0x180006e5b  xor     edx, edx
0x180006e5d  mov     rax, [rax+30h]
0x180006e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e66  lea     rcx, [rbp+arg_0]
0x180006e6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006e6f  nop
0x180006e70  lea     rcx, [rbp+arg_10]
0x180006e74  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006e79  nop
0x180006e7a  lea     rax, [rbx+170h]
0x180006e81  mov     [rbp+var_10], rax
0x180006e85  lea     rdx, [rbp+arg_10]
0x180006e89  mov     rcx, rax
0x180006e8c  call    ?GetSuspendFile@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetSuspendFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180006e91  mov     esi, eax
0x180006e93  test    eax, eax
0x180006e95  jns     short loc_180006EE1
0x180006e97  lea     rax, aFailedToGetSus; "Failed to get suspend file path"
0x180006e9e  mov     [rsp+58h+var_30], rax
0x180006ea3  mov     [rsp+58h+var_38], 810h
0x180006eab  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006eb2  lea     r8, aWinreagentExec_12; "WinREAgent::Executor::Cleanup"
0x180006eb9  mov     edx, esi
0x180006ebb  mov     ecx, 2
0x180006ec0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006ec5  nop
0x180006ec6  mov     rcx, [rbp+arg_10]
0x180006eca  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006ece  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006ed3  nop
0x180006ed4  mov     rcx, [rbp+arg_0]
0x180006ed8  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180006edc  jmp     loc_180007499
0x180006ee1  lea     rcx, [rbp+arg_10]
0x180006ee5  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006eea  lea     r14, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006ef1  lea     r15, aWinreagentExec_12; "WinREAgent::Executor::Cleanup"
0x180006ef8  test    al, al
0x180006efa  jz      short loc_180006F56
0x180006efc  lea     rdx, aCleanupSuspend; "Cleanup suspend file"
0x180006f03  xor     ecx, ecx
0x180006f05  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006f0a  lea     rcx, [rbp+arg_10]
0x180006f0e  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180006f13  mov     esi, eax
0x180006f15  test    eax, eax
0x180006f17  jns     short loc_180006F56
0x180006f19  mov     r8d, eax
0x180006f1c  mov     rdi, [rbp+arg_10]
0x180006f20  mov     rdx, rdi
0x180006f23  lea     rcx, [rbp+arg_0]
0x180006f27  call    ?LogCleanupFailure@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGJ@Z; LogCleanupFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,long)
0x180006f2c  lea     rax, aFailedToCleanu_1; "Failed to cleanup suspend file"
0x180006f33  mov     [rsp+58h+var_30], rax
0x180006f38  mov     [rsp+58h+var_38], 819h
0x180006f40  mov     r9, r14
0x180006f43  mov     r8, r15
0x180006f46  mov     edx, esi
0x180006f48  mov     ecx, 1
0x180006f4d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006f52  xor     esi, esi
0x180006f54  jmp     short loc_180006F5A
0x180006f56  mov     rdi, [rbp+arg_10]
0x180006f5a  mov     rax, [rbx+198h]
0x180006f61  test    rax, rax
0x180006f64  jz      loc_180007434
0x180006f6a  mov     qword ptr [rax+1C0h], 0
0x180006f75  test    r12, r12
0x180006f78  jz      loc_180007042
0x180006f7e  mov     r8, r12
0x180006f81  lea     rdx, aMoveBackupOfWi; "Move backup of WinRE to [%s]"
0x180006f88  xor     ecx, ecx
0x180006f8a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006f8f  mov     rcx, [rbx+198h]
0x180006f96  add     rcx, 0F8h
0x180006f9d  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006fa2  test    al, al
0x180006fa4  jz      short loc_180007023
0x180006fa6  mov     rdx, r12
0x180006fa9  lea     rcx, [rbp+arg_8]
0x180006fad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006fb2  nop
0x180006fb3  mov     rcx, [rbx+198h]
0x180006fba  add     rcx, 0F8h
0x180006fc1  mov     r9b, 1
0x180006fc4  xor     r8d, r8d
0x180006fc7  lea     rdx, [rbp+arg_8]
0x180006fcb  call    ?Copy@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::Directory::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x180006fd0  mov     esi, eax
0x180006fd2  mov     rcx, [rbp+arg_8]
0x180006fd6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006fda  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006fdf  test    esi, esi
0x180006fe1  jns     short loc_180007042
0x180006fe3  mov     rcx, [rbx+198h]
0x180006fea  mov     [rsp+58h+var_20], r12
0x180006fef  mov     rcx, [rcx+0F8h]
0x180006ff6  mov     [rsp+58h+var_28], rcx
0x180006ffb  lea     rax, aFailedToMoveST; "Failed to move [%s] to [%s]"
0x180007002  mov     [rsp+58h+var_30], rax
0x180007007  mov     [rsp+58h+var_38], 830h
0x18000700f  mov     r9, r14
0x180007012  mov     r8, r15
0x180007015  mov     edx, esi
0x180007017  mov     ecx, 1
0x18000701c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180007021  jmp     short loc_180007042
0x180007023  mov     r8, [rbx+198h]
0x18000702a  mov     r8, [r8+0F8h]
0x180007031  lea     rdx, aBackupDirector; "Backup directory [%s] doesn't exist"
0x180007038  mov     ecx, 1
0x18000703d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180007042  mov     rcx, [rbx+198h]
0x180007049  add     rcx, 0F8h
0x180007050  mov     rax, [rcx]
0x180007053  xor     r12d, r12d
0x180007056  cmp     [rax-10h], r12d
0x18000705a  jz      short loc_1800070CC
0x18000705c  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180007061  test    al, al
0x180007063  jz      short loc_1800070CC
0x180007065  lea     rdx, aCleanupBackupD; "Cleanup Backup directory"
0x18000706c  xor     ecx, ecx
0x18000706e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180007073  mov     rcx, [rbx+198h]
0x18000707a  add     rcx, 0F8h
0x180007081  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x180007086  mov     esi, eax
0x180007088  test    eax, eax
0x18000708a  jns     short loc_1800070CC
0x18000708c  mov     rdx, [rbx+198h]
0x180007093  mov     r8d, eax
0x180007096  mov     rdx, [rdx+0F8h]
0x18000709d  lea     rcx, [rbp+arg_0]
0x1800070a1  call    ?LogCleanupFailure@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGJ@Z; LogCleanupFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,long)
0x1800070a6  lea     rax, aFailedToCleanu_2; "Failed to cleanup Backup directory"
0x1800070ad  mov     [rsp+58h+var_30], rax
0x1800070b2  mov     [rsp+58h+var_38], 844h
0x1800070ba  mov     r9, r14
0x1800070bd  mov     r8, r15
0x1800070c0  mov     edx, esi
0x1800070c2  lea     ecx, [r12+1]
0x1800070c7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800070cc  mov     rcx, [rbx+198h]
0x1800070d3  add     rcx, 118h
0x1800070da  mov     rax, [rcx]
0x1800070dd  cmp     [rax-10h], r12d
0x1800070e1  jz      short loc_180007153
0x1800070e3  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800070e8  test    al, al
0x1800070ea  jz      short loc_180007153
0x1800070ec  lea     rdx, aCleanupUpdated; "Cleanup Updated wim"
0x1800070f3  xor     ecx, ecx
0x1800070f5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800070fa  mov     rcx, [rbx+198h]
0x180007101  add     rcx, 118h
0x180007108  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x18000710d  mov     esi, eax
0x18000710f  test    eax, eax
0x180007111  jns     short loc_180007153
0x180007113  mov     rdx, [rbx+198h]
0x18000711a  mov     r8d, eax
0x18000711d  mov     rdx, [rdx+118h]
0x180007124  lea     rcx, [rbp+arg_0]
0x180007128  call    ?LogCleanupFailure@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGJ@Z; LogCleanupFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,long)
0x18000712d  lea     rax, aFailedToCleanu_6; "Failed to cleanup updated wim"
0x180007134  mov     [rsp+58h+var_30], rax
0x180007139  mov     [rsp+58h+var_38], 852h
0x180007141  mov     r9, r14
0x180007144  mov     r8, r15
0x180007147  mov     edx, esi
0x180007149  mov     ecx, 1
0x18000714e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180007153  mov     rcx, [rbx+198h]
0x18000715a  add     rcx, 0B8h
0x180007161  mov     rax, [rcx]
0x180007164  cmp     [rax-10h], r12d
0x180007168  jz      short loc_1800071DA
0x18000716a  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000716f  test    al, al
0x180007171  jz      short loc_1800071DA
0x180007173  lea     rdx, aCleanupScratch_0; "Cleanup Scratch directory"
0x18000717a  xor     ecx, ecx
0x18000717c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180007181  mov     rcx, [rbx+198h]
0x180007188  add     rcx, 0B8h
0x18000718f  call    ?CleanupScratchDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::WorkDir::CleanupScratchDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180007194  mov     esi, eax
0x180007196  test    eax, eax
0x180007198  jns     short loc_1800071DA
0x18000719a  mov     rdx, [rbx+198h]
0x1800071a1  mov     r8d, eax
0x1800071a4  mov     rdx, [rdx+0B8h]
0x1800071ab  lea     rcx, [rbp+arg_0]
0x1800071af  call    ?LogCleanupFailure@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGJ@Z; LogCleanupFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,long)
0x1800071b4  lea     rax, aFailedToCleanu_7; "Failed to cleanup scratch dir"
0x1800071bb  mov     [rsp+58h+var_30], rax
0x1800071c0  mov     [rsp+58h+var_38], 860h
0x1800071c8  mov     r9, r14
0x1800071cb  mov     r8, r15
0x1800071ce  mov     edx, esi
0x1800071d0  mov     ecx, 1
0x1800071d5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800071da  mov     rax, [rbx+198h]
0x1800071e1  mov     rcx, [rax+78h]
0x1800071e5  cmp     [rcx-10h], r12d
0x1800071e9  jz      loc_18000735E
0x1800071ef  lea     rcx, [rbp+arg_18]
0x1800071f3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800071f8  nop
0x1800071f9  mov     rcx, [rbx+198h]
0x180007200  add     rcx, 78h ; 'x'
0x180007204  lea     rdx, [rbp+arg_18]
0x180007208  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000720d  mov     ebx, eax
0x18000720f  test    eax, eax
0x180007211  jns     short loc_180007266
0x180007213  lea     rax, aFailedToConstr_1; "Failed to construct WinRE parent direct"...
0x18000721a  mov     [rsp+58h+var_30], rax
0x18000721f  mov     [rsp+58h+var_38], 86Ah
0x180007227  mov     r9, r14
0x18000722a  mov     r8, r15
0x18000722d  mov     edx, ebx
0x18000722f  mov     ecx, 2
0x180007234  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180007239  nop
0x18000723a  mov     rcx, [rbp+arg_18]
0x18000723e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007242  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007247  nop
0x180007248  lea     rcx, [rdi-18h]; this
0x18000724c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007251  nop
0x180007252  mov     rcx, [rbp+arg_0]
0x180007256  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000725a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000725f  mov     eax, ebx
0x180007261  jmp     loc_1800074A0
0x180007266  lea     rcx, [rbp+arg_8]
0x18000726a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000726f  nop
0x180007270  lea     rdx, aUpdateWim; "update.wim"
0x180007277  lea     rcx, [rbp+var_18]
0x18000727b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007280  nop
0x180007281  lea     r8, [rbp+arg_8]
0x180007285  lea     rdx, [rbp+var_18]
0x180007289  lea     rcx, [rbp+arg_18]
0x18000728d  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180007292  mov     ebx, eax
0x180007294  mov     rcx, [rbp+var_18]
0x180007298  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000729c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800072a1  test    ebx, ebx
0x1800072a3  jns     short loc_1800072DE
0x1800072a5  lea     rax, aFailedToBuildP; "Failed to build path for updated wim ne"...
0x1800072ac  mov     [rsp+58h+var_30], rax
0x1800072b1  mov     [rsp+58h+var_38], 86Eh
0x1800072b9  mov     r9, r14
0x1800072bc  mov     r8, r15
0x1800072bf  mov     edx, ebx
0x1800072c1  mov     ecx, 2
0x1800072c6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800072cb  nop
0x1800072cc  mov     rcx, [rbp+arg_8]
0x1800072d0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800072d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800072d9  jmp     loc_18000723A
0x1800072de  lea     rcx, [rbp+arg_8]
  ... truncated ...
```
