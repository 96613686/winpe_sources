# RetailDemoUserAgent::TerminateAppsInDMSInclusionList(void)

- ea: `0x1800412d0`
- end: `0x1800415bf`
- name: `?TerminateAppsInDMSInclusionList@RetailDemoUserAgent@@AEAAXXZ`
- size: `751`
- prototype: `void __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180039b80`

## callees

- `0x180003390`
- `0x180003e00`
- `0x180006450`
- `0x180008bbc`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180022ad8`
- `0x180030a64`
- `0x180035174`
- `0x18003e0fc`
- `0x18003f074`
- `0x1800412d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800414e2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800414e2`
- `SHLWAPI!PathFileExistsW` at `0x180041397`
- `SHLWAPI!PathFileExistsW` at `0x180041397`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180041347`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180041379`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180041347`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180041379`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180041499`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180041499`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1800414bd`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1800414bd`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800414fa`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800414fa`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180041463`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180041463`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041318`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041318`

## string_xrefs

- `0x18004132e`: `Configuration`
- `0x180041584`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180041598`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800415ac`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18004135d`: `ProcessCloseInclusionList.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RetailDemoUserAgent::TerminateAppsInDMSInclusionList(RetailDemoUserAgent *this)
{
  HRESULT v1; // eax
  HRESULT v2; // eax
  HRESULT v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  struct Windows::Data::Json::IJsonObject **v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  HANDLE Toolhelp32Snapshot; // rdi
  HANDLE v13; // rax
  void *v14; // rbx
  PWSTR ppszPath; // [rsp+20h] [rbp-6B8h] BYREF
  unsigned __int16 v16[4]; // [rsp+28h] [rbp-6B0h] BYREF
  WifiSetting *v17; // [rsp+30h] [rbp-6A8h] BYREF
  __int128 v18; // [rsp+38h] [rbp-6A0h]
  HANDLE v19; // [rsp+48h] [rbp-690h] BYREF
  HANDLE v20[2]; // [rsp+50h] [rbp-688h] BYREF
  PROCESSENTRY32W pe; // [rsp+60h] [rbp-678h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2A0h] [rbp-438h] BYREF
  WCHAR ImageFileName[264]; // [rsp+4B0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+0h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v1 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C0,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v1,
        (int)ppszPath);
    v2 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Configuration");
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C2,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v2,
        (int)ppszPath);
    v3 = PathCchCombine(pszPathOut, 0x104u, pszPathOut, L"ProcessCloseInclusionList.json");
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C3,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v3,
        (int)ppszPath);
    if ( PathFileExistsW(pszPathOut) )
    {
      *(_QWORD *)v16 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16, v4, v5);
      RetailDemoUtil::GetJsonObjectFromFile((RetailDemoUtil *)pszPathOut, v16, v7);
      if ( *(_QWORD *)v16 )
      {
        RetailDemoUserAgent::ParseProcessListFromJson(v9, &v17);
        v11 = v18;
        if ( v17 == (WifiSetting *)v18 )
        {
          if ( v17 )
          {
            std::_Destroy_range<std::allocator<ProcessInfo>>(v17);
            std::_Deallocate<16>(v17, (*((_QWORD *)&v18 + 1) - (_QWORD)v17) & 0xFFFFFFFFFFFFFFC0uLL);
            v17 = 0;
            v18 = 0;
          }
        }
        else
        {
          Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
          v20[0] = Toolhelp32Snapshot;
          memset_0(&pe.cntUsage, 0, 0x234u);
          pe.dwSize = 568;
          while ( Process32NextW(Toolhelp32Snapshot, &pe) )
          {
            v13 = OpenProcess(0x401u, 0, pe.th32ProcessID);
            v14 = v13;
            v19 = v13;
            if ( v13
              && K32GetProcessImageFileNameW(v13, ImageFileName, 0x104u)
              && (unsigned __int8)RetailDemoUserAgent::IsProcessInProcessInfoList(&v17, ImageFileName) )
            {
              TerminateProcess(v14, 0);
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
          }
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
          if ( v17 )
          {
            std::_Destroy_range<std::allocator<ProcessInfo>>(v17);
            std::_Deallocate<16>(v17, (*((_QWORD *)&v18 + 1) - (_QWORD)v17) & 0xFFFFFFFFFFFFFFC0uLL);
            v17 = 0;
            v18 = 0;
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16, v11, v10);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      }
      else
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16, v8, 0);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x5F3,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x1800412d0  mov     [rsp+arg_0], rbx
0x1800412d5  push    rdi
0x1800412d6  sub     rsp, 6D0h
0x1800412dd  mov     rax, cs:__security_cookie
0x1800412e4  xor     rax, rsp
0x1800412e7  mov     [rsp+6D8h+var_18], rax
0x1800412ef  mov     [rsp+6D8h+ppszPath], 0; int
0x1800412f8  xor     edx, edx
0x1800412fa  lea     rcx, [rsp+6D8h+ppszPath]
0x1800412ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180041304  lea     r9, [rsp+6D8h+ppszPath]; ppszPath
0x180041309  xor     r8d, r8d; hToken
0x18004130c  mov     edx, 5000h; dwFlags
0x180041311  lea     rcx, FOLDERID_RetailDemo; rfid
0x180041318  call    cs:__imp_SHGetKnownFolderPath
0x18004131e  mov     rcx, [rsp+6D8h]; this
0x180041326  test    eax, eax
0x180041328  js      loc_180041581
0x18004132e  lea     r9, aConfiguration; "Configuration"
0x180041335  mov     r8, [rsp+6D8h+ppszPath]; pszPathIn
0x18004133a  mov     edx, 104h; cchPathOut
0x18004133f  lea     rcx, [rsp+6D8h+pszPathOut]; pszPathOut
0x180041347  call    cs:__imp_PathCchCombine
0x18004134d  mov     rcx, [rsp+6D8h]; this
0x180041355  test    eax, eax
0x180041357  js      loc_180041595
0x18004135d  lea     r9, aProcessclosein; "ProcessCloseInclusionList.json"
0x180041364  lea     r8, [rsp+6D8h+pszPathOut]; pszPathIn
0x18004136c  mov     edx, 104h; cchPathOut
0x180041371  lea     rcx, [rsp+6D8h+pszPathOut]; pszPathOut
0x180041379  call    cs:__imp_PathCchCombine
0x18004137f  mov     rcx, [rsp+6D8h]; this
0x180041387  test    eax, eax
0x180041389  js      loc_1800415A9
0x18004138f  lea     rcx, [rsp+6D8h+pszPathOut]; pszPath
0x180041397  call    cs:__imp_PathFileExistsW
0x18004139d  test    eax, eax
0x18004139f  jnz     short loc_1800413B0
0x1800413a1  lea     rcx, [rsp+6D8h+ppszPath]
0x1800413a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800413ab  jmp     loc_180041560
0x1800413b0  mov     qword ptr [rsp+6D8h+var_6B0], 0
0x1800413b9  lea     rcx, [rsp+6D8h+var_6B0]
0x1800413be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800413c3  lea     rdx, [rsp+6D8h+var_6B0]; unsigned __int16 *
0x1800413c8  lea     rcx, [rsp+6D8h+pszPathOut]; this
0x1800413d0  call    ?GetJsonObjectFromFile@RetailDemoUtil@@YAXPEBGPEAPEAUIJsonObject@Json@Data@Windows@@@Z; RetailDemoUtil::GetJsonObjectFromFile(ushort const *,Windows::Data::Json::IJsonObject * *)
0x1800413d5  mov     r8, qword ptr [rsp+6D8h+var_6B0]
0x1800413da  test    r8, r8
0x1800413dd  jnz     short loc_1800413F9
0x1800413df  lea     rcx, [rsp+6D8h+var_6B0]
0x1800413e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800413e9  nop
0x1800413ea  lea     rcx, [rsp+6D8h+ppszPath]
0x1800413ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800413f4  jmp     loc_180041560
0x1800413f9  lea     rdx, [rsp+6D8h+var_6A8]
0x1800413fe  call    ?ParseProcessListFromJson@RetailDemoUserAgent@@AEAA?AV?$vector@UProcessInfo@@V?$allocator@UProcessInfo@@@std@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z; RetailDemoUserAgent::ParseProcessListFromJson(Windows::Data::Json::IJsonObject *)
0x180041403  mov     rdx, qword ptr [rsp+6D8h+var_6A0]
0x180041408  mov     rcx, [rsp+6D8h+var_6A8]; this
0x18004140d  cmp     rcx, rdx
0x180041410  jnz     short loc_18004145E
0x180041412  test    rcx, rcx
0x180041415  jz      short loc_180041444
0x180041417  call    ??$_Destroy_range@V?$allocator@UProcessInfo@@@std@@@std@@YAXPEAUProcessInfo@@QEAU1@AEAV?$allocator@UProcessInfo@@@0@@Z; std::_Destroy_range<std::allocator<ProcessInfo>>(ProcessInfo *,ProcessInfo * const,std::allocator<ProcessInfo> &)
0x18004141c  mov     rcx, [rsp+6D8h+var_6A8]
0x180041421  mov     rdx, qword ptr [rsp+6D8h+var_6A0+8]
0x180041426  sub     rdx, rcx
0x180041429  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18004142d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041432  mov     [rsp+6D8h+var_6A8], 0
0x18004143b  xorps   xmm0, xmm0
0x18004143e  movdqu  [rsp+6D8h+var_6A0], xmm0
0x180041444  lea     rcx, [rsp+6D8h+var_6B0]
0x180041449  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004144e  nop
0x18004144f  lea     rcx, [rsp+6D8h+ppszPath]
0x180041454  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041459  jmp     loc_180041560
0x18004145e  xor     edx, edx; th32ProcessID
0x180041460  lea     ecx, [rdx+2]; dwFlags
0x180041463  call    cs:__imp_CreateToolhelp32Snapshot
0x180041469  mov     rdi, rax
0x18004146c  mov     [rsp+6D8h+var_688], rax
0x180041471  xor     edx, edx; Val
0x180041473  mov     r8d, 234h; Size
0x180041479  lea     rcx, [rsp+6D8h+pe.cntUsage]; void *
0x18004147e  call    memset_0
0x180041483  mov     [rsp+6D8h+pe.dwSize], 238h
0x18004148b  jmp     short loc_1800414F2
0x18004148d  mov     r8d, [rsp+6D8h+pe.th32ProcessID]; dwProcessId
0x180041492  xor     edx, edx; bInheritHandle
0x180041494  mov     ecx, 401h; dwDesiredAccess
0x180041499  call    cs:__imp_OpenProcess
0x18004149f  mov     rbx, rax
0x1800414a2  mov     [rsp+6D8h+var_690], rax
0x1800414a7  test    rax, rax
0x1800414aa  jz      short loc_1800414E8
0x1800414ac  mov     r8d, 104h; nSize
0x1800414b2  lea     rdx, [rsp+6D8h+ImageFileName]; lpImageFileName
0x1800414ba  mov     rcx, rax; hProcess
0x1800414bd  call    cs:__imp_K32GetProcessImageFileNameW
0x1800414c3  test    eax, eax
0x1800414c5  jz      short loc_1800414E8
0x1800414c7  lea     rdx, [rsp+6D8h+ImageFileName]
0x1800414cf  lea     rcx, [rsp+6D8h+var_6A8]
0x1800414d4  call    ?IsProcessInProcessInfoList@RetailDemoUserAgent@@CA_NAEBV?$vector@UProcessInfo@@V?$allocator@UProcessInfo@@@std@@@std@@PEBG@Z; RetailDemoUserAgent::IsProcessInProcessInfoList(std::vector<ProcessInfo> const &,ushort const *)
0x1800414d9  test    al, al
0x1800414db  jz      short loc_1800414E8
0x1800414dd  xor     edx, edx; uExitCode
0x1800414df  mov     rcx, rbx; hProcess
0x1800414e2  call    cs:__imp_TerminateProcess
0x1800414e8  lea     rcx, [rsp+6D8h+var_690]
0x1800414ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800414f2  lea     rdx, [rsp+6D8h+pe]; lppe
0x1800414f7  mov     rcx, rdi; hSnapshot
0x1800414fa  call    cs:__imp_Process32NextW
0x180041500  test    eax, eax
0x180041502  jnz     short loc_18004148D
0x180041504  lea     rcx, [rsp+6D8h+var_688]
0x180041509  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004150e  mov     rcx, [rsp+6D8h+var_6A8]; this
0x180041513  test    rcx, rcx
0x180041516  jz      short loc_18004154A
0x180041518  mov     rdx, qword ptr [rsp+6D8h+var_6A0]
0x18004151d  call    ??$_Destroy_range@V?$allocator@UProcessInfo@@@std@@@std@@YAXPEAUProcessInfo@@QEAU1@AEAV?$allocator@UProcessInfo@@@0@@Z; std::_Destroy_range<std::allocator<ProcessInfo>>(ProcessInfo *,ProcessInfo * const,std::allocator<ProcessInfo> &)
0x180041522  mov     rcx, [rsp+6D8h+var_6A8]
0x180041527  mov     rdx, qword ptr [rsp+6D8h+var_6A0+8]
0x18004152c  sub     rdx, rcx
0x18004152f  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180041533  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041538  mov     [rsp+6D8h+var_6A8], 0
0x180041541  xorps   xmm0, xmm0
0x180041544  movdqu  [rsp+6D8h+var_6A0], xmm0
0x18004154a  lea     rcx, [rsp+6D8h+var_6B0]
0x18004154f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041554  nop
0x180041555  lea     rcx, [rsp+6D8h+ppszPath]
0x18004155a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004155f  nop
0x180041560  mov     rcx, [rsp+6D8h+var_18]
0x180041568  xor     rcx, rsp; StackCookie
0x18004156b  call    __security_check_cookie
0x180041570  mov     rbx, [rsp+6D8h+arg_0]
0x180041578  add     rsp, 6D0h
0x18004157f  pop     rdi
0x180041580  retn
0x180041581  mov     r9d, eax; char *
0x180041584  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004158b  mov     edx, 5C0h; void *
0x180041590  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041595  mov     r9d, eax; char *
0x180041598  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004159f  mov     edx, 5C2h; void *
0x1800415a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800415a9  mov     r9d, eax; char *
0x1800415ac  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800415b3  mov     edx, 5C3h; void *
0x1800415b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
