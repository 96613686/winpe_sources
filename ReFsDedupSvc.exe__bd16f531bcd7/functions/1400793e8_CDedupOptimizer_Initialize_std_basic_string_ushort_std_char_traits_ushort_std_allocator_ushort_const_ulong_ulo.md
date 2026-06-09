# CDedupOptimizer::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,RefsDedup::DedupInitializeFlags)

- ea: `0x1400793e8`
- end: `0x140079bb4`
- name: `?Initialize@CDedupOptimizer@@QEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKW4DedupInitializeFlags@RefsDedup@@@Z`
- size: `1996`
- prototype: `__int64 __fastcall(char *pv, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation`

## callers

- `0x14006293c`

## callees

- `0x140004870`
- `0x140004c6c`
- `0x1400057f8`
- `0x1400172f0`
- `0x140019600`
- `0x14001983c`
- `0x140023d88`
- `0x140041dc4`
- `0x14006224c`
- `0x14006251c`
- `0x140062a80`
- `0x1400635dc`
- `0x140063a2c`
- `0x140063bbc`
- `0x140064c9c`
- `0x140065e44`
- `0x140066468`
- `0x1400667a0`
- `0x140066b5c`
- `0x140066fa8`
- `0x140069d88`
- `0x140069dc8`
- `0x14006b9d0`
- `0x14006e690`
- `0x140074024`
- `0x140075e8c`
- `0x140077f6c`
- `0x1400793e8`
- `0x14007ac74`
- `0x14007b0dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400794be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007978f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400794be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007978f`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1400797e4`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1400797e4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400794ae`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400794ae`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14007977f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14007977f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140079705`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140079705`

## string_xrefs

- `0x140079600`: `ReFS dedup not supported on remotely mounted nodes, error = 0x%x\n`
- `0x140079a8d`: `Failed to initialize/open hash index, error = 0x%x\n`
- `0x140079919`: `Failed to create/verify dedup metadata directory, error = 0x%x\n`

## pseudocode

```c
__int64 __fastcall CDedupOptimizer::Initialize(char *pv, __int64 a2, __int64 a3, int a4, char a5)
{
  bool v8; // si
  const WCHAR *v10; // rax
  DWORD LastError; // ebx
  __int64 v12; // r8
  __int64 VolumeGuid; // rax
  __int64 v14; // r8
  char IsReFSVolume; // al
  int v16; // ecx
  char IsCsvVolume; // bl
  __int64 v18; // rcx
  __int64 v19; // rax
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  const unsigned __int16 *v32; // rax
  bool v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int MdsPathFromCsv; // [rsp+54h] [rbp-ACh] BYREF
  DWORD SectorsPerCluster; // [rsp+58h] [rbp-A8h] BYREF
  DWORD BytesPerSector; // [rsp+5Ch] [rbp-A4h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+60h] [rbp-A0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+80h] [rbp-80h]
  char v41; // [rsp+84h] [rbp-7Ch]
  unsigned int *v42; // [rsp+88h] [rbp-78h]
  char *v43; // [rsp+90h] [rbp-70h]
  bool *v44; // [rsp+98h] [rbp-68h]
  char v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h] BYREF
  int v47; // [rsp+B0h] [rbp-50h]
  char v48; // [rsp+B4h] [rbp-4Ch] BYREF
  _OWORD v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[32]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v51[3]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v52[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v53[32]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+170h] [rbp+70h] BYREF

  MdsPathFromCsv = 0;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  v33 = (a5 & 1) != 0;
  v8 = (a5 & 2) != 0;
  v42 = &MdsPathFromCsv;
  v43 = pv;
  v44 = &v33;
  v45 = 1;
  if ( !*(_QWORD *)(a2 + 16) )
    return 87;
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !GetVolumePathNameW(v10, szVolumePathName, 0x104u) )
  {
    LastError = GetLastError();
    if ( MdsPathFromCsv )
      CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
    return LastError;
  }
  std::wstring::wstring(v49, szVolumePathName);
  LOBYTE(v12) = 1;
  VolumeGuid = DedupUtil::GetVolumeGuid(v50, v49, v12);
  std::wstring::operator=(pv + 160, VolumeGuid);
  std::wstring::_Tidy_deallocate(v50);
  std::wstring::_Tidy_deallocate(v49);
  v14 = -1;
  do
    ++v14;
  while ( szVolumePathName[v14] );
  std::wstring::_Assign<unsigned short>(pv + 128, szVolumePathName);
  IsReFSVolume = DedupUtil::IsReFSVolume(pv + 160);
  pv[120] = IsReFSVolume;
  *((_DWORD *)pv + 56) = 1021;
  v16 = 0x100000;
  if ( a4 )
    v16 = a4;
  *((_DWORD *)pv + 57) = v16;
  if ( IsReFSVolume )
  {
    std::wstring::wstring(v49, szVolumePathName);
    IsCsvVolume = DedupUtil::IsCsvVolume(v49);
    std::wstring::_Tidy_deallocate(v49);
    if ( IsCsvVolume )
    {
      v49[0] = 0;
      v49[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v49[0]) = 0;
      std::wstring::wstring(v50, szVolumePathName);
      MdsPathFromCsv = DedupUtil::GetMdsPathFromCsv(v50, v49);
      std::wstring::_Tidy_deallocate(v50);
      if ( MdsPathFromCsv == 5990 )
      {
        DedupUtil::Print<unsigned short (&)[260],unsigned long &>(
          v18,
          L"ReFS dedup not supported on remotely mounted nodes, error = 0x%x\n",
          szVolumePathName,
          &MdsPathFromCsv);
        LastError = MdsPathFromCsv;
        std::wstring::_Tidy_deallocate(v49);
        if ( MdsPathFromCsv )
          CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
        return LastError;
      }
      if ( MdsPathFromCsv )
      {
        DedupUtil::Print<unsigned short (&)[260],unsigned long &>(
          v18,
          L"ReFS dedup not supported on %s, error = 0x%x\n",
          szVolumePathName,
          &MdsPathFromCsv);
        LastError = MdsPathFromCsv;
        std::wstring::_Tidy_deallocate(v49);
        if ( MdsPathFromCsv )
          CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
        return LastError;
      }
      pv[121] = 1;
      v19 = std::operator+<unsigned short>(v50, v49, L"\\");
      std::wstring::operator=(pv + 192, v19);
      std::wstring::_Tidy_deallocate(v50);
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 192);
      DedupUtil::Print<unsigned short const *>(0, L"%s is an ReFS Cluster Shared Volume\n", &v46);
      std::wstring::_Tidy_deallocate(v49);
    }
    else
    {
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 128);
      DedupUtil::Print<unsigned short const *>(0, L"%s is an ReFS volume.\n", &v46);
    }
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 160);
    if ( !GetDiskFreeSpaceExW(v20, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
    {
      MdsPathFromCsv = GetLastError();
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 128);
      DedupUtil::Print<unsigned short const *,unsigned long &>(
        0,
        L"Unable to query disk free space on %s, error = 0x%x\n",
        &v46,
        &MdsPathFromCsv);
      LastError = MdsPathFromCsv;
      if ( MdsPathFromCsv )
        CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
      return LastError;
    }
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 160);
    if ( !GetDiskFreeSpaceW(v21, &SectorsPerCluster, &BytesPerSector, 0, 0) )
    {
      MdsPathFromCsv = GetLastError();
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 128);
      DedupUtil::Print<unsigned short const *,unsigned long &>(
        6,
        L"Unable to query cluster and sector on %s, error = 0x%x\n",
        &v46,
        &MdsPathFromCsv);
      LastError = MdsPathFromCsv;
      if ( MdsPathFromCsv )
        CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
      return LastError;
    }
    *((_DWORD *)pv + 22) = GetActiveProcessorCount(0xFFFFu);
    v22 = operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
    v46 = (__int64)v22;
    if ( v22 )
      v23 = CHashIndex::CHashIndex(v22);
    else
      v23 = 0;
    v46 = 0;
    v24 = *((_QWORD *)pv + 29);
    *((_QWORD *)pv + 29) = v23;
    if ( v24 )
      utl::default_delete<CHashIndex>::operator()();
    utl::unique_ptr<CHashIndex,utl::default_delete<CHashIndex>>::~unique_ptr<CHashIndex,utl::default_delete<CHashIndex>>(&v46);
    if ( *((_QWORD *)pv + 29) )
    {
      *((union _ULARGE_INTEGER *)pv + 14) = TotalNumberOfFreeBytes;
      *((union _ULARGE_INTEGER *)pv + 13) = TotalNumberOfBytes;
      v25 = SectorsPerCluster * BytesPerSector;
      *((_DWORD *)pv + 62) = SectorsPerCluster * BytesPerSector;
      _BitScanForward(&v25, v25);
      *((_DWORD *)pv + 63) = v25;
      *((_DWORD *)pv + 60) = *((_DWORD *)pv + 62);
      DedupUtil::Print<unsigned long &>(0, L"Using %d byte chunk size\n");
      v46 = 0x1200000011LL;
      v47 = 28;
      *(_QWORD *)&v49[0] = &v46;
      *((_QWORD *)&v49[0] + 1) = &v48;
      std::vector<unsigned long>::operator=(pv + 264, v49);
      v39 = 0;
      v40 = 0;
      v41 = 0;
      DedupUtil::ScopedPrivileges::EnablePrivileges(&v39, pv + 264);
      MdsPathFromCsv = CDedupOptimizer::EnsureDedupMetadataDirectoryExists(v26, (__int64)(pv + 160));
      if ( MdsPathFromCsv )
      {
        DedupUtil::Print<unsigned long &>(
          6,
          L"Failed to create/verify dedup metadata directory, error = 0x%x\n",
          &MdsPathFromCsv);
        LastError = MdsPathFromCsv;
        DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v39);
        if ( MdsPathFromCsv )
          CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
        return LastError;
      }
      memset(v51, 0, sizeof(v51));
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 160);
      std::wstring::wstring(v50, v27);
      RefsDedup::IsEnabled(v50, v51);
      std::wstring::_Tidy_deallocate(v50);
      if ( BYTE5(v51[0]) )
      {
        if ( BYTE7(v51[0]) )
          v8 = 1;
      }
      else
      {
        v33 = 1;
      }
      v28 = std::operator+<unsigned short>(v51, pv + 160, L"System Volume Information");
      v29 = std::operator+<unsigned short>(v53, v28, L"\\");
      v30 = std::operator+<unsigned short>(v49, v29, L"NativeDedup");
      v31 = std::operator+<unsigned short>(v50, v30, L"\\");
      std::operator+<unsigned short>(v52, v31, L"DedupIndex.db");
      std::wstring::_Tidy_deallocate(v50);
      std::wstring::_Tidy_deallocate(v49);
      std::wstring::_Tidy_deallocate(v53);
      std::wstring::_Tidy_deallocate(v51);
      v32 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
      MdsPathFromCsv = CHashIndex::Initialize(
                         *((CHashIndex **)pv + 29),
                         v32,
                         *((_QWORD *)pv + 13),
                         *((_QWORD *)pv + 14),
                         *((_DWORD *)pv + 62),
                         *((_DWORD *)pv + 56),
                         *((_DWORD *)pv + 57),
                         v33,
                         a5 & 1);
      if ( MdsPathFromCsv )
      {
        DedupUtil::Print<unsigned long &>(6, L"Failed to initialize/open hash index, error = 0x%x\n", &MdsPathFromCsv);
        LastError = MdsPathFromCsv;
        std::wstring::_Tidy_deallocate(v52);
        DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v39);
        if ( MdsPathFromCsv )
          CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
        return LastError;
      }
      pv[475] = 0;
      if ( v8 )
      {
        *((_WORD *)pv + 236) = 0;
        LastError = CDedupOptimizer::ScrubAsync(pv);
        MdsPathFromCsv = LastError;
        if ( LastError )
        {
          std::wstring::_Tidy_deallocate(v52);
          DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v39);
          if ( MdsPathFromCsv )
            CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
          return LastError;
        }
      }
      std::wstring::_Tidy_deallocate(v52);
      DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v39);
      if ( MdsPathFromCsv )
        CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
      return 0;
    }
    else
    {
      if ( MdsPathFromCsv )
        CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
      return 8;
    }
  }
  else
  {
    v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 128);
    DedupUtil::Print<unsigned short const *>(0, L"%s is not an ReFS volume, dedup not supported!\n", &v46);
    if ( MdsPathFromCsv )
      CDedupOptimizer::Uninitialize((CDedupOptimizer *)pv, v33);
    return 50;
  }
}

```

## disassembly

```asm
0x1400793e8  mov     [rsp-8+arg_10], rbx
0x1400793ed  push    rbp
0x1400793ee  push    rsi
0x1400793ef  push    rdi
0x1400793f0  push    r12
0x1400793f2  push    r13
0x1400793f4  push    r14
0x1400793f6  push    r15
0x1400793f8  lea     rbp, [rsp-290h]
0x140079400  sub     rsp, 390h
0x140079407  mov     rax, cs:__security_cookie
0x14007940e  xor     rax, rsp
0x140079411  mov     [rbp+2C0h+var_40], rax
0x140079418  mov     r12d, r9d
0x14007941b  mov     rbx, rdx
0x14007941e  mov     rdi, rcx
0x140079421  xor     r14d, r14d
0x140079424  mov     [rsp+3C0h+var_36C], r14d
0x140079429  mov     [rsp+3C0h+var_370], r14b
0x14007942e  mov     [rsp+3C0h+SectorsPerCluster], r14d
0x140079433  mov     [rsp+3C0h+BytesPerSector], r14d
0x140079438  mov     qword ptr [rsp+3C0h+TotalNumberOfBytes], r14
0x14007943d  mov     qword ptr [rsp+3C0h+TotalNumberOfFreeBytes], r14
0x140079442  xor     edx, edx; Val
0x140079444  mov     r8d, 208h; Size
0x14007944a  lea     rcx, [rbp+2C0h+szVolumePathName]; void *
0x14007944e  call    memset_0
0x140079453  mov     esi, [rbp+2C0h+arg_20]
0x140079459  mov     r13d, esi
0x14007945c  lea     r15d, [r14+1]
0x140079460  and     r13d, r15d
0x140079463  jz      short loc_14007946A
0x140079465  mov     [rsp+3C0h+var_370], r15b
0x14007946a  shr     esi, 1
0x14007946c  and     sil, r15b
0x14007946f  lea     rax, [rsp+3C0h+var_36C]
0x140079474  mov     [rbp+2C0h+var_338], rax
0x140079478  mov     [rbp+2C0h+var_330], rdi
0x14007947c  lea     rax, [rsp+3C0h+var_370]
0x140079481  mov     [rbp+2C0h+var_328], rax
0x140079485  mov     [rbp+2C0h+var_320], r15b
0x140079489  cmp     [rbx+10h], r14
0x14007948d  jnz     short loc_140079499
0x14007948f  mov     eax, 57h ; 'W'
0x140079494  jmp     loc_140079B89
0x140079499  mov     rcx, rbx
0x14007949c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400794a1  mov     r8d, 104h; cchBufferLength
0x1400794a7  lea     rdx, [rbp+2C0h+szVolumePathName]; lpszVolumePathName
0x1400794ab  mov     rcx, rax; lpszFileName
0x1400794ae  call    cs:__imp_GetVolumePathNameW
0x1400794b5  nop     dword ptr [rax+rax+00h]
0x1400794ba  test    eax, eax
0x1400794bc  jnz     short loc_1400794E7
0x1400794be  call    cs:__imp_GetLastError
0x1400794c5  nop     dword ptr [rax+rax+00h]
0x1400794ca  mov     ebx, eax
0x1400794cc  cmp     [rsp+3C0h+var_36C], r14d
0x1400794d1  jz      short loc_1400794E0
0x1400794d3  mov     dl, [rsp+3C0h+var_370]; bool
0x1400794d7  mov     rcx, rdi; this
0x1400794da  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x1400794df  nop
0x1400794e0  mov     eax, ebx
0x1400794e2  jmp     loc_140079B89
0x1400794e7  lea     rdx, [rbp+2C0h+szVolumePathName]
0x1400794eb  lea     rcx, [rbp+2C0h+var_300]
0x1400794ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400794f4  nop
0x1400794f5  mov     r8b, r15b
0x1400794f8  lea     rdx, [rbp+2C0h+var_300]
0x1400794fc  lea     rcx, [rbp+2C0h+var_2E0]
0x140079500  call    ?GetVolumeGuid@DedupUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DedupUtil::GetVolumeGuid(std::wstring const &,bool)
0x140079505  lea     r15, [rdi+0A0h]
0x14007950c  mov     rdx, rax
0x14007950f  mov     rcx, r15
0x140079512  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140079517  lea     rcx, [rbp+2C0h+var_2E0]
0x14007951b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140079520  nop
0x140079521  lea     rcx, [rbp+2C0h+var_300]
0x140079525  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007952a  lea     rax, [rbp+2C0h+szVolumePathName]
0x14007952e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140079532  inc     r8
0x140079535  cmp     [rax+r8*2], r14w
0x14007953a  jnz     short loc_140079532
0x14007953c  lea     r14, [rdi+80h]
0x140079543  lea     rdx, [rbp+2C0h+szVolumePathName]
0x140079547  mov     rcx, r14
0x14007954a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14007954f  mov     rcx, r15
0x140079552  call    ?IsReFSVolume@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DedupUtil::IsReFSVolume(std::wstring const &)
0x140079557  mov     [rdi+78h], al
0x14007955a  mov     dword ptr [rdi+0E0h], 3FDh
0x140079564  mov     ecx, 100000h
0x140079569  test    r12d, r12d
0x14007956c  cmovnz  ecx, r12d
0x140079570  mov     [rdi+0E4h], ecx
0x140079576  xor     r12d, r12d
0x140079579  test    al, al
0x14007957b  jz      loc_140079B51
0x140079581  lea     rdx, [rbp+2C0h+szVolumePathName]
0x140079585  lea     rcx, [rbp+2C0h+var_300]
0x140079589  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14007958e  nop
0x14007958f  lea     rcx, [rbp+2C0h+var_300]
0x140079593  call    ?IsCsvVolume@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DedupUtil::IsCsvVolume(std::wstring const &)
0x140079598  mov     bl, al
0x14007959a  lea     rcx, [rbp+2C0h+var_300]
0x14007959e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400795a3  test    bl, bl
0x1400795a5  jz      loc_1400796D0
0x1400795ab  xorps   xmm0, xmm0
0x1400795ae  movups  [rbp+2C0h+var_300], xmm0
0x1400795b2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400795ba  movdqu  [rbp+2C0h+var_2F0], xmm1
0x1400795bf  mov     word ptr [rbp+2C0h+var_300], r12w
0x1400795c4  lea     rdx, [rbp+2C0h+szVolumePathName]
0x1400795c8  lea     rcx, [rbp+2C0h+var_2E0]
0x1400795cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400795d1  nop
0x1400795d2  lea     rdx, [rbp+2C0h+var_300]
0x1400795d6  lea     rcx, [rbp+2C0h+var_2E0]
0x1400795da  call    ?GetMdsPathFromCsv@DedupUtil@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DedupUtil::GetMdsPathFromCsv(std::wstring const &,std::wstring &)
0x1400795df  mov     [rsp+3C0h+var_36C], eax
0x1400795e3  lea     rcx, [rbp+2C0h+var_2E0]
0x1400795e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400795ec  mov     eax, [rsp+3C0h+var_36C]
0x1400795f0  cmp     eax, 1766h
0x1400795f5  jnz     short loc_140079633
0x1400795f7  lea     r9, [rsp+3C0h+var_36C]
0x1400795fc  lea     r8, [rbp+2C0h+szVolumePathName]
0x140079600  lea     rdx, aRefsDedupNotSu; "ReFS dedup not supported on remotely mo"...
0x140079607  call    ??$Print@AEAY0BAE@GAEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAY0BAE@GAEAK@Z; DedupUtil::Print<ushort (&)[260],ulong &>(DedupUtil::MessageType,ushort const *,ushort (&)[260],ulong &)
0x14007960c  mov     ebx, [rsp+3C0h+var_36C]
0x140079610  lea     rcx, [rbp+2C0h+var_300]
0x140079614  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140079619  nop
0x14007961a  cmp     [rsp+3C0h+var_36C], r12d
0x14007961f  jz      short loc_14007962E
0x140079621  mov     dl, [rsp+3C0h+var_370]; bool
0x140079625  mov     rcx, rdi; this
0x140079628  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x14007962d  nop
0x14007962e  jmp     loc_1400794E0
0x140079633  test    eax, eax
0x140079635  jz      short loc_140079673
0x140079637  lea     r9, [rsp+3C0h+var_36C]
0x14007963c  lea     r8, [rbp+2C0h+szVolumePathName]
0x140079640  lea     rdx, aRefsDedupNotSu_0; "ReFS dedup not supported on %s, error ="...
0x140079647  call    ??$Print@AEAY0BAE@GAEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAY0BAE@GAEAK@Z; DedupUtil::Print<ushort (&)[260],ulong &>(DedupUtil::MessageType,ushort const *,ushort (&)[260],ulong &)
0x14007964c  mov     ebx, [rsp+3C0h+var_36C]
0x140079650  lea     rcx, [rbp+2C0h+var_300]
0x140079654  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140079659  nop
0x14007965a  cmp     [rsp+3C0h+var_36C], r12d
0x14007965f  jz      short loc_14007966E
0x140079661  mov     dl, [rsp+3C0h+var_370]; bool
0x140079665  mov     rcx, rdi; this
0x140079668  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x14007966d  nop
0x14007966e  jmp     loc_1400794E0
0x140079673  mov     byte ptr [rdi+79h], 1
0x140079677  lea     r8, StringValue; "\\"
0x14007967e  lea     rdx, [rbp+2C0h+var_300]
0x140079682  lea     rcx, [rbp+2C0h+var_2E0]
0x140079686  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007968b  lea     rbx, [rdi+0C0h]
0x140079692  mov     rdx, rax
0x140079695  mov     rcx, rbx
0x140079698  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14007969d  lea     rcx, [rbp+2C0h+var_2E0]
0x1400796a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400796a6  mov     rcx, rbx
0x1400796a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400796ae  mov     [rbp+2C0h+var_318], rax
0x1400796b2  lea     r8, [rbp+2C0h+var_318]
0x1400796b6  lea     rdx, aSIsAnRefsClust; "%s is an ReFS Cluster Shared Volume\n"
0x1400796bd  xor     ecx, ecx
0x1400796bf  call    ??$Print@PEBG@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG@Z; DedupUtil::Print<ushort const *>(DedupUtil::MessageType,ushort const *,ushort const * &&)
0x1400796c4  nop
0x1400796c5  lea     rcx, [rbp+2C0h+var_300]
0x1400796c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400796ce  jmp     short loc_1400796EE
0x1400796d0  mov     rcx, r14
0x1400796d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400796d8  mov     [rbp+2C0h+var_318], rax
0x1400796dc  lea     r8, [rbp+2C0h+var_318]
0x1400796e0  lea     rdx, aSIsAnRefsVolum; "%s is an ReFS volume.\n"
0x1400796e7  xor     ecx, ecx
0x1400796e9  call    ??$Print@PEBG@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG@Z; DedupUtil::Print<ushort const *>(DedupUtil::MessageType,ushort const *,ushort const * &&)
0x1400796ee  mov     rcx, r15
0x1400796f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400796f6  lea     r9, [rsp+3C0h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1400796fb  lea     r8, [rsp+3C0h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x140079700  xor     edx, edx; lpFreeBytesAvailableToCaller
0x140079702  mov     rcx, rax; lpDirectoryName
0x140079705  call    cs:__imp_GetDiskFreeSpaceExW
0x14007970c  nop     dword ptr [rax+rax+00h]
0x140079711  test    eax, eax
0x140079713  jnz     short loc_140079762
0x140079715  call    cs:__imp_GetLastError
0x14007971c  nop     dword ptr [rax+rax+00h]
0x140079721  mov     [rsp+3C0h+var_36C], eax
0x140079725  mov     rcx, r14
0x140079728  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14007972d  mov     [rbp+2C0h+var_318], rax
0x140079731  lea     r9, [rsp+3C0h+var_36C]
0x140079736  lea     r8, [rbp+2C0h+var_318]
0x14007973a  lea     rdx, aUnableToQueryD; "Unable to query disk free space on %s, "...
0x140079741  xor     ecx, ecx
0x140079743  call    ??$Print@PEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAK@Z; DedupUtil::Print<ushort const *,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &)
0x140079748  mov     ebx, [rsp+3C0h+var_36C]
0x14007974c  test    ebx, ebx
0x14007974e  jz      short loc_14007975D
0x140079750  mov     dl, [rsp+3C0h+var_370]; bool
0x140079754  mov     rcx, rdi; this
0x140079757  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x14007975c  nop
0x14007975d  jmp     loc_1400794E0
0x140079762  mov     rcx, r15
0x140079765  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14007976a  mov     [rsp+3C0h+lpTotalNumberOfClusters], r12; lpTotalNumberOfClusters
0x14007976f  xor     r9d, r9d; lpNumberOfFreeClusters
0x140079772  lea     r8, [rsp+3C0h+BytesPerSector]; lpBytesPerSector
0x140079777  lea     rdx, [rsp+3C0h+SectorsPerCluster]; lpSectorsPerCluster
0x14007977c  mov     rcx, rax; lpRootPathName
0x14007977f  call    cs:__imp_GetDiskFreeSpaceW
0x140079786  nop     dword ptr [rax+rax+00h]
0x14007978b  test    eax, eax
0x14007978d  jnz     short loc_1400797DF
0x14007978f  call    cs:__imp_GetLastError
0x140079796  nop     dword ptr [rax+rax+00h]
0x14007979b  mov     [rsp+3C0h+var_36C], eax
0x14007979f  mov     rcx, r14
0x1400797a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400797a7  mov     [rbp+2C0h+var_318], rax
0x1400797ab  lea     r9, [rsp+3C0h+var_36C]
0x1400797b0  lea     r8, [rbp+2C0h+var_318]
0x1400797b4  lea     rdx, aUnableToQueryC; "Unable to query cluster and sector on %"...
0x1400797bb  mov     ecx, 6
0x1400797c0  call    ??$Print@PEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAK@Z; DedupUtil::Print<ushort const *,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &)
0x1400797c5  mov     ebx, [rsp+3C0h+var_36C]
0x1400797c9  test    ebx, ebx
0x1400797cb  jz      short loc_1400797DA
0x1400797cd  mov     dl, [rsp+3C0h+var_370]; bool
0x1400797d1  mov     rcx, rdi; this
0x1400797d4  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x1400797d9  nop
0x1400797da  jmp     loc_1400794E0
0x1400797df  mov     ecx, 0FFFFh; GroupNumber
0x1400797e4  call    cs:__imp_GetActiveProcessorCount
0x1400797eb  nop     dword ptr [rax+rax+00h]
0x1400797f0  mov     [rdi+58h], eax
0x1400797f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400797fa  mov     ecx, 160h; unsigned __int64
0x1400797ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140079804  mov     [rbp+2C0h+var_318], rax
0x140079808  test    rax, rax
0x14007980b  jz      short loc_140079817
0x14007980d  mov     rcx, rax
0x140079810  call    ??0CHashIndex@@QEAA@W4DatabaseEngine@@W4SecureHashAlgorithm@@HW4FastHashAlgorithm@@@Z; CHashIndex::CHashIndex(DatabaseEngine,SecureHashAlgorithm,int,FastHashAlgorithm)
0x140079815  jmp     short loc_14007981A
0x140079817  mov     rax, r12
0x14007981a  mov     [rbp+2C0h+var_318], r12
0x14007981e  mov     rdx, [rdi+0E8h]
0x140079825  mov     [rdi+0E8h], rax
0x14007982c  test    rdx, rdx
0x14007982f  jz      short loc_140079836
0x140079831  call    ??R?$default_delete@VCHashIndex@@@utl@@QEBAXPEAVCHashIndex@@@Z; utl::default_delete<CHashIndex>::operator()(CHashIndex *)
0x140079836  lea     rcx, [rbp+2C0h+var_318]
0x14007983a  call    ??1?$unique_ptr@VCHashIndex@@U?$default_delete@VCHashIndex@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CHashIndex,utl::default_delete<CHashIndex>>::~unique_ptr<CHashIndex,utl::default_delete<CHashIndex>>(void)
0x14007983f  cmp     [rdi+0E8h], r12
0x140079846  jnz     short loc_140079866
0x140079848  cmp     [rsp+3C0h+var_36C], r12d
0x14007984d  jz      short loc_14007985C
0x14007984f  mov     dl, [rsp+3C0h+var_370]; bool
0x140079853  mov     rcx, rdi; this
0x140079856  call    ?Uninitialize@CDedupOptimizer@@QEAAX_N@Z; CDedupOptimizer::Uninitialize(bool)
0x14007985b  nop
0x14007985c  mov     eax, 8
0x140079861  jmp     loc_140079B89
0x140079866  mov     rax, qword ptr [rsp+3C0h+TotalNumberOfFreeBytes]
0x14007986b  mov     [rdi+70h], rax
0x14007986f  mov     rax, qword ptr [rsp+3C0h+TotalNumberOfBytes]
0x140079874  mov     [rdi+68h], rax
0x140079878  mov     eax, [rsp+3C0h+BytesPerSector]
0x14007987c  imul    eax, [rsp+3C0h+SectorsPerCluster]
0x140079881  mov     [rdi+0F8h], eax
0x140079887  bsf     eax, eax
0x14007988a  mov     [rdi+0FCh], eax
0x140079890  lea     r8, [rdi+0F0h]
0x140079897  mov     eax, [rdi+0F8h]
0x14007989d  mov     [r8], eax
0x1400798a0  lea     rdx, aUsingDByteChun; "Using %d byte chunk size\n"
0x1400798a7  xor     ecx, ecx
0x1400798a9  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x1400798ae  mov     dword ptr [rbp+2C0h+var_318], 11h
0x1400798b5  mov     dword ptr [rbp+2C0h+var_318+4], 12h
  ... truncated ...
```
