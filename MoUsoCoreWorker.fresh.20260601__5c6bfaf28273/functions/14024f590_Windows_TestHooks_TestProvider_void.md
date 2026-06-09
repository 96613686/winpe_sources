# Windows::TestHooks::TestProvider(void)

- ea: `0x14024f590`
- end: `0x14024f92f`
- name: `?TestProvider@TestHooks@Windows@@UEAA?AV?$optional@V?$unique_ptr@VUpdateProvider@@U?$default_delete@VUpdateProvider@@@std@@@std@@@std@@XZ`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400289d4`
- `0x14003c578`
- `0x140040184`
- `0x14004f25c`
- `0x140057a20`
- `0x1400741c4`
- `0x14012c748`
- `0x140148408`
- `0x1401498b4`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x14024d9e0`
- `0x14024f590`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024f7a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024f823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024f7a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14024f823`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f792`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f803`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f812`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f792`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f803`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14024f812`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14024f85c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14024f85c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14024f7c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14024f848`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14024f7c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14024f848`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14024f7d5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14024f7d5`

## string_xrefs

- `0x14024f8d2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024f6c0`: `%WINDIR%\System32\TestProvider.dll`
- `0x14024f904`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x14024f91d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x14024f619`: `ExpeditedAppRegistrationPathOverride`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BYTE *__fastcall Windows::TestHooks::TestProvider(__int64 a1, _BYTE *a2)
{
  int v3; // eax
  __int64 traits_2_unsigned_short; // rax
  const char *v5; // r9
  __int64 v6; // r11
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  HMODULE v11; // rbx
  bool v12; // si
  __int64 v13; // rcx
  HMODULE LibraryW; // rax
  const char *v15; // r9
  HMODULE v16; // rcx
  FARPROC ProcAddress; // rax
  const char *v18; // r9
  __int64 *v19; // rax
  __int64 v20; // rcx
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v24[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v25[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v26[4]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v27[34]; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  pv = a2;
  v26[2] = &Windows::g_testDllMutex;
  if ( (unsigned int)mtx_do_lock(&Windows::g_testDllMutex, 0) )
    std::_Throw_Cpp_error(5);
  v3 = dword_1405077FC;
  if ( dword_1405077FC == 0x7FFFFFFF )
  {
    dword_1405077FC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !Windows::g_testDll )
  {
    hLibModule = (HMODULE)&Windows::Registry::`vftable';
    traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                L"TestProviderEnabled",
                                L"ExpeditedAppRegistrationPathOverride",
                                0);
    if ( traits_2_unsigned_short == v6
      || (v7 = (traits_2_unsigned_short - (__int64)L"TestProviderEnabled") >> 1, v7 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v5);
    }
    v8 = -1;
    do
      ++v8;
    while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v8] );
    v9 = -1;
    do
      ++v9;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v9] );
    v25[0] = L"TestProviderEnabled";
    v25[1] = v7;
    v26[0] = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
    v26[1] = v8;
    *(_QWORD *)&v24[0] = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    *((_QWORD *)&v24[0] + 1) = v9;
    if ( !(unsigned __int8)SystemInterface::Registry::GetSystemBoolOrDefault(
                             (unsigned int)&hLibModule,
                             (unsigned int)v24,
                             (unsigned int)v26,
                             (unsigned int)v25,
                             0) )
    {
      a2[8] = 0;
LABEL_22:
      if ( !--dword_1405077FC )
      {
        dword_1405077F8 = -1;
        ReleaseSRWLockExclusive(&stru_1405077C0);
      }
      return a2;
    }
    pv = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      &pv,
      L"%WINDIR%\\System32\\TestProvider.dll");
    memset(v27, 0, sizeof(v27));
    std::ifstream::ifstream(v27, pv);
    if ( *(_DWORD *)((char *)&v27[2] + *(int *)(v27[0] + 4LL)) )
    {
      a2[8] = 0;
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v27[22]);
      v27[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v27[22]);
LABEL_20:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_22;
    }
    std::ifstream::~ifstream<char,std::char_traits<char>>(&v27[22]);
    v27[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v27[22]);
    hLibModule = 0;
    Windows::TestHooks::GetSelfHostDll(v10, &hLibModule);
    v11 = hLibModule;
    v12 = hLibModule != 0;
    if ( !hLibModule )
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      *(_QWORD *)&v24[0] = pv;
      *((_QWORD *)&v24[0] + 1) = v13;
      if ( !Windows::Trust::IsFileSelfSigned(v24) )
      {
        a2[8] = 0;
        if ( v12 )
          FreeLibrary(0);
        goto LABEL_20;
      }
    }
    LibraryW = LoadLibraryW((LPCWSTR)pv);
    v25[0] = LibraryW;
    if ( !LibraryW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x140,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
        v15);
    v16 = Windows::g_testDll;
    Windows::g_testDll = LibraryW;
    if ( v16 )
      FreeLibrary(v16);
    if ( v12 )
      FreeLibrary(v11);
    if ( pv )
      CoTaskMemFree(pv);
    v3 = dword_1405077FC;
  }
  dword_1405077FC = v3 - 1;
  if ( v3 == 1 )
  {
    dword_1405077F8 = -1;
    ReleaseSRWLockExclusive(&stru_1405077C0);
  }
  ProcAddress = GetProcAddress(Windows::g_testDll, "GetTestProvider");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x148,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
      v18);
  v19 = (__int64 *)((__int64 (__fastcall *)(LPVOID *))ProcAddress)(&pv);
  v20 = *v19;
  *v19 = 0;
  *(_QWORD *)a2 = v20;
  a2[8] = 1;
  if ( pv )
    (**(void (__fastcall ***)(LPVOID, __int64))pv)(pv, 1);
  return a2;
}

```

## disassembly

```asm
0x14024f590  mov     rax, rsp
0x14024f593  mov     [rax+8], rbx
0x14024f597  mov     [rax+18h], rsi
0x14024f59b  mov     [rax+20h], rdi
0x14024f59f  push    rbp
0x14024f5a0  push    r14
0x14024f5a2  push    r15
0x14024f5a4  lea     rbp, [rax-0C8h]
0x14024f5ab  sub     rsp, 1B0h
0x14024f5b2  mov     rax, cs:__security_cookie
0x14024f5b9  xor     rax, rsp
0x14024f5bc  mov     [rbp+0C0h+var_20], rax
0x14024f5c3  mov     rdi, rdx
0x14024f5c6  mov     [rsp+1C0h+pv], rdx
0x14024f5cb  xor     r14d, r14d
0x14024f5ce  lea     rcx, ?g_testDllMutex@Windows@@3Vmutex@std@@A; std::mutex Windows::g_testDllMutex
0x14024f5d5  mov     [rbp+0C0h+var_140], rcx
0x14024f5d9  xor     edx, edx
0x14024f5db  call    mtx_do_lock
0x14024f5e0  test    eax, eax
0x14024f5e2  jnz     loc_14024F8E4
0x14024f5e8  mov     eax, cs:dword_1405077FC
0x14024f5ee  cmp     eax, 7FFFFFFFh
0x14024f5f3  jz      loc_14024F8EF
0x14024f5f9  or      r15, 0FFFFFFFFFFFFFFFFh
0x14024f5fd  cmp     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x14024f604  jnz     loc_14024F82F
0x14024f60a  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x14024f611  mov     [rsp+1C0h+hLibModule], rax
0x14024f616  xor     r8d, r8d
0x14024f619  lea     r11, aExpeditedappre_0; "ExpeditedAppRegistrationPathOverride"
0x14024f620  mov     rdx, r11
0x14024f623  lea     rbx, aTestprovideren; "TestProviderEnabled"
0x14024f62a  mov     rcx, rbx
0x14024f62d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024f632  cmp     rax, r11
0x14024f635  jz      loc_14024F8CB
0x14024f63b  sub     rax, rbx
0x14024f63e  sar     rax, 1
0x14024f641  cmp     rax, r15
0x14024f644  jz      loc_14024F8CB
0x14024f64a  mov     r8, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x14024f651  mov     rcx, r15
0x14024f654  inc     rcx
0x14024f657  cmp     [r8+rcx*2], r14w
0x14024f65c  jnz     short loc_14024F654
0x14024f65e  mov     r9, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x14024f665  mov     rdx, r15
0x14024f668  inc     rdx
0x14024f66b  cmp     [r9+rdx*2], r14w
0x14024f670  jnz     short loc_14024F668
0x14024f672  mov     [rsp+1C0h+var_160], rbx
0x14024f677  mov     [rsp+1C0h+var_158], rax
0x14024f67c  mov     [rsp+1C0h+var_150], r8
0x14024f681  mov     [rsp+1C0h+var_148], rcx
0x14024f686  mov     [rsp+1C0h+var_180], r9
0x14024f68b  mov     [rsp+1C0h+var_178], rdx
0x14024f690  mov     [rsp+1C0h+var_1A0], r14b
0x14024f695  lea     r9, [rsp+1C0h+var_160]
0x14024f69a  lea     r8, [rsp+1C0h+var_150]
0x14024f69f  lea     rdx, [rsp+1C0h+var_180]
0x14024f6a4  lea     rcx, [rsp+1C0h+hLibModule]
0x14024f6a9  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@QEAA_NV?$basic_zstring_view@_W@wil@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool)
0x14024f6ae  test    al, al
0x14024f6b0  jnz     short loc_14024F6BB
0x14024f6b2  mov     [rdi+8], r14b
0x14024f6b6  jmp     loc_14024F7AA
0x14024f6bb  mov     [rsp+1C0h+pv], r14
0x14024f6c0  lea     rdx, aWindirSystem32_2; "%WINDIR%\\System32\\TestProvider.dll"
0x14024f6c7  lea     rcx, [rsp+1C0h+pv]
0x14024f6cc  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x14024f6d1  nop
0x14024f6d2  xor     edx, edx; Val
0x14024f6d4  mov     r8d, 110h; Size
0x14024f6da  lea     rcx, [rbp+0C0h+var_130]; void *
0x14024f6de  call    memset
0x14024f6e3  mov     rdx, [rsp+1C0h+pv]
0x14024f6e8  lea     rcx, [rbp+0C0h+var_130]
0x14024f6ec  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x14024f6f1  mov     rax, [rbp+0C0h+var_130]
0x14024f6f5  movsxd  rcx, dword ptr [rax+4]
0x14024f6f9  cmp     [rbp+rcx+0C0h+var_120], r14d
0x14024f6fe  lea     rcx, [rbp+0C0h+var_80]
0x14024f702  jz      short loc_14024F723
0x14024f704  mov     [rdi+8], r14b
0x14024f708  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x14024f70d  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x14024f714  mov     [rbp+0C0h+var_80], rax
0x14024f718  lea     rcx, [rbp+0C0h+var_80]; this
0x14024f71c  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x14024f721  jmp     short loc_14024F799
0x14024f723  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x14024f728  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x14024f72f  mov     [rbp+0C0h+var_80], rax
0x14024f733  lea     rcx, [rbp+0C0h+var_80]; this
0x14024f737  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x14024f73c  mov     [rsp+1C0h+hLibModule], r14
0x14024f741  lea     rdx, [rsp+1C0h+hLibModule]
0x14024f746  call    ?GetSelfHostDll@TestHooks@Windows@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::TestHooks::GetSelfHostDll(void)
0x14024f74b  nop
0x14024f74c  mov     rbx, [rsp+1C0h+hLibModule]
0x14024f751  test    rbx, rbx
0x14024f754  setnz   sil
0x14024f758  test    rbx, rbx
0x14024f75b  jnz     short loc_14024F7D0
0x14024f75d  mov     rax, [rsp+1C0h+pv]
0x14024f762  mov     rcx, r15
0x14024f765  inc     rcx
0x14024f768  cmp     [rax+rcx*2], r14w
0x14024f76d  jnz     short loc_14024F765
0x14024f76f  mov     [rsp+1C0h+var_180], rax
0x14024f774  mov     [rsp+1C0h+var_178], rcx
0x14024f779  lea     rcx, [rsp+1C0h+var_180]
0x14024f77e  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x14024f783  test    al, al
0x14024f785  jnz     short loc_14024F7D0
0x14024f787  mov     [rdi+8], r14b
0x14024f78b  test    sil, sil
0x14024f78e  jz      short loc_14024F799
0x14024f790  xor     ecx, ecx; hLibModule
0x14024f792  call    cs:__imp_FreeLibrary
0x14024f798  nop
0x14024f799  mov     rcx, [rsp+1C0h+pv]; pv
0x14024f79e  test    rcx, rcx
0x14024f7a1  jz      short loc_14024F7AA
0x14024f7a3  call    cs:__imp_CoTaskMemFree
0x14024f7a9  nop
0x14024f7aa  sub     cs:dword_1405077FC, 1
0x14024f7b1  jnz     loc_14024F89C
0x14024f7b7  mov     cs:dword_1405077F8, r15d
0x14024f7be  lea     rcx, stru_1405077C0; SRWLock
0x14024f7c5  call    cs:__imp_ReleaseSRWLockExclusive
0x14024f7cb  jmp     loc_14024F89C
0x14024f7d0  mov     rcx, [rsp+1C0h+pv]; lpLibFileName
0x14024f7d5  call    cs:__imp_LoadLibraryW
0x14024f7db  mov     [rsp+1C0h+var_160], rax
0x14024f7e0  mov     rcx, [rbp+0C8h]; this
0x14024f7e7  test    rax, rax
0x14024f7ea  jz      loc_14024F904
0x14024f7f0  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hLibModule
0x14024f7f7  mov     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rax; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x14024f7fe  test    rcx, rcx
0x14024f801  jz      short loc_14024F80A
0x14024f803  call    cs:__imp_FreeLibrary
0x14024f809  nop
0x14024f80a  test    sil, sil
0x14024f80d  jz      short loc_14024F819
0x14024f80f  mov     rcx, rbx; hLibModule
0x14024f812  call    cs:__imp_FreeLibrary
0x14024f818  nop
0x14024f819  mov     rcx, [rsp+1C0h+pv]; pv
0x14024f81e  test    rcx, rcx
0x14024f821  jz      short loc_14024F829
0x14024f823  call    cs:__imp_CoTaskMemFree
0x14024f829  mov     eax, cs:dword_1405077FC
0x14024f82f  sub     eax, 1
0x14024f832  mov     cs:dword_1405077FC, eax
0x14024f838  jnz     short loc_14024F84E
0x14024f83a  mov     cs:dword_1405077F8, r15d
0x14024f841  lea     rcx, stru_1405077C0; SRWLock
0x14024f848  call    cs:__imp_ReleaseSRWLockExclusive
0x14024f84e  lea     rdx, aGettestprovide; "GetTestProvider"
0x14024f855  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x14024f85c  call    cs:__imp_GetProcAddress
0x14024f862  test    rax, rax
0x14024f865  jz      loc_14024F916
0x14024f86b  lea     rcx, [rsp+1C0h+pv]
0x14024f870  call    _guard_dispatch_icall
0x14024f875  mov     rcx, [rax]
0x14024f878  mov     [rax], r14
0x14024f87b  mov     [rdi], rcx
0x14024f87e  mov     byte ptr [rdi+8], 1
0x14024f882  mov     rcx, [rsp+1C0h+pv]
0x14024f887  test    rcx, rcx
0x14024f88a  jz      short loc_14024F89C
0x14024f88c  mov     r8, [rcx]
0x14024f88f  mov     edx, 1
0x14024f894  mov     rax, [r8]
0x14024f897  call    _guard_dispatch_icall
0x14024f89c  mov     rax, rdi
0x14024f89f  mov     rcx, [rbp+0C0h+var_20]
0x14024f8a6  xor     rcx, rsp; StackCookie
0x14024f8a9  call    __security_check_cookie
0x14024f8ae  lea     r11, [rsp+1C0h+var_10]
0x14024f8b6  mov     rbx, [r11+20h]
0x14024f8ba  mov     rsi, [r11+30h]
0x14024f8be  mov     rdi, [r11+38h]
0x14024f8c2  mov     rsp, r11
0x14024f8c5  pop     r15
0x14024f8c7  pop     r14
0x14024f8c9  pop     rbp
0x14024f8ca  retn
0x14024f8cb  mov     rcx, [rbp+0C8h]; this
0x14024f8d2  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14024f8d9  mov     edx, 0C9h; void *
0x14024f8de  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14024f8e4  mov     ecx, 5; int
0x14024f8e9  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14024f8ef  mov     cs:dword_1405077FC, 7FFFFFFEh
0x14024f8f9  mov     ecx, 6; int
0x14024f8fe  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14024f904  lea     r8, aCW1SSrcOrchest_52; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024f90b  mov     edx, 140h; void *
0x14024f910  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024f916  mov     rcx, [rbp+0C8h]; this
0x14024f91d  lea     r8, aCW1SSrcOrchest_52; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14024f924  mov     edx, 148h; void *
0x14024f929  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
