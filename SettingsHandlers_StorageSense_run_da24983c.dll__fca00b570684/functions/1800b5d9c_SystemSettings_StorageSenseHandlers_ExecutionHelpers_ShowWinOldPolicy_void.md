# SystemSettings::StorageSenseHandlers::ExecutionHelpers::ShowWinOldPolicy(void)

- ea: `0x1800b5d9c`
- end: `0x1800b5fa5`
- name: `?ShowWinOldPolicy@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YA_NXZ`
- size: `521`
- prototype: `bool __fastcall(SystemSettings::StorageSenseHandlers::ExecutionHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180081de0`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18003b430`
- `0x18004c8bc`
- `0x18009d56c`
- `0x1800b4520`
- `0x1800b4638`
- `0x1800b4c80`
- `0x1800b5d9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b5ea2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b5ea2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b5f62`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b5f62`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b5e66`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b5f38`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b5e66`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b5f38`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b5e3c`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b5e3c`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x1800b5dfd`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x1800b5dfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall SystemSettings::StorageSenseHandlers::ExecutionHelpers::ShowWinOldPolicy(
        SystemSettings::StorageSenseHandlers::ExecutionHelpers *this)
{
  char v1; // di
  const unsigned __int16 *v2; // rdx
  char *FirstFile; // rbx
  bool i; // zf
  const unsigned __int16 *v6; // rdx
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR v8; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR v9; // [rsp+40h] [rbp-C0h] BYREF
  char *v10; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPathIn[558]; // [rsp+2A4h] [rbp+1A4h] BYREF

  if ( !SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsUserAdmin(this) )
    return 0;
  memset_0(pszPathIn, 0, 0x454u);
  v12 = 1112;
  if ( (int)GetStorageDeviceInfo(0, 0, &v12) < 0 )
    return 0;
  ppszPathOut = 0;
  v8 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v1 = 1;
  if ( PathAllocCanonicalize(pszPathIn, 1u, &ppszPathOut) < 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v8,
          0),
        PathAllocCombine(ppszPathOut, L"*.*", 1u, &v8) < 0) )
  {
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    return 0;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = (char *)FindFirstFileExW(v8, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
  v10 = FirstFile;
  for ( i = FirstFile + 1 == 0; ; i = !FindNextFileW(FirstFile, &FindFileData) )
  {
    if ( i )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v10);
      goto LABEL_8;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0
      || !SystemSettings::StorageSenseHandlers::StringHelpers::IsWinOldPatternDirectory(
            (SystemSettings::StorageSenseHandlers::StringHelpers *)FindFileData.cFileName,
            v2) )
    {
      continue;
    }
    v9 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v9,
      0);
    if ( PathAllocCombine(ppszPathOut, FindFileData.cFileName, 1u, &v9) < 0 )
      break;
    if ( SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(v9, v6) )
      goto LABEL_17;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
  }
  v1 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return v1;
}

```

## disassembly

```asm
0x1800b5d9c  mov     [rsp-8+arg_0], rbx
0x1800b5da1  mov     [rsp-8+arg_8], rdi
0x1800b5da6  push    rbp
0x1800b5da7  lea     rbp, [rsp-610h]
0x1800b5daf  sub     rsp, 710h
0x1800b5db6  mov     rax, cs:__security_cookie
0x1800b5dbd  xor     rax, rsp
0x1800b5dc0  mov     [rbp+610h+var_10], rax
0x1800b5dc7  call    ?IsUserAdmin@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YA_NXZ; SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsUserAdmin(void)
0x1800b5dcc  test    al, al
0x1800b5dce  jz      loc_1800B5ED6
0x1800b5dd4  xor     edx, edx; Val
0x1800b5dd6  mov     r8d, 454h; Size
0x1800b5ddc  lea     rcx, [rbp+610h+pszPathIn]; void *
0x1800b5de3  call    memset_0
0x1800b5de8  mov     [rbp+610h+var_470], 458h
0x1800b5df2  lea     r8, [rbp+610h+var_470]
0x1800b5df9  xor     edx, edx
0x1800b5dfb  xor     ecx, ecx
0x1800b5dfd  call    cs:__imp_GetStorageDeviceInfo
0x1800b5e03  test    eax, eax
0x1800b5e05  js      loc_1800B5ED6
0x1800b5e0b  mov     [rsp+710h+ppszPathOut], 0
0x1800b5e14  mov     [rsp+710h+var_6D8], 0
0x1800b5e1d  xor     edx, edx
0x1800b5e1f  lea     rcx, [rsp+710h+ppszPathOut]
0x1800b5e24  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b5e29  lea     r8, [rsp+710h+ppszPathOut]; ppszPathOut
0x1800b5e2e  mov     edi, 1
0x1800b5e33  mov     edx, edi; dwFlags
0x1800b5e35  lea     rcx, [rbp+610h+pszPathIn]; pszPathIn
0x1800b5e3c  call    cs:__imp_PathAllocCanonicalize
0x1800b5e42  test    eax, eax
0x1800b5e44  js      short loc_1800B5EC1
0x1800b5e46  xor     edx, edx
0x1800b5e48  lea     rcx, [rsp+710h+var_6D8]
0x1800b5e4d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b5e52  lea     r9, [rsp+710h+var_6D8]; ppszPathOut
0x1800b5e57  mov     r8d, edi; dwFlags
0x1800b5e5a  lea     rdx, asc_18011A000; "*.*"
0x1800b5e61  mov     rcx, [rsp+710h+ppszPathOut]; pszPathIn
0x1800b5e66  call    cs:__imp_PathAllocCombine
0x1800b5e6c  test    eax, eax
0x1800b5e6e  js      short loc_1800B5EC1
0x1800b5e70  xor     edx, edx; Val
0x1800b5e72  mov     r8d, 250h; Size
0x1800b5e78  lea     rcx, [rsp+710h+FindFileData]; void *
0x1800b5e7d  call    memset_0
0x1800b5e82  mov     [rsp+710h+dwAdditionalFlags], 2; dwAdditionalFlags
0x1800b5e8a  mov     [rsp+710h+lpSearchFilter], 0; lpSearchFilter
0x1800b5e93  xor     r9d, r9d; fSearchOp
0x1800b5e96  lea     r8, [rsp+710h+FindFileData]; lpFindFileData
0x1800b5e9b  mov     edx, edi; fInfoLevelId
0x1800b5e9d  mov     rcx, [rsp+710h+var_6D8]; lpFileName
0x1800b5ea2  call    cs:__imp_FindFirstFileExW
0x1800b5ea8  mov     rbx, rax
0x1800b5eab  mov     [rsp+710h+var_6C8], rax
0x1800b5eb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b5eb4  jnz     short loc_1800B5EFC
0x1800b5eb6  lea     rcx, [rsp+710h+var_6C8]
0x1800b5ebb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b5ec0  nop
0x1800b5ec1  lea     rcx, [rsp+710h+var_6D8]
0x1800b5ec6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5ecb  nop
0x1800b5ecc  lea     rcx, [rsp+710h+ppszPathOut]
0x1800b5ed1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5ed6  xor     al, al
0x1800b5ed8  mov     rcx, [rbp+610h+var_10]
0x1800b5edf  xor     rcx, rsp; StackCookie
0x1800b5ee2  call    __security_check_cookie
0x1800b5ee7  lea     r11, [rsp+710h+var_s0]
0x1800b5eef  mov     rbx, [r11+10h]
0x1800b5ef3  mov     rdi, [r11+18h]
0x1800b5ef7  mov     rsp, r11
0x1800b5efa  pop     rbp
0x1800b5efb  retn
0x1800b5efc  test    [rsp+710h+FindFileData], 10h
0x1800b5f01  jz      short loc_1800B5F5A
0x1800b5f03  lea     rcx, [rsp+710h+pszMore]; this
0x1800b5f08  call    ?IsWinOldPatternDirectory@StringHelpers@StorageSenseHandlers@SystemSettings@@YA_NPEBG@Z; SystemSettings::StorageSenseHandlers::StringHelpers::IsWinOldPatternDirectory(ushort const *)
0x1800b5f0d  test    al, al
0x1800b5f0f  jz      short loc_1800B5F5A
0x1800b5f11  mov     [rsp+710h+var_6D0], 0
0x1800b5f1a  xor     edx, edx
0x1800b5f1c  lea     rcx, [rsp+710h+var_6D0]
0x1800b5f21  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b5f26  lea     r9, [rsp+710h+var_6D0]; ppszPathOut
0x1800b5f2b  mov     r8d, edi; dwFlags
0x1800b5f2e  lea     rdx, [rsp+710h+pszMore]; pszMore
0x1800b5f33  mov     rcx, [rsp+710h+ppszPathOut]; pszPathIn
0x1800b5f38  call    cs:__imp_PathAllocCombine
0x1800b5f3e  test    eax, eax
0x1800b5f40  js      short loc_1800B5F6F
0x1800b5f42  mov     rcx, [rsp+710h+var_6D0]; this
0x1800b5f47  call    ?RecursiveCheckNonEmptyDirectory@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NPEBG@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(ushort const *)
0x1800b5f4c  test    al, al
0x1800b5f4e  jnz     short loc_1800B5F72
0x1800b5f50  lea     rcx, [rsp+710h+var_6D0]
0x1800b5f55  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5f5a  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x1800b5f5f  mov     rcx, rbx; hFindFile
0x1800b5f62  call    cs:__imp_FindNextFileW
0x1800b5f68  test    eax, eax
0x1800b5f6a  jmp     loc_1800B5EB4
0x1800b5f6f  xor     dil, dil
0x1800b5f72  lea     rcx, [rsp+710h+var_6D0]
0x1800b5f77  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5f7c  nop
0x1800b5f7d  lea     rcx, [rsp+710h+var_6C8]
0x1800b5f82  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b5f87  nop
0x1800b5f88  lea     rcx, [rsp+710h+var_6D8]
0x1800b5f8d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5f92  nop
0x1800b5f93  lea     rcx, [rsp+710h+ppszPathOut]
0x1800b5f98  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5f9d  mov     al, dil
0x1800b5fa0  jmp     loc_1800B5ED8
```
