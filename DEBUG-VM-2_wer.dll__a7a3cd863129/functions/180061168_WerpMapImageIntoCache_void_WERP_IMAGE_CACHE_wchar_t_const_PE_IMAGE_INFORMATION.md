# WerpMapImageIntoCache(void * *,WERP_IMAGE_CACHE *,wchar_t const *,PE_IMAGE_INFORMATION *)

- ea: `0x180061168`
- end: `0x1800616c6`
- name: `?WerpMapImageIntoCache@@YAJPEAPEAXPEAUWERP_IMAGE_CACHE@@PEB_WPEAUPE_IMAGE_INFORMATION@@@Z`
- size: `1374`
- prototype: `int(void **, struct WERP_IMAGE_CACHE *, const wchar_t *, struct PE_IMAGE_INFORMATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x180044b14`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000d75c`
- `0x18000dad0`
- `0x180013730`
- `0x180016f98`
- `0x18002b7a4`
- `0x18002f678`
- `0x180061020`
- `0x180061168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061608`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061641`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061608`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061641`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006131b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006131b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800614ac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180061518`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800614ac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180061518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006128c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006139f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006128c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006139f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614e1`
- `ntdll!wcsrchr` at `0x1800615e6`
- `ntdll!wcsrchr` at `0x18006161f`
- `ntdll!wcsrchr` at `0x1800615e6`
- `ntdll!wcsrchr` at `0x18006161f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800612d9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800612d9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180061383`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180061383`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180061399`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180061399`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180061282`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180061282`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006123f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006123f`
- `dbghelp!RangeMapFree` at `0x18006149c`
- `dbghelp!RangeMapFree` at `0x18006149c`
- `dbghelp!RangeMapCreate` at `0x180061489`
- `dbghelp!RangeMapCreate` at `0x180061489`
- `dbghelp!RangeMapAddPeImageSections` at `0x1800614d7`
- `dbghelp!RangeMapAddPeImageSections` at `0x1800614d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WerpMapImageIntoCache(
        void **a1,
        struct WERP_IMAGE_CACHE *a2,
        const wchar_t *a3,
        struct PE_IMAGE_INFORMATION *a4)
{
  __int64 v8; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v11; // edi
  HANDLE v12; // rbx
  DWORD v13; // eax
  HANDLE FileMappingW; // r13
  DWORD v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  LPVOID v18; // rax
  const void *v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  int ImageInformation; // edi
  int v23; // eax
  int v24; // eax
  PVOID v25; // rax
  void *v26; // rcx
  DWORD v27; // eax
  DWORD v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // ecx
  __int64 v32; // xmm1_8
  __int64 v33; // rax
  DWORD LowPart; // eax
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  wchar_t *v37; // rax
  const wchar_t *v38; // rax
  wchar_t *v39; // rax
  const wchar_t *v40; // rax
  _QWORD *v41; // [rsp+40h] [rbp-79h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-71h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-69h] BYREF
  LARGE_INTEGER v44; // [rsp+58h] [rbp-61h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-59h] BYREF
  __int128 v46; // [rsp+68h] [rbp-51h] BYREF
  __int128 v47; // [rsp+78h] [rbp-41h]
  __int64 v48; // [rsp+88h] [rbp-31h]
  __int128 v49; // [rsp+90h] [rbp-29h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-19h]
  LPCWSTR lpFileName[13]; // [rsp+A8h] [rbp-11h] BYREF
  HANDLE v52; // [rsp+120h] [rbp+67h] BYREF

  FileSize.QuadPart = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  PerformanceCount.QuadPart = 0;
  v44.QuadPart = 0;
  *a1 = 0;
  hFile = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(lpFileName)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpFileName,
                           L"\\\\.\\GLOBALROOT",
                           14)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           lpFileName,
                           a3,
                           v8) )
  {
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
    return 2147942414LL;
  }
  FileW = CreateFileW(lpFileName[0], 0x80000000, 7u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  LastError = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(LastError);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  v12 = hFile;
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
LABEL_40:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
    return v11;
  }
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    v13 = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(v13);
    goto LABEL_40;
  }
  if ( FileSize.HighPart )
  {
    v11 = -805304060;
    goto LABEL_40;
  }
  if ( FileSize.LowPart < 0x148 )
  {
    v11 = -2147024703;
    goto LABEL_40;
  }
  FileMappingW = CreateFileMappingW(v12, 0, 8u, 0, 0, 0);
  v52 = FileMappingW;
  v15 = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(v15);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, 0);
  if ( (unsigned __int64)FileMappingW + 1 <= 1 )
  {
LABEL_39:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    goto LABEL_40;
  }
  v16 = HeapAlloc(g_hWerheap, 0, 0x40u);
  v17 = v16;
  if ( v16 )
  {
    *(_OWORD *)v16 = 0;
    v16[2] = 0;
    v16[3] = 0;
    *((_OWORD *)v16 + 2) = 0;
    v16[6] = 0;
    *((_DWORD *)v16 + 14) = 0;
  }
  else
  {
    v17 = 0;
  }
  v41 = v17;
  if ( !v17 )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147024882;
    goto LABEL_40;
  }
  v18 = MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
  v19 = (const void *)v17[2];
  v17[2] = v18;
  if ( v19 )
    UnmapViewOfFile(v19);
  v20 = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(v20);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v52, 0);
  v21 = v17[2];
  if ( !v21 )
  {
LABEL_38:
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    goto LABEL_39;
  }
  v47 = 0;
  *(_QWORD *)&v46 = &PepProtectedCopyMemory;
  *((_QWORD *)&v46 + 1) = v21;
  LODWORD(v47) = FileSize.LowPart;
  v48 = 2;
  ImageInformation = PeReadImageInformation((struct PE_IMAGE_INFORMATION *)&v49, (struct PE_FILE *)&v46);
  if ( ImageInformation < 0 )
  {
    v11 = ImageInformation | 0x10000000;
    goto LABEL_38;
  }
  if ( *(_DWORD *)a4 && *(_DWORD *)a4 != (_DWORD)v49 )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147022995;
    goto LABEL_40;
  }
  v23 = *((_DWORD *)a4 + 1);
  if ( v23 && v23 != DWORD1(v49) )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147023434;
    goto LABEL_40;
  }
  v24 = *((_DWORD *)a4 + 2);
  if ( v24 && v24 != DWORD2(v49) )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -805305823;
    goto LABEL_40;
  }
  v25 = RangeMapCreate();
  v26 = (void *)v17[3];
  v17[3] = v25;
  if ( v26 )
    RangeMapFree(v26);
  if ( !v17[3]
    || (QueryPerformanceCounter(&PerformanceCount),
        !RangeMapAddPeImageSections(
           (PVOID)v17[3],
           a3,
           (PVOID)v17[2],
           FileSize.LowPart,
           *((_QWORD *)a4 + 2),
           0,
           0xE0000005)) )
  {
    v27 = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(v27);
    goto LABEL_38;
  }
  QueryPerformanceCounter(&v44);
  v29 = FileSize.LowPart + *((_DWORD *)a2 + 5);
  if ( v29 < FileSize.LowPart )
    v29 = -1;
  if ( FileSize.LowPart < *((_DWORD *)a2 + 4) )
  {
    if ( v29 <= *((_DWORD *)a2 + 4) )
    {
      v31 = 0;
      goto LABEL_49;
    }
    v30 = v29 - *((_DWORD *)a2 + 4);
  }
  else
  {
    ++*((_DWORD *)a2 + 6);
    v30 = 0;
  }
  v31 = WerpFlushImageCache(a2, v30);
LABEL_49:
  v32 = *((_QWORD *)a4 + 2);
  *((_OWORD *)v17 + 2) = *(_OWORD *)a4;
  v17[6] = v32;
  *((_DWORD *)v17 + 14) = FileSize.LowPart;
  *a1 = (void *)v17[3];
  v41 = 0;
  v33 = *(_QWORD *)a2;
  if ( *(struct WERP_IMAGE_CACHE **)(*(_QWORD *)a2 + 8LL) != a2 )
    __fastfail(3u);
  *v17 = v33;
  v17[1] = a2;
  *(_QWORD *)(v33 + 8) = v17;
  *(_QWORD *)a2 = v17;
  LowPart = FileSize.LowPart;
  *((_DWORD *)a2 + 5) += FileSize.LowPart;
  ++*((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 7) += v31;
  *((_QWORD *)a2 + 23) += v44.QuadPart - PerformanceCount.QuadPart;
  v35 = *((_DWORD *)a2 + 9);
  if ( v35 <= *((_DWORD *)a2 + 8) )
    v35 = *((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 9) = v35;
  v36 = *((_DWORD *)a2 + 10);
  if ( v36 <= *((_DWORD *)a2 + 5) )
    v36 = *((_DWORD *)a2 + 5);
  *((_DWORD *)a2 + 10) = v36;
  if ( !*((_DWORD *)a2 + 11) || LowPart < *((_DWORD *)a2 + 11) )
  {
    *((_DWORD *)a2 + 11) = LowPart;
    v37 = wcsrchr(a3, 0x5Cu);
    if ( v37 )
      v38 = v37 + 1;
    else
      v38 = a3;
    _o_wcsncpy_s((char *)a2 + 52, 32, v38, -1);
    LowPart = FileSize.LowPart;
  }
  if ( LowPart > *((_DWORD *)a2 + 12) )
  {
    *((_DWORD *)a2 + 12) = LowPart;
    v39 = wcsrchr(a3, 0x5Cu);
    if ( v39 )
      v40 = v39 + 1;
    else
      v40 = a3;
    _o_wcsncpy_s((char *)a2 + 116, 32, v40, -1);
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1b05c2b80b7f37aefcd0b72690fdc185_Traceguids, a3);
  utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return 0;
}

```

## disassembly

```asm
0x180061168  push    rbp
0x18006116a  push    rbx
0x18006116b  push    rsi
0x18006116c  push    rdi
0x18006116d  push    r12
0x18006116f  push    r13
0x180061171  push    r14
0x180061173  push    r15
0x180061175  lea     rbp, [rsp-1Fh]
0x18006117a  sub     rsp, 0D8h
0x180061181  mov     r15, r9
0x180061184  mov     r14, r8
0x180061187  mov     rsi, rdx
0x18006118a  mov     r12, rcx
0x18006118d  xor     r13d, r13d
0x180061190  mov     qword ptr [rbp+57h+FileSize], r13
0x180061194  xorps   xmm0, xmm0
0x180061197  xor     eax, eax
0x180061199  movups  [rbp+57h+var_A8], xmm0
0x18006119d  movups  [rbp+57h+var_98], xmm0
0x1800611a1  mov     [rbp+57h+var_88], rax
0x1800611a5  movups  [rbp+57h+var_80], xmm0
0x1800611a9  mov     [rbp+57h+var_70], rax
0x1800611ad  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x1800611b1  mov     qword ptr [rbp+57h+var_B8], r13
0x1800611b5  mov     [rcx], r13
0x1800611b8  mov     [rbp+57h+hFile], r13
0x1800611bc  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800611c0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800611c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800611c9  inc     rbx
0x1800611cc  cmp     [r14+rbx*2], r13w
0x1800611d1  jnz     short loc_1800611C9
0x1800611d3  lea     rdx, [rbx+0Eh]
0x1800611d7  lea     rcx, [rbp+57h+lpFileName]
0x1800611db  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x1800611e0  test    al, al
0x1800611e2  jz      loc_18006169A
0x1800611e8  mov     r8d, 0Eh
0x1800611ee  mov     rdx, cs:off_1800AE9A8; "\\\\.\\GLOBALROOT"
0x1800611f5  lea     rcx, [rbp+57h+lpFileName]
0x1800611f9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800611fe  test    al, al
0x180061200  jz      loc_18006169A
0x180061206  mov     r8, rbx
0x180061209  mov     rdx, r14
0x18006120c  lea     rcx, [rbp+57h+lpFileName]
0x180061210  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180061215  test    al, al
0x180061217  jz      loc_18006169A
0x18006121d  mov     [rsp+110h+hTemplateFile], r13; hTemplateFile
0x180061222  mov     [rsp+110h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180061227  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18006122f  xor     r9d, r9d; lpSecurityAttributes
0x180061232  mov     edx, 80000000h; dwDesiredAccess
0x180061237  lea     r8d, [r9+7]; dwShareMode
0x18006123b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18006123f  call    cs:__imp_CreateFileW
0x180061245  mov     rdx, rax
0x180061248  lea     rcx, [rbp+57h+hFile]
0x18006124c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180061251  call    cs:__imp_GetLastError
0x180061257  mov     ecx, eax; unsigned int
0x180061259  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006125e  mov     edi, eax
0x180061260  lea     rcx, [rbp+57h+lpFileName]; void *
0x180061264  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180061269  mov     rbx, [rbp+57h+hFile]
0x18006126d  lea     rax, [rbx+1]
0x180061271  cmp     rax, 1
0x180061275  jbe     loc_180061504
0x18006127b  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x18006127f  mov     rcx, rbx; hFile
0x180061282  call    cs:__imp_GetFileSizeEx
0x180061288  test    eax, eax
0x18006128a  jnz     short loc_1800612A0
0x18006128c  call    cs:__imp_GetLastError
0x180061292  mov     ecx, eax; unsigned int
0x180061294  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180061299  mov     edi, eax
0x18006129b  jmp     loc_180061504
0x1800612a0  cmp     dword ptr [rbp+57h+FileSize+4], r13d
0x1800612a4  jz      short loc_1800612B0
0x1800612a6  mov     edi, 0D0000904h
0x1800612ab  jmp     loc_180061504
0x1800612b0  cmp     dword ptr [rbp+57h+FileSize], 148h
0x1800612b7  jnb     short loc_1800612C3
0x1800612b9  mov     edi, 800700C1h
0x1800612be  jmp     loc_180061504
0x1800612c3  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; lpName
0x1800612c8  mov     [rsp+110h+dwCreationDisposition], r13d; dwMaximumSizeLow
0x1800612cd  xor     r9d, r9d; dwMaximumSizeHigh
0x1800612d0  xor     edx, edx; lpFileMappingAttributes
0x1800612d2  lea     r8d, [r9+8]; flProtect
0x1800612d6  mov     rcx, rbx; hFile
0x1800612d9  call    cs:__imp_CreateFileMappingW
0x1800612df  mov     r13, rax
0x1800612e2  mov     [rbp+57h+arg_0], rax
0x1800612e6  call    cs:__imp_GetLastError
0x1800612ec  mov     ecx, eax; unsigned int
0x1800612ee  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800612f3  mov     edi, eax
0x1800612f5  xor     edx, edx
0x1800612f7  lea     rcx, [rbp+57h+hFile]
0x1800612fb  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180061300  lea     rcx, [r13+1]
0x180061304  cmp     rcx, 1
0x180061308  jbe     loc_1800614FA
0x18006130e  xor     edx, edx; dwFlags
0x180061310  lea     r8d, [rdx+40h]; dwBytes
0x180061314  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006131b  call    cs:__imp_HeapAlloc
0x180061321  mov     rbx, rax
0x180061324  xor     ecx, ecx
0x180061326  test    rax, rax
0x180061329  jz      short loc_180061348
0x18006132b  xorps   xmm0, xmm0
0x18006132e  movups  xmmword ptr [rax], xmm0
0x180061331  mov     [rax+10h], rcx
0x180061335  mov     [rax+18h], rcx
0x180061339  xor     eax, eax
0x18006133b  movups  xmmword ptr [rbx+20h], xmm0
0x18006133f  mov     [rbx+30h], rax
0x180061343  mov     [rbx+38h], ecx
0x180061346  jmp     short loc_18006134B
0x180061348  mov     rbx, rcx
0x18006134b  mov     [rbp+57h+var_D0], rbx
0x18006134f  test    rbx, rbx
0x180061352  jnz     short loc_180061371
0x180061354  lea     rcx, [rbp+57h+var_D0]
0x180061358  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x18006135d  nop
0x18006135e  lea     rcx, [rbp+57h+arg_0]
0x180061362  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180061367  mov     edi, 8007000Eh
0x18006136c  jmp     loc_180061504
0x180061371  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x180061376  xor     r9d, r9d; dwFileOffsetLow
0x180061379  xor     r8d, r8d; dwFileOffsetHigh
0x18006137c  lea     edx, [r9+1]; dwDesiredAccess
0x180061380  mov     rcx, r13; hFileMappingObject
0x180061383  call    cs:__imp_MapViewOfFile
0x180061389  mov     rcx, [rbx+10h]; lpBaseAddress
0x18006138d  mov     [rbx+10h], rax
0x180061391  xor     r13d, r13d
0x180061394  test    rcx, rcx
0x180061397  jz      short loc_18006139F
0x180061399  call    cs:__imp_UnmapViewOfFile
0x18006139f  call    cs:__imp_GetLastError
0x1800613a5  mov     ecx, eax; unsigned int
0x1800613a7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800613ac  mov     edi, eax
0x1800613ae  xor     edx, edx
0x1800613b0  lea     rcx, [rbp+57h+arg_0]
0x1800613b4  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800613b9  mov     rcx, [rbx+10h]
0x1800613bd  test    rcx, rcx
0x1800613c0  jz      loc_1800614F0
0x1800613c6  xorps   xmm0, xmm0
0x1800613c9  xor     eax, eax
0x1800613cb  movups  [rbp+57h+var_A8], xmm0
0x1800613cf  movups  [rbp+57h+var_98], xmm0
0x1800613d3  mov     [rbp+57h+var_88], rax
0x1800613d7  mov     eax, dword ptr [rbp+57h+FileSize]
0x1800613da  lea     rdx, PepProtectedCopyMemory
0x1800613e1  mov     qword ptr [rbp+57h+var_A8], rdx
0x1800613e5  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x1800613e9  mov     dword ptr [rbp+57h+var_98], eax
0x1800613ec  mov     dword ptr [rbp+57h+var_88], 2
0x1800613f3  lea     rdx, [rbp+57h+var_A8]; struct PE_FILE *
0x1800613f7  lea     rcx, [rbp+57h+var_80]; struct PE_IMAGE_INFORMATION *
0x1800613fb  call    ?PeReadImageInformation@@YAJPEAUPE_IMAGE_INFORMATION@@PEAUPE_FILE@@@Z; PeReadImageInformation(PE_IMAGE_INFORMATION *,PE_FILE *)
0x180061400  mov     edi, eax
0x180061402  test    eax, eax
0x180061404  jns     short loc_18006140F
0x180061406  bts     edi, 1Ch
0x18006140a  jmp     loc_1800614F0
0x18006140f  mov     eax, [r15]
0x180061412  test    eax, eax
0x180061414  jz      short loc_180061438
0x180061416  cmp     eax, dword ptr [rbp+57h+var_80]
0x180061419  jz      short loc_180061438
0x18006141b  lea     rcx, [rbp+57h+var_D0]
0x18006141f  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180061424  nop
0x180061425  lea     rcx, [rbp+57h+arg_0]
0x180061429  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006142e  mov     edi, 8007076Dh
0x180061433  jmp     loc_180061504
0x180061438  mov     eax, [r15+4]
0x18006143c  test    eax, eax
0x18006143e  jz      short loc_180061462
0x180061440  cmp     eax, dword ptr [rbp+57h+var_80+4]
0x180061443  jz      short loc_180061462
0x180061445  lea     rcx, [rbp+57h+var_D0]
0x180061449  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x18006144e  nop
0x18006144f  lea     rcx, [rbp+57h+arg_0]
0x180061453  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180061458  mov     edi, 800705B6h
0x18006145d  jmp     loc_180061504
0x180061462  mov     eax, [r15+8]
0x180061466  test    eax, eax
0x180061468  jz      short loc_180061489
0x18006146a  cmp     eax, dword ptr [rbp+57h+var_80+8]
0x18006146d  jz      short loc_180061489
0x18006146f  lea     rcx, [rbp+57h+var_D0]
0x180061473  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180061478  nop
0x180061479  lea     rcx, [rbp+57h+arg_0]
0x18006147d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180061482  mov     edi, 0D0000221h
0x180061487  jmp     short loc_180061504
0x180061489  call    cs:__imp_RangeMapCreate
0x18006148f  mov     rcx, [rbx+18h]; RmapHandle
0x180061493  mov     [rbx+18h], rax
0x180061497  test    rcx, rcx
0x18006149a  jz      short loc_1800614A2
0x18006149c  call    cs:__imp_RangeMapFree
0x1800614a2  cmp     [rbx+18h], r13
0x1800614a6  jz      short loc_1800614E1
0x1800614a8  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800614ac  call    cs:__imp_QueryPerformanceCounter
0x1800614b2  mov     dword ptr [rsp+110h+hTemplateFile], 0E0000005h; MappingFlags
0x1800614ba  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; UserTag
0x1800614bf  mov     rax, [r15+10h]
0x1800614c3  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ImageBase
0x1800614c8  mov     r9d, dword ptr [rbp+57h+FileSize]; MappingBytes
0x1800614cc  mov     r8, [rbx+10h]; MappedImage
0x1800614d0  mov     rdx, r14; ImageName
0x1800614d3  mov     rcx, [rbx+18h]; RmapHandle
0x1800614d7  call    cs:__imp_RangeMapAddPeImageSections
0x1800614dd  test    eax, eax
0x1800614df  jnz     short loc_180061514
0x1800614e1  call    cs:__imp_GetLastError
0x1800614e7  mov     ecx, eax; unsigned int
0x1800614e9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800614ee  mov     edi, eax
0x1800614f0  lea     rcx, [rbp+57h+var_D0]
0x1800614f4  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x1800614f9  nop
0x1800614fa  lea     rcx, [rbp+57h+arg_0]
0x1800614fe  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180061503  nop
0x180061504  lea     rcx, [rbp+57h+hFile]
0x180061508  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006150d  mov     eax, edi
0x18006150f  jmp     loc_1800616B2
0x180061514  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x180061518  call    cs:__imp_QueryPerformanceCounter
0x18006151e  mov     edx, [rsi+14h]
0x180061521  mov     rax, qword ptr [rbp+57h+FileSize]
0x180061525  add     edx, eax
0x180061527  or      ecx, 0FFFFFFFFh
0x18006152a  cmp     edx, eax
0x18006152c  cmovb   edx, ecx
0x18006152f  cmp     eax, [rsi+10h]
0x180061532  jb      short loc_18006153B
0x180061534  inc     dword ptr [rsi+18h]
0x180061537  xor     edx, edx
0x180061539  jmp     short loc_180061543
0x18006153b  cmp     edx, [rsi+10h]
0x18006153e  jbe     short loc_18006154F
0x180061540  sub     edx, [rsi+10h]; unsigned int
0x180061543  mov     rcx, rsi; struct WERP_IMAGE_CACHE *
0x180061546  call    ?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x18006154b  mov     ecx, eax
0x18006154d  jmp     short loc_180061552
0x18006154f  mov     ecx, r13d
0x180061552  movups  xmm0, xmmword ptr [r15]
0x180061556  movsd   xmm1, qword ptr [r15+10h]
0x18006155c  movups  xmmword ptr [rbx+20h], xmm0
0x180061560  movsd   qword ptr [rbx+30h], xmm1
0x180061565  mov     eax, dword ptr [rbp+57h+FileSize]
0x180061568  mov     [rbx+38h], eax
0x18006156b  mov     rax, [rbx+18h]
0x18006156f  mov     [r12], rax
0x180061573  mov     [rbp+57h+var_D0], r13
0x180061577  mov     rax, [rsi]
0x18006157a  cmp     [rax+8], rsi
0x18006157e  jz      short loc_180061587
0x180061580  mov     ecx, 3
0x180061585  int     29h; Win8: RtlFailFast(ecx)
0x180061587  mov     [rbx], rax
0x18006158a  mov     [rbx+8], rsi
0x18006158e  mov     [rax+8], rbx
0x180061592  mov     [rsi], rbx
0x180061595  mov     rax, qword ptr [rbp+57h+FileSize]
0x180061599  add     [rsi+14h], eax
0x18006159c  inc     dword ptr [rsi+20h]
0x18006159f  add     [rsi+1Ch], ecx
0x1800615a2  mov     rcx, qword ptr [rbp+57h+var_B8]
0x1800615a6  sub     rcx, qword ptr [rbp+57h+PerformanceCount]
0x1800615aa  add     [rsi+0B8h], rcx
0x1800615b1  mov     ecx, [rsi+24h]
0x1800615b4  cmp     ecx, [rsi+20h]
0x1800615b7  cmovbe  ecx, [rsi+20h]
0x1800615bb  mov     [rsi+24h], ecx
0x1800615be  mov     ecx, [rsi+28h]
0x1800615c1  cmp     ecx, [rsi+14h]
  ... truncated ...
```
