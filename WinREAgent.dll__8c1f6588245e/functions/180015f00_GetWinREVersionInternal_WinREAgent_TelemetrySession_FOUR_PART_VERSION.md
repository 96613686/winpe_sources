# GetWinREVersionInternal(WinREAgent::TelemetrySession *,_FOUR_PART_VERSION *)

- ea: `0x180015f00`
- end: `0x180016433`
- name: `?GetWinREVersionInternal@@YAJPEAVTelemetrySession@WinREAgent@@PEAT_FOUR_PART_VERSION@@@Z`
- size: `1331`
- prototype: `signed int __fastcall(struct WinREAgent::TelemetrySession *this, union _FOUR_PART_VERSION *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800168a0`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x1800089d0`
- `0x18000d570`
- `0x18000d640`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18001586c`
- `0x180015f00`
- `0x180016440`
- `0x18001f194`
- `0x18002dee0`
- `0x18002f378`
- `0x18003717c`
- `0x180037344`
- `0x180050488`
- `0x1800536bc`
- `0x180053afc`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180015f52`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180015f52`
- `KERNEL32!GetLastError` at `0x180015f5c`
- `KERNEL32!GetLastError` at `0x180015f9e`
- `KERNEL32!GetLastError` at `0x180015f5c`
- `KERNEL32!GetLastError` at `0x180015f9e`
- `DismApi!DismGetImageInfo` at `0x180016283`
- `DismApi!DismGetImageInfo` at `0x180016283`

## string_xrefs

- `0x18001620e`: `Failed to open DISM session`
- `0x180015f70`: `Failed to get system Windows directory`
- `0x180015f84`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016008`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016073`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x1800160e9`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x1800161b1`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016222`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x1800162b3`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180015ff4`: `Failed to build log path`
- `0x1800160d5`: `Failed to read WinRE configuration`
- `0x18001619d`: `Failed to get winre path`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
signed int __fastcall GetWinREVersionInternal(struct WinREAgent::TelemetrySession *this, union _FOUR_PART_VERSION *a2)
{
  signed int LastError; // eax
  signed int result; // eax
  int LogDir; // ebx
  struct PushButtonReset::WindowsRE::Config **v7; // rax
  __int64 v8; // rax
  const unsigned __int16 *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  int ImageInfo; // esi
  unsigned int v15; // ecx
  __int64 v16; // [rsp+20h] [rbp-E0h]
  _BYTE v17[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v20[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v24[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v25[2]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v25);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      v25,
      L"%c:\\",
      Buffer[0]);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v23);
    LogDir = WinREAgent::WorkDir::GetLogDir(v25, &v23);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "GetWinREVersionInternal",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        174,
        L"Failed to build log path");
LABEL_27:
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v25[0] - 24LL));
      return LogDir;
    }
    v17[0] = 0;
    v20[1] = PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &,bool>(
               &v23,
               v17);
    v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
    PushButtonReset::Logging::Trace(0, L"Enter GetWinREVersionInternal");
    if ( !a2 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942487LL,
        "GetWinREVersionInternal",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        181,
        L"Invalid argument");
      v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
      LogDir = -2147024809;
      goto LABEL_27;
    }
    v18[1] = 0;
    v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    v7 = (struct PushButtonReset::WindowsRE::Config **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v18);
    LogDir = PushButtonReset::WindowsRE::OpenConfig(v7);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "GetWinREVersionInternal",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        186,
        L"Failed to read WinRE configuration");
LABEL_12:
      v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v18);
      v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
      goto LABEL_27;
    }
    if ( this )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
      v9 = L"True";
      if ( *(_DWORD *)(v8 + 8) != 1 )
        v9 = L"False";
      WinREAgent::TelemetrySession::TraceDataPoint(this, L"ServicingInfoGroup", L"WinREAvailable", v9);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v22);
    v10 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
    LogDir = PushButtonReset::WindowsRE::Config::GetCurrentWimPath(v10, &v22);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "GetWinREVersionInternal",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        199,
        L"Failed to get winre path");
LABEL_19:
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
      goto LABEL_12;
    }
    v24[1] = 0;
    v24[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    v11 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v24);
    LogDir = PushButtonReset::DismAutoShutdown::Create(&v23, v11);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "GetWinREVersionInternal",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        203,
        L"Failed to open DISM session");
      v24[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v24);
      goto LABEL_19;
    }
    v19[1] = 0;
    v19[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
    v21 = 0;
    v12 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v19);
    v13 = v22;
    ImageInfo = DismGetImageInfo(v22, v12, &v21);
    if ( ImageInfo >= 0 )
    {
      if ( v21 )
      {
        *((_WORD *)a2 + 3) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19) + 84);
        *((_WORD *)a2 + 2) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19) + 88);
        *((_WORD *)a2 + 1) = *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19) + 92);
        v15 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19) + 96);
        *(_WORD *)a2 = v15;
        if ( this )
          WinREAgent::TelemetrySession::TraceWinREVersion(
            this,
            *((unsigned __int16 *)a2 + 3),
            *((unsigned __int16 *)a2 + 2),
            *((unsigned __int16 *)a2 + 1),
            v15);
        LODWORD(v16) = *((unsigned __int16 *)a2 + 1);
        PushButtonReset::Logging::Trace(
          0,
          L"WinRE version: %u.%u.%u.%u",
          *((unsigned __int16 *)a2 + 3),
          *((unsigned __int16 *)a2 + 2),
          v16,
          *(unsigned __int16 *)a2);
        PushButtonReset::Logging::Trace(0, L"Exit GetWinREVersionInternal");
        goto LABEL_26;
      }
      ImageInfo = -2147467259;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)ImageInfo,
      "GetWinREVersionInternal",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
      216,
      L"Failed to get image info");
LABEL_26:
    v19[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
    RAII::CAutoDismDelete<_DismPackageInfo *>::Release(v19);
    v24[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v24);
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
    v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v18);
    v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
    LogDir = ImageInfo;
    goto LABEL_27;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LastError,
    "GetWinREVersionInternal",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
    166,
    L"Failed to get system Windows directory");
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180015f00  mov     [rsp-8+arg_10], rbx
0x180015f05  mov     [rsp-8+arg_18], rsi
0x180015f0a  push    rbp
0x180015f0b  push    rdi
0x180015f0c  push    r12
0x180015f0e  push    r13
0x180015f10  push    r14
0x180015f12  lea     rbp, [rsp-1C0h]
0x180015f1a  sub     rsp, 2C0h
0x180015f21  mov     rax, cs:__security_cookie
0x180015f28  xor     rax, rsp
0x180015f2b  mov     [rbp+1E0h+var_30], rax
0x180015f32  mov     rdi, rdx
0x180015f35  mov     r14, rcx
0x180015f38  xor     edx, edx; Val
0x180015f3a  mov     r8d, 20Ah; Size
0x180015f40  lea     rcx, [rbp+1E0h+Buffer]; void *
0x180015f44  call    memset_0
0x180015f49  mov     edx, 104h; uSize
0x180015f4e  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x180015f52  call    cs:__imp_GetSystemWindowsDirectoryW
0x180015f58  test    eax, eax
0x180015f5a  jnz     short loc_180015FB6
0x180015f5c  call    cs:__imp_GetLastError
0x180015f62  mov     ebx, 80070000h
0x180015f67  test    eax, eax
0x180015f69  jle     short loc_180015F70
0x180015f6b  movzx   eax, ax
0x180015f6e  or      eax, ebx
0x180015f70  lea     rcx, aFailedToGetSys_0; "Failed to get system Windows directory"
0x180015f77  mov     [rsp+2E0h+var_2B8], rcx
0x180015f7c  mov     dword ptr [rsp+2E0h+var_2C0], 0A6h
0x180015f84  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180015f8b  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x180015f92  mov     edx, eax
0x180015f94  mov     ecx, 2
0x180015f99  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180015f9e  call    cs:__imp_GetLastError
0x180015fa4  test    eax, eax
0x180015fa6  jle     loc_180016343
0x180015fac  movzx   eax, ax
0x180015faf  or      eax, ebx
0x180015fb1  jmp     loc_180016343
0x180015fb6  lea     rcx, [rbp+1E0h+var_250]
0x180015fba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180015fbf  nop
0x180015fc0  movzx   r8d, [rbp+1E0h+Buffer]
0x180015fc5  lea     rdx, aC; "%c:\\"
0x180015fcc  lea     rcx, [rbp+1E0h+var_250]
0x180015fd0  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180015fd5  lea     rcx, [rsp+2E0h+var_268]
0x180015fda  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180015fdf  nop
0x180015fe0  lea     rdx, [rsp+2E0h+var_268]
0x180015fe5  lea     rcx, [rbp+1E0h+var_250]
0x180015fe9  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180015fee  mov     ebx, eax
0x180015ff0  test    eax, eax
0x180015ff2  jns     short loc_180016027
0x180015ff4  lea     rax, aFailedToBuildL; "Failed to build log path"
0x180015ffb  mov     [rsp+2E0h+var_2B8], rax
0x180016000  mov     dword ptr [rsp+2E0h+var_2C0], 0AEh
0x180016008  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001600f  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x180016016  mov     edx, ebx
0x180016018  mov     ecx, 2
0x18001601d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016022  jmp     loc_180016325
0x180016027  mov     [rsp+2E0h+var_2B0], 0
0x18001602c  lea     rdx, [rsp+2E0h+var_2B0]
0x180016031  lea     rcx, [rsp+2E0h+var_268]
0x180016036  call    ??$PbrNew@VLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@@YAPEAVLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEA_N@Z; PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &&)
0x18001603b  mov     [rsp+2E0h+var_280], rax
0x180016040  lea     r12, ??_7?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable'
0x180016047  mov     [rsp+2E0h+var_288], r12
0x18001604c  lea     rdx, aEnterGetwinrev; "Enter GetWinREVersionInternal"
0x180016053  xor     ecx, ecx
0x180016055  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001605a  test    rdi, rdi
0x18001605d  jnz     short loc_1800160A8
0x18001605f  lea     rax, aInvalidArgumen; "Invalid argument"
0x180016066  mov     [rsp+2E0h+var_2B8], rax
0x18001606b  mov     dword ptr [rsp+2E0h+var_2C0], 0B5h
0x180016073  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001607a  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x180016081  mov     edx, 80070057h
0x180016086  lea     ecx, [rdi+2]
0x180016089  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001608e  nop
0x18001608f  mov     [rsp+2E0h+var_288], r12
0x180016094  lea     rcx, [rsp+2E0h+var_288]
0x180016099  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x18001609e  mov     ebx, 80070057h
0x1800160a3  jmp     loc_180016325
0x1800160a8  mov     [rsp+2E0h+var_2A0], 0
0x1800160b1  lea     r13, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x1800160b8  mov     [rsp+2E0h+var_2A8], r13
0x1800160bd  lea     rcx, [rsp+2E0h+var_2A8]
0x1800160c2  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800160c7  mov     rcx, rax; struct PushButtonReset::WindowsRE::Config **
0x1800160ca  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x1800160cf  mov     ebx, eax
0x1800160d1  test    eax, eax
0x1800160d3  jns     short loc_180016128
0x1800160d5  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x1800160dc  mov     [rsp+2E0h+var_2B8], rax
0x1800160e1  mov     dword ptr [rsp+2E0h+var_2C0], 0BAh
0x1800160e9  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800160f0  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x1800160f7  mov     edx, ebx
0x1800160f9  mov     ecx, 2
0x1800160fe  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016103  nop
0x180016104  mov     [rsp+2E0h+var_2A8], r13
0x180016109  lea     rcx, [rsp+2E0h+var_2A8]
0x18001610e  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180016113  nop
0x180016114  mov     [rsp+2E0h+var_288], r12
0x180016119  lea     rcx, [rsp+2E0h+var_288]
0x18001611e  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180016123  jmp     loc_180016325
0x180016128  test    r14, r14
0x18001612b  jz      short loc_18001616C
0x18001612d  mov     rax, [rsp+2E0h+var_2A8]
0x180016132  lea     rcx, [rsp+2E0h+var_2A8]
0x180016137  mov     rax, [rax+18h]
0x18001613b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016140  lea     rcx, aFalse_1; "False"
0x180016147  lea     r9, aTrue_0; "True"
0x18001614e  cmp     dword ptr [rax+8], 1
0x180016152  cmovnz  r9, rcx; unsigned __int16 *
0x180016156  lea     r8, aWinreavailable; "WinREAvailable"
0x18001615d  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180016164  mov     rcx, r14; this
0x180016167  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18001616c  lea     rcx, [rsp+2E0h+var_270]
0x180016171  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016176  nop
0x180016177  mov     rax, [rsp+2E0h+var_2A8]
0x18001617c  lea     rcx, [rsp+2E0h+var_2A8]
0x180016181  mov     rax, [rax+18h]
0x180016185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001618a  lea     rdx, [rsp+2E0h+var_270]
0x18001618f  mov     rcx, rax
0x180016192  call    ?GetCurrentWimPath@Config@WindowsRE@PushButtonReset@@QEAAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WindowsRE::Config::GetCurrentWimPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180016197  mov     ebx, eax
0x180016199  test    eax, eax
0x18001619b  jns     short loc_1800161DF
0x18001619d  lea     rax, aFailedToGetWin_0; "Failed to get winre path"
0x1800161a4  mov     [rsp+2E0h+var_2B8], rax
0x1800161a9  mov     dword ptr [rsp+2E0h+var_2C0], 0C7h
0x1800161b1  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800161b8  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x1800161bf  mov     edx, ebx
0x1800161c1  mov     ecx, 2
0x1800161c6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800161cb  nop
0x1800161cc  mov     rcx, [rsp+2E0h+var_270]
0x1800161d1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800161d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800161da  jmp     loc_180016104
0x1800161df  mov     [rbp+1E0h+var_258], 0
0x1800161e7  lea     rsi, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x1800161ee  mov     [rbp+1E0h+var_260], rsi
0x1800161f2  lea     rcx, [rbp+1E0h+var_260]
0x1800161f6  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800161fb  mov     rdx, rax
0x1800161fe  lea     rcx, [rsp+2E0h+var_268]
0x180016203  call    ?Create@DismAutoShutdown@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::DismAutoShutdown::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DismAutoShutdown * *)
0x180016208  mov     ebx, eax
0x18001620a  test    eax, eax
0x18001620c  jns     short loc_18001624C
0x18001620e  lea     rax, aFailedToOpenDi_1; "Failed to open DISM session"
0x180016215  mov     [rsp+2E0h+var_2B8], rax
0x18001621a  mov     dword ptr [rsp+2E0h+var_2C0], 0CBh
0x180016222  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016229  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x180016230  mov     edx, ebx
0x180016232  mov     ecx, 2
0x180016237  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001623c  nop
0x18001623d  mov     [rbp+1E0h+var_260], rsi
0x180016241  lea     rcx, [rbp+1E0h+var_260]
0x180016245  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x18001624a  jmp     short loc_1800161CC
0x18001624c  mov     [rsp+2E0h+var_290], 0
0x180016255  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x18001625c  mov     [rsp+2E0h+var_298], rax
0x180016261  mov     [rsp+2E0h+var_278], 0
0x180016269  lea     rcx, [rsp+2E0h+var_298]
0x18001626e  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180016273  lea     r8, [rsp+2E0h+var_278]
0x180016278  mov     rdx, rax
0x18001627b  mov     rbx, [rsp+2E0h+var_270]
0x180016280  mov     rcx, rbx
0x180016283  call    cs:__imp_DismGetImageInfo
0x180016289  mov     esi, eax
0x18001628b  test    eax, eax
0x18001628d  js      short loc_18001629F
0x18001628f  cmp     [rsp+2E0h+var_278], 0
0x180016294  jnz     loc_18001636E
0x18001629a  mov     esi, 80004005h
0x18001629f  lea     rax, aFailedToGetIma_0; "Failed to get image info"
0x1800162a6  mov     [rsp+2E0h+var_2B8], rax
0x1800162ab  mov     dword ptr [rsp+2E0h+var_2C0], 0D8h
0x1800162b3  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800162ba  lea     r8, aGetwinreversio_1; "GetWinREVersionInternal"
0x1800162c1  mov     edx, esi
0x1800162c3  mov     ecx, 2
0x1800162c8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800162cd  nop
0x1800162ce  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x1800162d5  mov     [rsp+2E0h+var_298], rax
0x1800162da  lea     rcx, [rsp+2E0h+var_298]
0x1800162df  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x1800162e4  nop
0x1800162e5  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x1800162ec  mov     [rbp+1E0h+var_260], rax
0x1800162f0  lea     rcx, [rbp+1E0h+var_260]
0x1800162f4  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x1800162f9  nop
0x1800162fa  lea     rcx, [rbx-18h]; this
0x1800162fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016303  nop
0x180016304  mov     [rsp+2E0h+var_2A8], r13
0x180016309  lea     rcx, [rsp+2E0h+var_2A8]
0x18001630e  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180016313  nop
0x180016314  mov     [rsp+2E0h+var_288], r12
0x180016319  lea     rcx, [rsp+2E0h+var_288]
0x18001631e  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180016323  mov     ebx, esi
0x180016325  mov     rcx, [rsp+2E0h+var_268]
0x18001632a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001632e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016333  nop
0x180016334  mov     rcx, [rbp+1E0h+var_250]
0x180016338  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001633c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016341  mov     eax, ebx
0x180016343  mov     rcx, [rbp+1E0h+var_30]
0x18001634a  xor     rcx, rsp; StackCookie
0x18001634d  call    __security_check_cookie
0x180016352  lea     r11, [rsp+2E0h+var_20]
0x18001635a  mov     rbx, [r11+40h]
0x18001635e  mov     rsi, [r11+48h]
0x180016362  mov     rsp, r11
0x180016365  pop     r14
0x180016367  pop     r13
0x180016369  pop     r12
0x18001636b  pop     rdi
0x18001636c  pop     rbp
0x18001636d  retn
0x18001636e  mov     rax, [rsp+2E0h+var_298]
0x180016373  lea     rcx, [rsp+2E0h+var_298]
0x180016378  mov     rax, [rax+20h]
0x18001637c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016381  movzx   ecx, word ptr [rax+54h]
0x180016385  mov     [rdi+6], cx
0x180016389  mov     rax, [rsp+2E0h+var_298]
0x18001638e  lea     rcx, [rsp+2E0h+var_298]
0x180016393  mov     rax, [rax+20h]
0x180016397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001639c  movzx   ecx, word ptr [rax+58h]
0x1800163a0  mov     [rdi+4], cx
0x1800163a4  mov     rax, [rsp+2E0h+var_298]
0x1800163a9  lea     rcx, [rsp+2E0h+var_298]
0x1800163ae  mov     rax, [rax+20h]
0x1800163b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163b7  movzx   ecx, word ptr [rax+5Ch]
0x1800163bb  mov     [rdi+2], cx
0x1800163bf  mov     rax, [rsp+2E0h+var_298]
0x1800163c4  lea     rcx, [rsp+2E0h+var_298]
0x1800163c9  mov     rax, [rax+20h]
0x1800163cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163d2  movzx   ecx, word ptr [rax+60h]
0x1800163d6  mov     [rdi], cx
0x1800163d9  test    r14, r14
0x1800163dc  jz      short loc_1800163F8
0x1800163de  movzx   r9d, word ptr [rdi+2]; unsigned int
0x1800163e3  movzx   r8d, word ptr [rdi+4]; unsigned int
0x1800163e8  movzx   edx, word ptr [rdi+6]; unsigned int
0x1800163ec  mov     dword ptr [rsp+2E0h+var_2C0], ecx; unsigned int
0x1800163f0  mov     rcx, r14; this
0x1800163f3  call    ?TraceWinREVersion@TelemetrySession@WinREAgent@@QEBAXKKKK@Z; WinREAgent::TelemetrySession::TraceWinREVersion(ulong,ulong,ulong,ulong)
0x1800163f8  movzx   eax, word ptr [rdi]
0x1800163fb  movzx   ecx, word ptr [rdi+2]
0x1800163ff  movzx   r9d, word ptr [rdi+4]
0x180016404  movzx   r8d, word ptr [rdi+6]
0x180016409  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x18001640d  mov     dword ptr [rsp+2E0h+var_2C0], ecx
0x180016411  lea     rdx, aWinreVersionUU; "WinRE version: %u.%u.%u.%u"
0x180016418  xor     ecx, ecx
0x18001641a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001641f  lea     rdx, aExitGetwinreve; "Exit GetWinREVersionInternal"
0x180016426  xor     ecx, ecx
0x180016428  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001642d  jmp     loc_1800162CE
```
