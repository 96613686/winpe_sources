# CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)

- ea: `0x18003e904`
- end: `0x18003ec78`
- name: `?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z`
- size: `884`
- prototype: `int __fastcall(CloudStoreUtilities *this, const unsigned __int16 *, const struct _SECURITY_ATTRIBUTES *, HKEY *)`
- caller_count: `19`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180012ad4`
- `0x1800137f0`
- `0x1800139b4`
- `0x1800141d4`
- `0x180014384`
- `0x18003e0d0`
- `0x18003e2b0`
- `0x18003e6dc`
- `0x180053574`
- `0x18005f34c`
- `0x1800d4534`
- `0x1800d5dd8`
- `0x1800e3ef0`
- `0x1800f11b0`
- `0x1800f12fc`
- `0x1800feca0`
- `0x18011a214`
- `0x1801ad540`
- `0x1801c8b50`

## callees

- `0x180019080`
- `0x1800320d4`
- `0x18003b488`
- `0x18003bb30`
- `0x18003e670`
- `0x18003e904`
- `0x18003f6c4`
- `0x180053a60`
- `0x18008e564`
- `0x1800921d4`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801201a0`
- `0x1801c104c`
- `0x1801c11b0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003eadf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003eb5b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003eadf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003eb5b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003eb26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003eb26`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18003ebbf`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18003ebbf`

## string_xrefs

- `0x18003e9a9`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003e9e9`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003ebf4`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003ec62`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
int __fastcall CloudStoreUtilities::GetRegistryRootKey(
        CloudStoreUtilities *this,
        const unsigned __int16 *a2,
        const struct _SECURITY_ATTRIBUTES *a3,
        HKEY *a4)
{
  __int64 v7; // r8
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  CloudStoreUtilities::StorageTestHook *v10; // rcx
  CloudStoreUtilities::StorageTestHook *v11; // rdx
  HRESULT FileSystemRootFolder; // ebx
  __int64 v13; // rdx
  int result; // eax
  CloudStoreUtilities *v15; // rcx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r9
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  HANDLE FileW; // rax
  unsigned int v21; // eax
  const unsigned __int16 *v22; // r8
  unsigned int v23; // r9d
  __int64 v24; // rdx
  unsigned int v25; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  HKEY *hTemplateFile; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  struct HKEY__ v33; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPathIn[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR pszPathOut[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR File[264]; // [rsp+680h] [rbp+580h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8D8h] [rbp+7D8h]

  *(_QWORD *)&a3->nLength = 0;
  v7 = 260;
  v8 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore";
  v9 = 2147483646;
  v10 = (CloudStoreUtilities::StorageTestHook *)&v33;
  do
  {
    if ( !v9 )
      break;
    if ( !*v8 )
      break;
    *(_WORD *)v10 = *v8++;
    v10 = (CloudStoreUtilities::StorageTestHook *)((char *)v10 + 2);
    --v9;
    --v7;
  }
  while ( v7 );
  v11 = (CloudStoreUtilities::StorageTestHook *)((char *)v10 - 2);
  FileSystemRootFolder = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v11 = v10;
  *(_WORD *)v11 = 0;
  if ( !v7 )
  {
    v13 = 421;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)FileSystemRootFolder,
      dwCreationDisposition);
    return FileSystemRootFolder;
  }
  if ( CloudStoreUtilities::StorageTestHook::IsEnabled(v10) )
  {
    v18 = StringCchCatW((unsigned __int16 *)&v33, 0x104u, L"\\TestRoot");
    FileSystemRootFolder = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDisposition);
      v13 = 423;
      goto LABEL_9;
    }
  }
  if ( a2 )
  {
    FileSystemRootFolder = StringCchCatW((unsigned __int16 *)&v33, 0x104u, L"\\");
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 427;
      goto LABEL_9;
    }
    FileSystemRootFolder = StringCchCatW((unsigned __int16 *)&v33, 0x104u, a2);
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 428;
      goto LABEL_9;
    }
  }
  if ( (!this || !*(_WORD *)this) && !CloudStoreUtilities::IsRoamingProfile(v15) )
  {
    v25 = CloudStoreUtilities::RegCreateKeyExWithProfileCheck(
            (CloudStoreUtilities *)0xFFFFFFFF80000001LL,
            &v33,
            v16,
            (unsigned int)v17,
            dwCreationDisposition,
            a3,
            hTemplateFile,
            v30);
    if ( v25 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1D2,
               (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
               (const char *)v25,
               dwCreationDispositionb);
    return 0;
  }
  if ( !this || !*(_WORD *)this )
  {
    FileSystemRootFolder = CloudStoreUtilities::GetFileSystemRootFolder(
                             L"Microsoft\\Windows\\CloudStore",
                             pszPathIn,
                             v16,
                             (unsigned int)v17);
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 455;
      goto LABEL_9;
    }
LABEL_32:
    FileSystemRootFolder = PathCchCombine(File, 0x104u, pszPathIn, L"cloudstore.dat");
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 459;
      goto LABEL_9;
    }
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v21 = RegLoadAppKeyW(File, &phkResult, 0xF003Fu, 0, 0);
    if ( v21 )
    {
      v24 = 461;
LABEL_40:
      FileSystemRootFolder = wil::details::in1diag3::Return_Win32(
                               retaddr,
                               (void *)v24,
                               (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
                               (const char *)v21,
                               dwCreationDispositiona);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return FileSystemRootFolder;
    }
    v21 = CloudStoreUtilities::RegCreateKeyExWithProfileCheck(
            (CloudStoreUtilities *)phkResult,
            &v33,
            v22,
            v23,
            dwCreationDispositiona,
            a3,
            hTemplateFile,
            v30);
    if ( v21 )
    {
      v24 = 462;
      goto LABEL_40;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return 0;
  }
  FileSystemRootFolder = CloudStoreUtilities::GetPackageRootFolder(
                           L"Microsoft\\Windows\\CloudStore",
                           (const unsigned __int16 *)this,
                           pszPathIn,
                           v17,
                           dwCreationDisposition);
  if ( FileSystemRootFolder >= 0 )
  {
    FileSystemRootFolder = wil::CreateDirectoryDeepNoThrow((wil *)pszPathIn, v19);
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 438;
      goto LABEL_9;
    }
    FileSystemRootFolder = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"cloudstore.dat");
    if ( FileSystemRootFolder < 0 )
    {
      v13 = 441;
      goto LABEL_9;
    }
    v32 = -1;
    FileW = CreateFileW(pszPathOut, 0xC0000000, 2u, 0, 1u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v32,
      FileW);
    std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&v32);
    goto LABEL_32;
  }
  result = -2147024894;
  if ( FileSystemRootFolder != -2147024894 )
  {
    v13 = 437;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x18003e904  push    rbp
0x18003e906  push    rbx
0x18003e907  push    rsi
0x18003e908  push    rdi
0x18003e909  push    r12
0x18003e90b  push    r14
0x18003e90d  push    r15
0x18003e90f  lea     rbp, [rsp-7A0h]
0x18003e917  sub     rsp, 8A0h
0x18003e91e  mov     rax, cs:__security_cookie
0x18003e925  xor     rax, rsp
0x18003e928  mov     [rbp+7D0h+var_40], rax
0x18003e92f  xor     r15d, r15d
0x18003e932  mov     r12d, 104h
0x18003e938  mov     [r8], r15
0x18003e93b  mov     r14, r8
0x18003e93e  mov     rsi, rdx
0x18003e941  mov     rdi, rcx
0x18003e944  mov     r8d, r12d
0x18003e947  lea     rdx, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003e94e  mov     eax, 7FFFFFFEh
0x18003e953  lea     rcx, [rsp+8D0h+var_880]
0x18003e958  test    rax, rax
0x18003e95b  jz      short loc_18003E97C
0x18003e95d  movzx   r9d, word ptr [rdx]
0x18003e961  test    r9w, r9w
0x18003e965  jz      short loc_18003E97C
0x18003e967  mov     [rcx], r9w
0x18003e96b  add     rdx, 2
0x18003e96f  add     rcx, 2; this
0x18003e973  dec     rax
0x18003e976  sub     r8, 1
0x18003e97a  jnz     short loc_18003E958
0x18003e97c  mov     rax, r8
0x18003e97f  lea     rdx, [rcx-2]
0x18003e983  neg     rax
0x18003e986  sbb     ebx, ebx
0x18003e988  not     ebx
0x18003e98a  and     ebx, 8007007Ah
0x18003e990  test    r8, r8
0x18003e993  cmovnz  rdx, rcx
0x18003e997  mov     [rdx], r15w
0x18003e99b  jnz     short loc_18003E9BF
0x18003e99d  mov     edx, 1A5h; void *
0x18003e9a2  mov     rcx, [rbp+7D8h]; this
0x18003e9a9  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003e9b0  mov     r9d, ebx; char *
0x18003e9b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9b8  mov     eax, ebx
0x18003e9ba  jmp     loc_18003EC20
0x18003e9bf  call    ?IsEnabled@StorageTestHook@CloudStoreUtilities@@YA_NXZ; CloudStoreUtilities::StorageTestHook::IsEnabled(void)
0x18003e9c4  test    al, al
0x18003e9c6  jz      short loc_18003EA04
0x18003e9c8  lea     r8, aTestroot; "\\TestRoot"
0x18003e9cf  mov     rdx, r12; unsigned __int64
0x18003e9d2  lea     rcx, [rsp+8D0h+var_880]; unsigned __int16 *
0x18003e9d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e9dc  mov     ebx, eax
0x18003e9de  test    eax, eax
0x18003e9e0  jns     short loc_18003EA04
0x18003e9e2  mov     rcx, [rbp+7D8h]; this
0x18003e9e9  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003e9f0  mov     r9d, eax; char *
0x18003e9f3  mov     edx, 161h; void *
0x18003e9f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9fd  mov     edx, 1A7h
0x18003ea02  jmp     short loc_18003E9A2
0x18003ea04  test    rsi, rsi
0x18003ea07  jz      short loc_18003EA4D
0x18003ea09  lea     r8, asc_1802285AC; "\\"
0x18003ea10  mov     rdx, r12; unsigned __int64
0x18003ea13  lea     rcx, [rsp+8D0h+var_880]; unsigned __int16 *
0x18003ea18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ea1d  mov     ebx, eax
0x18003ea1f  test    eax, eax
0x18003ea21  jns     short loc_18003EA2D
0x18003ea23  mov     edx, 1ABh
0x18003ea28  jmp     loc_18003E9A2
0x18003ea2d  mov     r8, rsi; unsigned __int16 *
0x18003ea30  lea     rcx, [rsp+8D0h+var_880]; unsigned __int16 *
0x18003ea35  mov     rdx, r12; unsigned __int64
0x18003ea38  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ea3d  mov     ebx, eax
0x18003ea3f  test    eax, eax
0x18003ea41  jns     short loc_18003EA4D
0x18003ea43  mov     edx, 1ACh
0x18003ea48  jmp     loc_18003E9A2
0x18003ea4d  test    rdi, rdi
0x18003ea50  jz      short loc_18003EA58
0x18003ea52  cmp     [rdi], r15w
0x18003ea56  jnz     short loc_18003EA65
0x18003ea58  call    ?IsRoamingProfile@CloudStoreUtilities@@YA_NXZ; CloudStoreUtilities::IsRoamingProfile(void)
0x18003ea5d  test    al, al
0x18003ea5f  jz      loc_18003EC41
0x18003ea65  test    rdi, rdi
0x18003ea68  jz      loc_18003EB71
0x18003ea6e  cmp     [rdi], r15w
0x18003ea72  jz      loc_18003EB71
0x18003ea78  lea     r8, [rbp+7D0h+pszPathIn]; unsigned __int16 *
0x18003ea7f  mov     rdx, rdi; unsigned __int16 *
0x18003ea82  lea     rcx, aMicrosoftWindo_0; "Microsoft\\Windows\\CloudStore"
0x18003ea89  call    ?GetPackageRootFolder@CloudStoreUtilities@@YAJPEBG0PEAGK@Z; CloudStoreUtilities::GetPackageRootFolder(ushort const *,ushort const *,ushort *,ulong)
0x18003ea8e  mov     ebx, eax
0x18003ea90  test    eax, eax
0x18003ea92  jns     short loc_18003EAAB
0x18003ea94  mov     eax, 80070002h
0x18003ea99  cmp     ebx, eax
0x18003ea9b  jz      loc_18003EC20
0x18003eaa1  mov     edx, 1B5h
0x18003eaa6  jmp     loc_18003E9A2
0x18003eaab  lea     rcx, [rbp+7D0h+pszPathIn]; this
0x18003eab2  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003eab7  mov     ebx, eax
0x18003eab9  test    eax, eax
0x18003eabb  jns     short loc_18003EAC7
0x18003eabd  mov     edx, 1B6h
0x18003eac2  jmp     loc_18003E9A2
0x18003eac7  lea     r9, aCloudstoreDat; "cloudstore.dat"
0x18003eace  mov     rdx, r12; cchPathOut
0x18003ead1  lea     r8, [rbp+7D0h+pszPathIn]; pszPathIn
0x18003ead8  lea     rcx, [rbp+7D0h+pszPathOut]; pszPathOut
0x18003eadf  call    cs:__imp_PathCchCombine
0x18003eae5  mov     ebx, eax
0x18003eae7  test    eax, eax
0x18003eae9  jns     short loc_18003EAF5
0x18003eaeb  mov     edx, 1B9h
0x18003eaf0  jmp     loc_18003E9A2
0x18003eaf5  xor     r9d, r9d; lpSecurityAttributes
0x18003eaf8  mov     [rsp+8D0h+hTemplateFile], r15; HKEY *
0x18003eafd  mov     [rsp+8D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003eb05  lea     rcx, [rbp+7D0h+pszPathOut]; lpFileName
0x18003eb0c  mov     edx, 0C0000000h; dwDesiredAccess
0x18003eb11  mov     [rsp+8D0h+var_888], 0FFFFFFFFFFFFFFFFh
0x18003eb1a  mov     [rsp+8D0h+dwCreationDisposition], 1; dwCreationDisposition
0x18003eb22  lea     r8d, [r9+2]; dwShareMode
0x18003eb26  call    cs:__imp_CreateFileW
0x18003eb2c  mov     rdx, rax
0x18003eb2f  lea     rcx, [rsp+8D0h+var_888]
0x18003eb34  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003eb39  lea     rcx, [rsp+8D0h+var_888]
0x18003eb3e  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x18003eb43  lea     r9, aCloudstoreDat; "cloudstore.dat"
0x18003eb4a  mov     rdx, r12; cchPathOut
0x18003eb4d  lea     r8, [rbp+7D0h+pszPathIn]; pszPathIn
0x18003eb54  lea     rcx, [rbp+7D0h+File]; pszPathOut
0x18003eb5b  call    cs:__imp_PathCchCombine
0x18003eb61  mov     ebx, eax
0x18003eb63  test    eax, eax
0x18003eb65  jns     short loc_18003EB94
0x18003eb67  mov     edx, 1CBh
0x18003eb6c  jmp     loc_18003E9A2
0x18003eb71  lea     rdx, [rbp+7D0h+pszPathIn]; pszPathOut
0x18003eb78  lea     rcx, aMicrosoftWindo_0; "Microsoft\\Windows\\CloudStore"
0x18003eb7f  call    ?GetFileSystemRootFolder@CloudStoreUtilities@@YAJPEBGPEAGK@Z; CloudStoreUtilities::GetFileSystemRootFolder(ushort const *,ushort *,ulong)
0x18003eb84  mov     ebx, eax
0x18003eb86  test    eax, eax
0x18003eb88  jns     short loc_18003EB43
0x18003eb8a  mov     edx, 1C7h
0x18003eb8f  jmp     loc_18003E9A2
0x18003eb94  xor     edx, edx
0x18003eb96  mov     [rsp+8D0h+phkResult], r15
0x18003eb9b  lea     rcx, [rsp+8D0h+phkResult]
0x18003eba0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003eba5  xor     r9d, r9d; dwOptions
0x18003eba8  mov     [rsp+8D0h+dwCreationDisposition], r15d; unsigned int
0x18003ebad  mov     r8d, 0F003Fh; samDesired
0x18003ebb3  lea     rdx, [rsp+8D0h+phkResult]; phkResult
0x18003ebb8  lea     rcx, [rbp+7D0h+File]; lpFile
0x18003ebbf  call    cs:__imp_RegLoadAppKeyW
0x18003ebc5  test    eax, eax
0x18003ebc7  jz      short loc_18003EBD0
0x18003ebc9  mov     edx, 1CDh
0x18003ebce  jmp     short loc_18003EBED
0x18003ebd0  mov     rcx, [rsp+8D0h+phkResult]; this
0x18003ebd5  lea     rdx, [rsp+8D0h+var_880]; HKEY
0x18003ebda  mov     qword ptr [rsp+8D0h+dwFlagsAndAttributes], r14; struct _SECURITY_ATTRIBUTES *
0x18003ebdf  call    ?RegCreateKeyExWithProfileCheck@CloudStoreUtilities@@YAJPEAUHKEY__@@PEBGKKPEBU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; CloudStoreUtilities::RegCreateKeyExWithProfileCheck(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES const *,HKEY__ * *,ulong *)
0x18003ebe4  test    eax, eax
0x18003ebe6  jz      short loc_18003EC14
0x18003ebe8  mov     edx, 1CEh; void *
0x18003ebed  mov     rcx, [rbp+7D8h]; this
0x18003ebf4  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003ebfb  mov     r9d, eax; char *
0x18003ebfe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ec03  lea     rcx, [rsp+8D0h+phkResult]
0x18003ec08  mov     ebx, eax
0x18003ec0a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ec0f  jmp     loc_18003E9B8
0x18003ec14  lea     rcx, [rsp+8D0h+phkResult]
0x18003ec19  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ec1e  xor     eax, eax
0x18003ec20  mov     rcx, [rbp+7D0h+var_40]
0x18003ec27  xor     rcx, rsp; StackCookie
0x18003ec2a  call    __security_check_cookie
0x18003ec2f  add     rsp, 8A0h
0x18003ec36  pop     r15
0x18003ec38  pop     r14
0x18003ec3a  pop     r12
0x18003ec3c  pop     rdi
0x18003ec3d  pop     rsi
0x18003ec3e  pop     rbx
0x18003ec3f  pop     rbp
0x18003ec40  retn
0x18003ec41  lea     rdx, [rsp+8D0h+var_880]; HKEY
0x18003ec46  mov     qword ptr [rsp+8D0h+dwFlagsAndAttributes], r14; struct _SECURITY_ATTRIBUTES *
0x18003ec4b  mov     rcx, 0FFFFFFFF80000001h; this
0x18003ec52  call    ?RegCreateKeyExWithProfileCheck@CloudStoreUtilities@@YAJPEAUHKEY__@@PEBGKKPEBU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; CloudStoreUtilities::RegCreateKeyExWithProfileCheck(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES const *,HKEY__ * *,ulong *)
0x18003ec57  test    eax, eax
0x18003ec59  jz      short loc_18003EC1E
0x18003ec5b  mov     rcx, [rbp+7D8h]; this
0x18003ec62  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003ec69  mov     r9d, eax; char *
0x18003ec6c  mov     edx, 1D2h; void *
0x18003ec71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ec76  jmp     short loc_18003EC20
```
