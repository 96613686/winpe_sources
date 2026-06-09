# DeviceEncryptionResourceManager::RefreshVolumesNoLock(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> const &)

- ea: `0x18000dde0`
- end: `0x18000ee09`
- name: `?RefreshVolumesNoLock@DeviceEncryptionResourceManager@@IEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z`
- size: `4137`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800062d0`
- `0x1800748b0`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000dde0`
- `0x18000ee10`
- `0x18000f0e4`
- `0x18000f130`
- `0x18000f1a0`
- `0x18001b7f0`
- `0x18001c970`
- `0x18001d0cc`
- `0x18001d1b0`
- `0x18001ee3c`
- `0x180022cd8`
- `0x18002a718`
- `0x18002afa4`
- `0x18002c174`
- `0x18002c1d0`
- `0x18002cac4`
- `0x18002e628`
- `0x18002f734`
- `0x1800304a8`
- `0x180034070`
- `0x180034440`
- `0x180034500`
- `0x180034d28`
- `0x180046fb8`
- `0x1800735b8`
- `0x180074108`
- `0x180074148`
- `0x18007428c`
- `0x18007441c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000e3c1`
- `ntdll!RtlFreeUnicodeString` at `0x18000e3c1`
- `ntdll!RtlNtStatusToDosError` at `0x18000e2e5`
- `ntdll!RtlNtStatusToDosError` at `0x18000e2e5`
- `ntdll!RtlStringFromGUID` at `0x18000e2d7`
- `ntdll!RtlStringFromGUID` at `0x18000e2d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e867`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e412`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e4a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e412`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e4a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e7ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e7ea`
- `VirtDisk!GetStorageDependencyInformation` at `0x18000e81c`
- `VirtDisk!GetStorageDependencyInformation` at `0x18000e81c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceEncryptionResourceManager::RefreshVolumesNoLock(
        DeviceEncryptionResourceManager *a1,
        __int64 **a2)
{
  DeviceEncryptionResourceManager *v3; // rsi
  int v4; // ebx
  WCHAR *v5; // r8
  __int64 v6; // rdi
  PVOID *v7; // r10
  _QWORD *v8; // rbx
  _QWORD *v9; // r14
  __int64 *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 i; // rax
  DeviceEncryptionResourceManager *v15; // rcx
  _BYTE *v16; // rax
  _QWORD **v17; // rdi
  _QWORD *j; // rbx
  const struct _GUID *v19; // rdx
  _STORAGE_DEPENDENCY_INFO *p_StorageDependencyInfo; // rcx
  _STORAGE_DEPENDENCY_INFO *v21; // r9
  unsigned int v22; // eax
  __int64 v23; // r14
  unsigned int v24; // r15d
  __int64 v25; // rax
  unsigned int *v26; // r9
  __int64 v27; // rcx
  unsigned int UniqueNo; // eax
  WCHAR *v29; // rax
  WCHAR *v30; // rbx
  NTSTATUS v31; // eax
  int v32; // eax
  bool v33; // zf
  int KnownLastErrorHR; // ebx
  int v35; // eax
  DWORD FileAttributesW; // ebx
  WCHAR *v37; // rax
  _QWORD *v38; // rcx
  int BcdVolumesNoLock; // eax
  __int64 v40; // rbx
  _QWORD *v41; // rax
  __int64 v42; // rdx
  WCHAR *v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rdx
  WCHAR v46; // ax
  __int64 v47; // rcx
  WCHAR *v48; // rax
  __int64 v49; // rax
  unsigned __int64 v50; // rax
  HANDLE FileW; // rsi
  signed int StorageDependencyInformation; // eax
  signed int v53; // ebx
  char v54; // r14
  WCHAR *v55; // r9
  _QWORD *v56; // rsi
  __int64 v57; // rax
  __int64 v58; // rbx
  WCHAR *v59; // rsi
  WCHAR *v60; // r9
  _QWORD *v61; // rbx
  WCHAR *v62; // rax
  __int64 v63; // rsi
  PVOID *v64; // rcx
  WCHAR *v65; // rax
  __int64 v66; // rcx
  __int64 k; // rax
  void **v68; // rsi
  _QWORD **v69; // rcx
  _QWORD *v70; // rdi
  _QWORD *v71; // rbx
  char v73; // [rsp+40h] [rbp-958h]
  int v74; // [rsp+48h] [rbp-950h] BYREF
  char v75; // [rsp+50h] [rbp-948h]
  WCHAR *v76; // [rsp+58h] [rbp-940h]
  _QWORD *v77; // [rsp+60h] [rbp-938h] BYREF
  DeviceEncryptionResourceManager *v78; // [rsp+68h] [rbp-930h]
  void *v79; // [rsp+70h] [rbp-928h] BYREF
  __int64 v80; // [rsp+78h] [rbp-920h] BYREF
  ULONG SizeUsed; // [rsp+80h] [rbp-918h] BYREF
  __int64 v82; // [rsp+88h] [rbp-910h] BYREF
  char v83; // [rsp+90h] [rbp-908h]
  int v84; // [rsp+94h] [rbp-904h]
  struct _UNICODE_STRING GuidString; // [rsp+98h] [rbp-900h] BYREF
  __int64 v86; // [rsp+A8h] [rbp-8F0h]
  char v87[8]; // [rsp+B0h] [rbp-8E8h] BYREF
  _BYTE v88[16]; // [rsp+B8h] [rbp-8E0h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-8D0h]
  _STORAGE_DEPENDENCY_INFO StorageDependencyInfo; // [rsp+D0h] [rbp-8C8h] BYREF
  unsigned __int64 v91; // [rsp+E8h] [rbp-8B0h]
  WCHAR FileName[1024]; // [rsp+160h] [rbp-838h] BYREF

  v3 = a1;
  v78 = a1;
  v77 = 0;
  v79 = 0;
  v4 = 0;
  v74 = 0;
  DeviceEncryptionResourceManager::PublishDEManagedVolumeCount(a2);
  if ( !*((_QWORD *)v3 + 13) )
    goto LABEL_245;
  v75 = 0;
  v73 = 0;
  v6 = **a2;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( (__int64 *)v6 == *a2 )
    {
      v8 = (_QWORD *)**((_QWORD **)v3 + 9);
      while ( v8 != *((_QWORD **)v3 + 9) )
      {
        v9 = v8 + 4;
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
          a2,
          v88,
          v8 + 4);
        v10 = (__int64 *)v89;
        if ( *(_BYTE *)(v89 + 25) || (unsigned __int8)std::operator<<unsigned short>(v8 + 4, v89 + 32) || v10 == *a2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            if ( v8[7] > 7u )
              v9 = (_QWORD *)*v9;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v9);
          }
          v8 = *(_QWORD **)std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeEntry>>>>,0>(
                             (char *)v3 + 72,
                             &v80,
                             v8);
        }
        else
        {
          v13 = v8[2];
          if ( *(_BYTE *)(v13 + 25) )
          {
            for ( i = v8[1]; !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
            {
              if ( v8 != *(_QWORD **)(i + 16) )
                break;
              v8 = (_QWORD *)i;
            }
            v8 = (_QWORD *)i;
          }
          else
          {
            v8 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min(
                             v13,
                             v11,
                             v12);
          }
        }
      }
      v15 = v78;
      v16 = (_BYTE *)*((_QWORD *)v78 + 8);
      if ( v16 && v79 && (v16[88] & 8) != 0 && (*v16 & 0x28) != 0 )
      {
        v17 = *(_QWORD ***)v79;
        for ( j = **(_QWORD ***)v79; j != v17; j = (_QWORD *)*j )
        {
          std::pair<std::wstring const,VolumeEntry>::pair<std::wstring const,VolumeEntry>(&StorageDependencyInfo, j + 2);
          p_StorageDependencyInfo = &StorageDependencyInfo;
          if ( v91 > 7 )
            p_StorageDependencyInfo = *(_STORAGE_DEPENDENCY_INFO **)&StorageDependencyInfo.Version;
          if ( (int)FveEasUtil::InitializeFDV((const unsigned __int16 *)p_StorageDependencyInfo, v19) >= 0 )
          {
            try
            {
              std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::emplace<std::pair<std::wstring const,VolumeEntry> &>(
                (char *)v3 + 72,
                &GuidString,
                &StorageDependencyInfo);
              v75 = 1;
            }
            catch ( std::bad_alloc )
            {
              v74 = -2147024882;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                  2147942414LL);
              std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(&StorageDependencyInfo);
              v4 = v74;
              goto LABEL_245;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v21 = &StorageDependencyInfo;
            if ( v91 > 7 )
              v21 = *(_STORAGE_DEPENDENCY_INFO **)&StorageDependencyInfo.Version;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v21);
          }
          std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(&StorageDependencyInfo);
        }
        v15 = v78;
      }
      if ( v75 )
      {
        v22 = DeviceEncryptionResourceManager::ProcessStateChangeNoLock(v15, 0);
        v4 = v22;
        v74 = v22;
        if ( !v22 )
          goto LABEL_245;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_245;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_245;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v22);
        goto LABEL_245;
      }
      v4 = v74;
      goto LABEL_245;
    }
    v23 = v6 + 64;
    v24 = *(_DWORD *)(v6 + 64);
    v25 = *(_QWORD *)(v6 + 152);
    v80 = v25;
    if ( (v24 & 0x4000) == 0 )
    {
      if ( (v24 & 0x400000) != 0 )
        goto LABEL_238;
      v29 = (WCHAR *)(v6 + 32);
      v76 = (WCHAR *)(v6 + 32);
      if ( *(int *)(v6 + 140) < 0 )
      {
        if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 8) == 0 )
          goto LABEL_238;
        if ( *(_QWORD *)(v6 + 56) > 7u )
          v29 = *(WCHAR **)v29;
        v42 = 16;
        goto LABEL_236;
      }
      if ( *(_QWORD *)(v6 + 56) <= 7u )
        v30 = (WCHAR *)(v6 + 32);
      else
        v30 = *(WCHAR **)v29;
      v82 = 0;
      v83 = 0;
      v84 = 0;
      GuidString = 0;
      memset_0(FileName, 0, sizeof(FileName));
      v31 = RtlStringFromGUID(&DE_VOLUME_OPTED_OUT_FILE_TYPE_GUID, &GuidString);
      v32 = RtlNtStatusToDosError(v31);
      v74 = v32;
      v33 = v32 == 0;
      if ( v32 > 0 )
      {
        v32 = (unsigned __int16)v32 | 0x80070000;
        v74 = v32;
        v33 = v32 == 0;
      }
      if ( v33 )
        goto LABEL_76;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          321,
          WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          (unsigned int)v32);
        v32 = v74;
      }
      if ( v32 >= 0 )
      {
LABEL_76:
        KnownLastErrorHR = StringCchPrintfW(
                             FileName,
                             0x400u,
                             L"%s\\System Volume Information\\FVE2.%s",
                             v30,
                             GuidString.Buffer);
        v74 = KnownLastErrorHR;
        if ( !KnownLastErrorHR )
          goto LABEL_81;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            322,
            WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            (unsigned int)KnownLastErrorHR);
        if ( KnownLastErrorHR >= 0 )
LABEL_81:
          FileName[1023] = 0;
      }
      else
      {
        KnownLastErrorHR = v74;
      }
      RtlFreeUnicodeString(&GuidString);
      if ( KnownLastErrorHR )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            323,
            WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            (unsigned int)KnownLastErrorHR);
        if ( KnownLastErrorHR < 0 )
          goto LABEL_104;
      }
      if ( GetFileAttributesW(FileName) == -1 )
      {
        if ( GetLastError() != 5 )
          goto LABEL_96;
        v74 = 17;
        v35 = CNgscbScopedPrivilege::AcquirePrivileges((CNgscbScopedPrivilege *)&v82, &v74);
        v74 = v35;
        if ( v35 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              324,
              WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
              (unsigned int)v35);
            v35 = v74;
          }
          if ( v35 < 0 )
          {
            KnownLastErrorHR = v74;
            goto LABEL_104;
          }
        }
        FileAttributesW = GetFileAttributesW(FileName);
        CNgscbScopedPrivilege::ReleasePrivilege((CNgscbScopedPrivilege *)&v82);
        if ( FileAttributesW == -1 )
        {
LABEL_96:
          KnownLastErrorHR = NgscbGetKnownLastErrorHR();
          v74 = KnownLastErrorHR;
          if ( (unsigned int)(KnownLastErrorHR + 2147024894) <= 1 )
          {
            v73 = 0;
            CNgscbScopedPrivilege::ReleasePrivilege((CNgscbScopedPrivilege *)&v82);
            v74 = 0;
            goto LABEL_113;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              325,
              WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
              (unsigned int)KnownLastErrorHR);
LABEL_104:
          CNgscbScopedPrivilege::ReleasePrivilege((CNgscbScopedPrivilege *)&v82);
          if ( KnownLastErrorHR < 0 )
          {
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_111;
            LODWORD(v37) = (_DWORD)v76;
            if ( *((_QWORD *)v76 + 3) > 7u )
              v37 = *(WCHAR **)v76;
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
              (_DWORD)v37,
              KnownLastErrorHR);
LABEL_110:
            v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_111:
            v74 = 0;
            goto LABEL_238;
          }
          if ( v73 )
            goto LABEL_129;
LABEL_113:
          v38 = v77;
          if ( v77 )
            goto LABEL_119;
          BcdVolumesNoLock = DeviceEncryptionResourceManager::GetBcdVolumesNoLock(v3, &v77);
          v74 = BcdVolumesNoLock;
          if ( BcdVolumesNoLock >= 0 )
          {
            v38 = v77;
LABEL_119:
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              v38,
              &GuidString,
              v76);
            v40 = v86;
            if ( *(_BYTE *)(v86 + 25) || (unsigned __int8)std::operator<<unsigned short>(v76, v86 + 32) )
            {
              v41 = v77;
              v40 = *v77;
            }
            else
            {
              v41 = v77;
            }
            if ( v40 == *v41 )
            {
LABEL_129:
              if ( *((_QWORD *)v76 + 3) <= 7u )
                v43 = v76;
              else
                v43 = *(WCHAR **)v76;
              memset_0(FileName, 0, 0x20Cu);
              StorageDependencyInfo.Version = STORAGE_DEPENDENCY_INFO_VERSION_2;
              memset_0(&StorageDependencyInfo.NumberEntries, 0, 0x44u);
              SizeUsed = 0;
              v44 = 2147483646;
              v45 = 262;
              v5 = FileName;
              while ( v44 )
              {
                v46 = *v43;
                if ( !*v43 )
                  break;
                ++v43;
                *v5++ = v46;
                --v44;
                if ( !--v45 )
                {
                  *(v5 - 1) = 0;
LABEL_167:
                  v7 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_168;
                }
              }
              *v5 = 0;
              v47 = 262;
              v48 = FileName;
              while ( *v48 )
              {
                ++v48;
                if ( !--v47 )
                  goto LABEL_167;
              }
              v49 = 262 - v47;
              if ( v47 != 262 && v47 != 261 )
              {
                if ( FileName[v49 - 1] == 92 )
                {
                  v50 = 2 * v49 - 2;
                  if ( v50 >= 0x20C )
                    _report_rangecheckfailure(v47, v45);
                  *(WCHAR *)((char *)FileName + v50) = 0;
                }
                FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
                StorageDependencyInformation = GetStorageDependencyInformation(
                                                 FileW,
                                                 GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                                 0x48u,
                                                 &StorageDependencyInfo,
                                                 &SizeUsed);
                v53 = StorageDependencyInformation;
                if ( (unsigned int)StorageDependencyInformation <= 1 || StorageDependencyInformation == -1069940715 )
                {
                  v54 = 0;
LABEL_156:
                  v53 = 0;
                }
                else
                {
                  if ( StorageDependencyInformation == 122 )
                  {
                    v54 = 1;
                    goto LABEL_156;
                  }
                  v54 = 0;
                  if ( StorageDependencyInformation > 0 )
                    v53 = (unsigned __int16)StorageDependencyInformation | 0x80070000;
                }
                if ( FileW != (HANDLE)-1LL )
                  CloseHandle(FileW);
                if ( v53 >= 0 && v54 )
                {
                  v7 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                    goto LABEL_238;
                  v29 = v76;
                  if ( *((_QWORD *)v76 + 3) > 7u )
                    v29 = *(WCHAR **)v76;
                  v42 = 20;
                  goto LABEL_236;
                }
                v23 = v6 + 64;
                v3 = v78;
                goto LABEL_167;
              }
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  69,
                  &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
                  2147942487LL);
                goto LABEL_167;
              }
LABEL_168:
              if ( (v24 & 1) != 0 )
              {
                if ( (v24 & 0x800) != 0 )
                {
                  if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 8) == 0 )
                    goto LABEL_238;
                  v29 = v76;
                  if ( *((_QWORD *)v76 + 3) > 7u )
                    v29 = *(WCHAR **)v76;
                  v42 = 21;
                  goto LABEL_236;
                }
                if ( (*(_BYTE *)(v23 + 88) & 8) == 0 )
                {
                  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
                  {
                    if ( *((_QWORD *)v76 + 3) <= 7u )
                      v55 = v76;
                    else
                      v55 = *(WCHAR **)v76;
                    WPP_SF_S(v7[2], 22, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v55);
                  }
                  v73 = 1;
                }
              }
              else if ( !v73 )
              {
                v59 = v76;
                if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
                {
                  if ( *((_QWORD *)v76 + 3) <= 7u )
                    v60 = v76;
                  else
                    v60 = *(WCHAR **)v76;
                  WPP_SF_S(v7[2], 23, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v60);
                }
                v61 = v79;
                if ( !v79 )
                {
                  v4 = MakeUniqueNoThrow<std::list<std::pair<std::wstring const,VolumeEntry>>>((void ***)&v79);
                  v74 = v4;
                  if ( v4 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        24,
                        WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                        (unsigned int)v4);
                    if ( v4 < 0 )
                      goto LABEL_245;
                  }
                  v61 = v79;
                }
                try
                {
                  std::pair<std::wstring const,VolumeEntry>::pair<std::wstring const,VolumeEntry>(
                    &StorageDependencyInfo,
                    v59,
                    v23);
                  std::list<std::pair<std::wstring const,VolumeEntry>>::_Emplace<std::pair<std::wstring const,VolumeEntry>>(
                    v61,
                    *v61,
                    &StorageDependencyInfo);
                  std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(&StorageDependencyInfo);
                }
                catch ( std::bad_alloc )
                {
                  v74 = -2147024882;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      25,
                      WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                      2147942414LL);
                  v4 = v74;
                  goto LABEL_245;
                }
                goto LABEL_237;
              }
              v56 = (_QWORD *)((char *)v3 + 72);
              v57 = std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::_Find<std::wstring>(
                      v56,
                      v76);
              v58 = v57;
              if ( v57 != *v56 )
              {
                if ( v73 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    v62 = v76;
                    if ( *((_QWORD *)v76 + 3) > 7u )
                      v62 = *(WCHAR **)v76;
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      28,
                      WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                      v62);
                  }
                  std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeEntry>>>>,0>(
                    v56,
                    v87,
                    v58);
                }
                else
                {
                  v63 = v80;
                  if ( *(_DWORD *)(v57 + 64) != v24 || *(_QWORD *)(v57 + 152) != v80 )
                  {
                    v64 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        v65 = v76;
                        if ( *((_QWORD *)v76 + 3) > 7u )
                          v65 = *(WCHAR **)v76;
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          29,
                          WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                          v65);
                        v64 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v64 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v64 + 28) & 8) != 0 )
                        {
                          WPP_SF_d(
                            v64[2],
                            30,
                            WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                            *(unsigned int *)(v58 + 64));
                          v64 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v64 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v64 + 28) & 8) != 0 )
                          {
                            WPP_SF_d(v64[2], 31, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v24);
                            v64 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v64 != &WPP_GLOBAL_Control )
                          {
                            if ( (*((_BYTE *)v64 + 28) & 8) != 0 )
                            {
                              WPP_SF_Li(
                                v64[2],
                                32,
                                WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                                *(unsigned int *)(v58 + 64),
                                *(_QWORD *)(v58 + 152));
                              v64 = (PVOID *)WPP_GLOBAL_Control;
                            }
                            if ( v64 != &WPP_GLOBAL_Control && (*((_BYTE *)v64 + 28) & 8) != 0 )
                              WPP_SF_Li(v64[2], 33, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v24, v63);
                          }
                        }
                      }
                    }
                    *(_DWORD *)(v58 + 64) = *(_DWORD *)v23;
                    *(_DWORD *)(v58 + 68) = *(_DWORD *)(v23 + 4);
                    *(_DWORD *)(v58 + 72) = *(_DWORD *)(v23 + 8);
                    *(_QWORD *)(v58 + 80) = *(_QWORD *)(v23 + 16);
                    *(_DWORD *)(v58 + 88) = *(_DWORD *)(v23 + 24);
                    *(_DWORD *)(v58 + 92) = *(_DWORD *)(v23 + 28);
                    *(_DWORD *)(v58 + 96) = *(_DWORD *)(v23 + 32);
                    *(_DWORD *)(v58 + 136) = *(_DWORD *)(v23 + 72);
                    *(_DWORD *)(v58 + 140) = *(_DWORD *)(v23 + 76);
                    *(_DWORD *)(v58 + 144) = *(_DWORD *)(v23 + 80);
                    *(_QWORD *)(v58 + 152) = *(_QWORD *)(v23 + 88);
                    *(_OWORD *)(v58 + 160) = *(_OWORD *)(v23 + 96);
                    v75 = 1;
                  }
                }
                goto LABEL_237;
              }
              if ( !v73 )
              {
                try
                {
                  std::pair<std::wstring const,VolumeEntry>::pair<std::wstring const,VolumeEntry>(
                    &StorageDependencyInfo,
                    v76,
                    v23);
                  std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::emplace<std::pair<std::wstring const,VolumeEntry> &>(
                    v56,
                    v88,
                    &StorageDependencyInfo);
                  std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(&StorageDependencyInfo);
                  v75 = 1;
                }
                catch ( std::bad_alloc )
                {
                  v74 = -2147024882;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      27,
                      WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
                      2147942414LL);
                  v4 = v74;
                  goto LABEL_245;
                }
                goto LABEL_237;
              }
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_238;
              v29 = v76;
              if ( *((_QWORD *)v76 + 3) > 7u )
                v29 = *(WCHAR **)v76;
              v42 = 26;
            }
            else
            {
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_238;
              v29 = v76;
              if ( *((_QWORD *)v76 + 3) > 7u )
                v29 = *(WCHAR **)v76;
              v42 = 19;
            }
LABEL_236:
            WPP_SF_S(v7[2], v42, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v29);
LABEL_237:
            v7 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_238;
          }
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_111;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
            (unsigned int)BcdVolumesNoLock);
          goto LABEL_110;
        }
        KnownLastErrorHR = v74;
      }
      v73 = 1;
      goto LABEL_104;
    }
    v26 = (unsigned int *)*((_QWORD *)v3 + 8);
    if ( v26 )
    {
      if ( *v26 == v24 && *((_QWORD *)v26 + 11) == v25 )
        goto LABEL_238;
      if ( v7 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v7 + 28) & 8) != 0 )
        {
          WPP_SF_(v7[2], 13, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
          v26 = (unsigned int *)*((_QWORD *)v3 + 8);
          v7 = (PVOID *)WPP_GLOBAL_Control;
          v25 = v80;
        }
        if ( v7 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v7 + 28) & 8) != 0 )
          {
            WPP_SF_Li(v7[2], 14, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, *v26, *((_QWORD *)v26 + 11));
            v7 = (PVOID *)WPP_GLOBAL_Control;
            v25 = v80;
          }
          if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
            WPP_SF_Li(v7[2], 15, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v24, v25);
        }
      }
      v27 = *((_QWORD *)v3 + 8);
      *(_DWORD *)v27 = *(_DWORD *)v23;
      *(_DWORD *)(v27 + 4) = *(_DWORD *)(v6 + 68);
      *(_DWORD *)(v27 + 8) = *(_DWORD *)(v6 + 72);
      *(_QWORD *)(v27 + 16) = *(_QWORD *)(v6 + 80);
      *(_DWORD *)(v27 + 24) = *(_DWORD *)(v6 + 88);
      *(_DWORD *)(v27 + 28) = *(_DWORD *)(v6 + 92);
      *(_DWORD *)(v27 + 32) = *(_DWORD *)(v6 + 96);
      *(_DWORD *)(v27 + 72) = *(_DWORD *)(v6 + 136);
      *(_DWORD *)(v27 + 76) = *(_DWORD *)(v6 + 140);
      *(_DWORD *)(v27 + 80) = *(_DWORD *)(v6 + 144);
      *(_QWORD *)(v27 + 88) = *(_QWORD *)(v6 + 152);
      *(_OWORD *)(v27 + 96) = *(_OWORD *)(v6 + 160);
      v75 = 1;
      goto LABEL_237;
    }
    UniqueNo = MakeUniqueNoThrow<VolumeEntry,VolumeEntry const &>(
                 (VolumeEntry **)v3 + 8,
                 (const struct VolumeEntry *)(v6 + 64));
    v4 = UniqueNo;
    v74 = UniqueNo;
    if ( UniqueNo )
      break;
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
    v75 = 1;
LABEL_238:
    v66 = *(_QWORD *)(v6 + 16);
    if ( *(_BYTE *)(v66 + 25) )
    {
      for ( k = *(_QWORD *)(v6 + 8); !*(_BYTE *)(k + 25); k = *(_QWORD *)(k + 8) )
      {
        if ( v6 != *(_QWORD *)(k + 16) )
          break;
        v6 = k;
      }
      v6 = k;
      v3 = v78;
    }
    else
    {
      v6 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min(
             v66,
             &WPP_GLOBAL_Control,
             v5);
      v3 = v78;
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, UniqueNo);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 )
    goto LABEL_63;
LABEL_245:
  v68 = (void **)v79;
  if ( v79 )
  {
    v69 = *(_QWORD ***)v79;
    **(_QWORD **)(*(_QWORD *)v79 + 8LL) = 0;
    v70 = *v69;
    if ( *v69 )
    {
      do
      {
        v71 = (_QWORD *)*v70;
        std::pair<std::wstring const,VolumeEntry>::`scalar deleting destructor'(v70 + 2);
        std::_Deallocate<16>(v70, (struct std::nothrow_t *)0xA0);
        v70 = v71;
      }
      while ( v71 );
      v4 = v74;
    }
    std::_Deallocate<16>(*v68, (struct std::nothrow_t *)0xA0);
    operator delete(v68, (const struct std::nothrow_t *)0x10);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000dde0  mov     [rsp+arg_10], rbx
0x18000dde5  mov     [rsp+arg_18], rsi
0x18000ddea  push    rdi
0x18000ddeb  push    r12
0x18000dded  push    r13
0x18000ddef  push    r14
0x18000ddf1  push    r15
0x18000ddf3  sub     rsp, 970h
0x18000ddfa  mov     rax, cs:__security_cookie
0x18000de01  xor     rax, rsp
0x18000de04  mov     [rsp+998h+var_38], rax
0x18000de0c  mov     r13, rdx
0x18000de0f  mov     rsi, rcx
0x18000de12  mov     [rsp+998h+var_930], rcx
0x18000de17  xor     r12d, r12d
0x18000de1a  mov     [rsp+998h+var_938], r12
0x18000de1f  mov     [rsp+998h+var_928], r12
0x18000de24  mov     ebx, r12d
0x18000de27  mov     [rsp+998h+var_950], ebx
0x18000de2b  mov     rcx, rdx
0x18000de2e  call    ?PublishDEManagedVolumeCount@DeviceEncryptionResourceManager@@KAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; DeviceEncryptionResourceManager::PublishDEManagedVolumeCount(std::map<std::wstring,VolumeEntry> const &)
0x18000de33  cmp     [rsi+68h], rbx
0x18000de37  jz      loc_18000ED7E
0x18000de3d  mov     [rsp+998h+var_948], bl
0x18000de41  mov     [rsp+998h+var_958], bl
0x18000de45  mov     rdi, [r13+0]
0x18000de49  mov     rdi, [rdi]
0x18000de4c  mov     r10, cs:WPP_GLOBAL_Control
0x18000de53  lea     rdx, WPP_GLOBAL_Control
0x18000de5a  cmp     rdi, [r13+0]
0x18000de5e  jnz     loc_18000E0A1
0x18000de64  mov     rbx, [rsi+48h]
0x18000de68  mov     rbx, [rbx]
0x18000de6b  lea     r15, WPP_GLOBAL_Control
0x18000de72  cmp     rbx, [rsi+48h]
0x18000de76  jz      loc_18000DF39
0x18000de7c  lea     r14, [rbx+20h]
0x18000de80  mov     r8, r14
0x18000de83  lea     rdx, [rsp+998h+var_8E0]
0x18000de8b  mov     rcx, r13
0x18000de8e  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000de93  mov     rdi, [rsp+998h+var_8D0]
0x18000de9b  cmp     byte ptr [rdi+19h], 0
0x18000de9f  jnz     short loc_18000DEEC
0x18000dea1  lea     rdx, [rdi+20h]
0x18000dea5  mov     rcx, r14
0x18000dea8  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000dead  test    al, al
0x18000deaf  jnz     short loc_18000DEEC
0x18000deb1  cmp     rdi, [r13+0]
0x18000deb5  jz      short loc_18000DEEC
0x18000deb7  mov     rcx, [rbx+10h]
0x18000debb  cmp     [rcx+19h], al
0x18000debe  jz      short loc_18000DEE2
0x18000dec0  mov     rax, [rbx+8]
0x18000dec4  cmp     byte ptr [rax+19h], 0
0x18000dec8  jnz     short loc_18000DEDD
0x18000deca  cmp     rbx, [rax+10h]
0x18000dece  jnz     short loc_18000DEDD
0x18000ded0  mov     rbx, rax
0x18000ded3  mov     rax, [rax+8]
0x18000ded7  cmp     byte ptr [rax+19h], 0
0x18000dedb  jz      short loc_18000DECA
0x18000dedd  mov     rbx, rax
0x18000dee0  jmp     short loc_18000DE72
0x18000dee2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<CSessionState>>,void *> *)
0x18000dee7  mov     rbx, rax
0x18000deea  jmp     short loc_18000DE72
0x18000deec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def3  cmp     rcx, r15
0x18000def6  jz      short loc_18000DF20
0x18000def8  test    byte ptr [rcx+1Ch], 8
0x18000defc  jz      short loc_18000DF20
0x18000defe  cmp     qword ptr [rbx+38h], 7
0x18000df03  jbe     short loc_18000DF08
0x18000df05  mov     r14, [r14]
0x18000df08  mov     edx, 22h ; '"'
0x18000df0d  mov     r9, r14
0x18000df10  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000df17  mov     rcx, [rcx+10h]
0x18000df1b  call    WPP_SF_S
0x18000df20  mov     r8, rbx
0x18000df23  lea     rdx, [rsp+998h+var_920]
0x18000df28  lea     rcx, [rsi+48h]
0x18000df2c  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeEntry>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,VolumeEntry>>>>)
0x18000df31  mov     rbx, [rax]
0x18000df34  jmp     loc_18000DE72
0x18000df39  mov     rcx, [rsp+998h+var_930]
0x18000df3e  mov     rax, [rcx+40h]
0x18000df42  test    rax, rax
0x18000df45  jz      loc_18000E04A
0x18000df4b  mov     rdi, [rsp+998h+var_928]
0x18000df50  test    rdi, rdi
0x18000df53  jz      loc_18000E04A
0x18000df59  test    byte ptr [rax+58h], 8
0x18000df5d  jz      loc_18000E04A
0x18000df63  test    byte ptr [rax], 28h
0x18000df66  jz      loc_18000E04A
0x18000df6c  mov     rdi, [rdi]
0x18000df6f  mov     rbx, [rdi]
0x18000df72  cmp     rbx, rdi
0x18000df75  jz      loc_18000E045
0x18000df7b  lea     rdx, [rbx+10h]
0x18000df7f  lea     rcx, [rsp+998h+StorageDependencyInfo]
0x18000df87  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,VolumeEntry>::pair<std::wstring const,VolumeEntry>(std::pair<std::wstring const,VolumeEntry> const &)
0x18000df8c  nop
0x18000df8d  lea     rcx, [rsp+998h+StorageDependencyInfo]
0x18000df95  cmp     [rsp+998h+var_8B0], 7
0x18000df9e  cmova   rcx, qword ptr [rsp+998h+StorageDependencyInfo.Version]; unsigned __int16 *
0x18000dfa7  call    ?InitializeFDV@FveEasUtil@@SAJPEBGPEBU_GUID@@@Z; FveEasUtil::InitializeFDV(ushort const *,_GUID const *)
0x18000dfac  test    eax, eax
0x18000dfae  js      short loc_18000DFEE
0x18000dfb0  lea     r8, [rsp+998h+StorageDependencyInfo]
0x18000dfb8  lea     rdx, [rsp+998h+GuidString]
0x18000dfc0  lea     rcx, [rsi+48h]
0x18000dfc4  call    ??$emplace@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::emplace<std::pair<std::wstring const,VolumeEntry> &>(std::pair<std::wstring const,VolumeEntry> &)
0x18000dfc9  nop
0x18000dfca  mov     [rsp+998h+var_948], 1
0x18000dfcf  jmp     short loc_18000E030
0x18000dfd1  lea     rcx, [rsp+998h+StorageDependencyInfo]
0x18000dfd9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@QEAA@XZ; std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(void)
0x18000dfde  xor     r12d, r12d
0x18000dfe1  mov     ebx, [rsp+998h+var_950]
0x18000dfe5  mov     [rsp+998h+var_950], ebx
0x18000dfe9  jmp     loc_18000ED7E
0x18000dfee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dff5  cmp     rcx, r15
0x18000dff8  jz      short loc_18000E030
0x18000dffa  test    byte ptr [rcx+1Ch], 2
0x18000dffe  jz      short loc_18000E030
0x18000e000  lea     r9, [rsp+998h+StorageDependencyInfo]
0x18000e008  cmp     [rsp+998h+var_8B0], 7
0x18000e011  cmova   r9, qword ptr [rsp+998h+StorageDependencyInfo.Version]
0x18000e01a  mov     edx, 24h ; '$'
0x18000e01f  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e026  mov     rcx, [rcx+10h]
0x18000e02a  call    WPP_SF_S
0x18000e02f  nop
0x18000e030  lea     rcx, [rsp+998h+StorageDependencyInfo]
0x18000e038  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@QEAA@XZ; std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(void)
0x18000e03d  mov     rbx, [rbx]
0x18000e040  jmp     loc_18000DF72
0x18000e045  mov     rcx, [rsp+998h+var_930]; this
0x18000e04a  cmp     [rsp+998h+var_948], 0
0x18000e04f  jz      loc_18000ED7A
0x18000e055  xor     edx, edx; void *
0x18000e057  call    ?ProcessStateChangeNoLock@DeviceEncryptionResourceManager@@IEAAJPEBX@Z; DeviceEncryptionResourceManager::ProcessStateChangeNoLock(void const *)
0x18000e05c  mov     ebx, eax
0x18000e05e  mov     [rsp+998h+var_950], eax
0x18000e062  test    eax, eax
0x18000e064  jz      loc_18000ED7E
0x18000e06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e071  cmp     rcx, r15
0x18000e074  jz      loc_18000ED7E
0x18000e07a  test    byte ptr [rcx+1Ch], 40h
0x18000e07e  jz      loc_18000ED7E
0x18000e084  mov     edx, 25h ; '%'
0x18000e089  mov     r9d, eax
0x18000e08c  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e093  mov     rcx, [rcx+10h]
0x18000e097  call    WPP_SF_d
0x18000e09c  jmp     loc_18000ED7E
0x18000e0a1  lea     r14, [rdi+40h]
0x18000e0a5  mov     r15d, [r14]
0x18000e0a8  mov     rax, [rdi+98h]
0x18000e0af  mov     [rsp+998h+var_920], rax
0x18000e0b4  bt      r15d, 0Eh
0x18000e0b9  jnb     loc_18000E262
0x18000e0bf  mov     r9, [rsi+40h]
0x18000e0c3  test    r9, r9
0x18000e0c6  jz      loc_18000E1EB
0x18000e0cc  cmp     [r9], r15d
0x18000e0cf  jnz     short loc_18000E0DB
0x18000e0d1  cmp     [r9+58h], rax
0x18000e0d5  jz      loc_18000ED34
0x18000e0db  cmp     r10, rdx
0x18000e0de  jz      loc_18000E187
0x18000e0e4  test    byte ptr [r10+1Ch], 8
0x18000e0e9  jz      short loc_18000E117
0x18000e0eb  mov     edx, 0Dh
0x18000e0f0  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e0f7  mov     rcx, [r10+10h]
0x18000e0fb  call    WPP_SF_
0x18000e100  mov     r9, [rsi+40h]
0x18000e104  mov     r10, cs:WPP_GLOBAL_Control
0x18000e10b  mov     rax, [rsp+998h+var_920]
0x18000e110  lea     rdx, WPP_GLOBAL_Control
0x18000e117  cmp     r10, rdx
0x18000e11a  jz      short loc_18000E187
0x18000e11c  test    byte ptr [r10+1Ch], 8
0x18000e121  jz      short loc_18000E157
0x18000e123  mov     edx, 0Eh
0x18000e128  mov     rax, [r9+58h]
0x18000e12c  mov     qword ptr [rsp+998h+dwCreationDisposition], rax
0x18000e131  mov     r9d, [r9]
0x18000e134  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e13b  mov     rcx, [r10+10h]
0x18000e13f  call    WPP_SF_Li
0x18000e144  mov     r10, cs:WPP_GLOBAL_Control
0x18000e14b  mov     rax, [rsp+998h+var_920]
0x18000e150  lea     rdx, WPP_GLOBAL_Control
0x18000e157  cmp     r10, rdx
0x18000e15a  jz      short loc_18000E187
0x18000e15c  test    byte ptr [r10+1Ch], 8
0x18000e161  jz      short loc_18000E187
0x18000e163  mov     edx, 0Fh
0x18000e168  mov     qword ptr [rsp+998h+dwCreationDisposition], rax
0x18000e16d  mov     r9d, r15d
0x18000e170  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e177  mov     rcx, [r10+10h]
0x18000e17b  call    WPP_SF_Li
0x18000e180  lea     rdx, WPP_GLOBAL_Control
0x18000e187  mov     rcx, [rsi+40h]
0x18000e18b  mov     eax, [r14]
0x18000e18e  mov     [rcx], eax
0x18000e190  mov     eax, [r14+4]
0x18000e194  mov     [rcx+4], eax
0x18000e197  mov     eax, [r14+8]
0x18000e19b  mov     [rcx+8], eax
0x18000e19e  mov     rax, [r14+10h]
0x18000e1a2  mov     [rcx+10h], rax
0x18000e1a6  mov     eax, [r14+18h]
0x18000e1aa  mov     [rcx+18h], eax
0x18000e1ad  mov     eax, [r14+1Ch]
0x18000e1b1  mov     [rcx+1Ch], eax
0x18000e1b4  mov     eax, [r14+20h]
0x18000e1b8  mov     [rcx+20h], eax
0x18000e1bb  mov     eax, [r14+48h]
0x18000e1bf  mov     [rcx+48h], eax
0x18000e1c2  mov     eax, [r14+4Ch]
0x18000e1c6  mov     [rcx+4Ch], eax
0x18000e1c9  mov     eax, [r14+50h]
0x18000e1cd  mov     [rcx+50h], eax
0x18000e1d0  mov     rax, [r14+58h]
0x18000e1d4  mov     [rcx+58h], rax
0x18000e1d8  movups  xmm0, xmmword ptr [r14+60h]
0x18000e1dd  movups  xmmword ptr [rcx+60h], xmm0
0x18000e1e1  mov     [rsp+998h+var_948], 1
0x18000e1e6  jmp     loc_18000ED2D
0x18000e1eb  mov     rdx, r14
0x18000e1ee  lea     rcx, [rsi+40h]
0x18000e1f2  call    ??$MakeUniqueNoThrow@UVolumeEntry@@AEBU1@@@YAJAEAV?$unique_ptr@UVolumeEntry@@U?$default_delete@UVolumeEntry@@@std@@@std@@AEBUVolumeEntry@@@Z; MakeUniqueNoThrow<VolumeEntry,VolumeEntry const &>(std::unique_ptr<VolumeEntry> &,VolumeEntry const &)
0x18000e1f7  mov     ebx, eax
0x18000e1f9  mov     [rsp+998h+var_950], eax
0x18000e1fd  test    eax, eax
0x18000e1ff  jz      short loc_18000E24A
0x18000e201  mov     r10, cs:WPP_GLOBAL_Control
0x18000e208  lea     rdx, WPP_GLOBAL_Control
0x18000e20f  cmp     r10, rdx
0x18000e212  jz      short loc_18000E241
0x18000e214  test    byte ptr [r10+1Ch], 40h
0x18000e219  jz      short loc_18000E241
0x18000e21b  mov     edx, 0Ch
0x18000e220  mov     r9d, eax
0x18000e223  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18000e22a  mov     rcx, [r10+10h]
0x18000e22e  call    WPP_SF_d
0x18000e233  mov     r10, cs:WPP_GLOBAL_Control
0x18000e23a  lea     rdx, WPP_GLOBAL_Control
0x18000e241  test    ebx, ebx
0x18000e243  jns     short loc_18000E258
0x18000e245  jmp     loc_18000ED7E
0x18000e24a  mov     r10, cs:WPP_GLOBAL_Control
0x18000e251  lea     rdx, WPP_GLOBAL_Control
0x18000e258  mov     [rsp+998h+var_948], 1
0x18000e25d  jmp     loc_18000ED34
0x18000e262  bt      r15d, 16h
0x18000e267  jb      loc_18000ED34
0x18000e26d  lea     rax, [rdi+20h]
0x18000e271  mov     [rsp+998h+var_940], rax
0x18000e276  cmp     dword ptr [r14+4Ch], 0
0x18000e27b  jl      loc_18000ECF8
0x18000e281  cmp     qword ptr [rax+18h], 7
0x18000e286  jbe     short loc_18000E28D
0x18000e288  mov     rbx, [rax]
0x18000e28b  jmp     short loc_18000E290
0x18000e28d  mov     rbx, rax
0x18000e290  mov     [rsp+998h+var_910], r12
0x18000e298  mov     [rsp+998h+var_908], 0
0x18000e2a0  mov     [rsp+998h+var_904], r12d
0x18000e2a8  xorps   xmm0, xmm0
0x18000e2ab  movups  xmmword ptr [rsp+998h+GuidString.Length], xmm0
0x18000e2b3  xor     edx, edx; Val
0x18000e2b5  mov     r8d, 800h; Size
0x18000e2bb  lea     rcx, [rsp+998h+FileName]; void *
0x18000e2c3  call    memset_0
0x18000e2c8  lea     rdx, [rsp+998h+GuidString]; GuidString
0x18000e2d0  lea     rcx, DE_VOLUME_OPTED_OUT_FILE_TYPE_GUID; Guid
0x18000e2d7  call    cs:__imp_RtlStringFromGUID
0x18000e2de  nop     dword ptr [rax+rax+00h]
0x18000e2e3  mov     ecx, eax; Status
0x18000e2e5  call    cs:__imp_RtlNtStatusToDosError
0x18000e2ec  nop     dword ptr [rax+rax+00h]
0x18000e2f1  mov     [rsp+998h+var_950], eax
0x18000e2f5  test    eax, eax
0x18000e2f7  jle     short loc_18000E307
0x18000e2f9  movzx   eax, ax
0x18000e2fc  or      eax, 80070000h
0x18000e301  mov     [rsp+998h+var_950], eax
0x18000e305  test    eax, eax
  ... truncated ...
```
