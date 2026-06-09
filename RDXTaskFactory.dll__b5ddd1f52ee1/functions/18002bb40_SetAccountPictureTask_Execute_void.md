# SetAccountPictureTask::Execute(void)

- ea: `0x18002bb40`
- end: `0x18002bc90`
- name: `?Execute@SetAccountPictureTask@@MEAAXXZ`
- size: `336`
- prototype: `void __fastcall(SetAccountPictureTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x18002bb40`
- `0x18002e5b8`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002bbf9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002bbf9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002bbc3`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002bbc3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002bb87`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002bb87`

## string_xrefs

- `0x18002bb9c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setaccountpicturetask.cpp`
- `0x18002bbd8`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setaccountpicturetask.cpp`
- `0x18002bc0e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setaccountpicturetask.cpp`
- `0x18002bc50`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setaccountpicturetask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SetAccountPictureTask::Execute(PCWSTR *this)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  _QWORD *UserAgent; // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  PWSTR ppszPath; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setaccountpicturetask.cpp",
      (const char *)(unsigned int)v2,
      (int)ppszPath);
  v3 = PathCchCombine(pszPathOut, 0x104u, ppszPath, this[10]);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setaccountpicturetask.cpp",
      (const char *)(unsigned int)v3,
      (int)ppszPath);
  v4 = PathCchAppend(pszPathOut, 0x104u, L"AccountPicture\\picture.jpg");
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setaccountpicturetask.cpp",
      (const char *)(unsigned int)v4,
      (int)ppszPath);
  UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(v10, 0);
  v6 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*UserAgent + 80LL))(*UserAgent, pszPathOut);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setaccountpicturetask.cpp",
      (const char *)(unsigned int)v6,
      (int)ppszPath);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v10, v7, v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
}

```

## disassembly

```asm
0x18002bb40  push    rbx
0x18002bb42  sub     rsp, 250h
0x18002bb49  mov     rax, cs:__security_cookie
0x18002bb50  xor     rax, rsp
0x18002bb53  mov     [rsp+258h+var_18], rax
0x18002bb5b  mov     rbx, rcx
0x18002bb5e  mov     [rsp+258h+ppszPath], 0; int
0x18002bb67  xor     edx, edx
0x18002bb69  lea     rcx, [rsp+258h+ppszPath]
0x18002bb6e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002bb73  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x18002bb78  xor     r8d, r8d; hToken
0x18002bb7b  mov     edx, 5000h; dwFlags
0x18002bb80  lea     rcx, FOLDERID_RetailDemo; rfid
0x18002bb87  call    cs:__imp_SHGetKnownFolderPath
0x18002bb8d  mov     rcx, [rsp+258h]; this
0x18002bb95  test    eax, eax
0x18002bb97  jns     short loc_18002BBAE
0x18002bb99  mov     r9d, eax; char *
0x18002bb9c  lea     r8, aPcshellShellRe_6; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002bba3  mov     edx, 25h ; '%'; void *
0x18002bba8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bbae  mov     r9, [rbx+50h]; pszMore
0x18002bbb2  mov     r8, [rsp+258h+ppszPath]; pszPathIn
0x18002bbb7  mov     ebx, 104h
0x18002bbbc  mov     edx, ebx; cchPathOut
0x18002bbbe  lea     rcx, [rsp+258h+pszPathOut]; pszPathOut
0x18002bbc3  call    cs:__imp_PathCchCombine
0x18002bbc9  mov     rcx, [rsp+258h]; this
0x18002bbd1  test    eax, eax
0x18002bbd3  jns     short loc_18002BBEA
0x18002bbd5  mov     r9d, eax; char *
0x18002bbd8  lea     r8, aPcshellShellRe_6; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002bbdf  mov     edx, 27h ; '''; void *
0x18002bbe4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bbea  lea     r8, aAccountpicture; "AccountPicture\\picture.jpg"
0x18002bbf1  mov     rdx, rbx; cchPath
0x18002bbf4  lea     rcx, [rsp+258h+pszPathOut]; pszPath
0x18002bbf9  call    cs:__imp_PathCchAppend
0x18002bbff  mov     rcx, [rsp+258h]; this
0x18002bc07  test    eax, eax
0x18002bc09  jns     short loc_18002BC20
0x18002bc0b  mov     r9d, eax; char *
0x18002bc0e  lea     r8, aPcshellShellRe_6; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002bc15  mov     edx, 28h ; '('; void *
0x18002bc1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bc20  xor     edx, edx
0x18002bc22  lea     rcx, [rsp+258h+var_230]
0x18002bc27  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x18002bc2c  nop
0x18002bc2d  mov     rcx, [rax]
0x18002bc30  mov     rax, [rcx]
0x18002bc33  lea     rdx, [rsp+258h+pszPathOut]
0x18002bc38  mov     rax, [rax+50h]
0x18002bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc41  mov     rcx, [rsp+258h]; this
0x18002bc49  test    eax, eax
0x18002bc4b  jns     short loc_18002BC62
0x18002bc4d  mov     r9d, eax; char *
0x18002bc50  lea     r8, aPcshellShellRe_6; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002bc57  mov     edx, 29h ; ')'; void *
0x18002bc5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bc62  lea     rcx, [rsp+258h+var_230]
0x18002bc67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc6c  nop
0x18002bc6d  lea     rcx, [rsp+258h+ppszPath]
0x18002bc72  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bc77  mov     rcx, [rsp+258h+var_18]
0x18002bc7f  xor     rcx, rsp; StackCookie
0x18002bc82  call    __security_check_cookie
0x18002bc87  add     rsp, 250h
0x18002bc8e  pop     rbx
0x18002bc8f  retn
```
