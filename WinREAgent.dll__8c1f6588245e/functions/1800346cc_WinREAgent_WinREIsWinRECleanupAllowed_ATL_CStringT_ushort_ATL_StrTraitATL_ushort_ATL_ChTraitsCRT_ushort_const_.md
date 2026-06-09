# WinREAgent::WinREIsWinRECleanupAllowed(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x1800346cc`
- end: `0x180035523`
- name: `?WinREIsWinRECleanupAllowed@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@PEA_NPEAV23@@Z`
- size: `3671`
- prototype: ``
- caller_count: `4`
- callee_count: `43`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000febc`
- `0x180024a40`
- `0x180027204`
- `0x180027580`

## callees

- `0x1800028e4`
- `0x180004978`
- `0x1800049a4`
- `0x180004af8`
- `0x1800050bc`
- `0x180005c70`
- `0x180005cc0`
- `0x180006500`
- `0x1800066f8`
- `0x18000677c`
- `0x1800074b8`
- `0x1800089d0`
- `0x18000d540`
- `0x18000d8c0`
- `0x18000d92c`
- `0x1800119dc`
- `0x180011ef4`
- `0x180012d60`
- `0x180013e74`
- `0x18002476c`
- `0x180033a20`
- `0x180033c44`
- `0x180033c94`
- `0x180033fbc`
- `0x180034480`
- `0x1800345c0`
- `0x1800346cc`
- `0x18003552c`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004c614`
- `0x18004e144`
- `0x18004e47c`
- `0x18004e5a4`
- `0x18004e7f8`
- `0x18004e9dc`
- `0x18004ea8c`
- `0x18004fb00`
- `0x18005c8b8`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180034f17`
- `msvcrt!_wcsicmp` at `0x180034f17`
- `KERNEL32!GetLastError` at `0x180034b47`
- `KERNEL32!GetLastError` at `0x180034b81`
- `KERNEL32!GetLastError` at `0x180034b47`
- `KERNEL32!GetLastError` at `0x180034b81`
- `KERNEL32!GetWindowsDirectoryW` at `0x180034b3d`
- `KERNEL32!GetWindowsDirectoryW` at `0x180034b3d`

## string_xrefs

- `0x180034837`: `Failed to create OneSettings infrastructure`
- `0x18003490a`: `WinRECleanupCanDeleteList`
- `0x180034b5b`: `Failed to get host system Windows directory`
- `0x180034729`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180034793`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x1800352a3`: `Failed to get volume relative path of [%s]`
- `0x180034730`: `WinREAgent::WinREIsWinRECleanupAllowed`
- `0x18003479a`: `WinREAgent::WinREIsWinRECleanupAllowed`
- `0x1800347ae`: `Getting can delete list`
- `0x1800347ee`: `Add [%s] to can delete list`
- `0x180034a4f`: `Getting extra can delete list from caller`
- `0x180034bf0`: `Failed to get volume for OS directory [%s]`
- `0x180034cfc`: `Failed to parse can delete list`
- `0x180035332`: `Failed to construct path to [%s] in [%s]`
- `0x180034f81`: `Failed to get size of directory [%s]`
- `0x180035067`: `Cannot delete content: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall WinREAgent::WinREIsWinRECleanupAllowed(_QWORD *a1, __int64 a2, bool *a3, _QWORD *a4)
{
  bool *v4; // rdi
  int VolumeRelPath; // r15d
  __int64 v9; // r8
  unsigned __int64 i; // rbx
  __int64 *v11; // rax
  __int64 v12; // r8
  _QWORD *v13; // rax
  struct ISetupOneSettings **v14; // rax
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rcx
  int SetupOneSettings; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, const wchar_t *, __int64, unsigned int *); // rbx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // rdx
  _QWORD *v26; // rcx
  int *v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // r8
  unsigned __int64 j; // rbx
  __int64 *v31; // rax
  signed int Volume; // ebx
  signed int LastError; // eax
  signed int v34; // eax
  int v35; // edx
  int v36; // r8d
  int v37; // r9d
  int v38; // edx
  int v39; // r8d
  int v40; // r9d
  int v41; // xmm5_4
  _QWORD *v42; // rax
  unsigned int v43; // ebx
  __int64 v44; // r8
  unsigned __int64 v45; // rax
  __int64 v46; // rsi
  _QWORD *v47; // rax
  __int64 v48; // r8
  unsigned __int64 v49; // rax
  _QWORD *v50; // rax
  int v51; // r14d
  char IsFile; // al
  wchar_t *v53; // r14
  int v54; // edi
  __int64 v55; // rdi
  char v56; // al
  char v57; // bl
  ATL::CStringData *v58; // rcx
  unsigned __int8 v59; // al
  char IsEnabled; // al
  __int64 v61; // rbx
  _QWORD *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rsi
  __int64 v65; // rbx
  __int64 v66; // rbx
  ATL::CStringData *v67; // rcx
  ATL::CStringData *v68; // rcx
  __int64 v69; // rdi
  __int64 v70; // rbx
  __int64 v71; // rbx
  _QWORD *v72; // r12
  int *v73; // rdi
  __int64 v74; // rbx
  unsigned int v75; // ecx
  const wchar_t *v76; // r8
  unsigned __int8 v77; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v78[7]; // [rsp+41h] [rbp-BFh] BYREF
  __int64 v79; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v80; // [rsp+50h] [rbp-B0h] BYREF
  ATL::CStringData *v81; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v82; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v83; // [rsp+68h] [rbp-98h] BYREF
  __int64 v84; // [rsp+70h] [rbp-90h] BYREF
  __int64 v85; // [rsp+78h] [rbp-88h] BYREF
  __int64 v86; // [rsp+80h] [rbp-80h] BYREF
  ATL::CStringData *v87; // [rsp+88h] [rbp-78h]
  wchar_t *String1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v89; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v90; // [rsp+A0h] [rbp-60h]
  __int64 v91; // [rsp+A8h] [rbp-58h]
  int v92; // [rsp+B0h] [rbp-50h]
  __int64 v93; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v94; // [rsp+C0h] [rbp-40h]
  __int64 v95; // [rsp+C8h] [rbp-38h]
  int v96; // [rsp+D0h] [rbp-30h]
  bool *v97; // [rsp+D8h] [rbp-28h]
  _QWORD v98[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v99; // [rsp+F8h] [rbp-8h]
  _QWORD *v100; // [rsp+100h] [rbp+0h]
  _BYTE v101[80]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v102[80]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v103; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v104[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v105[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v106; // [rsp+1D8h] [rbp+D8h] BYREF
  WCHAR Buffer[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v100 = a4;
  v4 = a3;
  v97 = a3;
  VolumeRelPath = 0;
  if ( !a3 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      428,
      L"res cannot be null");
    return 2147942487LL;
  }
  if ( !a4 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      429,
      L"unknownContentReport cannot be null");
    return 2147942487LL;
  }
  memset(v98, 0, sizeof(v98));
  v99 = 0;
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::SetCount(
    v98,
    0);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl) )
  {
    if ( a2 )
    {
      PushButtonReset::Logging::Trace(0, L"Getting can delete list");
      for ( i = 0; i < *(_QWORD *)(a2 + 8); ++i )
      {
        v11 = (__int64 *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                           a2,
                           i,
                           v9);
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
          v98,
          *v11);
        v13 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                          a2,
                          i,
                          v12);
        PushButtonReset::Logging::Trace(0, L"Add [%s] to can delete list", *v13);
      }
    }
  }
  else
  {
    v104[1] = 0;
    v104[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
    v14 = (struct ISetupOneSettings **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v104);
    SetupOneSettings = CreateSetupOneSettings(v16, v15, v14);
    if ( SetupOneSettings < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)SetupOneSettings,
        "WinREAgent::WinREIsWinRECleanupAllowed",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
        452,
        L"Failed to create OneSettings infrastructure");
      (*(void (__fastcall **)(_QWORD *, _QWORD))(v104[0] + 48LL))(v104, 0);
    }
    v83 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, unsigned __int64 *))(v104[0] + 64LL))(v104, &v83) )
    {
      v103 = 0x10000;
      v105[1] = operator new[](0x20000u);
      v105[0] = &RAII::CAutoDeleteArray<unsigned short>::`vftable';
      v18 = (*(__int64 (__fastcall **)(_QWORD *))(v104[0] + 24LL))(v104);
      v19 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, unsigned int *))(*(_QWORD *)v18 + 16LL);
      v20 = (*(__int64 (__fastcall **)(_QWORD *))(v105[0] + 32LL))(v105);
      v21 = v19(v18, L"WinRECleanupCanDeleteList", v20, &v103);
      if ( v21 >= 0 )
      {
        LODWORD(v81) = 0;
        v22 = (*(__int64 (__fastcall **)(_QWORD *))(v105[0] + 32LL))(v105);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v86,
          v22);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
          &v86,
          &v80,
          v23,
          &v81);
        while ( *(int *)(v80 - 16) > 0 )
        {
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
            v98,
            v80);
          v25 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                             &v86,
                             &v83,
                             v24,
                             &v81);
          v26 = (_QWORD *)(v25 - 24);
          v27 = (int *)(v80 - 24);
          if ( v25 - 24 != v80 - 24 )
          {
            if ( v27[4] >= 0 && *v26 == *(_QWORD *)v27 )
            {
              v28 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v26);
              ATL::CStringData::Release((ATL::CStringData *)v27);
              v80 = v28 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v80, v25, *(unsigned int *)(v25 - 16));
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v83 - 24));
        }
        ATL::CStringData::Release((ATL::CStringData *)(v80 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v86 - 24));
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v21,
          "WinREAgent::WinREIsWinRECleanupAllowed",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
          465,
          L"Faled to get block list of WinRE partition cleanup");
      }
      v105[0] = &RAII::CAutoDeleteArray<unsigned short>::`vftable';
      RAII::CAutoDeleteArray<unsigned short const *>::Release(v105);
      v4 = v97;
    }
    if ( a2 )
    {
      PushButtonReset::Logging::Trace(0, L"Getting extra can delete list from caller");
      for ( j = 0; j < *(_QWORD *)(a2 + 8); ++j )
      {
        v31 = (__int64 *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                           a2,
                           j,
                           v29);
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
          v98,
          *v31);
      }
    }
    v104[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
    RAII::CAutoRelease<ISetupOneSettings *>::Release(v104);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v86);
  Volume = PushButtonReset::Path::GetVolume(a1, &v86);
  if ( Volume < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Volume,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      494,
      L"Failed to get volume for WinRE.wim at [%s]",
      *a1);
    goto LABEL_106;
  }
  ATL::operator+(&v106, &v86, L"\\");
  PushButtonReset::Logging::Trace(0, L"WinRE partition root: [%s]", v106);
  memset_0(Buffer, 0, 0x20Au);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      505,
      L"Failed to get host system Windows directory");
    v34 = GetLastError();
    Volume = v34;
    if ( v34 > 0 )
      Volume = (unsigned __int16)v34 | 0x80070000;
    goto LABEL_37;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v82);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&String1,
    (__int64)Buffer);
  Volume = PushButtonReset::Path::GetVolume(&String1, &v82);
  ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
  if ( Volume < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Volume,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      510,
      L"Failed to get volume for OS directory [%s]",
      Buffer);
LABEL_40:
    ATL::CStringData::Release((ATL::CStringData *)(v82 - 24));
LABEL_37:
    ATL::CStringData::Release((ATL::CStringData *)(v106 - 24));
    goto LABEL_106;
  }
  v77 = 0;
  Volume = PushButtonReset::Path::SameVolume(&v82, &v106, &v77);
  if ( Volume < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Volume,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      515,
      L"Failed to check whether WinRE partition is on same volume as host OS");
    goto LABEL_40;
  }
  if ( v77 )
  {
    PushButtonReset::Logging::Trace(
      2,
      L"WinRE partition and host OS are on same volume. Cannot cleanup WinRE partition");
    *v4 = 0;
    goto LABEL_105;
  }
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>(
    (unsigned int)v102,
    v35,
    v36,
    v37,
    LODWORD(FLOAT_2_25));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>(
    (unsigned int)v101,
    v38,
    v39,
    v40,
    v41);
  v42 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v83,
          &v86);
  VolumeRelPath = winreBuildCanDeleteMap(v42, v98, v102, v101);
  if ( VolumeRelPath < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)VolumeRelPath,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      530,
      L"Failed to parse can delete list");
    VolumeRelPath = 0;
  }
  v43 = 0;
  v103 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v80);
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::SetCount(
    &v89,
    0);
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
    &v89,
    v106);
  v45 = 0;
  v83 = 0;
  v46 = v80;
  if ( v90 )
  {
    while ( 1 )
    {
      v47 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                        &v89,
                        v45,
                        v44);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v85,
        v47);
      v93 = 0;
      v94 = 0;
      v95 = 0;
      v96 = 0;
      VolumeRelPath = PushButtonReset::Directory::Enum(&v85, &v93);
      if ( VolumeRelPath < 0 )
        break;
      v49 = 0;
      v104[0] = 0;
      if ( v94 )
      {
        while ( 1 )
        {
          v50 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                            &v93,
                            v49,
                            v48);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v84,
            v50);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v79);
          v51 = PushButtonReset::Path::Combine(&v85, &v84, &v79);
          if ( v51 < 0 )
          {
            v69 = v85;
            v70 = v84;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v51,
              "WinREAgent::WinREIsWinRECleanupAllowed",
              "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
              553,
              L"Failed to construct path to [%s] in [%s]",
              v84,
              v85);
            ATL::CStringData::Release((ATL::CStringData *)(v79 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v70 - 24));
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v93);
            ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v89);
            ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
            ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v101);
            ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v102);
            ATL::CStringData::Release((ATL::CStringData *)(v82 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v106 - 24));
            Volume = v51;
            goto LABEL_106;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
          VolumeRelPath = PushButtonReset::Path::GetVolumeRelPath(&v79, &String1);
          if ( VolumeRelPath < 0 )
          {
            v66 = v79;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)VolumeRelPath,
              "WinREAgent::WinREIsWinRECleanupAllowed",
              "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
              557,
              L"Failed to get volume relative path of [%s]",
              v79);
            ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
            ATL::CStringData::Release((ATL::CStringData *)(v66 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v84 - 24));
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v93);
            v67 = (ATL::CStringData *)(v85 - 24);
            goto LABEL_93;
          }
          v77 = 0;
          v87 = 0;
          v81 = 0;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v79);
          IsFile = PushButtonReset::Path::IsFile(&v79);
          v53 = String1;
          if ( IsFile )
            break;
          if ( !(unsigned __int8)PushButtonReset::Path::IsDirectory(&v79) )
          {
            LODWORD(v81) = 85;
            v55 = v79;
            goto LABEL_71;
          }
          if ( _wcsicmp(v53, L"\\System Volume Information") )
          {
            v54 = WinREAgent::WinREIsKnownWinREFolder(&v79, &v77);
            if ( v54 < 0 )
            {
              v65 = v79;
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v54,
                "WinREAgent::WinREIsWinRECleanupAllowed",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                592,
                L"Failed to check whether [%s] is a known WinRE folder",
                v79);
              goto LABEL_90;
            }
            VolumeRelPath = PushButtonReset::Directory::GetSize(&v79, &v81);
            v55 = v79;
            if ( VolumeRelPath >= 0 )
            {
              v87 = v81;
            }
            else
            {
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)VolumeRelPath,
                "WinREAgent::WinREIsWinRECleanupAllowed",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                599,
                L"Failed to get size of directory [%s]",
                v79);
              VolumeRelPath = 0;
              v87 = 0;
            }
            v78[0] = 0;
            v59 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::Lookup(
                    v101,
                    v55,
                    v78);
            v57 = v77 | v59;
            if ( !(v77 | v59) || !v78[0] )
            {
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
                &v89,
                v55);
              LODWORD(v81) = 68;
              goto LABEL_68;
            }
LABEL_83:
            ATL::CStringData::Release((ATL::CStringData *)(v53 - 12));
            ATL::CStringData::Release((ATL::CStringData *)(v55 - 24));
            v58 = (ATL::CStringData *)(v84 - 24);
            v43 = v103;
            goto LABEL_84;
          }
          ATL::CStringData::Release((ATL::CStringData *)(v53 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v79 - 24));
          v58 = (ATL::CStringData *)(v84 - 24);
LABEL_84:
          ATL::CStringData::Release(v58);
          v49 = v104[0] + 1LL;
          v104[0] = v49;
          if ( v49 >= v94 )
            goto LABEL_87;
        }
        v54 = WinREAgent::WinREIsKnownWinREFile(&v79, &v77, 0);
        if ( v54 < 0 )
        {
          v65 = v79;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v54,
            "WinREAgent::WinREIsWinRECleanupAllowed",
            "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
            568,
            L"Failed to check whether [%s] is a known WinRE file",
            v79);
LABEL_90:
          ATL::CStringData::Release((ATL::CStringData *)(v53 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v84 - 24));
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v93);
          ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v89);
          ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
          ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v101);
          ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v102);
          ATL::CStringData::Release((ATL::CStringData *)(v82 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v106 - 24));
          Volume = v54;
          goto LABEL_106;
        }
        VolumeRelPath = PushButtonReset::File::GetSize(&v79, &v81);
        v55 = v79;
        if ( VolumeRelPath >= 0 )
        {
          v87 = v81;
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)VolumeRelPath,
            "WinREAgent::WinREIsWinRECleanupAllowed",
            "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
            575,
            L"Failed to get size of file [%s]",
            v79);
          VolumeRelPath = 0;
          v87 = 0;
        }
        v56 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::Lookup(
                v102,
                v55,
                v78);
        v57 = v77 | v56;
        LODWORD(v81) = 70;
LABEL_68:
        if ( v57 )
          goto LABEL_83;
        v43 = v103;
LABEL_71:
        v103 = v43 + 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v105);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          v105,
          L"%s,%c,%llu",
          v53,
          (unsigned int)v81,
          v87);
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl);
        v61 = v105[0];
        if ( IsEnabled )
          PushButtonReset::Logging::Trace(0, L"Cannot delete content: [%s]", v105[0]);
        if ( *(_DWORD *)(v46 - 16) )
        {
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v80);
          ATL::CSimpleStringT<unsigned short,0>::Append(&v80, v61, *(unsigned int *)(v61 - 16));
        }
        else
        {
          v62 = (_QWORD *)(v61 - 24);
          v63 = v46 - 24;
          v87 = (ATL::CStringData *)(v46 - 24);
          if ( v61 - 24 == v46 - 24 )
          {
LABEL_81:
            if ( v103 >= 0x14 )
            {
              PushButtonReset::Logging::Trace(0, L"Unknown content count reached threshold, abort the enumeration");
              ATL::CStringData::Release((ATL::CStringData *)(v61 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v53 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v55 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v84 - 24));
              goto LABEL_87;
            }
            ATL::CStringData::Release((ATL::CStringData *)(v61 - 24));
            goto LABEL_83;
          }
          if ( *(int *)(v63 + 16) >= 0 && *v62 == *(_QWORD *)v63 )
          {
            v64 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v62);
            ATL::CStringData::Release(v87);
            v46 = v64 + 24;
            v80 = v46;
            goto LABEL_81;
          }
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v80, v61, *(unsigned int *)(v61 - 16));
        }
        v46 = v80;
        goto LABEL_81;
      }
LABEL_87:
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v93);
      ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
      v45 = v83 + 1;
      v83 = v45;
      if ( v45 >= v90 )
        goto LABEL_96;
      v43 = v103;
    }
    v71 = v85;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)VolumeRelPath,
      "WinREAgent::WinREIsWinRECleanupAllowed",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      546,
      L"Failed to enumerate contents of [%s]",
      v85);
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v93);
    v67 = (ATL::CStringData *)(v71 - 24);
LABEL_93:
    ATL::CStringData::Release(v67);
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v89);
    v68 = (ATL::CStringData *)(v46 - 24);
  }
  else
  {
LABEL_96:
    v72 = v100;
    v73 = (int *)(*v100 - 24LL);
    if ( (int *)(v46 - 24) != v73 )
    {
      if ( v73[4] >= 0 && *(_QWORD *)(v46 - 24) == *(_QWORD *)v73 )
      {
        v74 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v46 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v73);
        *v72 = v74 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v100, v46, *(unsigned int *)(v46 - 16));
      }
    }
    v75 = v103;
    *v97 = v103 == 0;
    v76 = L"Allow";
    if ( v75 )
      v76 = L"Not allow";
    PushButtonReset::Logging::Trace(0, L"%s cleanup WinRE partition", v76);
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v89);
    v68 = (ATL::CStringData *)(v46 - 24);
  }
  ATL::CStringData::Release(v68);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v101);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v102);
LABEL_105:
  ATL::CStringData::Release((ATL::CStringData *)(v82 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v106 - 24));
  Volume = VolumeRelPath;
LABEL_106:
  ATL::CStringData::Release((ATL::CStringData *)(v86 - 24));
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v98);
  return (unsigned int)Volume;
}

```

## disassembly

```asm
0x1800346cc  push    rbp
0x1800346ce  push    rbx
0x1800346cf  push    rsi
0x1800346d0  push    rdi
0x1800346d1  push    r12
0x1800346d3  push    r13
0x1800346d5  push    r14
0x1800346d7  push    r15
0x1800346d9  lea     rbp, [rsp-308h]
0x1800346e1  sub     rsp, 408h
0x1800346e8  mov     rax, cs:__security_cookie
0x1800346ef  xor     rax, rsp
0x1800346f2  mov     [rbp+340h+var_50], rax
0x1800346f9  mov     rax, r9
0x1800346fc  mov     [rbp+340h+var_340], rax
0x180034700  mov     rdi, r8
0x180034703  mov     [rbp+340h+var_368], r8
0x180034707  mov     rsi, rdx
0x18003470a  mov     r14, rcx
0x18003470d  xor     r15d, r15d
0x180034710  test    r8, r8
0x180034713  jnz     short loc_180034750
0x180034715  lea     rax, aResCannotBeNul; "res cannot be null"
0x18003471c  mov     [rsp+440h+var_418], rax
0x180034721  mov     dword ptr [rsp+440h+var_420], 1ACh
0x180034729  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180034730  lea     r8, aWinreagentWinr_18; "WinREAgent::WinREIsWinRECleanupAllowed"
0x180034737  mov     edx, 80070057h
0x18003473c  mov     ecx, 2
0x180034741  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034746  mov     eax, 80070057h
0x18003474b  jmp     loc_180035500
0x180034750  test    rax, rax
0x180034753  jnz     short loc_18003476B
0x180034755  lea     rax, aUnknowncontent; "unknownContentReport cannot be null"
0x18003475c  mov     [rsp+440h+var_418], rax
0x180034761  mov     dword ptr [rsp+440h+var_420], 1ADh
0x180034769  jmp     short loc_180034729
0x18003476b  mov     [rbp+340h+var_360], r15
0x18003476f  mov     [rbp+340h+var_358], r15
0x180034773  mov     [rbp+340h+var_350], r15
0x180034777  mov     [rbp+340h+var_348], r15d
0x18003477b  xor     edx, edx
0x18003477d  lea     rcx, [rbp+340h+var_360]
0x180034781  call    ?SetCount@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::SetCount(unsigned __int64,int)
0x180034786  nop
0x180034787  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl(void)'::`2'::impl
0x18003478e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled(void)
0x180034793  lea     r12, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003479a  lea     r13, aWinreagentWinr_18; "WinREAgent::WinREIsWinRECleanupAllowed"
0x1800347a1  test    al, al
0x1800347a3  jz      short loc_18003480A
0x1800347a5  test    rsi, rsi
0x1800347a8  jz      loc_180034AA1
0x1800347ae  lea     rdx, aGettingCanDele; "Getting can delete list"
0x1800347b5  xor     ecx, ecx
0x1800347b7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800347bc  mov     rbx, r15
0x1800347bf  cmp     [rsi+8], r15
0x1800347c3  jbe     loc_180034AA1
0x1800347c9  mov     rdx, rbx
0x1800347cc  mov     rcx, rsi
0x1800347cf  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800347d4  mov     rdx, [rax]
0x1800347d7  lea     rcx, [rbp+340h+var_360]
0x1800347db  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x1800347e0  mov     rdx, rbx
0x1800347e3  mov     rcx, rsi
0x1800347e6  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800347eb  mov     r8, [rax]
0x1800347ee  lea     rdx, aAddSToCanDelet; "Add [%s] to can delete list"
0x1800347f5  xor     ecx, ecx
0x1800347f7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800347fc  inc     rbx
0x1800347ff  cmp     rbx, [rsi+8]
0x180034803  jb      short loc_1800347C9
0x180034805  jmp     loc_180034AA1
0x18003480a  mov     [rbp+340h+var_280], r15
0x180034811  lea     rax, ??_7?$CAutoRelease@PEAUISetupOneSettings@@@RAII@@6B@; const RAII::CAutoRelease<ISetupOneSettings *>::`vftable'
0x180034818  mov     [rbp+340h+var_288], rax
0x18003481f  lea     rcx, [rbp+340h+var_288]
0x180034826  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18003482b  mov     r8, rax; struct ISetupOneSettings **
0x18003482e  call    ?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z; CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)
0x180034833  test    eax, eax
0x180034835  jns     short loc_180034876
0x180034837  lea     rcx, aFailedToCreate_34; "Failed to create OneSettings infrastruc"...
0x18003483e  mov     [rsp+440h+var_418], rcx
0x180034843  mov     dword ptr [rsp+440h+var_420], 1C4h
0x18003484b  mov     r9, r12
0x18003484e  mov     r8, r13
0x180034851  mov     edx, eax
0x180034853  mov     ecx, 1
0x180034858  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003485d  mov     rax, [rbp+340h+var_288]
0x180034864  xor     edx, edx
0x180034866  lea     rcx, [rbp+340h+var_288]
0x18003486d  mov     rax, [rax+30h]
0x180034871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034876  mov     [rsp+440h+var_3D8], r15
0x18003487b  mov     rax, [rbp+340h+var_288]
0x180034882  lea     rdx, [rsp+440h+var_3D8]
0x180034887  lea     rcx, [rbp+340h+var_288]
0x18003488e  mov     rax, [rax+40h]
0x180034892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034897  test    al, al
0x180034899  jz      loc_180034A4A
0x18003489f  mov     [rbp+340h+var_290], 10000h
0x1800348a9  mov     ecx, 20000h; unsigned __int64
0x1800348ae  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800348b3  mov     [rbp+340h+var_270], rax
0x1800348ba  lea     rax, ??_7?$CAutoDeleteArray@G@RAII@@6B@; const RAII::CAutoDeleteArray<ushort>::`vftable'
0x1800348c1  mov     [rbp+340h+var_278], rax
0x1800348c8  mov     rax, [rbp+340h+var_288]
0x1800348cf  lea     rcx, [rbp+340h+var_288]
0x1800348d6  mov     rax, [rax+18h]
0x1800348da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348df  mov     rdi, rax
0x1800348e2  mov     rcx, [rax]
0x1800348e5  mov     rbx, [rcx+10h]
0x1800348e9  mov     rcx, [rbp+340h+var_278]
0x1800348f0  mov     rax, [rcx+20h]
0x1800348f4  lea     rcx, [rbp+340h+var_278]
0x1800348fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034900  lea     r9, [rbp+340h+var_290]
0x180034907  mov     r8, rax
0x18003490a  lea     rdx, aWinrecleanupca; "WinRECleanupCanDeleteList"
0x180034911  mov     rcx, rdi
0x180034914  mov     rax, rbx
0x180034917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003491c  test    eax, eax
0x18003491e  jns     short loc_18003494B
0x180034920  lea     rcx, aFaledToGetBloc; "Faled to get block list of WinRE partit"...
0x180034927  mov     [rsp+440h+var_418], rcx
0x18003492c  mov     dword ptr [rsp+440h+var_420], 1D1h
0x180034934  mov     r9, r12
0x180034937  mov     r8, r13
0x18003493a  mov     edx, eax
0x18003493c  mov     ecx, 1
0x180034941  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034946  jmp     loc_180034A2C
0x18003494b  mov     dword ptr [rsp+440h+var_3E8], r15d
0x180034950  mov     rax, [rbp+340h+var_278]
0x180034957  lea     rcx, [rbp+340h+var_278]
0x18003495e  mov     rax, [rax+20h]
0x180034962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034967  mov     rdx, rax
0x18003496a  lea     rcx, [rbp+340h+var_3C0]
0x18003496e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180034973  nop
0x180034974  lea     r9, [rsp+440h+var_3E8]
0x180034979  lea     rdx, [rsp+440h+var_3F0]
0x18003497e  lea     rcx, [rbp+340h+var_3C0]
0x180034982  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180034987  nop
0x180034988  jmp     short loc_180034A05
0x18003498a  mov     rdx, rcx
0x18003498d  lea     rcx, [rbp+340h+var_360]
0x180034991  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x180034996  lea     r9, [rsp+440h+var_3E8]
0x18003499b  lea     rdx, [rsp+440h+var_3D8]
0x1800349a0  lea     rcx, [rbp+340h+var_3C0]
0x1800349a4  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x1800349a9  nop
0x1800349aa  mov     rdx, [rax]
0x1800349ad  lea     rcx, [rdx-18h]
0x1800349b1  mov     rdi, [rsp+440h+var_3F0]
0x1800349b6  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800349ba  cmp     rcx, rdi
0x1800349bd  jz      short loc_1800349F7
0x1800349bf  cmp     [rdi+10h], r15d
0x1800349c3  jl      short loc_1800349E8
0x1800349c5  mov     rax, [rdi]
0x1800349c8  cmp     [rcx], rax
0x1800349cb  jnz     short loc_1800349E8
0x1800349cd  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800349d2  mov     rbx, rax
0x1800349d5  mov     rcx, rdi; this
0x1800349d8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800349dd  lea     rax, [rbx+18h]
0x1800349e1  mov     [rsp+440h+var_3F0], rax
0x1800349e6  jmp     short loc_1800349F7
0x1800349e8  mov     r8d, [rdx-10h]
0x1800349ec  lea     rcx, [rsp+440h+var_3F0]
0x1800349f1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800349f6  nop
0x1800349f7  mov     rcx, [rsp+440h+var_3D8]
0x1800349fc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034a00  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034a05  mov     rcx, [rsp+440h+var_3F0]
0x180034a0a  cmp     [rcx-10h], r15d
0x180034a0e  jg      loc_18003498A
0x180034a14  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034a18  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034a1d  nop
0x180034a1e  mov     rcx, [rbp+340h+var_3C0]
0x180034a22  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034a26  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034a2b  nop
0x180034a2c  lea     rax, ??_7?$CAutoDeleteArray@G@RAII@@6B@; const RAII::CAutoDeleteArray<ushort>::`vftable'
0x180034a33  mov     [rbp+340h+var_278], rax
0x180034a3a  lea     rcx, [rbp+340h+var_278]
0x180034a41  call    ?Release@?$CAutoDeleteArray@PEBG@RAII@@UEAAXXZ; RAII::CAutoDeleteArray<ushort const *>::Release(void)
0x180034a46  mov     rdi, [rbp+340h+var_368]
0x180034a4a  test    rsi, rsi
0x180034a4d  jz      short loc_180034A86
0x180034a4f  lea     rdx, aGettingExtraCa; "Getting extra can delete list from call"...
0x180034a56  xor     ecx, ecx
0x180034a58  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180034a5d  mov     rbx, r15
0x180034a60  cmp     [rsi+8], r15
0x180034a64  jbe     short loc_180034A86
0x180034a66  mov     rdx, rbx
0x180034a69  mov     rcx, rsi
0x180034a6c  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180034a71  mov     rdx, [rax]
0x180034a74  lea     rcx, [rbp+340h+var_360]
0x180034a78  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x180034a7d  inc     rbx
0x180034a80  cmp     rbx, [rsi+8]
0x180034a84  jb      short loc_180034A66
0x180034a86  lea     rax, ??_7?$CAutoRelease@PEAUISetupOneSettings@@@RAII@@6B@; const RAII::CAutoRelease<ISetupOneSettings *>::`vftable'
0x180034a8d  mov     [rbp+340h+var_288], rax
0x180034a94  lea     rcx, [rbp+340h+var_288]
0x180034a9b  call    ?Release@?$CAutoRelease@PEAUISetupOneSettings@@@RAII@@UEAAXXZ; RAII::CAutoRelease<ISetupOneSettings *>::Release(void)
0x180034aa0  nop
0x180034aa1  lea     rcx, [rbp+340h+var_3C0]
0x180034aa5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180034aaa  nop
0x180034aab  lea     rdx, [rbp+340h+var_3C0]
0x180034aaf  mov     rcx, r14
0x180034ab2  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180034ab7  mov     ebx, eax
0x180034ab9  test    eax, eax
0x180034abb  jns     short loc_180034AF0
0x180034abd  mov     rcx, [r14]
0x180034ac0  mov     [rsp+440h+var_410], rcx
0x180034ac5  lea     rax, aFailedToGetVol_0; "Failed to get volume for WinRE.wim at ["...
0x180034acc  mov     [rsp+440h+var_418], rax
0x180034ad1  mov     dword ptr [rsp+440h+var_420], 1EEh
0x180034ad9  mov     r9, r12
0x180034adc  mov     r8, r13
0x180034adf  mov     edx, ebx
0x180034ae1  mov     ecx, 2
0x180034ae6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034aeb  jmp     loc_1800354E7
0x180034af0  lea     r8, SubBlock; "\\"
0x180034af7  lea     rdx, [rbp+340h+var_3C0]
0x180034afb  lea     rcx, [rbp+340h+var_268]
0x180034b02  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180034b07  nop
0x180034b08  mov     r8, [rbp+340h+var_268]
0x180034b0f  lea     rdx, aWinrePartition_6; "WinRE partition root: [%s]"
0x180034b16  xor     ecx, ecx
0x180034b18  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180034b1d  xor     edx, edx; Val
0x180034b1f  mov     r8d, 20Ah; Size
0x180034b25  lea     rcx, [rbp+340h+Buffer]; void *
0x180034b2c  call    memset_0
0x180034b31  mov     edx, 104h; uSize
0x180034b36  lea     rcx, [rbp+340h+Buffer]; lpBuffer
0x180034b3d  call    cs:__imp_GetWindowsDirectoryW
0x180034b43  test    eax, eax
0x180034b45  jnz     short loc_180034BA7
0x180034b47  call    cs:__imp_GetLastError
0x180034b4d  mov     edi, 80070000h
0x180034b52  test    eax, eax
0x180034b54  jle     short loc_180034B5B
0x180034b56  movzx   eax, ax
0x180034b59  or      eax, edi
0x180034b5b  lea     rcx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180034b62  mov     [rsp+440h+var_418], rcx
0x180034b67  mov     dword ptr [rsp+440h+var_420], 1F9h
0x180034b6f  mov     r9, r12
0x180034b72  mov     r8, r13
0x180034b75  mov     edx, eax
0x180034b77  mov     ecx, 2
0x180034b7c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034b81  call    cs:__imp_GetLastError
0x180034b87  mov     ebx, eax
0x180034b89  test    eax, eax
0x180034b8b  jle     short loc_180034B92
0x180034b8d  movzx   ebx, ax
0x180034b90  or      ebx, edi
0x180034b92  mov     rcx, [rbp+340h+var_268]
0x180034b99  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034b9d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034ba2  jmp     loc_1800354E7
0x180034ba7  lea     rcx, [rsp+440h+var_3E0]
0x180034bac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180034bb1  nop
0x180034bb2  lea     rdx, [rbp+340h+Buffer]
0x180034bb9  lea     rcx, [rbp+340h+String1]
0x180034bbd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180034bc2  nop
0x180034bc3  lea     rdx, [rsp+440h+var_3E0]
0x180034bc8  lea     rcx, [rbp+340h+String1]
0x180034bcc  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180034bd1  mov     ebx, eax
0x180034bd3  mov     rcx, [rbp+340h+String1]
  ... truncated ...
```
