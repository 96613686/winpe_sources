# CloudCacheInitializer::AddCapabilityAccessToCloudStoreDirectory(ulong)

- ea: `0x18003c1a0`
- end: `0x18003c337`
- name: `?AddCapabilityAccessToCloudStoreDirectory@CloudCacheInitializer@@AEAAJK@Z`
- size: `407`
- prototype: `__int64 __fastcall(CloudCacheInitializer *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18003c340`
- `0x18003c5b8`

## callees

- `0x180031fb0`
- `0x1800320d4`
- `0x18003b488`
- `0x18003b5f4`
- `0x18003c1a0`
- `0x1800c8458`
- `0x1800fc644`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003c23c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003c264`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003c23c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003c264`
- `USERENV!GetUserProfileDirectoryW` at `0x18003c1f5`
- `USERENV!GetUserProfileDirectoryW` at `0x18003c1f5`

## string_xrefs

- `0x18003c2c1`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003c2db`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003c2fc`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003c31e`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CloudCacheInitializer::AddCapabilityAccessToCloudStoreDirectory(
        CloudCacheInitializer *this,
        char a2)
{
  HANDLE *v4; // rax
  BOOL UserProfileDirectoryW; // ebx
  const char *v6; // r9
  const WCHAR *v7; // r9
  HRESULT v8; // ebx
  const unsigned __int16 *v9; // rdx
  int DirectoryDeepNoThrow; // eax
  CloudCacheInitializer *v11; // rcx
  enum _SE_OBJECT_TYPE v12; // r8d
  const unsigned __int16 *v13; // r9
  int v14; // eax
  __int64 v16; // rdx
  DWORD cchSize; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[24]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR v19[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszPathOut[264]; // [rsp+460h] [rbp+360h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+5A8h]

  if ( *((_BYTE *)this + 80) )
    return 0;
  cchSize = 260;
  v4 = (HANDLE *)CloudStoreUtilities::OpenCurrentThreadAccessToken(v18);
  UserProfileDirectoryW = GetUserProfileDirectoryW(*v4, ProfileDir, &cchSize);
  std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(v18);
  if ( !UserProfileDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x395,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             v6);
  *((_BYTE *)this + 80) = 1;
  v7 = L"AppData\\Local";
  if ( (a2 & 6) == 0 )
    v7 = L"AppData\\Roaming";
  v8 = PathCchCombine(pszPathOut, 0x104u, ProfileDir, v7);
  if ( v8 < 0 )
  {
    v16 = 924;
  }
  else
  {
    v8 = PathCchCombine(v19, 0x104u, pszPathOut, L"Microsoft\\Windows\\CloudStore");
    if ( v8 < 0 )
    {
      v16 = 928;
    }
    else
    {
      DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v19, v9);
      v8 = DirectoryDeepNoThrow;
      if ( DirectoryDeepNoThrow < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
          (const char *)(unsigned int)DirectoryDeepNoThrow,
          cchSize);
      }
      else
      {
        v14 = CloudCacheInitializer::AddCapabilityAccessToObject(v11, v19, v12, v13);
        v8 = v14;
        if ( v14 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A9,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)(unsigned int)v14,
            cchSize);
        if ( v8 >= 0 )
          return 0;
      }
      v16 = 929;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
    (const char *)(unsigned int)v8,
    cchSize);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c1a0  push    rbp
0x18003c1a2  push    rbx
0x18003c1a3  push    rsi
0x18003c1a4  push    rdi
0x18003c1a5  lea     rbp, [rsp-588h]
0x18003c1ad  sub     rsp, 688h
0x18003c1b4  mov     rax, cs:__security_cookie
0x18003c1bb  xor     rax, rsp
0x18003c1be  mov     [rbp+5A0h+var_30], rax
0x18003c1c5  cmp     byte ptr [rcx+50h], 0
0x18003c1c9  mov     esi, edx
0x18003c1cb  mov     rdi, rcx
0x18003c1ce  jnz     loc_18003C298
0x18003c1d4  lea     rcx, [rsp+6A0h+var_678]
0x18003c1d9  mov     [rsp+6A0h+cchSize], 104h; int
0x18003c1e1  call    ?OpenCurrentThreadAccessToken@CloudStoreUtilities@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@XZ; CloudStoreUtilities::OpenCurrentThreadAccessToken(void)
0x18003c1e6  lea     r8, [rsp+6A0h+cchSize]; lpcchSize
0x18003c1eb  lea     rdx, [rbp+5A0h+ProfileDir]; lpProfileDir
0x18003c1f2  mov     rcx, [rax]; hToken
0x18003c1f5  call    cs:__imp_GetUserProfileDirectoryW
0x18003c1fb  lea     rcx, [rsp+6A0h+var_678]
0x18003c200  mov     ebx, eax
0x18003c202  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x18003c207  test    ebx, ebx
0x18003c209  jz      loc_18003C2D4
0x18003c20f  lea     rax, aAppdataRoaming; "AppData\\Roaming"
0x18003c216  mov     byte ptr [rdi+50h], 1
0x18003c21a  test    sil, 6
0x18003c21e  lea     r9, aAppdataLocal; "AppData\\Local"
0x18003c225  lea     r8, [rbp+5A0h+ProfileDir]; pszPathIn
0x18003c22c  mov     edx, 104h; cchPathOut
0x18003c231  cmovz   r9, rax; pszMore
0x18003c235  lea     rcx, [rbp+5A0h+pszPathOut]; pszPathOut
0x18003c23c  call    cs:__imp_PathCchCombine
0x18003c242  mov     ebx, eax
0x18003c244  test    eax, eax
0x18003c246  js      loc_18003C2EE
0x18003c24c  lea     r9, aMicrosoftWindo_0; "Microsoft\\Windows\\CloudStore"
0x18003c253  mov     edx, 104h; cchPathOut
0x18003c258  lea     r8, [rbp+5A0h+pszPathOut]; pszPathIn
0x18003c25f  lea     rcx, [rsp+6A0h+var_660]; pszPathOut
0x18003c264  call    cs:__imp_PathCchCombine
0x18003c26a  mov     ebx, eax
0x18003c26c  test    eax, eax
0x18003c26e  js      short loc_18003C2B5
0x18003c270  lea     rcx, [rsp+6A0h+var_660]; this
0x18003c275  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003c27a  mov     ebx, eax
0x18003c27c  test    eax, eax
0x18003c27e  js      short loc_18003C2F5
0x18003c280  lea     rdx, [rsp+6A0h+var_660]; unsigned __int16 *
0x18003c285  call    ?AddCapabilityAccessToObject@CloudCacheInitializer@@AEAAJPEBGW4_SE_OBJECT_TYPE@@0@Z; CloudCacheInitializer::AddCapabilityAccessToObject(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x18003c28a  mov     ebx, eax
0x18003c28c  test    eax, eax
0x18003c28e  js      loc_18003C317
0x18003c294  test    ebx, ebx
0x18003c296  js      short loc_18003C310
0x18003c298  xor     eax, eax
0x18003c29a  mov     rcx, [rbp+5A0h+var_30]
0x18003c2a1  xor     rcx, rsp; StackCookie
0x18003c2a4  call    __security_check_cookie
0x18003c2a9  add     rsp, 688h
0x18003c2b0  pop     rdi
0x18003c2b1  pop     rsi
0x18003c2b2  pop     rbx
0x18003c2b3  pop     rbp
0x18003c2b4  retn
0x18003c2b5  mov     edx, 3A0h; void *
0x18003c2ba  mov     rcx, [rbp+5A8h]; this
0x18003c2c1  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003c2c8  mov     r9d, ebx; char *
0x18003c2cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2d0  mov     eax, ebx
0x18003c2d2  jmp     short loc_18003C29A
0x18003c2d4  mov     rcx, [rbp+5A8h]; this
0x18003c2db  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003c2e2  mov     edx, 395h; void *
0x18003c2e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c2ec  jmp     short loc_18003C29A
0x18003c2ee  mov     edx, 39Ch
0x18003c2f3  jmp     short loc_18003C2BA
0x18003c2f5  mov     rcx, [rbp+5A8h]; this
0x18003c2fc  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003c303  mov     r9d, eax; char *
0x18003c306  mov     edx, 3A8h; void *
0x18003c30b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c310  mov     edx, 3A1h
0x18003c315  jmp     short loc_18003C2BA
0x18003c317  mov     rcx, [rbp+5A8h]; this
0x18003c31e  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003c325  mov     r9d, ebx; char *
0x18003c328  mov     edx, 3A9h; void *
0x18003c32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c332  jmp     loc_18003C294
```
