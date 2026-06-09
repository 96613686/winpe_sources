# `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedScrubSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::LoadFrom(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (void)>)'::`2'::_lambda_1_::operator()(Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData &)

- ea: `0x140025208`
- end: `0x1400254fa`
- name: `??R_lambda_1_@?1??LoadFrom@?$VolumePersistedState@VVolumePersistedScrubSchedule@ReFs@FileSystem@Windows@@UOnDiskScrubSchedule@PersistedData_v1@234@@ReFs@FileSystem@Windows@@KA?AVVolumePersistedScrubSchedule@345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXXZ@8@@Z@QEBA@AEAVLoadVolumePersistedData@Logging@SvcLib@345@@Z`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x140023924`

## callees

- `0x140004870`
- `0x140018f38`
- `0x140018f7c`
- `0x140019130`
- `0x140019600`
- `0x1400196b8`
- `0x14001983c`
- `0x14001c194`
- `0x14001c9e4`
- `0x14001fa14`
- `0x140022214`
- `0x140023b40`
- `0x1400243ec`
- `0x140024924`
- `0x140025208`
- `0x140025dc0`
- `0x140029b70`
- `0x14002a468`
- `0x14002be80`
- `0x14002c7d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14002532c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14002532c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400252dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400252dc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400253b8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400253b8`

## string_xrefs

- `0x1400252fd`: `Failed to open the service state file for the volume`

## pseudocode

```c
_QWORD *__fastcall `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedScrubSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::LoadFrom'::`2'::_lambda_1_::operator()(
        __int64 *a1,
        _QWORD *a2,
        Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData *a3)
{
  const struct std::filesystem::path *v6; // rdx
  bool v7; // bl
  __int64 *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  char *FileW; // rbx
  const char *v14; // r9
  int v15; // eax
  unsigned __int64 v16; // rcx
  __int64 *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  DWORD v21; // esi
  const char *v22; // r9
  __int64 New; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  LPVOID v26; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-89h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-89h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-81h]
  DWORD nNumberOfBytesToRead; // [rsp+40h] [rbp-69h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-65h] BYREF
  _QWORD *v33; // [rsp+48h] [rbp-61h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-49h] BYREF
  _OWORD v36[2]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v37[24]; // [rsp+90h] [rbp-19h] BYREF
  LPVOID lpBuffer; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v39; // [rsp+B0h] [rbp+7h]
  __int64 v40; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v33 = a2;
  Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges((Windows::FileSystem::ReFs *)v37, qword_140223020);
  std::filesystem::path::path((__int64)&lpBuffer, *a1);
  v7 = std::filesystem::exists((std::filesystem *)&lpBuffer, v6);
  std::wstring::_Tidy_deallocate(&lpBuffer);
  if ( v7 )
  {
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1);
    FileW = (char *)CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v33 = FileW;
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
      (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
      (bool)"Failed to open the service state file for the volume",
      dwFlagsAndAttributes);
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
        v14);
    nNumberOfBytesToRead = 0;
    v15 = LongLongToULong(FileSize.QuadPart, &nNumberOfBytesToRead);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
    if ( v16 >= 0x28 )
    {
      NumberOfBytesRead = 0;
      v21 = nNumberOfBytesToRead;
      Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>(
        &lpBuffer,
        nNumberOfBytesToRead);
      if ( !ReadFile(FileW, lpBuffer, v21, &NumberOfBytesRead, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
          v22);
      if ( NumberOfBytesRead != v21 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\VolumePersistedState.h",
          (const char *)0x8007001ELL,
          dwCreationDispositiona);
      v36[0] = *(_OWORD *)lpBuffer;
      v35[0] = (char *)lpBuffer + 16;
      v35[1] = v39 - (_QWORD)lpBuffer - 16;
      if ( !(unsigned __int8)Windows::FileSystem::ReFs::Md5Hasher::ValidateHash(v35, v36) )
      {
        if ( *(_QWORD *)(a1[1] + 56) )
          std::_Func_class<void,>::operator()();
        Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData::StateCorruptionReset(a3);
        New = Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(v36);
        std::vector<unsigned char>::operator=(&lpBuffer, New);
        std::vector<unsigned char>::_Tidy(v36);
      }
      v24 = v40;
      v40 = 0;
      v25 = v39;
      v39 = 0;
      v26 = lpBuffer;
      lpBuffer = 0;
      *a2 = v26;
      a2[1] = v25;
      a2[2] = v24;
    }
    else
    {
      v17 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(&lpBuffer);
      v18 = v17[2];
      v17[2] = 0;
      v19 = v17[1];
      v17[1] = 0;
      v20 = *v17;
      *v17 = 0;
      *a2 = v20;
      a2[1] = v19;
      a2[2] = v18;
    }
    std::vector<unsigned char>::_Tidy(&lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  }
  else
  {
    v8 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(&lpBuffer);
    v9 = v8[2];
    v8[2] = 0;
    v10 = v8[1];
    v8[1] = 0;
    v11 = *v8;
    *v8 = 0;
    *a2 = v11;
    a2[1] = v10;
    a2[2] = v9;
    std::vector<unsigned char>::_Tidy(&lpBuffer);
  }
  __1__lambda_call_V_lambda_1___1__ScopedAdjustTokenPrivileges_ReFs_FileSystem_Windows__YA_PEBU_TOKEN_PRIVILEGES___Z__details_wil__QEAA_XZ(v37);
  return a2;
}

```

## disassembly

```asm
0x140025208  mov     [rsp-8+arg_18], rbx
0x14002520d  push    rbp
0x14002520e  push    rsi
0x14002520f  push    rdi
0x140025210  push    r12
0x140025212  push    r13
0x140025214  push    r14
0x140025216  push    r15
0x140025218  lea     rbp, [rsp-27h]
0x14002521d  sub     rsp, 0D0h
0x140025224  mov     rax, cs:__security_cookie
0x14002522b  xor     rax, rsp
0x14002522e  mov     [rbp+57h+var_38], rax
0x140025232  mov     r15, r8
0x140025235  mov     rdi, rdx
0x140025238  mov     r14, rcx
0x14002523b  mov     [rbp+57h+var_B8], rdx
0x14002523f  xor     r12d, r12d
0x140025242  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x140025249  lea     rcx, [rbp+57h+var_70]; this
0x14002524d  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x140025252  nop
0x140025253  mov     rdx, [r14]
0x140025256  lea     rcx, [rbp+57h+lpBuffer]
0x14002525a  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x14002525f  nop
0x140025260  lea     rcx, [rbp+57h+lpBuffer]; this
0x140025264  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x140025269  mov     bl, al
0x14002526b  lea     rcx, [rbp+57h+lpBuffer]
0x14002526f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025274  test    bl, bl
0x140025276  jnz     short loc_1400252B0
0x140025278  lea     rcx, [rbp+57h+lpBuffer]
0x14002527c  call    ?AllocateNew@OnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(void)
0x140025281  mov     r8, [rax+10h]
0x140025285  mov     [rax+10h], r12
0x140025289  mov     rdx, [rax+8]
0x14002528d  mov     [rax+8], r12
0x140025291  mov     rcx, [rax]
0x140025294  mov     [rax], r12
0x140025297  mov     [rdi], rcx
0x14002529a  mov     [rdi+8], rdx
0x14002529e  mov     [rdi+10h], r8
0x1400252a2  lea     rcx, [rbp+57h+lpBuffer]
0x1400252a6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400252ab  jmp     loc_140025482
0x1400252b0  mov     rcx, [r14]
0x1400252b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400252b8  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x1400252bd  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], 80h; char *
0x1400252c5  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1400252cd  xor     r9d, r9d; lpSecurityAttributes
0x1400252d0  mov     edx, 80000000h; dwDesiredAccess
0x1400252d5  lea     r8d, [r9+1]; dwShareMode
0x1400252d9  mov     rcx, rax; lpFileName
0x1400252dc  call    cs:__imp_CreateFileW
0x1400252e3  nop     dword ptr [rax+rax+00h]
0x1400252e8  mov     rbx, rax
0x1400252eb  mov     [rbp+57h+var_B8], rax
0x1400252ef  dec     rax
0x1400252f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400252f6  setnbe  al
0x1400252f9  mov     rcx, [rbp+5Fh]; this
0x1400252fd  lea     rdx, aFailedToOpenTh; "Failed to open the service state file f"...
0x140025304  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx; int
0x140025309  movzx   r9d, al; char *
0x14002530d  lea     r13, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140025314  mov     r8, r13; unsigned int
0x140025317  mov     edx, 0F6h; void *
0x14002531c  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140025321  mov     qword ptr [rbp+57h+FileSize], r12
0x140025325  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140025329  mov     rcx, rbx; hFile
0x14002532c  call    cs:__imp_GetFileSizeEx
0x140025333  nop     dword ptr [rax+rax+00h]
0x140025338  mov     rcx, [rbp+5Fh]; this
0x14002533c  test    eax, eax
0x14002533e  jz      loc_1400254CA
0x140025344  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x140025348  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x14002534c  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x140025350  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x140025355  mov     r10, [rbp+5Fh]
0x140025359  test    eax, eax
0x14002535b  js      loc_1400254D8
0x140025361  cmp     rcx, 28h ; '('
0x140025365  lea     rcx, [rbp+57h+lpBuffer]
0x140025369  jnb     short loc_140025396
0x14002536b  call    ?AllocateNew@OnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(void)
0x140025370  mov     r8, [rax+10h]
0x140025374  mov     [rax+10h], r12
0x140025378  mov     rdx, [rax+8]
0x14002537c  mov     [rax+8], r12
0x140025380  mov     rcx, [rax]
0x140025383  mov     [rax], r12
0x140025386  mov     [rdi], rcx
0x140025389  mov     [rdi+8], rdx
0x14002538d  mov     [rdi+10h], r8
0x140025391  jmp     loc_14002546E
0x140025396  mov     [rbp+57h+NumberOfBytesRead], r12d
0x14002539a  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x14002539d  mov     edx, esi
0x14002539f  call    ??0?$BlobMem@UOnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@_K@Z; Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule>(unsigned __int64)
0x1400253a4  nop
0x1400253a5  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; int
0x1400253aa  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400253ae  mov     r8d, esi; nNumberOfBytesToRead
0x1400253b1  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1400253b5  mov     rcx, rbx; hFile
0x1400253b8  call    cs:__imp_ReadFile
0x1400253bf  nop     dword ptr [rax+rax+00h]
0x1400253c4  mov     rcx, [rbp+5Fh]; this
0x1400253c8  test    eax, eax
0x1400253ca  jz      loc_1400254EC
0x1400253d0  cmp     [rbp+57h+NumberOfBytesRead], esi
0x1400253d3  setnz   al
0x1400253d6  mov     rcx, [rbp+5Fh]; this
0x1400253da  test    al, al
0x1400253dc  jnz     loc_1400254B6
0x1400253e2  mov     rcx, [rbp+57h+lpBuffer]
0x1400253e6  movups  xmm0, xmmword ptr [rcx]
0x1400253e9  movdqu  [rbp+57h+var_90], xmm0
0x1400253ee  lea     rax, [rcx+10h]
0x1400253f2  mov     [rbp+57h+var_A0], rax
0x1400253f6  mov     rax, [rbp+57h+var_50]
0x1400253fa  sub     rax, rcx
0x1400253fd  sub     rax, 10h
0x140025401  mov     [rbp+57h+var_98], rax
0x140025405  lea     rdx, [rbp+57h+var_90]
0x140025409  lea     rcx, [rbp+57h+var_A0]
0x14002540d  call    ?ValidateHash@Md5Hasher@ReFs@FileSystem@Windows@@SA_NV?$span@$$CBE$0?0@std@@V?$array@E$0BA@@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ValidateHash(std::span<uchar const,-1>,std::array<uchar,16>)
0x140025412  test    al, al
0x140025414  jnz     short loc_14002544B
0x140025416  mov     rcx, [r14+8]
0x14002541a  cmp     [rcx+38h], r12
0x14002541e  jz      short loc_140025425
0x140025420  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x140025425  mov     rcx, r15; this
0x140025428  call    ?StateCorruptionReset@LoadVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData::StateCorruptionReset(void)
0x14002542d  lea     rcx, [rbp+57h+var_90]
0x140025431  call    ?AllocateNew@OnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskScrubSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskScrubSchedule::AllocateNew(void)
0x140025436  mov     rdx, rax
0x140025439  lea     rcx, [rbp+57h+lpBuffer]
0x14002543d  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140025442  lea     rcx, [rbp+57h+var_90]
0x140025446  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002544b  mov     rdx, [rbp+57h+var_48]
0x14002544f  mov     [rbp+57h+var_48], r12
0x140025453  mov     rcx, [rbp+57h+var_50]
0x140025457  mov     [rbp+57h+var_50], r12
0x14002545b  mov     rax, [rbp+57h+lpBuffer]
0x14002545f  mov     [rbp+57h+lpBuffer], r12
0x140025463  mov     [rdi], rax
0x140025466  mov     [rdi+8], rcx
0x14002546a  mov     [rdi+10h], rdx
0x14002546e  lea     rcx, [rbp+57h+lpBuffer]
0x140025472  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140025477  nop
0x140025478  lea     rcx, [rbp+57h+var_B8]
0x14002547c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025481  nop
0x140025482  lea     rcx, [rbp+57h+var_70]
0x140025486  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x14002548b  mov     rax, rdi
0x14002548e  mov     rcx, [rbp+57h+var_38]
0x140025492  xor     rcx, rsp; StackCookie
0x140025495  call    __security_check_cookie
0x14002549a  mov     rbx, [rsp+100h+arg_18]
0x1400254a2  add     rsp, 0D0h
0x1400254a9  pop     r15
0x1400254ab  pop     r14
0x1400254ad  pop     r13
0x1400254af  pop     r12
0x1400254b1  pop     rdi
0x1400254b2  pop     rsi
0x1400254b3  pop     rbp
0x1400254b4  retn
0x1400254b6  mov     r9d, 8007001Eh; char *
0x1400254bc  mov     r8, r13; unsigned int
0x1400254bf  mov     edx, 10Bh; void *
0x1400254c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400254ca  mov     r8, r13; unsigned int
0x1400254cd  mov     edx, 0F9h; void *
0x1400254d2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400254d8  mov     r9d, eax; char *
0x1400254db  mov     r8, r13; unsigned int
0x1400254de  mov     edx, 0FDh; void *
0x1400254e3  mov     rcx, r10; this
0x1400254e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400254ec  mov     r8, r13; unsigned int
0x1400254ef  mov     edx, 10Ah; void *
0x1400254f4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
