# WinREAgent::Executor::CanExecute(WinREAgent::TelemetrySession *)

- ea: `0x180006b20`
- end: `0x180006d4d`
- name: `?CanExecute@Executor@WinREAgent@@QEBA_NPEAVTelemetrySession@2@@Z`
- size: `557`
- prototype: `bool __fastcall(WinREAgent::Executor *__hidden this, struct WinREAgent::TelemetrySession *)`
- caller_count: `7`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800178e0`
- `0x180017b90`
- `0x180017f20`
- `0x1800183f0`
- `0x18001bf30`
- `0x18001c3a0`
- `0x18001c970`

## callees

- `0x1800047f8`
- `0x1800049a4`
- `0x180006b20`
- `0x180008378`
- `0x18000d92c`
- `0x180011ef4`
- `0x18003717c`
- `0x180037344`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x180006bed`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180006bed`
- `KERNEL32!GetLastError` at `0x180006c02`
- `KERNEL32!GetLastError` at `0x180006c02`

## string_xrefs

- `0x180006c2d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006c87`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006cde`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180006b7c`: `NotScheduled`
- `0x180006c34`: `WinREAgent::Executor::CanExecute`
- `0x180006c8e`: `WinREAgent::Executor::CanExecute`
- `0x180006ce5`: `WinREAgent::Executor::CanExecute`
- `0x180006cca`: `Not enough space on target OS volume to service winre`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall WinREAgent::Executor::CanExecute(WinREAgent::Executor *this, struct WinREAgent::TelemetrySession *a2)
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
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+B8h] [rbp+40h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v19,
    (__int64)L"Unknown");
  v4 = 1;
  v18 = 1;
  v13[0] = 0;
  v14 = TraceCanExecuteReason;
  v15 = a2;
  v16 = &v19;
  v17 = &v18;
  if ( !*((_BYTE *)this + 272) )
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
      "WinREAgent::Executor::CanExecute",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1232,
      L"Failed to get free space on target volume [%s]",
      v9);
    v5 = 4;
    v6 = L"Fail";
    goto LABEL_3;
  }
  v20 = 0;
  v11 = WinREAgent::Executor::EstimateDiskSpacePeak((char *)this + 32, (char *)this + 64, &v20);
  if ( v11 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v11,
      "WinREAgent::Executor::CanExecute",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1241,
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
      "WinREAgent::Executor::CanExecute",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1253,
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
0x180006b20  push    rbp
0x180006b22  push    rbx
0x180006b23  push    rsi
0x180006b24  push    rdi
0x180006b25  mov     rbp, rsp
0x180006b28  sub     rsp, 78h
0x180006b2c  mov     rbx, rdx
0x180006b2f  mov     rdi, rcx
0x180006b32  lea     rdx, aUnknown; "Unknown"
0x180006b39  lea     rcx, [rbp+arg_8]
0x180006b3d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180006b42  nop
0x180006b43  mov     esi, 1
0x180006b48  mov     [rbp+arg_0], sil
0x180006b4c  mov     [rbp+var_38], 0
0x180006b50  lea     rax, TraceCanExecuteReason
0x180006b57  mov     [rbp+var_30], rax
0x180006b5b  mov     [rbp+var_28], rbx
0x180006b5f  lea     rax, [rbp+arg_8]
0x180006b63  mov     [rbp+var_20], rax
0x180006b67  lea     rax, [rbp+arg_0]
0x180006b6b  mov     [rbp+var_18], rax
0x180006b6f  cmp     byte ptr [rdi+110h], 0
0x180006b76  jnz     short loc_180006BAB
0x180006b78  lea     r8d, [rsi+0Bh]
0x180006b7c  lea     rdx, aNotscheduled; "NotScheduled"
0x180006b83  lea     rcx, [rbp+arg_8]
0x180006b87  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006b8c  nop
0x180006b8d  lea     rcx, [rbp+var_38]
0x180006b91  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x180006b96  nop
0x180006b97  mov     rcx, [rbp+arg_8]
0x180006b9b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006b9f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006ba4  xor     al, al
0x180006ba6  jmp     loc_180006D44
0x180006bab  mov     rcx, [rdi+198h]
0x180006bb2  cmp     byte ptr [rcx+98h], 0
0x180006bb9  jnz     short loc_180006BD8
0x180006bbb  lea     rdx, aWinreIsNotAvai; "WinRE is not available"
0x180006bc2  xor     ecx, ecx
0x180006bc4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180006bc9  mov     r8d, 15h
0x180006bcf  lea     rdx, aNorecoveryenvi; "NoRecoveryEnvironment"
0x180006bd6  jmp     short loc_180006B83
0x180006bd8  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x180006be0  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180006be4  xor     r8d, r8d; lpTotalNumberOfBytes
0x180006be7  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180006be9  mov     rcx, [rcx+38h]; lpDirectoryName
0x180006bed  call    cs:__imp_GetDiskFreeSpaceExW
0x180006bf3  test    eax, eax
0x180006bf5  jnz     short loc_180006C56
0x180006bf7  mov     rax, [rdi+198h]
0x180006bfe  mov     rbx, [rax+38h]
0x180006c02  call    cs:__imp_GetLastError
0x180006c08  test    eax, eax
0x180006c0a  jle     short loc_180006C14
0x180006c0c  movzx   eax, ax
0x180006c0f  or      eax, 80070000h
0x180006c14  mov     [rsp+78h+var_48], rbx
0x180006c19  lea     rcx, aFailedToGetFre; "Failed to get free space on target volu"...
0x180006c20  mov     [rsp+78h+var_50], rcx
0x180006c25  mov     [rsp+78h+var_58], 4D0h
0x180006c2d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006c34  lea     r8, aWinreagentExec_18; "WinREAgent::Executor::CanExecute"
0x180006c3b  mov     edx, eax
0x180006c3d  mov     ecx, esi
0x180006c3f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006c44  mov     r8d, 4
0x180006c4a  lea     rdx, aFail; "Fail"
0x180006c51  jmp     loc_180006B83
0x180006c56  mov     [rbp+arg_10], 0
0x180006c5e  lea     rdx, [rdi+40h]
0x180006c62  lea     rcx, [rdi+20h]
0x180006c66  lea     r8, [rbp+arg_10]
0x180006c6a  call    ?EstimateDiskSpacePeak@Executor@WinREAgent@@CAJAEBV?$CAtlArray@PEAVOperation@WinREAgent@@V?$CElementTraits@PEAVOperation@WinREAgent@@@ATL@@@ATL@@0AEA_J@Z; WinREAgent::Executor::EstimateDiskSpacePeak(ATL::CAtlArray<WinREAgent::Operation *,ATL::CElementTraits<WinREAgent::Operation *>> const &,ATL::CAtlArray<WinREAgent::Operation *,ATL::CElementTraits<WinREAgent::Operation *>> const &,__int64 &)
0x180006c6f  test    eax, eax
0x180006c71  jns     short loc_180006CB0
0x180006c73  lea     rcx, aFailedToEstima_0; "Failed to estimate disk usage"
0x180006c7a  mov     [rsp+78h+var_50], rcx
0x180006c7f  mov     [rsp+78h+var_58], 4D9h
0x180006c87  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006c8e  lea     r8, aWinreagentExec_18; "WinREAgent::Executor::CanExecute"
0x180006c95  mov     edx, eax
0x180006c97  mov     ecx, esi
0x180006c99  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006c9e  mov     r8d, 17h
0x180006ca4  lea     rdx, aFaileddiskusag; "FailedDiskUsageEstimate"
0x180006cab  jmp     loc_180006B83
0x180006cb0  mov     rcx, [rbp+arg_10]
0x180006cb4  xor     eax, eax
0x180006cb6  test    rcx, rcx
0x180006cb9  cmovle  rcx, rax
0x180006cbd  lea     rax, [rcx+40000000h]
0x180006cc4  cmp     qword ptr [rbp+TotalNumberOfFreeBytes], rax
0x180006cc8  jnb     short loc_180006D13
0x180006cca  lea     rax, aNotEnoughSpace_0; "Not enough space on target OS volume to"...
0x180006cd1  mov     [rsp+78h+var_50], rax
0x180006cd6  mov     [rsp+78h+var_58], 4E5h
0x180006cde  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180006ce5  lea     r8, aWinreagentExec_18; "WinREAgent::Executor::CanExecute"
0x180006cec  mov     edx, 80073CF4h
0x180006cf1  mov     ecx, esi
0x180006cf3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180006cf8  mov     r8d, 15h
0x180006cfe  lea     rdx, aInsufficientfr; "InsufficientFreeSpace"
0x180006d05  lea     rcx, [rbp+arg_8]
0x180006d09  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006d0e  xor     sil, sil
0x180006d11  jmp     short loc_180006D2A
0x180006d13  mov     r8d, 7
0x180006d19  lea     rdx, aSuccess; "Success"
0x180006d20  lea     rcx, [rbp+arg_8]
0x180006d24  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006d29  nop
0x180006d2a  lea     rcx, [rbp+var_38]
0x180006d2e  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x180006d33  nop
0x180006d34  mov     rcx, [rbp+arg_8]
0x180006d38  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006d3c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006d41  mov     al, sil
0x180006d44  add     rsp, 78h
0x180006d48  pop     rdi
0x180006d49  pop     rsi
0x180006d4a  pop     rbx
0x180006d4b  pop     rbp
0x180006d4c  retn
```
