# UserOOBEController::LaunchCommandPrompt(void)

- ea: `0x180025ca0`
- end: `0x180025eb0`
- name: `?LaunchCommandPrompt@UserOOBEController@@UEAAJXZ`
- size: `528`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004200`
- `0x180007114`
- `0x180007134`
- `0x18000a5c8`
- `0x18000e580`
- `0x1800109f0`
- `0x180025ca0`
- `0x180025fd8`
- `0x180027a38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025df5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025df5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e80`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180025d69`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180025d69`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x180025e5d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x180025e5d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180025e6c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180025e6c`
- `ext-ms-win-ntuser-misc-l1-1-0!WaitForInputIdle` at `0x180025e39`
- `ext-ms-win-ntuser-misc-l1-1-0!WaitForInputIdle` at `0x180025e39`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180025cd8`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180025cd8`

## string_xrefs

- `0x180025ceb`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180025d38`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180025d7c`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180025e03`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEController::LaunchCommandPrompt(UserOOBEController *this)
{
  HRESULT v1; // eax
  unsigned int LastError; // ebx
  __int64 v3; // rax
  size_t v4; // rdi
  WCHAR *v5; // rbx
  HRESULT v6; // eax
  HRESULT v7; // edi
  const char *v8; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-89h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-59h] BYREF
  LPARAM lParam; // [rsp+68h] [rbp-41h] BYREF
  HWND hWnd; // [rsp+70h] [rbp-39h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  PWSTR pszPathOut; // [rsp+118h] [rbp+6Fh] BYREF
  PWSTR ppszPath; // [rsp+120h] [rbp+77h] BYREF

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v1 = SHGetKnownFolderPath(&FOLDERID_System, 0x5000u, 0, &ppszPath);
  LastError = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      bInheritHandles);
    goto LABEL_18;
  }
  v3 = -1;
  do
    ++v3;
  while ( ppszPath[v3] );
  v4 = v3 + 9;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pszPathOut,
    ppszPath,
    v3 + 9);
  v5 = pszPathOut;
  if ( !pszPathOut )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)0x8007000ELL,
      bInheritHandles);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathOut);
    goto LABEL_18;
  }
  v6 = PathCchCombine(pszPathOut, v4, ppszPath, L"cmd.exe");
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v6,
      bInheritHandles);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathOut);
    LastError = v7;
    goto LABEL_18;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  if ( !CreateProcessW(0, v5, 0, 0, 0, 0, 0, ppszPath, &StartupInfo, &ProcessInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x157,
                  (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                  v8);
    goto LABEL_7;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59319732>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59319732>::GetImpl'::`2'::impl) )
    UserOOBETelemetry::OobeCommandPromptLaunched();
  if ( !WaitForInputIdle(ProcessInformation.hProcess, 0xBB8u) )
  {
    lParam = ProcessInformation.dwProcessId;
    hWnd = 0;
    EnumWindows(lambda_59575e90c3231435483931bff83e0039_::_lambda_invoker_cdecl_, (LPARAM)&lParam);
    if ( hWnd )
      SetForegroundWindow(hWnd);
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathOut);
  LastError = 0;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  return LastError;
}

```

## disassembly

```asm
0x180025ca0  mov     [rsp-8+arg_0], rbx
0x180025ca5  push    rbp
0x180025ca6  push    rsi
0x180025ca7  push    rdi
0x180025ca8  lea     rbp, [rsp-47h]
0x180025cad  sub     rsp, 0F0h
0x180025cb4  xor     esi, esi
0x180025cb6  mov     [rbp+57h+ppszPath], rsi
0x180025cba  xor     edx, edx
0x180025cbc  lea     rcx, [rbp+57h+ppszPath]
0x180025cc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025cc5  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x180025cc9  xor     r8d, r8d; hToken
0x180025ccc  mov     edx, 5000h; dwFlags
0x180025cd1  lea     rcx, FOLDERID_System; rfid
0x180025cd8  call    cs:__imp_SHGetKnownFolderPath
0x180025cde  mov     ebx, eax
0x180025ce0  test    eax, eax
0x180025ce2  jns     short loc_180025D01
0x180025ce4  mov     rcx, [rbp+5Fh]; this
0x180025ce8  mov     r9d, eax; char *
0x180025ceb  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180025cf2  mov     edx, 14Dh; void *
0x180025cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025cfc  jmp     loc_180025E92
0x180025d01  mov     rdx, [rbp+57h+ppszPath]
0x180025d05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025d09  inc     rax
0x180025d0c  cmp     [rdx+rax*2], si
0x180025d10  jnz     short loc_180025D09
0x180025d12  lea     rdi, [rax+9]
0x180025d16  mov     r8, rdi
0x180025d19  lea     rcx, [rbp+57h+pszPathOut]
0x180025d1d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180025d22  nop
0x180025d23  mov     rbx, [rbp+57h+pszPathOut]
0x180025d27  test    rbx, rbx
0x180025d2a  jnz     short loc_180025D58
0x180025d2c  mov     rcx, [rbp+5Fh]; this
0x180025d30  mov     ebx, 8007000Eh
0x180025d35  mov     r9d, ebx; char *
0x180025d38  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180025d3f  mov     edx, 151h; void *
0x180025d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d49  nop
0x180025d4a  lea     rcx, [rbp+57h+pszPathOut]
0x180025d4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025d53  jmp     loc_180025E92
0x180025d58  lea     r9, pszMore; "cmd.exe"
0x180025d5f  mov     r8, [rbp+57h+ppszPath]; pszPathIn
0x180025d63  mov     rdx, rdi; cchPathOut
0x180025d66  mov     rcx, rbx; pszPathOut
0x180025d69  call    cs:__imp_PathCchCombine
0x180025d6f  mov     edi, eax
0x180025d71  test    eax, eax
0x180025d73  jns     short loc_180025D9E
0x180025d75  mov     rcx, [rbp+5Fh]; this
0x180025d79  mov     r9d, eax; char *
0x180025d7c  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180025d83  mov     edx, 152h; void *
0x180025d88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d8d  nop
0x180025d8e  lea     rcx, [rbp+57h+pszPathOut]
0x180025d92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025d97  mov     ebx, edi
0x180025d99  jmp     loc_180025E92
0x180025d9e  xorps   xmm0, xmm0
0x180025da1  xor     eax, eax
0x180025da3  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180025da7  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180025dab  mov     qword ptr [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180025db3  xor     edx, edx; Val
0x180025db5  lea     r8d, [rax+60h]; Size
0x180025db9  lea     rcx, [rbp+57h+StartupInfo.lpReserved]; void *
0x180025dbd  call    memset_0
0x180025dc2  mov     rax, [rbp+57h+ppszPath]
0x180025dc6  lea     rcx, [rbp+57h+ProcessInformation]
0x180025dca  mov     [rsp+100h+lpProcessInformation], rcx; lpProcessInformation
0x180025dcf  lea     rcx, [rbp+57h+StartupInfo]
0x180025dd3  mov     [rsp+100h+lpStartupInfo], rcx; lpStartupInfo
0x180025dd8  mov     [rsp+100h+lpCurrentDirectory], rax; lpCurrentDirectory
0x180025ddd  mov     [rsp+100h+lpEnvironment], rsi; lpEnvironment
0x180025de2  mov     [rsp+100h+dwCreationFlags], esi; dwCreationFlags
0x180025de6  mov     [rsp+100h+bInheritHandles], esi; bInheritHandles
0x180025dea  xor     r9d, r9d; lpThreadAttributes
0x180025ded  xor     r8d, r8d; lpProcessAttributes
0x180025df0  mov     rdx, rbx; lpCommandLine
0x180025df3  xor     ecx, ecx; lpApplicationName
0x180025df5  call    cs:__imp_CreateProcessW
0x180025dfb  test    eax, eax
0x180025dfd  jnz     short loc_180025E1B
0x180025dff  mov     rcx, [rbp+5Fh]; this
0x180025e03  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180025e0a  mov     edx, 157h; void *
0x180025e0f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025e14  mov     ebx, eax
0x180025e16  jmp     loc_180025D4A
0x180025e1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59319732@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59319732@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59319732> `wil::Feature<__WilFeatureTraits_Feature_59319732>::GetImpl(void)'::`2'::impl
0x180025e22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59319732@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59319732>::__private_IsEnabled(void)
0x180025e27  test    al, al
0x180025e29  jz      short loc_180025E30
0x180025e2b  call    ?OobeCommandPromptLaunched@UserOOBETelemetry@@SAXXZ; UserOOBETelemetry::OobeCommandPromptLaunched(void)
0x180025e30  mov     edx, 0BB8h; dwMilliseconds
0x180025e35  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x180025e39  call    cs:__imp_WaitForInputIdle
0x180025e3f  test    eax, eax
0x180025e41  jnz     short loc_180025E72
0x180025e43  mov     eax, [rbp+57h+ProcessInformation.dwProcessId]
0x180025e46  mov     dword ptr [rbp+57h+lParam], eax
0x180025e49  xor     eax, eax
0x180025e4b  mov     dword ptr [rbp+57h+lParam+4], eax
0x180025e4e  mov     [rbp+57h+hWnd], rsi
0x180025e52  lea     rdx, [rbp+57h+lParam]; lParam
0x180025e56  lea     rcx, _lambda_59575e90c3231435483931bff83e0039____lambda_invoker_cdecl_; lpEnumFunc
0x180025e5d  call    cs:__imp_EnumWindows
0x180025e63  mov     rcx, [rbp+57h+hWnd]; hWnd
0x180025e67  test    rcx, rcx
0x180025e6a  jz      short loc_180025E72
0x180025e6c  call    cs:__imp_SetForegroundWindow
0x180025e72  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180025e76  call    cs:__imp_CloseHandle
0x180025e7c  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180025e80  call    cs:__imp_CloseHandle
0x180025e86  nop
0x180025e87  lea     rcx, [rbp+57h+pszPathOut]
0x180025e8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025e90  mov     ebx, esi
0x180025e92  lea     rcx, [rbp+57h+ppszPath]
0x180025e96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025e9b  mov     eax, ebx
0x180025e9d  mov     rbx, [rsp+100h+arg_0]
0x180025ea5  add     rsp, 0F0h
0x180025eac  pop     rdi
0x180025ead  pop     rsi
0x180025eae  pop     rbp
0x180025eaf  retn
```
