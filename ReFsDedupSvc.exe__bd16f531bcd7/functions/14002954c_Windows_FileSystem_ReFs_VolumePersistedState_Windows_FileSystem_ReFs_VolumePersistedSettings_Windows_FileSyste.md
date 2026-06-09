# Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSettings,Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::SaveTo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14002954c`
- end: `0x1400299a2`
- name: `?SaveTo@?$VolumePersistedState@VVolumePersistedSettings@ReFs@FileSystem@Windows@@UOnDiskSvcSettings@PersistedSettings_v1@234@@ReFs@FileSystem@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1110`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140029ae0`

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
- `0x14002954c`
- `0x140029b70`
- `0x14002a4a8`
- `0x14002b88c`
- `0x14002c7d4`
- `0x14002c8f8`
- `0x14002caec`
- `0x14004eb14`
- `0x14004f950`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002980a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002980a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140029863`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140029863`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400296ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140029776`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400296ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140029776`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140029897`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140029897`

## string_xrefs

- `0x140029721`: `Failed to open or create the persisted state file`
- `0x14002979b`: `Failed to open temp file for writing new settings`
- `0x140029840`: `Could not write full state! (%d,%d))`

## pseudocode

```c
void __fastcall Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSettings,Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::SaveTo(
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
  if ( v18 < 0x20 )
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
0x14002954c  mov     [rsp-8+arg_10], rbx
0x140029551  mov     [rsp-8+arg_18], rsi
0x140029556  push    rbp
0x140029557  push    rdi
0x140029558  push    r12
0x14002955a  push    r14
0x14002955c  push    r15
0x14002955e  lea     rbp, [rsp-140h]
0x140029566  sub     rsp, 240h
0x14002956d  mov     rax, cs:__security_cookie
0x140029574  xor     rax, rsp
0x140029577  mov     [rbp+160h+var_30], rax
0x14002957e  mov     rdi, rdx
0x140029581  mov     r14, rcx
0x140029584  lea     rcx, [rbp+160h+var_180]
0x140029588  call    ??$Start@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@SA?AV012345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::Start<std::wstring const &>(std::wstring const &)
0x14002958d  nop
0x14002958e  mov     rdx, rdi
0x140029591  lea     rcx, [rsp+260h+var_200]
0x140029596  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x14002959b  nop
0x14002959c  lea     rcx, [rsp+260h+var_200]; this
0x1400295a1  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1400295a6  mov     bl, al
0x1400295a8  lea     rcx, [rsp+260h+var_200]
0x1400295ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400295b2  xor     r15d, r15d
0x1400295b5  test    bl, bl
0x1400295b7  jnz     short loc_1400295FA
0x1400295b9  mov     rcx, rdi
0x1400295bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400295c1  mov     [rsp+260h+var_210], rax
0x1400295c6  mov     rax, [rdi+10h]
0x1400295ca  mov     [rsp+260h+var_208], rax
0x1400295cf  lea     rdx, [rsp+260h+var_210]
0x1400295d4  lea     rcx, [rsp+260h+var_200]
0x1400295d9  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x1400295de  nop
0x1400295df  mov     rcx, rax
0x1400295e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400295e7  mov     rcx, rax; this
0x1400295ea  call    ?CreateDirectoryDeep@wil@@YAXPEBG@Z; wil::CreateDirectoryDeep(ushort const *)
0x1400295ef  nop
0x1400295f0  lea     rcx, [rsp+260h+var_200]
0x1400295f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400295fa  lea     rcx, [rsp+260h+NumberOfBytesWritten]; lplpsz
0x1400295ff  call    ?make_guid_str@ReFs@FileSystem@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::FileSystem::ReFs::make_guid_str(void)
0x140029604  nop
0x140029605  mov     rcx, [rax]
0x140029608  mov     [rsp+260h+var_210], rcx
0x14002960d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140029611  inc     rax
0x140029614  cmp     [rcx+rax*2], r15w
0x140029619  jnz     short loc_140029611
0x14002961b  mov     [rsp+260h+var_208], rax
0x140029620  mov     rcx, rdi
0x140029623  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029628  mov     [rbp+160h+var_1E0], rax
0x14002962c  mov     rax, [rdi+10h]
0x140029630  mov     [rbp+160h+var_1D8], rax
0x140029634  lea     rdx, [rbp+160h+var_1E0]
0x140029638  lea     rcx, [rbp+160h+var_1A0]
0x14002963c  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x140029641  mov     rdx, rax
0x140029644  mov     rcx, rax
0x140029647  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002964c  lea     rcx, [rsp+260h+var_210]
0x140029651  mov     [rbp+160h+var_1E0], rcx
0x140029655  lea     rcx, [rsp+260h+var_200]
0x14002965a  mov     [rbp+160h+var_1D8], rcx
0x14002965e  mov     [rsp+260h+var_200], rax
0x140029663  mov     rax, [rdx+10h]
0x140029667  mov     [rsp+260h+var_1F8], rax
0x14002966c  lea     r8, [rbp+160h+var_1E0]
0x140029670  lea     rdx, [rsp+260h+var_200]
0x140029675  lea     rcx, [rbp+160h+var_1C0]
0x140029679  call    ?Combine@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@V?$initializer_list@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@6@@Z; Windows::FileSystem::ReFs::Path::Combine(std::basic_string_view<ushort>,std::initializer_list<std::basic_string_view<ushort>>)
0x14002967e  nop
0x14002967f  lea     rcx, [rbp+160h+var_1A0]
0x140029683  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029688  nop
0x140029689  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x14002968e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140029693  mov     rbx, [r14]
0x140029696  lea     rax, [rbx+10h]
0x14002969a  mov     [rsp+260h+var_200], rax
0x14002969f  mov     rax, [r14+8]
0x1400296a3  sub     rax, rbx
0x1400296a6  sub     rax, 10h
0x1400296aa  mov     [rsp+260h+var_1F8], rax
0x1400296af  lea     rdx, [rsp+260h+var_200]
0x1400296b4  lea     rcx, [rbp+160h+var_1E0]
0x1400296b8  call    ?ComputeHash@Md5Hasher@ReFs@FileSystem@Windows@@SA?AV?$array@E$0BA@@std@@V?$span@$$CBE$0?0@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(std::span<uchar const,-1>)
0x1400296bd  movups  xmm0, xmmword ptr [rax]
0x1400296c0  movdqu  xmmword ptr [rbx], xmm0
0x1400296c4  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x1400296cb  lea     rcx, [rsp+260h+var_200]; this
0x1400296d0  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x1400296d5  nop
0x1400296d6  mov     rcx, rdi
0x1400296d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400296de  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x1400296e3  mov     ebx, 80h
0x1400296e8  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x1400296ec  mov     [rsp+260h+dwCreationDisposition], 4; dwCreationDisposition
0x1400296f4  xor     r9d, r9d; lpSecurityAttributes
0x1400296f7  xor     r8d, r8d; dwShareMode
0x1400296fa  xor     edx, edx; dwDesiredAccess
0x1400296fc  mov     rcx, rax; lpFileName
0x1400296ff  call    cs:__imp_CreateFileW
0x140029706  nop     dword ptr [rax+rax+00h]
0x14002970b  mov     qword ptr [rsp+260h+NumberOfBytesWritten], rax
0x140029710  dec     rax
0x140029713  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029717  setnbe  al
0x14002971a  mov     rcx, [rbp+168h]; this
0x140029721  lea     rdx, aFailedToOpenOr; "Failed to open or create the persisted "...
0x140029728  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; bool
0x14002972d  movzx   r9d, al; char *
0x140029731  lea     r12, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140029738  mov     r8, r12; unsigned int
0x14002973b  lea     edx, [rbx+3Fh]; void *
0x14002973e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140029743  nop
0x140029744  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x140029749  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002974e  lea     rcx, [rbp+160h+var_1C0]
0x140029752  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029757  mov     rcx, rax; lpFileName
0x14002975a  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x14002975f  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x140029763  mov     [rsp+260h+dwCreationDisposition], 2; dwCreationDisposition
0x14002976b  xor     r9d, r9d; lpSecurityAttributes
0x14002976e  xor     r8d, r8d; dwShareMode
0x140029771  mov     edx, 40000000h; dwDesiredAccess
0x140029776  call    cs:__imp_CreateFileW
0x14002977d  nop     dword ptr [rax+rax+00h]
0x140029782  mov     rbx, rax
0x140029785  mov     [rsp+260h+var_210], rax
0x14002978a  dec     rax
0x14002978d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029791  setnbe  al
0x140029794  mov     rcx, [rbp+168h]; this
0x14002979b  lea     rdx, aFailedToOpenTe; "Failed to open temp file for writing ne"...
0x1400297a2  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; int
0x1400297a7  movzx   r9d, al; char *
0x1400297ab  mov     r8, r12; unsigned int
0x1400297ae  mov     edx, 0C5h; void *
0x1400297b3  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1400297b8  mov     rcx, [r14+8]
0x1400297bc  sub     rcx, [r14]; __int64
0x1400297bf  mov     rax, [rbp+168h]
0x1400297c6  cmp     rcx, 20h ; ' '
0x1400297ca  jb      loc_14002996F
0x1400297d0  mov     [rsp+260h+nNumberOfBytesToWrite], r15d
0x1400297d5  lea     rdx, [rsp+260h+nNumberOfBytesToWrite]; unsigned int *
0x1400297da  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x1400297df  mov     rcx, [rbp+168h]; this
0x1400297e6  test    eax, eax
0x1400297e8  js      loc_140029986
0x1400297ee  mov     [rsp+260h+NumberOfBytesWritten], r15d
0x1400297f3  mov     qword ptr [rsp+260h+dwCreationDisposition], r15; lpOverlapped
0x1400297f8  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400297fd  mov     esi, [rsp+260h+nNumberOfBytesToWrite]
0x140029801  mov     r8d, esi; nNumberOfBytesToWrite
0x140029804  mov     rdx, [r14]; lpBuffer
0x140029807  mov     rcx, rbx; hFile
0x14002980a  call    cs:__imp_WriteFile
0x140029811  nop     dword ptr [rax+rax+00h]
0x140029816  mov     rcx, [rbp+168h]; this
0x14002981d  mov     r8, r12; unsigned int
0x140029820  test    eax, eax
0x140029822  jz      loc_140029997
0x140029828  mov     eax, [rsp+260h+NumberOfBytesWritten]
0x14002982c  cmp     eax, esi
0x14002982e  setb    dl
0x140029831  mov     rcx, [rbp+168h]; this
0x140029838  mov     [rsp+260h+var_228], eax
0x14002983c  mov     dword ptr [rsp+260h+hTemplateFile], esi; char *
0x140029840  lea     rax, aCouldNotWriteF; "Could not write full state! (%d,%d))"
0x140029847  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rax; bool
0x14002984c  mov     byte ptr [rsp+260h+dwCreationDisposition], dl; char
0x140029850  mov     r9d, 8007007Ah; char *
0x140029856  mov     edx, 0D0h; void *
0x14002985b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140029860  mov     rcx, rbx; hFile
0x140029863  call    cs:__imp_FlushFileBuffers
0x14002986a  nop     dword ptr [rax+rax+00h]
0x14002986f  nop
0x140029870  lea     rcx, [rsp+260h+var_210]
0x140029875  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002987a  mov     rcx, rdi
0x14002987d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029882  mov     rdx, rax
0x140029885  lea     rcx, [rbp+160h+var_1C0]
0x140029889  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002988e  mov     rcx, rax; lpExistingFileName
0x140029891  mov     r8d, 1; dwFlags
0x140029897  call    cs:__imp_MoveFileExW
0x14002989e  nop     dword ptr [rax+rax+00h]
0x1400298a3  mov     rcx, [rbp+168h]; this
0x1400298aa  test    eax, eax
0x1400298ac  jz      loc_140029961
0x1400298b2  mov     rdx, rdi
0x1400298b5  lea     rcx, [rbp+160h+var_1E0]
0x1400298b9  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1400298be  nop
0x1400298bf  lea     rcx, [rbp+160h+var_1E0]; this
0x1400298c3  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x1400298c8  mov     rbx, rax
0x1400298cb  lea     rcx, [rbp+160h+var_1E0]
0x1400298cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400298d4  mov     rcx, [r14+8]
0x1400298d8  sub     rcx, [r14]
0x1400298db  cmp     rbx, rcx
0x1400298de  setb    al
0x1400298e1  mov     rcx, [rbp+168h]; this
0x1400298e8  lea     rdx, aFinalSizeOfPer; "Final size of persisted data is invalid"...
0x1400298ef  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rdx; bool
0x1400298f4  mov     byte ptr [rsp+260h+dwCreationDisposition], al; char
0x1400298f8  mov     r9d, 8007001Dh; char *
0x1400298fe  mov     r8, r12; unsigned int
0x140029901  mov     edx, 0DAh; void *
0x140029906  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14002990b  xor     edx, edx
0x14002990d  lea     rcx, [rbp+160h+var_180]
0x140029911  call    ?Stop@?$ActivityBase@VLogging@SvcLib@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::SvcLib::Logging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140029916  nop
0x140029917  lea     rcx, [rsp+260h+var_200]
0x14002991c  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x140029921  nop
0x140029922  lea     rcx, [rbp+160h+var_1C0]
0x140029926  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002992b  nop
0x14002992c  lea     rcx, [rbp+160h+var_180]; this
0x140029930  call    ??1SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::~SaveVolumePersistedData(void)
0x140029935  mov     rcx, [rbp+160h+var_30]
0x14002993c  xor     rcx, rsp; StackCookie
0x14002993f  call    __security_check_cookie
0x140029944  lea     r11, [rsp+260h+var_20]
0x14002994c  mov     rbx, [r11+40h]
0x140029950  mov     rsi, [r11+48h]
0x140029954  mov     rsp, r11
0x140029957  pop     r15
0x140029959  pop     r14
0x14002995b  pop     r12
0x14002995d  pop     rdi
0x14002995e  pop     rbp
0x14002995f  retn
0x140029961  mov     r8, r12; unsigned int
0x140029964  mov     edx, 0D6h; void *
0x140029969  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14002996f  mov     r9d, 80070057h; char *
0x140029975  mov     r8, r12; unsigned int
0x140029978  mov     edx, 0C9h; void *
0x14002997d  mov     rcx, rax; this
0x140029980  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140029986  mov     r9d, eax; char *
0x140029989  mov     r8, r12; unsigned int
0x14002998c  mov     edx, 0CCh; void *
0x140029991  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140029997  mov     edx, 0CFh; void *
0x14002999c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
