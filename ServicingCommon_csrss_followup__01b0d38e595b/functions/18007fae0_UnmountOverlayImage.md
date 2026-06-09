# UnmountOverlayImage

- ea: `0x18007fae0`
- end: `0x1800801c0`
- name: `UnmountOverlayImage`
- size: `1760`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180018df0`
- `0x18001f840`
- `0x180020dc0`
- `0x18002d2b0`
- `0x180042bac`
- `0x180047d5c`
- `0x18006c244`
- `0x1800735e0`
- `0x18007cbb8`
- `0x18007d5a8`
- `0x18007d6f4`
- `0x18007d794`
- `0x18007df88`
- `0x18007e064`
- `0x18007e5c0`
- `0x18007fae0`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007fdb5`
- `KERNEL32!GetLastError` at `0x18007fdcc`
- `KERNEL32!GetLastError` at `0x18007fe65`
- `KERNEL32!GetLastError` at `0x18007fe7c`
- `KERNEL32!GetLastError` at `0x18007ff37`
- `KERNEL32!GetLastError` at `0x18007ff8a`
- `KERNEL32!GetLastError` at `0x180080093`
- `KERNEL32!GetLastError` at `0x180080136`
- `KERNEL32!GetLastError` at `0x18007fdb5`
- `KERNEL32!GetLastError` at `0x18007fdcc`
- `KERNEL32!GetLastError` at `0x18007fe65`
- `KERNEL32!GetLastError` at `0x18007fe7c`
- `KERNEL32!GetLastError` at `0x18007ff37`
- `KERNEL32!GetLastError` at `0x18007ff8a`
- `KERNEL32!GetLastError` at `0x180080093`
- `KERNEL32!GetLastError` at `0x180080136`
- `KERNEL32!DeleteFileW` at `0x18008007f`
- `KERNEL32!DeleteFileW` at `0x18008007f`
- `KERNEL32!CreateFileW` at `0x18007fd87`
- `KERNEL32!CreateFileW` at `0x18007fd87`
- `KERNEL32!ReadFile` at `0x18007fe55`
- `KERNEL32!ReadFile` at `0x18007ff27`
- `KERNEL32!ReadFile` at `0x18007fe55`
- `KERNEL32!ReadFile` at `0x18007ff27`
- `ntdll!RtlRaiseStatus` at `0x18007ff9f`
- `ntdll!RtlRaiseStatus` at `0x18008014f`
- `ntdll!RtlRaiseStatus` at `0x18007ff9f`
- `ntdll!RtlRaiseStatus` at `0x18008014f`
- `CIMFS!CimDismountImage` at `0x18008003e`
- `CIMFS!CimDismountImage` at `0x18008003e`

## string_xrefs

- `0x18007fb70`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fbd7`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fc3c`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fcbb`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fde8`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fe98`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fed3`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ff54`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ffb1`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080005`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18008004e`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x1800800b5`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fc4f`: `ImageRootPath.assign(ImageRoot)`
- `0x18007fcce`: `CimRootPath.assign(CimRoot)`
- `0x1800800cd`: `EnsureBOOL(::DeleteFileW(GuidFilePath.c_str()))`
- `0x18007fb89`: `UnmountOverlayImage`
- `0x18007fbee`: `UnmountOverlayImage`
- `0x18007fc56`: `UnmountOverlayImage`
- `0x18007fcd5`: `UnmountOverlayImage`
- `0x18007fdf3`: `UnmountOverlayImage`
- `0x18007fea3`: `UnmountOverlayImage`
- `0x18007feea`: `UnmountOverlayImage`
- `0x18007ff5f`: `UnmountOverlayImage`
- `0x18007ffcb`: `UnmountOverlayImage`
- `0x18008001a`: `UnmountOverlayImage`
- `0x180080063`: `UnmountOverlayImage`
- `0x1800800c1`: `UnmountOverlayImage`
- `0x18007feae`: `EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&CimGuid), BytesToRead, &BytesRead, nullptr))`
- `0x18007fb60`: `RemoveFileSystemUnion`
- `0x180080026`: `pfnRemoveFileSystemUnion( &UnionGuid, UFS_CONFIG_OPTION_NONE, nullptr)`
- `0x18007ff6a`: `EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&UnionGuid), BytesToRead, &BytesRead, nullptr))`
- `0x18008006f`: `CimDismountImage(&CimGuid)`

## pseudocode

```c
__int64 __fastcall UnmountOverlayImage(Windows::WCP::Implementation::Rtl *a1, __int64 a2)
{
  int MountGuidsFilePath; // ebx
  HINSTANCE *InitPointer; // rax
  _QWORD *v6; // rdx
  __int64 v7; // r8
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  signed int LastError; // eax
  _QWORD *v11; // rdx
  int v12; // eax
  const char **v13; // rdx
  signed int v14; // eax
  const char *v15; // rcx
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  const char *v19; // [rsp+50h] [rbp-B0h] BYREF
  const char *v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  const char *v22; // [rsp+68h] [rbp-98h]
  __int64 (*v23)(void); // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v25[4]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v26[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v27[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v29[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v30[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v31[4]; // [rsp+158h] [rbp+58h] BYREF
  int v32; // [rsp+178h] [rbp+78h] BYREF
  DWORD NumberOfBytesRead; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v34; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v35[2]; // [rsp+188h] [rbp+88h] BYREF
  _WORD v36[8]; // [rsp+198h] [rbp+98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  _WORD v38[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v39[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  _WORD v40[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v41; // [rsp+1E8h] [rbp+E8h] BYREF
  char v42; // [rsp+1F0h] [rbp+F0h]
  __int128 v43; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 Buffer; // [rsp+208h] [rbp+108h] BYREF

  v32 = 0;
  Windows::WCP::Implementation::Rtl::InitializeWdscore(a1);
  v41 = 0;
  v42 = 0;
  MountGuidsFilePath = RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition *)&v41);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_58;
  v17 = 0;
  v23 = 0;
  InitPointer = (HINSTANCE *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v17);
  if ( !IsOverlayAPISupported("RemoveFileSystemUnion", InitPointer, &v23) )
  {
    v24[2] = 791;
    v24[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v6 = v24;
    v24[3] = 0;
    v24[1] = "UnmountOverlayImage";
    v7 = 3221225659LL;
LABEL_4:
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v32,
                           v6,
                           v7);
LABEL_57:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v17);
LABEL_58:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v41);
    return (unsigned int)MountGuidsFilePath;
  }
  v34 = 0;
  MountGuidsFilePath = IsOverlayImageMounted(a1, &v34);
  if ( MountGuidsFilePath < 0 )
    goto LABEL_57;
  if ( !v34 )
  {
    v25[2] = 798;
    v25[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v6 = v25;
    v25[3] = 0;
    v25[1] = "UnmountOverlayImage";
    v7 = 3221225485LL;
    goto LABEL_4;
  }
  v36[0] = 0;
  v35[0] = v36;
  v35[1] = v36;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v35, a1) )
  {
    v26[2] = 802;
    v26[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v26[3] = "ImageRootPath.assign(ImageRoot)";
    v26[1] = "UnmountOverlayImage";
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v32,
                           v26,
                           3221225495LL);
LABEL_56:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v35);
    goto LABEL_57;
  }
  v40[0] = 0;
  v39[0] = v40;
  v39[1] = v40;
  if ( a2
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v39, a2) )
  {
    v27[2] = 807;
    v27[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v27[3] = "CimRootPath.assign(CimRoot)";
    v27[1] = "UnmountOverlayImage";
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v32,
                           v27,
                           3221225495LL);
LABEL_55:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v39);
    goto LABEL_56;
  }
  v38[0] = 0;
  lpFileName[0] = v38;
  lpFileName[1] = v38;
  MountGuidsFilePath = GetMountGuidsFilePath(v35, v39, lpFileName);
  if ( MountGuidsFilePath < 0 )
  {
LABEL_54:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpFileName);
    goto LABEL_55;
  }
  hFile = 0;
  Buffer = 0;
  v43 = 0;
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hFile,
    FileW);
  v9 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_18:
      v28[2] = 827;
      v28[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v28[1] = "UnmountOverlayImage";
      v28[3] = "GuidFile.IsValid()";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = v28;
LABEL_21:
      v12 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
              &v32,
              v11,
              (unsigned int)LastError);
LABEL_22:
      MountGuidsFilePath = v12;
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
      goto LABEL_54;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_18;
LABEL_40:
    RtlRaiseStatus(-1073741595);
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, &Buffer, 0x10u, &NumberOfBytesRead, 0) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_40;
    }
    else
    {
      LastError = 14077;
    }
    v29[2] = 837;
    v29[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v29[1] = "UnmountOverlayImage";
    v29[3] = "EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&CimGuid), BytesToRead, &BytesRead, nullptr))";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = v29;
    goto LABEL_21;
  }
  if ( NumberOfBytesRead != 16 )
  {
    v30[2] = 840;
    v30[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v13 = (const char **)v30;
    v30[3] = 0;
    v30[1] = "UnmountOverlayImage";
LABEL_32:
    v12 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v32,
            v13,
            3221225730LL);
    goto LABEL_22;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v9, &v43, 0x10u, &NumberOfBytesRead, 0) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_40;
    }
    else
    {
      LastError = 14077;
    }
    v31[2] = 851;
    v31[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v31[1] = "UnmountOverlayImage";
    v31[3] = "EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&UnionGuid), BytesToRead, &BytesRead, nullptr))";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = v31;
    goto LABEL_21;
  }
  if ( NumberOfBytesRead != 16 )
  {
    v21 = 854;
    v19 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v13 = &v19;
    v22 = 0;
    v20 = "UnmountOverlayImage";
    goto LABEL_32;
  }
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
  v14 = ((__int64 (__fastcall *)(__int128 *, _QWORD, _QWORD))v23)(&v43, 0, 0);
  if ( v14 < 0 )
  {
    v21 = 862;
    v19 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v20 = "UnmountOverlayImage";
    v15 = "pfnRemoveFileSystemUnion( &UnionGuid, UFS_CONFIG_OPTION_NONE, nullptr)";
LABEL_45:
    v22 = v15;
LABEL_53:
    MountGuidsFilePath = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
                           &v32,
                           &v19,
                           (unsigned int)v14);
    goto LABEL_54;
  }
  v14 = CimDismountImage(&Buffer);
  if ( v14 < 0 )
  {
    v21 = 864;
    v19 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v20 = "UnmountOverlayImage";
    v15 = "CimDismountImage(&CimGuid)";
    goto LABEL_45;
  }
  if ( !DeleteFileW(lpFileName[0]) )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      if ( !v14 )
        RtlRaiseStatus(-1073741595);
    }
    else
    {
      v14 = 14077;
    }
    v21 = 866;
    v19 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v20 = "UnmountOverlayImage";
    v22 = "EnsureBOOL(::DeleteFileW(GuidFilePath.c_str()))";
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_53;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v39);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v35);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v17);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v41);
  return 0;
}

```

## disassembly

```asm
0x18007fae0  mov     [rsp-8+arg_10], rbx
0x18007fae5  mov     [rsp-8+arg_18], rsi
0x18007faea  push    rbp
0x18007faeb  push    rdi
0x18007faec  push    r14
0x18007faee  lea     rbp, [rsp-120h]
0x18007faf6  sub     rsp, 220h
0x18007fafd  mov     rax, cs:__security_cookie
0x18007fb04  xor     rax, rsp
0x18007fb07  mov     [rbp+130h+var_18], rax
0x18007fb0e  xor     r14d, r14d
0x18007fb11  mov     rdi, rdx
0x18007fb14  mov     [rbp+130h+var_B8], r14d
0x18007fb18  mov     rsi, rcx
0x18007fb1b  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x18007fb20  lea     rcx, [rbp+130h+var_48]; this
0x18007fb27  mov     [rbp+130h+var_48], r14
0x18007fb2e  mov     [rbp+130h+var_40], r14b
0x18007fb35  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007fb3a  mov     ebx, eax
0x18007fb3c  test    eax, eax
0x18007fb3e  js      loc_180080126
0x18007fb44  lea     rcx, [rsp+230h+var_1F0]
0x18007fb49  mov     [rsp+230h+var_1F0], r14
0x18007fb4e  mov     [rsp+230h+var_1C0], r14
0x18007fb53  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007fb58  mov     rdx, rax; HINSTANCE *
0x18007fb5b  lea     r8, [rsp+230h+var_1C0]; __int64 (**)(void)
0x18007fb60  lea     rcx, aRemovefilesyst; "RemoveFileSystemUnion"
0x18007fb67  call    ?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18007fb6c  test    al, al
0x18007fb6e  jnz     short loc_18007FBAE
0x18007fb70  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fb77  mov     [rbp+130h+var_1A8], 317h
0x18007fb7f  mov     [rsp+230h+var_1B8], rcx
0x18007fb84  lea     rdx, [rsp+230h+var_1B8]
0x18007fb89  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fb90  mov     [rbp+130h+var_1A0], r14
0x18007fb94  mov     [rbp+130h+var_1B0], rcx
0x18007fb98  mov     r8d, 0C00000BBh
0x18007fb9e  lea     rcx, [rbp+130h+var_B8]
0x18007fba2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007fba7  mov     ebx, eax
0x18007fba9  jmp     loc_18008011C
0x18007fbae  lea     rdx, [rbp+130h+var_B0]
0x18007fbb5  mov     [rbp+130h+var_B0], r14d
0x18007fbbc  mov     rcx, rsi
0x18007fbbf  call    IsOverlayImageMounted
0x18007fbc4  mov     ebx, eax
0x18007fbc6  test    eax, eax
0x18007fbc8  js      loc_18008011C
0x18007fbce  cmp     [rbp+130h+var_B0], r14d
0x18007fbd5  jnz     short loc_18007FC05
0x18007fbd7  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fbde  mov     [rbp+130h+var_188], 31Eh
0x18007fbe6  mov     [rbp+130h+var_198], rcx
0x18007fbea  lea     rdx, [rbp+130h+var_198]
0x18007fbee  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fbf5  mov     [rbp+130h+var_180], r14
0x18007fbf9  mov     [rbp+130h+var_190], rcx
0x18007fbfd  mov     r8d, 0C000000Dh
0x18007fc03  jmp     short loc_18007FB9E
0x18007fc05  lea     rax, [rbp+130h+var_98]
0x18007fc0c  mov     [rbp+130h+var_98], r14w
0x18007fc14  mov     [rbp+130h+var_A8], rax
0x18007fc1b  lea     rcx, [rbp+130h+var_A8]
0x18007fc22  lea     rax, [rbp+130h+var_98]
0x18007fc29  mov     rdx, rsi
0x18007fc2c  mov     [rbp+130h+var_A0], rax
0x18007fc33  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007fc38  test    al, al
0x18007fc3a  jnz     short loc_18007FC7F
0x18007fc3c  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fc43  mov     [rbp+130h+var_168], 322h
0x18007fc4b  mov     [rbp+130h+var_178], rcx
0x18007fc4f  lea     rax, aImagerootpathA; "ImageRootPath.assign(ImageRoot)"
0x18007fc56  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fc5d  mov     [rbp+130h+var_160], rax
0x18007fc61  mov     [rbp+130h+var_170], rcx
0x18007fc65  lea     rdx, [rbp+130h+var_178]
0x18007fc69  lea     rcx, [rbp+130h+var_B8]
0x18007fc6d  mov     r8d, 0C0000017h
0x18007fc73  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007fc78  mov     ebx, eax
0x18007fc7a  jmp     loc_180080110
0x18007fc7f  mov     [rbp+130h+var_58], r14w
0x18007fc87  lea     rax, [rbp+130h+var_58]
0x18007fc8e  mov     [rbp+130h+var_68], rax
0x18007fc95  lea     rax, [rbp+130h+var_58]
0x18007fc9c  mov     [rbp+130h+var_60], rax
0x18007fca3  test    rdi, rdi
0x18007fca6  jz      short loc_18007FCFE
0x18007fca8  mov     rdx, rdi
0x18007fcab  lea     rcx, [rbp+130h+var_68]
0x18007fcb2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007fcb7  test    al, al
0x18007fcb9  jnz     short loc_18007FCFE
0x18007fcbb  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fcc2  mov     [rbp+130h+var_148], 327h
0x18007fcca  mov     [rbp+130h+var_158], rcx
0x18007fcce  lea     rax, aCimrootpathAss; "CimRootPath.assign(CimRoot)"
0x18007fcd5  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fcdc  mov     [rbp+130h+var_140], rax
0x18007fce0  mov     [rbp+130h+var_150], rcx
0x18007fce4  lea     rdx, [rbp+130h+var_158]
0x18007fce8  lea     rcx, [rbp+130h+var_B8]
0x18007fcec  mov     r8d, 0C0000017h
0x18007fcf2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007fcf7  mov     ebx, eax
0x18007fcf9  jmp     loc_180080104
0x18007fcfe  lea     rax, [rbp+130h+var_78]
0x18007fd05  mov     [rbp+130h+var_78], r14w
0x18007fd0d  mov     [rbp+130h+lpFileName], rax
0x18007fd14  lea     r8, [rbp+130h+lpFileName]
0x18007fd1b  lea     rax, [rbp+130h+var_78]
0x18007fd22  lea     rdx, [rbp+130h+var_68]
0x18007fd29  mov     [rbp+130h+var_80], rax
0x18007fd30  lea     rcx, [rbp+130h+var_A8]
0x18007fd37  call    ?GetMountGuidsFilePath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; GetMountGuidsFilePath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007fd3c  mov     ebx, eax
0x18007fd3e  test    eax, eax
0x18007fd40  js      loc_1800800F8
0x18007fd46  mov     rcx, [rbp+130h+lpFileName]; lpFileName
0x18007fd4d  xor     r9d, r9d; lpSecurityAttributes
0x18007fd50  xorps   xmm0, xmm0
0x18007fd53  mov     [rsp+230h+hTemplateFile], r14; hTemplateFile
0x18007fd58  xorps   xmm1, xmm1
0x18007fd5b  mov     [rsp+230h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007fd63  mov     edx, 0C0000000h; dwDesiredAccess
0x18007fd68  mov     [rsp+230h+hFile], r14
0x18007fd6d  lea     r8d, [r9+1]; dwShareMode
0x18007fd71  mov     [rsp+230h+dwCreationDisposition], 3; dwCreationDisposition
0x18007fd79  movups  [rbp+130h+Buffer], xmm0
0x18007fd80  movups  [rbp+130h+var_38], xmm1
0x18007fd87  call    cs:__imp_CreateFileW
0x18007fd8e  nop     dword ptr [rax+rax+00h]
0x18007fd93  mov     rdx, rax
0x18007fd96  lea     rcx, [rsp+230h+hFile]
0x18007fd9b  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007fda0  mov     rbx, [rsp+230h+hFile]
0x18007fda5  lea     rax, [rbx+1]
0x18007fda9  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007fdaf  jnz     loc_18007FE36
0x18007fdb5  call    cs:__imp_GetLastError
0x18007fdbc  nop     dword ptr [rax+rax+00h]
0x18007fdc1  test    eax, eax
0x18007fdc3  jnz     short loc_18007FDCC
0x18007fdc5  mov     eax, 36FDh
0x18007fdca  jmp     short loc_18007FDE0
0x18007fdcc  call    cs:__imp_GetLastError
0x18007fdd3  nop     dword ptr [rax+rax+00h]
0x18007fdd8  test    eax, eax
0x18007fdda  jz      loc_18007FF9A
0x18007fde0  mov     [rbp+130h+var_128], 33Bh
0x18007fde8  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fdef  mov     [rbp+130h+var_138], rcx
0x18007fdf3  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fdfa  mov     [rbp+130h+var_130], rcx
0x18007fdfe  lea     rcx, aGuidfileIsvali; "GuidFile.IsValid()"
0x18007fe05  mov     [rbp+130h+var_120], rcx
0x18007fe09  test    eax, eax
0x18007fe0b  jle     short loc_18007FE15
0x18007fe0d  movzx   eax, ax
0x18007fe10  or      eax, 80070000h
0x18007fe15  lea     rdx, [rbp+130h+var_138]
0x18007fe19  mov     r8d, eax
0x18007fe1c  lea     rcx, [rbp+130h+var_B8]
0x18007fe20  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007fe25  lea     rcx, [rsp+230h+hFile]
0x18007fe2a  mov     ebx, eax
0x18007fe2c  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007fe31  jmp     loc_1800800F8
0x18007fe36  mov     edi, 10h
0x18007fe3b  mov     [rbp+130h+NumberOfBytesRead], r14d
0x18007fe3f  mov     r8d, edi; nNumberOfBytesToRead
0x18007fe42  mov     qword ptr [rsp+230h+dwCreationDisposition], r14; lpOverlapped
0x18007fe47  lea     r9, [rbp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007fe4b  mov     rcx, rbx; hFile
0x18007fe4e  lea     rdx, [rbp+130h+Buffer]; lpBuffer
0x18007fe55  call    cs:__imp_ReadFile
0x18007fe5c  nop     dword ptr [rax+rax+00h]
0x18007fe61  test    eax, eax
0x18007fe63  jnz     short loc_18007FECE
0x18007fe65  call    cs:__imp_GetLastError
0x18007fe6c  nop     dword ptr [rax+rax+00h]
0x18007fe71  test    eax, eax
0x18007fe73  jnz     short loc_18007FE7C
0x18007fe75  mov     eax, 36FDh
0x18007fe7a  jmp     short loc_18007FE90
0x18007fe7c  call    cs:__imp_GetLastError
0x18007fe83  nop     dword ptr [rax+rax+00h]
0x18007fe88  test    eax, eax
0x18007fe8a  jz      loc_18007FF9A
0x18007fe90  mov     [rbp+130h+var_108], 345h
0x18007fe98  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fe9f  mov     [rbp+130h+var_118], rcx
0x18007fea3  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007feaa  mov     [rbp+130h+var_110], rcx
0x18007feae  lea     rcx, aEnsureboolRead_0; "EnsureBOOL(::ReadFile( GuidFile, reinte"...
0x18007feb5  mov     [rbp+130h+var_100], rcx
0x18007feb9  test    eax, eax
0x18007febb  jle     short loc_18007FEC5
0x18007febd  movzx   eax, ax
0x18007fec0  or      eax, 80070000h
0x18007fec5  lea     rdx, [rbp+130h+var_118]
0x18007fec9  jmp     loc_18007FE19
0x18007fece  cmp     [rbp+130h+NumberOfBytesRead], edi
0x18007fed1  jz      short loc_18007FF0D
0x18007fed3  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007feda  mov     [rbp+130h+var_E8], 348h
0x18007fee2  mov     [rbp+130h+var_F8], rcx
0x18007fee6  lea     rdx, [rbp+130h+var_F8]
0x18007feea  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007fef1  mov     [rbp+130h+var_E0], r14
0x18007fef5  mov     [rbp+130h+var_F0], rcx
0x18007fef9  mov     r8d, 0C0000102h
0x18007feff  lea     rcx, [rbp+130h+var_B8]
0x18007ff03  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007ff08  jmp     loc_18007FE25
0x18007ff0d  lea     r9, [rbp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007ff11  mov     [rbp+130h+NumberOfBytesRead], r14d
0x18007ff15  mov     r8d, edi; nNumberOfBytesToRead
0x18007ff18  mov     qword ptr [rsp+230h+dwCreationDisposition], r14; lpOverlapped
0x18007ff1d  lea     rdx, [rbp+130h+var_38]; lpBuffer
0x18007ff24  mov     rcx, rbx; hFile
0x18007ff27  call    cs:__imp_ReadFile
0x18007ff2e  nop     dword ptr [rax+rax+00h]
0x18007ff33  test    eax, eax
0x18007ff35  jnz     short loc_18007FFAC
0x18007ff37  call    cs:__imp_GetLastError
0x18007ff3e  nop     dword ptr [rax+rax+00h]
0x18007ff43  test    eax, eax
0x18007ff45  jnz     short loc_18007FF8A
0x18007ff47  mov     eax, 36FDh
0x18007ff4c  mov     [rbp+130h+var_C8], 353h
0x18007ff54  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ff5b  mov     [rbp+130h+var_D8], rcx
0x18007ff5f  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007ff66  mov     [rbp+130h+var_D0], rcx
0x18007ff6a  lea     rcx, aEnsureboolRead; "EnsureBOOL(::ReadFile( GuidFile, reinte"...
0x18007ff71  mov     [rbp+130h+var_C0], rcx
0x18007ff75  test    eax, eax
0x18007ff77  jle     short loc_18007FF81
0x18007ff79  movzx   eax, ax
0x18007ff7c  or      eax, 80070000h
0x18007ff81  lea     rdx, [rbp+130h+var_D8]
0x18007ff85  jmp     loc_18007FE19
0x18007ff8a  call    cs:__imp_GetLastError
0x18007ff91  nop     dword ptr [rax+rax+00h]
0x18007ff96  test    eax, eax
0x18007ff98  jnz     short loc_18007FF4C
0x18007ff9a  mov     ecx, 0C00000E5h; Status
0x18007ff9f  call    cs:__imp_RtlRaiseStatus
0x18007ffa6  nop     dword ptr [rax+rax+00h]
0x18007ffab  int     3; Trap to Debugger
0x18007ffac  cmp     [rbp+130h+NumberOfBytesRead], edi
0x18007ffaf  jz      short loc_18007FFE1
0x18007ffb1  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ffb8  mov     [rsp+230h+var_1D0], 356h
0x18007ffc1  mov     [rsp+230h+var_1E0], rcx
0x18007ffc6  lea     rdx, [rsp+230h+var_1E0]
0x18007ffcb  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18007ffd2  mov     [rsp+230h+var_1C8], r14
0x18007ffd7  mov     [rsp+230h+var_1D8], rcx
0x18007ffdc  jmp     loc_18007FEF9
0x18007ffe1  lea     rcx, [rsp+230h+hFile]
0x18007ffe6  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007ffeb  mov     rax, [rsp+230h+var_1C0]
0x18007fff0  lea     rcx, [rbp+130h+var_38]
0x18007fff7  xor     r8d, r8d
0x18007fffa  xor     edx, edx
0x18007fffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080001  test    eax, eax
0x180080003  jns     short loc_180080037
0x180080005  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18008000c  mov     [rsp+230h+var_1D0], 35Eh
0x180080015  mov     [rsp+230h+var_1E0], rcx
0x18008001a  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080021  mov     [rsp+230h+var_1D8], rcx
0x180080026  lea     rcx, aPfnremovefiles; "pfnRemoveFileSystemUnion( &UnionGuid, U"...
0x18008002d  mov     [rsp+230h+var_1C8], rcx
0x180080032  jmp     loc_1800800E5
0x180080037  lea     rcx, [rbp+130h+Buffer]
0x18008003e  call    cs:__imp_CimDismountImage
0x180080045  nop     dword ptr [rax+rax+00h]
0x18008004a  test    eax, eax
0x18008004c  jns     short loc_180080078
0x18008004e  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080055  mov     [rsp+230h+var_1D0], 360h
0x18008005e  mov     [rsp+230h+var_1E0], rcx
0x180080063  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x18008006a  mov     [rsp+230h+var_1D8], rcx
0x18008006f  lea     rcx, aCimdismountima_0; "CimDismountImage(&CimGuid)"
0x180080076  jmp     short loc_18008002D
0x180080078  mov     rcx, [rbp+130h+lpFileName]; lpFileName
0x18008007f  call    cs:__imp_DeleteFileW
0x180080086  nop     dword ptr [rax+rax+00h]
0x18008008b  test    eax, eax
0x18008008d  jnz     loc_18008015C
0x180080093  call    cs:__imp_GetLastError
  ... truncated ...
```
