# Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::SaveTo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140028c90`
- end: `0x1400290e9`
- name: `?SaveTo@?$VolumePersistedState@VVolumePersistedResults@ReFs@FileSystem@Windows@@UOnDiskSvcResults@PersistedData_v1@234@@ReFs@FileSystem@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1113`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400299a8`

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
- `0x140028c90`
- `0x140029b70`
- `0x14002a4a8`
- `0x14002b88c`
- `0x14002c7d4`
- `0x14002c8f8`
- `0x14002caec`
- `0x14004eb14`
- `0x14004f950`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140028f51`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140028f51`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140028faa`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140028faa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028e43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028eba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028e43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028eba`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140028fde`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140028fde`

## string_xrefs

- `0x140028e65`: `Failed to open or create the persisted state file`
- `0x140028edf`: `Failed to open temp file for writing new settings`
- `0x140028f87`: `Could not write full state! (%d,%d))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::SaveTo(
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
  std::filesystem::path::path(&v36, a2);
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
  Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges((Windows::FileSystem::ReFs *)&v36, qword_140223020);
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
  if ( v18 < 0xE8 )
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
  std::filesystem::path::path(&v38, a2);
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
0x140028c90  mov     [rsp-8+arg_10], rbx
0x140028c95  mov     [rsp-8+arg_18], rsi
0x140028c9a  push    rbp
0x140028c9b  push    rdi
0x140028c9c  push    r12
0x140028c9e  push    r14
0x140028ca0  push    r15
0x140028ca2  lea     rbp, [rsp-140h]
0x140028caa  sub     rsp, 240h
0x140028cb1  mov     rax, cs:__security_cookie
0x140028cb8  xor     rax, rsp
0x140028cbb  mov     [rbp+160h+var_30], rax
0x140028cc2  mov     rdi, rdx
0x140028cc5  mov     r14, rcx
0x140028cc8  lea     rcx, [rbp+160h+var_180]
0x140028ccc  call    ??$Start@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@SA?AV012345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::Start<std::wstring const &>(std::wstring const &)
0x140028cd1  nop
0x140028cd2  mov     rdx, rdi
0x140028cd5  lea     rcx, [rsp+260h+var_200]
0x140028cda  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140028cdf  nop
0x140028ce0  lea     rcx, [rsp+260h+var_200]; this
0x140028ce5  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x140028cea  mov     bl, al
0x140028cec  lea     rcx, [rsp+260h+var_200]
0x140028cf1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028cf6  xor     r15d, r15d
0x140028cf9  test    bl, bl
0x140028cfb  jnz     short loc_140028D3E
0x140028cfd  mov     rcx, rdi
0x140028d00  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028d05  mov     [rsp+260h+var_210], rax
0x140028d0a  mov     rax, [rdi+10h]
0x140028d0e  mov     [rsp+260h+var_208], rax
0x140028d13  lea     rdx, [rsp+260h+var_210]
0x140028d18  lea     rcx, [rsp+260h+var_200]
0x140028d1d  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x140028d22  nop
0x140028d23  mov     rcx, rax
0x140028d26  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028d2b  mov     rcx, rax; this
0x140028d2e  call    ?CreateDirectoryDeep@wil@@YAXPEBG@Z; wil::CreateDirectoryDeep(ushort const *)
0x140028d33  nop
0x140028d34  lea     rcx, [rsp+260h+var_200]
0x140028d39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028d3e  lea     rcx, [rsp+260h+NumberOfBytesWritten]; lplpsz
0x140028d43  call    ?make_guid_str@ReFs@FileSystem@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::FileSystem::ReFs::make_guid_str(void)
0x140028d48  nop
0x140028d49  mov     rcx, [rax]
0x140028d4c  mov     [rsp+260h+var_210], rcx
0x140028d51  or      rax, 0FFFFFFFFFFFFFFFFh
0x140028d55  inc     rax
0x140028d58  cmp     [rcx+rax*2], r15w
0x140028d5d  jnz     short loc_140028D55
0x140028d5f  mov     [rsp+260h+var_208], rax
0x140028d64  mov     rcx, rdi
0x140028d67  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028d6c  mov     [rbp+160h+var_1E0], rax
0x140028d70  mov     rax, [rdi+10h]
0x140028d74  mov     [rbp+160h+var_1D8], rax
0x140028d78  lea     rdx, [rbp+160h+var_1E0]
0x140028d7c  lea     rcx, [rbp+160h+var_1A0]
0x140028d80  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x140028d85  mov     rdx, rax
0x140028d88  mov     rcx, rax
0x140028d8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028d90  lea     rcx, [rsp+260h+var_210]
0x140028d95  mov     [rbp+160h+var_1E0], rcx
0x140028d99  lea     rcx, [rsp+260h+var_200]
0x140028d9e  mov     [rbp+160h+var_1D8], rcx
0x140028da2  mov     [rsp+260h+var_200], rax
0x140028da7  mov     rax, [rdx+10h]
0x140028dab  mov     [rsp+260h+var_1F8], rax
0x140028db0  lea     r8, [rbp+160h+var_1E0]
0x140028db4  lea     rdx, [rsp+260h+var_200]
0x140028db9  lea     rcx, [rbp+160h+var_1C0]
0x140028dbd  call    ?Combine@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@V?$initializer_list@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@6@@Z; Windows::FileSystem::ReFs::Path::Combine(std::basic_string_view<ushort>,std::initializer_list<std::basic_string_view<ushort>>)
0x140028dc2  nop
0x140028dc3  lea     rcx, [rbp+160h+var_1A0]
0x140028dc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140028dcc  nop
0x140028dcd  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x140028dd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140028dd7  mov     rbx, [r14]
0x140028dda  lea     rax, [rbx+10h]
0x140028dde  mov     [rsp+260h+var_200], rax
0x140028de3  mov     rax, [r14+8]
0x140028de7  sub     rax, rbx
0x140028dea  sub     rax, 10h
0x140028dee  mov     [rsp+260h+var_1F8], rax
0x140028df3  lea     rdx, [rsp+260h+var_200]
0x140028df8  lea     rcx, [rbp+160h+var_1E0]
0x140028dfc  call    ?ComputeHash@Md5Hasher@ReFs@FileSystem@Windows@@SA?AV?$array@E$0BA@@std@@V?$span@$$CBE$0?0@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(std::span<uchar const,-1>)
0x140028e01  movups  xmm0, xmmword ptr [rax]
0x140028e04  movdqu  xmmword ptr [rbx], xmm0
0x140028e08  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x140028e0f  lea     rcx, [rsp+260h+var_200]; this
0x140028e14  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x140028e19  nop
0x140028e1a  mov     rcx, rdi
0x140028e1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028e22  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x140028e27  mov     ebx, 80h
0x140028e2c  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x140028e30  mov     [rsp+260h+dwCreationDisposition], 4; dwCreationDisposition
0x140028e38  xor     r9d, r9d; lpSecurityAttributes
0x140028e3b  xor     r8d, r8d; dwShareMode
0x140028e3e  xor     edx, edx; dwDesiredAccess
0x140028e40  mov     rcx, rax; lpFileName
0x140028e43  call    cs:__imp_CreateFileW
0x140028e4a  nop     dword ptr [rax+rax+00h]
0x140028e4f  mov     qword ptr [rsp+260h+NumberOfBytesWritten], rax
0x140028e54  dec     rax
0x140028e57  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140028e5b  setnbe  al
0x140028e5e  mov     rcx, [rbp+168h]; this
0x140028e65  lea     rdx, aFailedToOpenOr; "Failed to open or create the persisted "...
0x140028e6c  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; bool
0x140028e71  movzx   r9d, al; char *
0x140028e75  lea     r12, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140028e7c  mov     r8, r12; unsigned int
0x140028e7f  lea     edx, [rbx+3Fh]; void *
0x140028e82  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140028e87  nop
0x140028e88  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x140028e8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140028e92  lea     rcx, [rbp+160h+var_1C0]
0x140028e96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028e9b  mov     rcx, rax; lpFileName
0x140028e9e  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x140028ea3  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x140028ea7  mov     [rsp+260h+dwCreationDisposition], 2; dwCreationDisposition
0x140028eaf  xor     r9d, r9d; lpSecurityAttributes
0x140028eb2  xor     r8d, r8d; dwShareMode
0x140028eb5  mov     edx, 40000000h; dwDesiredAccess
0x140028eba  call    cs:__imp_CreateFileW
0x140028ec1  nop     dword ptr [rax+rax+00h]
0x140028ec6  mov     rbx, rax
0x140028ec9  mov     [rsp+260h+var_210], rax
0x140028ece  dec     rax
0x140028ed1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140028ed5  setnbe  al
0x140028ed8  mov     rcx, [rbp+168h]; this
0x140028edf  lea     rdx, aFailedToOpenTe; "Failed to open temp file for writing ne"...
0x140028ee6  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; int
0x140028eeb  movzx   r9d, al; char *
0x140028eef  mov     r8, r12; unsigned int
0x140028ef2  mov     edx, 0C5h; void *
0x140028ef7  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140028efc  mov     rcx, [r14+8]
0x140028f00  sub     rcx, [r14]; __int64
0x140028f03  mov     rax, [rbp+168h]
0x140028f0a  cmp     rcx, 0E8h
0x140028f11  jb      loc_1400290B6
0x140028f17  mov     [rsp+260h+nNumberOfBytesToWrite], r15d
0x140028f1c  lea     rdx, [rsp+260h+nNumberOfBytesToWrite]; unsigned int *
0x140028f21  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x140028f26  mov     rcx, [rbp+168h]; this
0x140028f2d  test    eax, eax
0x140028f2f  js      loc_1400290CD
0x140028f35  mov     [rsp+260h+NumberOfBytesWritten], r15d
0x140028f3a  mov     qword ptr [rsp+260h+dwCreationDisposition], r15; lpOverlapped
0x140028f3f  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140028f44  mov     esi, [rsp+260h+nNumberOfBytesToWrite]
0x140028f48  mov     r8d, esi; nNumberOfBytesToWrite
0x140028f4b  mov     rdx, [r14]; lpBuffer
0x140028f4e  mov     rcx, rbx; hFile
0x140028f51  call    cs:__imp_WriteFile
0x140028f58  nop     dword ptr [rax+rax+00h]
0x140028f5d  mov     rcx, [rbp+168h]; this
0x140028f64  mov     r8, r12; unsigned int
0x140028f67  test    eax, eax
0x140028f69  jz      loc_1400290DE
0x140028f6f  mov     eax, [rsp+260h+NumberOfBytesWritten]
0x140028f73  cmp     eax, esi
0x140028f75  setb    dl
0x140028f78  mov     rcx, [rbp+168h]; this
0x140028f7f  mov     [rsp+260h+var_228], eax
0x140028f83  mov     dword ptr [rsp+260h+hTemplateFile], esi; char *
0x140028f87  lea     rax, aCouldNotWriteF; "Could not write full state! (%d,%d))"
0x140028f8e  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rax; bool
0x140028f93  mov     byte ptr [rsp+260h+dwCreationDisposition], dl; char
0x140028f97  mov     r9d, 8007007Ah; char *
0x140028f9d  mov     edx, 0D0h; void *
0x140028fa2  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140028fa7  mov     rcx, rbx; hFile
0x140028faa  call    cs:__imp_FlushFileBuffers
0x140028fb1  nop     dword ptr [rax+rax+00h]
0x140028fb6  nop
0x140028fb7  lea     rcx, [rsp+260h+var_210]
0x140028fbc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140028fc1  mov     rcx, rdi
0x140028fc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028fc9  mov     rdx, rax
0x140028fcc  lea     rcx, [rbp+160h+var_1C0]
0x140028fd0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140028fd5  mov     rcx, rax; lpExistingFileName
0x140028fd8  mov     r8d, 1; dwFlags
0x140028fde  call    cs:__imp_MoveFileExW
0x140028fe5  nop     dword ptr [rax+rax+00h]
0x140028fea  mov     rcx, [rbp+168h]; this
0x140028ff1  test    eax, eax
0x140028ff3  jz      loc_1400290A8
0x140028ff9  mov     rdx, rdi
0x140028ffc  lea     rcx, [rbp+160h+var_1E0]
0x140029000  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140029005  nop
0x140029006  lea     rcx, [rbp+160h+var_1E0]; this
0x14002900a  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x14002900f  mov     rbx, rax
0x140029012  lea     rcx, [rbp+160h+var_1E0]
0x140029016  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002901b  mov     rcx, [r14+8]
0x14002901f  sub     rcx, [r14]
0x140029022  cmp     rbx, rcx
0x140029025  setb    al
0x140029028  mov     rcx, [rbp+168h]; this
0x14002902f  lea     rdx, aFinalSizeOfPer; "Final size of persisted data is invalid"...
0x140029036  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rdx; bool
0x14002903b  mov     byte ptr [rsp+260h+dwCreationDisposition], al; char
0x14002903f  mov     r9d, 8007001Dh; char *
0x140029045  mov     r8, r12; unsigned int
0x140029048  mov     edx, 0DAh; void *
0x14002904d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140029052  xor     edx, edx
0x140029054  lea     rcx, [rbp+160h+var_180]
0x140029058  call    ?Stop@?$ActivityBase@VLogging@SvcLib@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::SvcLib::Logging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14002905d  nop
0x14002905e  lea     rcx, [rsp+260h+var_200]
0x140029063  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x140029068  nop
0x140029069  lea     rcx, [rbp+160h+var_1C0]
0x14002906d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029072  nop
0x140029073  lea     rcx, [rbp+160h+var_180]; this
0x140029077  call    ??1SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::~SaveVolumePersistedData(void)
0x14002907c  mov     rcx, [rbp+160h+var_30]
0x140029083  xor     rcx, rsp; StackCookie
0x140029086  call    __security_check_cookie
0x14002908b  lea     r11, [rsp+260h+var_20]
0x140029093  mov     rbx, [r11+40h]
0x140029097  mov     rsi, [r11+48h]
0x14002909b  mov     rsp, r11
0x14002909e  pop     r15
0x1400290a0  pop     r14
0x1400290a2  pop     r12
0x1400290a4  pop     rdi
0x1400290a5  pop     rbp
0x1400290a6  retn
0x1400290a8  mov     r8, r12; unsigned int
0x1400290ab  mov     edx, 0D6h; void *
0x1400290b0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400290b6  mov     r9d, 80070057h; char *
0x1400290bc  mov     r8, r12; unsigned int
0x1400290bf  mov     edx, 0C9h; void *
0x1400290c4  mov     rcx, rax; this
0x1400290c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400290cd  mov     r9d, eax; char *
0x1400290d0  mov     r8, r12; unsigned int
0x1400290d3  mov     edx, 0CCh; void *
0x1400290d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400290de  mov     edx, 0CFh; void *
0x1400290e3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
