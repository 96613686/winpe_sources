# CTreeWalker::Init(ushort const *,bool,bool,bool *,bool)

- ea: `0x180040da4`
- end: `0x1800411cc`
- name: `?Init@CTreeWalker@@QEAAXPEBG_N1PEA_N1@Z`
- size: `1064`
- prototype: `void __usercall(CTreeWalker *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, bool@<r8b>, bool@<r9b>, bool *, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800388b4`

## callees

- `0x18000d030`
- `0x180012ce0`
- `0x18001c208`
- `0x18001f634`
- `0x180039fa0`
- `0x18003da18`
- `0x18003dc28`
- `0x18003dd14`
- `0x18003df68`
- `0x18003df84`
- `0x18003fe70`
- `0x180040658`
- `0x180040684`
- `0x1800409e8`
- `0x180040da4`
- `0x1800411d4`
- `0x180041398`
- `0x180041414`
- `0x180041450`
- `0x1800442f4`
- `0x180045b80`
- `0x18004617c`
- `0x18004bed8`
- `0x18004cd94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180040e3d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180040e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004116b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004116b`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180041187`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180041187`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180040f27`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180040f27`
- `storageusage!GetStorageDeviceSize` at `0x1800410ea`
- `storageusage!GetStorageDeviceSize` at `0x1800410ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CTreeWalker::Init(CTreeWalker *this, const unsigned __int16 *a2, char a3, char a4, bool *a5, bool a6)
{
  CTreeWalker *v9; // rcx
  int IsNTFS; // eax
  bool v11; // zf
  char v12; // al
  __int64 v13; // rdx
  unsigned int v14; // ebx
  FOLDER_USAGE *v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  __int64 *j; // rcx
  __int64 *v19; // rbx
  __int64 *i; // rax
  _QWORD *v21; // rcx
  _QWORD *k; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // r8
  DWORD NumberOfFreeClusters; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesPerSector; // [rsp+54h] [rbp-ACh] BYREF
  DWORD SectorsPerCluster; // [rsp+58h] [rbp-A8h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v37[72]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[72]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v39[32]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR RootPathName[4]; // [rsp+140h] [rbp+40h] BYREF
  __int16 v41; // [rsp+148h] [rbp+48h] BYREF
  int v42; // [rsp+14Ah] [rbp+4Ah]
  wchar_t v43; // [rsp+14Eh] [rbp+4Eh]
  WCHAR FileName[264]; // [rsp+150h] [rbp+50h] BYREF

  if ( a5 )
    *a5 = 0;
  *((_BYTE *)this + 312) = a3;
  *((_BYTE *)this + 313) = a4;
  *((_BYTE *)this + 316) = a6;
  CTreeWalker::LoadDependencies(this);
  _wsplitpath_s(a2, (wchar_t *)this + 164, 3u, 0, 0, 0, 0, 0, 0);
  if ( StringCchPrintfW(FileName, 0x104u, L"\\\\.\\%s", (char *)this + 328) >= 0 )
  {
    IsNTFS = CTreeWalker::IsNTFS(v9, a2);
    *((_BYTE *)this + 314) = IsNTFS != 0;
    if ( !a3 || (v11 = IsNTFS == 0, v12 = 1, v11) )
      v12 = 0;
    *((_BYTE *)this + 312) = v12;
    if ( !*((_BYTE *)this + 315) )
    {
      if ( a5 )
        *a5 = 1;
      CTreeWalker::PopulateWellKnownPaths(this, FileName);
      if ( !*((_BYTE *)this + 313) )
      {
        LOBYTE(v13) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
          v13);
      }
      CTreeWalker::PopulateWellKnownExtensions(this);
      if ( *((_BYTE *)this + 314) )
      {
        if ( (int)CTreeWalker::QueryFileLayout(this, FileName) < 0 )
          return;
        if ( *((_BYTE *)this + 313) )
          CTreeWalker::FixupUnresolvedReferences(this);
      }
      else
      {
        SectorsPerCluster = 0;
        BytesPerSector = 0;
        NumberOfFreeClusters = 0;
        TotalNumberOfClusters = 0;
        v14 = 0;
        if ( StringCchPrintfW(RootPathName, 4u, L"%s\\", (char *)this + 328) >= 0
          && GetDiskFreeSpaceW(
               RootPathName,
               &SectorsPerCluster,
               &BytesPerSector,
               &NumberOfFreeClusters,
               &TotalNumberOfClusters) )
        {
          v14 = SectorsPerCluster * BytesPerSector;
        }
        v15 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v38, -2, 0, 0);
        v36 = 0x5000000000005LL;
        FOLDER_USAGE::FOLDER_USAGE(v37, v15);
        std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
          (_QWORD *)this + 8,
          (__int64)v35,
          (unsigned __int8 *)&v36);
        std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(&v36);
        FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v38);
        v16 = std::wstring::wstring((__int64)v39, (__int64)RootPathName);
        *(_QWORD *)(*(_QWORD *)std::map<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>>::_Try_emplace<std::wstring,>(
                                 (__int64 *)this + 33,
                                 (__int64)v35,
                                 v16)
                  + 64LL) = 0x5000000000005LL;
        std::wstring::_Tidy_deallocate(v39);
        CTreeWalker::FindFirstQueryFileLayout(this, FileName, 0x5000000000005uLL, v14);
      }
      v17 = 0;
      v32 = 0;
      v33 = 0;
      v41 = 88;
      v42 = *(_DWORD *)L":\\";
      v43 = asc_180095F50[3];
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive((char *)this + 288, &SRWLock);
      v19 = (__int64 *)**((_QWORD **)this + 31);
      while ( v19 != *((__int64 **)this + 31) )
      {
        NumberOfFreeClusters = CTreeWalker::DataTypeNodeFromReserveID(j, *((unsigned int *)v19 + 8));
        std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(
          this,
          RootPathName,
          &NumberOfFreeClusters);
        if ( *(_QWORD *)RootPathName != *((_QWORD *)this + 1) )
          *(_QWORD *)(*(_QWORD *)RootPathName + 48LL) = v19[5];
        j = (__int64 *)v19[2];
        if ( *((_BYTE *)j + 25) )
        {
          for ( i = (__int64 *)v19[1]; !*((_BYTE *)i + 25) && v19 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v19 = i;
          v19 = i;
        }
        else
        {
          v19 = (__int64 *)v19[2];
          for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v19 = j;
        }
      }
      v21 = (_QWORD *)*((_QWORD *)this + 1);
      for ( k = (_QWORD *)*v21; k != v21; k = (_QWORD *)*k )
        v17 += k[6];
      v41 = *((_WORD *)this + 164);
      if ( (int)GetStorageDeviceSize(&v41, 0, &v32, &v33) >= 0 )
      {
        v24 = v32;
        v25 = v33;
        if ( v32 > v33 )
        {
          NumberOfFreeClusters = 1;
          std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(
            this,
            RootPathName,
            &NumberOfFreeClusters);
          v26 = *(_QWORD *)(*(_QWORD *)RootPathName + 48LL);
          if ( *(_QWORD *)RootPathName == *((_QWORD *)this + 1) || v17 >= v24 - v25 )
          {
            v27 = *(_QWORD *)(*(_QWORD *)RootPathName + 48LL);
          }
          else
          {
            v27 = v24 - v25 - v17 + v26;
            *(_QWORD *)(*(_QWORD *)RootPathName + 48LL) = v27;
            v24 = v32;
            v25 = v33;
          }
          TelemetrySystemFilesSize(v26, v24 - v25 - v17, v27);
        }
      }
      if ( SRWLock )
      {
        ReleaseSRWLockExclusive(SRWLock);
        SRWLock = 0;
      }
      LOBYTE(v23) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl'::`2'::impl,
        v23);
      if ( GetDriveTypeW((LPCWSTR)this + 164) == 3 )
        CTreeWalker::FindMediaLibraryFolderSuggestions(this);
    }
    *((_BYTE *)this + 315) = 1;
  }
}

```

## disassembly

```asm
0x180040da4  mov     [rsp-8+arg_10], rbx
0x180040da9  mov     [rsp-8+arg_18], rsi
0x180040dae  push    rbp
0x180040daf  push    rdi
0x180040db0  push    r12
0x180040db2  push    r14
0x180040db4  push    r15
0x180040db6  lea     rbp, [rsp-270h]
0x180040dbe  sub     rsp, 370h
0x180040dc5  mov     rax, cs:__security_cookie
0x180040dcc  xor     rax, rsp
0x180040dcf  mov     [rbp+290h+var_30], rax
0x180040dd6  mov     sil, r8b
0x180040dd9  mov     r14, rdx
0x180040ddc  mov     rdi, rcx
0x180040ddf  mov     rbx, [rbp+290h+arg_20]
0x180040de6  xor     r12d, r12d
0x180040de9  test    rbx, rbx
0x180040dec  jz      short loc_180040DF1
0x180040dee  mov     [rbx], r12b
0x180040df1  mov     [rcx+138h], sil
0x180040df8  mov     [rcx+139h], r9b
0x180040dff  mov     al, [rbp+290h+arg_28]
0x180040e05  mov     [rcx+13Ch], al
0x180040e0b  call    ?LoadDependencies@CTreeWalker@@QEAAXXZ; CTreeWalker::LoadDependencies(void)
0x180040e10  lea     r15, [rdi+148h]
0x180040e17  mov     [rsp+390h+ExtCount], r12; ExtCount
0x180040e1c  mov     [rsp+390h+Ext], r12; Ext
0x180040e21  mov     [rsp+390h+FilenameCount], r12; FilenameCount
0x180040e26  mov     [rsp+390h+Filename], r12; Filename
0x180040e2b  mov     [rsp+390h+DirCount], r12; DirCount
0x180040e30  xor     r9d, r9d; Dir
0x180040e33  lea     r8d, [r9+3]; DriveCount
0x180040e37  mov     rdx, r15; Drive
0x180040e3a  mov     rcx, r14; FullPath
0x180040e3d  call    cs:__imp__wsplitpath_s
0x180040e43  mov     r9, r15
0x180040e46  lea     r8, aS_0; "\\\\.\\%s"
0x180040e4d  mov     edx, 104h; unsigned __int64
0x180040e52  lea     rcx, [rbp+290h+FileName]; unsigned __int16 *
0x180040e56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040e5b  test    eax, eax
0x180040e5d  js      loc_1800411A1
0x180040e63  mov     rdx, r14; unsigned __int16 *
0x180040e66  call    ?IsNTFS@CTreeWalker@@QEAAHPEBG@Z; CTreeWalker::IsNTFS(ushort const *)
0x180040e6b  test    eax, eax
0x180040e6d  setnz   cl
0x180040e70  mov     [rdi+13Ah], cl
0x180040e76  test    sil, sil
0x180040e79  jz      short loc_180040E81
0x180040e7b  test    eax, eax
0x180040e7d  mov     al, 1
0x180040e7f  jnz     short loc_180040E84
0x180040e81  mov     al, r12b
0x180040e84  mov     [rdi+138h], al
0x180040e8a  cmp     [rdi+13Bh], r12b
0x180040e91  jnz     loc_18004119A
0x180040e97  test    rbx, rbx
0x180040e9a  jz      short loc_180040E9F
0x180040e9c  mov     byte ptr [rbx], 1
0x180040e9f  lea     rdx, [rbp+290h+FileName]; lpFileName
0x180040ea3  mov     rcx, rdi; this
0x180040ea6  call    ?PopulateWellKnownPaths@CTreeWalker@@QEAAJPEBG@Z; CTreeWalker::PopulateWellKnownPaths(ushort const *)
0x180040eab  cmp     [rdi+139h], r12b
0x180040eb2  jnz     short loc_180040EC2
0x180040eb4  mov     dl, 1
0x180040eb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions> `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl(void)'::`2'::impl
0x180040ebd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180040ec2  mov     rcx, rdi; this
0x180040ec5  call    ?PopulateWellKnownExtensions@CTreeWalker@@QEAAXXZ; CTreeWalker::PopulateWellKnownExtensions(void)
0x180040eca  cmp     [rdi+13Ah], r12b
0x180040ed1  jnz     loc_180040FD5
0x180040ed7  mov     [rsp+390h+SectorsPerCluster], r12d
0x180040edc  mov     [rsp+390h+BytesPerSector], r12d
0x180040ee1  mov     [rsp+390h+NumberOfFreeClusters], r12d
0x180040ee6  mov     [rsp+390h+TotalNumberOfClusters], r12d
0x180040eeb  mov     ebx, r12d
0x180040eee  mov     r9, r15
0x180040ef1  lea     r8, aS_1; "%s\\"
0x180040ef8  mov     edx, 4; unsigned __int64
0x180040efd  lea     rcx, [rbp+290h+RootPathName]; unsigned __int16 *
0x180040f01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040f06  test    eax, eax
0x180040f08  js      short loc_180040F3A
0x180040f0a  lea     rax, [rsp+390h+TotalNumberOfClusters]
0x180040f0f  mov     [rsp+390h+DirCount], rax; lpTotalNumberOfClusters
0x180040f14  lea     r9, [rsp+390h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180040f19  lea     r8, [rsp+390h+BytesPerSector]; lpBytesPerSector
0x180040f1e  lea     rdx, [rsp+390h+SectorsPerCluster]; lpSectorsPerCluster
0x180040f23  lea     rcx, [rbp+290h+RootPathName]; lpRootPathName
0x180040f27  call    cs:__imp_GetDiskFreeSpaceW
0x180040f2d  test    eax, eax
0x180040f2f  jz      short loc_180040F3A
0x180040f31  mov     ebx, [rsp+390h+BytesPerSector]
0x180040f35  imul    ebx, [rsp+390h+SectorsPerCluster]
0x180040f3a  xor     r9d, r9d; unsigned __int64
0x180040f3d  xor     r8d, r8d; unsigned int
0x180040f40  lea     rdx, [r9-2]; __int64
0x180040f44  lea     rcx, [rbp+290h+var_2B8]; this
0x180040f48  call    ??0FOLDER_USAGE@@QEAA@_JK_K@Z; FOLDER_USAGE::FOLDER_USAGE(__int64,ulong,unsigned __int64)
0x180040f4d  nop
0x180040f4e  mov     rsi, 5000000000005h
0x180040f58  mov     [rbp+290h+var_308], rsi
0x180040f5c  mov     rdx, rax
0x180040f5f  lea     rcx, [rbp+290h+var_300]
0x180040f63  call    ??0FOLDER_USAGE@@QEAA@$$QEAV0@@Z; FOLDER_USAGE::FOLDER_USAGE(FOLDER_USAGE &&)
0x180040f68  nop
0x180040f69  lea     rcx, [rdi+40h]
0x180040f6d  lea     r8, [rbp+290h+var_308]
0x180040f71  lea     rdx, [rsp+390h+var_318]
0x180040f76  call    ??$emplace@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CB_JVFOLDER_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(std::pair<__int64 const,FOLDER_USAGE> &&)
0x180040f7b  nop
0x180040f7c  lea     rcx, [rbp+290h+var_308]
0x180040f80  call    ??1?$pair@$$CB_JVFOLDER_USAGE@@@std@@QEAA@XZ; std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(void)
0x180040f85  nop
0x180040f86  lea     rcx, [rbp+290h+var_2B8]; this
0x180040f8a  call    ??1FOLDER_USAGE@@QEAA@XZ; FOLDER_USAGE::~FOLDER_USAGE(void)
0x180040f8f  lea     rdx, [rbp+290h+RootPathName]
0x180040f93  lea     rcx, [rbp+290h+var_270]
0x180040f97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040f9c  nop
0x180040f9d  lea     rcx, [rdi+108h]
0x180040fa4  mov     r8, rax
0x180040fa7  lea     rdx, [rsp+390h+var_318]
0x180040fac  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_JUStringComparatorIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180040fb1  mov     rcx, [rax]
0x180040fb4  mov     [rcx+40h], rsi
0x180040fb8  lea     rcx, [rbp+290h+var_270]
0x180040fbc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040fc1  mov     r9d, ebx; unsigned int
0x180040fc4  mov     r8, rsi; unsigned __int64
0x180040fc7  lea     rdx, [rbp+290h+FileName]; unsigned __int16 *
0x180040fcb  mov     rcx, rdi; this
0x180040fce  call    ?FindFirstQueryFileLayout@CTreeWalker@@QEAAXPEBG_KK@Z; CTreeWalker::FindFirstQueryFileLayout(ushort const *,unsigned __int64,ulong)
0x180040fd3  jmp     short loc_180040FFA
0x180040fd5  lea     rdx, [rbp+290h+FileName]; unsigned __int16 *
0x180040fd9  mov     rcx, rdi; this
0x180040fdc  call    ?QueryFileLayout@CTreeWalker@@QEAAJPEBG@Z; CTreeWalker::QueryFileLayout(ushort const *)
0x180040fe1  test    eax, eax
0x180040fe3  js      loc_1800411A1
0x180040fe9  cmp     [rdi+139h], r12b
0x180040ff0  jz      short loc_180040FFA
0x180040ff2  mov     rcx, rdi; this
0x180040ff5  call    ?FixupUnresolvedReferences@CTreeWalker@@QEAAXXZ; CTreeWalker::FixupUnresolvedReferences(void)
0x180040ffa  mov     r14, r12
0x180040ffd  mov     [rsp+390h+var_330], r12
0x180041002  mov     [rsp+390h+var_328], r12
0x180041007  mov     eax, 58h ; 'X'
0x18004100c  mov     [rbp+290h+var_248], ax
0x180041010  mov     eax, dword ptr cs:asc_180095F50+2; ":\\"
0x180041016  mov     [rbp+290h+var_246], eax
0x180041019  movzx   eax, word ptr cs:asc_180095F50+6; ""
0x180041020  mov     [rbp+290h+var_242], ax
0x180041024  lea     rcx, [rdi+120h]
0x18004102b  lea     rdx, [rsp+390h+SRWLock]
0x180041030  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockExclusive@Details@234@XZ; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(void)
0x180041035  nop
0x180041036  mov     rbx, [rdi+0F8h]
0x18004103d  mov     rbx, [rbx]
0x180041040  cmp     rbx, [rdi+0F8h]
0x180041047  jz      short loc_1800410BD
0x180041049  mov     edx, [rbx+20h]
0x18004104c  call    ?DataTypeNodeFromReserveID@CTreeWalker@@AEAA?AW4_DATA_TYPE_NODE@@W4_STORAGE_RESERVE_ID@@@Z; CTreeWalker::DataTypeNodeFromReserveID(_STORAGE_RESERVE_ID)
0x180041051  mov     [rsp+390h+NumberOfFreeClusters], eax
0x180041055  lea     r8, [rsp+390h+NumberOfFreeClusters]
0x18004105a  lea     rdx, [rbp+290h+RootPathName]
0x18004105e  mov     rcx, rdi
0x180041061  call    ?find@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@2@AEBH@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(int const &)
0x180041066  mov     rax, qword ptr [rbp+290h+RootPathName]
0x18004106a  cmp     rax, [rdi+8]
0x18004106e  jz      short loc_180041078
0x180041070  mov     rcx, [rbx+28h]
0x180041074  mov     [rax+30h], rcx
0x180041078  mov     rcx, [rbx+10h]
0x18004107c  cmp     [rcx+19h], r12b
0x180041080  jz      short loc_1800410A0
0x180041082  mov     rax, [rbx+8]
0x180041086  jmp     short loc_180041095
0x180041088  cmp     rbx, [rax+10h]
0x18004108c  jnz     short loc_18004109B
0x18004108e  mov     rbx, rax
0x180041091  mov     rax, [rax+8]
0x180041095  cmp     [rax+19h], r12b
0x180041099  jz      short loc_180041088
0x18004109b  mov     rbx, rax
0x18004109e  jmp     short loc_180041040
0x1800410a0  mov     rbx, rcx
0x1800410a3  mov     rcx, [rcx]
0x1800410a6  cmp     [rcx+19h], r12b
0x1800410aa  jnz     short loc_180041040
0x1800410ac  mov     rbx, rcx
0x1800410af  mov     rax, [rcx]
0x1800410b2  mov     rcx, rax
0x1800410b5  cmp     [rax+19h], r12b
0x1800410b9  jz      short loc_1800410AC
0x1800410bb  jmp     short loc_180041040
0x1800410bd  mov     rcx, [rdi+8]
0x1800410c1  mov     rax, [rcx]
0x1800410c4  cmp     rax, rcx
0x1800410c7  jz      short loc_1800410D2
0x1800410c9  add     r14, [rax+30h]
0x1800410cd  mov     rax, [rax]
0x1800410d0  jmp     short loc_1800410C4
0x1800410d2  movzx   eax, word ptr [r15]
0x1800410d6  mov     [rbp+290h+var_248], ax
0x1800410da  lea     r9, [rsp+390h+var_328]
0x1800410df  lea     r8, [rsp+390h+var_330]
0x1800410e4  xor     edx, edx
0x1800410e6  lea     rcx, [rbp+290h+var_248]
0x1800410ea  call    cs:__imp_GetStorageDeviceSize
0x1800410f0  test    eax, eax
0x1800410f2  js      short loc_180041161
0x1800410f4  mov     rbx, [rsp+390h+var_330]
0x1800410f9  mov     rsi, [rsp+390h+var_328]
0x1800410fe  cmp     rbx, rsi
0x180041101  jbe     short loc_180041161
0x180041103  mov     [rsp+390h+NumberOfFreeClusters], 1
0x18004110b  lea     r8, [rsp+390h+NumberOfFreeClusters]
0x180041110  lea     rdx, [rbp+290h+RootPathName]
0x180041114  mov     rcx, rdi
0x180041117  call    ?find@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@2@AEBH@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::find(int const &)
0x18004111c  mov     rax, qword ptr [rbp+290h+RootPathName]
0x180041120  mov     r9, [rax+30h]
0x180041124  cmp     rax, [rdi+8]
0x180041128  jz      short loc_18004114C
0x18004112a  mov     rcx, rbx
0x18004112d  sub     rcx, rsi
0x180041130  cmp     r14, rcx
0x180041133  jnb     short loc_18004114C
0x180041135  sub     rcx, r14
0x180041138  lea     r8, [rcx+r9]
0x18004113c  mov     [rax+30h], r8
0x180041140  mov     rbx, [rsp+390h+var_330]
0x180041145  mov     rsi, [rsp+390h+var_328]
0x18004114a  jmp     short loc_18004114F
0x18004114c  mov     r8, r9; unsigned __int64
0x18004114f  sub     rbx, rsi
0x180041152  sub     rbx, r14
0x180041155  mov     rdx, rbx; unsigned __int64
0x180041158  mov     rcx, r9; unsigned __int64
0x18004115b  call    ?TelemetrySystemFilesSize@@YAX_K00@Z; TelemetrySystemFilesSize(unsigned __int64,unsigned __int64,unsigned __int64)
0x180041160  nop
0x180041161  mov     rcx, [rsp+390h+SRWLock]; SRWLock
0x180041166  test    rcx, rcx
0x180041169  jz      short loc_180041176
0x18004116b  call    cs:__imp_ReleaseSRWLockExclusive
0x180041171  mov     [rsp+390h+SRWLock], r12
0x180041176  mov     dl, 1
0x180041178  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions> `wil::Feature<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::GetImpl(void)'::`2'::impl
0x18004117f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageServiceFolderSuggestions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageServiceFolderSuggestions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180041184  mov     rcx, r15; lpRootPathName
0x180041187  call    cs:__imp_GetDriveTypeW
0x18004118d  cmp     eax, 3
0x180041190  jnz     short loc_18004119A
0x180041192  mov     rcx, rdi; this
0x180041195  call    ?FindMediaLibraryFolderSuggestions@CTreeWalker@@AEAAXXZ; CTreeWalker::FindMediaLibraryFolderSuggestions(void)
0x18004119a  mov     byte ptr [rdi+13Bh], 1
0x1800411a1  mov     rcx, [rbp+290h+var_30]
0x1800411a8  xor     rcx, rsp; StackCookie
0x1800411ab  call    __security_check_cookie
0x1800411b0  lea     r11, [rsp+390h+var_20]
0x1800411b8  mov     rbx, [r11+40h]
0x1800411bc  mov     rsi, [r11+48h]
0x1800411c0  mov     rsp, r11
0x1800411c3  pop     r15
0x1800411c5  pop     r14
0x1800411c7  pop     r12
0x1800411c9  pop     rdi
0x1800411ca  pop     rbp
0x1800411cb  retn
```
