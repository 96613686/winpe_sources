# MountOverlayImage

- ea: `0x18007eb20`
- end: `0x18007fad0`
- name: `MountOverlayImage`
- size: `4016`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *)`
- caller_count: `0`
- callee_count: `38`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000cc90`
- `0x180018df0`
- `0x18001f1d8`
- `0x18001f840`
- `0x180020dc0`
- `0x180021878`
- `0x18002d2b0`
- `0x180030ba8`
- `0x180042bac`
- `0x180047d5c`
- `0x18006c244`
- `0x1800735e0`
- `0x18007c898`
- `0x18007c930`
- `0x18007cb38`
- `0x18007cbb8`
- `0x18007cde4`
- `0x18007d5a8`
- `0x18007d6f4`
- `0x18007d794`
- `0x18007d7cc`
- `0x18007da70`
- `0x18007df88`
- `0x18007dfb0`
- `0x18007dff4`
- `0x18007e020`
- `0x18007e064`
- `0x18007e1a8`
- `0x18007e288`
- `0x18007e328`
- `0x18007e3f0`
- `0x18007e5c0`
- `0x18007eb20`
- `0x180080f10`
- `0x180080f3c`
- `0x180081914`
- `0x180096860`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007ef88`
- `KERNEL32!GetLastError` at `0x18007efe9`
- `KERNEL32!GetLastError` at `0x18007f91c`
- `KERNEL32!GetLastError` at `0x18007f933`
- `KERNEL32!GetLastError` at `0x18007f985`
- `KERNEL32!GetLastError` at `0x18007f99c`
- `KERNEL32!GetLastError` at `0x18007f9d7`
- `KERNEL32!GetLastError` at `0x18007faaa`
- `KERNEL32!GetLastError` at `0x18007ef88`
- `KERNEL32!GetLastError` at `0x18007efe9`
- `KERNEL32!GetLastError` at `0x18007f91c`
- `KERNEL32!GetLastError` at `0x18007f933`
- `KERNEL32!GetLastError` at `0x18007f985`
- `KERNEL32!GetLastError` at `0x18007f99c`
- `KERNEL32!GetLastError` at `0x18007f9d7`
- `KERNEL32!GetLastError` at `0x18007faaa`
- `KERNEL32!DeleteFileW` at `0x18007ef74`
- `KERNEL32!DeleteFileW` at `0x18007ef74`
- `KERNEL32!CreateFileW` at `0x18007f077`
- `KERNEL32!CreateFileW` at `0x18007f077`
- `KERNEL32!WriteFile` at `0x18007f0b8`
- `KERNEL32!WriteFile` at `0x18007f125`
- `KERNEL32!WriteFile` at `0x18007f0b8`
- `KERNEL32!WriteFile` at `0x18007f125`
- `ntdll!RtlRaiseStatus` at `0x18007effe`
- `ntdll!RtlRaiseStatus` at `0x18007fac3`
- `ntdll!RtlRaiseStatus` at `0x18007effe`
- `ntdll!RtlRaiseStatus` at `0x18007fac3`
- `RPCRT4!UuidCreate` at `0x18007ed57`
- `RPCRT4!UuidCreate` at `0x18007ed7a`
- `RPCRT4!UuidCreate` at `0x18007ed57`
- `RPCRT4!UuidCreate` at `0x18007ed7a`
- `CIMFS!CimMergeMountImage` at `0x18007f73a`
- `CIMFS!CimMergeMountImage` at `0x18007f73a`

## string_xrefs

- `0x18007eb67`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007eba8`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ec31`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ec8d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ed05`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007edaf`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ee74`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007eed7`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007efa5`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f0d9`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f19a`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f29a`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f551`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f5df`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f6d3`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f74c`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f7c5`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f881`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f94f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f9b0`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f9f0`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007edc8`: `ImageRootPath.assign(ImageRoot)`
- `0x18007ec21`: `CreateFileSystemUnion`
- `0x18007eb81`: `MountOverlayImage`
- `0x18007ebc2`: `MountOverlayImage`
- `0x18007ec48`: `MountOverlayImage`
- `0x18007ecad`: `MountOverlayImage`
- `0x18007ed25`: `MountOverlayImage`
- `0x18007edcf`: `MountOverlayImage`
- `0x18007ee94`: `MountOverlayImage`
- `0x18007eef7`: `MountOverlayImage`
- `0x18007efb0`: `MountOverlayImage`
- `0x18007f0ec`: `MountOverlayImage`
- `0x18007f1b4`: `MountOverlayImage`
- `0x18007f2ad`: `MountOverlayImage`
- `0x18007f560`: `MountOverlayImage`
- `0x18007f5f2`: `MountOverlayImage`
- `0x18007f6ed`: `MountOverlayImage`
- `0x18007f75f`: `MountOverlayImage`
- `0x18007f7df`: `MountOverlayImage`
- `0x18007f894`: `MountOverlayImage`
- `0x18007f95a`: `MountOverlayImage`
- `0x18007f9c3`: `MountOverlayImage`
- `0x18007fa03`: `MountOverlayImage`
- `0x18007eef0`: `ImageRootPath.insert(0, c_Long_Path_Prefix)`
- `0x18007ee8d`: `CimRootPath.assign(CimRoot)`
- `0x18007efbb`: `EnsureBOOL(::DeleteFileW(GuidFilePath.c_str()))`
- `0x18007f965`: `EnsureBOOL(::WriteFile( GuidFile, reinterpret_cast<PVOID>(&UnionGuid), BytesToWrite, &BytesWritten, nullptr))`
- `0x18007f9ce`: `EnsureBOOL(::WriteFile( GuidFile, reinterpret_cast<PVOID>(&CimGuid), BytesToWrite, &BytesWritten, nullptr))`
- `0x18007f1ad`: `CimVolume.resize(VolumePathLength)`
- `0x18007f293`: `Configuration.get()->OverlayType == OverlayType::UnionFS`
- `0x18007f6e6`: `Cim.RelativePath && *Cim.RelativePath`
- `0x18007f2d9`: `Configuration.get()->LoadType == OverlayLoadType::OsDeviceLoad`
- `0x18007f540`: `FullCimPaths.emplace_back()`
- `0x18007f6c7`: `CimRelativePath.assign(Cim.RelativePath)`
- `0x18007f630`: `SplitCimPaths.emplace_back()`
- `0x18007f7d8`: `NewImageRootPath.resize(NewLength)`
- `0x18007f76a`: `CimMergeMountImage( static_cast<UINT32>(CimImages.size()), CimImages.data(), MountFlags, &CimGuid)`
- `0x18007f89f`: `pfnCreateFileSystemUnion( &UnionGuid, LayerRootPaths, (sizeof(*RtlpNumberOf(LayerRootPaths))), UFS_CONFIG_OPTION_ALLOW_NESTED_UNION | UFS_CONFIG_OPTION_SELF_CONTAINED_UNION | UFS_CONFIG_OPTION_DELETE_PERSISTENCE_FILE_IF_CORRUPT, nullptr, nullptr)`

## pseudocode

```c
__int64 __fastcall MountOverlayImage(wchar_t *a1, wchar_t *a2)
{
  int MountGuidsFilePath; // ebx
  HINSTANCE *InitPointer; // rax
  const char **v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  int v10; // eax
  RPC_STATUS v11; // eax
  __m128i *v12; // rdx
  _WORD *v13; // rcx
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  signed int LastError; // eax
  HANDLE v17; // rax
  HANDLE v18; // rbx
  int v19; // eax
  const char *v20; // rax
  __int64 v21; // r13
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // r15
  __int64 v25; // r14
  _QWORD *v26; // r12
  _WORD *v27; // rdx
  _WORD *v28; // rcx
  int v29; // edi
  __int64 v30; // rdi
  __int64 v31; // rsi
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rax
  const char *v35; // rax
  __int64 v36; // r8
  wchar_t **v37; // rcx
  const char *v38; // rax
  int v39; // eax
  bool v40; // cf
  int v41; // eax
  const char *v42; // rcx
  size_t v43; // rbx
  signed int v44; // eax
  const char **v45; // rdx
  const char *v46; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  char v50[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hFile; // [rsp+80h] [rbp-80h] BYREF
  const char *v53; // [rsp+88h] [rbp-78h] BYREF
  const char *v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+98h] [rbp-68h]
  const char *v56; // [rsp+A0h] [rbp-60h]
  __int64 (*v57)(void); // [rsp+A8h] [rbp-58h] BYREF
  const char *v58; // [rsp+B0h] [rbp-50h] BYREF
  const char *v59; // [rsp+B8h] [rbp-48h]
  __int64 v60; // [rsp+C0h] [rbp-40h]
  const char *v61; // [rsp+C8h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp-30h] BYREF
  int v63; // [rsp+E8h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+ECh] [rbp-14h] BYREF
  _WORD *v65; // [rsp+F0h] [rbp-10h] BYREF
  _WORD *v66; // [rsp+F8h] [rbp-8h]
  _WORD v67[8]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v68; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v69; // [rsp+118h] [rbp+18h]
  __int64 v70; // [rsp+120h] [rbp+20h] BYREF
  const char *v71; // [rsp+128h] [rbp+28h]
  LPCWSTR lpFileName[2]; // [rsp+130h] [rbp+30h] BYREF
  _WORD v73[8]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v74[2]; // [rsp+150h] [rbp+50h] BYREF
  _WORD v75[8]; // [rsp+160h] [rbp+60h] BYREF
  UUID Uuid; // [rsp+170h] [rbp+70h] BYREF
  __m128i si128; // [rsp+180h] [rbp+80h] BYREF
  __int64 v78; // [rsp+190h] [rbp+90h]
  const char *v79; // [rsp+198h] [rbp+98h]
  __m128i v80; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v81; // [rsp+1B0h] [rbp+B0h]
  const char *v82; // [rsp+1B8h] [rbp+B8h]
  wchar_t *v83[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _WORD v84[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v85; // [rsp+1E0h] [rbp+E0h] BYREF
  __m128i v86; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v87; // [rsp+1F8h] [rbp+F8h]
  const char *v88; // [rsp+200h] [rbp+100h]
  _QWORD v89[2]; // [rsp+208h] [rbp+108h] BYREF
  const char *v90; // [rsp+218h] [rbp+118h] BYREF
  const char *v91; // [rsp+220h] [rbp+120h]
  _QWORD v92[2]; // [rsp+228h] [rbp+128h] BYREF
  const char *v93; // [rsp+238h] [rbp+138h] BYREF
  const char *v94; // [rsp+240h] [rbp+140h]
  _QWORD v95[2]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v96; // [rsp+258h] [rbp+158h] BYREF
  char v97; // [rsp+260h] [rbp+160h]
  UUID Buffer; // [rsp+268h] [rbp+168h] BYREF
  _QWORD v99[2]; // [rsp+278h] [rbp+178h] BYREF

  v63 = 0;
  Windows::WCP::Implementation::Rtl::InitializeWdscore((Windows::WCP::Implementation::Rtl *)a1);
  if ( !a1 )
  {
    v70 = 507;
    v68 = (wchar_t *)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v71 = "Not-null check failed: ImageRoot";
    v69 = (__int64 *)"MountOverlayImage";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v63,
             &v68);
  }
  if ( !*a1 )
  {
    v70 = 508;
    v68 = (wchar_t *)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v71 = "*ImageRoot";
    v69 = (__int64 *)"MountOverlayImage";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v63,
             &v68);
  }
  v96 = 0;
  v97 = 0;
  MountGuidsFilePath = RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition *)&v96);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_131;
  v51 = 0;
  v57 = 0;
  InitPointer = (HINSTANCE *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v51);
  if ( !IsOverlayAPISupported("CreateFileSystemUnion", InitPointer, &v57) )
  {
    v70 = 521;
    v68 = (wchar_t *)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v7 = (const char **)&v68;
    v71 = 0;
    v69 = (__int64 *)"MountOverlayImage";
    v8 = 3221225659LL;
LABEL_8:
    v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v63,
           v7,
           v8);
LABEL_9:
    MountGuidsFilePath = v9;
LABEL_130:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v51);
    goto LABEL_131;
  }
  NumberOfBytesWritten = 0;
  MountGuidsFilePath = IsOverlayImage(a1, &NumberOfBytesWritten);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_130;
  if ( !NumberOfBytesWritten )
  {
    v95[0] = 528;
    v93 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v7 = &v93;
    v95[1] = 0;
    v94 = "MountOverlayImage";
    v8 = 3221225485LL;
    goto LABEL_8;
  }
  v85 = 0;
  MountGuidsFilePath = IsOverlayImageMounted(a1, &v85);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_130;
  if ( v85 )
  {
    v10 = ConvertHResultToNtStatus(2147942583LL);
    if ( v10 < 0 )
    {
      v92[0] = 537;
      v90 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v7 = &v90;
      v92[1] = 0;
      v91 = "MountOverlayImage";
      v8 = (unsigned int)v10;
      goto LABEL_8;
    }
LABEL_42:
    RtlRaiseStatus(-1073741595);
  }
  Uuid = 0;
  Buffer = 0;
  v11 = UuidCreate(&Uuid);
  if ( v11 < 0 || (v11 = UuidCreate(&Buffer), v11 < 0) )
  {
    v9 = ConvertHResultToNtStatus((unsigned int)v11);
    goto LABEL_9;
  }
  v67[0] = 0;
  v65 = v67;
  v66 = v67;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v65, a1) )
  {
    v87 = 547;
    v86.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v88 = "ImageRootPath.assign(ImageRoot)";
    v86.m128i_i64[1] = (__int64)"MountOverlayImage";
    v12 = &v86;
LABEL_22:
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v63,
                           v12,
                           3221225495LL);
LABEL_129:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v65);
    goto LABEL_130;
  }
  v13 = v65;
  if ( (unsigned __int64)(v66 - v65) >= 4 )
  {
    v14 = 4;
    v15 = L"\\\\?\\";
    while ( *v15 == *v13 )
    {
      ++v15;
      ++v13;
      if ( !--v14 )
        goto LABEL_27;
    }
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(&v65) )
  {
    v81 = 552;
    v80.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v82 = "ImageRootPath.insert(0, c_Long_Path_Prefix)";
    v80.m128i_i64[1] = (__int64)"MountOverlayImage";
    v12 = &v80;
    goto LABEL_22;
  }
LABEL_27:
  v75[0] = 0;
  v74[0] = v75;
  v74[1] = v75;
  if ( a2
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v74, a2) )
  {
    v78 = 558;
    si128.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v79 = "CimRootPath.assign(CimRoot)";
    si128.m128i_i64[1] = (__int64)"MountOverlayImage";
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v63,
                           &si128,
                           3221225495LL);
LABEL_128:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v74);
    goto LABEL_129;
  }
  v73[0] = 0;
  lpFileName[0] = v73;
  lpFileName[1] = v73;
  MountGuidsFilePath = GetMountGuidsFilePath(&v65, v74, lpFileName);
  if ( MountGuidsFilePath < 0 || (v50[0] = 0, MountGuidsFilePath = FileExists(lpFileName, v50), MountGuidsFilePath < 0) )
  {
LABEL_127:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpFileName);
    goto LABEL_128;
  }
  if ( v50[0] && !DeleteFileW(lpFileName[0]) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_42;
    }
    else
    {
      LastError = 14077;
    }
    v55 = 568;
    v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v54 = "MountOverlayImage";
    v56 = "EnsureBOOL(::DeleteFileW(GuidFilePath.c_str()))";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
                           &v63,
                           &v53,
                           (unsigned int)LastError);
    goto LABEL_127;
  }
  v89[0] = 0;
  v89[1] = 0;
  MountGuidsFilePath = GetFileSystemDefaultSecurity(16, v89);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_126;
  SecurityAttributes.lpSecurityDescriptor = (LPVOID)v89[0];
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  hFile = 0;
  v17 = CreateFileW(lpFileName[0], 0xC0000000, 1u, &SecurityAttributes, 1u, 0x2000006u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hFile,
    v17);
  v18 = hFile;
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( GetLastError() )
    {
      v44 = GetLastError();
      if ( !v44 )
        goto LABEL_133;
    }
    else
    {
      v44 = 14077;
    }
    v60 = 592;
    v58 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v59 = "MountOverlayImage";
    v46 = "GuidFile.IsValid()";
LABEL_121:
    v61 = v46;
    if ( v44 > 0 )
      v44 = (unsigned __int16)v44 | 0x80070000;
    v45 = &v58;
    goto LABEL_124;
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(hFile, &Uuid, 0x10u, &NumberOfBytesWritten, 0) )
  {
    if ( GetLastError() )
    {
      v44 = GetLastError();
      if ( !v44 )
        goto LABEL_133;
    }
    else
    {
      v44 = 14077;
    }
    v60 = 602;
    v58 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v59 = "MountOverlayImage";
    v46 = "EnsureBOOL(::WriteFile( GuidFile, reinterpret_cast<PVOID>(&CimGuid), BytesToWrite, &BytesWritten, nullptr))";
    goto LABEL_121;
  }
  if ( NumberOfBytesWritten != 16 )
  {
    v55 = 605;
LABEL_48:
    v56 = 0;
    v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v54 = "MountOverlayImage";
    v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v63,
            &v53,
            3221225705LL);
LABEL_125:
    MountGuidsFilePath = v19;
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
LABEL_126:
    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(v89);
    goto LABEL_127;
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v18, &Buffer, 0x10u, &NumberOfBytesWritten, 0) )
  {
    if ( !GetLastError() )
    {
      v44 = 14077;
LABEL_111:
      v55 = 616;
      v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v54 = "MountOverlayImage";
      v56 = "EnsureBOOL(::WriteFile( GuidFile, reinterpret_cast<PVOID>(&UnionGuid), BytesToWrite, &BytesWritten, nullptr))";
      if ( v44 > 0 )
        v44 = (unsigned __int16)v44 | 0x80070000;
      v45 = &v53;
LABEL_124:
      v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
              &v63,
              v45,
              (unsigned int)v44);
      goto LABEL_125;
    }
    v44 = GetLastError();
    if ( v44 )
      goto LABEL_111;
LABEL_133:
    RtlRaiseStatus(-1073741595);
  }
  if ( NumberOfBytesWritten != 16 )
  {
    v55 = 619;
    goto LABEL_48;
  }
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(v89);
  v84[0] = 0;
  v83[0] = v84;
  v83[1] = v84;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(v83, 50) )
  {
    v55 = 625;
    v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v56 = "CimVolume.resize(VolumePathLength)";
    v54 = "MountOverlayImage";
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v63,
                           &v53,
                           3221225495LL);
LABEL_54:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v83);
    goto LABEL_127;
  }
  LODWORD(hTemplateFile) = Uuid.Data4[0];
  dwFlagsAndAttributes[0] = Uuid.Data3;
  dwCreationDisposition[0] = Uuid.Data2;
  swprintf_s(
    v83[0],
    0x32u,
    L"\\\\?\\Volume{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\\",
    Uuid.Data1,
    *(_QWORD *)dwCreationDisposition,
    *(_QWORD *)dwFlagsAndAttributes,
    hTemplateFile,
    Uuid.Data4[1],
    Uuid.Data4[2],
    Uuid.Data4[3],
    Uuid.Data4[4],
    Uuid.Data4[5],
    Uuid.Data4[6],
    Uuid.Data4[7]);
  hFile = 0;
  MountGuidsFilePath = GetOverlayConfiguration(a1, a2, (struct OVERLAY_CONFIGURATION **)&hFile);
  if ( MountGuidsFilePath < 0 )
  {
LABEL_56:
    AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr((AutoOverlayConfigurationPtr *)&hFile);
    goto LABEL_54;
  }
  if ( *(_DWORD *)hFile != 1 )
  {
    v55 = 650;
    v20 = "Configuration.get()->OverlayType == OverlayType::UnionFS";
LABEL_59:
    v56 = v20;
    v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v54 = "MountOverlayImage";
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v63,
                           &v53,
                           3221225659LL);
    goto LABEL_56;
  }
  if ( *((_DWORD *)hFile + 1) != 1 )
  {
    v55 = 651;
    v20 = "Configuration.get()->LoadType == OverlayLoadType::OsDeviceLoad";
    goto LABEL_59;
  }
  v21 = -1;
  v22 = *((unsigned int *)hFile + 6);
  v23 = *((_QWORD *)hFile + 4);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v80 = si128;
  v24 = si128.m128i_i64[1];
  v50[0] = 0;
  v25 = v23 + 56 * v22;
  v26 = (_QWORD *)si128.m128i_i64[1];
  v78 = -1;
  v81 = -1;
  v86 = si128;
  v87 = -1;
  while ( 1 )
  {
    if ( v23 == v25 )
    {
      v40 = v50[0] != 0;
      v50[0] = -v50[0];
      v41 = CimMergeMountImage(
              (unsigned int)((v24 - si128.m128i_i64[0]) >> 4),
              si128.m128i_i64[0],
              v40 ? 64 : 96,
              &Uuid);
      if ( v41 >= 0 )
      {
        if ( *(v66 - 1) != 92 )
        {
          LOWORD(v70) = 0;
          v43 = v66 - v65 + 2;
          v68 = (wchar_t *)&v70;
          v69 = &v70;
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                   &v68,
                                   v43) )
          {
            v55 = 734;
            v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
            v56 = "NewImageRootPath.resize(NewLength)";
            v54 = "MountOverlayImage";
            MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                                   &v63,
                                   &v53,
                                   3221225495LL);
            v37 = &v68;
            goto LABEL_86;
          }
          swprintf_s(v68, v43, L"%ws\\", v65);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(&v65, &v68);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v68);
        }
        v99[0] = v65;
        v99[1] = v83[0];
        v41 = ((__int64 (__fastcall *)(UUID *, _QWORD *, __int64))v57)(&Buffer, v99, 2);
        if ( v41 >= 0 )
        {
          utl::vector<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::_Uninit(&v86);
          utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&v80);
          utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(&si128);
          AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr((AutoOverlayConfigurationPtr *)&hFile);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v83);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpFileName);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v74);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v65);
          Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v51);
          RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v96);
          return 0;
        }
        v55 = 756;
        v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
        v54 = "MountOverlayImage";
        v42 = "pfnCreateFileSystemUnion( &UnionGuid, LayerRootPaths, (sizeof(*RtlpNumberOf(LayerRootPaths))), UFS_CONFIG_"
              "OPTION_ALLOW_NESTED_UNION | UFS_CONFIG_OPTION_SELF_CONTAINED_UNION | UFS_CONFIG_OPTION_DELETE_PERSISTENCE_"
              "FILE_IF_CORRUPT, nullptr, nullptr)";
      }
      else
      {
        v55 = 727;
        v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
        v54 = "MountOverlayImage";
        v42 = "CimMergeMountImage( static_cast<UINT32>(CimImages.size()), CimImages.data(), MountFlags, &CimGuid)";
      }
      v56 = v42;
      v39 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
              &v63,
              &v53,
              (unsigned int)v41);
LABEL_97:
      MountGuidsFilePath = v39;
      goto LABEL_87;
    }
    v27 = *(_WORD **)(v23 + 32);
    if ( !v27 || !*v27 )
    {
      v55 = 661;
      v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v56 = "Cim.RelativePath && *Cim.RelativePath";
      v54 = "MountOverlayImage";
      v39 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v63,
              &v53,
              3221225659LL);
      goto LABEL_97;
    }
    LOWORD(v92[0]) = 0;
    v90 = (const char *)v92;
    v91 = (const char *)v92;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v90,
                             v27) )
    {
      v55 = 664;
      v35 = "CimRelativePath.assign(Cim.RelativePath)";
LABEL_83:
      v56 = v35;
      v36 = 3221225495LL;
LABEL_84:
      v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v54 = "MountOverlayImage";
      MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                             &v63,
                             &v53,
                             v36);
LABEL_85:
      v37 = (wchar_t **)&v90;
LABEL_86:
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v37);
LABEL_87:
      utl::vector<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::_Uninit(&v86);
      utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&v80);
      utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(&si128);
      goto LABEL_56;
    }
    if ( v26 == (_QWORD *)v21 )
    {
      if ( !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(&v80) )
      {
        v55 = 666;
        v35 = "FullCimPaths.emplace_back()";
        goto LABEL_83;
      }
      v21 = v81;
      v26 = (_QWORD *)v80.m128i_i64[1];
    }
    v28 = v26 + 2;
    *v26 = v26 + 2;
    v26[1] = v26 + 2;
    v26 += 4;
    *v28 = 0;
    v80.m128i_i64[1] = (__int64)v26;
    v29 = CombinePaths(&v65, &v90, v26 - 4);
    if ( v29 < 0 )
      goto LABEL_94;
    if ( *(_DWORD *)(v23 + 4) != 1 )
    {
      if ( *(_DWORD *)(v23 + 4) != 2 )
      {
        v55 = 711;
        v36 = 3221225659LL;
        v56 = 0;
        goto LABEL_84;
      }
      v30 = *(_QWORD *)(v23 + 48);
      v31 = v30 + 16LL * *(unsigned int *)(v23 + 40);
      while ( v30 != v31 )
      {
        if ( !(unsigned __int8)utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::emplace_back<,0>(&si128) )
        {
          v55 = 704;
          v35 = "CimImages.emplace_back()";
          goto LABEL_83;
        }
        v24 = si128.m128i_i64[1];
        *(_QWORD *)(si128.m128i_i64[1] - 16) = *(v26 - 4);
        v32 = *(_QWORD *)(v30 + 8);
        v30 += 16;
        *(_QWORD *)(v24 - 8) = v32;
      }
      goto LABEL_81;
    }
    LOWORD(v70) = 0;
    v68 = (wchar_t *)&v70;
    LOWORD(v95[0]) = 0;
    v69 = &v70;
    v93 = (const char *)v95;
    v94 = (const char *)v95;
    v29 = SplitPath(v26 - 4, &v68, &v93);
    if ( v29 < 0 )
      break;
    if ( !(unsigned __int8)utl::vector<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::emplace_back<,0>(&v86) )
    {
      v55 = 691;
      v38 = "SplitCimPaths.emplace_back()";
      goto LABEL_91;
    }
    v33 = v86.m128i_i64[1];
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v86.m128i_i64[1] - 64, &v68);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v33 - 32, &v93);
    if ( !(unsigned __int8)utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::emplace_back<,0>(&si128) )
    {
      v55 = 695;
      v38 = "CimImages.emplace_back()";
LABEL_91:
      v56 = v38;
      v53 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v54 = "MountOverlayImage";
      MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                             &v63,
                             &v53,
                             3221225495LL);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v93);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v68);
      goto LABEL_85;
    }
    v34 = *(_QWORD *)(v33 - 64);
    v24 = si128.m128i_i64[1];
    v50[0] = 1;
    *(_QWORD *)(si128.m128i_i64[1] - 16) = v34;
    *(_QWORD *)(v24 - 8) = *(_QWORD *)(v33 - 32);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v93);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v68);
LABEL_81:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v90);
    v23 += 56;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v93);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v68);
LABEL_94:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v90);
  utl::vector<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::_Uninit(&v86);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&v80);
  utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(&si128);
  AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr((AutoOverlayConfigurationPtr *)&hFile);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v83);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v74);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v65);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v51);
  MountGuidsFilePath = v29;
LABEL_131:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v96);
  return (unsigned int)MountGuidsFilePath;
}

```

## disassembly

```asm
0x18007eb20  mov     [rsp-8+arg_10], rbx
0x18007eb25  push    rbp
0x18007eb26  push    rsi
0x18007eb27  push    rdi
0x18007eb28  push    r12
0x18007eb2a  push    r13
0x18007eb2c  push    r14
0x18007eb2e  push    r15
0x18007eb30  lea     rbp, [rsp-190h]
0x18007eb38  sub     rsp, 290h
0x18007eb3f  mov     rax, cs:__security_cookie
0x18007eb46  xor     rax, rsp
0x18007eb49  mov     [rbp+1C0h+var_38], rax
0x18007eb50  xor     r12d, r12d
0x18007eb53  mov     r15, rdx
0x18007eb56  mov     [rbp+1C0h+var_1D8], r12d
0x18007eb5a  mov     r14, rcx
0x18007eb5d  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x18007eb62  test    r14, r14
0x18007eb65  jnz     short loc_18007EBA2
0x18007eb67  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007eb6e  mov     [rbp+1C0h+var_1A0], 1FBh
0x18007eb76  mov     [rbp+1C0h+var_1B0], rcx
0x18007eb7a  lea     rax, aNotNullCheckFa_61; "Not-null check failed: ImageRoot"
0x18007eb81  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007eb88  mov     [rbp+1C0h+var_198], rax
0x18007eb8c  mov     [rbp+1C0h+var_1A8], rcx
0x18007eb90  lea     rdx, [rbp+1C0h+var_1B0]
0x18007eb94  lea     rcx, [rbp+1C0h+var_1D8]
0x18007eb98  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007eb9d  jmp     loc_18007FA7F
0x18007eba2  cmp     [r14], r12w
0x18007eba6  jnz     short loc_18007EBE3
0x18007eba8  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ebaf  mov     [rbp+1C0h+var_1A0], 1FCh
0x18007ebb7  mov     [rbp+1C0h+var_1B0], rcx
0x18007ebbb  lea     rax, aImageroot; "*ImageRoot"
0x18007ebc2  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007ebc9  mov     [rbp+1C0h+var_198], rax
0x18007ebcd  mov     [rbp+1C0h+var_1A8], rcx
0x18007ebd1  lea     rdx, [rbp+1C0h+var_1B0]
0x18007ebd5  lea     rcx, [rbp+1C0h+var_1D8]
0x18007ebd9  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007ebde  jmp     loc_18007FA7F
0x18007ebe3  lea     rcx, [rbp+1C0h+var_68]; this
0x18007ebea  mov     [rbp+1C0h+var_68], r12
0x18007ebf1  mov     [rbp+1C0h+var_60], r12b
0x18007ebf8  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007ebfd  mov     ebx, eax
0x18007ebff  test    eax, eax
0x18007ec01  js      loc_18007FA71
0x18007ec07  lea     rcx, [rsp+2C0h+var_248]
0x18007ec0c  mov     [rsp+2C0h+var_248], r12
0x18007ec11  mov     [rbp+1C0h+var_218], r12
0x18007ec15  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ec1a  mov     rdx, rax; HINSTANCE *
0x18007ec1d  lea     r8, [rbp+1C0h+var_218]; __int64 (**)(void)
0x18007ec21  lea     rcx, aCreatefilesyst; "CreateFileSystemUnion"
0x18007ec28  call    ?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18007ec2d  test    al, al
0x18007ec2f  jnz     short loc_18007EC6D
0x18007ec31  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ec38  mov     [rbp+1C0h+var_1A0], 209h
0x18007ec40  mov     [rbp+1C0h+var_1B0], rcx
0x18007ec44  lea     rdx, [rbp+1C0h+var_1B0]
0x18007ec48  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007ec4f  mov     [rbp+1C0h+var_198], r12
0x18007ec53  mov     [rbp+1C0h+var_1A8], rcx
0x18007ec57  mov     r8d, 0C00000BBh
0x18007ec5d  lea     rcx, [rbp+1C0h+var_1D8]
0x18007ec61  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007ec66  mov     ebx, eax
0x18007ec68  jmp     loc_18007FA67
0x18007ec6d  lea     rdx, [rbp+1C0h+NumberOfBytesWritten]
0x18007ec71  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18007ec75  mov     rcx, r14
0x18007ec78  call    IsOverlayImage
0x18007ec7d  mov     ebx, eax
0x18007ec7f  test    eax, eax
0x18007ec81  js      loc_18007FA67
0x18007ec87  cmp     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18007ec8b  jnz     short loc_18007ECCA
0x18007ec8d  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ec94  mov     [rbp+1C0h+var_78], 210h
0x18007ec9f  mov     [rbp+1C0h+var_88], rcx
0x18007eca6  lea     rdx, [rbp+1C0h+var_88]
0x18007ecad  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007ecb4  mov     [rbp+1C0h+var_70], r12
0x18007ecbb  mov     [rbp+1C0h+var_80], rcx
0x18007ecc2  mov     r8d, 0C000000Dh
0x18007ecc8  jmp     short loc_18007EC5D
0x18007ecca  lea     rdx, [rbp+1C0h+var_E0]
0x18007ecd1  mov     [rbp+1C0h+var_E0], r12d
0x18007ecd8  mov     rcx, r14
0x18007ecdb  call    IsOverlayImageMounted
0x18007ece0  mov     ebx, eax
0x18007ece2  test    eax, eax
0x18007ece4  js      loc_18007FA67
0x18007ecea  cmp     [rbp+1C0h+var_E0], r12d
0x18007ecf1  jz      short loc_18007ED42
0x18007ecf3  mov     ecx, 800700B7h
0x18007ecf8  call    ConvertHResultToNtStatus
0x18007ecfd  test    eax, eax
0x18007ecff  jns     loc_18007EFF9
0x18007ed05  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ed0c  mov     [rbp+1C0h+var_98], 219h
0x18007ed17  mov     [rbp+1C0h+var_A8], rcx
0x18007ed1e  lea     rdx, [rbp+1C0h+var_A8]
0x18007ed25  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007ed2c  mov     [rbp+1C0h+var_90], r12
0x18007ed33  mov     [rbp+1C0h+var_A0], rcx
0x18007ed3a  mov     r8d, eax
0x18007ed3d  jmp     loc_18007EC5D
0x18007ed42  xorps   xmm0, xmm0
0x18007ed45  lea     rcx, [rbp+1C0h+Uuid]; Uuid
0x18007ed49  xorps   xmm1, xmm1
0x18007ed4c  movups  xmmword ptr [rbp+1C0h+Uuid.Data1], xmm0
0x18007ed50  movups  xmmword ptr [rbp+1C0h+Buffer.Data1], xmm1
0x18007ed57  call    cs:__imp_UuidCreate
0x18007ed5e  nop     dword ptr [rax+rax+00h]
0x18007ed63  test    eax, eax
0x18007ed65  jns     short loc_18007ED73
0x18007ed67  mov     ecx, eax
0x18007ed69  call    ConvertHResultToNtStatus
0x18007ed6e  jmp     loc_18007EC66
0x18007ed73  lea     rcx, [rbp+1C0h+Buffer]; Uuid
0x18007ed7a  call    cs:__imp_UuidCreate
0x18007ed81  nop     dword ptr [rax+rax+00h]
0x18007ed86  test    eax, eax
0x18007ed88  js      short loc_18007ED67
0x18007ed8a  lea     rax, [rbp+1C0h+var_1C0]
0x18007ed8e  mov     [rbp+1C0h+var_1C0], r12w
0x18007ed93  mov     [rbp+1C0h+var_1D0], rax
0x18007ed97  lea     rcx, [rbp+1C0h+var_1D0]
0x18007ed9b  lea     rax, [rbp+1C0h+var_1C0]
0x18007ed9f  mov     rdx, r14
0x18007eda2  mov     [rbp+1C0h+var_1C8], rax
0x18007eda6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007edab  test    al, al
0x18007edad  jnz     short loc_18007EE01
0x18007edaf  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007edb6  mov     [rbp+1C0h+var_C8], 223h
0x18007edc1  mov     qword ptr [rbp+1C0h+var_D8], rcx
0x18007edc8  lea     rax, aImagerootpathA; "ImageRootPath.assign(ImageRoot)"
0x18007edcf  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007edd6  mov     [rbp+1C0h+var_C0], rax
0x18007eddd  mov     qword ptr [rbp+1C0h+var_D8+8], rcx
0x18007ede4  lea     rdx, [rbp+1C0h+var_D8]
0x18007edeb  mov     r8d, 0C0000017h
0x18007edf1  lea     rcx, [rbp+1C0h+var_1D8]
0x18007edf5  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007edfa  mov     ebx, eax
0x18007edfc  jmp     loc_18007FA5E
0x18007ee01  mov     rax, [rbp+1C0h+var_1C8]
0x18007ee05  mov     r9d, 4
0x18007ee0b  mov     rcx, [rbp+1C0h+var_1D0]
0x18007ee0f  sub     rax, rcx
0x18007ee12  sar     rax, 1
0x18007ee15  cmp     rax, r9
0x18007ee18  jb      loc_18007EEC6
0x18007ee1e  mov     r8d, r9d
0x18007ee21  lea     rdx, String1; "\\\\?\\"
0x18007ee28  movzx   eax, word ptr [rcx]
0x18007ee2b  cmp     [rdx], ax
0x18007ee2e  jnz     loc_18007EEC6
0x18007ee34  add     rdx, 2
0x18007ee38  add     rcx, 2
0x18007ee3c  sub     r8, 1
0x18007ee40  jnz     short loc_18007EE28
0x18007ee42  mov     [rbp+1C0h+var_160], r12w
0x18007ee47  lea     rax, [rbp+1C0h+var_160]
0x18007ee4b  mov     [rbp+1C0h+var_170], rax
0x18007ee4f  lea     rax, [rbp+1C0h+var_160]
0x18007ee53  mov     [rbp+1C0h+var_168], rax
0x18007ee57  test    r15, r15
0x18007ee5a  jz      loc_18007EF18
0x18007ee60  mov     rdx, r15
0x18007ee63  lea     rcx, [rbp+1C0h+var_170]
0x18007ee67  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007ee6c  test    al, al
0x18007ee6e  jnz     loc_18007EF18
0x18007ee74  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ee7b  mov     [rbp+1C0h+var_130], 22Eh
0x18007ee86  mov     qword ptr [rbp+1C0h+var_140], rcx
0x18007ee8d  lea     rax, aCimrootpathAss; "CimRootPath.assign(CimRoot)"
0x18007ee94  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007ee9b  mov     [rbp+1C0h+var_128], rax
0x18007eea2  mov     qword ptr [rbp+1C0h+var_140+8], rcx
0x18007eea9  lea     rdx, [rbp+1C0h+var_140]
0x18007eeb0  lea     rcx, [rbp+1C0h+var_1D8]
0x18007eeb4  mov     r8d, 0C0000017h
0x18007eeba  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007eebf  mov     ebx, eax
0x18007eec1  jmp     loc_18007FA55
0x18007eec6  lea     rcx, [rbp+1C0h+var_1D0]
0x18007eeca  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
0x18007eecf  test    al, al
0x18007eed1  jnz     loc_18007EE42
0x18007eed7  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007eede  mov     [rbp+1C0h+var_110], 228h
0x18007eee9  mov     qword ptr [rbp+1C0h+var_120], rcx
0x18007eef0  lea     rax, aImagerootpathI; "ImageRootPath.insert(0, c_Long_Path_Pre"...
0x18007eef7  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007eefe  mov     [rbp+1C0h+var_108], rax
0x18007ef05  mov     qword ptr [rbp+1C0h+var_120+8], rcx
0x18007ef0c  lea     rdx, [rbp+1C0h+var_120]
0x18007ef13  jmp     loc_18007EDEB
0x18007ef18  lea     rax, [rbp+1C0h+var_180]
0x18007ef1c  mov     [rbp+1C0h+var_180], r12w
0x18007ef21  mov     [rbp+1C0h+lpFileName], rax
0x18007ef25  lea     r8, [rbp+1C0h+lpFileName]
0x18007ef29  lea     rax, [rbp+1C0h+var_180]
0x18007ef2d  lea     rdx, [rbp+1C0h+var_170]
0x18007ef31  mov     [rbp+1C0h+var_188], rax
0x18007ef35  lea     rcx, [rbp+1C0h+var_1D0]
0x18007ef39  call    ?GetMountGuidsFilePath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; GetMountGuidsFilePath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007ef3e  lea     rcx, [rbp+1C0h+lpFileName]
0x18007ef42  mov     ebx, eax
0x18007ef44  test    eax, eax
0x18007ef46  js      loc_18007FA50
0x18007ef4c  lea     rdx, [rsp+2C0h+var_250]
0x18007ef51  mov     [rsp+2C0h+var_250], r12b
0x18007ef56  call    ?FileExists@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEA_N@Z; FileExists(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,bool &)
0x18007ef5b  mov     ebx, eax
0x18007ef5d  test    eax, eax
0x18007ef5f  js      loc_18007FA4C
0x18007ef65  cmp     [rsp+2C0h+var_250], r12b
0x18007ef6a  jz      loc_18007F00B
0x18007ef70  mov     rcx, [rbp+1C0h+lpFileName]; lpFileName
0x18007ef74  call    cs:__imp_DeleteFileW
0x18007ef7b  nop     dword ptr [rax+rax+00h]
0x18007ef80  test    eax, eax
0x18007ef82  jnz     loc_18007F00B
0x18007ef88  call    cs:__imp_GetLastError
0x18007ef8f  nop     dword ptr [rax+rax+00h]
0x18007ef94  test    eax, eax
0x18007ef96  jnz     short loc_18007EFE9
0x18007ef98  mov     eax, 36FDh
0x18007ef9d  mov     [rbp+1C0h+var_228], 238h
0x18007efa5  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007efac  mov     [rbp+1C0h+var_238], rcx
0x18007efb0  lea     rcx, aMountoverlayim_0; "MountOverlayImage"
0x18007efb7  mov     [rbp+1C0h+var_230], rcx
0x18007efbb  lea     rcx, aEnsureboolDele; "EnsureBOOL(::DeleteFileW(GuidFilePath.c"...
0x18007efc2  mov     [rbp+1C0h+var_220], rcx
0x18007efc6  test    eax, eax
0x18007efc8  jle     short loc_18007EFD2
0x18007efca  movzx   eax, ax
0x18007efcd  or      eax, 80070000h
0x18007efd2  mov     r8d, eax
0x18007efd5  lea     rdx, [rbp+1C0h+var_238]
0x18007efd9  lea     rcx, [rbp+1C0h+var_1D8]
0x18007efdd  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007efe2  mov     ebx, eax
0x18007efe4  jmp     loc_18007FA4C
0x18007efe9  call    cs:__imp_GetLastError
0x18007eff0  nop     dword ptr [rax+rax+00h]
0x18007eff5  test    eax, eax
0x18007eff7  jnz     short loc_18007EF9D
0x18007eff9  mov     ecx, 0C00000E5h; Status
0x18007effe  call    cs:__imp_RtlRaiseStatus
0x18007f005  nop     dword ptr [rax+rax+00h]
0x18007f00a  int     3; Trap to Debugger
0x18007f00b  mov     edi, 10h
0x18007f010  mov     [rbp+1C0h+var_B8], r12
0x18007f017  mov     ecx, edi
0x18007f019  mov     [rbp+1C0h+var_B0], r12
0x18007f020  lea     rdx, [rbp+1C0h+var_B8]
0x18007f027  call    ?GetFileSystemDefaultSecurity@@YAJKPEAV?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@@Z; GetFileSystemDefaultSecurity(ulong,Windows::Auto<_SECURITY_DESCRIPTOR> *)
0x18007f02c  mov     ebx, eax
0x18007f02e  test    eax, eax
0x18007f030  js      loc_18007FA40
0x18007f036  mov     rax, [rbp+1C0h+var_B8]
0x18007f03d  lea     r9, [rbp+1C0h+SecurityAttributes]; lpSecurityAttributes
0x18007f041  mov     rcx, [rbp+1C0h+lpFileName]; lpFileName
0x18007f045  lea     r8d, [rdi-0Fh]; dwShareMode
0x18007f049  mov     [rsp+2C0h+hTemplateFile], r12; hTemplateFile
0x18007f04e  mov     edx, 0C0000000h; dwDesiredAccess
0x18007f053  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x18007f05b  mov     [rbp+1C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18007f05f  mov     [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x18007f067  mov     qword ptr [rbp+1C0h+SecurityAttributes.nLength], 18h
0x18007f06f  mov     qword ptr [rbp+1C0h+SecurityAttributes.bInheritHandle], r12
0x18007f073  mov     [rbp+1C0h+hFile], r12
0x18007f077  call    cs:__imp_CreateFileW
0x18007f07e  nop     dword ptr [rax+rax+00h]
0x18007f083  mov     rdx, rax
0x18007f086  lea     rcx, [rbp+1C0h+hFile]
0x18007f08a  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007f08f  mov     rbx, [rbp+1C0h+hFile]
0x18007f093  lea     rax, [rbx-1]
0x18007f097  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007f09b  ja      loc_18007F9D7
0x18007f0a1  lea     r9, [rbp+1C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007f0a5  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18007f0a9  mov     r8d, edi; nNumberOfBytesToWrite
0x18007f0ac  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; lpOverlapped
0x18007f0b1  lea     rdx, [rbp+1C0h+Uuid]; lpBuffer
0x18007f0b5  mov     rcx, rbx; hFile
0x18007f0b8  call    cs:__imp_WriteFile
  ... truncated ...
```
