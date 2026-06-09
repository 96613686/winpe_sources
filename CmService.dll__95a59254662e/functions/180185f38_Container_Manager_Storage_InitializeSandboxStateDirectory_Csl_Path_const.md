# Container::Manager::Storage::InitializeSandboxStateDirectory(Csl::Path const &)

- ea: `0x180185f38`
- end: `0x1801865d7`
- name: `?InitializeSandboxStateDirectory@Storage@Manager@Container@@YAJAEBVPath@Csl@@@Z`
- size: `1695`
- prototype: `__int64 __fastcall(Container::Manager::Storage *__hidden this, const struct Path *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801865e0`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016774`
- `0x18002c1f4`
- `0x18002fae4`
- `0x18002fd88`
- `0x180185f38`
- `0x180197608`
- `0x1801a2c00`
- `0x1801a2cfc`
- `0x1801a32f8`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180186000`
- `ntdll!RtlAcquirePrivilege` at `0x180186000`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180186156`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180186156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185fa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801863b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018644a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018652f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801865ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185fa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801863b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018644a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018652f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801865ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180185f70`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180185f70`

## string_xrefs

- `0x18018601a`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Container::Manager::Storage::InitializeSandboxStateDirectory(
        Container::Manager::Storage *this,
        const struct Path *a2)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  NTSTATUS v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  struct _SECURITY_ATTRIBUTES *v10; // r8
  int DirectoryRecursive; // eax
  int OsVersionInfo; // edi
  WCHAR *v13; // rcx
  const char *v14; // r9
  __int64 v15; // rdx
  struct _SECURITY_ATTRIBUTES *v16; // r8
  __int64 v17; // rdx
  struct _OSVERSIONINFOW *v18; // rdx
  wchar_t **v19; // rsi
  unsigned int v20; // eax
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdi
  unsigned int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // rcx
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v29; // [rsp+38h] [rbp-C8h]
  _WORD v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v31; // [rsp+50h] [rbp-B0h] BYREF
  char *v32; // [rsp+58h] [rbp-A8h]
  _WORD v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  void *v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v37[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v40; // [rsp+C4h] [rbp-3Ch]
  int v41; // [rsp+C8h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+218h] [rbp+118h] BYREF
  PVOID ReturnedState; // [rsp+220h] [rbp+120h] BYREF
  __int64 Privilege; // [rsp+228h] [rbp+128h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x16F,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                  v3);
LABEL_3:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return LastError;
  }
  v38[0] = 24;
  v38[2] = 0;
  v38[1] = SecurityDescriptor;
  ReturnedState = 0;
  Privilege = 0x1200000011LL;
  v6 = RtlAcquirePrivilege((PULONG)&Privilege, 2u, 0, &ReturnedState);
  if ( v6 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x52,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
           (const char *)(unsigned int)v6,
           v27);
    LastError = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)(unsigned int)v7,
        v27);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      goto LABEL_3;
    }
  }
  lpFileName = v30;
  v29 = v30;
  v30[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpFileName,
                           *(_QWORD *)this,
                           (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1) )
  {
    v8 = 383;
    goto LABEL_11;
  }
  v34 = L"WcSandboxState";
  v35 = 14;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&lpFileName) )
  {
    v8 = 384;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)0x8007000ELL,
      v27);
    v9 = (WCHAR *)lpFileName;
    if ( lpFileName != v30 )
      goto LABEL_72;
    goto LABEL_73;
  }
  DirectoryRecursive = Csl::CreateDirectoryRecursive((Csl *)&lpFileName, (const struct Path *)v38, v10);
  OsVersionInfo = DirectoryRecursive;
  if ( DirectoryRecursive < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)DirectoryRecursive,
      v27);
    goto LABEL_17;
  }
  if ( !SetFileAttributesW(lpFileName, 6u) )
  {
    OsVersionInfo = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x186,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                      v14);
LABEL_17:
    v13 = (WCHAR *)lpFileName;
    if ( lpFileName == v30 )
    {
LABEL_82:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return (unsigned int)OsVersionInfo;
    }
LABEL_81:
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_82;
  }
  v31 = v33;
  v32 = (char *)v33;
  v33[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v31,
                           lpFileName,
                           v29 - lpFileName) )
  {
    v15 = 395;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)0x8007000ELL,
      v27);
    goto LABEL_69;
  }
  v34 = L"Hives";
  v35 = 5;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&v31) )
  {
    v15 = 396;
    goto LABEL_23;
  }
  OsVersionInfo = Csl::CreateDirectoryRecursive((Csl *)&v31, 0, v16);
  if ( OsVersionInfo < 0 )
  {
    v17 = 398;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)OsVersionInfo,
      v27);
    goto LABEL_78;
  }
  memset_0(v39, 0, 0x114u);
  OsVersionInfo = Csl::GetOsVersionInfo((Csl *)v39, v18);
  if ( OsVersionInfo < 0 )
  {
    v17 = 401;
    goto LABEL_28;
  }
  v19 = off_1801C87B0;
  while ( 1 )
  {
    Privilege = 0;
    v20 = ORCreateHiveEx(&Privilege, 1);
    if ( v20 )
    {
      OsVersionInfo = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x199,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                        (const char *)v20,
                        v27);
      if ( Privilege )
        ORCloseHive(Privilege);
LABEL_78:
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      v13 = (WCHAR *)lpFileName;
      if ( lpFileName == v30 )
        goto LABEL_82;
      goto LABEL_81;
    }
    v36[0] = v37;
    v36[1] = v37;
    v37[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v36,
                             v31,
                             (v32 - (_BYTE *)v31) >> 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)0x8007000ELL,
        v27);
      if ( v36[0] != v37 )
        operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
      v26 = Privilege;
      if ( Privilege )
        goto LABEL_68;
      goto LABEL_69;
    }
    v21 = v19[2];
    v34 = v21;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v35 = v22;
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v36) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)0x8007000ELL,
        v27);
      if ( v36[0] != v37 )
        operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
      v26 = Privilege;
      if ( Privilege )
LABEL_68:
        ORCloseHive(v26);
LABEL_69:
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      v9 = (WCHAR *)lpFileName;
      if ( lpFileName != v30 )
LABEL_72:
        operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
LABEL_73:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return 2147942414LL;
    }
    v23 = Privilege;
    v24 = ORSaveHiveEx(Privilege, v36[0], v40, v41, 1);
    if ( v24 )
      break;
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 )
      ORCloseHive(v23);
    v19 += 3;
    if ( v19 == (wchar_t **)&HNS::Schema::Global::Version_ClassData )
    {
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      if ( lpFileName != v30 )
        operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return 0;
    }
  }
  v25 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
          (const char *)v24,
          v27);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v23 )
    ORCloseHive(v23);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v30 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v25;
}

```

## disassembly

```asm
0x180185f38  push    rbp
0x180185f3a  push    rbx
0x180185f3b  push    rsi
0x180185f3c  push    rdi
0x180185f3d  push    r14
0x180185f3f  lea     rbp, [rsp-0E0h]
0x180185f47  sub     rsp, 1E0h
0x180185f4e  mov     rdi, rcx
0x180185f51  xor     r14d, r14d
0x180185f54  mov     [rbp+100h+SecurityDescriptor], r14
0x180185f5b  xor     r9d, r9d; SecurityDescriptorSize
0x180185f5e  lea     r8, [rbp+100h+SecurityDescriptor]; SecurityDescriptor
0x180185f65  lea     edx, [r14+1]; StringSDRevision
0x180185f69  lea     rcx, aDPAOiciGaSy; "D:P(A;OICI;GA;;;SY)"
0x180185f70  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180185f77  nop     dword ptr [rax+rax+00h]
0x180185f7c  test    eax, eax
0x180185f7e  jnz     short loc_180185FB9
0x180185f80  mov     rcx, [rbp+108h]; this
0x180185f87  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180185f8e  mov     edx, 16Fh; void *
0x180185f93  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180185f98  mov     ebx, eax
0x180185f9a  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x180185fa1  test    rcx, rcx
0x180185fa4  jz      short loc_180185FB2
0x180185fa6  call    cs:__imp_LocalFree
0x180185fad  nop     dword ptr [rax+rax+00h]
0x180185fb2  mov     eax, ebx
0x180185fb4  jmp     loc_1801865C8
0x180185fb9  mov     [rbp+100h+var_160], 18h
0x180185fc1  mov     [rbp+100h+var_150], r14
0x180185fc5  mov     rax, [rbp+100h+SecurityDescriptor]
0x180185fcc  mov     [rbp+100h+var_158], rax
0x180185fd0  mov     [rbp+100h+ReturnedState], r14
0x180185fd7  mov     dword ptr [rbp+100h+Privilege], 11h
0x180185fe1  mov     dword ptr [rbp+100h+Privilege+4], 12h
0x180185feb  lea     r9, [rbp+100h+ReturnedState]; ReturnedState
0x180185ff2  xor     r8d, r8d; Flags
0x180185ff5  lea     edx, [r8+2]; NumPriv
0x180185ff9  lea     rcx, [rbp+100h+Privilege]; Privilege
0x180186000  call    cs:__imp_RtlAcquirePrivilege
0x180186007  nop     dword ptr [rax+rax+00h]
0x18018600c  test    eax, eax
0x18018600e  jns     short loc_18018605D
0x180186010  mov     rcx, [rbp+108h]; this
0x180186017  mov     r9d, eax; char *
0x18018601a  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180186021  mov     edx, 52h ; 'R'; void *
0x180186026  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18018602b  mov     ebx, eax
0x18018602d  test    eax, eax
0x18018602f  jns     short loc_18018605D
0x180186031  mov     rcx, [rbp+108h]; this
0x180186038  mov     r9d, eax; char *
0x18018603b  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186042  mov     edx, 17Bh; void *
0x180186047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018604c  lea     rcx, [rbp+100h+ReturnedState]; this
0x180186053  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x180186058  jmp     loc_180185F9A
0x18018605d  lea     rax, [rsp+200h+var_1C0]
0x180186062  mov     [rsp+200h+lpFileName], rax
0x180186067  lea     rax, [rsp+200h+var_1C0]
0x18018606c  mov     [rsp+200h+var_1C8], rax
0x180186071  mov     [rsp+200h+var_1C0], r14w
0x180186077  mov     r8, [rdi+8]
0x18018607b  sub     r8, [rdi]
0x18018607e  sar     r8, 1
0x180186081  mov     rdx, [rdi]
0x180186084  lea     rcx, [rsp+200h+lpFileName]
0x180186089  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18018608e  test    al, al
0x180186090  jnz     short loc_1801860CF
0x180186092  mov     edx, 17Fh; void *
0x180186097  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x18018609e  mov     r9d, 8007000Eh; char *
0x1801860a4  mov     rcx, [rbp+108h]; this
0x1801860ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801860b0  mov     rcx, [rsp+200h+lpFileName]
0x1801860b5  lea     rax, [rsp+200h+var_1C0]
0x1801860ba  cmp     rcx, rax
0x1801860bd  jz      loc_180186517
0x1801860c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801860ca  jmp     loc_180186512
0x1801860cf  lea     rax, aWcsandboxstate; "WcSandboxState"
0x1801860d6  mov     [rsp+200h+var_190], rax
0x1801860db  mov     [rsp+200h+var_188], 0Eh
0x1801860e4  lea     rdx, [rsp+200h+var_190]
0x1801860e9  lea     rcx, [rsp+200h+lpFileName]; this
0x1801860ee  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1801860f3  test    al, al
0x1801860f5  jnz     short loc_1801860FE
0x1801860f7  mov     edx, 180h
0x1801860fc  jmp     short loc_180186097
0x1801860fe  lea     rdx, [rbp+100h+var_160]; struct Path *
0x180186102  lea     rcx, [rsp+200h+lpFileName]; this
0x180186107  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x18018610c  mov     edi, eax
0x18018610e  test    eax, eax
0x180186110  jns     short loc_18018614C
0x180186112  mov     rcx, [rbp+108h]; this
0x180186119  mov     r9d, eax; char *
0x18018611c  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186123  mov     edx, 182h; void *
0x180186128  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018612d  mov     rcx, [rsp+200h+lpFileName]
0x180186132  lea     rax, [rsp+200h+var_1C0]
0x180186137  cmp     rcx, rax
0x18018613a  jz      loc_1801865A2
0x180186140  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180186147  jmp     loc_18018659D
0x18018614c  mov     edx, 6; dwFileAttributes
0x180186151  mov     rcx, [rsp+200h+lpFileName]; lpFileName
0x180186156  call    cs:__imp_SetFileAttributesW
0x18018615d  nop     dword ptr [rax+rax+00h]
0x180186162  test    eax, eax
0x180186164  jnz     short loc_180186182
0x180186166  mov     rcx, [rbp+108h]; this
0x18018616d  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186174  mov     edx, 186h; void *
0x180186179  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018617e  mov     edi, eax
0x180186180  jmp     short loc_18018612D
0x180186182  lea     rax, [rsp+200h+var_1A0]
0x180186187  mov     [rsp+200h+var_1B0], rax
0x18018618c  lea     rax, [rsp+200h+var_1A0]
0x180186191  mov     [rsp+200h+var_1A8], rax
0x180186196  mov     [rsp+200h+var_1A0], r14w
0x18018619c  mov     rdx, [rsp+200h+lpFileName]
0x1801861a1  mov     r8, [rsp+200h+var_1C8]
0x1801861a6  sub     r8, rdx
0x1801861a9  sar     r8, 1
0x1801861ac  lea     rcx, [rsp+200h+var_1B0]
0x1801861b1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1801861b6  test    al, al
0x1801861b8  jnz     short loc_1801861E4
0x1801861ba  mov     edx, 18Bh; void *
0x1801861bf  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x1801861c6  mov     r9d, 8007000Eh; char *
0x1801861cc  mov     rcx, [rbp+108h]; this
0x1801861d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801861d8  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801861df  jmp     loc_1801864E9
0x1801861e4  lea     rax, aHives; "Hives"
0x1801861eb  mov     [rsp+200h+var_190], rax
0x1801861f0  mov     [rsp+200h+var_188], 5
0x1801861f9  lea     rdx, [rsp+200h+var_190]
0x1801861fe  lea     rcx, [rsp+200h+var_1B0]; this
0x180186203  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180186208  test    al, al
0x18018620a  jnz     short loc_180186213
0x18018620c  mov     edx, 18Ch
0x180186211  jmp     short loc_1801861BF
0x180186213  xor     edx, edx; struct Path *
0x180186215  lea     rcx, [rsp+200h+var_1B0]; this
0x18018621a  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x18018621f  mov     edi, eax
0x180186221  test    eax, eax
0x180186223  jns     short loc_18018624C
0x180186225  mov     edx, 18Eh; void *
0x18018622a  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186231  mov     r9d, edi; char *
0x180186234  mov     rcx, [rbp+108h]; this
0x18018623b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186240  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180186247  jmp     loc_180186574
0x18018624c  xor     edx, edx; Val
0x18018624e  mov     r8d, 114h; Size
0x180186254  lea     rcx, [rbp+100h+var_140]; void *
0x180186258  call    memset_0
0x18018625d  lea     rcx, [rbp+100h+var_140]; this
0x180186261  call    ?GetOsVersionInfo@Csl@@YAJAEAU_OSVERSIONINFOW@@@Z; Csl::GetOsVersionInfo(_OSVERSIONINFOW &)
0x180186266  mov     edi, eax
0x180186268  test    eax, eax
0x18018626a  jns     short loc_180186273
0x18018626c  mov     edx, 191h
0x180186271  jmp     short loc_18018622A
0x180186273  lea     rsi, off_1801C87B0; "SYSTEM"
0x18018627a  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180186281  mov     [rbp+100h+Privilege], r14
0x180186288  mov     edx, 1
0x18018628d  lea     rcx, [rbp+100h+Privilege]
0x180186294  call    ORCreateHiveEx
0x180186299  test    eax, eax
0x18018629b  jnz     loc_180186545
0x1801862a1  lea     rax, [rbp+100h+var_170]
0x1801862a5  mov     [rbp+100h+var_180], rax
0x1801862a9  lea     rax, [rbp+100h+var_170]
0x1801862ad  mov     [rbp+100h+var_178], rax
0x1801862b1  mov     [rbp+100h+var_170], r14w
0x1801862b6  mov     rdx, [rsp+200h+var_1B0]
0x1801862bb  mov     r8, [rsp+200h+var_1A8]
0x1801862c0  sub     r8, rdx
0x1801862c3  sar     r8, 1
0x1801862c6  lea     rcx, [rbp+100h+var_180]
0x1801862ca  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1801862cf  test    al, al
0x1801862d1  jz      loc_1801864A4
0x1801862d7  mov     rcx, [rsi+10h]
0x1801862db  mov     [rsp+200h+var_190], rcx
0x1801862e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801862e4  inc     rax
0x1801862e7  cmp     [rcx+rax*2], r14w
0x1801862ec  jnz     short loc_1801862E4
0x1801862ee  mov     [rsp+200h+var_188], rax
0x1801862f3  lea     rdx, [rsp+200h+var_190]
0x1801862f8  lea     rcx, [rbp+100h+var_180]; this
0x1801862fc  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180186301  test    al, al
0x180186303  jz      loc_18018645D
0x180186309  mov     [rsp+200h+var_1E0], 1; unsigned int
0x180186311  mov     r9d, [rbp+100h+var_138]
0x180186315  mov     r8d, [rbp+100h+var_13C]
0x180186319  mov     rdx, [rbp+100h+var_180]
0x18018631d  mov     rdi, [rbp+100h+Privilege]
0x180186324  mov     rcx, rdi
0x180186327  call    ORSaveHiveEx
0x18018632c  test    eax, eax
0x18018632e  jnz     loc_1801863C4
0x180186334  mov     rcx, [rbp+100h+var_180]; void *
0x180186338  lea     rax, [rbp+100h+var_170]
0x18018633c  cmp     rcx, rax
0x18018633f  jz      short loc_180186349
0x180186341  mov     rdx, rbx; struct std::nothrow_t *
0x180186344  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186349  test    rdi, rdi
0x18018634c  jz      short loc_180186357
0x18018634e  mov     rcx, rdi
0x180186351  call    ORCloseHive
0x180186356  nop
0x180186357  add     rsi, 18h
0x18018635b  lea     rax, ?Version_ClassData@Global@Schema@HNS@@3UClassData@Marshal@@B; Marshal::ClassData const HNS::Schema::Global::Version_ClassData
0x180186362  cmp     rsi, rax
0x180186365  jnz     loc_180186281
0x18018636b  mov     rcx, [rsp+200h+var_1B0]; void *
0x180186370  lea     rax, [rsp+200h+var_1A0]
0x180186375  cmp     rcx, rax
0x180186378  jz      short loc_180186382
0x18018637a  mov     rdx, rbx; struct std::nothrow_t *
0x18018637d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186382  mov     rcx, [rsp+200h+lpFileName]; void *
0x180186387  lea     rax, [rsp+200h+var_1C0]
0x18018638c  cmp     rcx, rax
0x18018638f  jz      short loc_180186399
0x180186391  mov     rdx, rbx; struct std::nothrow_t *
0x180186394  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186399  lea     rcx, [rbp+100h+ReturnedState]; this
0x1801863a0  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1801863a5  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x1801863ac  test    rcx, rcx
0x1801863af  jz      short loc_1801863BD
0x1801863b1  call    cs:__imp_LocalFree
0x1801863b8  nop     dword ptr [rax+rax+00h]
0x1801863bd  xor     eax, eax
0x1801863bf  jmp     loc_1801865C8
0x1801863c4  mov     rcx, [rbp+108h]; this
0x1801863cb  mov     r9d, eax; char *
0x1801863ce  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x1801863d5  mov     edx, 1A5h; void *
0x1801863da  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801863df  mov     esi, eax
0x1801863e1  mov     rcx, [rbp+100h+var_180]; void *
0x1801863e5  lea     rax, [rbp+100h+var_170]
0x1801863e9  cmp     rcx, rax
0x1801863ec  jz      short loc_1801863F6
0x1801863ee  mov     rdx, rbx; struct std::nothrow_t *
0x1801863f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801863f6  test    rdi, rdi
0x1801863f9  jz      short loc_180186404
0x1801863fb  mov     rcx, rdi
0x1801863fe  call    ORCloseHive
0x180186403  nop
0x180186404  mov     rcx, [rsp+200h+var_1B0]; void *
0x180186409  lea     rax, [rsp+200h+var_1A0]
0x18018640e  cmp     rcx, rax
0x180186411  jz      short loc_18018641B
0x180186413  mov     rdx, rbx; struct std::nothrow_t *
0x180186416  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018641b  mov     rcx, [rsp+200h+lpFileName]; void *
0x180186420  lea     rax, [rsp+200h+var_1C0]
0x180186425  cmp     rcx, rax
0x180186428  jz      short loc_180186432
0x18018642a  mov     rdx, rbx; struct std::nothrow_t *
0x18018642d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186432  lea     rcx, [rbp+100h+ReturnedState]; this
0x180186439  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x18018643e  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x180186445  test    rcx, rcx
0x180186448  jz      short loc_180186456
0x18018644a  call    cs:__imp_LocalFree
0x180186451  nop     dword ptr [rax+rax+00h]
0x180186456  mov     eax, esi
0x180186458  jmp     loc_1801865C8
0x18018645d  mov     rcx, [rbp+108h]; this
0x180186464  mov     r9d, 8007000Eh; char *
0x18018646a  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186471  mov     edx, 19Eh; void *
0x180186476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018647b  mov     rcx, [rbp+100h+var_180]; void *
  ... truncated ...
```
