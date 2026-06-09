# UnmountOverlayImage

- ea: `0x180080a50`
- end: `0x180081129`
- name: `UnmountOverlayImage`
- size: `1753`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ea3c`
- `0x18001f5d4`
- `0x18001f660`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003e810`
- `0x180044bcc`
- `0x18006c360`
- `0x180073840`
- `0x18007db54`
- `0x18007e534`
- `0x18007e680`
- `0x18007e720`
- `0x18007ef14`
- `0x18007eff0`
- `0x18007f540`
- `0x180080a50`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180080d25`
- `KERNEL32!GetLastError` at `0x180080d3c`
- `KERNEL32!GetLastError` at `0x180080dd5`
- `KERNEL32!GetLastError` at `0x180080dec`
- `KERNEL32!GetLastError` at `0x180080ea7`
- `KERNEL32!GetLastError` at `0x180080efa`
- `KERNEL32!GetLastError` at `0x180080ff7`
- `KERNEL32!GetLastError` at `0x18008109a`
- `KERNEL32!GetLastError` at `0x180080d25`
- `KERNEL32!GetLastError` at `0x180080d3c`
- `KERNEL32!GetLastError` at `0x180080dd5`
- `KERNEL32!GetLastError` at `0x180080dec`
- `KERNEL32!GetLastError` at `0x180080ea7`
- `KERNEL32!GetLastError` at `0x180080efa`
- `KERNEL32!GetLastError` at `0x180080ff7`
- `KERNEL32!GetLastError` at `0x18008109a`
- `KERNEL32!DeleteFileW` at `0x180080fe3`
- `KERNEL32!DeleteFileW` at `0x180080fe3`
- `KERNEL32!CreateFileW` at `0x180080cf7`
- `KERNEL32!CreateFileW` at `0x180080cf7`
- `KERNEL32!ReadFile` at `0x180080dc5`
- `KERNEL32!ReadFile` at `0x180080e97`
- `KERNEL32!ReadFile` at `0x180080dc5`
- `KERNEL32!ReadFile` at `0x180080e97`
- `CIMFS!CimDismountImage` at `0x180080fa2`
- `CIMFS!CimDismountImage` at `0x180080fa2`

## string_xrefs

- `0x180080ae0`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080b47`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080bac`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080c2b`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080d58`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080e08`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080e43`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080ec4`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080f15`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080f69`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080fb2`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180081019`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x180080bbf`: `ImageRootPath.assign(ImageRoot)`
- `0x180080c3e`: `CimRootPath.assign(CimRoot)`
- `0x180081031`: `EnsureBOOL(::DeleteFileW(GuidFilePath.c_str()))`
- `0x180080ad0`: `RemoveFileSystemUnion`
- `0x180080af9`: `UnmountOverlayImage`
- `0x180080b5e`: `UnmountOverlayImage`
- `0x180080bc6`: `UnmountOverlayImage`
- `0x180080c45`: `UnmountOverlayImage`
- `0x180080d63`: `UnmountOverlayImage`
- `0x180080e13`: `UnmountOverlayImage`
- `0x180080e5a`: `UnmountOverlayImage`
- `0x180080ecf`: `UnmountOverlayImage`
- `0x180080f2f`: `UnmountOverlayImage`
- `0x180080f7e`: `UnmountOverlayImage`
- `0x180080fc7`: `UnmountOverlayImage`
- `0x180081025`: `UnmountOverlayImage`
- `0x180080eda`: `EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&UnionGuid), BytesToRead, &BytesRead, nullptr))`
- `0x180080e1e`: `EnsureBOOL(::ReadFile( GuidFile, reinterpret_cast<PVOID>(&CimGuid), BytesToRead, &BytesRead, nullptr))`
- `0x180080fd3`: `CimDismountImage(&CimGuid)`
- `0x180080f8a`: `pfnRemoveFileSystemUnion( &UnionGuid, UFS_CONFIG_OPTION_NONE, nullptr)`

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
LABEL_62:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, &Buffer, 0x10u, &NumberOfBytesRead, 0) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_62;
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
        goto LABEL_62;
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
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180081128LL);
      }
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
0x180080a50  mov     [rsp-8+arg_10], rbx
0x180080a55  mov     [rsp-8+arg_18], rsi
0x180080a5a  push    rbp
0x180080a5b  push    rdi
0x180080a5c  push    r14
0x180080a5e  lea     rbp, [rsp-120h]
0x180080a66  sub     rsp, 220h
0x180080a6d  mov     rax, cs:__security_cookie
0x180080a74  xor     rax, rsp
0x180080a77  mov     [rbp+130h+var_18], rax
0x180080a7e  xor     r14d, r14d
0x180080a81  mov     rdi, rdx
0x180080a84  mov     [rbp+130h+var_B8], r14d
0x180080a88  mov     rsi, rcx
0x180080a8b  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x180080a90  lea     rcx, [rbp+130h+var_48]; this
0x180080a97  mov     [rbp+130h+var_48], r14
0x180080a9e  mov     [rbp+130h+var_40], r14b
0x180080aa5  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x180080aaa  mov     ebx, eax
0x180080aac  test    eax, eax
0x180080aae  js      loc_18008108A
0x180080ab4  lea     rcx, [rsp+230h+var_1F0]
0x180080ab9  mov     [rsp+230h+var_1F0], r14
0x180080abe  mov     [rsp+230h+var_1C0], r14
0x180080ac3  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x180080ac8  mov     rdx, rax; HINSTANCE *
0x180080acb  lea     r8, [rsp+230h+var_1C0]; __int64 (**)(void)
0x180080ad0  lea     rcx, aRemovefilesyst; "RemoveFileSystemUnion"
0x180080ad7  call    ?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x180080adc  test    al, al
0x180080ade  jnz     short loc_180080B1E
0x180080ae0  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080ae7  mov     [rbp+130h+var_1A8], 317h
0x180080aef  mov     [rsp+230h+var_1B8], rcx
0x180080af4  lea     rdx, [rsp+230h+var_1B8]
0x180080af9  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080b00  mov     [rbp+130h+var_1A0], r14
0x180080b04  mov     [rbp+130h+var_1B0], rcx
0x180080b08  mov     r8d, 0C00000BBh
0x180080b0e  lea     rcx, [rbp+130h+var_B8]
0x180080b12  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180080b17  mov     ebx, eax
0x180080b19  jmp     loc_180081080
0x180080b1e  lea     rdx, [rbp+130h+var_B0]
0x180080b25  mov     [rbp+130h+var_B0], r14d
0x180080b2c  mov     rcx, rsi
0x180080b2f  call    IsOverlayImageMounted
0x180080b34  mov     ebx, eax
0x180080b36  test    eax, eax
0x180080b38  js      loc_180081080
0x180080b3e  cmp     [rbp+130h+var_B0], r14d
0x180080b45  jnz     short loc_180080B75
0x180080b47  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080b4e  mov     [rbp+130h+var_188], 31Eh
0x180080b56  mov     [rbp+130h+var_198], rcx
0x180080b5a  lea     rdx, [rbp+130h+var_198]
0x180080b5e  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080b65  mov     [rbp+130h+var_180], r14
0x180080b69  mov     [rbp+130h+var_190], rcx
0x180080b6d  mov     r8d, 0C000000Dh
0x180080b73  jmp     short loc_180080B0E
0x180080b75  lea     rax, [rbp+130h+var_98]
0x180080b7c  mov     [rbp+130h+var_98], r14w
0x180080b84  mov     [rbp+130h+var_A8], rax
0x180080b8b  lea     rcx, [rbp+130h+var_A8]
0x180080b92  lea     rax, [rbp+130h+var_98]
0x180080b99  mov     rdx, rsi
0x180080b9c  mov     [rbp+130h+var_A0], rax
0x180080ba3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180080ba8  test    al, al
0x180080baa  jnz     short loc_180080BEF
0x180080bac  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080bb3  mov     [rbp+130h+var_168], 322h
0x180080bbb  mov     [rbp+130h+var_178], rcx
0x180080bbf  lea     rax, aImagerootpathA; "ImageRootPath.assign(ImageRoot)"
0x180080bc6  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080bcd  mov     [rbp+130h+var_160], rax
0x180080bd1  mov     [rbp+130h+var_170], rcx
0x180080bd5  lea     rdx, [rbp+130h+var_178]
0x180080bd9  lea     rcx, [rbp+130h+var_B8]
0x180080bdd  mov     r8d, 0C0000017h
0x180080be3  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180080be8  mov     ebx, eax
0x180080bea  jmp     loc_180081074
0x180080bef  mov     [rbp+130h+var_58], r14w
0x180080bf7  lea     rax, [rbp+130h+var_58]
0x180080bfe  mov     [rbp+130h+var_68], rax
0x180080c05  lea     rax, [rbp+130h+var_58]
0x180080c0c  mov     [rbp+130h+var_60], rax
0x180080c13  test    rdi, rdi
0x180080c16  jz      short loc_180080C6E
0x180080c18  mov     rdx, rdi
0x180080c1b  lea     rcx, [rbp+130h+var_68]
0x180080c22  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180080c27  test    al, al
0x180080c29  jnz     short loc_180080C6E
0x180080c2b  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080c32  mov     [rbp+130h+var_148], 327h
0x180080c3a  mov     [rbp+130h+var_158], rcx
0x180080c3e  lea     rax, aCimrootpathAss; "CimRootPath.assign(CimRoot)"
0x180080c45  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080c4c  mov     [rbp+130h+var_140], rax
0x180080c50  mov     [rbp+130h+var_150], rcx
0x180080c54  lea     rdx, [rbp+130h+var_158]
0x180080c58  lea     rcx, [rbp+130h+var_B8]
0x180080c5c  mov     r8d, 0C0000017h
0x180080c62  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180080c67  mov     ebx, eax
0x180080c69  jmp     loc_180081068
0x180080c6e  lea     rax, [rbp+130h+var_78]
0x180080c75  mov     [rbp+130h+var_78], r14w
0x180080c7d  mov     [rbp+130h+lpFileName], rax
0x180080c84  lea     r8, [rbp+130h+lpFileName]
0x180080c8b  lea     rax, [rbp+130h+var_78]
0x180080c92  lea     rdx, [rbp+130h+var_68]
0x180080c99  mov     [rbp+130h+var_80], rax
0x180080ca0  lea     rcx, [rbp+130h+var_A8]
0x180080ca7  call    ?GetMountGuidsFilePath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; GetMountGuidsFilePath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180080cac  mov     ebx, eax
0x180080cae  test    eax, eax
0x180080cb0  js      loc_18008105C
0x180080cb6  mov     rcx, [rbp+130h+lpFileName]; lpFileName
0x180080cbd  xor     r9d, r9d; lpSecurityAttributes
0x180080cc0  xorps   xmm0, xmm0
0x180080cc3  mov     [rsp+230h+hTemplateFile], r14; hTemplateFile
0x180080cc8  xorps   xmm1, xmm1
0x180080ccb  mov     [rsp+230h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180080cd3  mov     edx, 0C0000000h; dwDesiredAccess
0x180080cd8  mov     [rsp+230h+hFile], r14
0x180080cdd  lea     r8d, [r9+1]; dwShareMode
0x180080ce1  mov     [rsp+230h+dwCreationDisposition], 3; dwCreationDisposition
0x180080ce9  movups  [rbp+130h+Buffer], xmm0
0x180080cf0  movups  [rbp+130h+var_38], xmm1
0x180080cf7  call    cs:__imp_CreateFileW
0x180080cfe  nop     dword ptr [rax+rax+00h]
0x180080d03  mov     rdx, rax
0x180080d06  lea     rcx, [rsp+230h+hFile]
0x180080d0b  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180080d10  mov     rbx, [rsp+230h+hFile]
0x180080d15  lea     rax, [rbx+1]
0x180080d19  test    rax, 0FFFFFFFFFFFFFFFEh
0x180080d1f  jnz     loc_180080DA6
0x180080d25  call    cs:__imp_GetLastError
0x180080d2c  nop     dword ptr [rax+rax+00h]
0x180080d31  test    eax, eax
0x180080d33  jnz     short loc_180080D3C
0x180080d35  mov     eax, 36FDh
0x180080d3a  jmp     short loc_180080D50
0x180080d3c  call    cs:__imp_GetLastError
0x180080d43  nop     dword ptr [rax+rax+00h]
0x180080d48  test    eax, eax
0x180080d4a  jz      loc_180081113
0x180080d50  mov     [rbp+130h+var_128], 33Bh
0x180080d58  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080d5f  mov     [rbp+130h+var_138], rcx
0x180080d63  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080d6a  mov     [rbp+130h+var_130], rcx
0x180080d6e  lea     rcx, aGuidfileIsvali; "GuidFile.IsValid()"
0x180080d75  mov     [rbp+130h+var_120], rcx
0x180080d79  test    eax, eax
0x180080d7b  jle     short loc_180080D85
0x180080d7d  movzx   eax, ax
0x180080d80  or      eax, 80070000h
0x180080d85  lea     rdx, [rbp+130h+var_138]
0x180080d89  mov     r8d, eax
0x180080d8c  lea     rcx, [rbp+130h+var_B8]
0x180080d90  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180080d95  lea     rcx, [rsp+230h+hFile]
0x180080d9a  mov     ebx, eax
0x180080d9c  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180080da1  jmp     loc_18008105C
0x180080da6  mov     edi, 10h
0x180080dab  mov     [rbp+130h+NumberOfBytesRead], r14d
0x180080daf  mov     r8d, edi; nNumberOfBytesToRead
0x180080db2  mov     qword ptr [rsp+230h+dwCreationDisposition], r14; lpOverlapped
0x180080db7  lea     r9, [rbp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180080dbb  mov     rcx, rbx; hFile
0x180080dbe  lea     rdx, [rbp+130h+Buffer]; lpBuffer
0x180080dc5  call    cs:__imp_ReadFile
0x180080dcc  nop     dword ptr [rax+rax+00h]
0x180080dd1  test    eax, eax
0x180080dd3  jnz     short loc_180080E3E
0x180080dd5  call    cs:__imp_GetLastError
0x180080ddc  nop     dword ptr [rax+rax+00h]
0x180080de1  test    eax, eax
0x180080de3  jnz     short loc_180080DEC
0x180080de5  mov     eax, 36FDh
0x180080dea  jmp     short loc_180080E00
0x180080dec  call    cs:__imp_GetLastError
0x180080df3  nop     dword ptr [rax+rax+00h]
0x180080df8  test    eax, eax
0x180080dfa  jz      loc_180081113
0x180080e00  mov     [rbp+130h+var_108], 345h
0x180080e08  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080e0f  mov     [rbp+130h+var_118], rcx
0x180080e13  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080e1a  mov     [rbp+130h+var_110], rcx
0x180080e1e  lea     rcx, aEnsureboolRead_0; "EnsureBOOL(::ReadFile( GuidFile, reinte"...
0x180080e25  mov     [rbp+130h+var_100], rcx
0x180080e29  test    eax, eax
0x180080e2b  jle     short loc_180080E35
0x180080e2d  movzx   eax, ax
0x180080e30  or      eax, 80070000h
0x180080e35  lea     rdx, [rbp+130h+var_118]
0x180080e39  jmp     loc_180080D89
0x180080e3e  cmp     [rbp+130h+NumberOfBytesRead], edi
0x180080e41  jz      short loc_180080E7D
0x180080e43  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080e4a  mov     [rbp+130h+var_E8], 348h
0x180080e52  mov     [rbp+130h+var_F8], rcx
0x180080e56  lea     rdx, [rbp+130h+var_F8]
0x180080e5a  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080e61  mov     [rbp+130h+var_E0], r14
0x180080e65  mov     [rbp+130h+var_F0], rcx
0x180080e69  mov     r8d, 0C0000102h
0x180080e6f  lea     rcx, [rbp+130h+var_B8]
0x180080e73  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180080e78  jmp     loc_180080D95
0x180080e7d  lea     r9, [rbp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180080e81  mov     [rbp+130h+NumberOfBytesRead], r14d
0x180080e85  mov     r8d, edi; nNumberOfBytesToRead
0x180080e88  mov     qword ptr [rsp+230h+dwCreationDisposition], r14; lpOverlapped
0x180080e8d  lea     rdx, [rbp+130h+var_38]; lpBuffer
0x180080e94  mov     rcx, rbx; hFile
0x180080e97  call    cs:__imp_ReadFile
0x180080e9e  nop     dword ptr [rax+rax+00h]
0x180080ea3  test    eax, eax
0x180080ea5  jnz     short loc_180080F10
0x180080ea7  call    cs:__imp_GetLastError
0x180080eae  nop     dword ptr [rax+rax+00h]
0x180080eb3  test    eax, eax
0x180080eb5  jnz     short loc_180080EFA
0x180080eb7  mov     eax, 36FDh
0x180080ebc  mov     [rbp+130h+var_C8], 353h
0x180080ec4  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080ecb  mov     [rbp+130h+var_D8], rcx
0x180080ecf  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080ed6  mov     [rbp+130h+var_D0], rcx
0x180080eda  lea     rcx, aEnsureboolRead; "EnsureBOOL(::ReadFile( GuidFile, reinte"...
0x180080ee1  mov     [rbp+130h+var_C0], rcx
0x180080ee5  test    eax, eax
0x180080ee7  jle     short loc_180080EF1
0x180080ee9  movzx   eax, ax
0x180080eec  or      eax, 80070000h
0x180080ef1  lea     rdx, [rbp+130h+var_D8]
0x180080ef5  jmp     loc_180080D89
0x180080efa  call    cs:__imp_GetLastError
0x180080f01  nop     dword ptr [rax+rax+00h]
0x180080f06  test    eax, eax
0x180080f08  jz      loc_180081113
0x180080f0e  jmp     short loc_180080EBC
0x180080f10  cmp     [rbp+130h+NumberOfBytesRead], edi
0x180080f13  jz      short loc_180080F45
0x180080f15  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080f1c  mov     [rsp+230h+var_1D0], 356h
0x180080f25  mov     [rsp+230h+var_1E0], rcx
0x180080f2a  lea     rdx, [rsp+230h+var_1E0]
0x180080f2f  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080f36  mov     [rsp+230h+var_1C8], r14
0x180080f3b  mov     [rsp+230h+var_1D8], rcx
0x180080f40  jmp     loc_180080E69
0x180080f45  lea     rcx, [rsp+230h+hFile]
0x180080f4a  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180080f4f  mov     rax, [rsp+230h+var_1C0]
0x180080f54  lea     rcx, [rbp+130h+var_38]
0x180080f5b  xor     r8d, r8d
0x180080f5e  xor     edx, edx
0x180080f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f65  test    eax, eax
0x180080f67  jns     short loc_180080F9B
0x180080f69  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080f70  mov     [rsp+230h+var_1D0], 35Eh
0x180080f79  mov     [rsp+230h+var_1E0], rcx
0x180080f7e  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080f85  mov     [rsp+230h+var_1D8], rcx
0x180080f8a  lea     rcx, aPfnremovefiles; "pfnRemoveFileSystemUnion( &UnionGuid, U"...
0x180080f91  mov     [rsp+230h+var_1C8], rcx
0x180080f96  jmp     loc_180081049
0x180080f9b  lea     rcx, [rbp+130h+Buffer]
0x180080fa2  call    cs:__imp_CimDismountImage
0x180080fa9  nop     dword ptr [rax+rax+00h]
0x180080fae  test    eax, eax
0x180080fb0  jns     short loc_180080FDC
0x180080fb2  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x180080fb9  mov     [rsp+230h+var_1D0], 360h
0x180080fc2  mov     [rsp+230h+var_1E0], rcx
0x180080fc7  lea     rcx, aUnmountoverlay_0; "UnmountOverlayImage"
0x180080fce  mov     [rsp+230h+var_1D8], rcx
0x180080fd3  lea     rcx, aCimdismountima_0; "CimDismountImage(&CimGuid)"
0x180080fda  jmp     short loc_180080F91
0x180080fdc  mov     rcx, [rbp+130h+lpFileName]; lpFileName
0x180080fe3  call    cs:__imp_DeleteFileW
0x180080fea  nop     dword ptr [rax+rax+00h]
0x180080fef  test    eax, eax
0x180080ff1  jnz     loc_1800810AF
0x180080ff7  call    cs:__imp_GetLastError
0x180080ffe  nop     dword ptr [rax+rax+00h]
0x180081003  test    eax, eax
0x180081005  jnz     loc_18008109A
  ... truncated ...
```
