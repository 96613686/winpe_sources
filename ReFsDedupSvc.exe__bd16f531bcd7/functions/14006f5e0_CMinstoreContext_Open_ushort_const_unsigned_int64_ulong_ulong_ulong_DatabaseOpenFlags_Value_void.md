# CMinstoreContext::Open(ushort const *,unsigned __int64,ulong,ulong,ulong,DatabaseOpenFlags::Value,void * *)

- ea: `0x14006f5e0`
- end: `0x140070380`
- name: `?Open@CMinstoreContext@@UEAAKPEBG_KKKKW4Value@DatabaseOpenFlags@@PEAPEAX@Z`
- size: `3488`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned __int64, unsigned int, char, unsigned int, char, _QWORD *)`
- caller_count: `0`
- callee_count: `49`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004870`
- `0x140004c6c`
- `0x1400057f8`
- `0x14000dea0`
- `0x1400150bc`
- `0x1400172f0`
- `0x140019600`
- `0x14001983c`
- `0x140023d40`
- `0x140023d88`
- `0x140041dc4`
- `0x140058450`
- `0x1400635dc`
- `0x140063bbc`
- `0x140066150`
- `0x1400663e0`
- `0x140066468`
- `0x1400667a0`
- `0x140066b5c`
- `0x140067e70`
- `0x14006968c`
- `0x140069e2c`
- `0x140069f4c`
- `0x140069ff0`
- `0x14006a178`
- `0x14006a430`
- `0x14006aec8`
- `0x14006afa0`
- `0x14006b098`
- `0x14006b53c`
- `0x14006b57c`
- `0x14006b770`
- `0x14006b7c8`
- `0x14006c08c`
- `0x14006c0b4`
- `0x14006c74c`
- `0x14006cc1c`
- `0x14006cc78`
- `0x14006e9f0`
- `0x14006ebcc`
- `0x14006ed1c`
- `0x14006eea0`
- `0x14006f5e0`
- `0x14007058c`
- `0x1400709d0`
- `0x14007cbe8`
- `0x14008496c`
- `0x1400872d0`
- `0x140087610`

## import_xrefs

- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006f99e`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006fb65`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006fed5`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006f99e`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006fb65`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x14006fed5`
- `ntdll!NtCreateFile` at `0x14006f98c`
- `ntdll!NtCreateFile` at `0x14006fb53`
- `ntdll!NtCreateFile` at `0x14006fd36`
- `ntdll!NtCreateFile` at `0x14006f98c`
- `ntdll!NtCreateFile` at `0x14006fb53`
- `ntdll!NtCreateFile` at `0x14006fd36`
- `ntdll!RtlNtStatusToDosError` at `0x14006fc04`
- `ntdll!RtlNtStatusToDosError` at `0x14006fea4`
- `ntdll!RtlNtStatusToDosError` at `0x14006fc04`
- `ntdll!RtlNtStatusToDosError` at `0x14006fea4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14006f821`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14006f821`
- `ntdll!RtlFreeUnicodeString` at `0x14006f854`
- `ntdll!RtlFreeUnicodeString` at `0x14006f854`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006fbe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006fbe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fa92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fa92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006fee1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14006f699`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14006f699`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14006f6f4`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14006f6f4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14006fad5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14006fad5`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x14006f6ba`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x14006f6ba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fa25`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fa82`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fdaf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fa25`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fa82`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006fdaf`

## string_xrefs

- `0x14006f9c2`: `Couldn't create hash index file %s, error: 0x%x\n`
- `0x14006fb89`: `Couldn't open hash index file %s, error: 0x%x\n`
- `0x14006fec6`: `Couldn't set read-from-copy, error = 0x%x\n`
- `0x14006fef9`: `Couldn't open read-copy handle to hash index file %s, error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall CMinstoreContext::Open(
        __int64 a1,
        const WCHAR *a2,
        unsigned __int64 a3,
        unsigned int a4,
        char a5,
        unsigned int a6,
        char a7,
        _QWORD *a8)
{
  unsigned __int64 v8; // rsi
  _QWORD *v12; // rbx
  ULONG MdsPathFromCsv; // ebx
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  const WCHAR *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  ULONG CreateOptions; // ecx
  int v27; // eax
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  DWORD v30; // eax
  const wchar_t *v31; // rdx
  int v32; // edx
  int v33; // ecx
  int v34; // eax
  void *v35; // rdx
  __int64 FileSizeByHandle; // rax
  NTSTATUS v37; // eax
  __int64 *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  void *v41; // rdx
  void *v42; // rdx
  __int64 v43; // rbx
  unsigned int FileDataCopy; // eax
  __int64 v45; // rdx
  unsigned int v46; // ebx
  HANDLE *v47; // rsi
  HANDLE v48; // rdx
  int v49; // r15d
  unsigned int v50; // r15d
  unsigned __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned __int64 v54; // rax
  _QWORD *v55; // rsi
  unsigned __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // r9
  unsigned __int64 v59; // rcx
  __int64 v60; // rax
  unsigned int v61; // edx
  void *v62; // rax
  void *v63; // rax
  __int64 v64; // rax
  unsigned __int64 v65; // rdx
  __int64 v66; // r8
  unsigned __int64 v67; // rcx
  CHashIndexCmsTableSet *v68; // rbx
  unsigned __int64 v69; // rdx
  __int64 v70; // r8
  unsigned __int64 v71; // rcx
  CHashIndexCmsTableSet *v72; // rbx
  __int64 v73; // rax
  int EaBuffer; // [rsp+48h] [rbp-C8h]
  ULONG EaLength; // [rsp+50h] [rbp-C0h]
  DWORD LastError; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v78; // [rsp+94h] [rbp-7Ch] BYREF
  __int64 v79; // [rsp+98h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-70h] BYREF
  int v81; // [rsp+A8h] [rbp-68h] BYREF
  DWORD v82[2]; // [rsp+B0h] [rbp-60h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp-58h] BYREF
  NTSTATUS Status[2]; // [rsp+C0h] [rbp-50h] BYREF
  DWORD BytesPerSector; // [rsp+C8h] [rbp-48h] BYREF
  DWORD SectorsPerCluster; // [rsp+CCh] [rbp-44h] BYREF
  __int64 FileInformation; // [rsp+D0h] [rbp-40h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+D8h] [rbp-38h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+E8h] [rbp-28h] BYREF
  _QWORD v90[3]; // [rsp+F0h] [rbp-20h] BYREF
  char v91; // [rsp+108h] [rbp-8h]
  _QWORD *v92; // [rsp+110h] [rbp+0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+118h] [rbp+8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+130h] [rbp+20h] BYREF
  __int128 v96; // [rsp+160h] [rbp+50h] BYREF
  __m128i si128; // [rsp+170h] [rbp+60h]
  _BYTE v98[16]; // [rsp+180h] [rbp+70h] BYREF
  __int64 v99; // [rsp+190h] [rbp+80h]
  _BYTE v100[32]; // [rsp+1A0h] [rbp+90h] BYREF
  void *v101; // [rsp+1C0h] [rbp+B0h] BYREF
  unsigned int *v102; // [rsp+1C8h] [rbp+B8h]
  DWORD *p_LastError; // [rsp+1D0h] [rbp+C0h]
  char *v104; // [rsp+1D8h] [rbp+C8h]
  unsigned int *v105; // [rsp+1E0h] [rbp+D0h]
  __int128 v106; // [rsp+1E8h] [rbp+D8h] BYREF
  __int64 v107; // [rsp+1F8h] [rbp+E8h]
  __int128 InBuffer; // [rsp+208h] [rbp+F8h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+220h] [rbp+110h] BYREF

  v8 = a4;
  *(_QWORD *)v82 = a2;
  v12 = a8;
  v92 = a8;
  FileInformation = 0;
  LastError = 0;
  v81 = 0;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  FileHandle = (void *)-1LL;
  v79 = 0;
  *v12 = -1;
  v90[0] = &v92;
  v90[1] = &LastError;
  v90[2] = &FileHandle;
  v91 = 1;
  if ( GetVolumePathNameW(a2, szVolumePathName, 0x104u)
    && GetDiskFreeSpaceExW(szVolumePathName, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes)
    && GetDiskFreeSpaceW(szVolumePathName, &SectorsPerCluster, &BytesPerSector, 0, 0) )
  {
    v14 = a3 / v8;
    v15 = 0x80000000LL;
    if ( 2560 * (a3 / v8) / 0x64 > 0x80000000 )
      v15 = 2560 * (a3 / v8) / 0x64;
    *(_QWORD *)(a1 + 144) = (((a3 / v8) << 8) + 4095 + v15) & 0xFFFFFFFFFFFFF000uLL;
    std::wstring::wstring(&v101, a2);
    LOBYTE(v16) = 1;
    DedupUtil::GetVolumeGuid(v98, &v101, v16);
    std::wstring::_Tidy_deallocate(&v101);
    if ( !v99 )
    {
      LastError = 87;
      DedupUtil::Print<unsigned short const * &,unsigned long &>(v18, v17, v82, &LastError);
      MdsPathFromCsv = LastError;
LABEL_111:
      std::wstring::_Tidy_deallocate(v98);
      goto LABEL_112;
    }
    v96 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v96) = 0;
    NtPathName = 0;
    if ( (unsigned __int8)DedupUtil::IsCsvVolume(v98) )
    {
      MdsPathFromCsv = DedupUtil::GetMdsPathFromCsv(v98, &v96);
      LastError = MdsPathFromCsv;
      if ( MdsPathFromCsv )
      {
LABEL_110:
        std::wstring::_Tidy_deallocate(&v96);
        goto LABEL_111;
      }
      std::wstring::_Append<unsigned short>(&v96, L"\\", 1);
    }
    else
    {
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v98);
      if ( !RtlDosPathNameToNtPathName_U(v19, &NtPathName, 0, 0) )
      {
        MdsPathFromCsv = 3;
        LastError = 3;
        std::wstring::_Tidy_deallocate(&v96);
        std::wstring::_Tidy_deallocate(v98);
        v91 = 0;
        goto LABEL_115;
      }
      v20 = -1;
      do
        ++v20;
      while ( NtPathName.Buffer[v20] );
      std::wstring::_Assign<unsigned short>(&v96, NtPathName.Buffer);
      RtlFreeUnicodeString(&NtPathName);
    }
    std::wstring::wstring(v100, a2);
    v21 = *(_QWORD *)(std::wstring::wstring(&v106, v98) + 16);
    v22 = std::wstring::find(v100, v98);
    v23 = std::wstring::substr(v100, &v101, v21 + v22, -1);
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    std::wstring::_Append<unsigned short>(&v96, v24, v25);
    std::wstring::_Tidy_deallocate(&v101);
    std::wstring::_Tidy_deallocate(&v106);
    NtPathName.MaximumLength = 2 * si128.m128i_i16[0];
    NtPathName.Length = 2 * si128.m128i_i16[0];
    NtPathName.Buffer = (PWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v96);
    IoStatusBlock = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &NtPathName;
    v81 = a7 & 4;
    CreateOptions = v81 != 0 ? 18504 : 18496;
    v78 = ((a7 & 1) == 0) + 1;
    if ( ((((a7 & 1) == 0) + 1) & 1) != 0 )
    {
      v27 = NtCreateFile(&FileHandle, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 6u, 1u, 5u, CreateOptions, 0, 0);
      if ( v27 < 0 )
      {
        RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v27);
        LastError = GetLastError();
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v96);
        v29 = L"Couldn't create hash index file %s, error: 0x%x\n";
LABEL_19:
        v79 = v28;
        DedupUtil::Print<unsigned short const *,unsigned long &>(6, v29, &v79, &LastError);
LABEL_108:
        MdsPathFromCsv = LastError;
        goto LABEL_109;
      }
      BytesReturned = 0;
      InBuffer = 0;
      BYTE8(InBuffer) = 1;
      if ( !DeviceIoControl(FileHandle, 0x90380u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      {
        Status[0] = GetLastError();
        DedupUtil::Print<unsigned long>(6, L"Couldn't set hash index file integrity, error = 0x%x\n", Status);
      }
      BytesReturned = 0;
      if ( !DeviceIoControl(FileHandle, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0) )
      {
        v30 = GetLastError();
        v31 = L"Couldn't set hash index file sparse, error = 0x%x\n";
LABEL_24:
        LastError = v30;
        DedupUtil::Print<unsigned long &>(6, v31, &LastError);
        goto LABEL_108;
      }
      FileInformation = *(_QWORD *)(a1 + 144);
      if ( !SetFileInformationByHandle(FileHandle, FileEndOfFileInfo, &FileInformation, 8u) )
      {
        LastError = GetLastError();
        DedupUtil::Print<__int64 &,unsigned __int64 &,unsigned long &>(
          v33,
          v32,
          (unsigned int)&FileInformation,
          (unsigned int)&TotalNumberOfFreeBytes,
          (__int64)&LastError);
        goto LABEL_108;
      }
      goto LABEL_35;
    }
    if ( (a7 & 2) != 0 )
      CreateOptions |= 0x1000u;
    v34 = NtCreateFile(&FileHandle, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 6u, 1u, 1u, CreateOptions, 0, 0);
    if ( v34 < 0 )
    {
      RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v34);
      LastError = GetLastError();
      v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v96);
      v29 = L"Couldn't open hash index file %s, error: 0x%x\n";
      goto LABEL_19;
    }
    FileSizeByHandle = DedupUtil::GetFileSizeByHandle((DedupUtil *)FileHandle, v35);
    if ( FileSizeByHandle < 0 || FileSizeByHandle == *(_QWORD *)(a1 + 144) )
    {
LABEL_35:
      AcquireSRWLockExclusive(&g_UmeInitLock);
      *(_QWORD *)v82 = &g_UmeInitLock;
      if ( !g_UmeInitialized )
      {
        v37 = MsInitializeUserModeLibrary();
        if ( v37 < 0 )
        {
          MdsPathFromCsv = RtlNtStatusToDosError(v37);
          LastError = MdsPathFromCsv;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v82);
LABEL_109:
          std::wstring::_Tidy_deallocate(v100);
          goto LABEL_110;
        }
        g_UmeInitialized = 1;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v82);
      v38 = (__int64 *)utl::make_unique<MS_USERMODE_DEVICE_CONTEXT,,0>(v82);
      v39 = *v38;
      *v38 = 0;
      v40 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v39;
      if ( v40 )
        utl::default_delete<MS_USERMODE_DEVICE_CONTEXT>::operator()();
      utl::unique_ptr<MS_USERMODE_DEVICE_CONTEXT,utl::default_delete<MS_USERMODE_DEVICE_CONTEXT>>::~unique_ptr<MS_USERMODE_DEVICE_CONTEXT,utl::default_delete<MS_USERMODE_DEVICE_CONTEXT>>(v82);
      if ( !*(_QWORD *)(a1 + 24) )
        goto LABEL_113;
      LastError = DedupUtil::SetNoScrubOnHandle(FileHandle, v41);
      if ( LastError )
      {
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v96);
        v29 = L"Couldn't set noscrub on hash index file %s, error: 0x%x\n";
        goto LABEL_19;
      }
      **(_QWORD **)(a1 + 24) = FileHandle;
      v43 = *(_QWORD *)(a1 + 24);
      FileDataCopy = DedupUtil::GetFileDataCopy((DedupUtil *)FileHandle, v42);
      if ( !(unsigned __int8)utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::_Resize<,0>(
                               v43 + 32,
                               FileDataCopy) )
      {
LABEL_113:
        MdsPathFromCsv = 8;
        LastError = 8;
        goto LABEL_109;
      }
      v45 = *(_QWORD *)(a1 + 24);
      if ( (__int64)(*(_QWORD *)(v45 + 40) - *(_QWORD *)(v45 + 32)) >> 3 )
      {
        v46 = 0;
        while ( 1 )
        {
          v47 = (HANDLE *)(*(_QWORD *)(v45 + 32) + 8LL * v46);
          v101 = 0;
          v102 = (unsigned int *)v47;
          v48 = *v47;
          *v47 = 0;
          tlx::file_handle_traits::operator()(v46, v48);
          v49 = NtCreateFile(&v101, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 6u, 7u, 1u, 0x4848u, 0, 0);
          utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(&v101);
          if ( v49 < 0 )
            break;
          v106 = 0;
          v82[0] = 0;
          LODWORD(v106) = v46;
          v107 = 128;
          if ( !DeviceIoControl(*v47, 0x900FCu, &v106, 0x18u, 0, 0, v82, 0) )
          {
            v30 = GetLastError();
            v31 = L"Couldn't set read-from-copy, error = 0x%x\n";
            goto LABEL_24;
          }
          ++v46;
          v45 = *(_QWORD *)(a1 + 24);
          if ( v46 >= (unsigned __int64)((__int64)(*(_QWORD *)(v45 + 40) - *(_QWORD *)(v45 + 32)) >> 3) )
            goto LABEL_50;
        }
        RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v49);
        LastError = GetLastError();
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v96);
        v29 = L"Couldn't open read-copy handle to hash index file %s, error: 0x%x\n";
        goto LABEL_19;
      }
LABEL_50:
      if ( (int)MsUmeRegisterDeviceContext(v45) < 0 )
        goto LABEL_108;
      _BitScanForward(&v50, 0x1000u);
      v51 = (*(_QWORD *)(a1 + 144) >> v50) & 0xFFFFFFFFFFFFC000uLL;
      *(_QWORD *)(a1 + 152) = v51;
      Status[0] = MsInitializeVolume(
                    *(_QWORD *)(a1 + 24),
                    (unsigned __int64)qword_1402230B0 & -(__int64)((v78 & 1) != 0),
                    v51,
                    BytesPerSector,
                    v50,
                    v78,
                    (v78 & 1) != 0 ? 138412033 : 134348801,
                    (unsigned __int64)qword_1402230B0 & -(__int64)((v78 & 1) != 0),
                    (unsigned __int8)(v78 & 1) << 16,
                    EaBuffer,
                    EaLength,
                    3,
                    14,
                    (__int64)&v79);
      if ( Status[0] < 0 )
      {
        v81 = v78;
        DedupUtil::Print<unsigned long,long &>(v53, v52, &v81, Status);
        MdsPathFromCsv = RtlNtStatusToDosError(Status[0]);
        LastError = MdsPathFromCsv;
        goto LABEL_109;
      }
      *(_QWORD *)(a1 + 8) = v79;
      LastError = CMinstoreContext::InitializeIndexSchemas((CMinstoreContext *)a1);
      if ( LastError )
      {
        DedupUtil::Print<unsigned long &>(6, L"Failed to register hash index schema, error = 0x%x\n", &LastError);
        goto LABEL_108;
      }
      LastError = CMinstoreContext::InitializeIdTable(a1, v78, a6);
      if ( LastError )
      {
        DedupUtil::Print<unsigned long &>(6, L"Failed to initialize ID table, error = 0x%x\n", &LastError);
        goto LABEL_108;
      }
      v54 = v14 / a6;
      if ( !(_DWORD)v54 )
        v54 = 1;
      *(_DWORD *)(a1 + 64) = v54;
      v55 = (_QWORD *)(a1 + 72);
      if ( (v78 & 1) != 0 )
      {
        v56 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 80) - *(_QWORD *)(a1 + 72)) >> 4);
        if ( (unsigned int)v54 >= v56 )
        {
          if ( (unsigned int)v54 <= v56 )
            goto LABEL_78;
          if ( (unsigned int)v54 > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 88) - *(_QWORD *)(a1 + 72)) >> 4) )
          {
            std::vector<SIdTableData>::_Resize_reallocate<std::_Value_init_tag>(a1 + 72);
            goto LABEL_78;
          }
          v57 = std::_Uninitialized_value_construct_n<std::allocator<SIdTableData>>(
                  *(_QWORD *)(a1 + 80),
                  (unsigned int)v54 - v56,
                  a1 + 72);
        }
        else
        {
          v57 = *v55 + 48 * v54;
        }
        *(_QWORD *)(a1 + 80) = v57;
LABEL_78:
        if ( *(_DWORD *)(a1 + 64) >= 0x64u )
          v61 = *(_DWORD *)(a1 + 64) / 0x64u;
        else
          v61 = 1;
        *(_DWORD *)(a1 + 68) = v61;
        v62 = operator new(0x138u, (const struct std::nothrow_t *)std::nothrow);
        v79 = (__int64)v62;
        if ( v62 )
          v62 = (void *)CCandidateCmsTable::CCandidateCmsTable(
                          v62,
                          *(_QWORD *)(a1 + 8),
                          v50,
                          v78,
                          0,
                          *(unsigned int *)(a1 + 68));
        *(_QWORD *)(a1 + 192) = v62;
        if ( v62 )
        {
          v63 = operator new(0x138u, (const struct std::nothrow_t *)std::nothrow);
          v79 = (__int64)v63;
          v64 = v63
              ? CCandidateCmsTable::CCandidateCmsTable(
                  v63,
                  *(_QWORD *)(a1 + 8),
                  v50,
                  v78,
                  1,
                  *(unsigned int *)(a1 + 68))
              : 0LL;
          *(_QWORD *)(a1 + 200) = v64;
          if ( v64 )
          {
            v65 = *(unsigned int *)(a1 + 64);
            v66 = *(_QWORD *)(a1 + 96);
            v67 = 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 104) - v66) >> 3);
            if ( v65 >= v67 )
            {
              if ( v65 > v67 )
              {
                if ( v65 <= 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 112) - v66) >> 3) )
                  *(_QWORD *)(a1 + 104) = std::_Uninitialized_value_construct_n<std::allocator<CHashIndexCmsTableSet>>(
                                            *(_QWORD *)(a1 + 104),
                                            v65 - v67,
                                            a1 + 96);
                else
                  std::vector<CHashIndexCmsTableSet>::_Resize_reallocate<std::_Value_init_tag>(a1 + 96);
              }
            }
            else
            {
              v68 = (CHashIndexCmsTableSet *)(v66 + 40 * v65);
              std::_Destroy_range<std::allocator<CHashIndexCmsTableSet>>(v68);
              *(_QWORD *)(a1 + 104) = v68;
            }
            v69 = *(unsigned int *)(a1 + 64);
            v70 = *(_QWORD *)(a1 + 120);
            v71 = 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 128) - v70) >> 3);
            if ( v69 >= v71 )
            {
              if ( v69 > v71 )
              {
                if ( v69 <= 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 136) - v70) >> 3) )
                  *(_QWORD *)(a1 + 128) = std::_Uninitialized_value_construct_n<std::allocator<CHashIndexCmsTableSet>>(
                                            *(_QWORD *)(a1 + 128),
                                            v69 - v71,
                                            a1 + 120);
                else
                  std::vector<CHashIndexCmsTableSet>::_Resize_reallocate<std::_Value_init_tag>(a1 + 120);
              }
            }
            else
            {
              v72 = (CHashIndexCmsTableSet *)(v70 + 40 * v69);
              std::_Destroy_range<std::allocator<CHashIndexCmsTableSet>>(v72);
              *(_QWORD *)(a1 + 128) = v72;
            }
            v101 = (void *)a1;
            v102 = &v78;
            p_LastError = &LastError;
            v104 = &a5;
            v105 = &a6;
            v79 = *(_QWORD *)(a1 + 80);
            *(_QWORD *)Status = *v55;
            if ( (unsigned __int8)DedupUtil::Concurrency::parallel_all_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_SIdTableData_______CMinstoreContext::Open_::_1_::_lambda_3___(
                                    Status,
                                    &v79,
                                    &v101) )
            {
              if ( (v78 & 1) != 0 && (LastError = CMinstoreContext::PopulateIdTable((CMinstoreContext *)a1)) != 0 )
              {
                DedupUtil::Print<unsigned long &>(
                  6,
                  L"Failed to store table ID tuple in ID table, error = 0x%x\n",
                  &LastError);
              }
              else
              {
                LastError = CMinstoreContext::InitializeScrubContextTable((CMinstoreContext *)a1);
                if ( LastError )
                {
                  DedupUtil::Print<unsigned long &>(
                    5,
                    L"Failed to initialize scrub context table, error = 0x%x\n",
                    &LastError);
                  LastError = 0;
                }
                *(_BYTE *)(a1 + 16) = v81 == 0;
                byte_14022007F = 1;
                v73 = std::wstring::wstring(&v101, a2);
                std::wstring::operator=(a1 + 160, v73);
                std::wstring::_Tidy_deallocate(&v101);
                if ( (v78 & 1) == 0 )
                  CMinstoreContext::RegisterPerfmonCounters((CMinstoreContext *)a1);
              }
            }
            goto LABEL_108;
          }
        }
        goto LABEL_113;
      }
      v58 = *(_QWORD *)(a1 + 80);
      if ( *v55 == v58 )
      {
        v59 = 0xAAAAAAAAAAAAAAABuLL * ((v58 - *v55) >> 4);
        if ( (unsigned int)v54 >= v59 )
        {
          if ( (unsigned int)v54 <= v59 )
            goto LABEL_77;
          if ( (unsigned int)v54 > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 88) - *(_QWORD *)(a1 + 72)) >> 4) )
          {
            std::vector<SIdTableData>::_Resize_reallocate<std::_Value_init_tag>(a1 + 72);
            goto LABEL_77;
          }
          v60 = std::_Uninitialized_value_construct_n<std::allocator<SIdTableData>>(
                  *(_QWORD *)(a1 + 80),
                  (unsigned int)v54 - v59,
                  a1 + 72);
        }
        else
        {
          v60 = *v55 + 48 * v54;
        }
        *(_QWORD *)(a1 + 80) = v60;
      }
LABEL_77:
      MdsPathFromCsv = CMinstoreContext::InitializeTableIdMap((CMinstoreContext *)a1);
      LastError = MdsPathFromCsv;
      if ( MdsPathFromCsv )
        goto LABEL_109;
      goto LABEL_78;
    }
    std::wstring::_Tidy_deallocate(v100);
    std::wstring::_Tidy_deallocate(&v96);
    std::wstring::_Tidy_deallocate(v98);
    MdsPathFromCsv = 1462;
  }
  else
  {
    MdsPathFromCsv = GetLastError();
  }
LABEL_112:
  v91 = 0;
LABEL_115:
  CMinstoreContext::Open_::_2_::_lambda_1_::operator()(v90);
  return MdsPathFromCsv;
}

```

## disassembly

```asm
0x14006f5e0  mov     [rsp-8+arg_10], rbx
0x14006f5e5  push    rbp
0x14006f5e6  push    rsi
0x14006f5e7  push    rdi
0x14006f5e8  push    r12
0x14006f5ea  push    r13
0x14006f5ec  push    r14
0x14006f5ee  push    r15
0x14006f5f0  lea     rbp, [rsp-330h]
0x14006f5f8  sub     rsp, 440h
0x14006f5ff  mov     rax, cs:__security_cookie
0x14006f606  xor     rax, rsp
0x14006f609  mov     [rbp+360h+var_40], rax
0x14006f610  mov     esi, r9d
0x14006f613  mov     r14, r8
0x14006f616  mov     r12, rdx
0x14006f619  mov     rdi, rcx
0x14006f61c  mov     qword ptr [rbp+360h+var_3C0], rdx
0x14006f620  mov     rbx, [rbp+360h+arg_38]
0x14006f627  mov     [rbp+360h+var_360], rbx
0x14006f62b  xor     r15d, r15d
0x14006f62e  mov     [rbp+360h+FileInformation], r15
0x14006f632  mov     [rbp+360h+var_3E0], r15d
0x14006f636  mov     [rbp+360h+var_3C8], r15d
0x14006f63a  mov     [rbp+360h+SectorsPerCluster], r15d
0x14006f63e  mov     [rbp+360h+BytesPerSector], r15d
0x14006f642  mov     qword ptr [rbp+360h+TotalNumberOfBytes], r15
0x14006f646  mov     qword ptr [rbp+360h+TotalNumberOfFreeBytes], r15
0x14006f64a  xor     edx, edx; Val
0x14006f64c  mov     r8d, 208h; Size
0x14006f652  lea     rcx, [rbp+360h+szVolumePathName]; void *
0x14006f659  call    memset_0
0x14006f65e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006f662  mov     [rbp+360h+FileHandle], rax
0x14006f666  mov     [rbp+360h+var_3D8], r15
0x14006f66a  mov     [rbx], rax
0x14006f66d  lea     rax, [rbp+360h+var_360]
0x14006f671  mov     [rbp+360h+var_380], rax
0x14006f675  lea     rax, [rbp+360h+var_3E0]
0x14006f679  mov     [rbp+360h+var_378], rax
0x14006f67d  lea     rax, [rbp+360h+FileHandle]
0x14006f681  mov     [rbp+360h+var_370], rax
0x14006f685  mov     [rbp+360h+var_368], 1
0x14006f689  mov     r8d, 104h; cchBufferLength
0x14006f68f  lea     rdx, [rbp+360h+szVolumePathName]; lpszVolumePathName
0x14006f696  mov     rcx, r12; lpszFileName
0x14006f699  call    cs:__imp_GetVolumePathNameW
0x14006f6a0  nop     dword ptr [rax+rax+00h]
0x14006f6a5  test    eax, eax
0x14006f6a7  jz      short loc_14006F6CA
0x14006f6a9  lea     r9, [rbp+360h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x14006f6ad  lea     r8, [rbp+360h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x14006f6b1  xor     edx, edx; lpFreeBytesAvailableToCaller
0x14006f6b3  lea     rcx, [rbp+360h+szVolumePathName]; lpDirectoryName
0x14006f6ba  call    cs:__imp_GetDiskFreeSpaceExW
0x14006f6c1  nop     dword ptr [rax+rax+00h]
0x14006f6c6  test    eax, eax
0x14006f6c8  jnz     short loc_14006F6DD
0x14006f6ca  call    cs:__imp_GetLastError
0x14006f6d1  nop     dword ptr [rax+rax+00h]
0x14006f6d6  mov     ebx, eax
0x14006f6d8  jmp     loc_14007031A
0x14006f6dd  mov     [rsp+470h+lpTotalNumberOfClusters], r15; lpTotalNumberOfClusters
0x14006f6e2  xor     r9d, r9d; lpNumberOfFreeClusters
0x14006f6e5  lea     r8, [rbp+360h+BytesPerSector]; lpBytesPerSector
0x14006f6e9  lea     rdx, [rbp+360h+SectorsPerCluster]; lpSectorsPerCluster
0x14006f6ed  lea     rcx, [rbp+360h+szVolumePathName]; lpRootPathName
0x14006f6f4  call    cs:__imp_GetDiskFreeSpaceW
0x14006f6fb  nop     dword ptr [rax+rax+00h]
0x14006f700  test    eax, eax
0x14006f702  jz      short loc_14006F6CA
0x14006f704  xor     edx, edx
0x14006f706  mov     rax, r14
0x14006f709  div     rsi
0x14006f70c  mov     r13, rax
0x14006f70f  mov     r8, rax
0x14006f712  shl     r8, 8
0x14006f716  lea     rcx, [r8+r8*4]
0x14006f71a  add     rcx, rcx
0x14006f71d  mov     rax, 47AE147AE147AE15h
0x14006f727  mul     rcx
0x14006f72a  sub     rcx, rdx
0x14006f72d  shr     rcx, 1
0x14006f730  add     rcx, rdx
0x14006f733  shr     rcx, 6
0x14006f737  mov     edx, 80000000h
0x14006f73c  mov     eax, edx
0x14006f73e  cmp     rcx, rdx
0x14006f741  cmova   rax, rcx
0x14006f745  add     r8, 0FFFh
0x14006f74c  add     rax, r8
0x14006f74f  and     rax, 0FFFFFFFFFFFFF000h
0x14006f755  mov     [rdi+90h], rax
0x14006f75c  mov     rdx, r12
0x14006f75f  lea     rcx, [rbp+360h+var_2B0]
0x14006f766  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006f76b  nop
0x14006f76c  mov     esi, 1
0x14006f771  mov     r8b, sil
0x14006f774  lea     rdx, [rbp+360h+var_2B0]
0x14006f77b  lea     rcx, [rbp+360h+var_2F0]
0x14006f77f  call    ?GetVolumeGuid@DedupUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DedupUtil::GetVolumeGuid(std::wstring const &,bool)
0x14006f784  nop
0x14006f785  lea     rcx, [rbp+360h+var_2B0]
0x14006f78c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006f791  cmp     [rbp+360h+var_2E0], r15
0x14006f798  jnz     short loc_14006F7B6
0x14006f79a  mov     [rbp+360h+var_3E0], 57h ; 'W'
0x14006f7a1  lea     r9, [rbp+360h+var_3E0]
0x14006f7a5  lea     r8, [rbp+360h+var_3C0]
0x14006f7a9  call    ??$Print@AEAPEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAPEBGAEAK@Z; DedupUtil::Print<ushort const * &,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &,ulong &)
0x14006f7ae  mov     ebx, [rbp+360h+var_3E0]
0x14006f7b1  jmp     loc_140070310
0x14006f7b6  xorps   xmm0, xmm0
0x14006f7b9  movups  [rbp+360h+var_310], xmm0
0x14006f7bd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14006f7c5  movdqu  [rbp+360h+var_300], xmm1
0x14006f7ca  mov     word ptr [rbp+360h+var_310], r15w
0x14006f7cf  movups  xmmword ptr [rbp+360h+NtPathName.Length], xmm0
0x14006f7d3  lea     rcx, [rbp+360h+var_2F0]
0x14006f7d7  call    ?IsCsvVolume@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DedupUtil::IsCsvVolume(std::wstring const &)
0x14006f7dc  lea     rcx, [rbp+360h+var_2F0]
0x14006f7e0  test    al, al
0x14006f7e2  jz      short loc_14006F80F
0x14006f7e4  lea     rdx, [rbp+360h+var_310]
0x14006f7e8  call    ?GetMdsPathFromCsv@DedupUtil@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DedupUtil::GetMdsPathFromCsv(std::wstring const &,std::wstring &)
0x14006f7ed  mov     ebx, eax
0x14006f7ef  mov     [rbp+360h+var_3E0], eax
0x14006f7f2  test    eax, eax
0x14006f7f4  jnz     loc_140070306
0x14006f7fa  mov     r8, rsi
0x14006f7fd  lea     rdx, StringValue; "\\"
0x14006f804  lea     rcx, [rbp+360h+var_310]
0x14006f808  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14006f80d  jmp     short loc_14006F860
0x14006f80f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006f814  mov     rcx, rax; DosPathName
0x14006f817  xor     r9d, r9d; DirectoryInfo
0x14006f81a  xor     r8d, r8d; NtFileNamePart
0x14006f81d  lea     rdx, [rbp+360h+NtPathName]; NtPathName
0x14006f821  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14006f828  nop     dword ptr [rax+rax+00h]
0x14006f82d  test    al, al
0x14006f82f  jz      loc_14007032A
0x14006f835  mov     rdx, [rbp+360h+NtPathName.Buffer]
0x14006f839  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006f83d  inc     r8
0x14006f840  cmp     [rdx+r8*2], r15w
0x14006f845  jnz     short loc_14006F83D
0x14006f847  lea     rcx, [rbp+360h+var_310]
0x14006f84b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14006f850  lea     rcx, [rbp+360h+NtPathName]; UnicodeString
0x14006f854  call    cs:__imp_RtlFreeUnicodeString
0x14006f85b  nop     dword ptr [rax+rax+00h]
0x14006f860  mov     rdx, r12
0x14006f863  lea     rcx, [rbp+360h+var_2D0]
0x14006f86a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006f86f  nop
0x14006f870  lea     rdx, [rbp+360h+var_2F0]
0x14006f874  lea     rcx, [rbp+360h+var_288]
0x14006f87b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14006f880  nop
0x14006f881  mov     rbx, [rax+10h]
0x14006f885  lea     rdx, [rbp+360h+var_2F0]
0x14006f889  lea     rcx, [rbp+360h+var_2D0]
0x14006f890  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x14006f895  lea     r8, [rbx+rax]
0x14006f899  or      r9, 0FFFFFFFFFFFFFFFFh
0x14006f89d  lea     rdx, [rbp+360h+var_2B0]
0x14006f8a4  lea     rcx, [rbp+360h+var_2D0]
0x14006f8ab  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x14006f8b0  mov     r8, [rax+10h]
0x14006f8b4  mov     rcx, rax
0x14006f8b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006f8bc  mov     rdx, rax
0x14006f8bf  lea     rcx, [rbp+360h+var_310]
0x14006f8c3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14006f8c8  nop
0x14006f8c9  lea     rcx, [rbp+360h+var_2B0]
0x14006f8d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006f8d5  nop
0x14006f8d6  lea     rcx, [rbp+360h+var_288]
0x14006f8dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006f8e2  movzx   eax, word ptr [rbp+360h+var_300]
0x14006f8e6  add     ax, ax
0x14006f8e9  mov     [rbp+360h+NtPathName.MaximumLength], ax
0x14006f8ed  mov     [rbp+360h+NtPathName.Length], ax
0x14006f8f1  lea     rcx, [rbp+360h+var_310]
0x14006f8f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006f8fa  mov     [rbp+360h+NtPathName.Buffer], rax
0x14006f8fe  xorps   xmm0, xmm0
0x14006f901  movups  xmmword ptr [rbp+360h+IoStatusBlock], xmm0
0x14006f905  mov     qword ptr [rbp+360h+ObjectAttributes.Length], 30h ; '0'
0x14006f90d  mov     qword ptr [rbp+360h+ObjectAttributes.Attributes], r15
0x14006f911  mov     [rbp+360h+ObjectAttributes.RootDirectory], r15
0x14006f915  lea     rax, [rbp+360h+NtPathName]
0x14006f919  mov     [rbp+360h+ObjectAttributes.ObjectName], rax
0x14006f91d  movdqu  xmmword ptr [rbp+360h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006f922  mov     edx, dword ptr [rbp+360h+arg_30]
0x14006f928  mov     eax, edx
0x14006f92a  and     eax, 4
0x14006f92d  mov     [rbp+360h+var_3C8], eax
0x14006f930  neg     eax
0x14006f932  sbb     ecx, ecx
0x14006f934  and     ecx, 8
0x14006f937  add     ecx, 4840h
0x14006f93d  mov     eax, edx
0x14006f93f  not     eax
0x14006f941  and     eax, esi
0x14006f943  inc     eax
0x14006f945  mov     [rbp+360h+var_3DC], eax
0x14006f948  test    sil, al
0x14006f94b  jz      loc_14006FB13
0x14006f951  mov     [rsp+470h+EaLength], r15d; EaLength
0x14006f956  mov     [rsp+470h+EaBuffer], r15; EaBuffer
0x14006f95b  mov     [rsp+470h+CreateOptions], ecx; CreateOptions
0x14006f95f  mov     [rsp+470h+CreateDisposition], 5; CreateDisposition
0x14006f967  mov     [rsp+470h+ShareAccess], esi; ShareAccess
0x14006f96b  mov     r14d, 6
0x14006f971  mov     [rsp+470h+FileAttributes], r14d; FileAttributes
0x14006f976  mov     [rsp+470h+lpTotalNumberOfClusters], r15; AllocationSize
0x14006f97b  lea     r9, [rbp+360h+IoStatusBlock]; IoStatusBlock
0x14006f97f  lea     r8, [rbp+360h+ObjectAttributes]; ObjectAttributes
0x14006f983  mov     edx, 0C0110000h; DesiredAccess
0x14006f988  lea     rcx, [rbp+360h+FileHandle]; FileHandle
0x14006f98c  call    cs:__imp_NtCreateFile
0x14006f993  nop     dword ptr [rax+rax+00h]
0x14006f998  test    eax, eax
0x14006f99a  jns     short loc_14006F9E2
0x14006f99c  mov     ecx, eax; Status
0x14006f99e  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x14006f9a5  nop     dword ptr [rax+rax+00h]
0x14006f9aa  call    cs:__imp_GetLastError
0x14006f9b1  nop     dword ptr [rax+rax+00h]
0x14006f9b6  mov     [rbp+360h+var_3E0], eax
0x14006f9b9  lea     rcx, [rbp+360h+var_310]
0x14006f9bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006f9c2  lea     rdx, aCouldnTCreateH; "Couldn't create hash index file %s, err"...
0x14006f9c9  lea     r8, [rbp+360h+var_3D8]
0x14006f9cd  lea     r9, [rbp+360h+var_3E0]
0x14006f9d1  mov     [rbp+360h+var_3D8], rax
0x14006f9d5  mov     ecx, r14d
0x14006f9d8  call    ??$Print@PEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAK@Z; DedupUtil::Print<ushort const *,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &)
0x14006f9dd  jmp     loc_1400702F6
0x14006f9e2  mov     [rbp+360h+BytesReturned], r15d
0x14006f9e6  xorps   xmm0, xmm0
0x14006f9e9  movups  [rbp+360h+InBuffer], xmm0
0x14006f9f0  mov     byte ptr [rbp+360h+InBuffer+8], sil
0x14006f9f7  mov     qword ptr [rsp+470h+CreateDisposition], r15; lpOverlapped
0x14006f9fc  lea     rax, [rbp+360h+BytesReturned]
0x14006fa00  mov     qword ptr [rsp+470h+ShareAccess], rax; lpBytesReturned
0x14006fa05  mov     [rsp+470h+FileAttributes], r15d; nOutBufferSize
0x14006fa0a  mov     [rsp+470h+lpTotalNumberOfClusters], r15; lpOutBuffer
0x14006fa0f  mov     r9d, 10h; nInBufferSize
0x14006fa15  lea     r8, [rbp+360h+InBuffer]; lpInBuffer
0x14006fa1c  mov     edx, 90380h; dwIoControlCode
0x14006fa21  mov     rcx, [rbp+360h+FileHandle]; hDevice
0x14006fa25  call    cs:__imp_DeviceIoControl
0x14006fa2c  nop     dword ptr [rax+rax+00h]
0x14006fa31  test    eax, eax
0x14006fa33  jnz     short loc_14006FA57
0x14006fa35  call    cs:__imp_GetLastError
0x14006fa3c  nop     dword ptr [rax+rax+00h]
0x14006fa41  mov     [rbp+360h+Status], eax
0x14006fa44  lea     r8, [rbp+360h+Status]
0x14006fa48  lea     rdx, aCouldnTSetHash_0; "Couldn't set hash index file integrity,"...
0x14006fa4f  mov     ecx, r14d
0x14006fa52  call    ??$Print@K@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAK@Z; DedupUtil::Print<ulong>(DedupUtil::MessageType,ushort const *,ulong &&)
0x14006fa57  mov     [rbp+360h+BytesReturned], r15d
0x14006fa5b  mov     qword ptr [rsp+470h+CreateDisposition], r15; lpOverlapped
0x14006fa60  lea     rax, [rbp+360h+BytesReturned]
0x14006fa64  mov     qword ptr [rsp+470h+ShareAccess], rax; lpBytesReturned
0x14006fa69  mov     [rsp+470h+FileAttributes], r15d; nOutBufferSize
0x14006fa6e  mov     [rsp+470h+lpTotalNumberOfClusters], r15; lpOutBuffer
0x14006fa73  xor     r9d, r9d; nInBufferSize
0x14006fa76  xor     r8d, r8d; lpInBuffer
0x14006fa79  mov     edx, 900C4h; dwIoControlCode
0x14006fa7e  mov     rcx, [rbp+360h+FileHandle]; hDevice
0x14006fa82  call    cs:__imp_DeviceIoControl
0x14006fa89  nop     dword ptr [rax+rax+00h]
0x14006fa8e  test    eax, eax
0x14006fa90  jnz     short loc_14006FAB9
0x14006fa92  call    cs:__imp_GetLastError
0x14006fa99  nop     dword ptr [rax+rax+00h]
0x14006fa9e  lea     rdx, aCouldnTSetHash; "Couldn't set hash index file sparse, er"...
0x14006faa5  mov     [rbp+360h+var_3E0], eax
0x14006faa8  lea     r8, [rbp+360h+var_3E0]
0x14006faac  mov     ecx, r14d
0x14006faaf  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x14006fab4  jmp     loc_1400702F6
0x14006fab9  mov     rax, [rdi+90h]
0x14006fac0  mov     [rbp+360h+FileInformation], rax
0x14006fac4  mov     r9d, 8; dwBufferSize
0x14006faca  lea     r8, [rbp+360h+FileInformation]; lpFileInformation
0x14006face  mov     edx, r14d; FileInformationClass
0x14006fad1  mov     rcx, [rbp+360h+FileHandle]; hFile
0x14006fad5  call    cs:__imp_SetFileInformationByHandle
0x14006fadc  nop     dword ptr [rax+rax+00h]
0x14006fae1  test    eax, eax
0x14006fae3  jnz     loc_14006FBD6
  ... truncated ...
```
