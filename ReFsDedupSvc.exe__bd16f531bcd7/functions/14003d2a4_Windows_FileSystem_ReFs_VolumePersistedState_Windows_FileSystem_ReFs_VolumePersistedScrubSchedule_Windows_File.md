# Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedScrubSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::SaveTo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14003d2a4`
- end: `0x14003d6fa`
- name: `?SaveTo@?$VolumePersistedState@VVolumePersistedScrubSchedule@ReFs@FileSystem@Windows@@UOnDiskScrubSchedule@PersistedData_v1@234@@ReFs@FileSystem@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1110`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003d700`

## callees

- `0x140004870`
- `0x140018f38`
- `0x140018f7c`
- `0x140019130`
- `0x140019600`
- `0x1400196b8`
- `0x14001983c`
- `0x14001c194`
- `0x140022214`
- `0x140022920`
- `0x1400243ec`
- `0x1400244b0`
- `0x14002478c`
- `0x140025f8c`
- `0x1400260bc`
- `0x140029b70`
- `0x14002a4a8`
- `0x14002b88c`
- `0x14002c7d4`
- `0x14002c8f8`
- `0x14002caec`
- `0x14003d2a4`
- `0x14004eb14`
- `0x14004f950`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003d562`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003d562`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x14003d5bb`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x14003d5bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003d457`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003d4ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003d457`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003d4ce`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14003d5ef`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14003d5ef`

## string_xrefs

- `0x14003d479`: `Failed to open or create the persisted state file`
- `0x14003d4f3`: `Failed to open temp file for writing new settings`
- `0x14003d598`: `Could not write full state! (%d,%d))`

## pseudocode

```c
void __fastcall Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedScrubSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::SaveTo(
        __int64 a1,
        __int64 a2)
{
  const struct std::filesystem::path *v4; // rdx
  bool v5; // bl
  __int64 ParentDirectory; // rax
  wil *v7; // rax
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  _OWORD *v14; // rbx
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  char *FileW; // rbx
  unsigned __int64 v18; // rcx
  int v19; // eax
  DWORD v20; // esi
  const char *v21; // r9
  const WCHAR *v22; // rax
  LPCWSTR v23; // rdx
  const char *v24; // r9
  const struct std::filesystem::path *v25; // rdx
  unsigned __int64 v26; // rbx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h]
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int64 *v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v39; // [rsp+88h] [rbp-78h]
  _BYTE v40[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v41[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[336]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::Start<std::wstring const &>(v42);
  std::filesystem::path::path((__int64)&v36, a2);
  v5 = std::filesystem::exists((std::filesystem *)&v36, v4);
  std::wstring::_Tidy_deallocate(&v36);
  if ( !v5 )
  {
    v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v35 = *(_QWORD *)(a2 + 16);
    ParentDirectory = Windows::FileSystem::ReFs::Path::GetParentDirectory(&v36, &v34);
    v7 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ParentDirectory);
    wil::CreateDirectoryDeep(v7, v8);
    std::wstring::_Tidy_deallocate(&v36);
  }
  v9 = *(_QWORD *)Windows::FileSystem::ReFs::make_guid_str((LPOLESTR *)NumberOfBytesWritten);
  v34 = v9;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v9 + 2 * v10) );
  v35 = v10;
  v38 = (__int64 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v39 = *(__int64 **)(a2 + 16);
  v11 = Windows::FileSystem::ReFs::Path::GetParentDirectory(v41, &v38);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  v38 = &v34;
  v39 = &v36;
  v36 = v12;
  v37 = *(_QWORD *)(v13 + 16);
  Windows::FileSystem::ReFs::Path::Combine(v40, &v36, &v38);
  std::wstring::_Tidy_deallocate(v41);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(NumberOfBytesWritten);
  v14 = *(_OWORD **)a1;
  v36 = *(_QWORD *)a1 + 16LL;
  v37 = *(_QWORD *)(a1 + 8) - (_QWORD)v14 - 16LL;
  *v14 = *(_OWORD *)Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(&v38, &v36);
  Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges((Windows::FileSystem::ReFs *)&v36, qword_140223050);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  *(_QWORD *)NumberOfBytesWritten = CreateFileW(v15, 0, 0, 0, 4u, 0x80u, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xBF,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
    (const char *)((unsigned __int64)(*(_QWORD *)NumberOfBytesWritten - 1LL) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Failed to open or create the persisted state file",
    dwFlagsAndAttributes);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(NumberOfBytesWritten);
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
  FileW = (char *)CreateFileW(v16, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v34 = (__int64)FileW;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xC5,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Failed to open temp file for writing new settings",
    dwFlagsAndAttributesa);
  v18 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
  if ( v18 < 0x28 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  nNumberOfBytesToWrite = 0;
  v19 = LongLongToULong(v18, &nNumberOfBytesToWrite);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
      (const char *)(unsigned int)v19,
      dwCreationDisposition);
  NumberOfBytesWritten[0] = 0;
  v20 = nNumberOfBytesToWrite;
  if ( !WriteFile(FileW, *(LPCVOID *)a1, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
      v21);
  LODWORD(hTemplateFile) = v20;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xD0,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
    (const char *)0x8007007ALL,
    NumberOfBytesWritten[0] < v20,
    (bool)"Could not write full state! (%d,%d))",
    hTemplateFile,
    NumberOfBytesWritten[0]);
  FlushFileBuffers(FileW);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
  if ( !MoveFileExW(v22, v23, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
      v24);
  std::filesystem::path::path((__int64)&v38, a2);
  v26 = std::filesystem::file_size((std::filesystem *)&v38, v25);
  std::wstring::_Tidy_deallocate(&v38);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDA,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
    (const char *)0x8007001DLL,
    v26 < *(_QWORD *)(a1 + 8) - *(_QWORD *)a1,
    (bool)"Final size of persisted data is invalid!",
    hTemplateFilea);
  wil::ActivityBase<Windows::FileSystem::ReFs::SvcLib::Logging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v42,
    0);
  __1__lambda_call_V_lambda_1___1__ScopedAdjustTokenPrivileges_ReFs_FileSystem_Windows__YA_PEBU_TOKEN_PRIVILEGES___Z__details_wil__QEAA_XZ(&v36);
  std::wstring::_Tidy_deallocate(v40);
  Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::~SaveVolumePersistedData((Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData *)v42);
}

```

## disassembly

```asm
0x14003d2a4  mov     [rsp-8+arg_10], rbx
0x14003d2a9  mov     [rsp-8+arg_18], rsi
0x14003d2ae  push    rbp
0x14003d2af  push    rdi
0x14003d2b0  push    r12
0x14003d2b2  push    r14
0x14003d2b4  push    r15
0x14003d2b6  lea     rbp, [rsp-140h]
0x14003d2be  sub     rsp, 240h
0x14003d2c5  mov     rax, cs:__security_cookie
0x14003d2cc  xor     rax, rsp
0x14003d2cf  mov     [rbp+160h+var_30], rax
0x14003d2d6  mov     rdi, rdx
0x14003d2d9  mov     r14, rcx
0x14003d2dc  lea     rcx, [rbp+160h+var_180]
0x14003d2e0  call    ??$Start@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@SA?AV012345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::Start<std::wstring const &>(std::wstring const &)
0x14003d2e5  nop
0x14003d2e6  mov     rdx, rdi
0x14003d2e9  lea     rcx, [rsp+260h+var_200]
0x14003d2ee  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x14003d2f3  nop
0x14003d2f4  lea     rcx, [rsp+260h+var_200]; this
0x14003d2f9  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x14003d2fe  mov     bl, al
0x14003d300  lea     rcx, [rsp+260h+var_200]
0x14003d305  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003d30a  xor     r15d, r15d
0x14003d30d  test    bl, bl
0x14003d30f  jnz     short loc_14003D352
0x14003d311  mov     rcx, rdi
0x14003d314  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d319  mov     [rsp+260h+var_210], rax
0x14003d31e  mov     rax, [rdi+10h]
0x14003d322  mov     [rsp+260h+var_208], rax
0x14003d327  lea     rdx, [rsp+260h+var_210]
0x14003d32c  lea     rcx, [rsp+260h+var_200]
0x14003d331  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x14003d336  nop
0x14003d337  mov     rcx, rax
0x14003d33a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d33f  mov     rcx, rax; this
0x14003d342  call    ?CreateDirectoryDeep@wil@@YAXPEBG@Z; wil::CreateDirectoryDeep(ushort const *)
0x14003d347  nop
0x14003d348  lea     rcx, [rsp+260h+var_200]
0x14003d34d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003d352  lea     rcx, [rsp+260h+NumberOfBytesWritten]; lplpsz
0x14003d357  call    ?make_guid_str@ReFs@FileSystem@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::FileSystem::ReFs::make_guid_str(void)
0x14003d35c  nop
0x14003d35d  mov     rcx, [rax]
0x14003d360  mov     [rsp+260h+var_210], rcx
0x14003d365  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003d369  inc     rax
0x14003d36c  cmp     [rcx+rax*2], r15w
0x14003d371  jnz     short loc_14003D369
0x14003d373  mov     [rsp+260h+var_208], rax
0x14003d378  mov     rcx, rdi
0x14003d37b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d380  mov     [rbp+160h+var_1E0], rax
0x14003d384  mov     rax, [rdi+10h]
0x14003d388  mov     [rbp+160h+var_1D8], rax
0x14003d38c  lea     rdx, [rbp+160h+var_1E0]
0x14003d390  lea     rcx, [rbp+160h+var_1A0]
0x14003d394  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x14003d399  mov     rdx, rax
0x14003d39c  mov     rcx, rax
0x14003d39f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d3a4  lea     rcx, [rsp+260h+var_210]
0x14003d3a9  mov     [rbp+160h+var_1E0], rcx
0x14003d3ad  lea     rcx, [rsp+260h+var_200]
0x14003d3b2  mov     [rbp+160h+var_1D8], rcx
0x14003d3b6  mov     [rsp+260h+var_200], rax
0x14003d3bb  mov     rax, [rdx+10h]
0x14003d3bf  mov     [rsp+260h+var_1F8], rax
0x14003d3c4  lea     r8, [rbp+160h+var_1E0]
0x14003d3c8  lea     rdx, [rsp+260h+var_200]
0x14003d3cd  lea     rcx, [rbp+160h+var_1C0]
0x14003d3d1  call    ?Combine@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@V?$initializer_list@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@6@@Z; Windows::FileSystem::ReFs::Path::Combine(std::basic_string_view<ushort>,std::initializer_list<std::basic_string_view<ushort>>)
0x14003d3d6  nop
0x14003d3d7  lea     rcx, [rbp+160h+var_1A0]
0x14003d3db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003d3e0  nop
0x14003d3e1  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x14003d3e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14003d3eb  mov     rbx, [r14]
0x14003d3ee  lea     rax, [rbx+10h]
0x14003d3f2  mov     [rsp+260h+var_200], rax
0x14003d3f7  mov     rax, [r14+8]
0x14003d3fb  sub     rax, rbx
0x14003d3fe  sub     rax, 10h
0x14003d402  mov     [rsp+260h+var_1F8], rax
0x14003d407  lea     rdx, [rsp+260h+var_200]
0x14003d40c  lea     rcx, [rbp+160h+var_1E0]
0x14003d410  call    ?ComputeHash@Md5Hasher@ReFs@FileSystem@Windows@@SA?AV?$array@E$0BA@@std@@V?$span@$$CBE$0?0@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(std::span<uchar const,-1>)
0x14003d415  movups  xmm0, xmmword ptr [rax]
0x14003d418  movdqu  xmmword ptr [rbx], xmm0
0x14003d41c  mov     rdx, cs:qword_140223050; struct _TOKEN_PRIVILEGES *
0x14003d423  lea     rcx, [rsp+260h+var_200]; this
0x14003d428  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x14003d42d  nop
0x14003d42e  mov     rcx, rdi
0x14003d431  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d436  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x14003d43b  mov     ebx, 80h
0x14003d440  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x14003d444  mov     [rsp+260h+dwCreationDisposition], 4; dwCreationDisposition
0x14003d44c  xor     r9d, r9d; lpSecurityAttributes
0x14003d44f  xor     r8d, r8d; dwShareMode
0x14003d452  xor     edx, edx; dwDesiredAccess
0x14003d454  mov     rcx, rax; lpFileName
0x14003d457  call    cs:__imp_CreateFileW
0x14003d45e  nop     dword ptr [rax+rax+00h]
0x14003d463  mov     qword ptr [rsp+260h+NumberOfBytesWritten], rax
0x14003d468  dec     rax
0x14003d46b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003d46f  setnbe  al
0x14003d472  mov     rcx, [rbp+168h]; this
0x14003d479  lea     rdx, aFailedToOpenOr; "Failed to open or create the persisted "...
0x14003d480  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; bool
0x14003d485  movzx   r9d, al; char *
0x14003d489  lea     r12, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14003d490  mov     r8, r12; unsigned int
0x14003d493  lea     edx, [rbx+3Fh]; void *
0x14003d496  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x14003d49b  nop
0x14003d49c  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x14003d4a1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14003d4a6  lea     rcx, [rbp+160h+var_1C0]
0x14003d4aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d4af  mov     rcx, rax; lpFileName
0x14003d4b2  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x14003d4b7  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x14003d4bb  mov     [rsp+260h+dwCreationDisposition], 2; dwCreationDisposition
0x14003d4c3  xor     r9d, r9d; lpSecurityAttributes
0x14003d4c6  xor     r8d, r8d; dwShareMode
0x14003d4c9  mov     edx, 40000000h; dwDesiredAccess
0x14003d4ce  call    cs:__imp_CreateFileW
0x14003d4d5  nop     dword ptr [rax+rax+00h]
0x14003d4da  mov     rbx, rax
0x14003d4dd  mov     [rsp+260h+var_210], rax
0x14003d4e2  dec     rax
0x14003d4e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003d4e9  setnbe  al
0x14003d4ec  mov     rcx, [rbp+168h]; this
0x14003d4f3  lea     rdx, aFailedToOpenTe; "Failed to open temp file for writing ne"...
0x14003d4fa  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; int
0x14003d4ff  movzx   r9d, al; char *
0x14003d503  mov     r8, r12; unsigned int
0x14003d506  mov     edx, 0C5h; void *
0x14003d50b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x14003d510  mov     rcx, [r14+8]
0x14003d514  sub     rcx, [r14]; __int64
0x14003d517  mov     rax, [rbp+168h]
0x14003d51e  cmp     rcx, 28h ; '('
0x14003d522  jb      loc_14003D6C7
0x14003d528  mov     [rsp+260h+nNumberOfBytesToWrite], r15d
0x14003d52d  lea     rdx, [rsp+260h+nNumberOfBytesToWrite]; unsigned int *
0x14003d532  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x14003d537  mov     rcx, [rbp+168h]; this
0x14003d53e  test    eax, eax
0x14003d540  js      loc_14003D6DE
0x14003d546  mov     [rsp+260h+NumberOfBytesWritten], r15d
0x14003d54b  mov     qword ptr [rsp+260h+dwCreationDisposition], r15; lpOverlapped
0x14003d550  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003d555  mov     esi, [rsp+260h+nNumberOfBytesToWrite]
0x14003d559  mov     r8d, esi; nNumberOfBytesToWrite
0x14003d55c  mov     rdx, [r14]; lpBuffer
0x14003d55f  mov     rcx, rbx; hFile
0x14003d562  call    cs:__imp_WriteFile
0x14003d569  nop     dword ptr [rax+rax+00h]
0x14003d56e  mov     rcx, [rbp+168h]; this
0x14003d575  mov     r8, r12; unsigned int
0x14003d578  test    eax, eax
0x14003d57a  jz      loc_14003D6EF
0x14003d580  mov     eax, [rsp+260h+NumberOfBytesWritten]
0x14003d584  cmp     eax, esi
0x14003d586  setb    dl
0x14003d589  mov     rcx, [rbp+168h]; this
0x14003d590  mov     [rsp+260h+var_228], eax
0x14003d594  mov     dword ptr [rsp+260h+hTemplateFile], esi; char *
0x14003d598  lea     rax, aCouldNotWriteF; "Could not write full state! (%d,%d))"
0x14003d59f  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rax; bool
0x14003d5a4  mov     byte ptr [rsp+260h+dwCreationDisposition], dl; char
0x14003d5a8  mov     r9d, 8007007Ah; char *
0x14003d5ae  mov     edx, 0D0h; void *
0x14003d5b3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14003d5b8  mov     rcx, rbx; hFile
0x14003d5bb  call    cs:__imp_FlushFileBuffers
0x14003d5c2  nop     dword ptr [rax+rax+00h]
0x14003d5c7  nop
0x14003d5c8  lea     rcx, [rsp+260h+var_210]
0x14003d5cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14003d5d2  mov     rcx, rdi
0x14003d5d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d5da  mov     rdx, rax
0x14003d5dd  lea     rcx, [rbp+160h+var_1C0]
0x14003d5e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14003d5e6  mov     rcx, rax; lpExistingFileName
0x14003d5e9  mov     r8d, 1; dwFlags
0x14003d5ef  call    cs:__imp_MoveFileExW
0x14003d5f6  nop     dword ptr [rax+rax+00h]
0x14003d5fb  mov     rcx, [rbp+168h]; this
0x14003d602  test    eax, eax
0x14003d604  jz      loc_14003D6B9
0x14003d60a  mov     rdx, rdi
0x14003d60d  lea     rcx, [rbp+160h+var_1E0]
0x14003d611  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x14003d616  nop
0x14003d617  lea     rcx, [rbp+160h+var_1E0]; this
0x14003d61b  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x14003d620  mov     rbx, rax
0x14003d623  lea     rcx, [rbp+160h+var_1E0]
0x14003d627  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003d62c  mov     rcx, [r14+8]
0x14003d630  sub     rcx, [r14]
0x14003d633  cmp     rbx, rcx
0x14003d636  setb    al
0x14003d639  mov     rcx, [rbp+168h]; this
0x14003d640  lea     rdx, aFinalSizeOfPer; "Final size of persisted data is invalid"...
0x14003d647  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rdx; bool
0x14003d64c  mov     byte ptr [rsp+260h+dwCreationDisposition], al; char
0x14003d650  mov     r9d, 8007001Dh; char *
0x14003d656  mov     r8, r12; unsigned int
0x14003d659  mov     edx, 0DAh; void *
0x14003d65e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14003d663  xor     edx, edx
0x14003d665  lea     rcx, [rbp+160h+var_180]
0x14003d669  call    ?Stop@?$ActivityBase@VLogging@SvcLib@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::SvcLib::Logging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14003d66e  nop
0x14003d66f  lea     rcx, [rsp+260h+var_200]
0x14003d674  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x14003d679  nop
0x14003d67a  lea     rcx, [rbp+160h+var_1C0]
0x14003d67e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003d683  nop
0x14003d684  lea     rcx, [rbp+160h+var_180]; this
0x14003d688  call    ??1SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::~SaveVolumePersistedData(void)
0x14003d68d  mov     rcx, [rbp+160h+var_30]
0x14003d694  xor     rcx, rsp; StackCookie
0x14003d697  call    __security_check_cookie
0x14003d69c  lea     r11, [rsp+260h+var_20]
0x14003d6a4  mov     rbx, [r11+40h]
0x14003d6a8  mov     rsi, [r11+48h]
0x14003d6ac  mov     rsp, r11
0x14003d6af  pop     r15
0x14003d6b1  pop     r14
0x14003d6b3  pop     r12
0x14003d6b5  pop     rdi
0x14003d6b6  pop     rbp
0x14003d6b7  retn
0x14003d6b9  mov     r8, r12; unsigned int
0x14003d6bc  mov     edx, 0D6h; void *
0x14003d6c1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14003d6c7  mov     r9d, 80070057h; char *
0x14003d6cd  mov     r8, r12; unsigned int
0x14003d6d0  mov     edx, 0C9h; void *
0x14003d6d5  mov     rcx, rax; this
0x14003d6d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003d6de  mov     r9d, eax; char *
0x14003d6e1  mov     r8, r12; unsigned int
0x14003d6e4  mov     edx, 0CCh; void *
0x14003d6e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003d6ef  mov     edx, 0CFh; void *
0x14003d6f4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
