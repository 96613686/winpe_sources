# CDeploymentSession::GetPackageFileListPath(ActionList::Package const * const,wchar_t * *)

- ea: `0x180062e60`
- end: `0x1800638dc`
- name: `?GetPackageFileListPath@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z`
- size: `2684`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, const struct ActionList::Package *const, wchar_t **)`
- caller_count: `4`
- callee_count: `29`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ab64`
- `0x18004af24`
- `0x180054e0c`
- `0x18007c740`

## callees

- `0x1800059d0`
- `0x180005cf0`
- `0x180008fbc`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18000dd74`
- `0x18000ec6c`
- `0x18001f05c`
- `0x18001f244`
- `0x18002374c`
- `0x180038ecc`
- `0x180039f90`
- `0x18003c418`
- `0x1800408d0`
- `0x180058134`
- `0x180062e60`
- `0x180077664`
- `0x180078b9c`
- `0x180094d0c`
- `0x18009ad18`
- `0x18009d254`
- `0x180149180`
- `0x180149300`
- `0x1801507cc`
- `0x1801df624`
- `0x180203760`
- `0x180203fa4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180063739`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180063739`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006365f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006369e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800636ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063750`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006365f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006369e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800636ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006334c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063674`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800636b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063765`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006334c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063674`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800636b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063765`

## string_xrefs

- `0x18006389a`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x1800638b4`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x1800638c9`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180062f0b`: `CDeploymentSession::GetPackageFileListPath`
- `0x180062f5a`: `CDeploymentSession::GetPackageFileListPath`
- `0x1800632fd`: `CDeploymentSession::GetPackageFileListPath`
- `0x18006338d`: `CDeploymentSession::GetPackageFileListPath`
- `0x1800637e8`: `CDeploymentSession::GetPackageFileListPath`
- `0x18006312a`: `MFL creation failed and Package is LCU. Attempt fallback to expanding the metadata cab.`
- `0x18006318a`: `TargetPath: [%s]`
- `0x1800631bb`: `Failed to delete target directory. Error: [0x%X]`
- `0x1800631ee`: `Failed to create target directory. Error: [0x%X]`
- `0x1800633fd`: `TargetPath: [{}]`
- `0x180063471`: `Failed to create target directory`

## pseudocode

```c
__int64 __fastcall CDeploymentSession::GetPackageFileListPath(
        CDeploymentSession *this,
        const struct ActionList::Package *const a2,
        wchar_t **a3)
{
  wchar_t **v3; // r12
  _QWORD *v6; // rax
  int *v7; // rdx
  __int64 v8; // rcx
  int v9; // edi
  __int64 updated; // rcx
  __int64 v11; // rcx
  unsigned int v12; // eax
  void *v13; // rbx
  int StringCch; // eax
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  int Directory; // eax
  __int64 v25; // rcx
  int v26; // eax
  unsigned int i; // r12d
  __int64 v28; // rbx
  __int64 v29; // rdi
  __int64 v30; // r13
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  wchar_t *v35; // rbx
  HANDLE v36; // rax
  int v37; // eax
  __int64 v38; // rcx
  unsigned int v39; // ebx
  __int64 v40; // rdx
  const char *v41; // r9
  wchar_t *v42; // rcx
  unsigned int v43; // ebx
  const char *v44; // r9
  int exists; // eax
  int v46; // ebx
  __int64 v47; // rdx
  int v48; // eax
  int CabFile; // eax
  __int64 v50; // r8
  __int64 v51; // rdx
  int AllFiles; // eax
  __int64 v53; // rdx
  wchar_t *v54; // rbx
  HANDLE v55; // rax
  wchar_t *v56; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v58; // rax
  const char *v59; // r9
  wchar_t *v60; // rbx
  HANDLE v61; // rax
  wchar_t *v62; // rbx
  HANDLE v63; // rax
  __int64 result; // rax
  __int64 v65; // rcx
  __int64 v66; // rcx
  int v67; // eax
  void *v68; // rbx
  int Internal; // eax
  int *v70; // [rsp+20h] [rbp-E8h]
  int v71; // [rsp+20h] [rbp-E8h]
  __int64 v72; // [rsp+28h] [rbp-E0h]
  int v73; // [rsp+28h] [rbp-E0h]
  wchar_t *v74; // [rsp+30h] [rbp-D8h] BYREF
  int v75[2]; // [rsp+38h] [rbp-D0h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t **v77; // [rsp+48h] [rbp-C0h]
  _QWORD v78[2]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v79[3]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v80[16]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v81; // [rsp+88h] [rbp-80h] BYREF
  int v82; // [rsp+98h] [rbp-70h] BYREF
  wchar_t *v83; // [rsp+A0h] [rbp-68h] BYREF
  wchar_t *v84; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v85[2]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v79[2] = -2;
  v3 = a3;
  v77 = a3;
  v74 = 0;
  hLibModule = 0;
  v83 = 0;
  v85[0] = 0;
  v85[1] = 0;
  try
  {
    v6 = operator new(0x40u);
    *v6 = v6;
    v6[1] = v6;
    v6[2] = v6;
    *((_WORD *)v6 + 12) = 257;
    v85[0] = v6;
    v81 = 0;
    if ( !a2 )
    {
      v8 = *((_QWORD *)this + 75);
      v9 = -2147024809;
      if ( !v8 )
      {
LABEL_4:
        updated = 0;
        goto LABEL_8;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v8,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GetPackageFileListPath",
                                1215,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
      goto LABEL_8;
    }
    if ( !v3 )
    {
      v11 = *((_QWORD *)this + 75);
      v9 = -2147024809;
      if ( !v11 )
        goto LABEL_4;
      v73 = -2147024809;
      v71 = 1216;
      goto LABEL_12;
    }
    v12 = *((_DWORD *)this + 114);
    if ( v12 == 9 )
    {
      v13 = (void *)*((_QWORD *)this + 64);
      if ( v13 )
      {
        v82 = 0;
        StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v13, &v82);
        v9 = StringCch;
        if ( StringCch < 0 )
        {
LABEL_18:
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
LABEL_19:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
          if ( v9 < 0 )
          {
            v11 = *((_QWORD *)this + 75);
            if ( !v11 )
              goto LABEL_4;
            v73 = v9;
            v71 = 1220;
            goto LABEL_12;
          }
LABEL_105:
          v58 = v74;
          v74 = 0;
          *v3 = v58;
          goto LABEL_106;
        }
      }
      else
      {
        v13 = 0;
      }
      StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v13);
      v9 = StringCch;
      if ( StringCch >= 0 )
        goto LABEL_19;
      goto LABEL_18;
    }
    if ( v12 > 0x16 || (v15 = 4195440, !_bittest(&v15, v12)) )
    {
      v68 = (void *)*((_QWORD *)a2 + 16);
      v82 = 0;
      if ( v68
        && (Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v68, &v82),
            v9 = Internal,
            Internal < 0)
        || (Internal = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v68),
            v9 = Internal,
            Internal < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
      if ( v9 >= 0 )
        goto LABEL_105;
      v11 = *((_QWORD *)this + 75);
      if ( !v11 )
        goto LABEL_4;
      v73 = v9;
      v71 = 1357;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v11,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GetPackageFileListPath",
                                v71,
                                v73);
      goto LABEL_6;
    }
    v16 = CDeploymentSession::CheckCancelRequested(this, v7);
    v9 = v16;
    if ( v16 < 0 )
    {
      v11 = *((_QWORD *)this + 75);
      if ( !v11 )
        goto LABEL_4;
      v73 = v16;
      v71 = 1228;
      goto LABEL_12;
    }
    v9 = CDeploymentSession::GeneratePackageFileList(this, a2, &v74);
    if ( (unsigned int)(v9 + 2146498528) <= 1 || v9 == -2147023673 )
    {
      v65 = *((_QWORD *)this + 75);
      if ( v65 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v65,
          4,
          L"User cancelled the operation. Error: [0x%X]",
          (unsigned int)v9);
      v66 = *((_QWORD *)this + 75);
      if ( v66 )
      {
        v67 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v66,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::GetPackageFileListPath",
                1235,
                -2147023673);
        updated = (unsigned int)v67;
        if ( v67 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v67);
      }
      else
      {
        updated = 0;
      }
      v9 = -2147023673;
      goto LABEL_8;
    }
    if ( v9 >= 0 )
      goto LABEL_105;
    v17 = *((_QWORD *)this + 75);
    if ( v17 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v17,
        3,
        L"Failed to generate PackageFileList. Error: [0x%X]",
        (unsigned int)v9);
    LODWORD(v81) = v9;
    *((_QWORD *)&v81 + 1) = *((_QWORD *)a2 + 7);
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))(**((_QWORD **)this + 75) + 288LL))(
            *((_QWORD *)this + 75),
            &v81,
            16);
    if ( v18 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( v19 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v19,
          3,
          L"ReportEventFellBackToDownloadingAllPackageFiles failed with: [0x%X].",
          (unsigned int)v18);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl)
      || *((_DWORD *)a2 + 22) != 6 )
    {
LABEL_102:
      v56 = v74;
      if ( v74 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v56 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v74 = 0;
      }
      v9 = 0;
      goto LABEL_105;
    }
    v20 = *((_QWORD *)this + 75);
    if ( v20 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v20,
        2,
        L"MFL creation failed and Package is LCU. Attempt fallback to expanding the metadata cab.");
    v21 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *((_QWORD *)a2 + 9), 0);
    v9 = v21;
    v11 = *((_QWORD *)this + 75);
    if ( v21 < 0 )
    {
      if ( !v11 )
        goto LABEL_4;
      v73 = v21;
      v71 = 1266;
      goto LABEL_12;
    }
    if ( v11 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v11, 2, L"TargetPath: [%s]", v83);
    v22 = RecursiveRemoveDirectory(v11, v83);
    if ( v22 < 0 )
    {
      v23 = *((_QWORD *)this + 75);
      if ( v23 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v23,
          3,
          L"Failed to delete target directory. Error: [0x%X]",
          (unsigned int)v22);
    }
    Directory = RecursivelyCreateDirectory(v83, 0);
    v9 = Directory;
    if ( Directory < 0 )
    {
      v25 = *((_QWORD *)this + 75);
      if ( v25 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v25,
          4,
          L"Failed to create target directory. Error: [0x%X]",
          (unsigned int)Directory);
      v11 = *((_QWORD *)this + 75);
      if ( !v11 )
        goto LABEL_4;
      v73 = v9;
      v71 = 1279;
      goto LABEL_12;
    }
    v26 = DpxLoad(&hLibModule);
    v9 = v26;
    if ( v26 < 0 )
    {
      v11 = *((_QWORD *)this + 75);
      if ( !v11 )
        goto LABEL_4;
      v73 = v26;
      v71 = 1284;
      goto LABEL_12;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)a2 + 30) )
      {
        v3 = v77;
        goto LABEL_102;
      }
      v84 = 0;
      v28 = 184LL * i;
      v29 = *((_QWORD *)a2 + 14);
      v30 = v28 + v29;
      if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
              v85,
              v28 + v29 + 24) )
      {
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(
          v85,
          v80,
          v30 + 24);
        v31 = *((_QWORD *)this + 61);
        if ( *((_DWORD *)a2 + 30) <= 1u )
        {
          v37 = CMiscHelpersT<CEmptyType>::CombinePath(v31, *((_QWORD *)a2 + 9), 0);
          v9 = v37;
          if ( v37 < 0 )
          {
            v38 = *((_QWORD *)this + 75);
            if ( v38 )
            {
              LODWORD(v72) = v37;
              LODWORD(v70) = 1311;
              goto LABEL_70;
            }
            goto LABEL_61;
          }
        }
        else
        {
          v32 = CMiscHelpersT<CEmptyType>::CombinePath(v31, *(_QWORD *)(v28 + v29 + 96), 0);
          v9 = v32;
          if ( v32 < 0 )
          {
            v33 = *((_QWORD *)this + 75);
            if ( !v33 )
              goto LABEL_61;
            LODWORD(v72) = v32;
            LODWORD(v70) = 1307;
            v34 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v33,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::GetPackageFileListPath",
                                  v70,
                                  v72);
LABEL_63:
            if ( (int)v34 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
LABEL_65:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v34);
            v35 = v84;
            if ( !v84 )
              goto LABEL_106;
            v36 = GetProcessHeap();
            HeapFree(v36, 0, v35 - 2);
            updated = 0;
LABEL_8:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_106:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v85);
            v60 = v83;
            if ( v83 )
            {
              v61 = GetProcessHeap();
              HeapFree(v61, 0, v60 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v83 = 0;
            }
            if ( hLibModule )
              FreeLibrary(hLibModule);
            v62 = v74;
            if ( v74 )
            {
              v63 = GetProcessHeap();
              HeapFree(v63, 0, v62 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            return (unsigned int)v9;
          }
        }
        if ( v83 )
          v39 = *((_DWORD *)v83 - 1);
        else
          v39 = 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v42 = v83;
        v78[0] = v83;
        v78[1] = v39;
        if ( v83[v39] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xB6,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
            v41);
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LOBYTE(v40) = 1;
          LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v40,
            1,
            "TargetPath: [{}]",
            v78);
          v42 = v83;
        }
        if ( v42 )
          v43 = *((_DWORD *)v42 - 1);
        else
          v43 = 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v79[0] = v83;
        v79[1] = v43;
        if ( v83[v43] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xB6,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
            v44);
        exists = EnsureDirectoryExistsHr(v79);
        v46 = exists;
        if ( exists < 0 )
        {
          v82 = exists;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to create target directory");
            *(_QWORD *)v75 = &v82;
            v70 = v75;
            LOBYTE(v47) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v47,
              3,
              ": {}");
          }
        }
        if ( v46 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x525,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v46,
            (int)v70);
        v48 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v30 + 24), 0);
        v9 = v48;
        v38 = *((_QWORD *)this + 75);
        if ( v48 < 0 )
        {
          if ( v38 )
          {
            LODWORD(v72) = v48;
            LODWORD(v70) = 1319;
            goto LABEL_70;
          }
LABEL_61:
          v34 = 0;
          goto LABEL_65;
        }
        if ( v38 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v38, 2, L"SourceFile: [%s]", v84);
        CabFile = ExtractCabFile(v84, v83, 1);
        if ( CabFile < 0 )
        {
          v82 = CabFile;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<SH_SSTRING,SH_SSTRING>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              v50,
              "Failed to extract file as cab: {} in metadata folder {}. Trying to extract as WIM",
              &v84,
              &v83);
            *(_QWORD *)v75 = &v82;
            v70 = v75;
            LOBYTE(v51) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v51,
              1,
              ": {0}");
          }
          AllFiles = CbsEsdExtractAllFiles(v84, v83);
          v9 = AllFiles;
          if ( AllFiles < 0 )
          {
            v82 = AllFiles;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to extract file as wim: {}",
                &v84);
              *(_QWORD *)v75 = &v82;
              v70 = v75;
              LOBYTE(v53) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v53,
                3,
                ": {0}");
            }
            v38 = *((_QWORD *)this + 75);
            if ( !v38 )
              goto LABEL_61;
            LODWORD(v72) = v9;
            LODWORD(v70) = 1335;
LABEL_70:
            v34 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v38,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::GetPackageFileListPath",
                                  v70,
                                  v72);
            goto LABEL_63;
          }
        }
      }
      v54 = v84;
      if ( v84 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, v54 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x554,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v59);
  }
  return result;
}

```

## disassembly

```asm
0x180062e60  mov     r11, rsp
0x180062e63  push    rbx
0x180062e64  push    rsi
0x180062e65  push    rdi
0x180062e66  push    r12
0x180062e68  push    r13
0x180062e6a  push    r14
0x180062e6c  push    r15
0x180062e6e  sub     rsp, 0D0h
0x180062e75  mov     [rsp+108h+var_98], 0FFFFFFFFFFFFFFFEh
0x180062e7e  mov     rax, cs:__security_cookie
0x180062e85  xor     rax, rsp
0x180062e88  mov     [rsp+108h+var_48], rax
0x180062e90  mov     r12, r8
0x180062e93  mov     [rsp+108h+var_C0], r8
0x180062e98  mov     r14, rdx
0x180062e9b  mov     rsi, rcx
0x180062e9e  xor     r13d, r13d
0x180062ea1  mov     [rsp+108h+var_D8], r13
0x180062ea6  mov     [rsp+108h+hLibModule], r13
0x180062eab  mov     [r11-68h], r13
0x180062eaf  mov     [r11-58h], r13
0x180062eb3  mov     [r11-50h], r13
0x180062eb7  lea     ecx, [r13+40h]; Size
0x180062ebb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062ec0  mov     [rax], rax
0x180062ec3  mov     [rax+8], rax
0x180062ec7  mov     [rax+10h], rax
0x180062ecb  mov     word ptr [rax+18h], 101h
0x180062ed1  mov     [rsp+108h+var_58], rax
0x180062ed9  xorps   xmm0, xmm0
0x180062edc  movups  [rsp+108h+var_80], xmm0
0x180062ee4  test    r14, r14
0x180062ee7  jnz     short loc_180062F38
0x180062ee9  mov     rcx, [rsi+258h]
0x180062ef0  mov     edi, 80070057h
0x180062ef5  test    rcx, rcx
0x180062ef8  jnz     short loc_180062EFF
0x180062efa  mov     ecx, r13d
0x180062efd  jmp     short loc_180062F2E
0x180062eff  mov     dword ptr [rsp+108h+var_E0], edi
0x180062f03  mov     [rsp+108h+var_E8], 4BFh
0x180062f0b  lea     r9, aCdeploymentses_18; "CDeploymentSession::GetPackageFileListP"...
0x180062f12  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180062f19  mov     edx, 4
0x180062f1e  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180062f23  mov     ecx, eax
0x180062f25  test    ecx, ecx
0x180062f27  jns     short loc_180062F2E
0x180062f29  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180062f2e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180062f33  jmp     loc_1800636DC
0x180062f38  test    r12, r12
0x180062f3b  jnz     short loc_180062F76
0x180062f3d  mov     rcx, [rsi+258h]
0x180062f44  mov     edi, 80070057h
0x180062f49  test    rcx, rcx
0x180062f4c  jz      short loc_180062EFA
0x180062f4e  mov     dword ptr [rsp+108h+var_E0], edi
0x180062f52  mov     [rsp+108h+var_E8], 4C0h
0x180062f5a  lea     r9, aCdeploymentses_18; "CDeploymentSession::GetPackageFileListP"...
0x180062f61  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180062f68  mov     edx, 4
0x180062f6d  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180062f72  mov     ecx, eax
0x180062f74  jmp     short loc_180062F25
0x180062f76  mov     eax, [rsi+1C8h]
0x180062f7c  cmp     eax, 9
0x180062f7f  jnz     loc_180063008
0x180062f85  mov     rbx, [rsi+200h]
0x180062f8c  test    rbx, rbx
0x180062f8f  jnz     short loc_180062F99
0x180062f91  mov     edx, r13d
0x180062f94  mov     rbx, r13
0x180062f97  jmp     short loc_180062FBE
0x180062f99  mov     [rsp+108h+var_70], r13d
0x180062fa1  lea     rdx, [rsp+108h+var_70]
0x180062fa9  mov     rcx, rbx
0x180062fac  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x180062fb1  mov     edi, eax
0x180062fb3  test    eax, eax
0x180062fb5  js      short loc_180062FD1
0x180062fb7  mov     edx, [rsp+108h+var_70]
0x180062fbe  lea     r8, [rsp+108h+var_D8]
0x180062fc3  mov     rcx, rbx; Src
0x180062fc6  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x180062fcb  mov     edi, eax
0x180062fcd  test    eax, eax
0x180062fcf  jns     short loc_180062FD8
0x180062fd1  mov     ecx, eax
0x180062fd3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180062fd8  mov     ecx, edi
0x180062fda  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180062fdf  test    edi, edi
0x180062fe1  jns     loc_1800636CE
0x180062fe7  mov     rcx, [rsi+258h]
0x180062fee  test    rcx, rcx
0x180062ff1  jz      loc_180062EFA
0x180062ff7  mov     dword ptr [rsp+108h+var_E0], edi
0x180062ffb  mov     [rsp+108h+var_E8], 4C4h
0x180063003  jmp     loc_180062F5A
0x180063008  cmp     eax, 16h
0x18006300b  ja      loc_180063815
0x180063011  mov     ecx, 400470h
0x180063016  bt      ecx, eax
0x180063019  jnb     loc_180063815
0x18006301f  mov     rcx, rsi; this
0x180063022  call    ?CheckCancelRequested@CDeploymentSession@@QEAAJPEAH@Z; CDeploymentSession::CheckCancelRequested(int *)
0x180063027  mov     edi, eax
0x180063029  test    eax, eax
0x18006302b  jns     short loc_18006304E
0x18006302d  mov     rcx, [rsi+258h]
0x180063034  test    rcx, rcx
0x180063037  jz      loc_180062EFA
0x18006303d  mov     dword ptr [rsp+108h+var_E0], eax
0x180063041  mov     [rsp+108h+var_E8], 4CCh
0x180063049  jmp     loc_180062F5A
0x18006304e  lea     r8, [rsp+108h+var_D8]; wchar_t **
0x180063053  mov     rdx, r14; struct ActionList::Package *
0x180063056  mov     rcx, rsi; this
0x180063059  call    ?GeneratePackageFileList@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z; CDeploymentSession::GeneratePackageFileList(ActionList::Package const * const,wchar_t * *)
0x18006305e  mov     edi, eax
0x180063060  add     eax, 7FF0F7E0h
0x180063065  cmp     eax, 1
0x180063068  jbe     loc_1800637A7
0x18006306e  cmp     edi, 800704C7h
0x180063074  jz      loc_1800637A7
0x18006307a  test    edi, edi
0x18006307c  jns     loc_1800636CE
0x180063082  mov     rcx, [rsi+258h]
0x180063089  mov     r15d, 3
0x18006308f  test    rcx, rcx
0x180063092  jz      short loc_1800630A6
0x180063094  mov     r9d, edi
0x180063097  lea     r8, aFailedToGenera_1; "Failed to generate PackageFileList. Err"...
0x18006309e  mov     edx, r15d
0x1800630a1  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800630a6  mov     dword ptr [rsp+108h+var_80], edi
0x1800630ad  mov     rax, [r14+38h]
0x1800630b1  mov     qword ptr [rsp+108h+var_80+8], rax
0x1800630b9  mov     rcx, [rsi+258h]
0x1800630c0  mov     rax, [rcx]
0x1800630c3  mov     r8d, 10h
0x1800630c9  lea     rdx, [rsp+108h+var_80]
0x1800630d1  mov     rax, [rax+120h]
0x1800630d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630dd  test    eax, eax
0x1800630df  jns     short loc_1800630FF
0x1800630e1  mov     rcx, [rsi+258h]
0x1800630e8  test    rcx, rcx
0x1800630eb  jz      short loc_1800630FF
0x1800630ed  mov     r9d, eax
0x1800630f0  lea     r8, aReporteventfel_3; "ReportEventFellBackToDownloadingAllPack"...
0x1800630f7  mov     edx, r15d
0x1800630fa  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800630ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer> `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl(void)'::`2'::impl
0x180063106  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(void)
0x18006310b  test    al, al
0x18006310d  jz      loc_180063694
0x180063113  cmp     dword ptr [r14+58h], 6
0x180063118  jnz     loc_180063694
0x18006311e  mov     rcx, [rsi+258h]
0x180063125  test    rcx, rcx
0x180063128  jz      short loc_18006313B
0x18006312a  lea     r8, aMflCreationFai; "MFL creation failed and Package is LCU."...
0x180063131  mov     edx, 2
0x180063136  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006313b  lea     r9, [rsp+108h+var_68]
0x180063143  xor     r8d, r8d
0x180063146  mov     rdx, [r14+48h]
0x18006314a  mov     rcx, [rsi+1E8h]
0x180063151  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180063156  mov     edi, eax
0x180063158  mov     rcx, [rsi+258h]
0x18006315f  test    eax, eax
0x180063161  jns     short loc_18006317D
0x180063163  test    rcx, rcx
0x180063166  jz      loc_180062EFA
0x18006316c  mov     dword ptr [rsp+108h+var_E0], eax
0x180063170  mov     [rsp+108h+var_E8], 4F2h
0x180063178  jmp     loc_180062F5A
0x18006317d  test    rcx, rcx
0x180063180  jz      short loc_18006319B
0x180063182  mov     r9, [rsp+108h+var_68]
0x18006318a  lea     r8, aTargetpathS; "TargetPath: [%s]"
0x180063191  mov     edx, 2
0x180063196  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006319b  mov     rdx, [rsp+108h+var_68]
0x1800631a3  call    RecursiveRemoveDirectory
0x1800631a8  test    eax, eax
0x1800631aa  jns     short loc_1800631CA
0x1800631ac  mov     rcx, [rsi+258h]
0x1800631b3  test    rcx, rcx
0x1800631b6  jz      short loc_1800631CA
0x1800631b8  mov     r9d, eax
0x1800631bb  lea     r8, aFailedToDelete_6; "Failed to delete target directory. Erro"...
0x1800631c2  mov     edx, r15d
0x1800631c5  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800631ca  xor     edx, edx
0x1800631cc  mov     rcx, [rsp+108h+var_68]
0x1800631d4  call    RecursivelyCreateDirectory
0x1800631d9  mov     edi, eax
0x1800631db  test    eax, eax
0x1800631dd  jns     short loc_180063220
0x1800631df  mov     rcx, [rsi+258h]
0x1800631e6  test    rcx, rcx
0x1800631e9  jz      short loc_1800631FF
0x1800631eb  mov     r9d, eax
0x1800631ee  lea     r8, aFailedToCreate_36; "Failed to create target directory. Erro"...
0x1800631f5  mov     edx, 4
0x1800631fa  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800631ff  mov     rcx, [rsi+258h]
0x180063206  test    rcx, rcx
0x180063209  jz      loc_180062EFA
0x18006320f  mov     dword ptr [rsp+108h+var_E0], edi
0x180063213  mov     [rsp+108h+var_E8], 4FFh
0x18006321b  jmp     loc_180062F5A
0x180063220  lea     rcx, [rsp+108h+hLibModule]; HINSTANCE *
0x180063225  call    ?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z; DpxLoad(HINSTANCE__ * *)
0x18006322a  mov     edi, eax
0x18006322c  test    eax, eax
0x18006322e  jns     short loc_180063251
0x180063230  mov     rcx, [rsi+258h]
0x180063237  test    rcx, rcx
0x18006323a  jz      loc_180062EFA
0x180063240  mov     dword ptr [rsp+108h+var_E0], eax
0x180063244  mov     [rsp+108h+var_E8], 504h
0x18006324c  jmp     loc_180062F5A
0x180063251  mov     r12d, r13d
0x180063254  cmp     r12d, [r14+78h]
0x180063258  jnb     loc_18006368F
0x18006325e  mov     [rsp+108h+var_60], r13
0x180063266  mov     eax, r12d
0x180063269  imul    rbx, rax, 0B8h
0x180063270  mov     rdi, [r14+70h]
0x180063274  lea     r13, [rbx+rdi]
0x180063278  lea     rdx, [r13+18h]
0x18006327c  lea     rcx, [rsp+108h+var_58]
0x180063284  call    ??$count@PEA_WUWstringCaseInsensitiveCompare@@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEBA_KAEBQEA_W@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(wchar_t * const &)
0x180063289  test    rax, rax
0x18006328c  jz      short loc_180063296
0x18006328e  xor     r13d, r13d
0x180063291  jmp     loc_180063652
0x180063296  lea     r8, [r13+18h]
0x18006329a  lea     rdx, [rsp+108h+var_90]
0x18006329f  lea     rcx, [rsp+108h+var_58]
0x1800632a7  call    ??$emplace@AEBQEA_W@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBQEA_W@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(wchar_t * const &)
0x1800632ac  lea     r9, [rsp+108h+var_68]
0x1800632b4  xor     r8d, r8d
0x1800632b7  mov     rcx, [rsi+1E8h]
0x1800632be  cmp     dword ptr [r14+78h], 1
0x1800632c3  jbe     loc_18006335F
0x1800632c9  mov     rdx, [rbx+rdi+60h]
0x1800632ce  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1800632d3  mov     edi, eax
0x1800632d5  test    eax, eax
0x1800632d7  jns     loc_1800633AC
0x1800632dd  mov     rcx, [rsi+258h]
0x1800632e4  xor     r13d, r13d
0x1800632e7  test    rcx, rcx
0x1800632ea  jnz     short loc_1800632F1
0x1800632ec  mov     ecx, r13d
0x1800632ef  jmp     short loc_180063320
0x1800632f1  mov     dword ptr [rsp+108h+var_E0], eax
0x1800632f5  mov     [rsp+108h+var_E8], 51Bh
0x1800632fd  lea     r9, aCdeploymentses_18; "CDeploymentSession::GetPackageFileListP"...
0x180063304  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006330b  mov     edx, 4
0x180063310  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180063315  mov     ecx, eax
0x180063317  test    ecx, ecx
0x180063319  jns     short loc_180063320
0x18006331b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180063320  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180063325  nop
0x180063326  mov     rbx, [rsp+108h+var_60]
0x18006332e  test    rbx, rbx
0x180063331  jz      loc_1800636DC
0x180063337  call    cs:__imp_GetProcessHeap
0x18006333e  nop     dword ptr [rax+rax+00h]
0x180063343  mov     rcx, rax; hHeap
0x180063346  lea     r8, [rbx-4]; lpMem
0x18006334a  xor     edx, edx; dwFlags
0x18006334c  call    cs:__imp_HeapFree
0x180063353  nop     dword ptr [rax+rax+00h]
0x180063358  xor     ecx, ecx
0x18006335a  jmp     loc_180062F2E
0x18006335f  mov     rdx, [r14+48h]
0x180063363  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180063368  mov     edi, eax
0x18006336a  test    eax, eax
0x18006336c  jns     short loc_1800633AC
0x18006336e  mov     rcx, [rsi+258h]
0x180063375  xor     r13d, r13d
0x180063378  test    rcx, rcx
0x18006337b  jz      loc_1800632EC
0x180063381  mov     dword ptr [rsp+108h+var_E0], eax
0x180063385  mov     [rsp+108h+var_E8], 51Fh
0x18006338d  lea     r9, aCdeploymentses_18; "CDeploymentSession::GetPackageFileListP"...
0x180063394  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
  ... truncated ...
```
