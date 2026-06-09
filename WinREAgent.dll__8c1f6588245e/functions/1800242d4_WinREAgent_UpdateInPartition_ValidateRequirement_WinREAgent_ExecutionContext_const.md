# WinREAgent::UpdateInPartition::ValidateRequirement(WinREAgent::ExecutionContext const *)

- ea: `0x1800242d4`
- end: `0x18002467d`
- name: `?ValidateRequirement@UpdateInPartition@WinREAgent@@AEAAJPEBVExecutionContext@2@@Z`
- size: `937`
- prototype: `__int64 __fastcall(WinREAgent::UpdateInPartition *__hidden this, const struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180023ea0`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x18000d9ec`
- `0x180023c00`
- `0x1800242d4`
- `0x18003717c`
- `0x180037344`
- `0x18004d2ac`
- `0x18004d7a0`
- `0x18004e47c`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024507`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024507`
- `KERNEL32!GetVersionExW` at `0x18002455d`
- `KERNEL32!GetVersionExW` at `0x18002455d`
- `KERNEL32!GetLastError` at `0x180024511`
- `KERNEL32!GetLastError` at `0x180024600`
- `KERNEL32!GetLastError` at `0x180024642`
- `KERNEL32!GetLastError` at `0x180024511`
- `KERNEL32!GetLastError` at `0x180024600`
- `KERNEL32!GetLastError` at `0x180024642`

## string_xrefs

- `0x1800244b3`: `Failed to get current WinRE directory`
- `0x180024355`: `Does not have path to current wim`
- `0x18002430d`: `Does not have path to updated wim`
- `0x180024321`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180024393`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x1800243f2`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x1800244c7`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x1800245dc`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180024628`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180024328`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x18002439a`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x1800243f9`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x1800244ce`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x1800245e3`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x18002462f`: `WinREAgent::UpdateInPartition::ValidateRequirement`
- `0x18002437f`: `Updated WinRE [%s] doesn't exist`
- `0x180024460`: `UpdateInPartition: Current WinRE [%s] doesn't exist`
- `0x180024479`: `UpdateInPartition: Update Wim size [%llu], Current Wim size [%llu]`
- `0x18002459e`: `UpdateInPartition: WinRE partition free space [%llu]`
- `0x1800245af`: `UpdateInPartition: Required free space on recovery partition [%llu]`
- `0x1800245c8`: `Not enough free space on recovery partition to perform the update`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::UpdateInPartition::ValidateRequirement(
        WinREAgent::UpdateInPartition *this,
        const struct WinREAgent::ExecutionContext *a2)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // rbx
  unsigned int Size; // esi
  union _ULARGE_INTEGER v6; // r14
  LPCWSTR v7; // r15
  LPCWSTR v8; // rbx
  signed int v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  __int64 v14; // rdx
  union _ULARGE_INTEGER v15; // rdi
  signed int LastError; // eax
  signed int v17; // eax
  LPCWSTR lpDirectoryName; // [rsp+40h] [rbp-C0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+48h] [rbp-B8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+50h] [rbp-B0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+17Ah] [rbp+7Ah]

  v2 = (_QWORD *)((char *)a2 + 280);
  if ( !*(_DWORD *)(*((_QWORD *)a2 + 35) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::UpdateInPartition::ValidateRequirement",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      91,
      L"Does not have path to updated wim");
    return 2147942487LL;
  }
  v4 = (_QWORD *)((char *)a2 + 120);
  if ( !*(_DWORD *)(*((_QWORD *)a2 + 15) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::UpdateInPartition::ValidateRequirement",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      96,
      L"Does not have path to current wim");
    return 2147942487LL;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)a2 + 280) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942402LL,
      "WinREAgent::UpdateInPartition::ValidateRequirement",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      103,
      L"Updated WinRE [%s] doesn't exist",
      *v2);
    return 2147942402LL;
  }
  lpDirectoryName = 0;
  Size = PushButtonReset::File::GetSize(v2, &lpDirectoryName);
  if ( (Size & 0x80000000) != 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      Size,
      "WinREAgent::UpdateInPartition::ValidateRequirement",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      109,
      L"Failed to get size of [%s]",
      *v2);
    return Size;
  }
  v6.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !(unsigned __int8)PushButtonReset::File::Exists(v4) )
  {
    PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Current WinRE [%s] doesn't exist", *v4);
LABEL_16:
    v7 = lpDirectoryName;
    PushButtonReset::Logging::Trace(
      0,
      L"UpdateInPartition: Update Wim size [%llu], Current Wim size [%llu]",
      lpDirectoryName,
      v6.QuadPart);
    if ( (unsigned __int64)v7 <= v6.QuadPart )
      return Size;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpDirectoryName);
    Size = PushButtonReset::Path::GetDirectory(v4, &lpDirectoryName);
    v8 = lpDirectoryName;
    if ( (Size & 0x80000000) == 0 )
    {
      TotalNumberOfBytes.QuadPart = 0;
      TotalNumberOfFreeBytes.QuadPart = 0;
      if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
      {
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        if ( GetVersionExW(&VersionInformation) )
        {
          v13 = winreEstimateBufferNeededOnPartition_0(TotalNumberOfBytes.LowPart, v10, v11, v12, v22 == 1);
          LOBYTE(v14) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
            v14);
          v15.QuadPart = (ULONGLONG)v7 + v13 - v6.QuadPart;
          PushButtonReset::Logging::Trace(
            0,
            L"UpdateInPartition: WinRE partition free space [%llu]",
            TotalNumberOfFreeBytes.QuadPart);
          PushButtonReset::Logging::Trace(
            0,
            L"UpdateInPartition: Required free space on recovery partition [%llu]",
            v15.QuadPart);
          if ( TotalNumberOfFreeBytes.QuadPart < v15.QuadPart )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942512LL,
              "WinREAgent::UpdateInPartition::ValidateRequirement",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
              178,
              L"Not enough free space on recovery partition to perform the update");
            Size = -2147024784;
          }
          goto LABEL_32;
        }
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "WinREAgent::UpdateInPartition::ValidateRequirement",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
          152,
          L"Failed to get online OS version info");
      }
      else
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "WinREAgent::UpdateInPartition::ValidateRequirement",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
          137,
          L"Failed to get space info for recovery partition");
      }
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      Size = v17;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        Size,
        "WinREAgent::UpdateInPartition::ValidateRequirement",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
        130,
        L"Failed to get current WinRE directory");
    }
LABEL_32:
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
    return Size;
  }
  Size = PushButtonReset::File::GetSize(v4, &TotalNumberOfFreeBytes);
  if ( (Size & 0x80000000) == 0 )
  {
    v6 = TotalNumberOfFreeBytes;
    goto LABEL_16;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    Size,
    "WinREAgent::UpdateInPartition::ValidateRequirement",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
    115,
    L"Failed to get size of [%s]",
    *v4);
  return Size;
}

```

## disassembly

```asm
0x1800242d4  push    rbp
0x1800242d6  push    rbx
0x1800242d7  push    rsi
0x1800242d8  push    rdi
0x1800242d9  push    r14
0x1800242db  push    r15
0x1800242dd  lea     rbp, [rsp-98h]
0x1800242e5  sub     rsp, 198h
0x1800242ec  mov     rax, cs:__security_cookie
0x1800242f3  xor     rax, rsp
0x1800242f6  mov     [rbp+0C0h+var_40], rax
0x1800242fd  lea     rdi, [rdx+118h]
0x180024304  mov     rax, [rdi]
0x180024307  cmp     dword ptr [rax-10h], 0
0x18002430b  jnz     short loc_180024348
0x18002430d  lea     rax, aDoesNotHavePat; "Does not have path to updated wim"
0x180024314  mov     [rsp+1C0h+var_198], rax
0x180024319  mov     [rsp+1C0h+var_1A0], 5Bh ; '['
0x180024321  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024328  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x18002432f  mov     edx, 80070057h
0x180024334  mov     ecx, 2
0x180024339  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002433e  mov     eax, 80070057h
0x180024343  jmp     loc_18002465E
0x180024348  lea     rbx, [rdx+78h]
0x18002434c  mov     rax, [rbx]
0x18002434f  cmp     dword ptr [rax-10h], 0
0x180024353  jnz     short loc_18002436B
0x180024355  lea     rax, aDoesNotHavePat_0; "Does not have path to current wim"
0x18002435c  mov     [rsp+1C0h+var_198], rax
0x180024361  mov     [rsp+1C0h+var_1A0], 60h ; '`'
0x180024369  jmp     short loc_180024321
0x18002436b  mov     rcx, rdi
0x18002436e  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180024373  test    al, al
0x180024375  jnz     short loc_1800243BA
0x180024377  mov     rax, [rdi]
0x18002437a  mov     [rsp+1C0h+var_190], rax
0x18002437f  lea     rax, aUpdatedWinreSD; "Updated WinRE [%s] doesn't exist"
0x180024386  mov     [rsp+1C0h+var_198], rax
0x18002438b  mov     [rsp+1C0h+var_1A0], 67h ; 'g'
0x180024393  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002439a  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x1800243a1  mov     edx, 80070002h
0x1800243a6  mov     ecx, 2
0x1800243ab  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800243b0  mov     eax, 80070002h
0x1800243b5  jmp     loc_18002465E
0x1800243ba  mov     [rsp+1C0h+lpDirectoryName], 0
0x1800243c3  lea     rdx, [rsp+1C0h+lpDirectoryName]
0x1800243c8  mov     rcx, rdi
0x1800243cb  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x1800243d0  mov     esi, eax
0x1800243d2  test    eax, eax
0x1800243d4  jns     short loc_180024411
0x1800243d6  mov     rcx, [rdi]
0x1800243d9  mov     [rsp+1C0h+var_190], rcx
0x1800243de  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x1800243e5  mov     [rsp+1C0h+var_198], rax
0x1800243ea  mov     [rsp+1C0h+var_1A0], 6Dh ; 'm'
0x1800243f2  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800243f9  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x180024400  mov     edx, esi
0x180024402  mov     ecx, 2
0x180024407  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002440c  jmp     loc_18002465C
0x180024411  xor     r14d, r14d
0x180024414  mov     qword ptr [rsp+1C0h+TotalNumberOfFreeBytes], r14
0x180024419  mov     rcx, rbx
0x18002441c  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180024421  test    al, al
0x180024423  jz      short loc_18002445D
0x180024425  lea     rdx, [rsp+1C0h+TotalNumberOfFreeBytes]
0x18002442a  mov     rcx, rbx
0x18002442d  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180024432  mov     esi, eax
0x180024434  test    eax, eax
0x180024436  jns     short loc_180024456
0x180024438  mov     rax, [rbx]
0x18002443b  mov     [rsp+1C0h+var_190], rax
0x180024440  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x180024447  mov     [rsp+1C0h+var_198], rax
0x18002444c  mov     [rsp+1C0h+var_1A0], 73h ; 's'
0x180024454  jmp     short loc_1800243F2
0x180024456  mov     r14, qword ptr [rsp+1C0h+TotalNumberOfFreeBytes]
0x18002445b  jmp     short loc_18002446E
0x18002445d  mov     r8, [rbx]
0x180024460  lea     rdx, aUpdateinpartit_9; "UpdateInPartition: Current WinRE [%s] d"...
0x180024467  xor     ecx, ecx
0x180024469  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002446e  mov     r9, r14
0x180024471  mov     r15, [rsp+1C0h+lpDirectoryName]
0x180024476  mov     r8, r15
0x180024479  lea     rdx, aUpdateinpartit_1; "UpdateInPartition: Update Wim size [%ll"...
0x180024480  xor     ecx, ecx
0x180024482  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024487  cmp     r15, r14
0x18002448a  jbe     loc_18002465C
0x180024490  lea     rcx, [rsp+1C0h+lpDirectoryName]
0x180024495  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002449a  nop
0x18002449b  lea     rdx, [rsp+1C0h+lpDirectoryName]
0x1800244a0  mov     rcx, rbx
0x1800244a3  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800244a8  mov     esi, eax
0x1800244aa  mov     rbx, [rsp+1C0h+lpDirectoryName]
0x1800244af  test    eax, eax
0x1800244b1  jns     short loc_1800244E6
0x1800244b3  lea     rax, aFailedToGetCur_1; "Failed to get current WinRE directory"
0x1800244ba  mov     [rsp+1C0h+var_198], rax
0x1800244bf  mov     [rsp+1C0h+var_1A0], 82h
0x1800244c7  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800244ce  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x1800244d5  mov     edx, esi
0x1800244d7  mov     ecx, 2
0x1800244dc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800244e1  jmp     loc_180024653
0x1800244e6  mov     qword ptr [rsp+1C0h+TotalNumberOfBytes], 0
0x1800244ef  mov     qword ptr [rsp+1C0h+TotalNumberOfFreeBytes], 0
0x1800244f8  lea     r9, [rsp+1C0h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800244fd  lea     r8, [rsp+1C0h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180024502  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180024504  mov     rcx, rbx; lpDirectoryName
0x180024507  call    cs:__imp_GetDiskFreeSpaceExW
0x18002450d  test    eax, eax
0x18002450f  jnz     short loc_18002453E
0x180024511  call    cs:__imp_GetLastError
0x180024517  mov     edi, 80070000h
0x18002451c  test    eax, eax
0x18002451e  jle     short loc_180024525
0x180024520  movzx   eax, ax
0x180024523  or      eax, edi
0x180024525  lea     rcx, aFailedToGetSpa; "Failed to get space info for recovery p"...
0x18002452c  mov     [rsp+1C0h+var_198], rcx
0x180024531  mov     [rsp+1C0h+var_1A0], 89h
0x180024539  jmp     loc_180024628
0x18002453e  xor     edx, edx; Val
0x180024540  mov     r8d, 118h; Size
0x180024546  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x18002454b  call    memset_0
0x180024550  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180024558  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x18002455d  call    cs:__imp_GetVersionExW
0x180024563  test    eax, eax
0x180024565  jz      loc_180024600
0x18002456b  xor     eax, eax
0x18002456d  cmp     [rbp+0C0h+var_46], 1
0x180024571  setz    al
0x180024574  mov     [rsp+1C0h+var_1A0], eax
0x180024578  mov     rcx, qword ptr [rsp+1C0h+TotalNumberOfBytes]
0x18002457d  call    winreEstimateBufferNeededOnPartition_0
0x180024582  mov     rdi, rax
0x180024585  mov     dl, 1
0x180024587  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x18002458e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180024593  sub     rdi, r14
0x180024596  add     rdi, r15
0x180024599  mov     r8, qword ptr [rsp+1C0h+TotalNumberOfFreeBytes]
0x18002459e  lea     rdx, aUpdateinpartit_8; "UpdateInPartition: WinRE partition free"...
0x1800245a5  xor     ecx, ecx
0x1800245a7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800245ac  mov     r8, rdi
0x1800245af  lea     rdx, aUpdateinpartit; "UpdateInPartition: Required free space "...
0x1800245b6  xor     ecx, ecx
0x1800245b8  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800245bd  cmp     qword ptr [rsp+1C0h+TotalNumberOfFreeBytes], rdi
0x1800245c2  jnb     loc_180024653
0x1800245c8  lea     rax, aNotEnoughFreeS; "Not enough free space on recovery parti"...
0x1800245cf  mov     [rsp+1C0h+var_198], rax
0x1800245d4  mov     [rsp+1C0h+var_1A0], 0B2h
0x1800245dc  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800245e3  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x1800245ea  mov     edx, 80070070h
0x1800245ef  mov     ecx, 2
0x1800245f4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800245f9  mov     esi, 80070070h
0x1800245fe  jmp     short loc_180024653
0x180024600  call    cs:__imp_GetLastError
0x180024606  mov     edi, 80070000h
0x18002460b  test    eax, eax
0x18002460d  jle     short loc_180024614
0x18002460f  movzx   eax, ax
0x180024612  or      eax, edi
0x180024614  lea     rcx, aFailedToGetOnl; "Failed to get online OS version info"
0x18002461b  mov     [rsp+1C0h+var_198], rcx
0x180024620  mov     [rsp+1C0h+var_1A0], 98h
0x180024628  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002462f  lea     r8, aWinreagentUpda_3; "WinREAgent::UpdateInPartition::Validate"...
0x180024636  mov     edx, eax
0x180024638  mov     ecx, 2
0x18002463d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024642  call    cs:__imp_GetLastError
0x180024648  test    eax, eax
0x18002464a  jle     short loc_180024651
0x18002464c  movzx   eax, ax
0x18002464f  or      eax, edi
0x180024651  mov     esi, eax
0x180024653  lea     rcx, [rbx-18h]; this
0x180024657  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002465c  mov     eax, esi
0x18002465e  mov     rcx, [rbp+0C0h+var_40]
0x180024665  xor     rcx, rsp; StackCookie
0x180024668  call    __security_check_cookie
0x18002466d  add     rsp, 198h
0x180024674  pop     r15
0x180024676  pop     r14
0x180024678  pop     rdi
0x180024679  pop     rsi
0x18002467a  pop     rbx
0x18002467b  pop     rbp
0x18002467c  retn
```
