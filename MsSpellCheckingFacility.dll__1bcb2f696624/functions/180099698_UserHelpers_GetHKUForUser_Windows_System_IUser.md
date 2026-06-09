# UserHelpers::GetHKUForUser(Windows::System::IUser *)

- ea: `0x180099698`
- end: `0x18009974b`
- name: `?GetHKUForUser@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180043568`

## callees

- `0x1800437d8`
- `0x180044a24`
- `0x180044a88`
- `0x180098228`
- `0x180099698`
- `0x18009b470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800996e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800996e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009971a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009971a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHKEY __fastcall UserHelpers::GetHKUForUser(PHKEY phkResult, UserHelpers *a2)
{
  const WCHAR *v3; // rdx
  HKEY v4; // rdi
  unsigned int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+18h] BYREF
  char v12; // [rsp+68h] [rbp+20h] BYREF

  *phkResult = 0;
  UserHelpers::GetUserSidString((LPWSTR *)&lpSubKey, a2);
  v3 = lpSubKey;
  if ( lpSubKey )
  {
    v4 = *phkResult;
    if ( *phkResult )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      RegCloseKey(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
      v3 = lpSubKey;
    }
    *phkResult = 0;
    v5 = RegOpenKeyExW(HKEY_USERS, v3, 0, 0xF003Fu, phkResult);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v6, v7, (const char *)v5, phkResulta);
  }
  wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&lpSubKey);
  return phkResult;
}

```

## disassembly

```asm
0x180099698  mov     rax, rsp
0x18009969b  mov     [rax+10h], rbx
0x18009969f  mov     [rax+8], rcx
0x1800996a3  push    rdi
0x1800996a4  sub     rsp, 40h
0x1800996a8  mov     rbx, rcx
0x1800996ab  mov     dword ptr [rax-18h], 0
0x1800996b2  mov     qword ptr [rcx], 0
0x1800996b9  mov     dword ptr [rax-18h], 1
0x1800996c0  lea     rcx, [rax+18h]; StringSid
0x1800996c4  call    ?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserSidString(Windows::System::IUser *)
0x1800996c9  nop
0x1800996ca  mov     rdx, [rsp+48h+lpSubKey]
0x1800996cf  test    rdx, rdx
0x1800996d2  jz      short loc_180099732
0x1800996d4  mov     rdi, [rbx]
0x1800996d7  test    rdi, rdi
0x1800996da  jz      short loc_1800996FE
0x1800996dc  lea     rcx, [rsp+48h+arg_18]; this
0x1800996e1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800996e6  mov     rcx, rdi; hKey
0x1800996e9  call    cs:__imp_RegCloseKey
0x1800996ef  lea     rcx, [rsp+48h+arg_18]; this
0x1800996f4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800996f9  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x1800996fe  mov     qword ptr [rbx], 0
0x180099705  mov     qword ptr [rsp+48h+phkResult], rbx; unsigned int
0x18009970a  mov     r9d, 0F003Fh; samDesired
0x180099710  xor     r8d, r8d; ulOptions
0x180099713  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18009971a  call    cs:__imp_RegOpenKeyExW
0x180099720  mov     rcx, [rsp+48h]; this
0x180099725  test    eax, eax
0x180099727  jz      short loc_180099732
0x180099729  mov     r9d, eax; char *
0x18009972c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180099732  lea     rcx, [rsp+48h+lpSubKey]
0x180099737  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x18009973c  mov     rax, rbx
0x18009973f  mov     rbx, [rsp+48h+arg_8]
0x180099744  add     rsp, 40h
0x180099748  pop     rdi
0x180099749  retn
```
