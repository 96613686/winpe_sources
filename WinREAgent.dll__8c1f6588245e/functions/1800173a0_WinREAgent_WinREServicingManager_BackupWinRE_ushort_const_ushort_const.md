# WinREAgent::WinREServicingManager::BackupWinRE(ushort const *,ushort const *)

- ea: `0x1800173a0`
- end: `0x1800178d0`
- name: `?BackupWinRE@WinREServicingManager@WinREAgent@@SAJPEBG0@Z`
- size: `1328`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016680`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18001586c`
- `0x180016440`
- `0x1800173a0`
- `0x180019724`
- `0x18001f194`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004b35c`
- `0x18004bb04`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x1800536bc`
- `0x180053830`
- `0x180053afc`
- `0x18006f010`

## string_xrefs

- `0x180017428`: `Failed to build log path`
- `0x1800175aa`: `Failed to read WinRE configuration`
- `0x18001767a`: `Failed to get winre path`
- `0x1800173ec`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001743c`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001754a`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x1800175be`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180017631`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001768e`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x1800176e5`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x1800177a0`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001781b`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x1800173f3`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x180017443`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x180017551`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x1800175c5`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x180017638`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x180017695`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x1800176ec`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x1800177a7`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x180017822`: `WinREAgent::WinREServicingManager::BackupWinRE`
- `0x18001747b`: `Enter WinREAgent::WinREServicingManager::BackupWinRE`
- `0x1800174d5`: `Backup directory [%s] doesn't exist, creating`
- `0x180017536`: `Failed to create backup directory [%s]`
- `0x18001761d`: `Failed to read WinRE configuration from [%s]`
- `0x18001778c`: `Failed to construct path for target WinRE wim`
- `0x180017807`: `Failed to copy WinRE.wim from [%s] to [%s]`
- `0x180017846`: `Backup completed`
- `0x180017854`: `Exit WinREAgent::WinREServicingManager::BackupWinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinREAgent::WinREServicingManager::BackupWinRE(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  int TargetRoot; // ebx
  char v5; // bl
  struct PushButtonReset::WindowsRE::Config **v6; // rax
  struct PushButtonReset::WindowsRE::Config **v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // rdi
  ATL::CStringData *v13; // rcx
  __int64 v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  __int64 v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+48h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v15);
  TargetRoot = GetTargetRoot(a1, &v15);
  if ( TargetRoot >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v16);
    TargetRoot = WinREAgent::WorkDir::GetLogDir((__int64)&v15, (__int64)&v16);
    if ( TargetRoot < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)TargetRoot,
        "WinREAgent::WinREServicingManager::BackupWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1353,
        L"Failed to build log path");
LABEL_28:
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
      goto LABEL_29;
    }
    LOBYTE(v21) = 0;
    v20[1] = PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &,bool>(
               &v16,
               &v21);
    v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
    PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::BackupWinRE");
    if ( !a2 )
    {
      v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
      TargetRoot = -2147024809;
      goto LABEL_28;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v21,
      a2);
    v5 = PushButtonReset::Directory::Exists(&v21);
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    if ( !v5 )
    {
      PushButtonReset::Logging::Trace(0, L"Backup directory [%s] doesn't exist, creating", a2);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v22,
        &pszFormat);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v21,
        a2);
      TargetRoot = PushButtonReset::Directory::Create(&v21, 0, &v22);
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
      if ( TargetRoot < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)TargetRoot,
          "WinREAgent::WinREServicingManager::BackupWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1370,
          L"Failed to create backup directory [%s]",
          a2);
LABEL_10:
        v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
        goto LABEL_28;
      }
    }
    v19[1] = 0;
    v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    v6 = (struct PushButtonReset::WindowsRE::Config **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v19);
    if ( a1 )
    {
      v7 = v6;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v21,
        a1);
      TargetRoot = PushButtonReset::WindowsRE::OpenConfig(&v21, v7);
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      if ( TargetRoot < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)TargetRoot,
          "WinREAgent::WinREServicingManager::BackupWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1383,
          L"Failed to read WinRE configuration from [%s]",
          a1);
        goto LABEL_14;
      }
    }
    else
    {
      TargetRoot = PushButtonReset::WindowsRE::OpenConfig(v6);
      if ( TargetRoot < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)TargetRoot,
          "WinREAgent::WinREServicingManager::BackupWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1378,
          L"Failed to read WinRE configuration");
LABEL_14:
        v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
        goto LABEL_10;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v21);
    v8 = (*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
    TargetRoot = PushButtonReset::WindowsRE::Config::GetCurrentWimPath(v8, &v21);
    if ( TargetRoot >= 0 )
    {
      if ( !(unsigned __int8)PushButtonReset::File::Exists(&v21) )
      {
        v9 = v21;
        PushButtonReset::Logging::TraceErr(
          2,
          2147943568LL,
          "WinREAgent::WinREServicingManager::BackupWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1394,
          L"Current WinRE wim [%s] doesn't exist",
          v21);
        ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
        v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
        v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
        TargetRoot = -2147023728;
        goto LABEL_28;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v22);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v18,
        L"WinRE.wim");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v17,
        a2);
      TargetRoot = PushButtonReset::Path::Combine(&v17, &v18, &v22);
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
      if ( TargetRoot >= 0 )
      {
        PushButtonReset::Logging::Trace(0, L"Backup current WinRE as [%s]", v22);
        v10 = PushButtonReset::File::Copy(&v21, &v22, 0);
        if ( v10 >= 0 )
        {
          PushButtonReset::Logging::Trace(0, L"Backup completed");
          PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::BackupWinRE");
          ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
          v13 = (ATL::CStringData *)(v21 - 24);
        }
        else
        {
          v11 = v22;
          v12 = v21;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v10,
            "WinREAgent::WinREServicingManager::BackupWinRE",
            "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
            1407,
            L"Failed to copy WinRE.wim from [%s] to [%s]",
            v21,
            v22);
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
          v13 = (ATL::CStringData *)(v12 - 24);
        }
        ATL::CStringData::Release(v13);
        v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
        v20[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v20);
        TargetRoot = v10;
        goto LABEL_28;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)TargetRoot,
        "WinREAgent::WinREServicingManager::BackupWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1400,
        L"Failed to construct path for target WinRE wim");
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)TargetRoot,
        "WinREAgent::WinREServicingManager::BackupWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1388,
        L"Failed to get winre path");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    goto LABEL_14;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)TargetRoot,
    "WinREAgent::WinREServicingManager::BackupWinRE",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    1349,
    L"Failed to get target root");
LABEL_29:
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
  return (unsigned int)TargetRoot;
}

```

## disassembly

```asm
0x1800173a0  mov     [rsp-28h+arg_0], rbx
0x1800173a5  push    rbp
0x1800173a6  push    rsi
0x1800173a7  push    rdi
0x1800173a8  push    r14
0x1800173aa  push    r15
0x1800173ac  mov     rbp, rsp
0x1800173af  sub     rsp, 80h
0x1800173b6  mov     rdi, rdx
0x1800173b9  mov     rsi, rcx
0x1800173bc  lea     rcx, [rbp+var_40]
0x1800173c0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800173c5  nop
0x1800173c6  lea     rdx, [rbp+var_40]
0x1800173ca  mov     rcx, rsi
0x1800173cd  call    ?GetTargetRoot@@YAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetTargetRoot(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800173d2  mov     ebx, eax
0x1800173d4  test    eax, eax
0x1800173d6  jns     short loc_18001740B
0x1800173d8  lea     rax, aFailedToGetTar_0; "Failed to get target root"
0x1800173df  mov     [rsp+80h+var_58], rax
0x1800173e4  mov     [rsp+80h+var_60], 545h
0x1800173ec  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800173f3  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x1800173fa  mov     edx, ebx
0x1800173fc  mov     ecx, 2
0x180017401  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180017406  jmp     loc_1800178AA
0x18001740b  lea     rcx, [rbp+var_38]
0x18001740f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180017414  nop
0x180017415  lea     rdx, [rbp+var_38]
0x180017419  lea     rcx, [rbp+var_40]
0x18001741d  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180017422  mov     ebx, eax
0x180017424  test    eax, eax
0x180017426  jns     short loc_18001745B
0x180017428  lea     rax, aFailedToBuildL; "Failed to build log path"
0x18001742f  mov     [rsp+80h+var_58], rax
0x180017434  mov     [rsp+80h+var_60], 549h
0x18001743c  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180017443  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x18001744a  mov     edx, ebx
0x18001744c  mov     ecx, 2
0x180017451  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180017456  jmp     loc_18001789C
0x18001745b  mov     byte ptr [rbp+arg_10], 0
0x18001745f  lea     rdx, [rbp+arg_10]
0x180017463  lea     rcx, [rbp+var_38]
0x180017467  call    ??$PbrNew@VLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@@YAPEAVLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEA_N@Z; PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &&)
0x18001746c  mov     [rbp+var_8], rax
0x180017470  lea     r14, ??_7?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable'
0x180017477  mov     [rbp+var_10], r14
0x18001747b  lea     rdx, aEnterWinreagen_1; "Enter WinREAgent::WinREServicingManager"...
0x180017482  xor     ecx, ecx
0x180017484  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180017489  test    rdi, rdi
0x18001748c  jnz     short loc_1800174A5
0x18001748e  mov     [rbp+var_10], r14
0x180017492  lea     rcx, [rbp+var_10]
0x180017496  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x18001749b  mov     ebx, 80070057h
0x1800174a0  jmp     loc_18001789C
0x1800174a5  mov     rdx, rdi
0x1800174a8  lea     rcx, [rbp+arg_10]
0x1800174ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800174b1  nop
0x1800174b2  lea     rcx, [rbp+arg_10]
0x1800174b6  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800174bb  mov     bl, al
0x1800174bd  mov     rcx, [rbp+arg_10]
0x1800174c1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800174c5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800174ca  test    bl, bl
0x1800174cc  jnz     loc_180017577
0x1800174d2  mov     r8, rdi
0x1800174d5  lea     rdx, aBackupDirector_0; "Backup directory [%s] doesn't exist, cr"...
0x1800174dc  xor     ecx, ecx
0x1800174de  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800174e3  lea     rdx, pszFormat
0x1800174ea  lea     rcx, [rbp+arg_18]
0x1800174ee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800174f3  nop
0x1800174f4  mov     rdx, rdi
0x1800174f7  lea     rcx, [rbp+arg_10]
0x1800174fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180017500  nop
0x180017501  lea     r8, [rbp+arg_18]
0x180017505  xor     edx, edx
0x180017507  lea     rcx, [rbp+arg_10]
0x18001750b  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180017510  mov     ebx, eax
0x180017512  mov     rcx, [rbp+arg_10]
0x180017516  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001751a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001751f  nop
0x180017520  mov     rcx, [rbp+arg_18]
0x180017524  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017528  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001752d  test    ebx, ebx
0x18001752f  jns     short loc_180017577
0x180017531  mov     [rsp+80h+var_50], rdi
0x180017536  lea     rax, aFailedToCreate_42; "Failed to create backup directory [%s]"
0x18001753d  mov     [rsp+80h+var_58], rax
0x180017542  mov     [rsp+80h+var_60], 55Ah
0x18001754a  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180017551  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x180017558  mov     edx, ebx
0x18001755a  mov     ecx, 2
0x18001755f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180017564  nop
0x180017565  mov     [rbp+var_10], r14
0x180017569  lea     rcx, [rbp+var_10]
0x18001756d  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180017572  jmp     loc_18001789C
0x180017577  mov     [rbp+var_18], 0
0x18001757f  lea     r15, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x180017586  mov     [rbp+var_20], r15
0x18001758a  lea     rcx, [rbp+var_20]
0x18001758e  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180017593  test    rsi, rsi
0x180017596  jnz     short loc_1800175E9
0x180017598  mov     rcx, rax; struct PushButtonReset::WindowsRE::Config **
0x18001759b  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x1800175a0  mov     ebx, eax
0x1800175a2  test    eax, eax
0x1800175a4  jns     loc_18001764D
0x1800175aa  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x1800175b1  mov     [rsp+80h+var_58], rax
0x1800175b6  mov     [rsp+80h+var_60], 562h
0x1800175be  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800175c5  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x1800175cc  mov     edx, ebx
0x1800175ce  lea     ecx, [rsi+2]
0x1800175d1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800175d6  nop
0x1800175d7  mov     [rbp+var_20], r15
0x1800175db  lea     rcx, [rbp+var_20]
0x1800175df  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800175e4  jmp     loc_180017565
0x1800175e9  mov     rbx, rax
0x1800175ec  mov     rdx, rsi
0x1800175ef  lea     rcx, [rbp+arg_10]
0x1800175f3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800175f8  nop
0x1800175f9  mov     rdx, rbx
0x1800175fc  lea     rcx, [rbp+arg_10]
0x180017600  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WindowsRE::Config * *)
0x180017605  mov     ebx, eax
0x180017607  mov     rcx, [rbp+arg_10]
0x18001760b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001760f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180017614  test    ebx, ebx
0x180017616  jns     short loc_18001764D
0x180017618  mov     [rsp+80h+var_50], rsi
0x18001761d  lea     rax, aFailedToReadWi_1; "Failed to read WinRE configuration from"...
0x180017624  mov     [rsp+80h+var_58], rax
0x180017629  mov     [rsp+80h+var_60], 567h
0x180017631  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180017638  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x18001763f  mov     edx, ebx
0x180017641  mov     ecx, 2
0x180017646  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001764b  jmp     short loc_1800175D7
0x18001764d  lea     rcx, [rbp+arg_10]
0x180017651  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180017656  nop
0x180017657  mov     rax, [rbp+var_20]
0x18001765b  lea     rcx, [rbp+var_20]
0x18001765f  mov     rax, [rax+18h]
0x180017663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017668  lea     rdx, [rbp+arg_10]
0x18001766c  mov     rcx, rax
0x18001766f  call    ?GetCurrentWimPath@Config@WindowsRE@PushButtonReset@@QEAAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WindowsRE::Config::GetCurrentWimPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180017674  mov     ebx, eax
0x180017676  test    eax, eax
0x180017678  jns     short loc_1800176BB
0x18001767a  lea     rax, aFailedToGetWin_0; "Failed to get winre path"
0x180017681  mov     [rsp+80h+var_58], rax
0x180017686  mov     [rsp+80h+var_60], 56Ch
0x18001768e  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180017695  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x18001769c  mov     edx, ebx
0x18001769e  mov     ecx, 2
0x1800176a3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800176a8  nop
0x1800176a9  mov     rcx, [rbp+arg_10]
0x1800176ad  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800176b1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800176b6  jmp     loc_1800175D7
0x1800176bb  lea     rcx, [rbp+arg_10]
0x1800176bf  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800176c4  test    al, al
0x1800176c6  jnz     short loc_180017732
0x1800176c8  mov     rbx, [rbp+arg_10]
0x1800176cc  mov     [rsp+80h+var_50], rbx
0x1800176d1  lea     rax, aCurrentWinreWi; "Current WinRE wim [%s] doesn't exist"
0x1800176d8  mov     [rsp+80h+var_58], rax
0x1800176dd  mov     [rsp+80h+var_60], 572h
0x1800176e5  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800176ec  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x1800176f3  mov     edx, 80070490h
0x1800176f8  mov     ecx, 2
0x1800176fd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180017702  nop
0x180017703  lea     rcx, [rbx-18h]; this
0x180017707  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001770c  nop
0x18001770d  mov     [rbp+var_20], r15
0x180017711  lea     rcx, [rbp+var_20]
0x180017715  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18001771a  nop
0x18001771b  mov     [rbp+var_10], r14
0x18001771f  lea     rcx, [rbp+var_10]
0x180017723  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x180017728  mov     ebx, 80070490h
0x18001772d  jmp     loc_18001789C
0x180017732  lea     rcx, [rbp+arg_18]
0x180017736  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001773b  nop
0x18001773c  lea     rdx, aWinreWim; "WinRE.wim"
0x180017743  lea     rcx, [rbp+var_28]
0x180017747  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001774c  nop
0x18001774d  mov     rdx, rdi
0x180017750  lea     rcx, [rbp+var_30]
0x180017754  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180017759  nop
0x18001775a  lea     r8, [rbp+arg_18]
0x18001775e  lea     rdx, [rbp+var_28]
0x180017762  lea     rcx, [rbp+var_30]
0x180017766  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001776b  mov     ebx, eax
0x18001776d  mov     rcx, [rbp+var_30]
0x180017771  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017775  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001777a  nop
0x18001777b  mov     rcx, [rbp+var_28]
0x18001777f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017783  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180017788  test    ebx, ebx
0x18001778a  jns     short loc_1800177CD
0x18001778c  lea     rax, aFailedToConstr_0; "Failed to construct path for target Win"...
0x180017793  mov     [rsp+80h+var_58], rax
0x180017798  mov     [rsp+80h+var_60], 578h
0x1800177a0  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800177a7  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x1800177ae  mov     edx, ebx
0x1800177b0  mov     ecx, 2
0x1800177b5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800177ba  nop
0x1800177bb  mov     rcx, [rbp+arg_18]
0x1800177bf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800177c3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800177c8  jmp     loc_1800176A9
0x1800177cd  mov     r8, [rbp+arg_18]
0x1800177d1  lea     rdx, aBackupCurrentW; "Backup current WinRE as [%s]"
0x1800177d8  xor     ecx, ecx
0x1800177da  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800177df  xor     r8d, r8d
0x1800177e2  lea     rdx, [rbp+arg_18]
0x1800177e6  lea     rcx, [rbp+arg_10]
0x1800177ea  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x1800177ef  mov     esi, eax
0x1800177f1  test    eax, eax
0x1800177f3  jns     short loc_180017846
0x1800177f5  mov     rbx, [rbp+arg_18]
0x1800177f9  mov     [rsp+80h+var_48], rbx
0x1800177fe  mov     rdi, [rbp+arg_10]
0x180017802  mov     [rsp+80h+var_50], rdi
0x180017807  lea     rax, aFailedToCopyWi; "Failed to copy WinRE.wim from [%s] to ["...
0x18001780e  mov     [rsp+80h+var_58], rax
0x180017813  mov     [rsp+80h+var_60], 57Fh
0x18001781b  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180017822  lea     r8, aWinreagentWinr_26; "WinREAgent::WinREServicingManager::Back"...
0x180017829  mov     edx, esi
0x18001782b  mov     ecx, 2
0x180017830  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180017835  nop
0x180017836  lea     rcx, [rbx-18h]; this
0x18001783a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001783f  nop
0x180017840  lea     rcx, [rdi-18h]
0x180017844  jmp     short loc_180017879
0x180017846  lea     rdx, aBackupComplete; "Backup completed"
0x18001784d  xor     ecx, ecx
0x18001784f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180017854  lea     rdx, aExitWinreagent_4; "Exit WinREAgent::WinREServicingManager:"...
0x18001785b  xor     ecx, ecx
0x18001785d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180017862  nop
0x180017863  mov     rcx, [rbp+arg_18]
0x180017867  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001786b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180017870  nop
0x180017871  mov     rcx, [rbp+arg_10]
0x180017875  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017879  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001787e  nop
0x18001787f  mov     [rbp+var_20], r15
  ... truncated ...
```
