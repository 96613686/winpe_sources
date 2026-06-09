# RetailDemoSetupAccountsTask::AreOfficeBitsOnBox(void)

- ea: `0x1800215fc`
- end: `0x18002179f`
- name: `?AreOfficeBitsOnBox@RetailDemoSetupAccountsTask@@AEAA_NXZ`
- size: `419`
- prototype: `bool __fastcall(RetailDemoSetupAccountsTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021830`

## callees

- `0x180003390`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x1800215fc`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1800216d0`
- `SHLWAPI!PathFileExistsW` at `0x180021763`
- `SHLWAPI!PathFileExistsW` at `0x1800216d0`
- `SHLWAPI!PathFileExistsW` at `0x180021763`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800216a5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021738`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800216a5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021738`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002166b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800216fe`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002166b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800216fe`

## string_xrefs

- `0x18002167f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x1800216b9`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180021712`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x18002174c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall RetailDemoSetupAccountsTask::AreOfficeBitsOnBox(RetailDemoSetupAccountsTask *this)
{
  HRESULT v1; // eax
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszMore[20]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  wcscpy(pszMore, L"Microsoft Office");
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v1 = SHGetKnownFolderPath(&FOLDERID_ProgramFiles, 0x5000u, 0, &ppszPath);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
      (const char *)(unsigned int)v1,
      (int)ppszPath);
  v2 = PathCchCombine(pszPathOut, 0x104u, ppszPath, pszMore);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
      (const char *)(unsigned int)v2,
      (int)ppszPath);
  if ( PathFileExistsW(pszPathOut) )
    goto LABEL_12;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v3 = SHGetKnownFolderPath(&FOLDERID_ProgramFilesX86, 0x5000u, 0, &ppszPath);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
      (const char *)(unsigned int)v3,
      (int)ppszPath);
  v4 = PathCchCombine(pszPathOut, 0x104u, ppszPath, pszMore);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
      (const char *)(unsigned int)v4,
      (int)ppszPath);
  if ( PathFileExistsW(pszPathOut) )
  {
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return 1;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return 0;
  }
}

```

## disassembly

```asm
0x1800215fc  push    rbp
0x1800215fe  lea     rbp, [rsp-170h]
0x180021606  sub     rsp, 270h
0x18002160d  mov     rax, cs:__security_cookie
0x180021614  xor     rax, rsp
0x180021617  mov     [rbp+170h+var_10], rax
0x18002161e  movups  xmm0, xmmword ptr cs:aMicrosoftOffic; "Microsoft Office"
0x180021625  movups  xmmword ptr [rsp+270h+pszMore], xmm0
0x18002162a  movups  xmm1, xmmword ptr cs:aMicrosoftOffic+10h; "t Office"
0x180021631  movups  [rsp+270h+var_238], xmm1
0x180021636  movzx   eax, word ptr cs:aMicrosoftOffic+20h; ""
0x18002163d  mov     [rsp+270h+var_228], ax
0x180021642  mov     [rsp+270h+ppszPath], 0; int
0x18002164b  xor     edx, edx
0x18002164d  lea     rcx, [rsp+270h+ppszPath]
0x180021652  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180021657  lea     r9, [rsp+270h+ppszPath]; ppszPath
0x18002165c  xor     r8d, r8d; hToken
0x18002165f  mov     edx, 5000h; dwFlags
0x180021664  lea     rcx, FOLDERID_ProgramFiles; rfid
0x18002166b  call    cs:__imp_SHGetKnownFolderPath
0x180021671  mov     rcx, [rbp+178h]; this
0x180021678  test    eax, eax
0x18002167a  jns     short loc_180021691
0x18002167c  mov     r9d, eax; char *
0x18002167f  lea     r8, aPcshellShellRe_5; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180021686  mov     edx, 26h ; '&'; void *
0x18002168b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021691  lea     r9, [rsp+270h+pszMore]; pszMore
0x180021696  mov     r8, [rsp+270h+ppszPath]; pszPathIn
0x18002169b  mov     edx, 104h; cchPathOut
0x1800216a0  lea     rcx, [rsp+270h+pszPathOut]; pszPathOut
0x1800216a5  call    cs:__imp_PathCchCombine
0x1800216ab  mov     rcx, [rbp+178h]; this
0x1800216b2  test    eax, eax
0x1800216b4  jns     short loc_1800216CB
0x1800216b6  mov     r9d, eax; char *
0x1800216b9  lea     r8, aPcshellShellRe_5; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800216c0  mov     edx, 28h ; '('; void *
0x1800216c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800216cb  lea     rcx, [rsp+270h+pszPathOut]; pszPath
0x1800216d0  call    cs:__imp_PathFileExistsW
0x1800216d6  test    eax, eax
0x1800216d8  jnz     loc_18002177B
0x1800216de  xor     edx, edx
0x1800216e0  lea     rcx, [rsp+270h+ppszPath]
0x1800216e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800216ea  lea     r9, [rsp+270h+ppszPath]; ppszPath
0x1800216ef  xor     r8d, r8d; hToken
0x1800216f2  mov     edx, 5000h; dwFlags
0x1800216f7  lea     rcx, FOLDERID_ProgramFilesX86; rfid
0x1800216fe  call    cs:__imp_SHGetKnownFolderPath
0x180021704  mov     rcx, [rbp+178h]; this
0x18002170b  test    eax, eax
0x18002170d  jns     short loc_180021724
0x18002170f  mov     r9d, eax; char *
0x180021712  lea     r8, aPcshellShellRe_5; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180021719  mov     edx, 2Eh ; '.'; void *
0x18002171e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021724  lea     r9, [rsp+270h+pszMore]; pszMore
0x180021729  mov     r8, [rsp+270h+ppszPath]; pszPathIn
0x18002172e  mov     edx, 104h; cchPathOut
0x180021733  lea     rcx, [rsp+270h+pszPathOut]; pszPathOut
0x180021738  call    cs:__imp_PathCchCombine
0x18002173e  mov     rcx, [rbp+178h]; this
0x180021745  test    eax, eax
0x180021747  jns     short loc_18002175E
0x180021749  mov     r9d, eax; char *
0x18002174c  lea     r8, aPcshellShellRe_5; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180021753  mov     edx, 2Fh ; '/'; void *
0x180021758  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002175e  lea     rcx, [rsp+270h+pszPathOut]; pszPath
0x180021763  call    cs:__imp_PathFileExistsW
0x180021769  test    eax, eax
0x18002176b  jnz     short loc_18002177B
0x18002176d  lea     rcx, [rsp+270h+ppszPath]
0x180021772  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021777  xor     al, al
0x180021779  jmp     short loc_180021787
0x18002177b  lea     rcx, [rsp+270h+ppszPath]
0x180021780  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021785  mov     al, 1
0x180021787  mov     rcx, [rbp+170h+var_10]
0x18002178e  xor     rcx, rsp; StackCookie
0x180021791  call    __security_check_cookie
0x180021796  add     rsp, 270h
0x18002179d  pop     rbp
0x18002179e  retn
```
