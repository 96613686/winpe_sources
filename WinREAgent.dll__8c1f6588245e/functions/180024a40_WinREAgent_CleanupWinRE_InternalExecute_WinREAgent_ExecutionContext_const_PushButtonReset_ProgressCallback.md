# WinREAgent::CleanupWinRE::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x180024a40`
- end: `0x180024dbb`
- name: `?InternalExecute@CleanupWinRE@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(WinREAgent::CleanupWinRE *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180013e74`
- `0x18002476c`
- `0x180024a40`
- `0x18002dee0`
- `0x18002e1f8`
- `0x180034138`
- `0x1800346cc`
- `0x18003717c`
- `0x180037344`
- `0x18004e5a4`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024c16`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024cfd`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024c16`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024cfd`
- `KERNEL32!GetLastError` at `0x180024c2c`
- `KERNEL32!GetLastError` at `0x180024d07`
- `KERNEL32!GetLastError` at `0x180024c2c`
- `KERNEL32!GetLastError` at `0x180024d07`

## string_xrefs

- `0x180024ad0`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024b5a`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024bbb`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024c4b`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024caa`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024d26`: `base\diagnosis\srt\winreagent\lib\operations\src\cleanupwinre.cpp`
- `0x180024ad7`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024b61`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024bc2`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024c52`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024cb1`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024d2d`: `WinREAgent::CleanupWinRE::InternalExecute`
- `0x180024b11`: `IsCleanupAllowedInCommit`
- `0x180024c96`: `Failed to delete non-WinRE files in WinRE partition`
- `0x180024cc7`: `CleanupWinRE: Deleted file size: [%llu]`
- `0x180024cde`: `SizeDeleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::CleanupWinRE::InternalExecute(
        WinREAgent::CleanupWinRE *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  WinREAgent::TelemetrySession *v5; // rdi
  char *v6; // rdx
  int Volume; // ebx
  const unsigned __int16 *v8; // r9
  signed int LastError; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  signed int v13; // eax
  __int64 v15; // [rsp+40h] [rbp-40h] BYREF
  bool v16; // [rsp+48h] [rbp-38h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpDirectoryName; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v20; // [rsp+68h] [rbp-18h] BYREF

  PushButtonReset::Logging::Trace(0, L"CleanupWinRE: Cleanup WinRE partition", a3);
  v5 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  v16 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v20);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl) )
    v6 = (char *)this + 176;
  else
    v6 = 0;
  Volume = WinREAgent::WinREIsWinRECleanupAllowed((_QWORD *)a2 + 15, (__int64)v6, &v16, &v20);
  if ( Volume >= 0 )
  {
    if ( v5 )
    {
      v8 = L"True";
      if ( !v16 )
        v8 = L"False";
      WinREAgent::TelemetrySession::TraceDataPoint(v5, L"ExecutionInfoGroup", L"IsCleanupAllowedInCommit", v8);
      if ( *((_DWORD *)v20 - 4) )
        WinREAgent::TelemetrySession::TraceDataPoint(v5, L"ExecutionInfoGroup", L"UnknownContentOnWinREPartition", v20);
    }
    if ( v16 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v15);
      Volume = PushButtonReset::Path::GetVolume((char *)a2 + 120, &v15);
      if ( Volume >= 0 )
      {
        ATL::operator+(&lpDirectoryName, &v15, L"\\");
        PushButtonReset::Logging::Trace(0, L"CleanupWinRE: WinRE partition root: [%s]", lpDirectoryName);
        TotalNumberOfFreeBytes.QuadPart = 0;
        if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, 0, &TotalNumberOfFreeBytes) )
        {
          PushButtonReset::Logging::Trace(
            0,
            L"CleanupWinRE: Current free space on WinRE partition: [%llu]",
            TotalNumberOfFreeBytes.QuadPart);
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)LastError,
            "WinREAgent::CleanupWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
            160,
            L"Failed to get space info for recovery partition");
        }
        v19 = 0;
        Volume = WinREAgent::WinREEnumFiles((unsigned int)&lpDirectoryName, v10, v11, v12, (__int64)&v19);
        if ( Volume < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)Volume,
            "WinREAgent::CleanupWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
            176,
            L"Failed to delete non-WinRE files in WinRE partition");
          Volume = 0;
        }
        PushButtonReset::Logging::Trace(0, L"CleanupWinRE: Deleted file size: [%llu]", v19);
        if ( v5 )
          WinREAgent::TelemetrySession::TraceDataPoint(v5, L"ExecutionInfoGroup", L"SizeDeleted", v19);
        if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, 0, &TotalNumberOfFreeBytes) )
        {
          PushButtonReset::Logging::Trace(
            0,
            L"CleanupWinRE: Free space on WinRE partition after cleanup : [%llu]",
            TotalNumberOfFreeBytes.QuadPart);
          if ( v5 )
            WinREAgent::TelemetrySession::TraceDataPoint(
              v5,
              L"ExecutionInfoGroup",
              L"FreeSpaceAfterCleanup",
              TotalNumberOfFreeBytes.QuadPart);
        }
        else
        {
          v13 = GetLastError();
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v13,
            "WinREAgent::CleanupWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
            188,
            L"Failed to get space info for recovery partition");
        }
        ATL::CStringData::Release((ATL::CStringData *)(lpDirectoryName - 12));
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::CleanupWinRE::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
          151,
          L"Failed to get volume for WinRE.wim at [%s]",
          *((_QWORD *)a2 + 15));
      }
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942450LL,
        "WinREAgent::CleanupWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
        146,
        L"Cleanup WinRE partition is not allowed by policy");
      Volume = -2147024846;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Volume,
      "WinREAgent::CleanupWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\cleanupwinre.cpp",
      128,
      L"Failed to check whether cleanup WinRE partition is allowed");
  }
  ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
  return (unsigned int)Volume;
}

```

## disassembly

```asm
0x180024a40  mov     [rsp-28h+arg_10], rbx
0x180024a45  push    rbp
0x180024a46  push    rsi
0x180024a47  push    rdi
0x180024a48  push    r13
0x180024a4a  push    r14
0x180024a4c  mov     rbp, rsp
0x180024a4f  sub     rsp, 80h
0x180024a56  mov     rax, cs:__security_cookie
0x180024a5d  xor     rax, rsp
0x180024a60  mov     [rbp+var_10], rax
0x180024a64  mov     rsi, rdx
0x180024a67  mov     r14, rcx
0x180024a6a  lea     rdx, aCleanupwinreCl; "CleanupWinRE: Cleanup WinRE partition"
0x180024a71  xor     ecx, ecx
0x180024a73  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024a78  mov     rdi, [r14+70h]
0x180024a7c  mov     [rbp+var_38], 0
0x180024a80  lea     rcx, [rbp+var_18]
0x180024a84  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024a89  nop
0x180024a8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl(void)'::`2'::impl
0x180024a91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled(void)
0x180024a96  test    al, al
0x180024a98  jz      short loc_180024AA3
0x180024a9a  lea     rdx, [r14+0B0h]
0x180024aa1  jmp     short loc_180024AA5
0x180024aa3  xor     edx, edx
0x180024aa5  lea     r9, [rbp+var_18]
0x180024aa9  lea     r8, [rbp+var_38]
0x180024aad  lea     rcx, [rsi+78h]
0x180024ab1  call    ?WinREIsWinRECleanupAllowed@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@PEA_NPEAV23@@Z; WinREAgent::WinREIsWinRECleanupAllowed(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180024ab6  mov     ebx, eax
0x180024ab8  test    eax, eax
0x180024aba  jns     short loc_180024AEF
0x180024abc  lea     rax, aFailedToCheckW_7; "Failed to check whether cleanup WinRE p"...
0x180024ac3  mov     [rsp+80h+var_58], rax
0x180024ac8  mov     dword ptr [rsp+80h+var_60], 80h
0x180024ad0  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024ad7  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024ade  mov     edx, ebx
0x180024ae0  mov     ecx, 2
0x180024ae5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024aea  jmp     loc_180024D89
0x180024aef  lea     r14, aExecutioninfog; "ExecutionInfoGroup"
0x180024af6  test    rdi, rdi
0x180024af9  jz      short loc_180024B40
0x180024afb  lea     r9, aTrue_0; "True"
0x180024b02  lea     rax, aFalse_1; "False"
0x180024b09  cmp     [rbp+var_38], 0
0x180024b0d  cmovz   r9, rax; unsigned __int16 *
0x180024b11  lea     r8, aIscleanupallow_0; "IsCleanupAllowedInCommit"
0x180024b18  mov     rdx, r14; unsigned __int16 *
0x180024b1b  mov     rcx, rdi; this
0x180024b1e  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x180024b23  mov     r9, [rbp+var_18]; unsigned __int16 *
0x180024b27  cmp     dword ptr [r9-10h], 0
0x180024b2c  jz      short loc_180024B40
0x180024b2e  lea     r8, aUnknowncontent_0; "UnknownContentOnWinREPartition"
0x180024b35  mov     rdx, r14; unsigned __int16 *
0x180024b38  mov     rcx, rdi; this
0x180024b3b  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x180024b40  cmp     [rbp+var_38], 0
0x180024b44  jnz     short loc_180024B81
0x180024b46  lea     rax, aCleanupWinrePa_0; "Cleanup WinRE partition is not allowed "...
0x180024b4d  mov     [rsp+80h+var_58], rax
0x180024b52  mov     dword ptr [rsp+80h+var_60], 92h
0x180024b5a  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024b61  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024b68  mov     edx, 80070032h
0x180024b6d  mov     ecx, 2
0x180024b72  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024b77  mov     ebx, 80070032h
0x180024b7c  jmp     loc_180024D89
0x180024b81  lea     rcx, [rbp+var_40]
0x180024b85  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024b8a  nop
0x180024b8b  lea     rdx, [rbp+var_40]
0x180024b8f  lea     rcx, [rsi+78h]
0x180024b93  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180024b98  mov     ebx, eax
0x180024b9a  test    eax, eax
0x180024b9c  jns     short loc_180024BDA
0x180024b9e  mov     rcx, [rsi+78h]
0x180024ba2  mov     [rsp+80h+var_50], rcx
0x180024ba7  lea     rax, aFailedToGetVol_0; "Failed to get volume for WinRE.wim at ["...
0x180024bae  mov     [rsp+80h+var_58], rax
0x180024bb3  mov     dword ptr [rsp+80h+var_60], 97h
0x180024bbb  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024bc2  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024bc9  mov     edx, ebx
0x180024bcb  mov     ecx, 2
0x180024bd0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024bd5  jmp     loc_180024D7B
0x180024bda  lea     r8, SubBlock; "\\"
0x180024be1  lea     rdx, [rbp+var_40]
0x180024be5  lea     rcx, [rbp+lpDirectoryName]
0x180024be9  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180024bee  nop
0x180024bef  mov     r8, [rbp+lpDirectoryName]
0x180024bf3  lea     rdx, aCleanupwinreWi; "CleanupWinRE: WinRE partition root: [%s"...
0x180024bfa  xor     ecx, ecx
0x180024bfc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024c01  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x180024c09  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180024c0d  xor     r8d, r8d; lpTotalNumberOfBytes
0x180024c10  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180024c12  mov     rcx, [rbp+lpDirectoryName]; lpDirectoryName
0x180024c16  call    cs:__imp_GetDiskFreeSpaceExW
0x180024c1c  lea     r13, aFailedToGetSpa; "Failed to get space info for recovery p"...
0x180024c23  mov     esi, 1
0x180024c28  test    eax, eax
0x180024c2a  jnz     short loc_180024C64
0x180024c2c  call    cs:__imp_GetLastError
0x180024c32  test    eax, eax
0x180024c34  jle     short loc_180024C3E
0x180024c36  movzx   eax, ax
0x180024c39  or      eax, 80070000h
0x180024c3e  mov     [rsp+80h+var_58], r13
0x180024c43  mov     dword ptr [rsp+80h+var_60], 0A0h
0x180024c4b  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024c52  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024c59  mov     edx, eax
0x180024c5b  mov     ecx, esi
0x180024c5d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024c62  jmp     short loc_180024C76
0x180024c64  mov     r8, qword ptr [rbp+TotalNumberOfFreeBytes]
0x180024c68  lea     rdx, aCleanupwinreCu; "CleanupWinRE: Current free space on Win"...
0x180024c6f  xor     ecx, ecx
0x180024c71  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024c76  mov     [rbp+var_20], 0
0x180024c7e  lea     rax, [rbp+var_20]
0x180024c82  mov     [rsp+80h+var_60], rax
0x180024c87  lea     rcx, [rbp+lpDirectoryName]
0x180024c8b  call    ?WinREEnumFiles@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1P6AJ00PEAX@Z2@Z; WinREAgent::WinREEnumFiles(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,bool,long (*)(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *),void *)
0x180024c90  mov     ebx, eax
0x180024c92  test    eax, eax
0x180024c94  jns     short loc_180024CC3
0x180024c96  lea     rax, aFailedToDelete_11; "Failed to delete non-WinRE files in Win"...
0x180024c9d  mov     [rsp+80h+var_58], rax
0x180024ca2  mov     dword ptr [rsp+80h+var_60], 0B0h
0x180024caa  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024cb1  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024cb8  mov     edx, ebx
0x180024cba  mov     ecx, esi
0x180024cbc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024cc1  xor     ebx, ebx
0x180024cc3  mov     r8, [rbp+var_20]
0x180024cc7  lea     rdx, aCleanupwinreDe; "CleanupWinRE: Deleted file size: [%llu]"
0x180024cce  xor     ecx, ecx
0x180024cd0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024cd5  test    rdi, rdi
0x180024cd8  jz      short loc_180024CF0
0x180024cda  mov     r9, [rbp+var_20]; unsigned __int64
0x180024cde  lea     r8, aSizedeleted; "SizeDeleted"
0x180024ce5  mov     rdx, r14; unsigned __int16 *
0x180024ce8  mov     rcx, rdi; this
0x180024ceb  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180024cf0  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180024cf4  xor     r8d, r8d; lpTotalNumberOfBytes
0x180024cf7  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180024cf9  mov     rcx, [rbp+lpDirectoryName]; lpDirectoryName
0x180024cfd  call    cs:__imp_GetDiskFreeSpaceExW
0x180024d03  test    eax, eax
0x180024d05  jnz     short loc_180024D3F
0x180024d07  call    cs:__imp_GetLastError
0x180024d0d  test    eax, eax
0x180024d0f  jle     short loc_180024D19
0x180024d11  movzx   eax, ax
0x180024d14  or      eax, 80070000h
0x180024d19  mov     [rsp+80h+var_58], r13
0x180024d1e  mov     dword ptr [rsp+80h+var_60], 0BCh
0x180024d26  lea     r9, aBaseDiagnosisS_15; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024d2d  lea     r8, aWinreagentClea; "WinREAgent::CleanupWinRE::InternalExecu"...
0x180024d34  mov     edx, eax
0x180024d36  mov     ecx, esi
0x180024d38  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024d3d  jmp     short loc_180024D6D
0x180024d3f  mov     r8, qword ptr [rbp+TotalNumberOfFreeBytes]
0x180024d43  lea     rdx, aCleanupwinreFr; "CleanupWinRE: Free space on WinRE parti"...
0x180024d4a  xor     ecx, ecx
0x180024d4c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024d51  test    rdi, rdi
0x180024d54  jz      short loc_180024D6D
0x180024d56  mov     r9, qword ptr [rbp+TotalNumberOfFreeBytes]; unsigned __int64
0x180024d5a  lea     r8, aFreespaceafter; "FreeSpaceAfterCleanup"
0x180024d61  mov     rdx, r14; unsigned __int16 *
0x180024d64  mov     rcx, rdi; this
0x180024d67  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180024d6c  nop
0x180024d6d  mov     rcx, [rbp+lpDirectoryName]
0x180024d71  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024d75  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024d7a  nop
0x180024d7b  mov     rcx, [rbp+var_40]
0x180024d7f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024d83  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024d88  nop
0x180024d89  mov     rcx, [rbp+var_18]
0x180024d8d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024d91  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024d96  mov     eax, ebx
0x180024d98  mov     rcx, [rbp+var_10]
0x180024d9c  xor     rcx, rsp; StackCookie
0x180024d9f  call    __security_check_cookie
0x180024da4  mov     rbx, [rsp+80h+arg_10]
0x180024dac  add     rsp, 80h
0x180024db3  pop     r14
0x180024db5  pop     r13
0x180024db7  pop     rdi
0x180024db8  pop     rsi
0x180024db9  pop     rbp
0x180024dba  retn
```
