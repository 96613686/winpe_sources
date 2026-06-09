# Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::SaveTo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400290f0`
- end: `0x140029546`
- name: `?SaveTo@?$VolumePersistedState@VVolumePersistedSchedule@ReFs@FileSystem@Windows@@UOnDiskSchedule@PersistedData_v1@234@@ReFs@FileSystem@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140029a38`

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
- `0x1400290f0`
- `0x140029b70`
- `0x14002a4a8`
- `0x14002b88c`
- `0x14002c7d4`
- `0x14002c8f8`
- `0x14002caec`
- `0x14004eb14`
- `0x14004f950`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400293ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400293ae`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140029407`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140029407`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400292a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002931a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400292a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002931a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14002943b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14002943b`

## string_xrefs

- `0x1400292c5`: `Failed to open or create the persisted state file`
- `0x14002933f`: `Failed to open temp file for writing new settings`
- `0x1400293e4`: `Could not write full state! (%d,%d))`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::SaveTo(
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
  if ( v18 < 0x70 )
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
0x1400290f0  mov     [rsp-8+arg_10], rbx
0x1400290f5  mov     [rsp-8+arg_18], rsi
0x1400290fa  push    rbp
0x1400290fb  push    rdi
0x1400290fc  push    r12
0x1400290fe  push    r14
0x140029100  push    r15
0x140029102  lea     rbp, [rsp-140h]
0x14002910a  sub     rsp, 240h
0x140029111  mov     rax, cs:__security_cookie
0x140029118  xor     rax, rsp
0x14002911b  mov     [rbp+160h+var_30], rax
0x140029122  mov     rdi, rdx
0x140029125  mov     r14, rcx
0x140029128  lea     rcx, [rbp+160h+var_180]
0x14002912c  call    ??$Start@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@SA?AV012345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::Start<std::wstring const &>(std::wstring const &)
0x140029131  nop
0x140029132  mov     rdx, rdi
0x140029135  lea     rcx, [rsp+260h+var_200]
0x14002913a  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x14002913f  nop
0x140029140  lea     rcx, [rsp+260h+var_200]; this
0x140029145  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x14002914a  mov     bl, al
0x14002914c  lea     rcx, [rsp+260h+var_200]
0x140029151  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029156  xor     r15d, r15d
0x140029159  test    bl, bl
0x14002915b  jnz     short loc_14002919E
0x14002915d  mov     rcx, rdi
0x140029160  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029165  mov     [rsp+260h+var_210], rax
0x14002916a  mov     rax, [rdi+10h]
0x14002916e  mov     [rsp+260h+var_208], rax
0x140029173  lea     rdx, [rsp+260h+var_210]
0x140029178  lea     rcx, [rsp+260h+var_200]
0x14002917d  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x140029182  nop
0x140029183  mov     rcx, rax
0x140029186  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002918b  mov     rcx, rax; this
0x14002918e  call    ?CreateDirectoryDeep@wil@@YAXPEBG@Z; wil::CreateDirectoryDeep(ushort const *)
0x140029193  nop
0x140029194  lea     rcx, [rsp+260h+var_200]
0x140029199  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002919e  lea     rcx, [rsp+260h+NumberOfBytesWritten]; lplpsz
0x1400291a3  call    ?make_guid_str@ReFs@FileSystem@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::FileSystem::ReFs::make_guid_str(void)
0x1400291a8  nop
0x1400291a9  mov     rcx, [rax]
0x1400291ac  mov     [rsp+260h+var_210], rcx
0x1400291b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400291b5  inc     rax
0x1400291b8  cmp     [rcx+rax*2], r15w
0x1400291bd  jnz     short loc_1400291B5
0x1400291bf  mov     [rsp+260h+var_208], rax
0x1400291c4  mov     rcx, rdi
0x1400291c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400291cc  mov     [rbp+160h+var_1E0], rax
0x1400291d0  mov     rax, [rdi+10h]
0x1400291d4  mov     [rbp+160h+var_1D8], rax
0x1400291d8  lea     rdx, [rbp+160h+var_1E0]
0x1400291dc  lea     rcx, [rbp+160h+var_1A0]
0x1400291e0  call    ?GetParentDirectory@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::Path::GetParentDirectory(std::basic_string_view<ushort>)
0x1400291e5  mov     rdx, rax
0x1400291e8  mov     rcx, rax
0x1400291eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400291f0  lea     rcx, [rsp+260h+var_210]
0x1400291f5  mov     [rbp+160h+var_1E0], rcx
0x1400291f9  lea     rcx, [rsp+260h+var_200]
0x1400291fe  mov     [rbp+160h+var_1D8], rcx
0x140029202  mov     [rsp+260h+var_200], rax
0x140029207  mov     rax, [rdx+10h]
0x14002920b  mov     [rsp+260h+var_1F8], rax
0x140029210  lea     r8, [rbp+160h+var_1E0]
0x140029214  lea     rdx, [rsp+260h+var_200]
0x140029219  lea     rcx, [rbp+160h+var_1C0]
0x14002921d  call    ?Combine@Path@ReFs@FileSystem@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@V?$initializer_list@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@6@@Z; Windows::FileSystem::ReFs::Path::Combine(std::basic_string_view<ushort>,std::initializer_list<std::basic_string_view<ushort>>)
0x140029222  nop
0x140029223  lea     rcx, [rbp+160h+var_1A0]
0x140029227  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002922c  nop
0x14002922d  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x140029232  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140029237  mov     rbx, [r14]
0x14002923a  lea     rax, [rbx+10h]
0x14002923e  mov     [rsp+260h+var_200], rax
0x140029243  mov     rax, [r14+8]
0x140029247  sub     rax, rbx
0x14002924a  sub     rax, 10h
0x14002924e  mov     [rsp+260h+var_1F8], rax
0x140029253  lea     rdx, [rsp+260h+var_200]
0x140029258  lea     rcx, [rbp+160h+var_1E0]
0x14002925c  call    ?ComputeHash@Md5Hasher@ReFs@FileSystem@Windows@@SA?AV?$array@E$0BA@@std@@V?$span@$$CBE$0?0@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(std::span<uchar const,-1>)
0x140029261  movups  xmm0, xmmword ptr [rax]
0x140029264  movdqu  xmmword ptr [rbx], xmm0
0x140029268  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x14002926f  lea     rcx, [rsp+260h+var_200]; this
0x140029274  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x140029279  nop
0x14002927a  mov     rcx, rdi
0x14002927d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029282  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x140029287  mov     ebx, 80h
0x14002928c  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x140029290  mov     [rsp+260h+dwCreationDisposition], 4; dwCreationDisposition
0x140029298  xor     r9d, r9d; lpSecurityAttributes
0x14002929b  xor     r8d, r8d; dwShareMode
0x14002929e  xor     edx, edx; dwDesiredAccess
0x1400292a0  mov     rcx, rax; lpFileName
0x1400292a3  call    cs:__imp_CreateFileW
0x1400292aa  nop     dword ptr [rax+rax+00h]
0x1400292af  mov     qword ptr [rsp+260h+NumberOfBytesWritten], rax
0x1400292b4  dec     rax
0x1400292b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400292bb  setnbe  al
0x1400292be  mov     rcx, [rbp+168h]; this
0x1400292c5  lea     rdx, aFailedToOpenOr; "Failed to open or create the persisted "...
0x1400292cc  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; bool
0x1400292d1  movzx   r9d, al; char *
0x1400292d5  lea     r12, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x1400292dc  mov     r8, r12; unsigned int
0x1400292df  lea     edx, [rbx+3Fh]; void *
0x1400292e2  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1400292e7  nop
0x1400292e8  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x1400292ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400292f2  lea     rcx, [rbp+160h+var_1C0]
0x1400292f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400292fb  mov     rcx, rax; lpFileName
0x1400292fe  mov     [rsp+260h+hTemplateFile], r15; hTemplateFile
0x140029303  mov     [rsp+260h+dwFlagsAndAttributes], ebx; char *
0x140029307  mov     [rsp+260h+dwCreationDisposition], 2; dwCreationDisposition
0x14002930f  xor     r9d, r9d; lpSecurityAttributes
0x140029312  xor     r8d, r8d; dwShareMode
0x140029315  mov     edx, 40000000h; dwDesiredAccess
0x14002931a  call    cs:__imp_CreateFileW
0x140029321  nop     dword ptr [rax+rax+00h]
0x140029326  mov     rbx, rax
0x140029329  mov     [rsp+260h+var_210], rax
0x14002932e  dec     rax
0x140029331  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029335  setnbe  al
0x140029338  mov     rcx, [rbp+168h]; this
0x14002933f  lea     rdx, aFailedToOpenTe; "Failed to open temp file for writing ne"...
0x140029346  mov     qword ptr [rsp+260h+dwCreationDisposition], rdx; int
0x14002934b  movzx   r9d, al; char *
0x14002934f  mov     r8, r12; unsigned int
0x140029352  mov     edx, 0C5h; void *
0x140029357  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x14002935c  mov     rcx, [r14+8]
0x140029360  sub     rcx, [r14]; __int64
0x140029363  mov     rax, [rbp+168h]
0x14002936a  cmp     rcx, 70h ; 'p'
0x14002936e  jb      loc_140029513
0x140029374  mov     [rsp+260h+nNumberOfBytesToWrite], r15d
0x140029379  lea     rdx, [rsp+260h+nNumberOfBytesToWrite]; unsigned int *
0x14002937e  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x140029383  mov     rcx, [rbp+168h]; this
0x14002938a  test    eax, eax
0x14002938c  js      loc_14002952A
0x140029392  mov     [rsp+260h+NumberOfBytesWritten], r15d
0x140029397  mov     qword ptr [rsp+260h+dwCreationDisposition], r15; lpOverlapped
0x14002939c  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400293a1  mov     esi, [rsp+260h+nNumberOfBytesToWrite]
0x1400293a5  mov     r8d, esi; nNumberOfBytesToWrite
0x1400293a8  mov     rdx, [r14]; lpBuffer
0x1400293ab  mov     rcx, rbx; hFile
0x1400293ae  call    cs:__imp_WriteFile
0x1400293b5  nop     dword ptr [rax+rax+00h]
0x1400293ba  mov     rcx, [rbp+168h]; this
0x1400293c1  mov     r8, r12; unsigned int
0x1400293c4  test    eax, eax
0x1400293c6  jz      loc_14002953B
0x1400293cc  mov     eax, [rsp+260h+NumberOfBytesWritten]
0x1400293d0  cmp     eax, esi
0x1400293d2  setb    dl
0x1400293d5  mov     rcx, [rbp+168h]; this
0x1400293dc  mov     [rsp+260h+var_228], eax
0x1400293e0  mov     dword ptr [rsp+260h+hTemplateFile], esi; char *
0x1400293e4  lea     rax, aCouldNotWriteF; "Could not write full state! (%d,%d))"
0x1400293eb  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rax; bool
0x1400293f0  mov     byte ptr [rsp+260h+dwCreationDisposition], dl; char
0x1400293f4  mov     r9d, 8007007Ah; char *
0x1400293fa  mov     edx, 0D0h; void *
0x1400293ff  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140029404  mov     rcx, rbx; hFile
0x140029407  call    cs:__imp_FlushFileBuffers
0x14002940e  nop     dword ptr [rax+rax+00h]
0x140029413  nop
0x140029414  lea     rcx, [rsp+260h+var_210]
0x140029419  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002941e  mov     rcx, rdi
0x140029421  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029426  mov     rdx, rax
0x140029429  lea     rcx, [rbp+160h+var_1C0]
0x14002942d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140029432  mov     rcx, rax; lpExistingFileName
0x140029435  mov     r8d, 1; dwFlags
0x14002943b  call    cs:__imp_MoveFileExW
0x140029442  nop     dword ptr [rax+rax+00h]
0x140029447  mov     rcx, [rbp+168h]; this
0x14002944e  test    eax, eax
0x140029450  jz      loc_140029505
0x140029456  mov     rdx, rdi
0x140029459  lea     rcx, [rbp+160h+var_1E0]
0x14002945d  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140029462  nop
0x140029463  lea     rcx, [rbp+160h+var_1E0]; this
0x140029467  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x14002946c  mov     rbx, rax
0x14002946f  lea     rcx, [rbp+160h+var_1E0]
0x140029473  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029478  mov     rcx, [r14+8]
0x14002947c  sub     rcx, [r14]
0x14002947f  cmp     rbx, rcx
0x140029482  setb    al
0x140029485  mov     rcx, [rbp+168h]; this
0x14002948c  lea     rdx, aFinalSizeOfPer; "Final size of persisted data is invalid"...
0x140029493  mov     qword ptr [rsp+260h+dwFlagsAndAttributes], rdx; bool
0x140029498  mov     byte ptr [rsp+260h+dwCreationDisposition], al; char
0x14002949c  mov     r9d, 8007001Dh; char *
0x1400294a2  mov     r8, r12; unsigned int
0x1400294a5  mov     edx, 0DAh; void *
0x1400294aa  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400294af  xor     edx, edx
0x1400294b1  lea     rcx, [rbp+160h+var_180]
0x1400294b5  call    ?Stop@?$ActivityBase@VLogging@SvcLib@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::SvcLib::Logging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400294ba  nop
0x1400294bb  lea     rcx, [rsp+260h+var_200]
0x1400294c0  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x1400294c5  nop
0x1400294c6  lea     rcx, [rbp+160h+var_1C0]
0x1400294ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400294cf  nop
0x1400294d0  lea     rcx, [rbp+160h+var_180]; this
0x1400294d4  call    ??1SaveVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::SvcLib::Logging::SaveVolumePersistedData::~SaveVolumePersistedData(void)
0x1400294d9  mov     rcx, [rbp+160h+var_30]
0x1400294e0  xor     rcx, rsp; StackCookie
0x1400294e3  call    __security_check_cookie
0x1400294e8  lea     r11, [rsp+260h+var_20]
0x1400294f0  mov     rbx, [r11+40h]
0x1400294f4  mov     rsi, [r11+48h]
0x1400294f8  mov     rsp, r11
0x1400294fb  pop     r15
0x1400294fd  pop     r14
0x1400294ff  pop     r12
0x140029501  pop     rdi
0x140029502  pop     rbp
0x140029503  retn
0x140029505  mov     r8, r12; unsigned int
0x140029508  mov     edx, 0D6h; void *
0x14002950d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140029513  mov     r9d, 80070057h; char *
0x140029519  mov     r8, r12; unsigned int
0x14002951c  mov     edx, 0C9h; void *
0x140029521  mov     rcx, rax; this
0x140029524  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002952a  mov     r9d, eax; char *
0x14002952d  mov     r8, r12; unsigned int
0x140029530  mov     edx, 0CCh; void *
0x140029535  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002953b  mov     edx, 0CFh; void *
0x140029540  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
