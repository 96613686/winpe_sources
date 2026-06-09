# LogWinREStatusOnComplete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::TelemetrySession *)

- ea: `0x18000bd58`
- end: `0x18000bef6`
- name: `?LogWinREStatusOnComplete@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVTelemetrySession@WinREAgent@@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007570`

## callees

- `0x180004af8`
- `0x18000bd58`
- `0x18000d92c`
- `0x18002f038`
- `0x18003717c`
- `0x180037344`
- `0x18004d7a0`
- `0x18004e47c`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000be2f`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000be2f`
- `KERNEL32!GetLastError` at `0x18000be39`
- `KERNEL32!GetLastError` at `0x18000be7b`
- `KERNEL32!GetLastError` at `0x18000be39`
- `KERNEL32!GetLastError` at `0x18000be7b`

## string_xrefs

- `0x18000bdb0`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000be03`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000be61`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000bdb7`: `LogWinREStatusOnComplete`
- `0x18000be0a`: `LogWinREStatusOnComplete`
- `0x18000be68`: `LogWinREStatusOnComplete`
- `0x18000bdef`: `Failed to get current WinRE directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogWinREStatusOnComplete(_QWORD *a1, WinREAgent::TelemetrySession *a2)
{
  int Size; // edi
  LPCWSTR v5; // rbx
  signed int LastError; // eax
  signed int v7; // eax
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpDirectoryName; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int64 v11; // [rsp+80h] [rbp+30h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+88h] [rbp+38h] BYREF

  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v11 = 0;
  Size = PushButtonReset::File::GetSize(a1, &v11);
  if ( Size >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpDirectoryName);
    Size = PushButtonReset::Path::GetDirectory(a1, &lpDirectoryName);
    v5 = lpDirectoryName;
    if ( Size >= 0 )
    {
      if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
      {
        PushButtonReset::Logging::Trace(0, L"WinRE partition total space [%llu]", TotalNumberOfBytes.QuadPart);
        PushButtonReset::Logging::Trace(0, L"WinRE partition free space [%llu]", TotalNumberOfFreeBytes.QuadPart);
        PushButtonReset::Logging::Trace(0, L"WinRE size [%llu]", v11);
        if ( a2 )
          WinREAgent::TelemetrySession::TraceWinREPartitionInfoOnComplete(
            a2,
            TotalNumberOfBytes.QuadPart,
            TotalNumberOfFreeBytes.QuadPart,
            v11);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "LogWinREStatusOnComplete",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1495,
          L"Failed to get space info for recovery partition");
        v7 = GetLastError();
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        Size = v7;
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "LogWinREStatusOnComplete",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1491,
        L"Failed to get current WinRE directory");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "LogWinREStatusOnComplete",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1487,
      L"Failed to get size of [%s]",
      *a1);
  }
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18000bd58  mov     [rsp-18h+arg_0], rbx
0x18000bd5d  push    rbp
0x18000bd5e  push    rsi
0x18000bd5f  push    rdi
0x18000bd60  mov     rbp, rsp
0x18000bd63  sub     rsp, 50h
0x18000bd67  mov     rsi, rdx
0x18000bd6a  mov     rbx, rcx
0x18000bd6d  mov     qword ptr [rbp+TotalNumberOfBytes], 0
0x18000bd75  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x18000bd7d  mov     [rbp+arg_10], 0
0x18000bd85  lea     rdx, [rbp+arg_10]
0x18000bd89  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18000bd8e  mov     edi, eax
0x18000bd90  test    eax, eax
0x18000bd92  jns     short loc_18000BDCF
0x18000bd94  mov     rcx, [rbx]
0x18000bd97  mov     [rsp+50h+var_20], rcx
0x18000bd9c  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x18000bda3  mov     [rsp+50h+var_28], rax
0x18000bda8  mov     [rsp+50h+var_30], 5CFh
0x18000bdb0  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000bdb7  lea     r8, aLogwinrestatus; "LogWinREStatusOnComplete"
0x18000bdbe  mov     edx, edi
0x18000bdc0  mov     ecx, 2
0x18000bdc5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000bdca  jmp     loc_18000BEE7
0x18000bdcf  lea     rcx, [rbp+lpDirectoryName]
0x18000bdd3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000bdd8  nop
0x18000bdd9  lea     rdx, [rbp+lpDirectoryName]
0x18000bddd  mov     rcx, rbx
0x18000bde0  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000bde5  mov     edi, eax
0x18000bde7  mov     rbx, [rbp+lpDirectoryName]
0x18000bdeb  test    eax, eax
0x18000bded  jns     short loc_18000BE22
0x18000bdef  lea     rax, aFailedToGetCur_1; "Failed to get current WinRE directory"
0x18000bdf6  mov     [rsp+50h+var_28], rax
0x18000bdfb  mov     [rsp+50h+var_30], 5D3h
0x18000be03  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000be0a  lea     r8, aLogwinrestatus; "LogWinREStatusOnComplete"
0x18000be11  mov     edx, edi
0x18000be13  mov     ecx, 2
0x18000be18  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000be1d  jmp     loc_18000BEDE
0x18000be22  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18000be26  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18000be2a  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18000be2c  mov     rcx, rbx; lpDirectoryName
0x18000be2f  call    cs:__imp_GetDiskFreeSpaceExW
0x18000be35  test    eax, eax
0x18000be37  jnz     short loc_18000BE8E
0x18000be39  call    cs:__imp_GetLastError
0x18000be3f  mov     edi, 80070000h
0x18000be44  test    eax, eax
0x18000be46  jle     short loc_18000BE4D
0x18000be48  movzx   eax, ax
0x18000be4b  or      eax, edi
0x18000be4d  lea     rcx, aFailedToGetSpa; "Failed to get space info for recovery p"...
0x18000be54  mov     [rsp+50h+var_28], rcx
0x18000be59  mov     [rsp+50h+var_30], 5D7h
0x18000be61  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000be68  lea     r8, aLogwinrestatus; "LogWinREStatusOnComplete"
0x18000be6f  mov     edx, eax
0x18000be71  mov     ecx, 2
0x18000be76  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000be7b  call    cs:__imp_GetLastError
0x18000be81  test    eax, eax
0x18000be83  jle     short loc_18000BE8A
0x18000be85  movzx   eax, ax
0x18000be88  or      eax, edi
0x18000be8a  mov     edi, eax
0x18000be8c  jmp     short loc_18000BEDE
0x18000be8e  mov     r8, qword ptr [rbp+TotalNumberOfBytes]
0x18000be92  lea     rdx, aWinrePartition_4; "WinRE partition total space [%llu]"
0x18000be99  xor     ecx, ecx
0x18000be9b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000bea0  mov     r8, qword ptr [rbp+TotalNumberOfFreeBytes]
0x18000bea4  lea     rdx, aWinrePartition; "WinRE partition free space [%llu]"
0x18000beab  xor     ecx, ecx
0x18000bead  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000beb2  mov     r8, [rbp+arg_10]
0x18000beb6  lea     rdx, aWinreSizeLlu; "WinRE size [%llu]"
0x18000bebd  xor     ecx, ecx
0x18000bebf  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000bec4  test    rsi, rsi
0x18000bec7  jz      short loc_18000BEDE
0x18000bec9  mov     r9, [rbp+arg_10]; unsigned __int64
0x18000becd  mov     r8, qword ptr [rbp+TotalNumberOfFreeBytes]; unsigned __int64
0x18000bed1  mov     rdx, qword ptr [rbp+TotalNumberOfBytes]; unsigned __int64
0x18000bed5  mov     rcx, rsi; this
0x18000bed8  call    ?TraceWinREPartitionInfoOnComplete@TelemetrySession@WinREAgent@@QEBAX_K00@Z; WinREAgent::TelemetrySession::TraceWinREPartitionInfoOnComplete(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000bedd  nop
0x18000bede  lea     rcx, [rbx-18h]; this
0x18000bee2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000bee7  mov     eax, edi
0x18000bee9  mov     rbx, [rsp+50h+arg_0]
0x18000beee  add     rsp, 50h
0x18000bef2  pop     rdi
0x18000bef3  pop     rsi
0x18000bef4  pop     rbp
0x18000bef5  retn
```
