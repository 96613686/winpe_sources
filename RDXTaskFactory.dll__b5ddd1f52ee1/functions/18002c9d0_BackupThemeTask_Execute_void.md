# BackupThemeTask::Execute(void)

- ea: `0x18002c9d0`
- end: `0x18002cc2d`
- name: `?Execute@BackupThemeTask@@MEAAXXZ`
- size: `605`
- prototype: `void __fastcall(BackupThemeTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180014d04`
- `0x18002c9d0`
- `0x18002fc68`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cba6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002ca5d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002ca99`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002cad7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002ca5d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002ca99`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002cad7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002cb59`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002cb95`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002cb59`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002cb95`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002cbd7`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002cbd7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002ca22`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002ca22`

## string_xrefs

- `0x18002ca36`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002ca71`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002caad`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002caeb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002cb77`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002cbb3`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`
- `0x18002cbe8`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backupthemetask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall BackupThemeTask::Execute(PCWSTR *this)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  _QWORD *v6; // rdx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v12[7]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-98h]
  WCHAR pszPathOut[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPathIn[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR NewFileName[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v2,
      (int)ppszPath);
  v3 = PathCchCombine(pszPathOut, 0x104u, ppszPath, this[10]);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v3,
      (int)ppszPath);
  v4 = PathCchCombine(pszPathIn, 0x104u, pszPathOut, L"Wallpaper");
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v4,
      (int)ppszPath);
  v5 = PathCchCombine(NewFileName, 0x104u, pszPathIn, L"wallpaper_old.jpg");
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      (const char *)(unsigned int)v5,
      (int)ppszPath);
  lpExistingFileName = 0;
  v12[0] = off_180053068;
  v12[1] = &lpExistingFileName;
  v13 = v12;
  RetailDemoUtil::ExecuteAsDemoUser(v12);
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v6);
  }
  if ( !CreateDirectoryW(pszPathOut, 0) && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      v7);
  if ( !CreateDirectoryW(pszPathIn, 0) && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      v8);
  if ( !CopyFileW(lpExistingFileName, NewFileName, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backupthemetask.cpp",
      v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpExistingFileName);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
}

```

## disassembly

```asm
0x18002c9d0  mov     [rsp-8+arg_8], rbx
0x18002c9d5  push    rbp
0x18002c9d6  lea     rbp, [rsp-5B0h]
0x18002c9de  sub     rsp, 6B0h
0x18002c9e5  mov     rax, cs:__security_cookie
0x18002c9ec  xor     rax, rsp
0x18002c9ef  mov     [rbp+5B0h+var_10], rax
0x18002c9f6  mov     rbx, rcx
0x18002c9f9  mov     [rsp+6B0h+ppszPath], 0; int
0x18002ca02  xor     edx, edx
0x18002ca04  lea     rcx, [rsp+6B0h+ppszPath]
0x18002ca09  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002ca0e  lea     r9, [rsp+6B0h+ppszPath]; ppszPath
0x18002ca13  xor     r8d, r8d; hToken
0x18002ca16  mov     edx, 5000h; dwFlags
0x18002ca1b  lea     rcx, FOLDERID_RetailDemo; rfid
0x18002ca22  call    cs:__imp_SHGetKnownFolderPath
0x18002ca28  mov     rcx, [rbp+5B8h]; this
0x18002ca2f  test    eax, eax
0x18002ca31  jns     short loc_18002CA48
0x18002ca33  mov     r9d, eax; char *
0x18002ca36  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002ca3d  mov     edx, 24h ; '$'; void *
0x18002ca42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ca48  mov     r9, [rbx+50h]; pszMore
0x18002ca4c  mov     r8, [rsp+6B0h+ppszPath]; pszPathIn
0x18002ca51  mov     ebx, 104h
0x18002ca56  mov     edx, ebx; cchPathOut
0x18002ca58  lea     rcx, [rsp+6B0h+pszPathOut]; pszPathOut
0x18002ca5d  call    cs:__imp_PathCchCombine
0x18002ca63  mov     rcx, [rbp+5B8h]; this
0x18002ca6a  test    eax, eax
0x18002ca6c  jns     short loc_18002CA83
0x18002ca6e  mov     r9d, eax; char *
0x18002ca71  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002ca78  mov     edx, 26h ; '&'; void *
0x18002ca7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ca83  lea     r9, aWallpaper; "Wallpaper"
0x18002ca8a  lea     r8, [rsp+6B0h+pszPathOut]; pszPathIn
0x18002ca8f  mov     rdx, rbx; cchPathOut
0x18002ca92  lea     rcx, [rbp+5B0h+pszPathIn]; pszPathOut
0x18002ca99  call    cs:__imp_PathCchCombine
0x18002ca9f  mov     rcx, [rbp+5B8h]; this
0x18002caa6  test    eax, eax
0x18002caa8  jns     short loc_18002CABF
0x18002caaa  mov     r9d, eax; char *
0x18002caad  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cab4  mov     edx, 28h ; '('; void *
0x18002cab9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cabf  lea     r9, aWallpaperOldJp; "wallpaper_old.jpg"
0x18002cac6  lea     r8, [rbp+5B0h+pszPathIn]; pszPathIn
0x18002cacd  mov     rdx, rbx; cchPathOut
0x18002cad0  lea     rcx, [rbp+5B0h+NewFileName]; pszPathOut
0x18002cad7  call    cs:__imp_PathCchCombine
0x18002cadd  mov     rcx, [rbp+5B8h]; this
0x18002cae4  test    eax, eax
0x18002cae6  jns     short loc_18002CAFD
0x18002cae8  mov     r9d, eax; char *
0x18002caeb  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002caf2  mov     edx, 2Ah ; '*'; void *
0x18002caf7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cafd  mov     [rsp+6B0h+lpExistingFileName], 0
0x18002cb06  lea     rax, off_180053068
0x18002cb0d  mov     [rsp+6B0h+var_680], rax
0x18002cb12  lea     rax, [rsp+6B0h+lpExistingFileName]
0x18002cb17  mov     [rsp+6B0h+var_678], rax
0x18002cb1c  lea     rax, [rsp+6B0h+var_680]
0x18002cb21  mov     [rsp+6B0h+var_648], rax
0x18002cb26  lea     rcx, [rsp+6B0h+var_680]
0x18002cb2b  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x18002cb30  nop
0x18002cb31  mov     rcx, [rsp+6B0h+var_648]
0x18002cb36  test    rcx, rcx
0x18002cb39  jz      short loc_18002CB52
0x18002cb3b  mov     rax, [rcx]
0x18002cb3e  lea     rdx, [rsp+6B0h+var_680]
0x18002cb43  cmp     rcx, rdx
0x18002cb46  setnz   dl
0x18002cb49  mov     rax, [rax+20h]
0x18002cb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb52  xor     edx, edx; lpSecurityAttributes
0x18002cb54  lea     rcx, [rsp+6B0h+pszPathOut]; lpPathName
0x18002cb59  call    cs:__imp_CreateDirectoryW
0x18002cb5f  test    eax, eax
0x18002cb61  jnz     short loc_18002CB8C
0x18002cb63  mov     rbx, [rbp+5B8h]
0x18002cb6a  call    cs:__imp_GetLastError
0x18002cb70  cmp     eax, 0B7h
0x18002cb75  jz      short loc_18002CB8C
0x18002cb77  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cb7e  mov     edx, 37h ; '7'; void *
0x18002cb83  mov     rcx, rbx; this
0x18002cb86  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002cb8c  xor     edx, edx; lpSecurityAttributes
0x18002cb8e  lea     rcx, [rbp+5B0h+pszPathIn]; lpPathName
0x18002cb95  call    cs:__imp_CreateDirectoryW
0x18002cb9b  test    eax, eax
0x18002cb9d  jnz     short loc_18002CBC8
0x18002cb9f  mov     rbx, [rbp+5B8h]
0x18002cba6  call    cs:__imp_GetLastError
0x18002cbac  cmp     eax, 0B7h
0x18002cbb1  jz      short loc_18002CBC8
0x18002cbb3  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cbba  mov     edx, 3Ch ; '<'; void *
0x18002cbbf  mov     rcx, rbx; this
0x18002cbc2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002cbc8  xor     r8d, r8d; bFailIfExists
0x18002cbcb  lea     rdx, [rbp+5B0h+NewFileName]; lpNewFileName
0x18002cbd2  mov     rcx, [rsp+6B0h+lpExistingFileName]; lpExistingFileName
0x18002cbd7  call    cs:__imp_CopyFileW
0x18002cbdd  mov     rcx, [rbp+5B8h]; this
0x18002cbe4  test    eax, eax
0x18002cbe6  jnz     short loc_18002CBF8
0x18002cbe8  lea     r8, aPcshellShellRe_4; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cbef  lea     edx, [rax+3Fh]; void *
0x18002cbf2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002cbf8  lea     rcx, [rsp+6B0h+lpExistingFileName]
0x18002cbfd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002cc02  nop
0x18002cc03  lea     rcx, [rsp+6B0h+ppszPath]
0x18002cc08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002cc0d  mov     rcx, [rbp+5B0h+var_10]
0x18002cc14  xor     rcx, rsp; StackCookie
0x18002cc17  call    __security_check_cookie
0x18002cc1c  mov     rbx, [rsp+6B0h+arg_8]
0x18002cc24  add     rsp, 6B0h
0x18002cc2b  pop     rbp
0x18002cc2c  retn
```
