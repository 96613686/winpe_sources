# SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(ushort const *)

- ea: `0x1800b4c80`
- end: `0x1800b4e8b`
- name: `?RecursiveCheckNonEmptyDirectory@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NPEBG@Z`
- size: `523`
- prototype: `bool __fastcall(SystemSettings::StorageSenseHandlers::StorageSenseUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b4c80`
- `0x1800b5d9c`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18003b430`
- `0x18004c8bc`
- `0x18009d56c`
- `0x1800b4c80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b4d44`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b4d44`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b4e0f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b4e0f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4d16`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4dd5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4d16`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4dd5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b4ce8`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b4ce8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(
        const WCHAR *this,
        const unsigned __int16 *a2)
{
  char v3; // di
  HANDLE FirstFile; // rbx
  int v5; // edx
  int v6; // edx
  const unsigned __int16 *v7; // rdx
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR v10; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR pszPathIn; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v12; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ppszPathOut = 0;
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v3 = 1;
  if ( PathAllocCanonicalize(this, 1u, &ppszPathOut) < 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v10,
          0),
        PathAllocCombine(ppszPathOut, L"*.*", 1u, &v10) < 0) )
  {
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    return 0;
  }
  FirstFile = FindFirstFileExW(v10, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
  v12 = FirstFile;
  if ( FirstFile == (HANDLE)-1LL )
  {
    v3 = 0;
    goto LABEL_22;
  }
  while ( 1 )
  {
    v5 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v5 = FindFileData.cFileName[1];
    if ( !v5 )
      goto LABEL_18;
    v6 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v6 = FindFileData.cFileName[1] - 46;
      if ( FindFileData.cFileName[1] == 46 )
        v6 = FindFileData.cFileName[2];
    }
    if ( !v6 )
      goto LABEL_18;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( FindFileData.nFileSizeHigh || FindFileData.nFileSizeLow )
        goto LABEL_22;
      goto LABEL_18;
    }
    pszPathIn = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPathIn,
      0);
    if ( PathAllocCombine(ppszPathOut, FindFileData.cFileName, 1u, (PWSTR *)&pszPathIn) >= 0
      && SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(
           (SystemSettings::StorageSenseHandlers::StorageSenseUtils *)pszPathIn,
           v7) )
    {
      break;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
LABEL_18:
    if ( !FindNextFileW(FirstFile, &FindFileData) )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v12);
      goto LABEL_20;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
LABEL_22:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v12);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return v3;
}

```

## disassembly

```asm
0x1800b4c80  push    rbp
0x1800b4c82  push    rbx
0x1800b4c83  push    rdi
0x1800b4c84  push    r14
0x1800b4c86  lea     rbp, [rsp-1B8h]
0x1800b4c8e  sub     rsp, 2B8h
0x1800b4c95  mov     rax, cs:__security_cookie
0x1800b4c9c  xor     rax, rsp
0x1800b4c9f  mov     [rbp+1D0h+var_30], rax
0x1800b4ca6  mov     rbx, rcx
0x1800b4ca9  xor     edx, edx; Val
0x1800b4cab  mov     r8d, 250h; Size
0x1800b4cb1  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x1800b4cb6  call    memset_0
0x1800b4cbb  mov     [rsp+2D0h+ppszPathOut], 0
0x1800b4cc4  mov     [rsp+2D0h+var_298], 0
0x1800b4ccd  xor     edx, edx
0x1800b4ccf  lea     rcx, [rsp+2D0h+ppszPathOut]
0x1800b4cd4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b4cd9  lea     r8, [rsp+2D0h+ppszPathOut]; ppszPathOut
0x1800b4cde  mov     edi, 1
0x1800b4ce3  mov     edx, edi; dwFlags
0x1800b4ce5  mov     rcx, rbx; pszPathIn
0x1800b4ce8  call    cs:__imp_PathAllocCanonicalize
0x1800b4cee  test    eax, eax
0x1800b4cf0  js      loc_1800B4E28
0x1800b4cf6  xor     edx, edx
0x1800b4cf8  lea     rcx, [rsp+2D0h+var_298]
0x1800b4cfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b4d02  lea     r9, [rsp+2D0h+var_298]; ppszPathOut
0x1800b4d07  mov     r8d, edi; dwFlags
0x1800b4d0a  lea     rdx, asc_18011A000; "*.*"
0x1800b4d11  mov     rcx, [rsp+2D0h+ppszPathOut]; pszPathIn
0x1800b4d16  call    cs:__imp_PathAllocCombine
0x1800b4d1c  test    eax, eax
0x1800b4d1e  js      loc_1800B4E28
0x1800b4d24  mov     [rsp+2D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x1800b4d2c  mov     [rsp+2D0h+lpSearchFilter], 0; lpSearchFilter
0x1800b4d35  xor     r9d, r9d; fSearchOp
0x1800b4d38  lea     r8, [rsp+2D0h+FindFileData]; lpFindFileData
0x1800b4d3d  mov     edx, edi; fInfoLevelId
0x1800b4d3f  mov     rcx, [rsp+2D0h+var_298]; lpFileName
0x1800b4d44  call    cs:__imp_FindFirstFileExW
0x1800b4d4a  mov     rbx, rax
0x1800b4d4d  mov     [rsp+2D0h+var_288], rax
0x1800b4d52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b4d56  jnz     short loc_1800B4D60
0x1800b4d58  xor     dil, dil
0x1800b4d5b  jmp     loc_1800B4E66
0x1800b4d60  mov     r14d, 2Eh ; '.'
0x1800b4d66  movzx   edx, [rsp+2D0h+pszMore]
0x1800b4d6b  sub     edx, r14d
0x1800b4d6e  jnz     short loc_1800B4D7C
0x1800b4d70  movzx   edx, [rsp+2D0h+var_252]
0x1800b4d75  xor     eax, eax
0x1800b4d77  movzx   ecx, ax
0x1800b4d7a  sub     edx, ecx
0x1800b4d7c  test    edx, edx
0x1800b4d7e  jz      loc_1800B4E07
0x1800b4d84  movzx   edx, [rsp+2D0h+pszMore]
0x1800b4d89  sub     edx, r14d
0x1800b4d8c  jnz     short loc_1800B4DA3
0x1800b4d8e  movzx   edx, [rsp+2D0h+var_252]
0x1800b4d93  sub     edx, r14d
0x1800b4d96  jnz     short loc_1800B4DA3
0x1800b4d98  movzx   edx, [rbp+1D0h+var_250]
0x1800b4d9c  xor     eax, eax
0x1800b4d9e  movzx   ecx, ax
0x1800b4da1  sub     edx, ecx
0x1800b4da3  test    edx, edx
0x1800b4da5  jz      short loc_1800B4E07
0x1800b4da7  test    [rsp+2D0h+FindFileData], 10h
0x1800b4dac  jz      short loc_1800B4DF9
0x1800b4dae  mov     [rsp+2D0h+pszPathIn], 0
0x1800b4db7  xor     edx, edx
0x1800b4db9  lea     rcx, [rsp+2D0h+pszPathIn]
0x1800b4dbe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b4dc3  lea     r9, [rsp+2D0h+pszPathIn]; ppszPathOut
0x1800b4dc8  mov     r8d, edi; dwFlags
0x1800b4dcb  lea     rdx, [rsp+2D0h+pszMore]; pszMore
0x1800b4dd0  mov     rcx, [rsp+2D0h+ppszPathOut]; pszPathIn
0x1800b4dd5  call    cs:__imp_PathAllocCombine
0x1800b4ddb  test    eax, eax
0x1800b4ddd  js      short loc_1800B4DED
0x1800b4ddf  mov     rcx, [rsp+2D0h+pszPathIn]; this
0x1800b4de4  call    ?RecursiveCheckNonEmptyDirectory@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NPEBG@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::RecursiveCheckNonEmptyDirectory(ushort const *)
0x1800b4de9  test    al, al
0x1800b4deb  jnz     short loc_1800B4E5B
0x1800b4ded  lea     rcx, [rsp+2D0h+pszPathIn]
0x1800b4df2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4df7  jmp     short loc_1800B4E07
0x1800b4df9  cmp     [rsp+2D0h+var_264], 0
0x1800b4dfe  ja      short loc_1800B4E66
0x1800b4e00  cmp     [rsp+2D0h+var_260], 0
0x1800b4e05  ja      short loc_1800B4E66
0x1800b4e07  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x1800b4e0c  mov     rcx, rbx; hFindFile
0x1800b4e0f  call    cs:__imp_FindNextFileW
0x1800b4e15  test    eax, eax
0x1800b4e17  jnz     loc_1800B4D66
0x1800b4e1d  lea     rcx, [rsp+2D0h+var_288]
0x1800b4e22  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b4e27  nop
0x1800b4e28  lea     rcx, [rsp+2D0h+var_298]
0x1800b4e2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4e32  nop
0x1800b4e33  lea     rcx, [rsp+2D0h+ppszPathOut]
0x1800b4e38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4e3d  xor     al, al
0x1800b4e3f  mov     rcx, [rbp+1D0h+var_30]
0x1800b4e46  xor     rcx, rsp; StackCookie
0x1800b4e49  call    __security_check_cookie
0x1800b4e4e  add     rsp, 2B8h
0x1800b4e55  pop     r14
0x1800b4e57  pop     rdi
0x1800b4e58  pop     rbx
0x1800b4e59  pop     rbp
0x1800b4e5a  retn
0x1800b4e5b  lea     rcx, [rsp+2D0h+pszPathIn]
0x1800b4e60  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4e65  nop
0x1800b4e66  lea     rcx, [rsp+2D0h+var_288]
0x1800b4e6b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b4e70  nop
0x1800b4e71  lea     rcx, [rsp+2D0h+var_298]
0x1800b4e76  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4e7b  nop
0x1800b4e7c  lea     rcx, [rsp+2D0h+ppszPathOut]
0x1800b4e81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b4e86  mov     al, dil
0x1800b4e89  jmp     short loc_1800B4E3F
```
