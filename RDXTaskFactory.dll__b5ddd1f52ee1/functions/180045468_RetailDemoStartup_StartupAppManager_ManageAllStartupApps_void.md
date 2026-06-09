# RetailDemoStartup::StartupAppManager::ManageAllStartupApps(void)

- ea: `0x180045468`
- end: `0x180045821`
- name: `?ManageAllStartupApps@StartupAppManager@RetailDemoStartup@@QEAAJXZ`
- size: `953`
- prototype: `__int64 __fastcall(RetailDemoStartup::StartupAppManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ec40`

## callees

- `0x180003390`
- `0x180006450`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18000e3bc`
- `0x180010a60`
- `0x18002a8a4`
- `0x180030a64`
- `0x1800438a0`
- `0x180044a30`
- `0x1800453ac`
- `0x180045468`
- `0x180045ce4`
- `0x180045dc4`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18004559b`
- `SHLWAPI!PathFileExistsW` at `0x18004559b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004550e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004555c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004550e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004555c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800454bc`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800454bc`

## string_xrefs

- `0x1800454f6`: `Configuration`
- `0x1800454d3`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045525`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045573`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045640`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045548`: `StartupAppsAllowList.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RetailDemoStartup::StartupAppManager::ManageAllStartupApps(
        RetailDemoStartup::StartupAppManager *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  struct Windows::Data::Json::IJsonObject **v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int StartupItems; // eax
  __int64 v16; // r8
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // edi
  RetailDemoStartup::StartupAppInfo *v21; // rcx
  RetailDemoStartup::StartupAppInfo *v22; // rbx
  RetailDemoStartup::StartupAppInfo *v23; // rdx
  RetailDemoStartup::StartupAppInfo *v24; // r14
  char IsAppInAllowList; // si
  int v26; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v28[4]; // [rsp+28h] [rbp-270h] BYREF
  RetailDemoStartup::StartupAppInfo *v29[2]; // [rsp+30h] [rbp-268h] BYREF
  __int64 v30; // [rsp+40h] [rbp-258h]
  void *v31; // [rsp+48h] [rbp-250h] BYREF
  __int128 v32; // [rsp+50h] [rbp-248h]
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Configuration");
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = PathCchCombine(pszPathOut, 0x104u, pszPathOut, L"StartupAppsAllowList.json");
      v8 = v7;
      if ( v7 >= 0 )
      {
        if ( PathFileExistsW(pszPathOut) )
        {
          *(_QWORD *)v28 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28, v9, v10);
          RetailDemoUtil::GetJsonObjectFromFile(pszPathOut, v28, v11);
          if ( *(_QWORD *)v28 )
          {
            RetailDemoStartup::StartupAppManager::ParseAllowListFromJson(v13, &v31);
            *(_OWORD *)v29 = 0;
            v30 = 0;
            StartupItems = RetailDemoStartup::StartupAppManager::LoadStartupItems(v14, v29);
            v17 = StartupItems;
            if ( StartupItems >= 0 )
            {
              v20 = 0;
              v21 = v29[0];
              v22 = v29[0];
              v23 = v29[1];
              v24 = v29[1];
              while ( v22 != v24 )
              {
                IsAppInAllowList = RetailDemoStartup::StartupAppManager::IsAppInAllowList(v21, v22, &v31);
                v26 = RetailDemoStartup::StartupAppManager::ManageStartupItem(this, v22, IsAppInAllowList);
                if ( v26 < 0 )
                {
                  if ( v20 >= 0 )
                    v20 = v26;
                }
                else
                {
                  *((_BYTE *)v22 + 128) = IsAppInAllowList;
                }
                v22 = (RetailDemoStartup::StartupAppInfo *)((char *)v22 + 144);
                v23 = v29[1];
                v21 = v29[0];
              }
              if ( v21 )
              {
                std::_Destroy_range<std::allocator<RetailDemoStartup::StartupAppInfo>>(v21);
                std::_Deallocate<16>(v29[0], 16 * ((signed __int64)(v30 - (unsigned __int64)v29[0]) >> 4));
                *(_OWORD *)v29 = 0;
                v30 = 0;
              }
              if ( v31 )
              {
                std::_Destroy_range<std::allocator<std::wstring>>(v31, v32);
                std::_Deallocate<16>(v31, (*((_QWORD *)&v32 + 1) - (_QWORD)v31) & 0xFFFFFFFFFFFFFFE0uLL);
                v31 = 0;
                v32 = 0;
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28, v23, v16);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
              return (unsigned int)v20;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x231,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)StartupItems,
                (int)ppszPath);
              if ( v29[0] )
              {
                std::_Destroy_range<std::allocator<RetailDemoStartup::StartupAppInfo>>(v29[0]);
                std::_Deallocate<16>(v29[0], 16 * ((signed __int64)(v30 - (unsigned __int64)v29[0]) >> 4));
                *(_OWORD *)v29 = 0;
                v30 = 0;
              }
              if ( v31 )
              {
                std::_Destroy_range<std::allocator<std::wstring>>(v31, v32);
                std::_Deallocate<16>(v31, (*((_QWORD *)&v32 + 1) - (_QWORD)v31) & 0xFFFFFFFFFFFFFFE0uLL);
                v31 = 0;
                v32 = 0;
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28, v18, v19);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
              return v17;
            }
          }
          else
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28, v12, 0);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
            return 2147500037LL;
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
          return 2147500037LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
          (const char *)(unsigned int)v7,
          (int)ppszPath);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
        (const char *)(unsigned int)v5,
        (int)ppszPath);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
      (const char *)(unsigned int)v2,
      (int)ppszPath);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v3;
  }
}

```

## disassembly

```asm
0x180045468  mov     [rsp+arg_8], rbx
0x18004546d  mov     [rsp+arg_10], rsi
0x180045472  push    rdi
0x180045473  push    r14
0x180045475  push    r15
0x180045477  sub     rsp, 280h
0x18004547e  mov     rax, cs:__security_cookie
0x180045485  xor     rax, rsp
0x180045488  mov     [rsp+298h+var_28], rax
0x180045490  mov     r15, rcx
0x180045493  mov     [rsp+298h+ppszPath], 0; int
0x18004549c  xor     edx, edx
0x18004549e  lea     rcx, [rsp+298h+ppszPath]
0x1800454a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800454a8  lea     r9, [rsp+298h+ppszPath]; ppszPath
0x1800454ad  xor     r8d, r8d; hToken
0x1800454b0  mov     edx, 5000h; dwFlags
0x1800454b5  lea     rcx, FOLDERID_RetailDemo; rfid
0x1800454bc  call    cs:__imp_SHGetKnownFolderPath
0x1800454c2  mov     ebx, eax
0x1800454c4  test    eax, eax
0x1800454c6  jns     short loc_1800454F6
0x1800454c8  mov     rcx, [rsp+298h]; this
0x1800454d0  mov     r9d, eax; char *
0x1800454d3  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800454da  mov     edx, 21Bh; void *
0x1800454df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800454e4  nop
0x1800454e5  lea     rcx, [rsp+298h+ppszPath]
0x1800454ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800454ef  mov     eax, ebx
0x1800454f1  jmp     loc_1800457F7
0x1800454f6  lea     r9, aConfiguration; "Configuration"
0x1800454fd  mov     r8, [rsp+298h+ppszPath]; pszPathIn
0x180045502  mov     edi, 104h
0x180045507  mov     edx, edi; cchPathOut
0x180045509  lea     rcx, [rsp+298h+pszPathOut]; pszPathOut
0x18004550e  call    cs:__imp_PathCchCombine
0x180045514  mov     ebx, eax
0x180045516  test    eax, eax
0x180045518  jns     short loc_180045548
0x18004551a  mov     rcx, [rsp+298h]; this
0x180045522  mov     r9d, eax; char *
0x180045525  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004552c  mov     edx, 21Dh; void *
0x180045531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045536  nop
0x180045537  lea     rcx, [rsp+298h+ppszPath]
0x18004553c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180045541  mov     eax, ebx
0x180045543  jmp     loc_1800457F7
0x180045548  lea     r9, aStartupappsall; "StartupAppsAllowList.json"
0x18004554f  lea     r8, [rsp+298h+pszPathOut]; pszPathIn
0x180045554  mov     rdx, rdi; cchPathOut
0x180045557  lea     rcx, [rsp+298h+pszPathOut]; pszPathOut
0x18004555c  call    cs:__imp_PathCchCombine
0x180045562  mov     ebx, eax
0x180045564  test    eax, eax
0x180045566  jns     short loc_180045596
0x180045568  mov     rcx, [rsp+298h]; this
0x180045570  mov     r9d, eax; char *
0x180045573  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004557a  mov     edx, 21Eh; void *
0x18004557f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045584  nop
0x180045585  lea     rcx, [rsp+298h+ppszPath]
0x18004558a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004558f  mov     eax, ebx
0x180045591  jmp     loc_1800457F7
0x180045596  lea     rcx, [rsp+298h+pszPathOut]; pszPath
0x18004559b  call    cs:__imp_PathFileExistsW
0x1800455a1  test    eax, eax
0x1800455a3  jnz     short loc_1800455B9
0x1800455a5  lea     rcx, [rsp+298h+ppszPath]
0x1800455aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800455af  mov     eax, 80004005h
0x1800455b4  jmp     loc_1800457F7
0x1800455b9  mov     qword ptr [rsp+298h+var_270], 0
0x1800455c2  lea     rcx, [rsp+298h+var_270]
0x1800455c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800455cc  lea     rdx, [rsp+298h+var_270]; unsigned __int16 *
0x1800455d1  lea     rcx, [rsp+298h+pszPathOut]; this
0x1800455d6  call    ?GetJsonObjectFromFile@RetailDemoUtil@@YAXPEBGPEAPEAUIJsonObject@Json@Data@Windows@@@Z; RetailDemoUtil::GetJsonObjectFromFile(ushort const *,Windows::Data::Json::IJsonObject * *)
0x1800455db  mov     r8, qword ptr [rsp+298h+var_270]
0x1800455e0  test    r8, r8
0x1800455e3  jnz     short loc_180045604
0x1800455e5  lea     rcx, [rsp+298h+var_270]
0x1800455ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800455ef  nop
0x1800455f0  lea     rcx, [rsp+298h+ppszPath]
0x1800455f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800455fa  mov     eax, 80004005h
0x1800455ff  jmp     loc_1800457F7
0x180045604  lea     rdx, [rsp+298h+var_250]
0x180045609  call    ?ParseAllowListFromJson@StartupAppManager@RetailDemoStartup@@AEAA?AV?$vector@UAllowedAppInfo@RetailDemoStartup@@V?$allocator@UAllowedAppInfo@RetailDemoStartup@@@std@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z; RetailDemoStartup::StartupAppManager::ParseAllowListFromJson(Windows::Data::Json::IJsonObject *)
0x18004560e  nop
0x18004560f  xorps   xmm0, xmm0
0x180045612  movdqu  xmmword ptr [rsp+298h+var_268], xmm0
0x180045618  mov     [rsp+298h+var_258], 0
0x180045621  lea     rdx, [rsp+298h+var_268]
0x180045626  call    ?LoadStartupItems@StartupAppManager@RetailDemoStartup@@AEAAJAEAV?$vector@UStartupAppInfo@RetailDemoStartup@@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@@Z; RetailDemoStartup::StartupAppManager::LoadStartupItems(std::vector<RetailDemoStartup::StartupAppInfo> &)
0x18004562b  mov     ebx, eax
0x18004562d  test    eax, eax
0x18004562f  jns     loc_1800456FC
0x180045635  mov     rcx, [rsp+298h]; this
0x18004563d  mov     r9d, eax; char *
0x180045640  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180045647  mov     edx, 231h; void *
0x18004564c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045651  nop
0x180045652  mov     rcx, [rsp+298h+var_268]; this
0x180045657  test    rcx, rcx
0x18004565a  jz      short loc_1800456A4
0x18004565c  mov     rdx, [rsp+298h+var_268+8]
0x180045661  call    ??$_Destroy_range@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@YAXPEAUStartupAppInfo@RetailDemoStartup@@QEAU12@AEAV?$allocator@UStartupAppInfo@RetailDemoStartup@@@0@@Z; std::_Destroy_range<std::allocator<RetailDemoStartup::StartupAppInfo>>(RetailDemoStartup::StartupAppInfo *,RetailDemoStartup::StartupAppInfo * const,std::allocator<RetailDemoStartup::StartupAppInfo> &)
0x180045666  mov     rcx, [rsp+298h+var_268]
0x18004566b  mov     rax, [rsp+298h+var_258]
0x180045670  sub     rax, rcx
0x180045673  sar     rax, 4
0x180045677  mov     rdx, 8E38E38E38E38E39h
0x180045681  imul    rax, rdx
0x180045685  lea     rdx, [rax+rax*8]
0x180045689  shl     rdx, 4
0x18004568d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180045692  xorps   xmm0, xmm0
0x180045695  movdqu  xmmword ptr [rsp+298h+var_268], xmm0
0x18004569b  mov     [rsp+298h+var_258], 0
0x1800456a4  mov     rcx, [rsp+298h+var_250]
0x1800456a9  test    rcx, rcx
0x1800456ac  jz      short loc_1800456E0
0x1800456ae  mov     rdx, qword ptr [rsp+298h+var_248]
0x1800456b3  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800456b8  mov     rcx, [rsp+298h+var_250]
0x1800456bd  mov     rdx, qword ptr [rsp+298h+var_248+8]
0x1800456c2  sub     rdx, rcx
0x1800456c5  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800456c9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800456ce  mov     [rsp+298h+var_250], 0
0x1800456d7  xorps   xmm0, xmm0
0x1800456da  movdqu  [rsp+298h+var_248], xmm0
0x1800456e0  lea     rcx, [rsp+298h+var_270]
0x1800456e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800456ea  nop
0x1800456eb  lea     rcx, [rsp+298h+ppszPath]
0x1800456f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800456f5  mov     eax, ebx
0x1800456f7  jmp     loc_1800457F7
0x1800456fc  xor     edi, edi
0x1800456fe  mov     rcx, [rsp+298h+var_268]; this
0x180045703  mov     rbx, rcx
0x180045706  mov     rdx, [rsp+298h+var_268+8]
0x18004570b  mov     r14, rdx
0x18004570e  cmp     rbx, r14
0x180045711  jz      short loc_180045756
0x180045713  lea     r8, [rsp+298h+var_250]
0x180045718  mov     rdx, rbx
0x18004571b  call    ?IsAppInAllowList@StartupAppManager@RetailDemoStartup@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@UAllowedAppInfo@RetailDemoStartup@@V?$allocator@UAllowedAppInfo@RetailDemoStartup@@@std@@@4@@Z; RetailDemoStartup::StartupAppManager::IsAppInAllowList(std::wstring const &,std::vector<RetailDemoStartup::AllowedAppInfo> const &)
0x180045720  mov     sil, al
0x180045723  mov     r8b, al; bool
0x180045726  mov     rdx, rbx; struct RetailDemoStartup::StartupAppInfo *
0x180045729  mov     rcx, r15; this
0x18004572c  call    ?ManageStartupItem@StartupAppManager@RetailDemoStartup@@AEAAJAEBUStartupAppInfo@2@_N@Z; RetailDemoStartup::StartupAppManager::ManageStartupItem(RetailDemoStartup::StartupAppInfo const &,bool)
0x180045731  test    eax, eax
0x180045733  js      short loc_18004573E
0x180045735  mov     [rbx+80h], sil
0x18004573c  jmp     short loc_180045743
0x18004573e  test    edi, edi
0x180045740  cmovns  edi, eax
0x180045743  add     rbx, 90h
0x18004574a  mov     rdx, [rsp+298h+var_268+8]
0x18004574f  mov     rcx, [rsp+298h+var_268]
0x180045754  jmp     short loc_18004570E
0x180045756  test    rcx, rcx
0x180045759  jz      short loc_18004579E
0x18004575b  call    ??$_Destroy_range@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@YAXPEAUStartupAppInfo@RetailDemoStartup@@QEAU12@AEAV?$allocator@UStartupAppInfo@RetailDemoStartup@@@0@@Z; std::_Destroy_range<std::allocator<RetailDemoStartup::StartupAppInfo>>(RetailDemoStartup::StartupAppInfo *,RetailDemoStartup::StartupAppInfo * const,std::allocator<RetailDemoStartup::StartupAppInfo> &)
0x180045760  mov     rcx, [rsp+298h+var_268]
0x180045765  mov     rax, [rsp+298h+var_258]
0x18004576a  sub     rax, rcx
0x18004576d  sar     rax, 4
0x180045771  mov     rdx, 8E38E38E38E38E39h
0x18004577b  imul    rax, rdx
0x18004577f  lea     rdx, [rax+rax*8]
0x180045783  shl     rdx, 4
0x180045787  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004578c  xorps   xmm0, xmm0
0x18004578f  movdqu  xmmword ptr [rsp+298h+var_268], xmm0
0x180045795  mov     [rsp+298h+var_258], 0
0x18004579e  mov     rcx, [rsp+298h+var_250]
0x1800457a3  test    rcx, rcx
0x1800457a6  jz      short loc_1800457DA
0x1800457a8  mov     rdx, qword ptr [rsp+298h+var_248]
0x1800457ad  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800457b2  mov     rcx, [rsp+298h+var_250]
0x1800457b7  mov     rdx, qword ptr [rsp+298h+var_248+8]
0x1800457bc  sub     rdx, rcx
0x1800457bf  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800457c3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800457c8  mov     [rsp+298h+var_250], 0
0x1800457d1  xorps   xmm0, xmm0
0x1800457d4  movdqu  [rsp+298h+var_248], xmm0
0x1800457da  lea     rcx, [rsp+298h+var_270]
0x1800457df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800457e4  nop
0x1800457e5  lea     rcx, [rsp+298h+ppszPath]
0x1800457ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800457ef  mov     eax, edi
0x1800457f1  jmp     short loc_1800457F7
0x1800457f3  mov     eax, dword ptr [rsp+298h+ppszPath]
0x1800457f7  mov     rcx, [rsp+298h+var_28]
0x1800457ff  xor     rcx, rsp; StackCookie
0x180045802  call    __security_check_cookie
0x180045807  lea     r11, [rsp+298h+var_18]
0x18004580f  mov     rbx, [r11+28h]
0x180045813  mov     rsi, [r11+30h]
0x180045817  mov     rsp, r11
0x18004581a  pop     r15
0x18004581c  pop     r14
0x18004581e  pop     rdi
0x18004581f  retn
```
