# `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::LoadFrom(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (void)>)'::`2'::_lambda_1_::operator()(Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData &)

- ea: `0x140024f10`
- end: `0x140025202`
- name: `??R_lambda_1_@?1??LoadFrom@?$VolumePersistedState@VVolumePersistedSchedule@ReFs@FileSystem@Windows@@UOnDiskSchedule@PersistedData_v1@234@@ReFs@FileSystem@Windows@@KA?AVVolumePersistedSchedule@345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXXZ@8@@Z@QEBA@AEAVLoadVolumePersistedData@Logging@SvcLib@345@@Z`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x1400238c4`

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
- `0x140023b04`
- `0x1400243ec`
- `0x140024924`
- `0x140024f10`
- `0x140025d50`
- `0x140029b70`
- `0x14002a468`
- `0x14002be80`
- `0x14002c7d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140025034`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140025034`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140024fe4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140024fe4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400250c0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400250c0`

## string_xrefs

- `0x140025005`: `Failed to open the service state file for the volume`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall `Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedSchedule,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::LoadFrom'::`2'::_lambda_1_::operator()(
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
    if ( v16 >= 0x70 )
    {
      NumberOfBytesRead = 0;
      v21 = nNumberOfBytesToRead;
      Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>(
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
        New = Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(v36);
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
      v17 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(&lpBuffer);
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
    v8 = (__int64 *)Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(&lpBuffer);
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
0x140024f10  mov     [rsp-8+arg_18], rbx
0x140024f15  push    rbp
0x140024f16  push    rsi
0x140024f17  push    rdi
0x140024f18  push    r12
0x140024f1a  push    r13
0x140024f1c  push    r14
0x140024f1e  push    r15
0x140024f20  lea     rbp, [rsp-27h]
0x140024f25  sub     rsp, 0D0h
0x140024f2c  mov     rax, cs:__security_cookie
0x140024f33  xor     rax, rsp
0x140024f36  mov     [rbp+57h+var_38], rax
0x140024f3a  mov     r15, r8
0x140024f3d  mov     rdi, rdx
0x140024f40  mov     r14, rcx
0x140024f43  mov     [rbp+57h+var_B8], rdx
0x140024f47  xor     r12d, r12d
0x140024f4a  mov     rdx, cs:qword_140223020; struct _TOKEN_PRIVILEGES *
0x140024f51  lea     rcx, [rbp+57h+var_70]; this
0x140024f55  call    ?ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z; Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)
0x140024f5a  nop
0x140024f5b  mov     rdx, [r14]
0x140024f5e  lea     rcx, [rbp+57h+lpBuffer]
0x140024f62  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140024f67  nop
0x140024f68  lea     rcx, [rbp+57h+lpBuffer]; this
0x140024f6c  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x140024f71  mov     bl, al
0x140024f73  lea     rcx, [rbp+57h+lpBuffer]
0x140024f77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140024f7c  test    bl, bl
0x140024f7e  jnz     short loc_140024FB8
0x140024f80  lea     rcx, [rbp+57h+lpBuffer]
0x140024f84  call    ?AllocateNew@OnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(void)
0x140024f89  mov     r8, [rax+10h]
0x140024f8d  mov     [rax+10h], r12
0x140024f91  mov     rdx, [rax+8]
0x140024f95  mov     [rax+8], r12
0x140024f99  mov     rcx, [rax]
0x140024f9c  mov     [rax], r12
0x140024f9f  mov     [rdi], rcx
0x140024fa2  mov     [rdi+8], rdx
0x140024fa6  mov     [rdi+10h], r8
0x140024faa  lea     rcx, [rbp+57h+lpBuffer]
0x140024fae  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024fb3  jmp     loc_14002518A
0x140024fb8  mov     rcx, [r14]
0x140024fbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140024fc0  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x140024fc5  mov     dword ptr [rsp+100h+dwFlagsAndAttributes], 80h; char *
0x140024fcd  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x140024fd5  xor     r9d, r9d; lpSecurityAttributes
0x140024fd8  mov     edx, 80000000h; dwDesiredAccess
0x140024fdd  lea     r8d, [r9+1]; dwShareMode
0x140024fe1  mov     rcx, rax; lpFileName
0x140024fe4  call    cs:__imp_CreateFileW
0x140024feb  nop     dword ptr [rax+rax+00h]
0x140024ff0  mov     rbx, rax
0x140024ff3  mov     [rbp+57h+var_B8], rax
0x140024ff7  dec     rax
0x140024ffa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140024ffe  setnbe  al
0x140025001  mov     rcx, [rbp+5Fh]; this
0x140025005  lea     rdx, aFailedToOpenTh; "Failed to open the service state file f"...
0x14002500c  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx; int
0x140025011  movzx   r9d, al; char *
0x140025015  lea     r13, aOnecoreBaseFsR_7; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14002501c  mov     r8, r13; unsigned int
0x14002501f  mov     edx, 0F6h; void *
0x140025024  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140025029  mov     qword ptr [rbp+57h+FileSize], r12
0x14002502d  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140025031  mov     rcx, rbx; hFile
0x140025034  call    cs:__imp_GetFileSizeEx
0x14002503b  nop     dword ptr [rax+rax+00h]
0x140025040  mov     rcx, [rbp+5Fh]; this
0x140025044  test    eax, eax
0x140025046  jz      loc_1400251D2
0x14002504c  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x140025050  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x140025054  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x140025058  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x14002505d  mov     r10, [rbp+5Fh]
0x140025061  test    eax, eax
0x140025063  js      loc_1400251E0
0x140025069  cmp     rcx, 70h ; 'p'
0x14002506d  lea     rcx, [rbp+57h+lpBuffer]
0x140025071  jnb     short loc_14002509E
0x140025073  call    ?AllocateNew@OnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(void)
0x140025078  mov     r8, [rax+10h]
0x14002507c  mov     [rax+10h], r12
0x140025080  mov     rdx, [rax+8]
0x140025084  mov     [rax+8], r12
0x140025088  mov     rcx, [rax]
0x14002508b  mov     [rax], r12
0x14002508e  mov     [rdi], rcx
0x140025091  mov     [rdi+8], rdx
0x140025095  mov     [rdi+10h], r8
0x140025099  jmp     loc_140025176
0x14002509e  mov     [rbp+57h+NumberOfBytesRead], r12d
0x1400250a2  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x1400250a5  mov     edx, esi
0x1400250a7  call    ??0?$BlobMem@UOnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@_K@Z; Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>(unsigned __int64)
0x1400250ac  nop
0x1400250ad  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; int
0x1400250b2  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400250b6  mov     r8d, esi; nNumberOfBytesToRead
0x1400250b9  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1400250bd  mov     rcx, rbx; hFile
0x1400250c0  call    cs:__imp_ReadFile
0x1400250c7  nop     dword ptr [rax+rax+00h]
0x1400250cc  mov     rcx, [rbp+5Fh]; this
0x1400250d0  test    eax, eax
0x1400250d2  jz      loc_1400251F4
0x1400250d8  cmp     [rbp+57h+NumberOfBytesRead], esi
0x1400250db  setnz   al
0x1400250de  mov     rcx, [rbp+5Fh]; this
0x1400250e2  test    al, al
0x1400250e4  jnz     loc_1400251BE
0x1400250ea  mov     rcx, [rbp+57h+lpBuffer]
0x1400250ee  movups  xmm0, xmmword ptr [rcx]
0x1400250f1  movdqu  [rbp+57h+var_90], xmm0
0x1400250f6  lea     rax, [rcx+10h]
0x1400250fa  mov     [rbp+57h+var_A0], rax
0x1400250fe  mov     rax, [rbp+57h+var_50]
0x140025102  sub     rax, rcx
0x140025105  sub     rax, 10h
0x140025109  mov     [rbp+57h+var_98], rax
0x14002510d  lea     rdx, [rbp+57h+var_90]
0x140025111  lea     rcx, [rbp+57h+var_A0]
0x140025115  call    ?ValidateHash@Md5Hasher@ReFs@FileSystem@Windows@@SA_NV?$span@$$CBE$0?0@std@@V?$array@E$0BA@@6@@Z; Windows::FileSystem::ReFs::Md5Hasher::ValidateHash(std::span<uchar const,-1>,std::array<uchar,16>)
0x14002511a  test    al, al
0x14002511c  jnz     short loc_140025153
0x14002511e  mov     rcx, [r14+8]
0x140025122  cmp     [rcx+38h], r12
0x140025126  jz      short loc_14002512D
0x140025128  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x14002512d  mov     rcx, r15; this
0x140025130  call    ?StateCorruptionReset@LoadVolumePersistedData@Logging@SvcLib@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::SvcLib::Logging::LoadVolumePersistedData::StateCorruptionReset(void)
0x140025135  lea     rcx, [rbp+57h+var_90]
0x140025139  call    ?AllocateNew@OnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@SA?AU?$BlobMem@UOnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@345@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::AllocateNew(void)
0x14002513e  mov     rdx, rax
0x140025141  lea     rcx, [rbp+57h+lpBuffer]
0x140025145  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14002514a  lea     rcx, [rbp+57h+var_90]
0x14002514e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140025153  mov     rdx, [rbp+57h+var_48]
0x140025157  mov     [rbp+57h+var_48], r12
0x14002515b  mov     rcx, [rbp+57h+var_50]
0x14002515f  mov     [rbp+57h+var_50], r12
0x140025163  mov     rax, [rbp+57h+lpBuffer]
0x140025167  mov     [rbp+57h+lpBuffer], r12
0x14002516b  mov     [rdi], rax
0x14002516e  mov     [rdi+8], rcx
0x140025172  mov     [rdi+10h], rdx
0x140025176  lea     rcx, [rbp+57h+lpBuffer]
0x14002517a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002517f  nop
0x140025180  lea     rcx, [rbp+57h+var_B8]
0x140025184  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025189  nop
0x14002518a  lea     rcx, [rbp+57h+var_70]
0x14002518e  call    ??1?$lambda_call@V_lambda_1_@?1??ScopedAdjustTokenPrivileges@ReFs@FileSystem@Windows@@YA@PEBU_TOKEN_PRIVILEGES@@@Z@@details@wil@@QEAA@XZ; wil::details::lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>::~lambda_call<`Windows::FileSystem::ReFs::ScopedAdjustTokenPrivileges(_TOKEN_PRIVILEGES const *)'::`2'::_lambda_1_>(void)
0x140025193  mov     rax, rdi
0x140025196  mov     rcx, [rbp+57h+var_38]
0x14002519a  xor     rcx, rsp; StackCookie
0x14002519d  call    __security_check_cookie
0x1400251a2  mov     rbx, [rsp+100h+arg_18]
0x1400251aa  add     rsp, 0D0h
0x1400251b1  pop     r15
0x1400251b3  pop     r14
0x1400251b5  pop     r13
0x1400251b7  pop     r12
0x1400251b9  pop     rdi
0x1400251ba  pop     rsi
0x1400251bb  pop     rbp
0x1400251bc  retn
0x1400251be  mov     r9d, 8007001Eh; char *
0x1400251c4  mov     r8, r13; unsigned int
0x1400251c7  mov     edx, 10Bh; void *
0x1400251cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400251d2  mov     r8, r13; unsigned int
0x1400251d5  mov     edx, 0F9h; void *
0x1400251da  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400251e0  mov     r9d, eax; char *
0x1400251e3  mov     r8, r13; unsigned int
0x1400251e6  mov     edx, 0FDh; void *
0x1400251eb  mov     rcx, r10; this
0x1400251ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400251f4  mov     r8, r13; unsigned int
0x1400251f7  mov     edx, 10Ah; void *
0x1400251fc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
