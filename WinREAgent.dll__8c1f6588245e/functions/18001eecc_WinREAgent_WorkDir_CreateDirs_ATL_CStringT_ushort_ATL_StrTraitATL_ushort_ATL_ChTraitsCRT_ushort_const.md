# WinREAgent::WorkDir::CreateDirs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18001eecc`
- end: `0x18001f0dd`
- name: `?CreateDirs@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180019904`
- `0x18001b268`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x18001ed24`
- `0x18001eecc`
- `0x18001f228`
- `0x18001f2c4`
- `0x180037344`
- `0x18004bb04`
- `0x18004c034`
- `0x18004d1fc`

## string_xrefs

- `0x18001f07e`: `Failed to create dir [%s]`
- `0x18001eefa`: `Failed to get root winreagent dir`
- `0x18001ef0e`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001ef6d`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001efc1`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001f007`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001f092`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001ef15`: `WinREAgent::WorkDir::CreateDirs`
- `0x18001ef74`: `WinREAgent::WorkDir::CreateDirs`
- `0x18001efc8`: `WinREAgent::WorkDir::CreateDirs`
- `0x18001f00e`: `WinREAgent::WorkDir::CreateDirs`
- `0x18001f099`: `WinREAgent::WorkDir::CreateDirs`
- `0x18001eff3`: `Failed to create root dir [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::WorkDir::CreateDirs(__int64 a1)
{
  int RootDir; // ebx
  int v4; // eax
  __int64 v5; // rdi
  int v6; // esi
  __int64 v7; // rbx
  ATL::CStringData *v8; // rcx
  __int64 v9; // rbx
  ATL::CStringData *v10; // rcx
  __int64 v11; // [rsp+68h] [rbp+28h] BYREF
  __int64 v12; // [rsp+70h] [rbp+30h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
  RootDir = WinREAgent::WorkDir::GetRootDir(a1, &v12);
  if ( RootDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)RootDir,
      "WinREAgent::WorkDir::CreateDirs",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
      41,
      L"Failed to get root winreagent dir");
LABEL_3:
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
    return (unsigned int)RootDir;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v11);
  RootDir = WinREAgent::WorkDir::GetScratchDir(a1, &v11);
  if ( RootDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)RootDir,
      "WinREAgent::WorkDir::CreateDirs",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
      45,
      L"Failed to get scratch dir");
    ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
    goto LABEL_3;
  }
  v4 = WinREAgent::WorkDir::CleanupScratchDir(&v11);
  v5 = v11;
  if ( v4 < 0 )
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v4,
      "WinREAgent::WorkDir::CreateDirs",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
      51,
      L"Failed to cleanup scratch dir [%s]",
      v11);
  v6 = PushButtonReset::Directory::CreateWorkingRoot(&v12);
  if ( v6 >= 0 )
  {
    if ( (unsigned __int8)PushButtonReset::Directory::Exists(&v11)
      || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v13,
            &pszFormat),
          v6 = PushButtonReset::Directory::Create(&v11, 0, &v13),
          ATL::CStringData::Release((ATL::CStringData *)(v13 - 24)),
          v6 >= 0) )
    {
      v10 = (ATL::CStringData *)(v11 - 24);
    }
    else
    {
      v9 = v11;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v6,
        "WinREAgent::WorkDir::CreateDirs",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
        61,
        L"Failed to create dir [%s]",
        v11);
      v10 = (ATL::CStringData *)(v9 - 24);
    }
    ATL::CStringData::Release(v10);
    v8 = (ATL::CStringData *)(v12 - 24);
  }
  else
  {
    v7 = v12;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v6,
      "WinREAgent::WorkDir::CreateDirs",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
      56,
      L"Failed to create root dir [%s]",
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 24));
    v8 = (ATL::CStringData *)(v7 - 24);
  }
  ATL::CStringData::Release(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001eecc  mov     [rsp-18h+arg_0], rbx
0x18001eed1  push    rbp
0x18001eed2  push    rsi
0x18001eed3  push    rdi
0x18001eed4  mov     rbp, rsp
0x18001eed7  sub     rsp, 40h
0x18001eedb  mov     rdi, rcx
0x18001eede  lea     rcx, [rbp+arg_10]
0x18001eee2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001eee7  nop
0x18001eee8  lea     rdx, [rbp+arg_10]
0x18001eeec  mov     rcx, rdi
0x18001eeef  call    ?GetRootDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetRootDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001eef4  mov     ebx, eax
0x18001eef6  test    eax, eax
0x18001eef8  jns     short loc_18001EF3D
0x18001eefa  lea     rax, aFailedToGetRoo_0; "Failed to get root winreagent dir"
0x18001ef01  mov     [rsp+40h+var_18], rax
0x18001ef06  mov     [rsp+40h+var_20], 29h ; ')'
0x18001ef0e  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001ef15  lea     r8, aWinreagentWork_2; "WinREAgent::WorkDir::CreateDirs"
0x18001ef1c  mov     edx, ebx
0x18001ef1e  mov     ecx, 2
0x18001ef23  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001ef28  nop
0x18001ef29  mov     rcx, [rbp+arg_10]
0x18001ef2d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ef31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ef36  mov     eax, ebx
0x18001ef38  jmp     loc_18001F0D0
0x18001ef3d  lea     rcx, [rbp+arg_8]
0x18001ef41  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001ef46  nop
0x18001ef47  lea     rdx, [rbp+arg_8]
0x18001ef4b  mov     rcx, rdi
0x18001ef4e  call    ?GetScratchDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetScratchDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001ef53  mov     ebx, eax
0x18001ef55  test    eax, eax
0x18001ef57  jns     short loc_18001EF97
0x18001ef59  lea     rax, aFailedToGetScr; "Failed to get scratch dir"
0x18001ef60  mov     [rsp+40h+var_18], rax
0x18001ef65  mov     [rsp+40h+var_20], 2Dh ; '-'
0x18001ef6d  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001ef74  lea     r8, aWinreagentWork_2; "WinREAgent::WorkDir::CreateDirs"
0x18001ef7b  mov     edx, ebx
0x18001ef7d  mov     ecx, 2
0x18001ef82  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001ef87  nop
0x18001ef88  mov     rcx, [rbp+arg_8]
0x18001ef8c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ef90  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ef95  jmp     short loc_18001EF29
0x18001ef97  lea     rcx, [rbp+arg_8]
0x18001ef9b  call    ?CleanupScratchDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::WorkDir::CleanupScratchDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001efa0  mov     rdi, [rbp+arg_8]
0x18001efa4  test    eax, eax
0x18001efa6  jns     short loc_18001EFDB
0x18001efa8  mov     [rsp+40h+var_10], rdi
0x18001efad  lea     rcx, aFailedToCleanu; "Failed to cleanup scratch dir [%s]"
0x18001efb4  mov     [rsp+40h+var_18], rcx
0x18001efb9  mov     [rsp+40h+var_20], 33h ; '3'
0x18001efc1  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001efc8  lea     r8, aWinreagentWork_2; "WinREAgent::WorkDir::CreateDirs"
0x18001efcf  mov     edx, eax
0x18001efd1  mov     ecx, 1
0x18001efd6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001efdb  lea     rcx, [rbp+arg_10]
0x18001efdf  call    ?CreateWorkingRoot@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::CreateWorkingRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001efe4  mov     esi, eax
0x18001efe6  test    eax, eax
0x18001efe8  jns     short loc_18001F035
0x18001efea  mov     rbx, [rbp+arg_10]
0x18001efee  mov     [rsp+40h+var_10], rbx
0x18001eff3  lea     rax, aFailedToCreate_17; "Failed to create root dir [%s]"
0x18001effa  mov     [rsp+40h+var_18], rax
0x18001efff  mov     [rsp+40h+var_20], 38h ; '8'
0x18001f007  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001f00e  lea     r8, aWinreagentWork_2; "WinREAgent::WorkDir::CreateDirs"
0x18001f015  mov     edx, esi
0x18001f017  mov     ecx, 2
0x18001f01c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001f021  nop
0x18001f022  lea     rcx, [rdi-18h]; this
0x18001f026  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f02b  nop
0x18001f02c  lea     rcx, [rbx-18h]
0x18001f030  jmp     loc_18001F0C9
0x18001f035  lea     rcx, [rbp+arg_8]
0x18001f039  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001f03e  test    al, al
0x18001f040  jnz     short loc_18001F0B3
0x18001f042  lea     rdx, pszFormat
0x18001f049  lea     rcx, [rbp+arg_18]
0x18001f04d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001f052  nop
0x18001f053  lea     r8, [rbp+arg_18]
0x18001f057  xor     edx, edx
0x18001f059  lea     rcx, [rbp+arg_8]
0x18001f05d  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001f062  mov     esi, eax
0x18001f064  mov     rcx, [rbp+arg_18]
0x18001f068  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f06c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f071  test    esi, esi
0x18001f073  jns     short loc_18001F0B3
0x18001f075  mov     rbx, [rbp+arg_8]
0x18001f079  mov     [rsp+40h+var_10], rbx
0x18001f07e  lea     rax, aFailedToCreate_24; "Failed to create dir [%s]"
0x18001f085  mov     [rsp+40h+var_18], rax
0x18001f08a  mov     [rsp+40h+var_20], 3Dh ; '='
0x18001f092  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001f099  lea     r8, aWinreagentWork_2; "WinREAgent::WorkDir::CreateDirs"
0x18001f0a0  mov     edx, esi
0x18001f0a2  mov     ecx, 2
0x18001f0a7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001f0ac  nop
0x18001f0ad  lea     rcx, [rbx-18h]
0x18001f0b1  jmp     short loc_18001F0BB
0x18001f0b3  mov     rcx, [rbp+arg_8]
0x18001f0b7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f0bb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f0c0  nop
0x18001f0c1  mov     rcx, [rbp+arg_10]
0x18001f0c5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f0c9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f0ce  mov     eax, esi
0x18001f0d0  mov     rbx, [rsp+40h+arg_0]
0x18001f0d5  add     rsp, 40h
0x18001f0d9  pop     rdi
0x18001f0da  pop     rsi
0x18001f0db  pop     rbp
0x18001f0dc  retn
```
