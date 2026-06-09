# FontCacheStorage::CreateNewCache(DWrite::RefString const &,wchar_t const *,CacheWriter::CacheSizeParams,uint,uint,CacheWriter *,bool,bool)

- ea: `0x180041908`
- end: `0x180041d12`
- name: `?CreateNewCache@FontCacheStorage@@QEAAJAEBVRefString@DWrite@@PEB_WUCacheSizeParams@CacheWriter@@IIPEAV5@_N4@Z`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, const struct DWrite::RefString *, __int64, int, unsigned int, int, __int64, char, char)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f6ec`
- `0x180041d18`
- `0x1800b70ec`

## callees

- `0x1800086ac`
- `0x18000d55c`
- `0x18000e3f0`
- `0x18000e920`
- `0x18000f354`
- `0x18000f7bc`
- `0x180010d70`
- `0x180010dc4`
- `0x180010e24`
- `0x1800113a4`
- `0x180028c50`
- `0x180041734`
- `0x180041908`
- `0x180096a2c`
- `0x180099b28`
- `0x18009f830`
- `0x1800a3b30`
- `0x1800a3bc8`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c3f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041ced`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041ced`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180041b01`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180041b01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800419c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800419c6`

## string_xrefs

- `0x180041add`: `FontCache-Obsolete-*.dat`

## pseudocode

```c
__int64 __fastcall FontCacheStorage::CreateNewCache(
        __int64 a1,
        const struct DWrite::RefString *a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        char a8,
        char a9)
{
  __int64 v11; // r12
  DWORD dwLowDateTime; // ebx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  HANDLE FirstFileW; // rax
  int v18; // eax
  int v19; // r13d
  int v20; // edi
  __int64 v21; // rbx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-590h] BYREF
  struct DWrite::RefString::Data *v24; // [rsp+50h] [rbp-588h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-580h]
  int v26; // [rsp+5Ch] [rbp-57Ch]
  __int64 v27; // [rsp+60h] [rbp-578h]
  __int64 v28; // [rsp+68h] [rbp-570h]
  void *v29; // [rsp+70h] [rbp-568h] BYREF
  __int64 v30; // [rsp+78h] [rbp-560h]
  __int64 v31; // [rsp+80h] [rbp-558h]
  __int64 v32; // [rsp+88h] [rbp-550h]
  __int64 v33; // [rsp+90h] [rbp-548h]
  HANDLE hObject[3]; // [rsp+98h] [rbp-540h] BYREF
  void *v35[3]; // [rsp+B0h] [rbp-528h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-510h]
  char v37; // [rsp+D0h] [rbp-508h]
  _QWORD v38[2]; // [rsp+D8h] [rbp-500h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-4F0h]
  __int64 v40; // [rsp+F0h] [rbp-4E8h]
  _QWORD v41[5]; // [rsp+F8h] [rbp-4E0h] BYREF
  HANDLE v42; // [rsp+120h] [rbp-4B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+128h] [rbp-4B0h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp-258h] BYREF

  v28 = a3;
  v31 = a1;
  v33 = a1;
  v25 = a5;
  v26 = a6;
  v30 = a7;
  v32 = 0x676E697461657263LL;
  *(_QWORD *)(a1 + 24) = 0x676E697461657263LL;
  v27 = a1 + 16;
  EventLogger::LogEvent<EventTag>(a1 + 16, 0x656761726F7453LL, 0x6574617473LL, 0x676E697461657263LL);
  v11 = -1;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v24 = (struct DWrite::RefString::Data *)SystemTimeAsFileTime;
  dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
  memset(v35, 0, sizeof(v35));
  v36 = 0;
  v37 = 0;
  v13 = *(unsigned int *)(*(_QWORD *)a2 + 4LL);
  if ( (_DWORD)v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v28 + 2 * v14) );
    v38[0] = *(_QWORD *)a2 + 8LL;
    v38[1] = v13;
    v39 = v28;
    v40 = v14;
    DWrite::RefString::RefString(&v24, v38);
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v28 + 2 * v15) );
    v16 = *(_QWORD *)a2;
    LOWORD(v39) = 126;
    v41[0] = v16 + 8;
    v41[1] = *(unsigned int *)(v16 + 4);
    v41[2] = v39;
    v41[3] = v28;
    v41[4] = v15;
    DWrite::RefString::RefString(&SystemTimeAsFileTime, v41, v28);
    if ( FontCache::CombinePath(a2, L"FontCache-Obsolete-*.dat", FileName) )
    {
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      v42 = FirstFileW;
      while ( FirstFileW != (HANDLE)-1LL )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 && FontCache::CombinePath(a2, FindFileData.cFileName, FileName) )
          DeleteFileW(FileName);
        FileEnumerator::MoveNext((FileEnumerator *)&v42);
        FirstFileW = v42;
      }
    }
    FontCache::TryRenameAsObsolete((LPCWSTR)(*(_QWORD *)&SystemTimeAsFileTime + 8LL), a2);
    v18 = File::TryOpen(v35, *(_QWORD *)&SystemTimeAsFileTime + 8LL, 9);
    v19 = v27;
    if ( v18 < 0 )
    {
      EventLogger::LogEvent<long,EventTag,unsigned int>(v27, 1919906899, 1869771365, v18, 0x676E697461657263LL, 503);
    }
    else
    {
      v11 = (__int64)v35[0];
      dwLowDateTime = v36;
    }
    DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)&SystemTimeAsFileTime);
    DWrite::RefString::DecrementRef(v24);
  }
  else
  {
    v19 = v27;
  }
  FileMapping::FileMapping((FileMapping *)hObject, (void *)v11, v25);
  v20 = v26;
  CacheWriter::CreateNewServerCache((unsigned int)&v29, (unsigned int)hObject, dwLowDateTime, a4, v26, v30, a8, a9);
  v21 = v31;
  File::operator=(v31 + 32, v35);
  FileMapping::operator=(v21 + 72, hObject);
  IntrusivePtr<CacheWriter>::operator=(v21 + 96, &v29);
  *(_QWORD *)(v21 + 24) = 0x64657461657263LL;
  EventLogger::LogEvent<EventTag,unsigned int>(v19, 1919906899, 1952543859, 1634038371, v20);
  ReleaseReference<CacheWriter>(v29);
  if ( hObject[0] )
  {
    CloseHandle(hObject[0]);
    hObject[0] = 0;
    hObject[2] = 0;
  }
  File::Close((File *)v35);
  return 0;
}

```

## disassembly

```asm
0x180041908  push    rbx
0x18004190a  push    rsi
0x18004190b  push    rdi
0x18004190c  push    r12
0x18004190e  push    r13
0x180041910  push    r14
0x180041912  push    r15
0x180041914  sub     rsp, 5A0h
0x18004191b  mov     rax, cs:__security_cookie
0x180041922  xor     rax, rsp
0x180041925  mov     [rsp+5D8h+var_48], rax
0x18004192d  mov     r14, r9
0x180041930  mov     [rsp+5D8h+var_570], r8
0x180041935  mov     r13, rdx
0x180041938  mov     rax, rcx
0x18004193b  mov     [rsp+5D8h+var_558], rcx
0x180041943  mov     [rsp+5D8h+var_548], rcx
0x18004194b  mov     ecx, [rsp+5D8h+arg_20]
0x180041952  mov     dword ptr [rsp+5D8h+var_580], ecx
0x180041956  mov     ecx, [rsp+5D8h+arg_28]
0x18004195d  mov     dword ptr [rsp+5D8h+var_580+4], ecx
0x180041961  mov     rcx, [rsp+5D8h+arg_30]
0x180041969  mov     [rsp+5D8h+var_560], rcx
0x18004196e  xor     ebx, ebx
0x180041970  mov     rdi, 676E697461657263h
0x18004197a  mov     [rsp+5D8h+var_550], rdi
0x180041982  mov     [rax+18h], rdi
0x180041986  mov     r15, 6574617473h
0x180041990  add     rax, 10h
0x180041994  mov     [rsp+5D8h+var_578], rax
0x180041999  mov     rsi, 656761726F7453h
0x1800419a3  mov     r9, rdi
0x1800419a6  mov     r8, r15
0x1800419a9  mov     rdx, rsi
0x1800419ac  mov     rcx, rax
0x1800419af  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x1800419b4  mov     [rsp+5D8h+var_598], ebx
0x1800419b8  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800419bc  mov     qword ptr [rsp+5D8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800419c1  lea     rcx, [rsp+5D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800419c6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800419cc  mov     eax, [rsp+5D8h+SystemTimeAsFileTime.dwHighDateTime]
0x1800419d0  mov     dword ptr [rsp+5D8h+var_588+4], eax
0x1800419d4  mov     eax, [rsp+5D8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800419d8  mov     dword ptr [rsp+5D8h+var_588], eax
0x1800419dc  mov     rbx, [rsp+5D8h+var_588]
0x1800419e1  xor     r9d, r9d
0x1800419e4  mov     [rsp+5D8h+var_528], r9
0x1800419ec  mov     [rsp+5D8h+var_520], r9
0x1800419f4  mov     [rsp+5D8h+var_518], r9
0x1800419fc  mov     [rsp+5D8h+var_510], r9
0x180041a04  mov     [rsp+5D8h+var_508], r9b
0x180041a0c  mov     rax, [r13+0]
0x180041a10  mov     r8d, [rax+4]
0x180041a14  test    r8d, r8d
0x180041a17  jz      loc_180041C8A
0x180041a1d  mov     rcx, r12
0x180041a20  mov     rdx, [rsp+5D8h+var_570]
0x180041a25  inc     rcx
0x180041a28  cmp     [rdx+rcx*2], r9w
0x180041a2d  jnz     short loc_180041A25
0x180041a2f  add     rax, 8
0x180041a33  mov     [rsp+5D8h+var_500], rax
0x180041a3b  mov     [rsp+5D8h+var_4F8], r8
0x180041a43  mov     [rsp+5D8h+var_4F0], rdx
0x180041a4b  mov     [rsp+5D8h+var_4E8], rcx
0x180041a53  lea     rdx, [rsp+5D8h+var_500]
0x180041a5b  lea     rcx, [rsp+5D8h+var_588]
0x180041a60  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x180041a65  nop
0x180041a66  mov     rdx, r12
0x180041a69  mov     r8, [rsp+5D8h+var_570]
0x180041a6e  xor     eax, eax
0x180041a70  inc     rdx
0x180041a73  cmp     [r8+rdx*2], ax
0x180041a78  jnz     short loc_180041A70
0x180041a7a  mov     rcx, [r13+0]
0x180041a7e  mov     eax, 7Eh ; '~'
0x180041a83  mov     word ptr [rsp+5D8h+var_4F0], ax
0x180041a8b  lea     rax, [rcx+8]
0x180041a8f  mov     [rsp+5D8h+var_4E0], rax
0x180041a97  mov     eax, [rcx+4]
0x180041a9a  mov     [rsp+5D8h+var_4D8], rax
0x180041aa2  mov     rax, [rsp+5D8h+var_4F0]
0x180041aaa  mov     [rsp+5D8h+var_4D0], rax
0x180041ab2  mov     [rsp+5D8h+var_4C8], r8
0x180041aba  mov     [rsp+5D8h+var_4C0], rdx
0x180041ac2  lea     rdx, [rsp+5D8h+var_4E0]
0x180041aca  lea     rcx, [rsp+5D8h+SystemTimeAsFileTime]
0x180041acf  call    ??$?0V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t>,wchar_t const *>> const &)
0x180041ad4  nop
0x180041ad5  lea     r8, [rsp+5D8h+FileName]; wchar_t *
0x180041add  lea     rdx, aFontcacheObsol_0; "FontCache-Obsolete-*.dat"
0x180041ae4  mov     rcx, r13; struct DWrite::RefString *
0x180041ae7  call    ?CombinePath@FontCache@@KA_KAEBVRefString@DWrite@@PEB_WPEA_W@Z; FontCache::CombinePath(DWrite::RefString const &,wchar_t const *,wchar_t *)
0x180041aec  test    rax, rax
0x180041aef  jz      short loc_180041B18
0x180041af1  lea     rdx, [rsp+5D8h+FindFileData]; lpFindFileData
0x180041af9  lea     rcx, [rsp+5D8h+FileName]; lpFileName
0x180041b01  call    cs:__imp_FindFirstFileW
0x180041b07  mov     [rsp+5D8h+var_4B8], rax
0x180041b0f  cmp     rax, r12
0x180041b12  jnz     loc_180041CBE
0x180041b18  mov     rcx, qword ptr [rsp+5D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180041b1d  add     rcx, 8; lpExistingFileName
0x180041b21  mov     rdx, r13; struct DWrite::RefString *
0x180041b24  call    ?TryRenameAsObsolete@FontCache@@SAJPEB_WAEBVRefString@DWrite@@@Z; FontCache::TryRenameAsObsolete(wchar_t const *,DWrite::RefString const &)
0x180041b29  mov     rdx, qword ptr [rsp+5D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180041b2e  add     rdx, 8
0x180041b32  mov     r8d, 9
0x180041b38  lea     rcx, [rsp+5D8h+var_528]
0x180041b40  call    ?TryOpen@File@@QEAAJPEB_WW4OpenMode@1@@Z; File::TryOpen(wchar_t const *,File::OpenMode)
0x180041b45  mov     r13, [rsp+5D8h+var_578]
0x180041b4a  test    eax, eax
0x180041b4c  js      loc_180041C94
0x180041b52  mov     r12, [rsp+5D8h+var_528]
0x180041b5a  mov     rbx, [rsp+5D8h+var_510]
0x180041b62  mov     rcx, qword ptr [rsp+5D8h+SystemTimeAsFileTime.dwLowDateTime]; struct DWrite::RefString::Data *
0x180041b67  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180041b6c  nop
0x180041b6d  mov     rcx, [rsp+5D8h+var_588]; struct DWrite::RefString::Data *
0x180041b72  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180041b77  mov     r8d, dword ptr [rsp+5D8h+var_580]; unsigned __int64
0x180041b7c  mov     rdx, r12; void *
0x180041b7f  lea     rcx, [rsp+5D8h+hObject]; this
0x180041b87  call    ??0FileMapping@@QEAA@PEAX_K@Z; FileMapping::FileMapping(void *,unsigned __int64)
0x180041b8c  nop
0x180041b8d  mov     al, [rsp+5D8h+arg_40]
0x180041b94  mov     [rsp+5D8h+var_5A0], al
0x180041b98  mov     al, [rsp+5D8h+arg_38]
0x180041b9f  mov     [rsp+5D8h+var_5A8], al
0x180041ba3  mov     rax, [rsp+5D8h+var_560]
0x180041ba8  mov     [rsp+5D8h+var_5B0], rax
0x180041bad  mov     edi, dword ptr [rsp+5D8h+var_580+4]
0x180041bb1  mov     dword ptr [rsp+5D8h+var_5B8], edi
0x180041bb5  mov     r9, r14
0x180041bb8  mov     r8, rbx
0x180041bbb  lea     rdx, [rsp+5D8h+hObject]
0x180041bc3  lea     rcx, [rsp+5D8h+var_568]
0x180041bc8  call    ?CreateNewServerCache@CacheWriter@@SA?AV?$IntrusivePtr@VCacheWriter@@@@AEBVFileMapping@@VDateTime@@UCacheSizeParams@1@IPEAV1@_N4@Z; CacheWriter::CreateNewServerCache(FileMapping const &,DateTime,CacheWriter::CacheSizeParams,uint,CacheWriter *,bool,bool)
0x180041bcd  mov     rbx, [rsp+5D8h+var_558]
0x180041bd5  lea     rcx, [rbx+20h]
0x180041bd9  lea     rdx, [rsp+5D8h+var_528]
0x180041be1  call    ??4File@@QEAAAEAV0@$$QEAV0@@Z; File::operator=(File &&)
0x180041be6  lea     rcx, [rbx+48h]
0x180041bea  lea     rdx, [rsp+5D8h+hObject]
0x180041bf2  call    ??4FileMapping@@QEAAAEAV0@$$QEAV0@@Z; FileMapping::operator=(FileMapping &&)
0x180041bf7  lea     rcx, [rbx+60h]
0x180041bfb  lea     rdx, [rsp+5D8h+var_568]
0x180041c00  call    ??4?$IntrusivePtr@VCacheWriter@@@@QEAAAEAV0@$$QEAV0@@Z; IntrusivePtr<CacheWriter>::operator=(IntrusivePtr<CacheWriter> &&)
0x180041c05  mov     r9, 64657461657263h
0x180041c0f  mov     [rbx+18h], r9
0x180041c13  mov     dword ptr [rsp+5D8h+var_5B8], edi
0x180041c17  mov     r8, r15
0x180041c1a  mov     rdx, rsi
0x180041c1d  mov     rcx, r13
0x180041c20  call    ??$LogEvent@VEventTag@@I@EventLogger@@QEBAXVEventTag@@00I@Z; EventLogger::LogEvent<EventTag,uint>(EventTag,EventTag,EventTag,uint)
0x180041c25  mov     rcx, [rsp+5D8h+var_568]; void *
0x180041c2a  call    ??$ReleaseReference@VCacheWriter@@@@YAXPEAVCacheWriter@@@Z; ReleaseReference<CacheWriter>(CacheWriter *)
0x180041c2f  nop
0x180041c30  mov     rcx, [rsp+5D8h+hObject]; hObject
0x180041c38  xor     ebx, ebx
0x180041c3a  test    rcx, rcx
0x180041c3d  jz      short loc_180041C55
0x180041c3f  call    cs:__imp_CloseHandle
0x180041c45  mov     [rsp+5D8h+hObject], rbx
0x180041c4d  mov     [rsp+5D8h+var_530], rbx
0x180041c55  lea     rcx, [rsp+5D8h+var_528]; this
0x180041c5d  call    ?Close@File@@QEAAXXZ; File::Close(void)
0x180041c62  nop
0x180041c63  mov     eax, [rsp+5D8h+var_598]
0x180041c67  mov     rcx, [rsp+5D8h+var_48]
0x180041c6f  xor     rcx, rsp; StackCookie
0x180041c72  call    __security_check_cookie
0x180041c77  add     rsp, 5A0h
0x180041c7e  pop     r15
0x180041c80  pop     r14
0x180041c82  pop     r13
0x180041c84  pop     r12
0x180041c86  pop     rdi
0x180041c87  pop     rsi
0x180041c88  pop     rbx
0x180041c89  retn
0x180041c8a  mov     r13, [rsp+5D8h+var_578]
0x180041c8f  jmp     loc_180041B77
0x180041c94  mov     r8, 726F727265h
0x180041c9e  mov     dword ptr [rsp+5D8h+var_5B0], 1F7h
0x180041ca6  mov     [rsp+5D8h+var_5B8], rdi
0x180041cab  mov     r9d, eax
0x180041cae  mov     rdx, rsi
0x180041cb1  mov     rcx, r13
0x180041cb4  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x180041cb9  jmp     loc_180041B62
0x180041cbe  test    byte ptr [rsp+5D8h+FindFileData.dwFileAttributes], 10h
0x180041cc6  jnz     short loc_180041CF3
0x180041cc8  lea     r8, [rsp+5D8h+FileName]; wchar_t *
0x180041cd0  lea     rdx, [rsp+5D8h+FindFileData.cFileName]; wchar_t *
0x180041cd8  mov     rcx, r13; struct DWrite::RefString *
0x180041cdb  call    ?CombinePath@FontCache@@KA_KAEBVRefString@DWrite@@PEB_WPEA_W@Z; FontCache::CombinePath(DWrite::RefString const &,wchar_t const *,wchar_t *)
0x180041ce0  test    rax, rax
0x180041ce3  jz      short loc_180041CF3
0x180041ce5  lea     rcx, [rsp+5D8h+FileName]; lpFileName
0x180041ced  call    cs:__imp_DeleteFileW
0x180041cf3  lea     rcx, [rsp+5D8h+var_4B8]; this
0x180041cfb  call    ?MoveNext@FileEnumerator@@QEAA_NXZ; FileEnumerator::MoveNext(void)
0x180041d00  mov     rax, [rsp+5D8h+var_4B8]
0x180041d08  jmp     loc_180041B0F
0x180041d0d  jmp     loc_180041C63
```
