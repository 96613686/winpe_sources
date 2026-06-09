# ProcessPath

- ea: `0x1800d56f8`
- end: `0x1800d5b1b`
- name: `ProcessPath`
- size: `1059`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64 *, const char *, __int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d56f8`
- `0x1800d648c`

## callees

- `0x1800238d0`
- `0x180024fd0`
- `0x18002c020`
- `0x18005f060`
- `0x1800d1d50`
- `0x1800d56f8`
- `0x1800d5b24`
- `0x1800d5bdc`
- `0x1800d6a5c`
- `0x1800d6ba8`
- `0x1801201a0`
- `0x180120c94`
- `0x180141c08`
- `0x180178038`
- `0x1801a8948`
- `0x1801ac1e0`
- `0x1801ac280`
- `0x1801ac2d4`
- `0x1801ac450`
- `0x1801ac48c`
- `0x1801ac988`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d57c3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d57c3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d5ad2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d5ad2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d58f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d58f1`

## string_xrefs

- `0x1800d5762`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1800d57e7`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`

## pseudocode

```c
__int64 __fastcall ProcessPath(_QWORD *a1, _QWORD *a2, __int64 *a3, const char *a4, __int64 a5)
{
  IdGenerator *v5; // r12
  __int64 *v6; // r15
  _QWORD *v7; // rsi
  _QWORD *v8; // r13
  __int64 v9; // r14
  __int64 *v10; // rdi
  const WCHAR *v11; // rcx
  const unsigned __int16 *v12; // rdx
  char *FirstFileW; // rbx
  const char *v14; // r9
  __int64 v15; // rax
  __int64 ItemId; // rax
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // r9
  __int64 v22; // r8
  _QWORD *v23; // r9
  __int64 v24; // r8
  wil *v25; // rcx
  int v27; // edx
  int v28; // ecx
  int v29; // edi
  __int64 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r10
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  char v36; // bl
  __int64 v37; // rax
  __int64 v38; // r8
  _BYTE v39[32]; // [rsp+0h] [rbp-578h] BYREF
  int v40; // [rsp+30h] [rbp-548h]
  _QWORD *v41; // [rsp+38h] [rbp-540h]
  _QWORD *v42; // [rsp+40h] [rbp-538h]
  __int64 *v43; // [rsp+48h] [rbp-530h]
  __int64 v44; // [rsp+50h] [rbp-528h]
  char *v45; // [rsp+58h] [rbp-520h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp-518h] BYREF
  _QWORD v47[2]; // [rsp+68h] [rbp-510h] BYREF
  _QWORD *v48; // [rsp+78h] [rbp-500h]
  const char *v49; // [rsp+80h] [rbp-4F8h]
  _BYTE v50[224]; // [rsp+90h] [rbp-4E8h] BYREF
  char v51; // [rsp+170h] [rbp-408h]
  char v52[8]; // [rsp+180h] [rbp-3F8h] BYREF
  char v53[24]; // [rsp+188h] [rbp-3F0h] BYREF
  _BYTE v54[32]; // [rsp+1A0h] [rbp-3D8h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+1C0h] [rbp-3B8h] BYREF
  _BYTE v56[32]; // [rsp+1E0h] [rbp-398h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+200h] [rbp-378h] BYREF
  _BYTE v58[224]; // [rsp+450h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+0h]

  v5 = (IdGenerator *)a4;
  v6 = a3;
  v7 = a2;
  v41 = a2;
  v8 = a1;
  v9 = a5;
  v48 = a1;
  v42 = a2;
  v10 = a3;
  v43 = a3;
  v49 = a4;
  v44 = a5;
  if ( !a5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      a4);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  std::operator+<unsigned short>(lpFileName, v6, L"\\*");
  v11 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v11 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v11, &FindFileData);
  v45 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      v14);
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( *((_DWORD *)v5 + 32) < 4u && !wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v12) )
      {
        v15 = std::operator+<unsigned short>(v56, v10, L"\\");
        std::operator+<unsigned short>(v54, v15, FindFileData.cFileName);
        std::wstring::~wstring(v56);
        std::wstring::wstring(v52);
        IdGenerator::PushNext(v5, v52);
        std::wstring::~wstring(v52);
        ProcessPath(v8, v7, v54, v5, v9);
        IdGenerator::PopLast(v5);
        std::wstring::~wstring(v54);
      }
    }
    else if ( CompareStringOrdinal(FindFileData.cFileName, -1, L"data.dat", -1, 1) == 2 )
    {
      try
      {
        v51 = 0;
        v40 = 2;
        ItemId = IdGenerator::GetItemId(v5, v58);
        std::_Optional_construct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>::_Assign<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>(
          v50,
          ItemId);
        Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId((Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *)v58);
        v17 = std::optional<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>::value(v50);
        v40 = 4;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v8 + 120LL))(*v8, v17) )
        {
          if ( (Microsoft_Windows_CloudStoreEnableBits & 0x10) != 0 )
          {
            v23 = (_QWORD *)(v17 + 192);
            if ( *(_QWORD *)(v17 + 216) > 0xFu )
              v23 = (_QWORD *)*v23;
            if ( (unsigned __int64)v10[3] <= 7 )
              v24 = (__int64)v10;
            else
              v24 = *v6;
            McTemplateU0zs_EventWriteTransfer(v18, InitEarlyDownloadItemSkipped, v24, v23);
          }
          ++*(_DWORD *)(v9 + 8);
        }
        else
        {
          v40 = 1;
          v19 = std::operator+<unsigned short>(v56, v10, L"\\");
          std::operator+<unsigned short>(v54, v19, FindFileData.cFileName);
          std::wstring::~wstring(v56);
          ReadBase64EncodedFileIntoBlob(v52, (__int64)v54);
          v40 = 3;
          (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v8 + 40LL))(*v8, v17, v52);
          if ( (Microsoft_Windows_CloudStoreEnableBits & 0x10) != 0 )
          {
            v21 = (_QWORD *)(v17 + 192);
            if ( *(_QWORD *)(v17 + 216) > 0xFu )
              v21 = (_QWORD *)*v21;
            if ( (unsigned __int64)v10[3] <= 7 )
              v22 = (__int64)v10;
            else
              v22 = *v6;
            McTemplateU0zs_EventWriteTransfer(v20, InitEarlyDownloadItemProcessed, v22, v21);
          }
          boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v53);
          std::wstring::~wstring(v54);
        }
        std::_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>::~_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>(v50);
        v7 = v41;
      }
      catch ( ... )
      {
        v29 = wil::ResultFromCaughtException(v25);
        LODWORD(v41) = v29;
        v30 = (__int64 *)v44;
        ++*(_DWORD *)(v44 + 12);
        if ( v51 )
        {
          v31 = std::optional<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>::value(v50);
          v32 = *v30;
          v33 = (_QWORD *)(v31 + 160);
          if ( *(_QWORD *)(v31 + 184) > 0xFu )
            v33 = (_QWORD *)*v33;
          v46 = v33;
          v34 = (_QWORD *)(v31 + 64);
          if ( *(_QWORD *)(v31 + 88) > 0xFu )
            v34 = (_QWORD *)*v34;
          v47[0] = v34;
          v35 = (_QWORD *)(v31 + 128);
          if ( v35[3] > 0xFu )
            v35 = (_QWORD *)*v35;
          v47[1] = v35;
          v36 = v40;
          Windows::Internal::Storage::Cloud::CloudStoreTelemetry::CopyEarlyDownloadRestoreDataToBackupPartition::ItemCouldNotBeProcessed<long &,unsigned int,char const *,char const *,char const *>(
            v32,
            (unsigned int)v39 + 56,
            (unsigned int)v39 + 48,
            (unsigned int)v39 + 112,
            (__int64)v47,
            (__int64)&v46);
        }
        else
        {
          v36 = v40;
        }
        if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
        {
          v37 = (__int64)v43;
          if ( (unsigned __int64)v43[3] > 7 )
            v37 = *v43;
          LODWORD(v38) = (_DWORD)v42;
          if ( v42[3] > 0xFu )
            v38 = *v42;
          McTemplateU0sdqz_EventWriteTransfer(v28, v27, v38, v29, v36, v37);
        }
        std::_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>::~_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>(v50);
        FirstFileW = v45;
        v8 = v48;
        v7 = v42;
        v41 = v42;
        v10 = v43;
        v5 = (IdGenerator *)v49;
        v9 = v44;
        v6 = v43;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v45);
  return std::wstring::~wstring(lpFileName);
}

```

## disassembly

```asm
0x1800d56f8  push    rbx
0x1800d56fa  push    rsi
0x1800d56fb  push    rdi
0x1800d56fc  push    r12
0x1800d56fe  push    r13
0x1800d5700  push    r14
0x1800d5702  push    r15
0x1800d5704  sub     rsp, 540h
0x1800d570b  mov     rax, cs:__security_cookie
0x1800d5712  xor     rax, rsp
0x1800d5715  mov     [rsp+578h+var_48], rax
0x1800d571d  mov     r12, r9
0x1800d5720  mov     r15, r8
0x1800d5723  mov     rsi, rdx
0x1800d5726  mov     [rsp+578h+var_540], rdx
0x1800d572b  mov     r13, rcx
0x1800d572e  mov     r14, [rsp+578h+arg_20]
0x1800d5736  mov     [rsp+578h+var_500], rcx
0x1800d573b  mov     [rsp+578h+var_538], rdx
0x1800d5740  mov     rdi, r8
0x1800d5743  mov     [rsp+578h+var_530], r8
0x1800d5748  mov     [rsp+578h+var_4F8], r9
0x1800d5750  mov     [rsp+578h+var_528], r14
0x1800d5755  mov     rcx, [rsp+578h]; this
0x1800d575d  test    r14, r14
0x1800d5760  jnz     short loc_1800D5774
0x1800d5762  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d5769  mov     edx, 0B9h; void *
0x1800d576e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d5774  xor     edx, edx; Val
0x1800d5776  mov     r8d, 250h; Size
0x1800d577c  lea     rcx, [rsp+578h+FindFileData]; void *
0x1800d5784  call    memset_0
0x1800d5789  lea     r8, asc_18022DA5C; "\\*"
0x1800d5790  mov     rdx, r15
0x1800d5793  lea     rcx, [rsp+578h+lpFileName]
0x1800d579b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800d57a0  nop
0x1800d57a1  lea     rcx, [rsp+578h+lpFileName]
0x1800d57a9  cmp     [rsp+578h+var_3A0], 7
0x1800d57b2  cmova   rcx, [rsp+578h+lpFileName]; lpFileName
0x1800d57bb  lea     rdx, [rsp+578h+FindFileData]; lpFindFileData
0x1800d57c3  call    cs:__imp_FindFirstFileW
0x1800d57c9  mov     rbx, rax
0x1800d57cc  mov     [rsp+578h+var_520], rax
0x1800d57d1  dec     rax
0x1800d57d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d57d8  setnbe  al
0x1800d57db  mov     rcx, [rsp+578h]; this
0x1800d57e3  test    al, al
0x1800d57e5  jz      short loc_1800D57F9
0x1800d57e7  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d57ee  mov     edx, 0BFh; void *
0x1800d57f3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d57f9  test    byte ptr [rsp+578h+FindFileData.dwFileAttributes], 10h
0x1800d5801  jz      loc_1800D58D3
0x1800d5807  cmp     dword ptr [r12+80h], 4
0x1800d5810  jnb     loc_1800D5AC7
0x1800d5816  lea     rcx, [rsp+578h+FindFileData.cFileName]; this
0x1800d581e  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x1800d5823  test    al, al
0x1800d5825  jnz     loc_1800D5AC7
0x1800d582b  lea     r8, asc_1802285AC; "\\"
0x1800d5832  mov     rdx, rdi
0x1800d5835  lea     rcx, [rsp+578h+var_398]
0x1800d583d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800d5842  nop
0x1800d5843  lea     r8, [rsp+578h+FindFileData.cFileName]
0x1800d584b  mov     rdx, rax
0x1800d584e  lea     rcx, [rsp+578h+var_3D8]
0x1800d5856  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800d585b  nop
0x1800d585c  lea     rcx, [rsp+578h+var_398]
0x1800d5864  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d5869  lea     rdx, [rsp+578h+FindFileData.cFileName]
0x1800d5871  lea     rcx, [rsp+578h+var_3F8]
0x1800d5879  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d587e  nop
0x1800d587f  lea     rdx, [rsp+578h+var_3F8]
0x1800d5887  mov     rcx, r12
0x1800d588a  call    ?PushNext@IdGenerator@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IdGenerator::PushNext(std::wstring const &)
0x1800d588f  nop
0x1800d5890  lea     rcx, [rsp+578h+var_3F8]
0x1800d5898  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d589d  mov     qword ptr [rsp+578h+bIgnoreCase], r14
0x1800d58a2  mov     r9, r12
0x1800d58a5  lea     r8, [rsp+578h+var_3D8]
0x1800d58ad  mov     rdx, rsi
0x1800d58b0  mov     rcx, r13
0x1800d58b3  call    ProcessPath
0x1800d58b8  mov     rcx, r12; this
0x1800d58bb  call    ?PopLast@IdGenerator@@QEAAXXZ; IdGenerator::PopLast(void)
0x1800d58c0  nop
0x1800d58c1  lea     rcx, [rsp+578h+var_3D8]
0x1800d58c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d58ce  jmp     loc_1800D5AC7
0x1800d58d3  mov     [rsp+578h+bIgnoreCase], 1; bIgnoreCase
0x1800d58db  or      r9d, 0FFFFFFFFh; cchCount2
0x1800d58df  lea     r8, aDataDat; "data.dat"
0x1800d58e6  or      edx, r9d; cchCount1
0x1800d58e9  lea     rcx, [rsp+578h+FindFileData.cFileName]; lpString1
0x1800d58f1  call    cs:__imp_CompareStringOrdinal
0x1800d58f7  cmp     eax, 2
0x1800d58fa  jnz     loc_1800D5AC7
0x1800d5900  mov     [rsp+578h+var_408], 0
0x1800d5908  mov     [rsp+578h+var_548], eax
0x1800d590c  lea     rdx, [rsp+578h+var_128]
0x1800d5914  mov     rcx, r12
0x1800d5917  call    ?GetItemId@IdGenerator@@QEAA?AVCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@XZ; IdGenerator::GetItemId(void)
0x1800d591c  mov     rdx, rax
0x1800d591f  lea     rcx, [rsp+578h+var_4E8]
0x1800d5927  call    ??$_Assign@VCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@@?$_Optional_construct_base@VCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@@std@@QEAAX$$QEAVCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@@Z; std::_Optional_construct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>::_Assign<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId &&)
0x1800d592c  lea     rcx, [rsp+578h+var_128]; this
0x1800d5934  call    ??1CloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId(void)
0x1800d5939  lea     rcx, [rsp+578h+var_4E8]
0x1800d5941  call    ?value@?$optional@VCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@@std@@QEGAAAEAVCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@XZ; std::optional<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>::value(void)
0x1800d5946  mov     rsi, rax
0x1800d5949  mov     [rsp+578h+var_548], 4
0x1800d5951  mov     rcx, [r13+0]
0x1800d5955  mov     rdx, [rcx]
0x1800d5958  mov     rax, [rdx+78h]
0x1800d595c  mov     rdx, rsi
0x1800d595f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5964  test    al, al
0x1800d5966  jnz     loc_1800D5A41
0x1800d596c  mov     [rsp+578h+var_548], 1
0x1800d5974  lea     r8, asc_1802285AC; "\\"
0x1800d597b  mov     rdx, rdi
0x1800d597e  lea     rcx, [rsp+578h+var_398]
0x1800d5986  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800d598b  nop
0x1800d598c  lea     r8, [rsp+578h+FindFileData.cFileName]
0x1800d5994  mov     rdx, rax
0x1800d5997  lea     rcx, [rsp+578h+var_3D8]
0x1800d599f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800d59a4  nop
0x1800d59a5  lea     rcx, [rsp+578h+var_398]
0x1800d59ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d59b2  lea     rdx, [rsp+578h+var_3D8]
0x1800d59ba  lea     rcx, [rsp+578h+var_3F8]
0x1800d59c2  call    ReadBase64EncodedFileIntoBlob
0x1800d59c7  nop
0x1800d59c8  mov     [rsp+578h+var_548], 3
0x1800d59d0  mov     rcx, [r13+0]
0x1800d59d4  mov     rax, [rcx]
0x1800d59d7  lea     r8, [rsp+578h+var_3F8]
0x1800d59df  mov     rdx, rsi
0x1800d59e2  mov     rax, [rax+28h]
0x1800d59e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d59eb  test    cs:Microsoft_Windows_CloudStoreEnableBits, 10h
0x1800d59f2  jz      short loc_1800D5A24
0x1800d59f4  lea     r9, [rsi+0C0h]
0x1800d59fb  cmp     qword ptr [rsi+0D8h], 0Fh
0x1800d5a03  jbe     short loc_1800D5A08
0x1800d5a05  mov     r9, [r9]
0x1800d5a08  cmp     qword ptr [rdi+18h], 7
0x1800d5a0d  jbe     short loc_1800D5A14
0x1800d5a0f  mov     r8, [r15]
0x1800d5a12  jmp     short loc_1800D5A17
0x1800d5a14  mov     r8, rdi
0x1800d5a17  lea     rdx, InitEarlyDownloadItemProcessed
0x1800d5a1e  call    McTemplateU0zs_EventWriteTransfer
0x1800d5a23  nop
0x1800d5a24  lea     rcx, [rsp+578h+var_3F0]; this
0x1800d5a2c  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800d5a31  nop
0x1800d5a32  lea     rcx, [rsp+578h+var_3D8]
0x1800d5a3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d5a3f  jmp     short loc_1800D5A7D
0x1800d5a41  test    cs:Microsoft_Windows_CloudStoreEnableBits, 10h
0x1800d5a48  jz      short loc_1800D5A79
0x1800d5a4a  lea     r9, [rsi+0C0h]
0x1800d5a51  cmp     qword ptr [rsi+0D8h], 0Fh
0x1800d5a59  jbe     short loc_1800D5A5E
0x1800d5a5b  mov     r9, [r9]
0x1800d5a5e  cmp     qword ptr [rdi+18h], 7
0x1800d5a63  jbe     short loc_1800D5A6A
0x1800d5a65  mov     r8, [r15]
0x1800d5a68  jmp     short loc_1800D5A6D
0x1800d5a6a  mov     r8, rdi
0x1800d5a6d  lea     rdx, InitEarlyDownloadItemSkipped
0x1800d5a74  call    McTemplateU0zs_EventWriteTransfer
0x1800d5a79  inc     dword ptr [r14+8]
0x1800d5a7d  lea     rcx, [rsp+578h+var_4E8]
0x1800d5a85  call    ??1?$_Optional_destruct_base@VCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>::~_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>(void)
0x1800d5a8a  mov     rsi, [rsp+578h+var_540]
0x1800d5a8f  jmp     short loc_1800D5AC7
0x1800d5a91  lea     rcx, [rsp+578h+var_4E8]
0x1800d5a99  call    ??1?$_Optional_destruct_base@VCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>::~_Optional_destruct_base<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId,0>(void)
0x1800d5a9e  mov     rbx, [rsp+578h+var_520]
0x1800d5aa3  mov     r13, [rsp+578h+var_500]
0x1800d5aa8  mov     rsi, [rsp+578h+var_538]
0x1800d5aad  mov     [rsp+578h+var_540], rsi
0x1800d5ab2  mov     rdi, [rsp+578h+var_530]
0x1800d5ab7  mov     r12, [rsp+578h+var_4F8]
0x1800d5abf  mov     r14, [rsp+578h+var_528]
0x1800d5ac4  mov     r15, rdi
0x1800d5ac7  lea     rdx, [rsp+578h+FindFileData]; lpFindFileData
0x1800d5acf  mov     rcx, rbx; hFindFile
0x1800d5ad2  call    cs:__imp_FindNextFileW
0x1800d5ad8  test    eax, eax
0x1800d5ada  jnz     loc_1800D57F9
0x1800d5ae0  lea     rcx, [rsp+578h+var_520]
0x1800d5ae5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d5aea  nop
0x1800d5aeb  lea     rcx, [rsp+578h+lpFileName]
0x1800d5af3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d5af8  mov     rcx, [rsp+578h+var_48]
0x1800d5b00  xor     rcx, rsp; StackCookie
0x1800d5b03  call    __security_check_cookie
0x1800d5b08  add     rsp, 540h
0x1800d5b0f  pop     r15
0x1800d5b11  pop     r14
0x1800d5b13  pop     r13
0x1800d5b15  pop     r12
0x1800d5b17  pop     rdi
0x1800d5b18  pop     rsi
0x1800d5b19  pop     rbx
0x1800d5b1a  retn
```
