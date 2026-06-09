# WinREAgent::Executor::CanCommit(WinREAgent::TelemetrySession *)

- ea: `0x1800068f0`
- end: `0x180006b19`
- name: `?CanCommit@Executor@WinREAgent@@AEBA_NPEAVTelemetrySession@2@@Z`
- size: `553`
- prototype: `bool __fastcall(WinREAgent::Executor *__hidden this, struct WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x1800047f8`
- `0x1800049a4`
- `0x1800068f0`
- `0x18000856c`
- `0x18000d92c`
- `0x180011ef4`
- `0x18003717c`
- `0x180037344`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800069bd`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800069bd`
- `KERNEL32!GetLastError` at `0x1800069d2`
- `KERNEL32!GetLastError` at `0x1800069d2`

## string_xrefs

- `0x1800069fd`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006a53`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006aaa`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000694c`: `NotScheduled`
- `0x180006a96`: `Not enough space on target OS volume to service winre`
- `0x180006a04`: `WinREAgent::Executor::CanCommit`
- `0x180006a5a`: `WinREAgent::Executor::CanCommit`
- `0x180006ab1`: `WinREAgent::Executor::CanCommit`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall WinREAgent::Executor::CanCommit(WinREAgent::Executor *this, struct WinREAgent::TelemetrySession *a2)
{
  char v4; // si
  __int64 v5; // r8
  const wchar_t *v6; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  signed int LastError; // eax
  int v11; // eax
  __int64 v12; // rcx
  _BYTE v13[8]; // [rsp+40h] [rbp-38h] BYREF
  __int64 (__fastcall *v14)(); // [rsp+48h] [rbp-30h]
  struct WinREAgent::TelemetrySession *v15; // [rsp+50h] [rbp-28h]
  __int64 *v16; // [rsp+58h] [rbp-20h]
  char *v17; // [rsp+60h] [rbp-18h]
  char v18; // [rsp+A0h] [rbp+28h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+30h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+38h] BYREF
  _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+B8h] [rbp+40h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v19,
    (__int64)L"Unknown");
  v4 = 1;
  v18 = 1;
  v13[0] = 0;
  v14 = TraceCanCommitReason;
  v15 = a2;
  v16 = &v19;
  v17 = &v18;
  if ( !*((_BYTE *)this + 304) )
  {
    v5 = 12;
    v6 = L"NotScheduled";
LABEL_3:
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, v6, v5);
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v13);
    ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
    return 0;
  }
  v8 = *((_QWORD *)this + 51);
  if ( !*(_BYTE *)(v8 + 152) )
  {
    PushButtonReset::Logging::Trace(0, L"WinRE is not available");
    v5 = 21;
    v6 = L"NoRecoveryEnvironment";
    goto LABEL_3;
  }
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !GetDiskFreeSpaceExW(*(LPCWSTR *)(v8 + 56), 0, 0, &TotalNumberOfFreeBytes) )
  {
    v9 = *(_QWORD *)(*((_QWORD *)this + 51) + 56LL);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)LastError,
      "WinREAgent::Executor::CanCommit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1295,
      L"Failed to get free space on target volume [%s]",
      v9);
    v5 = 4;
    v6 = L"Fail";
    goto LABEL_3;
  }
  v20 = 0;
  v11 = WinREAgent::Executor::EstimateDiskSpacePeak((char *)this + 64, &v20);
  if ( v11 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v11,
      "WinREAgent::Executor::CanCommit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1304,
      L"Failed to estimate disk usage");
    v5 = 23;
    v6 = L"FailedDiskUsageEstimate";
    goto LABEL_3;
  }
  v12 = v20;
  if ( v20 <= 0 )
    v12 = 0;
  if ( TotalNumberOfFreeBytes.QuadPart >= v12 + 0x40000000 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, L"Success", 7);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      1,
      2147958004LL,
      "WinREAgent::Executor::CanCommit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1316,
      L"Not enough space on target OS volume to service winre");
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, L"InsufficientFreeSpace", 21);
    v4 = 0;
  }
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v13);
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  return v4;
}

```

## disassembly

```asm
0x1800068f0  push    rbp
0x1800068f2  push    rbx
0x1800068f3  push    rsi
0x1800068f4  push    rdi
0x1800068f5  mov     rbp, rsp
0x1800068f8  sub     rsp, 78h
0x1800068fc  mov     rbx, rdx
0x1800068ff  mov     rdi, rcx
0x180006902  lea     rdx, aUnknown; "Unknown"
0x180006909  lea     rcx, [rbp+arg_8]
0x18000690d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006912  nop
0x180006913  mov     esi, 1
0x180006918  mov     [rbp+arg_0], sil
0x18000691c  mov     [rbp+var_38], 0
0x180006920  lea     rax, TraceCanCommitReason
0x180006927  mov     [rbp+var_30], rax
0x18000692b  mov     [rbp+var_28], rbx
0x18000692f  lea     rax, [rbp+arg_8]
0x180006933  mov     [rbp+var_20], rax
0x180006937  lea     rax, [rbp+arg_0]
0x18000693b  mov     [rbp+var_18], rax
0x18000693f  cmp     byte ptr [rdi+130h], 0
0x180006946  jnz     short loc_18000697B
0x180006948  lea     r8d, [rsi+0Bh]
0x18000694c  lea     rdx, aNotscheduled; "NotScheduled"
0x180006953  lea     rcx, [rbp+arg_8]
0x180006957  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000695c  nop
0x18000695d  lea     rcx, [rbp+var_38]
0x180006961  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x180006966  nop
0x180006967  mov     rcx, [rbp+arg_8]
0x18000696b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000696f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006974  xor     al, al
0x180006976  jmp     loc_180006B10
0x18000697b  mov     rcx, [rdi+198h]
0x180006982  cmp     byte ptr [rcx+98h], 0
0x180006989  jnz     short loc_1800069A8
0x18000698b  lea     rdx, aWinreIsNotAvai; "WinRE is not available"
0x180006992  xor     ecx, ecx
0x180006994  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006999  mov     r8d, 15h
0x18000699f  lea     rdx, aNorecoveryenvi; "NoRecoveryEnvironment"
0x1800069a6  jmp     short loc_180006953
0x1800069a8  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x1800069b0  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800069b4  xor     r8d, r8d; lpTotalNumberOfBytes
0x1800069b7  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1800069b9  mov     rcx, [rcx+38h]; lpDirectoryName
0x1800069bd  call    cs:__imp_GetDiskFreeSpaceExW
0x1800069c3  test    eax, eax
0x1800069c5  jnz     short loc_180006A26
0x1800069c7  mov     rax, [rdi+198h]
0x1800069ce  mov     rbx, [rax+38h]
0x1800069d2  call    cs:__imp_GetLastError
0x1800069d8  test    eax, eax
0x1800069da  jle     short loc_1800069E4
0x1800069dc  movzx   eax, ax
0x1800069df  or      eax, 80070000h
0x1800069e4  mov     [rsp+78h+var_48], rbx
0x1800069e9  lea     rcx, aFailedToGetFre; "Failed to get free space on target volu"...
0x1800069f0  mov     [rsp+78h+var_50], rcx
0x1800069f5  mov     [rsp+78h+var_58], 50Fh
0x1800069fd  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006a04  lea     r8, aWinreagentExec_4; "WinREAgent::Executor::CanCommit"
0x180006a0b  mov     edx, eax
0x180006a0d  mov     ecx, esi
0x180006a0f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006a14  mov     r8d, 4
0x180006a1a  lea     rdx, aFail; "Fail"
0x180006a21  jmp     loc_180006953
0x180006a26  mov     [rbp+arg_10], 0
0x180006a2e  lea     rcx, [rdi+40h]
0x180006a32  lea     rdx, [rbp+arg_10]
0x180006a36  call    ?EstimateDiskSpacePeak@Executor@WinREAgent@@CAJAEBV?$CAtlArray@PEAVOperation@WinREAgent@@V?$CElementTraits@PEAVOperation@WinREAgent@@@ATL@@@ATL@@AEA_J@Z; WinREAgent::Executor::EstimateDiskSpacePeak(ATL::CAtlArray<WinREAgent::Operation *,ATL::CElementTraits<WinREAgent::Operation *>> const &,__int64 &)
0x180006a3b  test    eax, eax
0x180006a3d  jns     short loc_180006A7C
0x180006a3f  lea     rcx, aFailedToEstima_0; "Failed to estimate disk usage"
0x180006a46  mov     [rsp+78h+var_50], rcx
0x180006a4b  mov     [rsp+78h+var_58], 518h
0x180006a53  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006a5a  lea     r8, aWinreagentExec_4; "WinREAgent::Executor::CanCommit"
0x180006a61  mov     edx, eax
0x180006a63  mov     ecx, esi
0x180006a65  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006a6a  mov     r8d, 17h
0x180006a70  lea     rdx, aFaileddiskusag; "FailedDiskUsageEstimate"
0x180006a77  jmp     loc_180006953
0x180006a7c  mov     rcx, [rbp+arg_10]
0x180006a80  xor     eax, eax
0x180006a82  test    rcx, rcx
0x180006a85  cmovle  rcx, rax
0x180006a89  lea     rax, [rcx+40000000h]
0x180006a90  cmp     qword ptr [rbp+TotalNumberOfFreeBytes], rax
0x180006a94  jnb     short loc_180006ADF
0x180006a96  lea     rax, aNotEnoughSpace_0; "Not enough space on target OS volume to"...
0x180006a9d  mov     [rsp+78h+var_50], rax
0x180006aa2  mov     [rsp+78h+var_58], 524h
0x180006aaa  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006ab1  lea     r8, aWinreagentExec_4; "WinREAgent::Executor::CanCommit"
0x180006ab8  mov     edx, 80073CF4h
0x180006abd  mov     ecx, esi
0x180006abf  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006ac4  mov     r8d, 15h
0x180006aca  lea     rdx, aInsufficientfr; "InsufficientFreeSpace"
0x180006ad1  lea     rcx, [rbp+arg_8]
0x180006ad5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006ada  xor     sil, sil
0x180006add  jmp     short loc_180006AF6
0x180006adf  mov     r8d, 7
0x180006ae5  lea     rdx, aSuccess; "Success"
0x180006aec  lea     rcx, [rbp+arg_8]
0x180006af0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006af5  nop
0x180006af6  lea     rcx, [rbp+var_38]
0x180006afa  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x180006aff  nop
0x180006b00  mov     rcx, [rbp+arg_8]
0x180006b04  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006b08  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006b0d  mov     al, sil
0x180006b10  add     rsp, 78h
0x180006b14  pop     rdi
0x180006b15  pop     rsi
0x180006b16  pop     rbx
0x180006b17  pop     rbp
0x180006b18  retn
```
