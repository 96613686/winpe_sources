# RestoreStartLayoutTask::CustomStartExists(void)

- ea: `0x18002ce20`
- end: `0x18002cf8b`
- name: `?CustomStartExists@RestoreStartLayoutTask@@AEAA_NXZ`
- size: `363`
- prototype: `bool __fastcall(RestoreStartLayoutTask *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002cfa0`
- `0x18002d080`

## callees

- `0x180003390`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x18002ce20`
- `0x180032050`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18002cf3d`
- `SHLWAPI!PathFileExistsW` at `0x18002cf3d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002cf12`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002cf12`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002cedb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002cedb`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002ce6d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002ce6d`

## string_xrefs

- `0x18002ce81`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restorestartlayouttask.cpp`
- `0x18002ceef`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restorestartlayouttask.cpp`
- `0x18002cf26`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restorestartlayouttask.cpp`
- `0x18002cf01`: `start_th2.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall RestoreStartLayoutTask::CustomStartExists(RestoreStartLayoutTask *this)
{
  HRESULT v1; // eax
  HRESULT v2; // eax
  HRESULT v3; // eax
  bool v4; // bl
  PCWSTR pszMore; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v1 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restorestartlayouttask.cpp",
      (const char *)(unsigned int)v1,
      (int)pszMore);
  pszMore = 0;
  v8[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &pszMore,
    0);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v8,
    0);
  RetailDemoUtil::TryGetAssociatedFolders(0x2000, v8, &pszMore);
  v2 = PathCchCombine(pszPathOut, 0x104u, ppszPath, pszMore);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restorestartlayouttask.cpp",
      (const char *)(unsigned int)v2,
      (int)pszMore);
  v3 = PathCchAppend(pszPathOut, 0x104u, L"start_th2.xml");
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restorestartlayouttask.cpp",
      (const char *)(unsigned int)v3,
      (int)pszMore);
  v4 = PathFileExistsW(pszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszMore);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  return v4;
}

```

## disassembly

```asm
0x18002ce20  mov     [rsp-8+arg_0], rbx
0x18002ce25  push    rbp
0x18002ce26  lea     rbp, [rsp-160h]
0x18002ce2e  sub     rsp, 260h
0x18002ce35  mov     rax, cs:__security_cookie
0x18002ce3c  xor     rax, rsp
0x18002ce3f  mov     [rbp+160h+var_10], rax
0x18002ce46  xor     ebx, ebx
0x18002ce48  mov     [rsp+260h+ppszPath], rbx
0x18002ce4d  xor     edx, edx
0x18002ce4f  lea     rcx, [rsp+260h+ppszPath]
0x18002ce54  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002ce59  lea     r9, [rsp+260h+ppszPath]; ppszPath
0x18002ce5e  xor     r8d, r8d; hToken
0x18002ce61  mov     edx, 5000h; dwFlags
0x18002ce66  lea     rcx, FOLDERID_RetailDemo; rfid
0x18002ce6d  call    cs:__imp_SHGetKnownFolderPath
0x18002ce73  mov     rcx, [rbp+168h]; this
0x18002ce7a  test    eax, eax
0x18002ce7c  jns     short loc_18002CE91
0x18002ce7e  mov     r9d, eax; char *
0x18002ce81  lea     r8, aPcshellShellRe_21; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002ce88  lea     edx, [rbx+35h]; void *
0x18002ce8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ce91  mov     [rsp+260h+pszMore], rbx; int
0x18002ce96  mov     [rsp+260h+var_230], rbx
0x18002ce9b  xor     edx, edx
0x18002ce9d  lea     rcx, [rsp+260h+pszMore]
0x18002cea2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002cea7  xor     edx, edx
0x18002cea9  lea     rcx, [rsp+260h+var_230]
0x18002ceae  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002ceb3  lea     r8, [rsp+260h+pszMore]
0x18002ceb8  lea     rdx, [rsp+260h+var_230]
0x18002cebd  mov     ecx, 2000h
0x18002cec2  call    ?TryGetAssociatedFolders@RetailDemoUtil@@YA_NW4ProvisioningContentType@@PEAPEAG1@Z; RetailDemoUtil::TryGetAssociatedFolders(ProvisioningContentType,ushort * *,ushort * *)
0x18002cec7  mov     r9, [rsp+260h+pszMore]; pszMore
0x18002cecc  mov     r8, [rsp+260h+ppszPath]; pszPathIn
0x18002ced1  mov     edx, 104h; cchPathOut
0x18002ced6  lea     rcx, [rsp+260h+pszPathOut]; pszPathOut
0x18002cedb  call    cs:__imp_PathCchCombine
0x18002cee1  mov     rcx, [rbp+168h]; this
0x18002cee8  test    eax, eax
0x18002ceea  jns     short loc_18002CF01
0x18002ceec  mov     r9d, eax; char *
0x18002ceef  lea     r8, aPcshellShellRe_21; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cef6  mov     edx, 3Bh ; ';'; void *
0x18002cefb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cf01  lea     r8, aStartTh2Xml; "start_th2.xml"
0x18002cf08  mov     edx, 104h; cchPath
0x18002cf0d  lea     rcx, [rsp+260h+pszPathOut]; pszPath
0x18002cf12  call    cs:__imp_PathCchAppend
0x18002cf18  mov     rcx, [rbp+168h]; this
0x18002cf1f  test    eax, eax
0x18002cf21  jns     short loc_18002CF38
0x18002cf23  mov     r9d, eax; char *
0x18002cf26  lea     r8, aPcshellShellRe_21; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002cf2d  mov     edx, 3Ch ; '<'; void *
0x18002cf32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cf38  lea     rcx, [rsp+260h+pszPathOut]; pszPath
0x18002cf3d  call    cs:__imp_PathFileExistsW
0x18002cf43  nop
0x18002cf44  test    eax, eax
0x18002cf46  setnz   bl
0x18002cf49  lea     rcx, [rsp+260h+var_230]
0x18002cf4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002cf53  nop
0x18002cf54  lea     rcx, [rsp+260h+pszMore]
0x18002cf59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002cf5e  nop
0x18002cf5f  lea     rcx, [rsp+260h+ppszPath]
0x18002cf64  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002cf69  mov     al, bl
0x18002cf6b  mov     rcx, [rbp+160h+var_10]
0x18002cf72  xor     rcx, rsp; StackCookie
0x18002cf75  call    __security_check_cookie
0x18002cf7a  mov     rbx, [rsp+260h+arg_0]
0x18002cf82  add     rsp, 260h
0x18002cf89  pop     rbp
0x18002cf8a  retn
```
