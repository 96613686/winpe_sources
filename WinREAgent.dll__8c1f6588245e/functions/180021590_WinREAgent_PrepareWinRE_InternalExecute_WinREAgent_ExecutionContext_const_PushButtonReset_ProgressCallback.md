# WinREAgent::PrepareWinRE::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x180021590`
- end: `0x180021dde`
- name: `?InternalExecute@PrepareWinRE@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `2126`
- prototype: `__int64 __fastcall(WinREAgent::PrepareWinRE *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000509c`
- `0x180005cc0`
- `0x18000d640`
- `0x18000d92c`
- `0x18001f6e8`
- `0x1800204b8`
- `0x180020c28`
- `0x180021590`
- `0x1800229fc`
- `0x180022d8c`
- `0x180023654`
- `0x180023800`
- `0x180028b60`
- `0x18002e1f8`
- `0x180032480`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004bb04`
- `0x18004c2b0`
- `0x18004e47c`
- `0x18004ed94`
- `0x180050390`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180021c10`
- `KERNEL32!GetLastError` at `0x180021c5f`
- `KERNEL32!GetLastError` at `0x180021c10`
- `KERNEL32!GetLastError` at `0x180021c5f`
- `KERNEL32!CreateEventW` at `0x180021640`
- `KERNEL32!CreateEventW` at `0x180021640`
- `KERNEL32!SetEnvironmentVariableW` at `0x18002180d`
- `KERNEL32!SetEnvironmentVariableW` at `0x180021874`
- `KERNEL32!SetEnvironmentVariableW` at `0x18002180d`
- `KERNEL32!SetEnvironmentVariableW` at `0x180021874`
- `KERNEL32!GetFileAttributesW` at `0x180021bef`
- `KERNEL32!GetFileAttributesW` at `0x180021bef`
- `KERNEL32!SetFileAttributesW` at `0x180021bff`
- `KERNEL32!SetFileAttributesW` at `0x180021bff`
- `DismApi!DismUnmountImage` at `0x180021998`
- `DismApi!DismUnmountImage` at `0x180021998`
- `DismApi!DismMountImage` at `0x180021863`
- `DismApi!DismMountImage` at `0x180021863`

## string_xrefs

- `0x180021735`: `Mount`
- `0x18002176c`: `Failed to build mount path in scratch`
- `0x1800215e7`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021780`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021892`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021908`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021a1d`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021a8e`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021b7a`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021c40`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021c8a`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021d11`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800215d3`: `Does not have path to current wim`
- `0x1800215ee`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021787`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021899`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x18002190f`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021a24`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021a95`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021b81`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021c47`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021c91`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x180021d18`: `WinREAgent::PrepareWinRE::InternalExecute`
- `0x18002161e`: `Does not have path to updated wim`
- `0x1800217e9`: `Failed to create directory`
- `0x180021806`: `WIM_Apply_VerifyPath`
- `0x18002186d`: `WIM_Apply_VerifyPath`
- `0x18002187e`: `Failed to mount winre image`
- `0x1800218f4`: `Failed to get list of installed packages`
- `0x1800219a4`: `Failed to commmit image changes`
- `0x180021a09`: `Failed to delete directory`
- `0x180021a7a`: `Failed to build path to exported.wim`
- `0x180021abb`: `PrepareWinRE: Save exported WinRE wim path to Rollback info`
- `0x180021ad0`: `ExportedWimPath`
- `0x180021b2e`: `Failed to save exported WinRE wim path into Rollback info`
- `0x180021c2c`: `Failed to copy attributes from [%s] to [%s]`
- `0x180021cc0`: `Failed to replace updated wim`
- `0x180021d32`: `Size of update wim [%llu]`
- `0x180021d4e`: `UpdatedWinRESize`

## pseudocode

```c
__int64 __fastcall WinREAgent::PrepareWinRE::InternalExecute(
        WinREAgent::PrepareWinRE *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  LPCWSTR *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  int PackagesToBeInstalled; // ebx
  int v11; // eax
  __int64 v12; // rbx
  const WCHAR *v13; // rdx
  int v14; // eax
  __int64 v15; // rbx
  const WCHAR *v16; // rbx
  int v17; // r14d
  DWORD FileAttributesW; // eax
  LPCWSTR v19; // r14
  signed int v20; // eax
  LPCWSTR v21; // rbx
  signed int LastError; // eax
  WinREAgent::TelemetrySession *v23; // rcx
  unsigned __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[2]; // [rsp+68h] [rbp-98h] BYREF
  void **v28; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v30[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  __int64 v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  int v42; // [rsp+100h] [rbp+0h]

  if ( !*(_DWORD *)(*((_QWORD *)this + 18) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      556,
      L"Does not have path to current wim");
    return 2147942487LL;
  }
  v7 = (LPCWSTR *)((char *)a2 + 280);
  if ( !*(_DWORD *)(*((_QWORD *)a2 + 35) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      561,
      L"Does not have path to updated wim");
    return 2147942487LL;
  }
  v28 = &RAII::CAutoCleanup<void *>::`vftable';
  v29[0] = CreateEventW(0, 1, 0, 0);
  v30[0] = &WinREAgent::OperationProgress::`vftable';
  v30[1] = a3;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(&v28);
  ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, 200);
  v34 += 200;
  v8 = 100LL * *((_QWORD *)this + 20);
  ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, v8);
  v34 += v8;
  ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, 200);
  v34 += 200;
  ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, 200);
  v34 += 200;
  ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, 100);
  v34 += 100;
  v27[1] = 0;
  v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
  v9 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v27);
  PushButtonReset::DismAutoShutdown::Create((char *)a2 + 216, (char *)a2 + 184, v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v38);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v24,
    L"Mount");
  PackagesToBeInstalled = PushButtonReset::Path::Combine((char *)a2 + 184, &v24, &v38);
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  if ( PackagesToBeInstalled < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)PackagesToBeInstalled,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      585,
      L"Failed to build mount path in scratch");
    goto LABEL_50;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v24,
    &pszFormat);
  PackagesToBeInstalled = PushButtonReset::Directory::Create(&v38, 0, &v24);
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  if ( PackagesToBeInstalled < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)PackagesToBeInstalled,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      588,
      L"Failed to create directory");
    goto LABEL_50;
  }
  SetEnvironmentVariableW(L"WIM_Apply_VerifyPath", L"1");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount>::GetImpl'::`2'::impl) )
    v11 = DismMountImage(*v7, v38, 1, 0, 0, 4, v37, PrepareWinREProgressCallback, v30);
  else
    v11 = DismMountImage(*v7, v38, 1, 0, 0, 0, v37, PrepareWinREProgressCallback, v30);
  PackagesToBeInstalled = v11;
  SetEnvironmentVariableW(L"WIM_Apply_VerifyPath", 0);
  if ( PackagesToBeInstalled < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)PackagesToBeInstalled,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      620,
      L"Failed to mount winre image");
    goto LABEL_50;
  }
  WinREAgent::OperationProgress::CompletedOperation((WinREAgent::OperationProgress *)v30);
  if ( *((_BYTE *)this + 296) )
  {
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    PackagesToBeInstalled = GetPackagesToBeInstalled(&v38, (char *)this + 264, &v39);
    if ( PackagesToBeInstalled < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)PackagesToBeInstalled,
        "WinREAgent::PrepareWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        628,
        L"Failed to get list of installed packages");
LABEL_18:
      ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v39);
      goto LABEL_50;
    }
    v12 = 100 * v40;
    ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v31, 100 * v40);
    v34 += v12;
    PackagesToBeInstalled = PatchImageUsingCbs(&v38, (char *)this + 264, &v39, (char *)this + 208);
    if ( PackagesToBeInstalled < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)PackagesToBeInstalled,
        "WinREAgent::PrepareWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        633,
        L"Failed to patch winre image");
      goto LABEL_18;
    }
    ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v39);
  }
  else
  {
    PackagesToBeInstalled = PatchImage(&v38, (char *)this + 152, (char *)this + 208, v30);
    if ( PackagesToBeInstalled < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)PackagesToBeInstalled,
        "WinREAgent::PrepareWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        638,
        L"Failed to patch winre image");
      goto LABEL_50;
    }
  }
  PackagesToBeInstalled = DismUnmountImage(v38, 0, v37, PrepareWinREProgressCallback, v30);
  if ( PackagesToBeInstalled >= 0 )
  {
    WinREAgent::OperationProgress::CompletedOperation((WinREAgent::OperationProgress *)v30);
    v14 = PushButtonReset::Directory::Delete(&v38, v13);
    if ( v14 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v14,
        "WinREAgent::PrepareWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        655,
        L"Failed to delete directory");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v24,
      L"exported.wim");
    PackagesToBeInstalled = PushButtonReset::Path::Combine((char *)a2 + 184, &v24, &lpFileName);
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    if ( PackagesToBeInstalled >= 0 )
    {
      if ( *((_QWORD *)a2 + 56)
        && (PushButtonReset::Logging::Trace(0, L"PrepareWinRE: Save exported WinRE wim path to Rollback info"),
            v15 = *((_QWORD *)a2 + 56),
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v26,
              L"ExportedWimPath"),
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v24,
              L"GeneralInfo"),
            PackagesToBeInstalled = WinREAgent::RollbackHelper::WriteToConfig(v15, &v24, &v26, &lpFileName),
            ATL::CStringData::Release((ATL::CStringData *)(v24 - 24)),
            ATL::CStringData::Release((ATL::CStringData *)(v26 - 24)),
            PackagesToBeInstalled < 0) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)PackagesToBeInstalled,
          "WinREAgent::PrepareWinRE::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          671,
          L"Failed to save exported WinRE wim path into Rollback info");
      }
      else
      {
        v16 = lpFileName;
        v17 = ExportImage((__int64)lpFileName, (__int64)a2, (struct PushButtonReset::ProgressCallback *)v30);
        if ( v17 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v17,
            "WinREAgent::PrepareWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
            675,
            L"Failed to export image");
          ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
          v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v27);
          ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v31);
          v28 = &RAII::CAutoCleanup<void *>::`vftable';
          RAII::CleanupInfo<void *>::Release(v29);
          return (unsigned int)v17;
        }
        FileAttributesW = GetFileAttributesW(*v7);
        if ( FileAttributesW == -1 )
        {
          v21 = *v7;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)LastError,
            "WinREAgent::PrepareWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
            697,
            L"Failed to get file attributes for [%s]",
            v21);
        }
        else if ( !SetFileAttributesW(v16, FileAttributesW) )
        {
          v19 = *v7;
          v20 = GetLastError();
          if ( v20 > 0 )
            v20 = (unsigned __int16)v20 | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v20,
            "WinREAgent::PrepareWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
            688,
            L"Failed to copy attributes from [%s] to [%s]",
            v19,
            v16);
        }
        WinREAgent::OperationProgress::CompletedOperation((WinREAgent::OperationProgress *)v30);
        PackagesToBeInstalled = PushButtonReset::File::Move(&lpFileName, v7);
        if ( PackagesToBeInstalled >= 0 )
        {
          v24 = 0;
          PackagesToBeInstalled = PushButtonReset::File::GetSize(v7, &v24);
          if ( PackagesToBeInstalled >= 0 )
          {
            PushButtonReset::Logging::Trace(0, L"Size of update wim [%llu]", v24);
            v23 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
            if ( v23 )
              WinREAgent::TelemetrySession::TraceDataPoint(v23, L"ServicingInfoGroup", L"UpdatedWinRESize", v24);
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)PackagesToBeInstalled,
              "WinREAgent::PrepareWinRE::InternalExecute",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              708,
              L"Failed to get size of [%s]",
              *v7);
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)PackagesToBeInstalled,
            "WinREAgent::PrepareWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
            704,
            L"Failed to replace updated wim");
        }
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)PackagesToBeInstalled,
        "WinREAgent::PrepareWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        662,
        L"Failed to build path to exported.wim");
    }
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)PackagesToBeInstalled,
      "WinREAgent::PrepareWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      648,
      L"Failed to commmit image changes");
  }
LABEL_50:
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v27);
  ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v31);
  v28 = &RAII::CAutoCleanup<void *>::`vftable';
  RAII::CleanupInfo<void *>::Release(v29);
  return (unsigned int)PackagesToBeInstalled;
}

```

## disassembly

```asm
0x180021590  mov     [rsp-8+arg_10], rbx
0x180021595  push    rbp
0x180021596  push    rsi
0x180021597  push    rdi
0x180021598  push    r12
0x18002159a  push    r13
0x18002159c  push    r14
0x18002159e  push    r15
0x1800215a0  lea     rbp, [rsp-10h]
0x1800215a5  sub     rsp, 110h
0x1800215ac  mov     rax, cs:__security_cookie
0x1800215b3  xor     rax, rsp
0x1800215b6  mov     [rbp+40h+var_38], rax
0x1800215ba  mov     rbx, r8
0x1800215bd  mov     r14, rdx
0x1800215c0  mov     rsi, rcx
0x1800215c3  mov     rax, [rcx+90h]
0x1800215ca  xor     r13d, r13d
0x1800215cd  cmp     [rax-10h], r13d
0x1800215d1  jnz     short loc_18002160E
0x1800215d3  lea     rax, aDoesNotHavePat_0; "Does not have path to current wim"
0x1800215da  mov     [rsp+140h+var_118], rax
0x1800215df  mov     dword ptr [rsp+140h+var_120], 22Ch
0x1800215e7  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800215ee  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x1800215f5  mov     edx, 80070057h
0x1800215fa  mov     ecx, 2
0x1800215ff  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180021604  mov     eax, 80070057h
0x180021609  jmp     loc_180021DB7
0x18002160e  lea     rdi, [rdx+118h]
0x180021615  mov     rax, [rdi]
0x180021618  cmp     [rax-10h], r13d
0x18002161c  jnz     short loc_180021634
0x18002161e  lea     rax, aDoesNotHavePat; "Does not have path to updated wim"
0x180021625  mov     [rsp+140h+var_118], rax
0x18002162a  mov     dword ptr [rsp+140h+var_120], 231h
0x180021632  jmp     short loc_1800215E7
0x180021634  xor     r9d, r9d; lpName
0x180021637  xor     r8d, r8d; bInitialState
0x18002163a  lea     edx, [r9+1]; bManualReset
0x18002163e  xor     ecx, ecx; lpEventAttributes
0x180021640  call    cs:__imp_CreateEventW
0x180021646  lea     rcx, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x18002164d  mov     [rsp+140h+var_C8], rcx
0x180021652  mov     [rbp+40h+var_C0], rax
0x180021656  lea     rax, ??_7OperationProgress@WinREAgent@@6B@; const WinREAgent::OperationProgress::`vftable'
0x18002165d  mov     [rbp+40h+var_B0], rax
0x180021661  mov     [rbp+40h+var_A8], rbx
0x180021665  xorps   xmm0, xmm0
0x180021668  movdqa  [rbp+40h+var_A0], xmm0
0x18002166d  mov     [rbp+40h+var_90], r13
0x180021671  mov     [rbp+40h+var_88], r13d
0x180021675  mov     [rbp+40h+var_80], r13
0x180021679  mov     [rbp+40h+var_78], r13
0x18002167d  mov     [rbp+40h+var_70], r13
0x180021681  lea     rcx, [rsp+140h+var_C8]
0x180021686  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002168b  mov     rcx, [rax]
0x18002168e  mov     [rbp+40h+var_68], rcx
0x180021692  mov     r15d, 0C8h
0x180021698  mov     edx, r15d
0x18002169b  lea     rcx, [rbp+40h+var_A0]
0x18002169f  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800216a4  add     [rbp+40h+var_80], r15
0x1800216a8  lea     r12, [rsi+98h]
0x1800216af  imul    rbx, [r12+8], 64h ; 'd'
0x1800216b5  mov     rdx, rbx
0x1800216b8  lea     rcx, [rbp+40h+var_A0]
0x1800216bc  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800216c1  add     [rbp+40h+var_80], rbx
0x1800216c5  mov     edx, r15d
0x1800216c8  lea     rcx, [rbp+40h+var_A0]
0x1800216cc  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800216d1  add     [rbp+40h+var_80], r15
0x1800216d5  mov     edx, r15d
0x1800216d8  lea     rcx, [rbp+40h+var_A0]
0x1800216dc  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800216e1  add     [rbp+40h+var_80], r15
0x1800216e5  lea     edx, [r15-64h]
0x1800216e9  lea     rcx, [rbp+40h+var_A0]
0x1800216ed  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800216f2  add     [rbp+40h+var_80], 64h ; 'd'
0x1800216f7  mov     [rsp+140h+var_D0], r13
0x1800216fc  lea     r15, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x180021703  mov     [rsp+140h+var_D8], r15
0x180021708  lea     rcx, [rsp+140h+var_D8]
0x18002170d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180021712  lea     r13, [r14+0B8h]
0x180021719  lea     rcx, [r14+0D8h]
0x180021720  mov     r8, rax
0x180021723  mov     rdx, r13
0x180021726  call    ?Create@DismAutoShutdown@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAPEAV12@@Z; PushButtonReset::DismAutoShutdown::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DismAutoShutdown * *)
0x18002172b  lea     rcx, [rbp+40h+var_60]
0x18002172f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180021734  nop
0x180021735  lea     rdx, aMount; "Mount"
0x18002173c  lea     rcx, [rsp+140h+var_F0]
0x180021741  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180021746  nop
0x180021747  lea     r8, [rbp+40h+var_60]
0x18002174b  lea     rdx, [rsp+140h+var_F0]
0x180021750  mov     rcx, r13
0x180021753  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180021758  mov     ebx, eax
0x18002175a  mov     rcx, [rsp+140h+var_F0]
0x18002175f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021763  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021768  test    ebx, ebx
0x18002176a  jns     short loc_1800217B3
0x18002176c  lea     rax, aFailedToBuildM; "Failed to build mount path in scratch"
0x180021773  mov     [rsp+140h+var_118], rax
0x180021778  mov     dword ptr [rsp+140h+var_120], 249h
0x180021780  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180021787  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x18002178e  mov     edx, ebx
0x180021790  mov     ecx, 2
0x180021795  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002179a  nop
0x18002179b  mov     rcx, [rbp+40h+var_60]
0x18002179f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800217a3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800217a8  nop
0x1800217a9  mov     [rsp+140h+var_D8], r15
0x1800217ae  jmp     loc_180021D8B
0x1800217b3  lea     rdx, pszFormat
0x1800217ba  lea     rcx, [rsp+140h+var_F0]
0x1800217bf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800217c4  nop
0x1800217c5  lea     r8, [rsp+140h+var_F0]
0x1800217ca  xor     edx, edx
0x1800217cc  lea     rcx, [rbp+40h+var_60]
0x1800217d0  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800217d5  mov     ebx, eax
0x1800217d7  mov     rcx, [rsp+140h+var_F0]
0x1800217dc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800217e0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800217e5  test    ebx, ebx
0x1800217e7  jns     short loc_1800217FF
0x1800217e9  lea     rax, aFailedToCreate_8; "Failed to create directory"
0x1800217f0  mov     [rsp+140h+var_118], rax
0x1800217f5  mov     dword ptr [rsp+140h+var_120], 24Ch
0x1800217fd  jmp     short loc_180021780
0x1800217ff  lea     rdx, Value; "1"
0x180021806  lea     rcx, Name; "WIM_Apply_VerifyPath"
0x18002180d  call    cs:__imp_SetEnvironmentVariableW
0x180021813  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount>::GetImpl(void)'::`2'::impl
0x18002181a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_IntegrityFlagForMount>::__private_IsEnabled(void)
0x18002181f  xor     ecx, ecx
0x180021821  lea     r15, PrepareWinREProgressCallback
0x180021828  xor     r9d, r9d
0x18002182b  lea     r8d, [rcx+1]
0x18002182f  mov     rdx, [rbp+40h+var_60]
0x180021833  test    al, al
0x180021835  lea     rax, [rbp+40h+var_B0]
0x180021839  mov     [rsp+140h+var_100], rax
0x18002183e  mov     [rsp+140h+var_108], r15
0x180021843  mov     rax, [rbp+40h+var_68]
0x180021847  mov     [rsp+140h+var_110], rax
0x18002184c  jz      short loc_180021858
0x18002184e  mov     dword ptr [rsp+140h+var_118], 4
0x180021856  jmp     short loc_18002185C
0x180021858  mov     dword ptr [rsp+140h+var_118], ecx
0x18002185c  mov     dword ptr [rsp+140h+var_120], ecx
0x180021860  mov     rcx, [rdi]
0x180021863  call    cs:__imp_DismMountImage
0x180021869  mov     ebx, eax
0x18002186b  xor     edx, edx; lpValue
0x18002186d  lea     rcx, Name; "WIM_Apply_VerifyPath"
0x180021874  call    cs:__imp_SetEnvironmentVariableW
0x18002187a  test    ebx, ebx
0x18002187c  jns     short loc_1800218B1
0x18002187e  lea     rax, aFailedToMountW; "Failed to mount winre image"
0x180021885  mov     [rsp+140h+var_118], rax
0x18002188a  mov     dword ptr [rsp+140h+var_120], 26Ch
0x180021892  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180021899  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x1800218a0  mov     edx, ebx
0x1800218a2  mov     ecx, 2
0x1800218a7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800218ac  jmp     loc_180021D71
0x1800218b1  lea     rcx, [rbp+40h+var_B0]; this
0x1800218b5  call    ?CompletedOperation@OperationProgress@WinREAgent@@QEAAXXZ; WinREAgent::OperationProgress::CompletedOperation(void)
0x1800218ba  xor     eax, eax
0x1800218bc  cmp     [rsi+128h], al
0x1800218c2  jz      loc_1800219BD
0x1800218c8  mov     [rbp+40h+var_58], rax
0x1800218cc  mov     [rbp+40h+var_50], rax
0x1800218d0  mov     [rbp+40h+var_48], rax
0x1800218d4  mov     [rbp+40h+var_40], eax
0x1800218d7  lea     r12, [rsi+108h]
0x1800218de  lea     r8, [rbp+40h+var_58]
0x1800218e2  mov     rdx, r12
0x1800218e5  lea     rcx, [rbp+40h+var_60]
0x1800218e9  call    GetPackagesToBeInstalled
0x1800218ee  mov     ebx, eax
0x1800218f0  test    eax, eax
0x1800218f2  jns     short loc_180021931
0x1800218f4  lea     rax, aFailedToGetLis; "Failed to get list of installed package"...
0x1800218fb  mov     [rsp+140h+var_118], rax
0x180021900  mov     dword ptr [rsp+140h+var_120], 274h
0x180021908  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002190f  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x180021916  mov     edx, ebx
0x180021918  mov     ecx, 2
0x18002191d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180021922  nop
0x180021923  lea     rcx, [rbp+40h+var_58]
0x180021927  call    ??1?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::~CAtlArray<uchar,ATL::CElementTraits<uchar>>(void)
0x18002192c  jmp     loc_180021D71
0x180021931  imul    rbx, [rbp+40h+var_50], 64h ; 'd'
0x180021936  mov     rdx, rbx
0x180021939  lea     rcx, [rbp+40h+var_A0]
0x18002193d  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x180021942  add     [rbp+40h+var_80], rbx
0x180021946  lea     r9, [rsi+0D0h]
0x18002194d  lea     r8, [rbp+40h+var_58]
0x180021951  mov     rdx, r12
0x180021954  lea     rcx, [rbp+40h+var_60]
0x180021958  call    PatchImageUsingCbs
0x18002195d  mov     ebx, eax
0x18002195f  test    eax, eax
0x180021961  jns     short loc_180021979
0x180021963  lea     rcx, aFailedToPatchW; "Failed to patch winre image"
0x18002196a  mov     [rsp+140h+var_118], rcx
0x18002196f  mov     dword ptr [rsp+140h+var_120], 279h
0x180021977  jmp     short loc_180021908
0x180021979  lea     rcx, [rbp+40h+var_58]
0x18002197d  call    ??1?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::~CAtlArray<uchar,ATL::CElementTraits<uchar>>(void)
0x180021982  lea     rax, [rbp+40h+var_B0]
0x180021986  mov     [rsp+140h+var_120], rax
0x18002198b  mov     r9, r15
0x18002198e  mov     r8, [rbp+40h+var_68]
0x180021992  xor     edx, edx
0x180021994  mov     rcx, [rbp+40h+var_60]
0x180021998  call    cs:__imp_DismUnmountImage
0x18002199e  mov     ebx, eax
0x1800219a0  test    eax, eax
0x1800219a2  jns     short loc_1800219F3
0x1800219a4  lea     rax, aFailedToCommmi; "Failed to commmit image changes"
0x1800219ab  mov     [rsp+140h+var_118], rax
0x1800219b0  mov     dword ptr [rsp+140h+var_120], 288h
0x1800219b8  jmp     loc_180021892
0x1800219bd  lea     r8, [rsi+0D0h]
0x1800219c4  lea     r9, [rbp+40h+var_B0]
0x1800219c8  mov     rdx, r12
0x1800219cb  lea     rcx, [rbp+40h+var_60]
0x1800219cf  call    PatchImage
0x1800219d4  mov     ebx, eax
0x1800219d6  test    eax, eax
0x1800219d8  jns     short loc_180021982
0x1800219da  lea     rcx, aFailedToPatchW; "Failed to patch winre image"
0x1800219e1  mov     [rsp+140h+var_118], rcx
0x1800219e6  mov     dword ptr [rsp+140h+var_120], 27Eh
0x1800219ee  jmp     loc_180021892
0x1800219f3  lea     rcx, [rbp+40h+var_B0]; this
0x1800219f7  call    ?CompletedOperation@OperationProgress@WinREAgent@@QEAAXXZ; WinREAgent::OperationProgress::CompletedOperation(void)
0x1800219fc  lea     rcx, [rbp+40h+var_60]
0x180021a00  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x180021a05  test    eax, eax
0x180021a07  jns     short loc_180021A37
0x180021a09  lea     rcx, aFailedToDelete; "Failed to delete directory"
0x180021a10  mov     [rsp+140h+var_118], rcx
0x180021a15  mov     dword ptr [rsp+140h+var_120], 28Fh
0x180021a1d  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180021a24  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x180021a2b  mov     edx, eax
0x180021a2d  mov     ecx, 1
0x180021a32  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180021a37  lea     rcx, [rsp+140h+lpFileName]
0x180021a3c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180021a41  nop
0x180021a42  lea     rdx, aExportedWim; "exported.wim"
0x180021a49  lea     rcx, [rsp+140h+var_F0]
0x180021a4e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180021a53  nop
0x180021a54  lea     r8, [rsp+140h+lpFileName]
0x180021a59  lea     rdx, [rsp+140h+var_F0]
0x180021a5e  mov     rcx, r13
0x180021a61  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180021a66  mov     ebx, eax
0x180021a68  mov     rcx, [rsp+140h+var_F0]
0x180021a6d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021a71  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021a76  test    ebx, ebx
0x180021a78  jns     short loc_180021AAD
0x180021a7a  lea     rax, aFailedToBuildP_2; "Failed to build path to exported.wim"
0x180021a81  mov     [rsp+140h+var_118], rax
0x180021a86  mov     dword ptr [rsp+140h+var_120], 296h
0x180021a8e  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180021a95  lea     r8, aWinreagentPrep_0; "WinREAgent::PrepareWinRE::InternalExecu"...
0x180021a9c  mov     edx, ebx
0x180021a9e  mov     ecx, 2
0x180021aa3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180021aa8  jmp     loc_180021D62
0x180021aad  cmp     qword ptr [r14+1C0h], 0
0x180021ab5  jz      loc_180021B47
0x180021abb  lea     rdx, aPreparewinreSa; "PrepareWinRE: Save exported WinRE wim p"...
0x180021ac2  xor     ecx, ecx
0x180021ac4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
  ... truncated ...
```
