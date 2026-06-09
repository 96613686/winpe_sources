# WinREAgent::Scenario::DetermineScenarioTypeByWim(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::TelemetrySession *,bool,WinREAgent::ScenarioType &)

- ea: `0x18002383c`
- end: `0x180023bf8`
- name: `?DetermineScenarioTypeByWim@Scenario@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAVTelemetrySession@2@_NAEAW4ScenarioType@2@@Z`
- size: `956`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x18000dcc8`
- `0x18000ea90`

## callees

- `0x180004af8`
- `0x180009354`
- `0x18000d92c`
- `0x18000d9ec`
- `0x18002383c`
- `0x180023c00`
- `0x18002e1f8`
- `0x18002ee68`
- `0x18003717c`
- `0x180037344`
- `0x18004d7a0`
- `0x18004e47c`
- `0x18006c690`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800238bc`
- `msvcrt!_wcsicmp` at `0x1800238e7`
- `msvcrt!_wcsicmp` at `0x180023904`
- `msvcrt!_wcsicmp` at `0x1800238bc`
- `msvcrt!_wcsicmp` at `0x1800238e7`
- `msvcrt!_wcsicmp` at `0x180023904`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180023a53`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180023a53`
- `KERNEL32!GetLastError` at `0x180023a5d`
- `KERNEL32!GetLastError` at `0x180023aa1`
- `KERNEL32!GetLastError` at `0x180023a5d`
- `KERNEL32!GetLastError` at `0x180023aa1`

## string_xrefs

- `0x1800239fe`: `Failed to get current WinRE directory`
- `0x180023882`: `WINREAGENT_SCENARIO_SELECTION`
- `0x1800238b2`: `ReplaceInPlace`
- `0x1800238dd`: `UpdateInPartition`
- `0x180023936`: `base\diagnosis\srt\winreagent\lib\operations\src\scenario.cpp`
- `0x18002398f`: `base\diagnosis\srt\winreagent\lib\operations\src\scenario.cpp`
- `0x180023a12`: `base\diagnosis\srt\winreagent\lib\operations\src\scenario.cpp`
- `0x180023a87`: `base\diagnosis\srt\winreagent\lib\operations\src\scenario.cpp`
- `0x18002393d`: `WinREAgent::Scenario::DetermineScenarioTypeByWim`
- `0x180023996`: `WinREAgent::Scenario::DetermineScenarioTypeByWim`
- `0x180023a19`: `WinREAgent::Scenario::DetermineScenarioTypeByWim`
- `0x180023a8e`: `WinREAgent::Scenario::DetermineScenarioTypeByWim`
- `0x180023ae3`: `ReplaceInPlaceFreeSpaceReq`
- `0x180023b81`: `UpdateInPartitionFreeSpaceReq`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinREAgent::Scenario::DetermineScenarioTypeByWim(
        _QWORD *a1,
        _QWORD *a2,
        WinREAgent::TelemetrySession *a3,
        unsigned __int8 a4,
        _DWORD *a5)
{
  int EnvironmentVariableW; // eax
  wchar_t *v9; // rbx
  signed int Size; // esi
  ATL::CStringData *v12; // rcx
  LPCWSTR v13; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // r15
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // r12
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  LPCWSTR lpDirectoryName; // [rsp+48h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-21h] BYREF
  WinREAgent::TelemetrySession *v30; // [rsp+68h] [rbp-19h]
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+70h] [rbp-11h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+78h] [rbp-9h] BYREF

  v30 = a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
  EnvironmentVariableW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                           &String1,
                           L"WINREAGENT_SCENARIO_SELECTION");
  v9 = String1;
  if ( EnvironmentVariableW )
  {
    PushButtonReset::Logging::Trace(0, L"Get scenario from environment [%s]", String1);
    if ( !_wcsicmp(v9, L"ReplaceInPlace") )
    {
      *a5 = 1;
LABEL_4:
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
      return 0;
    }
    if ( !_wcsicmp(v9, L"UpdateInPartition") )
    {
      *a5 = 2;
      goto LABEL_4;
    }
    if ( _wcsicmp(v9, L"Repartition") )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942487LL,
        "WinREAgent::Scenario::DetermineScenarioTypeByWim",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\scenario.cpp",
        65,
        L"Invalid scenario [%s] from environment variable",
        v9);
      Size = -2147024809;
    }
    else
    {
      *a5 = 3;
      Size = 0;
    }
  }
  else
  {
    v28 = 0;
    Size = PushButtonReset::File::GetSize(a1, &v28);
    if ( Size >= 0 )
    {
      v29 = 0;
      Size = PushButtonReset::File::GetSize(a2, &v29);
      if ( Size >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpDirectoryName);
        Size = PushButtonReset::Path::GetDirectory(a1, &lpDirectoryName);
        if ( Size >= 0 )
        {
          TotalNumberOfBytes.QuadPart = 0;
          TotalNumberOfFreeBytes.QuadPart = 0;
          v13 = lpDirectoryName;
          if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
          {
            v16 = v28;
            v17 = v29;
            if ( a3 )
            {
              WinREAgent::TelemetrySession::TraceWinREPartitionInfo(
                a3,
                TotalNumberOfBytes.QuadPart,
                TotalNumberOfFreeBytes.QuadPart,
                v28);
              WinREAgent::TelemetrySession::TraceDataPoint(
                a3,
                L"ServicingInfoGroup",
                L"ReplaceInPlaceFreeSpaceReq",
                v17 + 10485760);
            }
            PushButtonReset::Logging::Trace(
              0,
              L"WinRE partition total space [%llu], free space [%llu], winre size [%llu], target WinRE size [%llu]",
              TotalNumberOfBytes.QuadPart,
              TotalNumberOfFreeBytes.QuadPart,
              v16,
              v17);
            if ( TotalNumberOfFreeBytes.QuadPart <= v17 + 10485760 )
            {
              v21 = winreEstimateBufferNeededOnPartition_0(TotalNumberOfBytes.LowPart, v18, v19, v20, a4);
              PushButtonReset::Logging::Trace(0, L"Free space requirement: [%llu]", v21);
              LOBYTE(v22) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
                v22);
              if ( v30 )
              {
                if ( v17 > v16 )
                  v24 = v17 + v21 - v16;
                else
                  v24 = 0;
                WinREAgent::TelemetrySession::TraceDataPoint(
                  v30,
                  L"ServicingInfoGroup",
                  L"UpdateInPartitionFreeSpaceReq",
                  v24);
              }
              if ( v17 <= v16 || TotalNumberOfFreeBytes.QuadPart > v17 + v21 - v16 )
              {
                *a5 = 2;
              }
              else
              {
                LOBYTE(v23) = 1;
                wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
                  `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
                  v23);
                *a5 = 3;
              }
            }
            else
            {
              *a5 = 1;
            }
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)LastError,
              "WinREAgent::Scenario::DetermineScenarioTypeByWim",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\scenario.cpp",
              85,
              L"Failed to get space info for recovery partition");
            v15 = GetLastError();
            Size = v15;
            if ( v15 > 0 )
              Size = (unsigned __int16)v15 | 0x80070000;
          }
          v12 = (ATL::CStringData *)(v13 - 12);
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Size,
            "WinREAgent::Scenario::DetermineScenarioTypeByWim",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\scenario.cpp",
            78,
            L"Failed to get current WinRE directory");
          v12 = (ATL::CStringData *)(lpDirectoryName - 12);
        }
        ATL::CStringData::Release(v12);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Size,
          "WinREAgent::Scenario::DetermineScenarioTypeByWim",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\scenario.cpp",
          74,
          L"Failed to get size of [%s]",
          *a2);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Scenario::DetermineScenarioTypeByWim",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\scenario.cpp",
        70,
        L"Failed to get size of [%s]",
        *a1);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18002383c  push    rbp
0x18002383e  push    rbx
0x18002383f  push    rsi
0x180023840  push    rdi
0x180023841  push    r12
0x180023843  push    r13
0x180023845  push    r14
0x180023847  push    r15
0x180023849  lea     rbp, [rsp-17h]
0x18002384e  sub     rsp, 98h
0x180023855  mov     rax, cs:__security_cookie
0x18002385c  xor     rax, rsp
0x18002385f  mov     [rbp+4Fh+var_50], rax
0x180023863  mov     [rbp+4Fh+var_90], r9b
0x180023867  mov     r12, r8
0x18002386a  mov     [rbp+4Fh+var_68], r8
0x18002386e  mov     r15, rdx
0x180023871  mov     rdi, rcx
0x180023874  mov     r14, [rbp+4Fh+arg_20]
0x180023878  lea     rcx, [rbp+4Fh+String1]
0x18002387c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180023881  nop
0x180023882  lea     rdx, aWinreagentScen_0; "WINREAGENT_SCENARIO_SELECTION"
0x180023889  lea     rcx, [rbp+4Fh+String1]
0x18002388d  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180023892  mov     rbx, [rbp+4Fh+String1]
0x180023896  xor     r13d, r13d
0x180023899  test    eax, eax
0x18002389b  jz      loc_18002395D
0x1800238a1  mov     r8, rbx
0x1800238a4  lea     rdx, aGetScenarioFro; "Get scenario from environment [%s]"
0x1800238ab  xor     ecx, ecx
0x1800238ad  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800238b2  lea     rdx, aReplaceinplace; "ReplaceInPlace"
0x1800238b9  mov     rcx, rbx; String1
0x1800238bc  call    cs:__imp__wcsicmp
0x1800238c2  test    eax, eax
0x1800238c4  jnz     short loc_1800238DD
0x1800238c6  mov     dword ptr [r14], 1
0x1800238cd  lea     rcx, [rbx-18h]; this
0x1800238d1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800238d6  xor     eax, eax
0x1800238d8  jmp     loc_180023BD8
0x1800238dd  lea     rdx, aUpdateinpartit_0; "UpdateInPartition"
0x1800238e4  mov     rcx, rbx; String1
0x1800238e7  call    cs:__imp__wcsicmp
0x1800238ed  test    eax, eax
0x1800238ef  jnz     short loc_1800238FA
0x1800238f1  mov     dword ptr [r14], 2
0x1800238f8  jmp     short loc_1800238CD
0x1800238fa  lea     rdx, aRepartition; "Repartition"
0x180023901  mov     rcx, rbx; String1
0x180023904  call    cs:__imp__wcsicmp
0x18002390a  test    eax, eax
0x18002390c  jnz     short loc_18002391D
0x18002390e  mov     dword ptr [r14], 3
0x180023915  mov     esi, r13d
0x180023918  jmp     loc_180023BCD
0x18002391d  mov     [rsp+0D0h+var_A0], rbx
0x180023922  lea     rax, aInvalidScenari; "Invalid scenario [%s] from environment "...
0x180023929  mov     [rsp+0D0h+var_A8], rax
0x18002392e  mov     dword ptr [rsp+0D0h+var_B0], 41h ; 'A'
0x180023936  lea     r9, aBaseDiagnosisS_14; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002393d  lea     r8, aWinreagentScen; "WinREAgent::Scenario::DetermineScenario"...
0x180023944  mov     edx, 80070057h
0x180023949  mov     ecx, 2
0x18002394e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180023953  mov     esi, 80070057h
0x180023958  jmp     loc_180023BCD
0x18002395d  mov     [rbp+4Fh+var_78], r13
0x180023961  lea     rdx, [rbp+4Fh+var_78]
0x180023965  mov     rcx, rdi
0x180023968  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18002396d  mov     esi, eax
0x18002396f  test    eax, eax
0x180023971  jns     short loc_1800239AE
0x180023973  mov     rcx, [rdi]
0x180023976  mov     [rsp+0D0h+var_A0], rcx
0x18002397b  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x180023982  mov     [rsp+0D0h+var_A8], rax
0x180023987  mov     dword ptr [rsp+0D0h+var_B0], 46h ; 'F'
0x18002398f  lea     r9, aBaseDiagnosisS_14; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023996  lea     r8, aWinreagentScen; "WinREAgent::Scenario::DetermineScenario"...
0x18002399d  mov     edx, esi
0x18002399f  mov     ecx, 2
0x1800239a4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800239a9  jmp     loc_180023BCD
0x1800239ae  mov     [rbp+4Fh+var_70], r13
0x1800239b2  lea     rdx, [rbp+4Fh+var_70]
0x1800239b6  mov     rcx, r15
0x1800239b9  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x1800239be  mov     esi, eax
0x1800239c0  test    eax, eax
0x1800239c2  jns     short loc_1800239E2
0x1800239c4  mov     rax, [r15]
0x1800239c7  mov     [rsp+0D0h+var_A0], rax
0x1800239cc  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x1800239d3  mov     [rsp+0D0h+var_A8], rax
0x1800239d8  mov     dword ptr [rsp+0D0h+var_B0], 4Ah ; 'J'
0x1800239e0  jmp     short loc_18002398F
0x1800239e2  lea     rcx, [rbp+4Fh+lpDirectoryName]
0x1800239e6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800239eb  nop
0x1800239ec  lea     rdx, [rbp+4Fh+lpDirectoryName]
0x1800239f0  mov     rcx, rdi
0x1800239f3  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800239f8  mov     esi, eax
0x1800239fa  test    eax, eax
0x1800239fc  jns     short loc_180023A3A
0x1800239fe  lea     rax, aFailedToGetCur_1; "Failed to get current WinRE directory"
0x180023a05  mov     [rsp+0D0h+var_A8], rax
0x180023a0a  mov     dword ptr [rsp+0D0h+var_B0], 4Eh ; 'N'
0x180023a12  lea     r9, aBaseDiagnosisS_14; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023a19  lea     r8, aWinreagentScen; "WinREAgent::Scenario::DetermineScenario"...
0x180023a20  mov     edx, esi
0x180023a22  mov     ecx, 2
0x180023a27  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180023a2c  nop
0x180023a2d  mov     rcx, [rbp+4Fh+lpDirectoryName]
0x180023a31  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180023a35  jmp     loc_180023BC7
0x180023a3a  mov     qword ptr [rbp+4Fh+TotalNumberOfBytes], r13
0x180023a3e  mov     qword ptr [rbp+4Fh+TotalNumberOfFreeBytes], r13
0x180023a42  lea     r9, [rbp+4Fh+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180023a46  lea     r8, [rbp+4Fh+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180023a4a  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180023a4c  mov     rdi, [rbp+4Fh+lpDirectoryName]
0x180023a50  mov     rcx, rdi; lpDirectoryName
0x180023a53  call    cs:__imp_GetDiskFreeSpaceExW
0x180023a59  test    eax, eax
0x180023a5b  jnz     short loc_180023ABC
0x180023a5d  call    cs:__imp_GetLastError
0x180023a63  mov     r14d, 80070000h
0x180023a69  test    eax, eax
0x180023a6b  jle     short loc_180023A73
0x180023a6d  movzx   eax, ax
0x180023a70  or      eax, r14d
0x180023a73  lea     rcx, aFailedToGetSpa; "Failed to get space info for recovery p"...
0x180023a7a  mov     [rsp+0D0h+var_A8], rcx
0x180023a7f  mov     dword ptr [rsp+0D0h+var_B0], 55h ; 'U'
0x180023a87  lea     r9, aBaseDiagnosisS_14; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023a8e  lea     r8, aWinreagentScen; "WinREAgent::Scenario::DetermineScenario"...
0x180023a95  mov     edx, eax
0x180023a97  mov     ecx, 2
0x180023a9c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180023aa1  call    cs:__imp_GetLastError
0x180023aa7  mov     esi, eax
0x180023aa9  test    eax, eax
0x180023aab  jle     loc_180023BC3
0x180023ab1  movzx   esi, ax
0x180023ab4  or      esi, r14d
0x180023ab7  jmp     loc_180023BC3
0x180023abc  mov     r13, [rbp+4Fh+var_78]
0x180023ac0  mov     r15, [rbp+4Fh+var_70]
0x180023ac4  test    r12, r12
0x180023ac7  jz      short loc_180023AF9
0x180023ac9  mov     r9, r13; unsigned __int64
0x180023acc  mov     r8, qword ptr [rbp+4Fh+TotalNumberOfFreeBytes]; unsigned __int64
0x180023ad0  mov     rdx, qword ptr [rbp+4Fh+TotalNumberOfBytes]; unsigned __int64
0x180023ad4  mov     rcx, r12; this
0x180023ad7  call    ?TraceWinREPartitionInfo@TelemetrySession@WinREAgent@@QEBAX_K00@Z; WinREAgent::TelemetrySession::TraceWinREPartitionInfo(unsigned __int64,unsigned __int64,unsigned __int64)
0x180023adc  lea     r9, [r15+0A00000h]; unsigned __int64
0x180023ae3  lea     r8, aReplaceinplace_0; "ReplaceInPlaceFreeSpaceReq"
0x180023aea  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180023af1  mov     rcx, r12; this
0x180023af4  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180023af9  mov     [rsp+0D0h+var_A8], r15
0x180023afe  mov     [rsp+0D0h+var_B0], r13
0x180023b03  mov     r9, qword ptr [rbp+4Fh+TotalNumberOfFreeBytes]
0x180023b07  mov     r8, qword ptr [rbp+4Fh+TotalNumberOfBytes]
0x180023b0b  lea     rdx, aWinrePartition_5; "WinRE partition total space [%llu], fre"...
0x180023b12  xor     ecx, ecx
0x180023b14  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023b19  lea     rax, [r15+0A00000h]
0x180023b20  cmp     qword ptr [rbp+4Fh+TotalNumberOfFreeBytes], rax
0x180023b24  jbe     short loc_180023B32
0x180023b26  mov     dword ptr [r14], 1
0x180023b2d  jmp     loc_180023BC3
0x180023b32  movzx   eax, [rbp+4Fh+var_90]
0x180023b36  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180023b3a  mov     rcx, qword ptr [rbp+4Fh+TotalNumberOfBytes]
0x180023b3e  call    winreEstimateBufferNeededOnPartition_0
0x180023b43  mov     r12, rax
0x180023b46  mov     r8, rax
0x180023b49  lea     rdx, aFreeSpaceRequi; "Free space requirement: [%llu]"
0x180023b50  xor     ecx, ecx
0x180023b52  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023b57  mov     dl, 1
0x180023b59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x180023b60  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180023b65  mov     rcx, [rbp+4Fh+var_68]; this
0x180023b69  test    rcx, rcx
0x180023b6c  jz      short loc_180023B94
0x180023b6e  cmp     r15, r13
0x180023b71  ja      short loc_180023B78
0x180023b73  xor     r9d, r9d
0x180023b76  jmp     short loc_180023B81
0x180023b78  mov     r9, r12
0x180023b7b  sub     r9, r13
0x180023b7e  add     r9, r15; unsigned __int64
0x180023b81  lea     r8, aUpdateinpartit_10; "UpdateInPartitionFreeSpaceReq"
0x180023b88  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180023b8f  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180023b94  cmp     r15, r13
0x180023b97  jbe     short loc_180023BBC
0x180023b99  sub     r12, r13
0x180023b9c  add     r12, r15
0x180023b9f  cmp     qword ptr [rbp+4Fh+TotalNumberOfFreeBytes], r12
0x180023ba3  ja      short loc_180023BBC
0x180023ba5  mov     dl, 1
0x180023ba7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x180023bae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180023bb3  mov     dword ptr [r14], 3
0x180023bba  jmp     short loc_180023BC3
0x180023bbc  mov     dword ptr [r14], 2
0x180023bc3  lea     rcx, [rdi-18h]; this
0x180023bc7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023bcc  nop
0x180023bcd  lea     rcx, [rbx-18h]; this
0x180023bd1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023bd6  mov     eax, esi
0x180023bd8  mov     rcx, [rbp+4Fh+var_50]
0x180023bdc  xor     rcx, rsp; StackCookie
0x180023bdf  call    __security_check_cookie
0x180023be4  add     rsp, 98h
0x180023beb  pop     r15
0x180023bed  pop     r14
0x180023bef  pop     r13
0x180023bf1  pop     r12
0x180023bf3  pop     rdi
0x180023bf4  pop     rsi
0x180023bf5  pop     rbx
0x180023bf6  pop     rbp
0x180023bf7  retn
```
