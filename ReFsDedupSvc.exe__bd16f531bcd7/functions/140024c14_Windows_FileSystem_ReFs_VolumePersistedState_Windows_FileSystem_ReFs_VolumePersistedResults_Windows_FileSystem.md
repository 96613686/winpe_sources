# `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::LoadFrom(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (void)>)'::`2'::_lambda_1_::operator()(Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData &)

- ea: `0x140024c14`
- end: `0x140024f09`
- name: `??R_lambda_1_@?1??LoadFrom@?$VolumePersistedState@VVolumePersistedResults@ReFs@FileSystem@Windows@@UOnDiskSvcResults@PersistedData_v1@234@@ReFs@FileSystem@Windows@@KA?AVVolumePersistedResults@345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXXZ@8@@Z@QEBA@AEAVLoadVolumePersistedData@Logging@SvcLib@345@@Z`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x140023864`

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
- `0x140023bb4`
- `0x1400243ec`
- `0x140024924`
- `0x140024c14`
- `0x140025dfc`
- `0x140029b70`
- `0x14002a468`
- `0x14002be80`
- `0x14002c7d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140024d38`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140024d38`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140024ce8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140024ce8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140024dc7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140024dc7`

## string_xrefs

- `0x140024d09`: `Failed to open the service state file for the volume`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::LoadFrom'::`2'::_lambda_1_::operator()(
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
    if ( v16 >= 0xE8 )
    {
      NumberOfBytesRead = 0;
      v21 = nNumberOfBytesToRead;
      Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>(
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
        New = Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(v36);
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
      v17 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(&lpBuffer);
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
    v8 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(&lpBuffer);
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
0x140024c14  mov     [rsp-8+arg_18], rbx
0x140024c19  push    rbp
0x140024c1a  push    rsi
0x140024c1b  push    rdi
0x140024c1c  push    r12
0x140024c1e  push    r13
0x140024c20  push    r14
0x140024c22  push    r15
0x140024c24  lea     rbp, [rsp-27h]
0x140024c29  sub     rsp, 0D0h
0x140024c30  mov     rax, cs:__security_cookie
0x140024c37  xor     rax, rsp
0x140024c3a  mov     [rbp+57h+var_38], rax
0x140024c3e  mov     r15, r8
0x140024c41  mov     rdi, rdx
0x140024c44  mov     r14, rcx
0x140024c47  mov     [rbp+57h+var_B8], rdx
0x140024c4b  xor     r12d, r12d
0x140024c4e  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x140024c55  lea     rcx, [rbp+57h+var_70]; this
0x140024c59  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x140024c5e  nop
0x140024c5f  mov     rdx, [r14]
0x140024c62  lea     rcx, [rbp+57h+lpBuffer]
0x140024c66  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140024c6b  nop
0x140024c6c  lea     rcx, [rbp+57h+lpBuffer]; this
0x140024c70  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x140024c75  mov     bl, al
0x140024c77  lea     rcx, [rbp+57h+lpBuffer]
0x140024c7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140024c80  test    bl, bl
0x140024c82  jnz     short loc_140024CBC
0x140024c84  lea     rcx, [rbp+57h+lpBuffer]
0x140024c88  call    ?AllocateNew@OnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(void)
0x140024c8d  mov     r8, [rax+10h]
0x140024c91  mov     [rax+10h], r12
0x140024c95  mov     rdx, [rax+8]
0x140024c99  mov     [rax+8], r12
0x140024c9d  mov     rcx, [rax]
0x140024ca0  mov     [rax], r12
0x140024ca3  mov     [rdi], rcx
0x140024ca6  mov     [rdi+8], rdx
0x140024caa  mov     [rdi+10h], r8
0x140024cae  lea     rcx, [rbp+57h+lpBuffer]
0x140024cb2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024cb7  jmp     loc_140024E91
0x140024cbc  mov     rcx, [r14]
0x140024cbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140024cc4  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x140024cc9  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], 80h; char *
0x140024cd1  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x140024cd9  xor     r9d, r9d; lpSecurityAttributes
0x140024cdc  mov     edx, 80000000h; dwDesiredAccess
0x140024ce1  lea     r8d, [r9+1]; dwShareMode
0x140024ce5  mov     rcx, rax; lpFileName
0x140024ce8  call    cs:__imp_CreateFileW
0x140024cef  nop     dword ptr [rax+rax+00h]
0x140024cf4  mov     rbx, rax
0x140024cf7  mov     [rbp+57h+var_B8], rax
0x140024cfb  dec     rax
0x140024cfe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140024d02  setnbe  al
0x140024d05  mov     rcx, [rbp+5Fh]; this
0x140024d09  lea     rdx, aFailedToOpenTh; "Failed to open the service state file f"...
0x140024d10  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx; int
0x140024d15  movzx   r9d, al; char *
0x140024d19  lea     r13, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140024d20  mov     r8, r13; unsigned int
0x140024d23  mov     edx, 0F6h; void *
0x140024d28  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140024d2d  mov     qword ptr [rbp+57h+FileSize], r12
0x140024d31  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140024d35  mov     rcx, rbx; hFile
0x140024d38  call    cs:__imp_GetFileSizeEx
0x140024d3f  nop     dword ptr [rax+rax+00h]
0x140024d44  mov     rcx, [rbp+5Fh]; this
0x140024d48  test    eax, eax
0x140024d4a  jz      loc_140024ED9
0x140024d50  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x140024d54  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x140024d58  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x140024d5c  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x140024d61  mov     r10, [rbp+5Fh]
0x140024d65  test    eax, eax
0x140024d67  js      loc_140024EE7
0x140024d6d  cmp     rcx, 0E8h
0x140024d74  lea     rcx, [rbp+57h+lpBuffer]
0x140024d78  jnb     short loc_140024DA5
0x140024d7a  call    ?AllocateNew@OnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(void)
0x140024d7f  mov     r8, [rax+10h]
0x140024d83  mov     [rax+10h], r12
0x140024d87  mov     rdx, [rax+8]
0x140024d8b  mov     [rax+8], r12
0x140024d8f  mov     rcx, [rax]
0x140024d92  mov     [rax], r12
0x140024d95  mov     [rdi], rcx
0x140024d98  mov     [rdi+8], rdx
0x140024d9c  mov     [rdi+10h], r8
0x140024da0  jmp     loc_140024E7D
0x140024da5  mov     [rbp+57h+NumberOfBytesRead], r12d
0x140024da9  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x140024dac  mov     edx, esi
0x140024dae  call    ??0?$BlobMem@UOnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@_K@Z; Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>(unsigned __int64)
0x140024db3  nop
0x140024db4  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; int
0x140024db9  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140024dbd  mov     r8d, esi; nNumberOfBytesToRead
0x140024dc0  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x140024dc4  mov     rcx, rbx; hFile
0x140024dc7  call    cs:__imp_ReadFile
0x140024dce  nop     dword ptr [rax+rax+00h]
0x140024dd3  mov     rcx, [rbp+5Fh]; this
0x140024dd7  test    eax, eax
0x140024dd9  jz      loc_140024EFB
0x140024ddf  cmp     [rbp+57h+NumberOfBytesRead], esi
0x140024de2  setnz   al
0x140024de5  mov     rcx, [rbp+5Fh]; this
0x140024de9  test    al, al
0x140024deb  jnz     loc_140024EC5
0x140024df1  mov     rcx, [rbp+57h+lpBuffer]
0x140024df5  movups  xmm0, xmmword ptr [rcx]
0x140024df8  movdqu  [rbp+57h+var_90], xmm0
0x140024dfd  lea     rax, [rcx+10h]
0x140024e01  mov     [rbp+57h+var_A0], rax
0x140024e05  mov     rax, [rbp+57h+var_50]
0x140024e09  sub     rax, rcx
0x140024e0c  sub     rax, 10h
0x140024e10  mov     [rbp+57h+var_98], rax
0x140024e14  lea     rdx, [rbp+57h+var_90]
0x140024e18  lea     rcx, [rbp+57h+var_A0]
0x140024e1c  call    ?ValidateHash@Md5Hasher@ReFs@FileSystem@Windows@@SA_NV?$span@$$CBE$0?0@std@@V?$array@E$0BA@@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ValidateHash(std::span<uchar const,-1>,std::array<uchar,16>)
0x140024e21  test    al, al
0x140024e23  jnz     short loc_140024E5A
0x140024e25  mov     rcx, [r14+8]
0x140024e29  cmp     [rcx+38h], r12
0x140024e2d  jz      short loc_140024E34
0x140024e2f  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x140024e34  mov     rcx, r15; this
0x140024e37  call    ?StateCorruptionReset@LoadVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData::StateCorruptionReset(void)
0x140024e3c  lea     rcx, [rbp+57h+var_90]
0x140024e40  call    ?AllocateNew@OnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSvcResults@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults::AllocateNew(void)
0x140024e45  mov     rdx, rax
0x140024e48  lea     rcx, [rbp+57h+lpBuffer]
0x140024e4c  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140024e51  lea     rcx, [rbp+57h+var_90]
0x140024e55  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024e5a  mov     rdx, [rbp+57h+var_48]
0x140024e5e  mov     [rbp+57h+var_48], r12
0x140024e62  mov     rcx, [rbp+57h+var_50]
0x140024e66  mov     [rbp+57h+var_50], r12
0x140024e6a  mov     rax, [rbp+57h+lpBuffer]
0x140024e6e  mov     [rbp+57h+lpBuffer], r12
0x140024e72  mov     [rdi], rax
0x140024e75  mov     [rdi+8], rcx
0x140024e79  mov     [rdi+10h], rdx
0x140024e7d  lea     rcx, [rbp+57h+lpBuffer]
0x140024e81  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024e86  nop
0x140024e87  lea     rcx, [rbp+57h+var_B8]
0x140024e8b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140024e90  nop
0x140024e91  lea     rcx, [rbp+57h+var_70]
0x140024e95  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x140024e9a  mov     rax, rdi
0x140024e9d  mov     rcx, [rbp+57h+var_38]
0x140024ea1  xor     rcx, rsp; StackCookie
0x140024ea4  call    __security_check_cookie
0x140024ea9  mov     rbx, [rsp+100h+arg_18]
0x140024eb1  add     rsp, 0D0h
0x140024eb8  pop     r15
0x140024eba  pop     r14
0x140024ebc  pop     r13
0x140024ebe  pop     r12
0x140024ec0  pop     rdi
0x140024ec1  pop     rsi
0x140024ec2  pop     rbp
0x140024ec3  retn
0x140024ec5  mov     r9d, 8007001Eh; char *
0x140024ecb  mov     r8, r13; unsigned int
0x140024ece  mov     edx, 10Bh; void *
0x140024ed3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140024ed9  mov     r8, r13; unsigned int
0x140024edc  mov     edx, 0F9h; void *
0x140024ee1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140024ee7  mov     r9d, eax; char *
0x140024eea  mov     r8, r13; unsigned int
0x140024eed  mov     edx, 0FDh; void *
0x140024ef2  mov     rcx, r10; this
0x140024ef5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140024efb  mov     r8, r13; unsigned int
0x140024efe  mov     edx, 10Ah; void *
0x140024f03  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
