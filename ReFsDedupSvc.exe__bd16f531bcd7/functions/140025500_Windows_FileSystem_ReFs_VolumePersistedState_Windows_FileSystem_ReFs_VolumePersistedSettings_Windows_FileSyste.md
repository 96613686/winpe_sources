# `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSettings,Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::LoadFrom(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (void)>)'::`2'::_lambda_1_::operator()(Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData &)

- ea: `0x140025500`
- end: `0x1400257f2`
- name: `??R_lambda_1_@?1??LoadFrom@?$VolumePersistedState@VVolumePersistedSettings@ReFs@FileSystem@Windows@@UOnDiskSvcSettings@PersistedSettings_v1@234@@ReFs@FileSystem@Windows@@KA?AVVolumePersistedSettings@345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXXZ@8@@Z@QEBA@AEAVLoadVolumePersistedData@Logging@SvcLib@345@@Z`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x140023984`

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
- `0x140023bf0`
- `0x1400243ec`
- `0x140024924`
- `0x140025500`
- `0x140025e3c`
- `0x140029b70`
- `0x14002a468`
- `0x14002be80`
- `0x14002c7d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140025624`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140025624`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400255d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400255d4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400256b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400256b0`

## string_xrefs

- `0x1400255f5`: `Failed to open the service state file for the volume`

## pseudocode

```c
_QWORD *__fastcall `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSettings,Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::LoadFrom'::`2'::_lambda_1_::operator()(
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
    if ( v16 >= 0x20 )
    {
      NumberOfBytesRead = 0;
      v21 = nNumberOfBytesToRead;
      Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::BlobMem<Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>(
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
        New = Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(v36);
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
      v17 = (__int64 *)Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(&lpBuffer);
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
    v8 = (__int64 *)Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(&lpBuffer);
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
0x140025500  mov     [rsp-8+arg_18], rbx
0x140025505  push    rbp
0x140025506  push    rsi
0x140025507  push    rdi
0x140025508  push    r12
0x14002550a  push    r13
0x14002550c  push    r14
0x14002550e  push    r15
0x140025510  lea     rbp, [rsp-27h]
0x140025515  sub     rsp, 0D0h
0x14002551c  mov     rax, cs:__security_cookie
0x140025523  xor     rax, rsp
0x140025526  mov     [rbp+57h+var_38], rax
0x14002552a  mov     r15, r8
0x14002552d  mov     rdi, rdx
0x140025530  mov     r14, rcx
0x140025533  mov     [rbp+57h+var_B8], rdx
0x140025537  xor     r12d, r12d
0x14002553a  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x140025541  lea     rcx, [rbp+57h+var_70]; this
0x140025545  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x14002554a  nop
0x14002554b  mov     rdx, [r14]
0x14002554e  lea     rcx, [rbp+57h+lpBuffer]
0x140025552  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140025557  nop
0x140025558  lea     rcx, [rbp+57h+lpBuffer]; this
0x14002555c  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x140025561  mov     bl, al
0x140025563  lea     rcx, [rbp+57h+lpBuffer]
0x140025567  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002556c  test    bl, bl
0x14002556e  jnz     short loc_1400255A8
0x140025570  lea     rcx, [rbp+57h+lpBuffer]
0x140025574  call    ?AllocateNew@OnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(void)
0x140025579  mov     r8, [rax+10h]
0x14002557d  mov     [rax+10h], r12
0x140025581  mov     rdx, [rax+8]
0x140025585  mov     [rax+8], r12
0x140025589  mov     rcx, [rax]
0x14002558c  mov     [rax], r12
0x14002558f  mov     [rdi], rcx
0x140025592  mov     [rdi+8], rdx
0x140025596  mov     [rdi+10h], r8
0x14002559a  lea     rcx, [rbp+57h+lpBuffer]
0x14002559e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400255a3  jmp     loc_14002577A
0x1400255a8  mov     rcx, [r14]
0x1400255ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400255b0  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x1400255b5  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], 80h; char *
0x1400255bd  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1400255c5  xor     r9d, r9d; lpSecurityAttributes
0x1400255c8  mov     edx, 80000000h; dwDesiredAccess
0x1400255cd  lea     r8d, [r9+1]; dwShareMode
0x1400255d1  mov     rcx, rax; lpFileName
0x1400255d4  call    cs:__imp_CreateFileW
0x1400255db  nop     dword ptr [rax+rax+00h]
0x1400255e0  mov     rbx, rax
0x1400255e3  mov     [rbp+57h+var_B8], rax
0x1400255e7  dec     rax
0x1400255ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400255ee  setnbe  al
0x1400255f1  mov     rcx, [rbp+5Fh]; this
0x1400255f5  lea     rdx, aFailedToOpenTh; "Failed to open the service state file f"...
0x1400255fc  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx; int
0x140025601  movzx   r9d, al; char *
0x140025605  lea     r13, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14002560c  mov     r8, r13; unsigned int
0x14002560f  mov     edx, 0F6h; void *
0x140025614  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140025619  mov     qword ptr [rbp+57h+FileSize], r12
0x14002561d  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140025621  mov     rcx, rbx; hFile
0x140025624  call    cs:__imp_GetFileSizeEx
0x14002562b  nop     dword ptr [rax+rax+00h]
0x140025630  mov     rcx, [rbp+5Fh]; this
0x140025634  test    eax, eax
0x140025636  jz      loc_1400257C2
0x14002563c  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x140025640  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x140025644  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x140025648  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x14002564d  mov     r10, [rbp+5Fh]
0x140025651  test    eax, eax
0x140025653  js      loc_1400257D0
0x140025659  cmp     rcx, 20h ; ' '
0x14002565d  lea     rcx, [rbp+57h+lpBuffer]
0x140025661  jnb     short loc_14002568E
0x140025663  call    ?AllocateNew@OnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(void)
0x140025668  mov     r8, [rax+10h]
0x14002566c  mov     [rax+10h], r12
0x140025670  mov     rdx, [rax+8]
0x140025674  mov     [rax+8], r12
0x140025678  mov     rcx, [rax]
0x14002567b  mov     [rax], r12
0x14002567e  mov     [rdi], rcx
0x140025681  mov     [rdi+8], rdx
0x140025685  mov     [rdi+10h], r8
0x140025689  jmp     loc_140025766
0x14002568e  mov     [rbp+57h+NumberOfBytesRead], r12d
0x140025692  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x140025695  mov     edx, esi
0x140025697  call    ??0?$BlobMem@UOnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@_K@Z; Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>::BlobMem<Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings>(unsigned __int64)
0x14002569c  nop
0x14002569d  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; int
0x1400256a2  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400256a6  mov     r8d, esi; nNumberOfBytesToRead
0x1400256a9  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1400256ad  mov     rcx, rbx; hFile
0x1400256b0  call    cs:__imp_ReadFile
0x1400256b7  nop     dword ptr [rax+rax+00h]
0x1400256bc  mov     rcx, [rbp+5Fh]; this
0x1400256c0  test    eax, eax
0x1400256c2  jz      loc_1400257E4
0x1400256c8  cmp     [rbp+57h+NumberOfBytesRead], esi
0x1400256cb  setnz   al
0x1400256ce  mov     rcx, [rbp+5Fh]; this
0x1400256d2  test    al, al
0x1400256d4  jnz     loc_1400257AE
0x1400256da  mov     rcx, [rbp+57h+lpBuffer]
0x1400256de  movups  xmm0, xmmword ptr [rcx]
0x1400256e1  movdqu  [rbp+57h+var_90], xmm0
0x1400256e6  lea     rax, [rcx+10h]
0x1400256ea  mov     [rbp+57h+var_A0], rax
0x1400256ee  mov     rax, [rbp+57h+var_50]
0x1400256f2  sub     rax, rcx
0x1400256f5  sub     rax, 10h
0x1400256f9  mov     [rbp+57h+var_98], rax
0x1400256fd  lea     rdx, [rbp+57h+var_90]
0x140025701  lea     rcx, [rbp+57h+var_A0]
0x140025705  call    ?ValidateHash@Md5Hasher@ReFs@FileSystem@Windows@@SA_NV?$span@$$CBE$0?0@std@@V?$array@E$0BA@@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ValidateHash(std::span<uchar const,-1>,std::array<uchar,16>)
0x14002570a  test    al, al
0x14002570c  jnz     short loc_140025743
0x14002570e  mov     rcx, [r14+8]
0x140025712  cmp     [rcx+38h], r12
0x140025716  jz      short loc_14002571D
0x140025718  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x14002571d  mov     rcx, r15; this
0x140025720  call    ?StateCorruptionReset@LoadVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData::StateCorruptionReset(void)
0x140025725  lea     rcx, [rbp+57h+var_90]
0x140025729  call    ?AllocateNew@OnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcSettings@PersistedSettings_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedSettings_v1::OnDiskSvcSettings::AllocateNew(void)
0x14002572e  mov     rdx, rax
0x140025731  lea     rcx, [rbp+57h+lpBuffer]
0x140025735  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14002573a  lea     rcx, [rbp+57h+var_90]
0x14002573e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140025743  mov     rdx, [rbp+57h+var_48]
0x140025747  mov     [rbp+57h+var_48], r12
0x14002574b  mov     rcx, [rbp+57h+var_50]
0x14002574f  mov     [rbp+57h+var_50], r12
0x140025753  mov     rax, [rbp+57h+lpBuffer]
0x140025757  mov     [rbp+57h+lpBuffer], r12
0x14002575b  mov     [rdi], rax
0x14002575e  mov     [rdi+8], rcx
0x140025762  mov     [rdi+10h], rdx
0x140025766  lea     rcx, [rbp+57h+lpBuffer]
0x14002576a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002576f  nop
0x140025770  lea     rcx, [rbp+57h+var_B8]
0x140025774  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025779  nop
0x14002577a  lea     rcx, [rbp+57h+var_70]
0x14002577e  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x140025783  mov     rax, rdi
0x140025786  mov     rcx, [rbp+57h+var_38]
0x14002578a  xor     rcx, rsp; StackCookie
0x14002578d  call    __security_check_cookie
0x140025792  mov     rbx, [rsp+100h+arg_18]
0x14002579a  add     rsp, 0D0h
0x1400257a1  pop     r15
0x1400257a3  pop     r14
0x1400257a5  pop     r13
0x1400257a7  pop     r12
0x1400257a9  pop     rdi
0x1400257aa  pop     rsi
0x1400257ab  pop     rbp
0x1400257ac  retn
0x1400257ae  mov     r9d, 8007001Eh; char *
0x1400257b4  mov     r8, r13; unsigned int
0x1400257b7  mov     edx, 10Bh; void *
0x1400257bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400257c2  mov     r8, r13; unsigned int
0x1400257c5  mov     edx, 0F9h; void *
0x1400257ca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400257d0  mov     r9d, eax; char *
0x1400257d3  mov     r8, r13; unsigned int
0x1400257d6  mov     edx, 0FDh; void *
0x1400257db  mov     rcx, r10; this
0x1400257de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400257e4  mov     r8, r13; unsigned int
0x1400257e7  mov     edx, 10Ah; void *
0x1400257ec  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
