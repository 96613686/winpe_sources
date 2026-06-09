# Windows::TestHooks::GetTestSettings(void)

- ea: `0x14024db10`
- end: `0x14024e029`
- name: `?GetTestSettings@TestHooks@Windows@@UEAA?AW4TestLevel@SystemInterface@@XZ`
- size: `1305`
- prototype: ``
- caller_count: `10`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14024e230`
- `0x14024e2d8`
- `0x14024e4f0`
- `0x14024e9f0`
- `0x14024eb70`
- `0x14024ecf0`
- `0x14024f040`
- `0x14024f940`
- `0x14024fac0`
- `0x14024fcf0`

## callees

- `0x1400289d4`
- `0x14003c578`
- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x14004f25c`
- `0x140057a20`
- `0x1400741c4`
- `0x140148408`
- `0x1401498b4`
- `0x140235744`
- `0x14024d9e0`
- `0x14024db10`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024dbd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024dd6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024df88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024dbd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024dd6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024df88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024df77`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024df77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14024dda9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14024dda9`

## string_xrefs

- `0x14024dfc6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024e016`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024dc5f`: `USOSelfHostDllNotSigned`
- `0x14024db53`: `%WINDIR%\System32\UsoSelfhost.dll`
- `0x14024dfd8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x14024dfea`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x14024dffc`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::TestHooks::GetTestSettings(__int64 a1)
{
  __int64 result; // rax
  const char *v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rax
  int v8; // edx
  const char *v9; // r9
  __int64 v10; // r11
  __int64 v11; // rax
  __int64 v12; // rax
  const char *v13; // r9
  FARPROC ProcAddress; // rax
  const char *v15; // r9
  int v16; // eax
  int v17; // eax
  const wchar_t *v18; // rdx
  __int64 v19; // r8
  void *traits_2_unsigned_short; // rax
  int v21; // edx
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-1B8h]
  LPVOID pv[2]; // [rsp+30h] [rbp-1A8h] BYREF
  __int128 v29; // [rsp+40h] [rbp-198h] BYREF
  __int128 v30; // [rsp+50h] [rbp-188h] BYREF
  __int128 v31; // [rsp+60h] [rbp-178h] BYREF
  HMODULE hModule; // [rsp+70h] [rbp-168h] BYREF
  __int128 v33; // [rsp+78h] [rbp-160h] BYREF
  __int64 v34; // [rsp+88h] [rbp-150h]
  __int64 v35; // [rsp+90h] [rbp-148h]
  char v36; // [rsp+98h] [rbp-140h]
  __int128 v37; // [rsp+A0h] [rbp-138h] BYREF
  _QWORD v38[34]; // [rsp+B0h] [rbp-128h] BYREF
  int v39; // [rsp+1C0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 12) )
    return *(unsigned int *)(a1 + 8);
  pv[0] = 0;
  try
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      pv,
      L"%WINDIR%\\System32\\UsoSelfhost.dll");
    memset(v38, 0, sizeof(v38));
    std::ifstream::ifstream(v38, pv[0]);
    if ( *(_DWORD *)((char *)&v38[2] + *(int *)(v38[0] + 4LL)) )
    {
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v38[22]);
      v38[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v38[22]);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      result = 0;
    }
    else
    {
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v38[22]);
      v38[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v38[22]);
      *(LPVOID *)&v29 = pv[0];
      v4 = -1;
      v5 = -1;
      do
        ++v5;
      while ( *((_WORD *)pv[0] + v5) );
      *((_QWORD *)&v29 + 1) = v5;
      v30 = v29;
      if ( (unsigned __int8)Windows::Trust::IsFileSelfSigned(&v30) )
      {
        hModule = 0;
        Windows::TestHooks::GetSelfHostDll(v6, &hModule);
        if ( !hModule )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x3F,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            v13);
        ProcAddress = GetProcAddress(hModule, "IsTestMode");
        if ( !ProcAddress )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x42,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            v15);
        v39 = 0;
        v16 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v39);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x45,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            (const char *)(unsigned int)v16,
            v27);
        LODWORD(v29) = (v39 != 0) + 1;
        BYTE4(v29) = 1;
        v17 = v29;
        *(_QWORD *)(a1 + 8) = v29;
        if ( *(_BYTE *)(a1 + 12) )
        {
          if ( v17 )
          {
            if ( v17 == 1 )
            {
              v18 = L"PPE";
            }
            else if ( v17 == 2 )
            {
              v18 = L"Sandbox";
            }
            else
            {
              v18 = L"Unknown to_wstring(TestLevel)";
            }
          }
          else
          {
            v18 = L"Production";
          }
        }
        else
        {
          v18 = L"ErrorNoValue";
        }
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        std::wstring::_Construct<1,wchar_t const *>(&v33, v18);
        v36 = 2;
        traits_2_unsigned_short = (void *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                            L"GetTestSettingsStatus",
                                            &unk_140471404,
                                            0);
        if ( traits_2_unsigned_short == &unk_140471404
          || (v24 = ((__int64)traits_2_unsigned_short - v23) >> 1, v24 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v22);
        }
        *(_QWORD *)&v30 = v23;
        *((_QWORD *)&v30 + 1) = v24;
        v25 = -1;
        do
          ++v25;
        while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v25] );
        *(_QWORD *)&v31 = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
        *((_QWORD *)&v31 + 1) = v25;
        *(_QWORD *)&v29 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        do
          ++v4;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v4] );
        *((_QWORD *)&v29 + 1) = v4;
        v37 = v30;
        v30 = v31;
        v31 = v29;
        Windows::Registry::SetValue(
          (unsigned int)&v29,
          v21,
          (unsigned int)&v31,
          (unsigned int)&v30,
          (__int64)&v37,
          (__int64)&v33);
        if ( v36 != -1 && v36 && v36 != 1 )
          std::wstring::~wstring(&v33);
        v26 = *(_DWORD *)(a1 + 8);
        if ( hModule )
          FreeLibrary(hModule);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        result = v26;
      }
      else
      {
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v33, L"USOSelfHostDllNotSigned");
        v36 = 2;
        v7 = (void *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"GetTestSettingsStatus",
                       &unk_140471404,
                       0);
        if ( v7 == &unk_140471404 || (v11 = ((__int64)v7 - v10) >> 1, v11 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v9);
        *(_QWORD *)&v29 = v10;
        *((_QWORD *)&v29 + 1) = v11;
        v12 = -1;
        do
          ++v12;
        while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v12] );
        *(_QWORD *)&v31 = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
        *((_QWORD *)&v31 + 1) = v12;
        *(_QWORD *)&v30 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        do
          ++v4;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v4] );
        *((_QWORD *)&v30 + 1) = v4;
        v37 = v29;
        Windows::Registry::SetValue(
          (unsigned int)&v29,
          v8,
          (unsigned int)&v30,
          (unsigned int)&v31,
          (__int64)&v37,
          (__int64)&v33);
        if ( v36 != -1 && v36 && v36 != 1 )
          std::wstring::~wstring(&v33);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x53,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
      v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14024db10  mov     [rsp+arg_8], rbx
0x14024db15  mov     [rsp+arg_10], rsi
0x14024db1a  mov     [rsp+arg_18], rdi
0x14024db1f  push    r14
0x14024db21  sub     rsp, 1D0h
0x14024db28  mov     rax, cs:__security_cookie
0x14024db2f  xor     rax, rsp
0x14024db32  mov     [rsp+1D8h+var_10], rax
0x14024db3a  mov     rdi, rcx
0x14024db3d  xor     r14d, r14d
0x14024db40  cmp     [rcx+0Ch], r14b
0x14024db44  jz      short loc_14024DB4E
0x14024db46  mov     eax, [rcx+8]
0x14024db49  jmp     loc_14024DF94
0x14024db4e  mov     [rsp+1D8h+pv], r14
0x14024db53  lea     rdx, aWindirSystem32_0; "%WINDIR%\\System32\\UsoSelfhost.dll"
0x14024db5a  lea     rcx, [rsp+1D8h+pv]
0x14024db5f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x14024db64  nop
0x14024db65  xor     edx, edx; Val
0x14024db67  mov     r8d, 110h; Size
0x14024db6d  lea     rcx, [rsp+1D8h+var_128]; void *
0x14024db75  call    memset
0x14024db7a  mov     rdx, [rsp+1D8h+pv]
0x14024db7f  lea     rcx, [rsp+1D8h+var_128]
0x14024db87  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x14024db8c  mov     rax, [rsp+1D8h+var_128]
0x14024db94  movsxd  rcx, dword ptr [rax+4]
0x14024db98  cmp     [rsp+rcx+1D8h+var_118], r14d
0x14024dba0  lea     rcx, [rsp+1D8h+var_78]
0x14024dba8  jz      short loc_14024DBE3
0x14024dbaa  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x14024dbaf  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x14024dbb6  mov     [rsp+1D8h+var_78], rax
0x14024dbbe  lea     rcx, [rsp+1D8h+var_78]; this
0x14024dbc6  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x14024dbcb  nop
0x14024dbcc  mov     rcx, [rsp+1D8h+pv]; pv
0x14024dbd1  test    rcx, rcx
0x14024dbd4  jz      short loc_14024DBDC
0x14024dbd6  call    cs:__imp_CoTaskMemFree
0x14024dbdc  xor     eax, eax
0x14024dbde  jmp     loc_14024DF94
0x14024dbe3  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x14024dbe8  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x14024dbef  mov     [rsp+1D8h+var_78], rax
0x14024dbf7  lea     rcx, [rsp+1D8h+var_78]; this
0x14024dbff  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x14024dc04  mov     rax, [rsp+1D8h+pv]
0x14024dc09  mov     qword ptr [rsp+1D8h+var_198], rax
0x14024dc0e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14024dc12  mov     rcx, rbx
0x14024dc15  inc     rcx
0x14024dc18  cmp     [rax+rcx*2], r14w
0x14024dc1d  jnz     short loc_14024DC15
0x14024dc1f  mov     qword ptr [rsp+1D8h+var_198+8], rcx
0x14024dc24  movaps  xmm0, [rsp+1D8h+var_198]
0x14024dc29  movdqa  [rsp+1D8h+var_188], xmm0
0x14024dc2f  lea     rcx, [rsp+1D8h+var_188]
0x14024dc34  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x14024dc39  test    al, al
0x14024dc3b  jnz     loc_14024DD7C
0x14024dc41  xorps   xmm0, xmm0
0x14024dc44  movups  [rsp+1D8h+var_160], xmm0
0x14024dc49  mov     [rsp+1D8h+var_150], r14
0x14024dc51  mov     [rsp+1D8h+var_148], r14
0x14024dc59  mov     r8d, 17h
0x14024dc5f  lea     rdx, aUsoselfhostdll; "USOSelfHostDllNotSigned"
0x14024dc66  lea     rcx, [rsp+1D8h+var_160]
0x14024dc6b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024dc70  mov     [rsp+1D8h+var_140], 2
0x14024dc78  xor     r8d, r8d
0x14024dc7b  lea     rsi, unk_140471404
0x14024dc82  mov     rdx, rsi
0x14024dc85  lea     r11, aGettestsetting; "GetTestSettingsStatus"
0x14024dc8c  mov     rcx, r11
0x14024dc8f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024dc94  cmp     rax, rsi
0x14024dc97  jz      loc_14024DFBE
0x14024dc9d  sub     rax, r11
0x14024dca0  sar     rax, 1
0x14024dca3  cmp     rax, rbx
0x14024dca6  jz      loc_14024DFBE
0x14024dcac  mov     qword ptr [rsp+1D8h+var_198], r11
0x14024dcb1  mov     qword ptr [rsp+1D8h+var_198+8], rax
0x14024dcb6  mov     rcx, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x14024dcbd  mov     rax, rbx
0x14024dcc0  inc     rax
0x14024dcc3  cmp     [rcx+rax*2], r14w
0x14024dcc8  jnz     short loc_14024DCC0
0x14024dcca  mov     qword ptr [rsp+1D8h+var_178], rcx
0x14024dccf  mov     qword ptr [rsp+1D8h+var_178+8], rax
0x14024dcd4  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x14024dcdb  mov     qword ptr [rsp+1D8h+var_188], rax
0x14024dce0  inc     rbx
0x14024dce3  cmp     [rax+rbx*2], r14w
0x14024dce8  jnz     short loc_14024DCE0
0x14024dcea  mov     qword ptr [rsp+1D8h+var_188+8], rbx
0x14024dcef  movups  xmm0, [rsp+1D8h+var_198]
0x14024dcf4  movdqu  [rsp+1D8h+var_138], xmm0
0x14024dcfd  movups  xmm1, [rsp+1D8h+var_178]
0x14024dd02  movdqu  [rsp+1D8h+var_178], xmm1
0x14024dd08  movaps  xmm0, [rsp+1D8h+var_188]
0x14024dd0d  movdqa  [rsp+1D8h+var_188], xmm0
0x14024dd13  lea     rax, [rsp+1D8h+var_160]
0x14024dd18  mov     [rsp+1D8h+var_1B0], rax
0x14024dd1d  lea     rax, [rsp+1D8h+var_138]
0x14024dd25  mov     [rsp+1D8h+var_1B8], rax
0x14024dd2a  lea     r9, [rsp+1D8h+var_178]
0x14024dd2f  lea     r8, [rsp+1D8h+var_188]
0x14024dd34  lea     rcx, [rsp+1D8h+var_198]
0x14024dd39  call    ?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::wstring> const &)
0x14024dd3e  nop
0x14024dd3f  movsx   rax, [rsp+1D8h+var_140]
0x14024dd48  add     rax, 1
0x14024dd4c  jz      short loc_14024DD65
0x14024dd4e  sub     rax, 1
0x14024dd52  jz      short loc_14024DD65
0x14024dd54  cmp     rax, 1
0x14024dd58  jz      short loc_14024DD65
0x14024dd5a  lea     rcx, [rsp+1D8h+var_160]
0x14024dd5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024dd64  nop
0x14024dd65  mov     rcx, [rsp+1D8h+pv]; pv
0x14024dd6a  test    rcx, rcx
0x14024dd6d  jz      short loc_14024DD75
0x14024dd6f  call    cs:__imp_CoTaskMemFree
0x14024dd75  xor     eax, eax
0x14024dd77  jmp     loc_14024DF94
0x14024dd7c  mov     [rsp+1D8h+hModule], r14
0x14024dd81  lea     rdx, [rsp+1D8h+hModule]
0x14024dd86  call    ?GetSelfHostDll@TestHooks@Windows@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::TestHooks::GetSelfHostDll(void)
0x14024dd8b  nop
0x14024dd8c  mov     rax, [rsp+1D8h]
0x14024dd94  mov     rcx, [rsp+1D8h+hModule]; hModule
0x14024dd99  test    rcx, rcx
0x14024dd9c  jz      loc_14024DFD8
0x14024dda2  lea     rdx, aIstestmode; "IsTestMode"
0x14024dda9  call    cs:__imp_GetProcAddress
0x14024ddaf  mov     rcx, [rsp+1D8h]; this
0x14024ddb7  test    rax, rax
0x14024ddba  jz      loc_14024DFEA
0x14024ddc0  mov     [rsp+1D8h+var_18], r14d
0x14024ddc8  lea     rcx, [rsp+1D8h+var_18]
0x14024ddd0  call    _guard_dispatch_icall
0x14024ddd5  mov     rcx, [rsp+1D8h]; this
0x14024dddd  test    eax, eax
0x14024dddf  js      loc_14024DFF9
0x14024dde5  mov     eax, [rsp+1D8h+var_18]
0x14024ddec  neg     eax
0x14024ddee  sbb     ecx, ecx
0x14024ddf0  neg     ecx
0x14024ddf2  inc     ecx
0x14024ddf4  mov     dword ptr [rsp+1D8h+var_198], ecx
0x14024ddf8  mov     byte ptr [rsp+1D8h+var_198+4], 1
0x14024ddfd  mov     rax, qword ptr [rsp+1D8h+var_198]
0x14024de02  mov     [rdi+8], rax
0x14024de06  cmp     [rdi+0Ch], r14b
0x14024de0a  jz      short loc_14024DE40
0x14024de0c  mov     ecx, eax
0x14024de0e  test    eax, eax
0x14024de10  jz      short loc_14024DE37
0x14024de12  sub     ecx, 1
0x14024de15  jz      short loc_14024DE2E
0x14024de17  cmp     ecx, 1
0x14024de1a  jz      short loc_14024DE25
0x14024de1c  lea     rdx, aUnknownToWstri; "Unknown to_wstring(TestLevel)"
0x14024de23  jmp     short loc_14024DE47
0x14024de25  lea     rdx, aSandbox; "Sandbox"
0x14024de2c  jmp     short loc_14024DE47
0x14024de2e  lea     rdx, aPpe; "PPE"
0x14024de35  jmp     short loc_14024DE47
0x14024de37  lea     rdx, aProduction; "Production"
0x14024de3e  jmp     short loc_14024DE47
0x14024de40  lea     rdx, aErrornovalue; "ErrorNoValue"
0x14024de47  xorps   xmm0, xmm0
0x14024de4a  movups  [rsp+1D8h+var_160], xmm0
0x14024de4f  mov     [rsp+1D8h+var_150], r14
0x14024de57  mov     [rsp+1D8h+var_148], r14
0x14024de5f  mov     r8, rbx
0x14024de62  inc     r8
0x14024de65  cmp     [rdx+r8*2], r14w
0x14024de6a  jnz     short loc_14024DE62
0x14024de6c  lea     rcx, [rsp+1D8h+var_160]
0x14024de71  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024de76  mov     [rsp+1D8h+var_140], 2
0x14024de7e  xor     r8d, r8d
0x14024de81  lea     rsi, unk_140471404
0x14024de88  mov     rdx, rsi
0x14024de8b  lea     r11, aGettestsetting; "GetTestSettingsStatus"
0x14024de92  mov     rcx, r11
0x14024de95  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024de9a  cmp     rax, rsi
0x14024de9d  jz      loc_14024E00E
0x14024dea3  sub     rax, r11
0x14024dea6  sar     rax, 1
0x14024dea9  cmp     rax, rbx
0x14024deac  jz      loc_14024E00E
0x14024deb2  mov     qword ptr [rsp+1D8h+var_188], r11
0x14024deb7  mov     qword ptr [rsp+1D8h+var_188+8], rax
0x14024debc  mov     rcx, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x14024dec3  mov     rax, rbx
0x14024dec6  inc     rax
0x14024dec9  cmp     [rcx+rax*2], r14w
0x14024dece  jnz     short loc_14024DEC6
0x14024ded0  mov     qword ptr [rsp+1D8h+var_178], rcx
0x14024ded5  mov     qword ptr [rsp+1D8h+var_178+8], rax
0x14024deda  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x14024dee1  mov     qword ptr [rsp+1D8h+var_198], rax
0x14024dee6  inc     rbx
0x14024dee9  cmp     [rax+rbx*2], r14w
0x14024deee  jnz     short loc_14024DEE6
0x14024def0  mov     qword ptr [rsp+1D8h+var_198+8], rbx
0x14024def5  movups  xmm0, [rsp+1D8h+var_188]
0x14024defa  movdqu  [rsp+1D8h+var_138], xmm0
0x14024df03  movups  xmm1, [rsp+1D8h+var_178]
0x14024df08  movdqu  [rsp+1D8h+var_188], xmm1
0x14024df0e  movaps  xmm0, [rsp+1D8h+var_198]
0x14024df13  movdqa  [rsp+1D8h+var_178], xmm0
0x14024df19  lea     rax, [rsp+1D8h+var_160]
0x14024df1e  mov     [rsp+1D8h+var_1B0], rax
0x14024df23  lea     rax, [rsp+1D8h+var_138]
0x14024df2b  mov     [rsp+1D8h+var_1B8], rax
0x14024df30  lea     r9, [rsp+1D8h+var_188]
0x14024df35  lea     r8, [rsp+1D8h+var_178]
0x14024df3a  lea     rcx, [rsp+1D8h+var_198]
0x14024df3f  call    ?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::wstring> const &)
0x14024df44  nop
0x14024df45  movsx   rax, [rsp+1D8h+var_140]
0x14024df4e  add     rax, 1
0x14024df52  jz      short loc_14024DF6A
0x14024df54  sub     rax, 1
0x14024df58  jz      short loc_14024DF6A
0x14024df5a  cmp     rax, 1
0x14024df5e  jz      short loc_14024DF6A
0x14024df60  lea     rcx, [rsp+1D8h+var_160]
0x14024df65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024df6a  mov     ebx, [rdi+8]
0x14024df6d  mov     rcx, [rsp+1D8h+hModule]; hLibModule
0x14024df72  test    rcx, rcx
0x14024df75  jz      short loc_14024DF7E
0x14024df77  call    cs:__imp_FreeLibrary
0x14024df7d  nop
0x14024df7e  mov     rcx, [rsp+1D8h+pv]; pv
0x14024df83  test    rcx, rcx
0x14024df86  jz      short loc_14024DF8E
0x14024df88  call    cs:__imp_CoTaskMemFree
0x14024df8e  mov     eax, ebx
0x14024df90  jmp     short loc_14024DF94
0x14024df92  xor     eax, eax
0x14024df94  mov     rcx, [rsp+1D8h+var_10]
0x14024df9c  xor     rcx, rsp; StackCookie
0x14024df9f  call    __security_check_cookie
0x14024dfa4  lea     r11, [rsp+1D8h+var_8]
0x14024dfac  mov     rbx, [r11+18h]
0x14024dfb0  mov     rsi, [r11+20h]
0x14024dfb4  mov     rdi, [r11+28h]
0x14024dfb8  mov     rsp, r11
0x14024dfbb  pop     r14
0x14024dfbd  retn
0x14024dfbe  mov     rcx, [rsp+1D8h]; this
0x14024dfc6  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14024dfcd  mov     edx, 0C9h; void *
0x14024dfd2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14024dfd8  lea     r8, aCW1SSrcOrchest_52; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024dfdf  lea     edx, [rcx+3Fh]; void *
0x14024dfe2  mov     rcx, rax; this
0x14024dfe5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024dfea  lea     r8, aCW1SSrcOrchest_52; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024dff1  lea     edx, [rax+42h]; void *
0x14024dff4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024dff9  mov     r9d, eax; char *
0x14024dffc  lea     r8, aCW1SSrcOrchest_52; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024e003  mov     edx, 45h ; 'E'; void *
0x14024e008  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14024e00e  mov     rcx, [rsp+1D8h]; this
0x14024e016  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14024e01d  mov     edx, 0C9h; void *
0x14024e022  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
