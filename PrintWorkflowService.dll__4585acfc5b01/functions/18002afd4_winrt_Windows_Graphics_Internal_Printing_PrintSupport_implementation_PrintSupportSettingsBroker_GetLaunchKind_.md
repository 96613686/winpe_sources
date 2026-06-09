# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetLaunchKind(void)

- ea: `0x18002afd4`
- end: `0x18002b18b`
- name: `?GetLaunchKind@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AW4SettingsLaunchKindPriv@345678@XZ`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002afa0`

## callees

- `0x1800097ec`
- `0x1800127a4`
- `0x1800166a8`
- `0x180023664`
- `0x1800253ec`
- `0x180028550`
- `0x18002aed8`
- `0x18002afd4`
- `0x18002c1a4`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b010`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b010`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b0fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b0fb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002b07d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002b07d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002b0da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002b0da`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18002b02b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18002b02b`

## string_xrefs

- `0x18002b134`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b14c`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b15e`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b179`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b0cb`: `rundll32.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetLaunchKind(
        __int64 a1)
{
  DWORD v2; // r8d
  char *v3; // rax
  __int64 v4; // rdx
  int v5; // eax
  const WCHAR *FileNameW; // rsi
  __int64 v7; // rdi
  unsigned int v8; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  LPCWCH lpString2[4]; // [rsp+30h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD dwProcessId; // [rsp+78h] [rbp+28h] BYREF
  LPCWSTR pszPath; // [rsp+80h] [rbp+30h] BYREF
  char *v15; // [rsp+88h] [rbp+38h] BYREF

  if ( !*(_BYTE *)(a1 + 216) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
      (const char *)0x8000000ELL,
      bIgnoreCase);
  dwProcessId = 0;
  LODWORD(pszPath) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &pszPath, 0);
  if ( (((_DWORD)pszPath - 14) & 0xFFFFFFFD) != 0 )
  {
    GetWindowThreadProcessId(*(HWND *)(a1 + 104), &dwProcessId);
    v2 = dwProcessId;
    if ( !dwProcessId )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
        (const char *)0x8000FFFFLL,
        bIgnoreCase);
  }
  else
  {
    LODWORD(pszPath) = *(_DWORD *)(a1 + 104);
    winrt::Windows::Internal::ApplicationModel::WindowManagement::Window::GetFromId((const struct winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId *)&v15);
    dwProcessId = winrt::impl::consume_Windows_Internal_ApplicationModel_WindowManagement_IWindow<winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow>::ProcessId(&v15);
    winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v15);
    v2 = dwProcessId;
  }
  v3 = (char *)OpenProcess(0x1000u, 0, v2);
  v15 = v3;
  if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
      (const char *)retaddr);
  pszPath = 0;
  v5 = wil::QueryFullProcessImageNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         (__int64)v3,
         v4,
         (__int64)&pszPath);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  lpString2[0] = L"systemsettings.exe";
  lpString2[1] = L"explorer.exe";
  lpString2[2] = L"rundll32.exe";
  FileNameW = PathFindFileNameW(pszPath);
  v7 = 0;
  v8 = 1;
  while ( CompareStringOrdinal(FileNameW, -1, lpString2[v7], -1, 1) != 2 )
  {
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= 3 )
    {
      v8 = 0;
      break;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  return v8;
}

```

## disassembly

```asm
0x18002afd4  mov     [rsp-18h+arg_0], rbx
0x18002afd9  push    rbp
0x18002afda  push    rsi
0x18002afdb  push    rdi
0x18002afdc  mov     rbp, rsp
0x18002afdf  sub     rsp, 50h
0x18002afe3  mov     rbx, rcx
0x18002afe6  mov     al, [rcx+0D8h]
0x18002afec  nop
0x18002afed  mov     rcx, [rbp+18h]; this
0x18002aff1  test    al, al
0x18002aff3  jz      loc_18002B173
0x18002aff9  mov     [rbp+dwProcessId], 0
0x18002b000  mov     dword ptr [rbp+pszPath], 0
0x18002b007  xor     r8d, r8d
0x18002b00a  lea     rdx, [rbp+pszPath]
0x18002b00e  xor     ecx, ecx
0x18002b010  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18002b016  mov     eax, dword ptr [rbp+pszPath]
0x18002b019  add     eax, 0FFFFFFF2h
0x18002b01c  test    eax, 0FFFFFFFDh
0x18002b021  jz      short loc_18002B049
0x18002b023  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18002b027  mov     rcx, [rbx+68h]; hWnd
0x18002b02b  call    cs:__imp_GetWindowThreadProcessId
0x18002b031  mov     r8d, [rbp+dwProcessId]
0x18002b035  test    r8d, r8d
0x18002b038  setnz   al
0x18002b03b  mov     rcx, [rbp+18h]; this
0x18002b03f  test    al, al
0x18002b041  jz      loc_18002B146
0x18002b047  jmp     short loc_18002B076
0x18002b049  mov     eax, [rbx+68h]
0x18002b04c  mov     dword ptr [rbp+pszPath], eax
0x18002b04f  lea     rdx, [rbp+pszPath]
0x18002b053  lea     rcx, [rbp+arg_18]; struct winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId *
0x18002b057  call    ?GetFromId@Window@WindowManagement@ApplicationModel@Internal@Windows@winrt@@SA@AEBUWindowId@23456@@Z; winrt::Windows::Internal::ApplicationModel::WindowManagement::Window::GetFromId(winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId const &)
0x18002b05c  nop
0x18002b05d  lea     rcx, [rbp+arg_18]
0x18002b061  call    ?ProcessId@?$consume_Windows_Internal_ApplicationModel_WindowManagement_IWindow@UIWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_ApplicationModel_WindowManagement_IWindow<winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow>::ProcessId(void)
0x18002b066  mov     [rbp+dwProcessId], eax
0x18002b069  lea     rcx, [rbp+arg_18]; this
0x18002b06d  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18002b072  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18002b076  xor     edx, edx; bInheritHandle
0x18002b078  mov     ecx, 1000h; dwDesiredAccess
0x18002b07d  call    cs:__imp_OpenProcess
0x18002b083  mov     [rbp+arg_18], rax
0x18002b087  mov     r9, [rbp+18h]; char *
0x18002b08b  lea     rcx, [rax-1]
0x18002b08f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002b093  ja      loc_18002B15E
0x18002b099  mov     [rbp+pszPath], 0
0x18002b0a1  lea     r8, [rbp+pszPath]
0x18002b0a5  mov     rcx, rax
0x18002b0a8  call    ??$QueryFullProcessImageNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::QueryFullProcessImageNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002b0ad  mov     rcx, [rbp+18h]; this
0x18002b0b1  test    eax, eax
0x18002b0b3  js      short loc_18002B131
0x18002b0b5  lea     rax, aSystemsettings; "systemsettings.exe"
0x18002b0bc  mov     [rbp+lpString2], rax
0x18002b0c0  lea     rax, aExplorerExe; "explorer.exe"
0x18002b0c7  mov     [rbp+var_18], rax
0x18002b0cb  lea     rax, aRundll32Exe; "rundll32.exe"
0x18002b0d2  mov     [rbp+var_10], rax
0x18002b0d6  mov     rcx, [rbp+pszPath]; pszPath
0x18002b0da  call    cs:__imp_PathFindFileNameW
0x18002b0e0  mov     rsi, rax
0x18002b0e3  xor     edi, edi
0x18002b0e5  lea     ebx, [rdi+1]
0x18002b0e8  mov     [rsp+50h+bIgnoreCase], ebx; bIgnoreCase
0x18002b0ec  or      r9d, 0FFFFFFFFh; cchCount2
0x18002b0f0  mov     r8, [rbp+rdi*8+lpString2]; lpString2
0x18002b0f5  or      edx, r9d; cchCount1
0x18002b0f8  mov     rcx, rsi; lpString1
0x18002b0fb  call    cs:__imp_CompareStringOrdinal
0x18002b101  cmp     eax, 2
0x18002b104  jz      short loc_18002B10F
0x18002b106  add     edi, ebx
0x18002b108  cmp     edi, 3
0x18002b10b  jb      short loc_18002B0E8
0x18002b10d  xor     ebx, ebx
0x18002b10f  lea     rcx, [rbp+pszPath]
0x18002b113  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b118  nop
0x18002b119  lea     rcx, [rbp+arg_18]
0x18002b11d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b122  mov     eax, ebx
0x18002b124  mov     rbx, [rsp+50h+arg_0]
0x18002b129  add     rsp, 50h
0x18002b12d  pop     rdi
0x18002b12e  pop     rsi
0x18002b12f  pop     rbp
0x18002b130  retn
0x18002b131  mov     r9d, eax; char *
0x18002b134  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b13b  mov     edx, 1AFh; void *
0x18002b140  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b146  mov     r9d, 8000FFFFh; char *
0x18002b14c  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b153  mov     edx, 1A6h; void *
0x18002b158  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b15e  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b165  mov     edx, 1ABh; void *
0x18002b16a  mov     rcx, r9; this
0x18002b16d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b173  mov     r9d, 8000000Eh; char *
0x18002b179  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b180  mov     edx, 19Ah; void *
0x18002b185  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
