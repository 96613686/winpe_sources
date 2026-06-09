# UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)

- ea: `0x1800136c0`
- end: `0x180013a5b`
- name: `?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z`
- size: `923`
- prototype: `__int128 *__fastcall(__int128 *, UserHelpers *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001442c`
- `0x180014c20`
- `0x1800153f0`
- `0x180015de4`

## callees

- `0x180001a30`
- `0x18000868c`
- `0x18000cd18`
- `0x18000cef4`
- `0x1800124d8`
- `0x1800136c0`
- `0x18001486c`
- `0x180014a04`
- `0x180015a4c`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001385b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013979`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001385b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001394b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001394b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013885`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013885`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a0`

## string_xrefs

- `0x180013a40`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
__int128 *__fastcall UserHelpers::UserCache::CacheForUser(__int128 *a1, UserHelpers *a2)
{
  _QWORD *UserTokenHandle; // rbx
  HKEY v5; // rax
  HKEY v6; // rcx
  volatile signed __int32 *v7; // rbx
  char **UserSidString; // rax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  WCHAR *v11; // rcx
  HKEY v12; // r14
  DWORD LastError; // ebx
  unsigned int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  volatile signed __int32 *v19; // rbx
  __int64 (__fastcall *v20)(UserHelpers *, HSTRING *); // r15
  HSTRING v21; // r14
  DWORD v22; // ebx
  int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-69h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v28; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v29[4]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v30; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string[2]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  hObject[0] = a1;
  v28 = 0;
  v29[3] = 7;
  v29[2] = 0;
  LOWORD(v29[0]) = 0;
  v30 = 0;
  string[0] = 0;
  UserTokenHandle = (_QWORD *)UserHelpers::GetUserTokenHandle(hObject, a2);
  v5 = (HKEY)operator new(0x18u);
  v6 = v5;
  hKey[0] = v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = 1;
    *((_DWORD *)v5 + 3) = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
    *((_QWORD *)v5 + 2) = *UserTokenHandle;
    *UserTokenHandle = 0;
  }
  else
  {
    v6 = 0;
  }
  hKey[1] = 0;
  hKey[0] = 0;
  v7 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  *((_QWORD *)&v28 + 1) = v6;
  *(_QWORD *)&v28 = v6 + 4;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  UserSidString = (char **)UserHelpers::GetUserSidString((LPWSTR *)hObject);
  v9 = *UserSidString;
  if ( *(_WORD *)*UserSidString )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v9[2 * v10] );
  }
  else
  {
    v10 = 0;
  }
  std::wstring::assign(v29, v9, v10);
  if ( hObject[0] )
    LocalFree(hObject[0]);
  hKey[0] = 0;
  UserHelpers::GetUserSidString((LPWSTR *)hObject);
  v11 = (WCHAR *)hObject[0];
  if ( hObject[0] )
  {
    v12 = hKey[0];
    if ( hKey[0] )
    {
      LastError = GetLastError();
      RegCloseKey(v12);
      SetLastError(LastError);
      v11 = (WCHAR *)hObject[0];
    }
    hKey[0] = 0;
    v14 = RegOpenKeyExW(HKEY_USERS, v11, 0, 0xF003Fu, hKey);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v15, v16, (const char *)v14, phkResult);
    v11 = (WCHAR *)hObject[0];
  }
  if ( v11 )
    LocalFree(v11);
  v17 = operator new(0x18u);
  v18 = v17;
  hObject[0] = v17;
  if ( v17 )
  {
    *((_DWORD *)v17 + 2) = 1;
    *((_DWORD *)v17 + 3) = 1;
    *v17 = &std::_Ref_count_obj<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::`vftable';
    v17[2] = hKey[0];
    hKey[0] = 0;
  }
  else
  {
    v18 = 0;
  }
  hObject[1] = 0;
  hObject[0] = 0;
  v19 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  *((_QWORD *)&v30 + 1) = v18;
  *(_QWORD *)&v30 = v18 + 2;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( a2 )
  {
    v20 = *(__int64 (__fastcall **)(UserHelpers *, HSTRING *))(*(_QWORD *)a2 + 48LL);
    v21 = string[0];
    if ( string[0] )
    {
      v22 = GetLastError();
      WindowsDeleteString(v21);
      SetLastError(v22);
    }
    string[0] = 0;
    v23 = v20(a2, string);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x144,
        (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
        (const char *)(unsigned int)v23,
        phkResult);
  }
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  if ( a1 != &v28 )
  {
    *((_QWORD *)a1 + 1) = *((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = 0;
    *(_QWORD *)a1 = v28;
    *(_QWORD *)&v28 = 0;
  }
  std::wstring::wstring(a1 + 1, v29);
  *((_QWORD *)a1 + 6) = 0;
  *((_QWORD *)a1 + 7) = 0;
  if ( a1 + 3 != &v30 )
  {
    *((_QWORD *)a1 + 7) = *((_QWORD *)&v30 + 1);
    *((_QWORD *)&v30 + 1) = 0;
    *((_QWORD *)a1 + 6) = v30;
    *(_QWORD *)&v30 = 0;
  }
  *((HSTRING *)a1 + 8) = string[0];
  string[0] = 0;
  UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)&v28);
  return a1;
}

```

## disassembly

```asm
0x1800136c0  mov     [rsp-8+arg_10], rbx
0x1800136c5  mov     [rsp-8+arg_18], rsi
0x1800136ca  push    rbp
0x1800136cb  push    rdi
0x1800136cc  push    r12
0x1800136ce  push    r14
0x1800136d0  push    r15
0x1800136d2  lea     rbp, [rsp-37h]
0x1800136d7  sub     rsp, 0C0h
0x1800136de  mov     rax, cs:__security_cookie
0x1800136e5  xor     rax, rsp
0x1800136e8  mov     [rbp+57h+var_30], rax
0x1800136ec  mov     rsi, rdx
0x1800136ef  mov     rdi, rcx
0x1800136f2  mov     [rbp+57h+hObject], rcx
0x1800136f6  xor     r12d, r12d
0x1800136f9  mov     [rbp+57h+var_B0], r12d
0x1800136fd  xorps   xmm0, xmm0
0x180013700  movdqa  [rbp+57h+var_80], xmm0
0x180013705  mov     [rbp+57h+var_58], 7
0x18001370d  mov     [rbp+57h+var_60], r12
0x180013711  mov     [rbp+57h+var_70], r12w
0x180013716  movdqa  [rbp+57h+var_50], xmm0
0x18001371b  mov     [rbp+57h+string], r12
0x18001371f  lea     rcx, [rbp+57h+hObject]; TokenHandle
0x180013723  call    ?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserTokenHandle(Windows::System::IUser *)
0x180013728  mov     rbx, rax
0x18001372b  lea     ecx, [r12+18h]; Size
0x180013730  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013735  mov     rcx, rax
0x180013738  mov     [rbp+57h+hKey], rax
0x18001373c  test    rax, rax
0x18001373f  jz      short loc_180013765
0x180013741  mov     dword ptr [rax+8], 1
0x180013748  mov     dword ptr [rax+0Ch], 1
0x18001374f  lea     rax, ??_7?$_Ref_count_obj@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x180013756  mov     [rcx], rax
0x180013759  mov     rax, [rbx]
0x18001375c  mov     [rcx+10h], rax
0x180013760  mov     [rbx], r12
0x180013763  jmp     short loc_180013768
0x180013765  mov     rcx, r12
0x180013768  mov     [rbp+57h+var_B0], 2
0x18001376f  mov     [rbp+57h+var_88], r12
0x180013773  mov     [rbp+57h+hKey], r12
0x180013777  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x18001377b  mov     qword ptr [rbp+57h+var_80+8], rcx
0x18001377f  lea     rax, [rcx+10h]
0x180013783  mov     qword ptr [rbp+57h+var_80], rax
0x180013787  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001378b  test    rbx, rbx
0x18001378e  jz      short loc_1800137C8
0x180013790  mov     eax, r15d
0x180013793  lock xadd [rbx+8], eax
0x180013798  add     eax, r15d
0x18001379b  jnz     short loc_1800137C8
0x18001379d  mov     rax, [rbx]
0x1800137a0  mov     rcx, rbx
0x1800137a3  mov     rax, [rax]
0x1800137a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ab  mov     eax, r15d
0x1800137ae  lock xadd [rbx+0Ch], eax
0x1800137b3  add     eax, r15d
0x1800137b6  jnz     short loc_1800137C8
0x1800137b8  mov     rax, [rbx]
0x1800137bb  mov     rcx, rbx
0x1800137be  mov     rax, [rax+8]
0x1800137c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137c7  nop
0x1800137c8  mov     rcx, [rbp+57h+hObject]; hObject
0x1800137cc  lea     rax, [rcx-1]
0x1800137d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800137d4  ja      short loc_1800137DC
0x1800137d6  call    cs:__imp_CloseHandle
0x1800137dc  mov     rdx, rsi
0x1800137df  lea     rcx, [rbp+57h+hObject]; StringSid
0x1800137e3  call    ?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserSidString(Windows::System::IUser *)
0x1800137e8  nop
0x1800137e9  mov     rdx, [rax]; Src
0x1800137ec  cmp     [rdx], r12w
0x1800137f0  jnz     short loc_1800137F7
0x1800137f2  mov     r8, r12
0x1800137f5  jmp     short loc_180013804
0x1800137f7  mov     r8, r15
0x1800137fa  inc     r8
0x1800137fd  cmp     [rdx+r8*2], r12w
0x180013802  jnz     short loc_1800137FA
0x180013804  lea     rcx, [rbp+57h+var_70]; void *
0x180013808  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001380d  nop
0x18001380e  mov     rcx, [rbp+57h+hObject]; hMem
0x180013812  test    rcx, rcx
0x180013815  jz      short loc_18001381E
0x180013817  call    cs:__imp_LocalFree
0x18001381d  nop
0x18001381e  mov     [rbp+57h+hKey], r12
0x180013822  mov     [rbp+57h+var_B0], 4
0x180013829  mov     rdx, rsi
0x18001382c  lea     rcx, [rbp+57h+hObject]; StringSid
0x180013830  call    ?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserSidString(Windows::System::IUser *)
0x180013835  nop
0x180013836  mov     rcx, [rbp+57h+hObject]
0x18001383a  test    rcx, rcx
0x18001383d  jz      short loc_18001389B
0x18001383f  mov     r14, [rbp+57h+hKey]
0x180013843  test    r14, r14
0x180013846  jz      short loc_180013865
0x180013848  call    cs:__imp_GetLastError
0x18001384e  mov     ebx, eax
0x180013850  mov     rcx, r14; hKey
0x180013853  call    cs:__imp_RegCloseKey
0x180013859  mov     ecx, ebx; dwErrCode
0x18001385b  call    cs:__imp_SetLastError
0x180013861  mov     rcx, [rbp+57h+hObject]
0x180013865  mov     [rbp+57h+hKey], r12
0x180013869  lea     rax, [rbp+57h+hKey]
0x18001386d  mov     qword ptr [rsp+0E0h+phkResult], rax; unsigned int
0x180013872  mov     r9d, 0F003Fh; samDesired
0x180013878  xor     r8d, r8d; ulOptions
0x18001387b  mov     rdx, rcx; lpSubKey
0x18001387e  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180013885  call    cs:__imp_RegOpenKeyExW
0x18001388b  mov     rcx, [rbp+5Fh]; this
0x18001388f  test    eax, eax
0x180013891  jnz     loc_180013A52
0x180013897  mov     rcx, [rbp+57h+hObject]; hMem
0x18001389b  test    rcx, rcx
0x18001389e  jz      short loc_1800138A7
0x1800138a0  call    cs:__imp_LocalFree
0x1800138a6  nop
0x1800138a7  mov     ecx, 18h; Size
0x1800138ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800138b1  mov     rcx, rax
0x1800138b4  mov     [rbp+57h+hObject], rax
0x1800138b8  test    rax, rax
0x1800138bb  jz      short loc_1800138E3
0x1800138bd  mov     dword ptr [rax+8], 1
0x1800138c4  mov     dword ptr [rax+0Ch], 1
0x1800138cb  lea     rax, ??_7?$_Ref_count_obj@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::`vftable'
0x1800138d2  mov     [rcx], rax
0x1800138d5  mov     rax, [rbp+57h+hKey]
0x1800138d9  mov     [rcx+10h], rax
0x1800138dd  mov     [rbp+57h+hKey], r12
0x1800138e1  jmp     short loc_1800138E6
0x1800138e3  mov     rcx, r12
0x1800138e6  mov     [rbp+57h+var_B0], 0Ch
0x1800138ed  mov     [rbp+57h+var_98], r12
0x1800138f1  mov     [rbp+57h+hObject], r12
0x1800138f5  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x1800138f9  mov     qword ptr [rbp+57h+var_50+8], rcx
0x1800138fd  lea     rax, [rcx+10h]
0x180013901  mov     qword ptr [rbp+57h+var_50], rax
0x180013905  test    rbx, rbx
0x180013908  jz      short loc_180013942
0x18001390a  mov     eax, r15d
0x18001390d  lock xadd [rbx+8], eax
0x180013912  add     eax, r15d
0x180013915  jnz     short loc_180013942
0x180013917  mov     rax, [rbx]
0x18001391a  mov     rcx, rbx
0x18001391d  mov     rax, [rax]
0x180013920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013925  mov     eax, r15d
0x180013928  lock xadd [rbx+0Ch], eax
0x18001392d  add     eax, r15d
0x180013930  jnz     short loc_180013942
0x180013932  mov     rax, [rbx]
0x180013935  mov     rcx, rbx
0x180013938  mov     rax, [rax+8]
0x18001393c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013941  nop
0x180013942  mov     rcx, [rbp+57h+hKey]; hKey
0x180013946  test    rcx, rcx
0x180013949  jz      short loc_180013951
0x18001394b  call    cs:__imp_RegCloseKey
0x180013951  test    rsi, rsi
0x180013954  jz      short loc_18001399E
0x180013956  mov     rax, [rsi]
0x180013959  mov     r15, [rax+30h]
0x18001395d  mov     r14, [rbp+57h+string]
0x180013961  test    r14, r14
0x180013964  jz      short loc_18001397F
0x180013966  call    cs:__imp_GetLastError
0x18001396c  mov     ebx, eax
0x18001396e  mov     rcx, r14; string
0x180013971  call    cs:__imp_WindowsDeleteString
0x180013977  mov     ecx, ebx; dwErrCode
0x180013979  call    cs:__imp_SetLastError
0x18001397f  mov     [rbp+57h+string], r12
0x180013983  lea     rdx, [rbp+57h+string]
0x180013987  mov     rcx, rsi
0x18001398a  mov     rax, r15
0x18001398d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013992  mov     rcx, [rbp+5Fh]; this
0x180013996  test    eax, eax
0x180013998  js      loc_180013A3D
0x18001399e  mov     [rdi], r12
0x1800139a1  mov     [rdi+8], r12
0x1800139a5  lea     rax, [rbp+57h+var_80]
0x1800139a9  cmp     rdi, rax
0x1800139ac  jz      short loc_1800139C5
0x1800139ae  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800139b2  mov     [rdi+8], rax
0x1800139b6  mov     qword ptr [rbp+57h+var_80+8], r12
0x1800139ba  mov     rax, qword ptr [rbp+57h+var_80]
0x1800139be  mov     [rdi], rax
0x1800139c1  mov     qword ptr [rbp+57h+var_80], r12
0x1800139c5  lea     rcx, [rdi+10h]
0x1800139c9  lea     rdx, [rbp+57h+var_70]
0x1800139cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800139d2  lea     rdx, [rdi+30h]
0x1800139d6  mov     [rdx], r12
0x1800139d9  mov     [rdx+8], r12
0x1800139dd  lea     rax, [rbp+57h+var_50]
0x1800139e1  cmp     rdx, rax
0x1800139e4  jz      short loc_1800139FD
0x1800139e6  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x1800139ea  mov     [rdx+8], rcx
0x1800139ee  mov     qword ptr [rbp+57h+var_50+8], r12
0x1800139f2  mov     rcx, qword ptr [rbp+57h+var_50]
0x1800139f6  mov     [rdx], rcx
0x1800139f9  mov     qword ptr [rbp+57h+var_50], r12
0x1800139fd  mov     rcx, [rbp+57h+string]
0x180013a01  mov     [rdi+40h], rcx
0x180013a05  mov     [rbp+57h+string], r12
0x180013a09  lea     rcx, [rbp+57h+var_80]; this
0x180013a0d  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x180013a12  mov     rax, rdi
0x180013a15  mov     rcx, [rbp+57h+var_30]
0x180013a19  xor     rcx, rsp; StackCookie
0x180013a1c  call    __security_check_cookie
0x180013a21  lea     r11, [rsp+0E0h+var_20]
0x180013a29  mov     rbx, [r11+40h]
0x180013a2d  mov     rsi, [r11+48h]
0x180013a31  mov     rsp, r11
0x180013a34  pop     r15
0x180013a36  pop     r14
0x180013a38  pop     r12
0x180013a3a  pop     rdi
0x180013a3b  pop     rbp
0x180013a3c  retn
0x180013a3d  mov     r9d, eax; char *
0x180013a40  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180013a47  mov     edx, 144h; void *
0x180013a4c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013a52  mov     r9d, eax; char *
0x180013a55  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
