# CUserTileBroker::FixCorruptedStore(ushort const *)

- ea: `0x18004fe60`
- end: `0x1800501c0`
- name: `?FixCorruptedStore@CUserTileBroker@@UEAAJPEBG@Z`
- size: `864`
- prototype: `__int64 __fastcall(CUserTileBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008e90`
- `0x180009eec`
- `0x18000bb20`
- `0x18000bd60`
- `0x180013e00`
- `0x180019df0`
- `0x18001a3d0`
- `0x18002555c`
- `0x18002d8a4`
- `0x18004fe60`
- `0x1800501c8`
- `0x180050210`
- `0x180050ba0`
- `0x180051524`
- `0x1800aa9f0`
- `0x1800c9c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004ffe3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004ffe3`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18004feb2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18004feb2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004ff6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004ff6f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180050168`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180050168`

## string_xrefs

- `0x18004fec7`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004fefb`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004ff42`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004ffc2`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180050062`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18005009d`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800500e2`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180050116`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CUserTileBroker::FixCorruptedStore(CUserTileBroker *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r14
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  char *FirstFileW; // rbx
  const char *v8; // r9
  int StringForUserTileType; // eax
  wchar_t *v10; // r13
  unsigned __int64 v11; // r12
  __int64 v12; // rsi
  int v13; // eax
  int CallerSIDString; // eax
  int UserTileRegKey; // eax
  int v16; // eax
  struct HWND__ *i; // rsi
  PWSTR pszPath; // [rsp+20h] [rbp-2D8h] BYREF
  wchar_t *SubStr; // [rsp+28h] [rbp-2D0h] BYREF
  HKEY phkResult; // [rsp+30h] [rbp-2C8h] BYREF
  LPCWSTR psz; // [rsp+38h] [rbp-2C0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-2B8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-2B0h] BYREF
  char *v25; // [rsp+50h] [rbp-2A8h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-2A0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&pszPath);
  v2 = -1;
  do
    ++v2;
  while ( pszPath[v2] );
  v3 = v2 + 1;
  v26 = v2 + 1;
  v4 = PathCchRemoveFileSpec(pszPath, v2 + 1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v4,
      (int)pszPath);
  v5 = StringCchCatW(pszPath, v3, L"\\");
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v5,
      (int)pszPath);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&lpFileName);
  v6 = StringCchCatW((unsigned __int16 *)lpFileName, v3, L"*");
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v6,
      (int)pszPath);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
  v25 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      try
      {
        for ( i = &c_optimizedTileSizes; i != (struct HWND__ *)&dword_18012DB64; i += 3 )
        {
          SubStr = 0;
          StringForUserTileType = GetStringForUserTileType(*((unsigned int *)i + 1), &SubStr);
          if ( StringForUserTileType < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1BE,
              (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
              (const char *)(unsigned int)StringForUserTileType,
              (int)pszPath);
          v10 = SubStr;
          if ( wcsstr(FindFileData.cFileName, SubStr) )
          {
            SubStr = 0;
            v11 = v3;
            v12 = -1;
            do
              ++v12;
            while ( v10[v12] );
            do
            {
              wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v24);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &SubStr,
                &v24);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v24);
              v13 = StringCchCatW(SubStr, v11, FindFileData.cFileName);
              v11 += v12;
            }
            while ( v13 == -2147024774 );
            if ( v13 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1CE,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)v13,
                (int)pszPath);
            psz = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &psz,
              0);
            CallerSIDString = CImpersonateCaller::GetCallerSIDString((unsigned __int16 **)&psz);
            if ( CallerSIDString < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D2,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)CallerSIDString,
                (int)pszPath);
            phkResult = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &phkResult,
              0);
            UserTileRegKey = GetUserTileRegKey(psz, 0x20006u, &phkResult);
            if ( UserTileRegKey < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D4,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)UserTileRegKey,
                (int)pszPath);
            v16 = SHRegSetString(phkResult, 0, v10, SubStr);
            if ( v16 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D6,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)v16,
                (int)pszPath);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&psz);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SubStr);
            goto LABEL_35;
          }
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
          v8);
        v3 = v26;
        FirstFileW = v25;
      }
LABEL_35:
      ;
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v25);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  return 0;
}

```

## disassembly

```asm
0x18004fe60  push    rbx
0x18004fe62  push    rsi
0x18004fe63  push    rdi
0x18004fe64  push    r12
0x18004fe66  push    r13
0x18004fe68  push    r14
0x18004fe6a  sub     rsp, 2C8h
0x18004fe71  mov     rax, cs:__security_cookie
0x18004fe78  xor     rax, rsp
0x18004fe7b  mov     [rsp+2F8h+var_48], rax
0x18004fe83  xor     edi, edi
0x18004fe85  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004fe89  lea     rcx, [rsp+2F8h+pszPath]
0x18004fe8e  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004fe93  nop
0x18004fe94  mov     rcx, [rsp+2F8h+pszPath]; pszPath
0x18004fe99  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fe9d  inc     rax
0x18004fea0  cmp     [rcx+rax*2], di
0x18004fea4  jnz     short loc_18004FE9D
0x18004fea6  lea     r14, [rax+1]
0x18004feaa  mov     [rsp+2F8h+var_2A0], r14
0x18004feaf  mov     rdx, r14; cchPath
0x18004feb2  call    cs:__imp_PathCchRemoveFileSpec
0x18004feb8  mov     rcx, [rsp+2F8h]; this
0x18004fec0  test    eax, eax
0x18004fec2  jns     short loc_18004FED8
0x18004fec4  mov     r9d, eax; char *
0x18004fec7  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004fece  mov     edx, 1AEh; void *
0x18004fed3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004fed8  lea     r8, pszSrc; "\\"
0x18004fedf  mov     rdx, r14; unsigned __int64
0x18004fee2  mov     rcx, [rsp+2F8h+pszPath]; unsigned __int16 *
0x18004fee7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004feec  mov     rcx, [rsp+2F8h]; this
0x18004fef4  test    eax, eax
0x18004fef6  jns     short loc_18004FF0C
0x18004fef8  mov     r9d, eax; char *
0x18004fefb  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004ff02  mov     edx, 1AFh; void *
0x18004ff07  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004ff0c  mov     r8, r14
0x18004ff0f  mov     rdx, [rsp+2F8h+pszPath]
0x18004ff14  lea     rcx, [rsp+2F8h+lpFileName]
0x18004ff19  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004ff1e  nop
0x18004ff1f  lea     r8, asc_180100588; "*"
0x18004ff26  mov     rdx, r14; unsigned __int64
0x18004ff29  mov     rcx, [rsp+2F8h+lpFileName]; unsigned __int16 *
0x18004ff2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004ff33  mov     rcx, [rsp+2F8h]; this
0x18004ff3b  test    eax, eax
0x18004ff3d  jns     short loc_18004FF53
0x18004ff3f  mov     r9d, eax; char *
0x18004ff42  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004ff49  mov     edx, 1B1h; void *
0x18004ff4e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004ff53  xor     edx, edx; Val
0x18004ff55  mov     r8d, 250h; Size
0x18004ff5b  lea     rcx, [rsp+2F8h+FindFileData]; void *
0x18004ff60  call    memset_0
0x18004ff65  lea     rdx, [rsp+2F8h+FindFileData]; lpFindFileData
0x18004ff6a  mov     rcx, [rsp+2F8h+lpFileName]; lpFileName
0x18004ff6f  call    cs:__imp_FindFirstFileW
0x18004ff75  mov     rbx, rax
0x18004ff78  mov     [rsp+2F8h+var_2A8], rax
0x18004ff7d  dec     rax
0x18004ff80  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ff84  ja      loc_180050176
0x18004ff8a  lea     rsi, ?c_optimizedTileSizes@@3PAUUSERTILE_OPTIMIZED_SIZES@@A; USERTILE_OPTIMIZED_SIZES near * c_optimizedTileSizes
0x18004ff91  lea     r12, dword_18012DB64
0x18004ff98  cmp     rsi, r12
0x18004ff9b  jz      loc_180050149
0x18004ffa1  mov     [rsp+2F8h+SubStr], rdi
0x18004ffa6  lea     rdx, [rsp+2F8h+SubStr]
0x18004ffab  mov     ecx, [rsi+4]
0x18004ffae  call    ?GetStringForUserTileType@@YAJW4USER_TILE_TYPE@@PEAPEBG@Z; GetStringForUserTileType(USER_TILE_TYPE,ushort const * *)
0x18004ffb3  mov     rcx, [rsp+2F8h]; this
0x18004ffbb  test    eax, eax
0x18004ffbd  jns     short loc_18004FFD3
0x18004ffbf  mov     r9d, eax; char *
0x18004ffc2  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004ffc9  mov     edx, 1BEh; void *
0x18004ffce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004ffd3  mov     r13, [rsp+2F8h+SubStr]
0x18004ffd8  mov     rdx, r13; SubStr
0x18004ffdb  lea     rcx, [rsp+2F8h+FindFileData.cFileName]; Str
0x18004ffe3  call    cs:__imp_wcsstr
0x18004ffe9  test    rax, rax
0x18004ffec  jz      loc_18005014B
0x18004fff2  mov     [rsp+2F8h+SubStr], rdi
0x18004fff7  mov     r12, r14
0x18004fffa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004fffe  inc     rsi
0x180050001  cmp     [r13+rsi*2+0], di
0x180050007  jnz     short loc_18004FFFE
0x180050009  mov     r8, r12
0x18005000c  mov     rdx, [rsp+2F8h+pszPath]
0x180050011  lea     rcx, [rsp+2F8h+var_2B0]
0x180050016  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005001b  lea     rdx, [rsp+2F8h+var_2B0]
0x180050020  lea     rcx, [rsp+2F8h+SubStr]
0x180050025  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18005002a  lea     rcx, [rsp+2F8h+var_2B0]
0x18005002f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180050034  lea     r8, [rsp+2F8h+FindFileData.cFileName]; unsigned __int16 *
0x18005003c  mov     rdx, r12; unsigned __int64
0x18005003f  mov     rcx, [rsp+2F8h+SubStr]; unsigned __int16 *
0x180050044  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180050049  add     r12, rsi
0x18005004c  cmp     eax, 8007007Ah
0x180050051  jz      short loc_180050009
0x180050053  mov     rcx, [rsp+2F8h]; this
0x18005005b  test    eax, eax
0x18005005d  jns     short loc_180050073
0x18005005f  mov     r9d, eax; char *
0x180050062  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180050069  mov     edx, 1CEh; void *
0x18005006e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180050073  mov     [rsp+2F8h+psz], rdi
0x180050078  xor     edx, edx
0x18005007a  lea     rcx, [rsp+2F8h+psz]
0x18005007f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180050084  lea     rcx, [rsp+2F8h+psz]; unsigned __int16 **
0x180050089  call    ?GetCallerSIDString@CImpersonateCaller@@SAJPEAPEAG@Z; CImpersonateCaller::GetCallerSIDString(ushort * *)
0x18005008e  mov     rcx, [rsp+2F8h]; this
0x180050096  test    eax, eax
0x180050098  jns     short loc_1800500AE
0x18005009a  mov     r9d, eax; char *
0x18005009d  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800500a4  mov     edx, 1D2h; void *
0x1800500a9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800500ae  mov     [rsp+2F8h+phkResult], rdi
0x1800500b3  xor     edx, edx
0x1800500b5  lea     rcx, [rsp+2F8h+phkResult]
0x1800500ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800500bf  lea     r8, [rsp+2F8h+phkResult]; phkResult
0x1800500c4  mov     edx, 20006h; samDesired
0x1800500c9  mov     rcx, [rsp+2F8h+psz]; psz
0x1800500ce  call    GetUserTileRegKey
0x1800500d3  mov     rcx, [rsp+2F8h]; this
0x1800500db  test    eax, eax
0x1800500dd  jns     short loc_1800500F3
0x1800500df  mov     r9d, eax; char *
0x1800500e2  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800500e9  mov     edx, 1D4h; void *
0x1800500ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800500f3  mov     r9, [rsp+2F8h+SubStr]; unsigned __int16 *
0x1800500f8  mov     r8, r13; unsigned __int16 *
0x1800500fb  xor     edx, edx; unsigned __int16 *
0x1800500fd  mov     rcx, [rsp+2F8h+phkResult]; HKEY
0x180050102  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180050107  mov     rcx, [rsp+2F8h]; this
0x18005010f  test    eax, eax
0x180050111  jns     short loc_180050128
0x180050113  mov     r9d, eax; char *
0x180050116  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18005011d  mov     edx, 1D6h; void *
0x180050122  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180050128  lea     rcx, [rsp+2F8h+phkResult]
0x18005012d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050132  nop
0x180050133  lea     rcx, [rsp+2F8h+psz]
0x180050138  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005013d  nop
0x18005013e  lea     rcx, [rsp+2F8h+SubStr]
0x180050143  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180050148  nop
0x180050149  jmp     short loc_180050160
0x18005014b  add     rsi, 0Ch
0x18005014f  jmp     loc_18004FF98
0x180050154  xor     edi, edi
0x180050156  mov     r14, [rsp+2F8h+var_2A0]
0x18005015b  mov     rbx, [rsp+2F8h+var_2A8]
0x180050160  lea     rdx, [rsp+2F8h+FindFileData]; lpFindFileData
0x180050165  mov     rcx, rbx; hFindFile
0x180050168  call    cs:__imp_FindNextFileW
0x18005016e  test    eax, eax
0x180050170  jnz     loc_18004FF8A
0x180050176  lea     rcx, [rsp+2F8h+var_2A8]
0x18005017b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180050180  nop
0x180050181  lea     rcx, [rsp+2F8h+lpFileName]
0x180050186  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005018b  nop
0x18005018c  lea     rcx, [rsp+2F8h+pszPath]
0x180050191  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180050196  xor     eax, eax
0x180050198  jmp     short loc_18005019E
0x18005019a  mov     eax, dword ptr [rsp+2F8h+pszPath]
0x18005019e  mov     rcx, [rsp+2F8h+var_48]
0x1800501a6  xor     rcx, rsp; StackCookie
0x1800501a9  call    __security_check_cookie
0x1800501ae  add     rsp, 2C8h
0x1800501b5  pop     r14
0x1800501b7  pop     r13
0x1800501b9  pop     r12
0x1800501bb  pop     rdi
0x1800501bc  pop     rsi
0x1800501bd  pop     rbx
0x1800501be  retn
```
